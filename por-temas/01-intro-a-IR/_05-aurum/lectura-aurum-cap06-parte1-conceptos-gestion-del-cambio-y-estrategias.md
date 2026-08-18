# Lectura en español — Cap. 6 · Parte 1: Conceptos, gestión del cambio y estrategias

> **Origen.** Capítulo 6, secciones 6.1 y 6.2, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Per Jönsson** (Instituto Tecnológico de Blekinge, Suecia) y **Mikael Lindvall** (Fraunhofer Center, Maryland).
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.

---

## Por qué este capítulo tiene más para vos de lo que parece

El análisis de impacto no está en tu cronograma. Pero este capítulo trae dos cosas que sí valen:

1. **Un marco completo de gestión del cambio**, con cinco piezas nombradas, que es de lo mejor explicado del libro.
2. **El mejor argumento del libro entero sobre por qué la ambigüedad cuesta plata.** Aparece dos veces: en los vínculos de trazabilidad sin semántica, y en la documentación de diseño ambigua. Los dos casos muestran la misma mecánica — una relación que se puede interpretar de dos maneras produce dos estimaciones de impacto distintas, y una de las dos está mal.

Y en la Parte 2 hay una sección sobre requisitos no funcionales que se conecta directo con las clases 06 y 07.

---

## 1. Introducción 🟡

### El problema: el software se deteriora

> **El cambio es una propiedad inescapable de cualquier software.** Pero los cambios pueden, y van a, si no se controlan apropiadamente, **llevar al deterioro del software**.

Los autores acumulan evidencia:

- Cuando se analizaron los **2.000.000 de líneas de código de Mozilla**, hubo **indicios fuertes de que el software se había deteriorado significativamente por cambio no controlado**, volviéndolo muy difícil de mantener.
- Un sistema de telecomunicaciones de **100.000.000 de líneas y quince años de antigüedad**, analizado a lo largo de varias versiones, **se había degradado por el cambio frecuente**. Los programadores que estimaban el esfuerzo de cambio concluyeron que **el código era más difícil de cambiar de lo que debería ser**.

### Por qué se deteriora 🔴

> **El deterioro ocurre en muchos casos porque los cambios al software rara vez tienen el impacto chico que se cree que tienen.**

Dos datos que lo respaldan:

**1.** En 1983, **algunos de los errores de programación más caros del mundo involucraron cada uno el cambio de un solo dígito** en un programa previamente correcto. Un cambio aparentemente trivial puede tener un impacto inmenso.

**2.** Un estudio de fines de los 90 mostró que los profesionales que hacían análisis de impacto y estimaban el cambio en un proyecto industrial **subestimaron la cantidad de cambio por un factor de tres**.

### La definición 🔴

La definición canónica, de Bohner y Arnold:

> **Análisis de impacto: la actividad de identificar las consecuencias potenciales —incluyendo efectos colaterales y efectos de propagación— de un cambio, o de estimar qué necesita modificarse para lograr un cambio, antes de haberlo hecho.**

**Para qué sirve la salida:** como base para **estimar el costo asociado al cambio**. Y ese costo sirve para **decidir si implementarlo o no**, según su relación costo/beneficio.

### Su lugar en la ingeniería de requisitos 🔴

> **El análisis de impacto es una parte importante de la IR, porque los cambios al software a menudo se inician por cambios en los requisitos.**

Y una crítica a la bibliografía: en los libros de texto de IR, el análisis de impacto **se reconoce como actividad esencial de la gestión del cambio, pero los detalles de cómo hacerlo suelen quedar afuera**, o limitarse a razonar sobre el impacto del cambio en la especificación de requisitos.

Los autores señalan además una asimetría curiosa: **pese a su lugar natural en la IR, la investigación sobre análisis de impacto se encuentra más comúnmente en la literatura de mantenimiento de software.** Este capítulo lo presenta desde la perspectiva de requisitos.

### En qué fase se hace 🔴

La experiencia de los autores: **es parte integral de cada fase del desarrollo.** Y lo que cambia es a qué afecta:

```
   FASE                        QUÉ SE VE AFECTADO POR UN
                               REQUISITO NUEVO O CAMBIADO
   ─────────────────────────────────────────────────────
   Desarrollo de requisitos  → solo los requisitos existentes
   (no existen diseño ni código)

   Diseño                    → requisitos + diseño
   (no existe código)

   Implementación            → requisitos + diseño + código
```

Y una aclaración: en procesos de desarrollo menos idealizados, **la situación se mantiene igual — los cambios de requisitos afectan a todas las representaciones existentes del sistema.**

---

## 2. Los conceptos que hay que tener 🔴

### 2.1 Objetos del ciclo de vida (SLO)

> **Un SLO** (*software life-cycle object*, también llamado producto de software o producto de trabajo) **es un artefacto producido durante un proyecto**: un requisito, un componente arquitectónico, una clase, y así.

Los SLO están **conectados entre sí por una red de relaciones**, que pueden ser:

- **entre SLO del mismo tipo** — dos requisitos interconectados para señalar que se relacionan;
- **entre SLO de tipos distintos** — un requisito conectado a un componente arquitectónico, para señalar que el componente lo implementa.

> Es el mismo vocabulario del capítulo 5 visto desde otro lado: allá se hablaba de objetos de información relacionados por trazabilidad; acá se los nombra SLO y se los usa para medir impacto.

### 2.2 Los dos tipos de análisis 🔴

El análisis de impacto se hace a menudo **analizando las relaciones** entre entidades del sistema. Hay dos tipos:

| | **Análisis de dependencias** | **Análisis de trazabilidad** |
|---|---|---|
| **Qué analiza** | Relaciones detalladas **entre entidades de programa** — variables, funciones — **extraídas del código fuente** | Relaciones **identificadas durante el desarrollo entre todos los tipos de SLO** |
| **Alcance** | Bajo nivel, muy fino | Requisitos, componentes arquitectónicos, documentación, etc. |
| **Cuándo se puede usar** | Solo cuando existe código | **Desde fases tempranas** |

> **El análisis de trazabilidad tiene una aplicación más amplia dentro de la IR**: puede usarse en fases más tempranas y puede identificar impacto más diverso, en términos de distintos tipos de SLO.

### 2.3 Los cuatro conjuntos de impacto 🔴

Este es el vocabulario central del capítulo. Cuatro conjuntos, definidos por Arnold y Bohner:

| Conjunto | Qué contiene |
|---|---|
| **Conjunto del Sistema** | **Todos los SLO del sistema.** Los otros tres son subconjuntos de este |
| **Conjunto de Impacto Inicial (SIS)** | Los objetos que **inicialmente se cree que van a cambiar**. Suele ser la entrada de los métodos de análisis |
| **Conjunto de Impacto Estimado (EIS)** | **Siempre incluye al SIS**; puede verse como su expansión. La expansión resulta de **aplicar reglas de propagación del cambio repetidamente** hasta descubrir todos los objetos que pueden verse afectados |
| **Conjunto de Impacto Real (AIS)** | Los SLO que **efectivamente resultaron afectados** una vez implementado el cambio |

**Los dos escenarios ideales:**

```
   SIS = EIS  ──► IDEAL: el impacto se limita a lo que
                  inicialmente se creyó que iba a cambiar

   EIS = AIS  ──► MEJOR CASO: la estimación del impacto
                  fue perfecta
```

Además de los conjuntos, hacen falta **dos formas de información** para determinar el impacto de un cambio:

1. **Información sobre las dependencias entre objetos** — capturada a menudo como referencias entre ellos.
2. **Conocimiento sobre cómo se propaga el cambio** de objeto a objeto vía dependencias y vínculos de trazabilidad — expresado a menudo como reglas o algoritmos.

### 2.4 Cambio primario y secundario 🔴

| | **Cambio primario** (impacto directo) | **Cambio secundario** (impacto indirecto) |
|---|---|---|
| **Qué es** | Los SLO identificados al analizar cómo los efectos del cambio propuesto afectan al sistema | Los cambios que los primarios provocan |
| **Se puede automatizar** | **Difícilmente** — se basa principalmente en **la pericia humana** | Sí, en buena medida |

Y una observación honesta: **como el cambio primario es difícil de automatizar, hay poco en la literatura sobre cómo identificarlo.** Es más común encontrar discusiones sobre cómo los cambios primarios causan los secundarios.

#### Las dos formas del impacto indirecto 🔴

| | **Efectos colaterales** (*side effects*) | **Efectos de propagación** (*ripple effects*) |
|---|---|---|
| **Qué son** | **Comportamientos no intencionados** que resultan de las modificaciones necesarias para implementar el cambio | Efectos sobre algunas partes del sistema **causados por hacer cambios en otras partes** |
| **Qué hacer** | Afectan la estabilidad y la función del sistema, y **deben evitarse** | **No pueden evitarse** — son consecuencia de la estructura y la implementación del sistema. Pero **deben identificarse y contabilizarse** al implementar el cambio |

> La distinción es fina y vale: unos son errores que se cometieron y hay que no cometer; los otros son consecuencia estructural inevitable, y lo que se puede hacer es verlos venir.

### 2.5 Arquitectura de software 🟢

Los autores incluyen la definición porque los componentes arquitectónicos son un tipo de SLO:

> **Arquitectura de software: la estructura o estructuras del sistema, que comprenden elementos de software, las propiedades visibles externamente de esos elementos, y las relaciones entre ellos.**

**Por qué le interesa a este capítulo:** la arquitectura se diseña típicamente temprano en el proyecto, ocultando detalles de bajo nivel, y se refina iterativamente. Eso la vuelve interesante desde el punto de vista de la IR y del análisis de impacto, **porque puede usarse para hacer análisis de impacto temprano —aunque inicialmente grueso— de requisitos que cambian**.

---

## 3. Por qué cambian los requisitos 🔴

### Las cuatro causas

Según Leffingwell y Widrig, los factores que pueden provocar cambios en los requisitos, tanto en el desarrollo inicial como en la evolución:

**1. Cambia el problema que el sistema debe resolver** — por razones económicas, políticas o tecnológicas.

**2. Los usuarios cambian de opinión** sobre qué quieren que haga el sistema, **a medida que entienden mejor sus propias necesidades**. Puede pasar porque inicialmente estaban inseguros de lo que querían, o porque **entran usuarios nuevos en escena**.

**3. Cambia el entorno en el que reside el sistema** — por ejemplo, aumentos en velocidad y capacidad de las computadoras pueden **cambiar las expectativas** sobre el sistema.

**4. El sistema nuevo se desarrolla y se libera, y eso lleva a los usuarios a descubrir requisitos nuevos.**

Sobre este último, los autores insisten: **es real y es común.**

> Cuando el sistema nuevo se libera, los usuarios se dan cuenta de que quieren funcionalidades adicionales, que necesitan los datos presentados de otra manera, que aparecen necesidades de integrarlo con otros sistemas. **Así, el uso del propio sistema genera requisitos nuevos.**

Y citan las "leyes de la evolución del software": **un sistema debe adaptarse continuamente, o va a resultar progresivamente menos satisfactorio en su entorno.**

> ⚠️ **Cruce con la cátedra.** La causa 2 es la misma **paradoja de la volatilidad** que viste en el capítulo 4: elicitar bien hace pensar a la gente sobre su trabajo, y eso les cambia lo que quieren. Y la causa 4 la extiende: **entregar el sistema también genera requisitos**. La volatilidad no es un defecto del proceso; es lo que pasa cuando el proceso funciona.

### La frase que resume todo 🔴

Los autores citan a Maciaszek, y vale tenerla:

> **"El cambio no es una patada en los dientes; el cambio no gestionado sí."**

---

## 4. El marco de gestión del cambio 🔴

Leffingwell y Widrig discuten **cinco partes necesarias** de un proceso de gestión del cambio. Juntas forman un marco que le permite al equipo manejar los cambios de manera controlada.

### 4.1 Planificar para el cambio

Involucra **reconocer que los cambios ocurren y que son una parte necesaria del desarrollo** del sistema. Esa preparación es esencial para que los cambios se reciban y se manejen efectivamente.

> Suena obvio y no lo es. Un proceso que trata cada cambio como una excepción molesta no tiene ningún mecanismo listo cuando el cambio llega — y llega siempre.

### 4.2 Establecer una línea base de requisitos

Significa **crear una instantánea del conjunto actual de requisitos**. El punto de este paso es **permitir que los cambios posteriores se comparen contra un conjunto estable y conocido**.

### 4.3 Un canal único

Es necesario para asegurar que **ningún cambio se implemente en el sistema antes de haber sido examinado** por una persona o varias **que tengan en mente el sistema, el proyecto y el presupuesto**.

En organizaciones grandes, ese canal único suele ser un **comité de control de cambios (CCB)**.

### 4.4 Un sistema de control de cambios

Le permite al comité **reunir, seguir y evaluar el impacto** de los cambios. Un cambio debe evaluarse en términos de:

- **impacto sobre el costo y la funcionalidad**;
- **impacto sobre los interesados externos** (por ejemplo, los clientes);
- **potencial de desestabilizar el sistema**.

Y una advertencia: **si se pasa por alto lo último, el sistema probablemente se deteriore.**

### 4.5 Gestionar jerárquicamente 🔴

Esta es la más interesante, porque describe un antipatrón concreto:

> Gestionar jerárquicamente **derrota una línea de acción quizás demasiado común: un programador ambicioso introduce un cambio en el código, y olvida o pasa por alto el efecto potencial que ese cambio tiene sobre los casos de prueba, el diseño, la arquitectura, los requisitos, y así.**
>
> **Los cambios deberían introducirse de arriba hacia abajo, empezando por los requisitos.** Si los requisitos están descompuestos y vinculados a otros SLO, es posible propagar el cambio de manera controlada.

> ⚠️ **Cruce con la cátedra.** Es el mismo principio que la regla del café con leche, aplicado al cambio: **el movimiento correcto va del nivel alto hacia el detalle, nunca al revés.** Un cambio que entra por el código deja atrás una especificación que ya no describe al sistema — y a partir de ahí el documento miente.

### El proceso concreto de Kotonya y Sommerville 🟡

El marco anterior deja abierto cuál es el proceso real. El que proponen Kotonya y Sommerville es detallado:

```
   1. ANÁLISIS DEL PROBLEMA Y ESPECIFICACIÓN DEL CAMBIO

   2. ANÁLISIS DEL CAMBIO Y COSTEO
      2a. verificar la validez del pedido de cambio
      2b. encontrar los requisitos DIRECTAMENTE afectados   ◄── impacto
      2c. encontrar los requisitos DEPENDIENTES             ◄── impacto
      2d. proponer los cambios a los requisitos
      2e. evaluar los costos del cambio                     ◄── impacto
      2f. evaluar la aceptabilidad del costo

   3. IMPLEMENTACIÓN DEL CAMBIO
```

**El análisis de impacto se realiza en los pasos 2b, 2c y 2e**, identificando los requisitos y componentes afectados. **El análisis debe expresarse en términos de esfuerzo requerido, tiempo, dinero y recursos disponibles.**

Los autores de ese proceso sugieren usar **tablas de trazabilidad** para identificar y gestionar dependencias entre requisitos, y entre requisitos y elementos de diseño.

---

## 5. Historia del análisis de impacto 🟢

En algún sentido, el análisis de impacto **se viene haciendo desde hace muchísimo tiempo**, aunque no necesariamente con ese nombre y no necesariamente resolviendo el problema de determinar con precisión el efecto de un cambio.

Los hitos que menciona el capítulo:

| Año | Aporte |
|---|---|
| **1972** | El trabajo de **Haney sobre análisis de conexión de módulos** — considerado a menudo el primer paper sobre análisis de impacto. Se basa en la idea de que **cada par de módulos tiene una probabilidad de que un cambio en uno obligue a un cambio en el otro**. Puede modelar la propagación del cambio entre cualquier componente del sistema, incluidos los requisitos |
| **1979** | **Weiser introduce el rebanado de programas** (*program slicing*) |
| **1980** | **Yau y Collofello introducen la noción de efecto de propagación** (*ripple effect*), con modelos para determinar cómo un cambio en un área del código propaga y causa cambios en otras |
| **1984** | La **trazabilidad de requisitos queda definida** en el estándar ANSI/IEEE 830-1984 |
| **1996** | **Arnold y Bohner publican una colección** de artículos de investigación sobre el tema |

### La tendencia 🟡

Es posible identificar una tendencia clara a lo largo de los años:

```
   TEMPRANO ──────────────────────► HOY
   foco en el ANÁLISIS DE           necesidad de entender cómo los
   CÓDIGO FUENTE                    cambios afectan a OTROS SLO
   (slicing y ripple effects        además del código: requisitos,
    para código)                    diseño, documentación
```

**El argumento de Turver y Munro:** el código fuente **no es el único producto que hay que cambiar** para desarrollar una versión nueva. En un enfoque orientado a documentos, **muchos documentos también se ven afectados** por requisitos nuevos y cambiados. El manual de usuario es el ejemplo obvio: hay que actualizarlo cuando se proveen funcionalidades nuevas.

**Una observación honesta sobre el estado del campo.** Al leer la colección de 1996 casi diez años después, los autores notan que **sigue siendo muy relevante**: los papers publicados después parecen trabajar con las mismas ideas y técnicas. No lo dicen para depreciar el trabajo hecho, pero indica que **el campo no está en estado de cambio acelerado**. El foco sigue en **adaptar técnicas y estrategias existentes a conceptos y contextos nuevos**.

**El efecto Y2K.** Cuando se acercaba el año 2000, el problema del cambio de siglo **hizo obvio que hacían falta esfuerzos extensivos de análisis de impacto** para identificar el software y las partes de software que había que cambiar. Eso **funcionó como una revelación para muchas organizaciones** cuyo proceso no incluía análisis de impacto explícito.

**Hacia dónde va.** Los sistemas de hoy son mucho más complejos que hace 25 años, **y se volvió muy difícil captar las implicaciones combinadas de los requisitos y de sus relaciones con la arquitectura, el diseño y el código**. Las redes de dependencias de sistemas grandes pueden ser tan complejas que **hace falta visualizarlas de maneras novedosas** — hay investigación que combina análisis de impacto con **visualización 3D**. Y hace falta extender el análisis de impacto a **middleware, software COTS y aplicaciones web**, donde la complejidad se corre **de las dependencias internas de datos y control hacia las dependencias de interoperabilidad**, para las cuales las estrategias actuales no están bien adaptadas.

---

## 6. Las estrategias para hacer análisis de impacto 🔴

Las estrategias comunes son cuatro:

```
   · analizar información de trazabilidad o de dependencias
   · utilizar técnicas de rebanado (slicing)
   · consultar especificaciones de diseño y otra documentación
   · entrevistar a desarrolladores con conocimiento
```

Y se dividen en dos categorías:

| | **Automatizables** | **Manuales** |
|---|---|---|
| **Qué son** | Las que son **algorítmicas** en su naturaleza | Las que se realizan mejor **por personas**, no por herramientas |
| **Ventaja** | Estimación **muy fina y automatizada** | **Requieren menos infraestructura**; son **más fáciles de adoptar** porque necesitan menos entrada estructurada y no hay que desarrollar formas nuevas de SLO |
| **Desventaja** | Requieren **una infraestructura detallada** y a veces producen **demasiados falsos positivos** | Estimación **más gruesa** |

### La observación sobre optimismo y conservadurismo 🔴

Un estudio previo indicó algo importante:

> **Los análisis de impacto de los desarrolladores resultan a menudo en predicciones optimistas** — es decir, el conjunto de cambios predicho representa **la menor cantidad de trabajo posible**. Por lo tanto, **el trabajo no puede ser más fácil que eso, solo más difícil.**

El estudio identificó la necesidad de hacer también **predicciones conservadoras**, estableciendo un "nivel peor". **La cantidad real de trabajo va a caer entre el nivel optimista y el conservador.**

**El problema de la predicción conservadora:** como identifica una parte tan grande del sistema, **los desarrolladores a menudo no pueden creer que sea realista**.

**Su beneficio:** poder determinar **la predicción más probable en algún punto entre la optimista y la conservadora**.

> Un enfoque ideal de análisis de impacto **daría siempre una estimación optimista y una conservadora**. Recolectando y analizando datos empíricos de las predicciones y de los cambios reales, **puede establecerse en qué punto de ese rango cae la respuesta correcta.**

---

## 7. Estrategias automatizables 🟡

Emplean métodos algorítmicos para identificar la propagación del cambio y el impacto indirecto. Por ejemplo, **grafos de relaciones** entre requisitos y otros SLO pueden usarse con **algoritmos de grafos** para identificar el impacto de un cambio propuesto.

**Su prerrequisito:** una **especificación estructurada** del sistema. Estructurada significa **consistente, completa, y que incluya alguna información semántica** — por ejemplo, el tipo de relación.

**Su límite general:** son útiles para evaluar el **Conjunto de Impacto Estimado**, identificando cambios secundarios. **No son adecuadas para identificar impacto directo.**

### 7.1 Análisis de trazabilidad y de dependencias 🔴

#### Análisis de dependencias

Extrayendo dependencias del código fuente se pueden obtener **grafos de llamadas, estructuras de control, grafos de datos**.

**Su ventaja:** como el código fuente es **la representación más exacta del sistema**, cualquier análisis basado en él **puede predecir el impacto con mucha precisión**. Es además **la estrategia más madura** disponible.

**Sus dos desventajas:**

1. **El código no está disponible hasta tarde en el proyecto**, lo que vuelve al análisis de dependencias **estrecho en su campo de aplicación**.
2. **Los sistemas muy grandes tienen cantidades masivas de dependencias de código**, lo que vuelve la red **difícil de usar y de abarcar visualmente**.

#### Análisis de trazabilidad

Requiere la presencia de **vínculos de relación entre los SLO** analizados. Típicamente esas relaciones se capturan y especifican **progresivamente durante el desarrollo** — lo que se conoce como **trazabilidad pre-registrada**.

> **El éxito del análisis de trazabilidad depende fuertemente de la completitud y la consistencia de las relaciones identificadas.** Pero si la información se registra apropiadamente desde el comienzo, **el análisis puede ser muy potente.**

#### La matriz de trazabilidad 🟡

El enfoque común para registrar vínculos: **una matriz donde cada fila y cada columna corresponden a un SLO**. La relación entre dos SLO se expresa **poniendo una marca donde se cruzan la fila del primero y la columna del segundo**.

También es posible **agregar información semántica** a la relación. Por ejemplo, la relación entre un requisito y un componente arquitectónico puede expandirse para incluir si el componente **implementa el requisito enteramente o solo parcialmente**.

### 7.2 El problema de los vínculos sin semántica 🔴

Esta es la parte más aprovechable de la sección, y es un caso de ambigüedad de manual.

Ramesh y Jarke reportan que **las prácticas actuales de requisitos no abrazan del todo el uso de información semántica** para aumentar la utilidad de las relaciones entre SLO. Y el problema que eso causa:

> **Una relación que dice que dos SLO se afectan mutuamente, pero no CÓMO, va a quedar abierta a la interpretación de todos los interesados.** Distintos interesados interpretan las relaciones sin información semántica de maneras distintas.
>
> **El ejemplo:** un usuario puede leer una relación como **"implementado-por"**, mientras un desarrollador puede leer **esa misma relación** como **"impone-restricciones-sobre"**.

> ⚠️ **Cruce con la cátedra — importante.** Este es el léxico de calidad aplicado a un artefacto que no es un requisito. **Una flecha sin etiqueta es un requisito ambiguo dibujado.** Dos personas la leen distinto, nadie se entera, y las dos calculan un impacto diferente.
>
> Es exactamente el argumento por el cual Laura no acepta que se dibuje mal una inclusión: **en UML la flecha tiene semántica declarada**, y esa semántica es lo que impide que cada uno lea lo que quiera. La notación no es prolijidad — es lo que hace que el diagrama signifique una sola cosa.

### 7.3 De la matriz a la matriz de alcanzabilidad 🟡

**El problema:** tanto el grafo de conectividad como la matriz de trazabilidad **muestran solo el impacto directo**. El impacto indirecto **solo puede deducirse recorriendo los vínculos**, y en sistemas con muchos SLO **la cantidad de impacto indirecto se vuelve rápidamente inmensa y difícil de deducir**.

**La solución técnica:** convertir la matriz de trazabilidad en una **matriz de alcanzabilidad**, usando un algoritmo de **clausura transitiva**.

> 🕳️ **Clausura transitiva.** Dado un grafo, se construye otro donde se agrega una arista entre A y B si era posible llegar de A a B por cualquier camino en el original. En criollo: **hace explícito todo lo que estaba conectado indirectamente**. Volvé al camino.

**El problema de esa solución** —y es instructivo: en el ejemplo del capítulo, la matriz de alcanzabilidad muestra que **todos los SLO terminan teniendo impacto sobre todos los demás**. Con lo cual **la matriz resulta de utilidad limitada**. Y ese problema **es común en contextos de software**, salvo que se tome alguna acción para limitar el alcance del impacto indirecto.

**Dos maneras de limitarlo:**

| Solución | Cómo funciona | Su límite |
|---|---|---|
| **Agregar distancias** a la matriz de alcanzabilidad | Permite **descartar impactos indirectos cuya distancia supere un umbral** predefinido | **No contempla que distintos tipos de relación de trazabilidad afectan el alcance del impacto indirecto de manera distinta** |
| **Agregar semántica de trazabilidad** y ajustar el algoritmo para tenerla en cuenta | El algoritmo **considera dos SLO alcanzables entre sí solo si las relaciones que forman el camino son de tipos que se espera que propaguen el cambio** | — |

> La segunda solución es la buena, y es la misma lección de antes: **sin semántica en los vínculos no se puede razonar sobre ellos.** Una relación "afecta a" propaga; una relación "es similar a" quizás no.

### 7.4 Técnicas de rebanado 🟢

**Rebanado de programas.** Intenta entender las dependencias usando **rebanadas independientes del programa**. El programa se rebana en:

- una **rebanada de descomposición**, que contiene el lugar del cambio;
- y **el resto del programa**, la **rebanada complemento**.

El rebanado se basa en **dependencias de datos y de control**. Y su garantía:

> **Los cambios hechos a la rebanada de descomposición, alrededor de la variable en la que la rebanada se basa, tienen garantizado no afectar a la rebanada complemento.**

Así, el rebanado **limita el alcance de la propagación del cambio y lo vuelve explícito**.

**Rebanado arquitectónico.** Similar, pero **opera sobre la arquitectura del sistema** en vez del código. Su ventaja decisiva:

> **Puede emplearse en desarrollo temprano, antes de que el código esté escrito.**

Usa un **grafo de flujos de información** para rastrear los componentes que pueden verse afectados por el componente que se cambia — **y también los que pueden afectar a ese componente**. Su requisito: **una especificación de la arquitectura que exponga todos los flujos de información** que contiene.

**Cómo se usa en IR:** para **aislar el impacto de un cambio de requisitos a una parte específica del sistema**. Pero primero **hay que evaluar el impacto directo**, que es el punto de partida del rebanado.

---

## 8. Estrategias manuales 🔴

No dependen tan fuertemente de especificaciones estructuradas. **Riesgo:** que sean **menos precisas**. **Ventaja:** son **más fáciles de introducir** en un proceso, y —según la experiencia de los autores— **se emplean comúnmente en la industria sin importar su precisión**.

**Su uso principal:** evaluar el **Conjunto de Impacto Inicial**, identificando el **impacto directo**. Identificar impacto secundario es posible, pero lo manejan mejor las automatizables.

Una nota útil: **las estrategias manuales pueden usarse para capturar los vínculos de trazabilidad** que después alimentan al análisis de trazabilidad.

### 8.1 Documentación de diseño 🔴

Viene en muchas formas: bocetos de arquitectura, modelos de arquitectura basados en vistas, diagramas UML orientados a objetos, descripciones textuales de componentes.

**La calidad de la documentación depende de:** el propósito para el que fue escrita, la frecuencia con que se actualiza, y la información que contiene.

Y una observación sobre la industria que vale la pena:

> **Es demasiado común que la documentación de diseño se escriba temprano en un proyecto solo para volverse material de estante, o que se escriba después del proyecto, solo por el hecho de escribirla.**

**Prerrequisitos para poder usarla:** que esté **actualizada y consistente con la implementación** hecha hasta el momento, y que sea posible **relacionar requisitos con los SLO de diseño** que figuran en ella.

#### Los cuatro factores de los que depende el éxito 🔴

**1. El conocimiento y la habilidad de quien hace el análisis.** Las personas con poca visión del sistema **muy probablemente tengan problemas para ubicar el impacto** de los requisitos cambiados.

**2. La disponibilidad de la documentación.** La documentación **"escondida" en computadoras personales o guardada en carpetas anónimas puede pasarse por alto** en el análisis.

**3. La cantidad de información que transmite.** Los bocetos de diseño simples son comunes, pero **no logran expresar la semántica de las conexiones** entre clases o componentes. **Los esquemas de nombres mal elegidos o la notación inconsistente vuelven ardua la tarea.**

**4. Documentación clara y consistente:**

> **La documentación ambigua está abierta a interpretación**, lo que significa, por ejemplo, que **el impacto de un cambio propuesto viene acoplado con gran incertidumbre — simplemente porque otra interpretación habría producido un impacto distinto.**

> ⚠️ **Cruce con la cátedra.** El factor 3 y el 4 son el léxico de corrección de Laura, dicho por otra gente y en otro contexto. **Nombres mal elegidos, notación inconsistente, ambigüedad** — las tres cosas que te penalizan, listadas acá como causas directas de estimaciones de impacto erróneas. Y el factor 4 nombra la mecánica exacta: **otra interpretación habría dado otro número.** Ese es el costo concreto de la ambigüedad, expresado en plata y en cronograma.

#### Dos medidas que ayudan 🟡

**Llevar una justificación de diseño** (*design rationale*) — documentación que describe **por qué las decisiones se tomaron como se tomaron**. Un experimento sugiere que **puede acortar el tiempo requerido para el análisis de impacto y aumentar su calidad**.

**Estimar el impacto de los requisitos apenas se desarrollan.** La estimación es necesariamente gruesa al principio, **pero puede mejorarse incrementalmente** a medida que crece el conocimiento sobre el sistema.

### 8.2 Entrevistas 🔴

Y acá está el hallazgo que más contrasta con todo lo anterior:

> **Entrevistar a desarrolladores con conocimiento es probablemente la manera más común de adquirir información sobre los efectos probables de requisitos nuevos o cambiados.**

El estudio encontró que **los desarrolladores lo perciben como altamente costo-efectivo: preguntarle a alguien que sabe, en vez de buscar en documentos u otras fuentes**. La comunicación extensiva entre desarrolladores también fue mencionada como **factor de éxito** de los proyectos.

**El segundo lugar:** el análisis del código fuente.

**Y el dato revelador.** Mientras **todos** los desarrolladores dijeron que entrevistaban a otros desarrolladores y consultaban el código fuente, **alrededor de la mitad** dijo que además consultaba información almacenada en la herramienta CASE en uso — modelos de casos de uso, modelos de objetos.

Preguntados por qué no usaban más la información de los modelos de objetos, **dieron dos razones**:

1. **La información de los modelos no era suficientemente detallada** para el análisis de impacto.
2. **No creían que la información de los modelos estuviera actualizada.** Y citan textualmente el argumento:

> **"El código fuente, en cambio, siempre está actualizado."**

Entre algunos desarrolladores, **especialmente los recién llegados**, la actitud hacia usar modelos de objetos como base para determinar el cambio **era menos que positiva**.

**Pero los modelos sí sirvieron para otra cosa:** fueron mencionados como **buena herramienta para documentar el análisis de impacto** y para **responder preguntas sobre la relación entre requisitos y objetos de diseño**, usando el soporte de vínculos de trazabilidad.

> ⚠️ **Cruce con la cátedra.** El argumento "el código siempre está actualizado" es demoledor y hay que tenerlo consciente: **un modelo desactualizado es peor que no tener modelo**, porque miente con autoridad. Eso le da sentido al modo de trabajo iterativo que declaró la cátedra —rehacer sobre lo entregado en vez de entregar y cerrar— y al hecho de que el TP integrador tenga entregas encadenadas donde cada una revisa la anterior.

---

## Mapa de la Parte 1

```
   EL PROBLEMA
   los cambios rara vez tienen el impacto chico que se cree
   (subestimación documentada: factor de 3)
   cambio no gestionado → deterioro del software

   ─────────────────────────────────────────────

   VOCABULARIO
   SLO ──────────► cualquier artefacto del proyecto
   SIS ──────────► lo que se cree que va a cambiar
   EIS ──────────► lo que se estima que va a cambiar
                   (SIS + propagación)
   AIS ──────────► lo que efectivamente cambió

   primario  = impacto directo (difícil de automatizar)
   secundario = indirecto:
        efectos colaterales → hay que EVITARLOS
        efectos de propagación → NO se pueden evitar,
                                 hay que VERLOS VENIR

   ─────────────────────────────────────────────

   GESTIÓN DEL CAMBIO — 5 piezas
   1. planificar para el cambio
   2. línea base de requisitos
   3. canal único (comité de control)
   4. sistema de control de cambios
   5. gestionar JERÁRQUICAMENTE (de arriba hacia abajo,
      NUNCA entrando por el código)

   ─────────────────────────────────────────────

   ESTRATEGIAS
   AUTOMATIZABLES          MANUALES
   · trazabilidad/         · documentación de diseño
     dependencias          · ENTREVISTAS ← la más usada
   · rebanado                en la práctica
   estiman el EIS          estiman el SIS
   (impacto indirecto)     (impacto directo)

   ─────────────────────────────────────────────

   LA AMBIGÜEDAD APARECE DOS VECES
   · vínculo de trazabilidad sin semántica:
     el usuario lee "implementado-por",
     el desarrollador lee "impone-restricciones-sobre"
   · documentación ambigua:
     otra interpretación habría dado OTRO impacto
```

---

## Preguntas para chequear que quedó

1. ¿Por qué se deteriora el software? ¿Qué evidencia dan Mozilla y el sistema de telecomunicaciones?
2. ¿Por qué factor subestimaron el cambio los profesionales del estudio de los 90?
3. Definí análisis de impacto y decí para qué sirve su salida.
4. ¿Qué se ve afectado por un cambio de requisitos en cada una de las tres fases?
5. ¿Qué es un SLO? Dé tres ejemplos.
6. Diferenciá análisis de dependencias de análisis de trazabilidad. ¿Cuál sirve más temprano y por qué?
7. Definí los cuatro conjuntos de impacto y las dos igualdades ideales.
8. ¿Por qué el cambio primario es difícil de automatizar?
9. Diferenciá efectos colaterales de efectos de propagación. ¿Qué se hace con cada uno?
10. Nombrá las cuatro causas de cambio en los requisitos. ¿Cuál se relaciona con la paradoja de la volatilidad del capítulo 4?
11. Explicá la frase "el cambio no es una patada en los dientes; el cambio no gestionado sí".
12. Nombrá las cinco piezas del marco de gestión del cambio.
13. ¿Qué antipatrón concreto derrota "gestionar jerárquicamente"?
14. ¿En qué pasos del proceso de Kotonya y Sommerville se hace análisis de impacto?
15. ¿Por qué las predicciones de los desarrolladores son "optimistas"? ¿Qué se propone hacer al respecto?
16. ¿Cuáles son las dos desventajas del análisis de dependencias sobre código?
17. Explicá el problema del vínculo de trazabilidad sin semántica con el ejemplo del usuario y el desarrollador.
18. ¿Qué es la matriz de alcanzabilidad y por qué resulta de utilidad limitada? ¿Cuáles son las dos maneras de limitar el problema?
19. ¿Qué garantiza el rebanado de programas? ¿Qué ventaja tiene el rebanado arquitectónico?
20. Nombrá los cuatro factores de los que depende usar la documentación de diseño para análisis de impacto.
21. ¿Por qué la documentación ambigua produce estimaciones de impacto inciertas?
22. ¿Cuál es la estrategia más usada en la práctica y por qué?
23. ¿Por qué los desarrolladores desconfían de los modelos de objetos? ¿Para qué sí los consideran útiles?

---

**FIN DEL CAPÍTULO 6 — PARTE 1**

*Sigue en la Parte 2: análisis de impacto para requisitos no funcionales, las métricas para cuantificar y evaluar el impacto, el estudio de campo en Ericsson, herramientas de soporte, futuro y cierre.*
