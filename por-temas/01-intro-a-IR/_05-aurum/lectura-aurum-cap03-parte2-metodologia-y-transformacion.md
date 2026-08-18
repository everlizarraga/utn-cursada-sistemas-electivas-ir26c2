# Lectura en español — Cap. 3 · Parte 2: Metodología de especificación y transformación de requisitos

> **Origen.** Capítulo 3, secciones 3.4 a 3.6, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Ricardo J. Machado, Isabel Ramos y João M. Fernandes**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1.** Se asume conocida la distinción requisitos de usuario / requisitos de sistema, la diferencia entre modelar y especificar, y qué es un metamodelo.

---

## Qué trae esta parte

Tres bloques, y el interés te va a subir hacia el final:

1. **Cómo se define una metodología de especificación** — lenguaje, control de complejidad y continuidad de modelos.
2. **Los requisitos no funcionales**, clasificados en tres grupos. Esto sí toca tu cursada de lleno.
3. **La técnica 4SRS**, un procedimiento concreto en cuatro pasos para **transformar casos de uso en objetos**. Es lo más aterrizado del capítulo.

---

## 1. Metodología de especificación 🟡

La **ingeniería de métodos** es la comunidad que se dedica a la descripción formal, la comparación y la construcción de métodos y técnicas para el desarrollo de sistemas.

Un par de términos que usa esa comunidad:

| Término | Qué es |
|---|---|
| **Meta-modelos de proceso** | Metamodelos **del proceso de desarrollo** |
| **Meta-modelos de datos** | Metamodelos **de los productos del desarrollo**, o entregables. *(Son a los que este capítulo llama simplemente "metamodelos".)* |

Enfoques conocidos de ingeniería de métodos: **ISO/IEC 12207**, **OPEN** y **PIE**.

Al acto de **definir la propia metodología de especificación** se lo llama **ingeniería de métodos situacional**. Y es en ese contexto donde importa tener en cuenta **tres cuestiones clave**:

```
   1. LENGUAJE DE ESPECIFICACIÓN
   2. CONTROL DE LA COMPLEJIDAD
   3. CONTINUIDAD DE MODELOS
```

### 1.1 Lenguaje de especificación 🟡

Los lenguajes de especificación deben permitir representar una vista particular del sistema **sin ambigüedades**. Ese es su propósito principal.

Pero además deben ofrecer **soporte para analizar y razonar sobre la especificación**. Los mecanismos de análisis disponibles dependen del lenguaje mismo, y son esencialmente de dos tipos:

| Mecanismo | Qué permite | Condición |
|---|---|---|
| **Análisis formal** | **Verificar si una especificación es incoherente** | Solo es posible si el lenguaje **posee una base matemática sólida** |
| **Ejecución de la especificación** | **Probar tempranamente prototipos** del sistema para validar requisitos | Vuelve el proceso de especificación más robusto y comprensible |

> Notá lo que dice el primero: el análisis formal no verifica que la especificación sea *correcta* respecto de lo que el cliente quería. Verifica que sea **coherente consigo misma** — que no se contradiga. Es mucho, pero no es lo mismo.

### 1.2 Control de la complejidad 🟡

Primero, una definición del problema que vale por sí sola:

> **La complejidad de un sistema no depende solo de la cantidad de sus partes, sino principalmente de la manera en que esas partes interactúan entre sí.**

El capítulo lo ilustra con el crecimiento de las interacciones posibles: con *n* partes, la cantidad de interacciones posibles es **n·(n−1)/2**. Con 2 partes hay 1 interacción; con 3 hay 3; con 4 hay 6. Crece mucho más rápido que la cantidad de piezas.

```
   2 partes    3 partes    4 partes         n partes
      1           3           6          n·(n-1)/2
   interacción interacciones interacciones
```

El control de la complejidad se puede ejercer en **dos dimensiones**.

#### Dimensión 1 — Complejidad representacional

Depende esencialmente **del lenguaje de especificación** y, si se maneja bien, permite obtener **especificaciones concisas y comprensibles**.

Se logra mediante **tres técnicas**:

**a) Jerarquía.** La jerarquización de modelos consiste en **agrupar partes similares del sistema** —estructurales o de comportamiento— **dentro de un elemento nuevo que representa al grupo**.

Acá aparece el concepto de **nivel de abstracción**: los desarrolladores deben ser capaces de **decidir el nivel apropiado** a usar. Típicamente, adoptar niveles de abstracción más altos **mejora el entendimiento del sistema como un todo, mientras oculta los detalles**.

**b) Ortogonalización.** La ortogonalización de modelos consiste en **describir un conjunto de comportamientos del sistema de forma independiente unos de otros**, siempre que sea posible.

**c) Esquema de representación.** Acá la decisión es entre representaciones **textuales** o **gráficas**.

Los esquemas gráficos implican **formalismos visuales**, donde tanto la interpretación sintáctica como la semántica se asignan a entidades gráficas. Y el veredicto del capítulo:

> **Los enfoques gráficos son usualmente más fáciles de entender que los textuales**, y por lo tanto mejoran la legibilidad y la comprensibilidad de la vista del sistema. **UML adopta un enfoque gráfico.**

#### Dimensión 2 — Complejidad de desarrollo

Se refiere a controlar **la evolución de la especificación del sistema** desde la conceptualización inicial de los requisitos.

Se logra de dos maneras:

- **Difiriendo ciertos detalles** a las fases siguientes del desarrollo.
- **Adoptando distintas evoluciones de especificación** a lo largo del proceso: **descendente** (*top-down*), **ascendente** (*bottom-up*) o **desde el medio** (*middle-out*).

### 1.3 Continuidad de modelos 🟡

Principio de arranque:

> **Los modelos obtenidos en las fases iniciales del desarrollo deben ser persistentes, evitando su reescritura en cada paso.**

Para soportar las metodologías de diseño e implementación, esta preocupación por la continuidad debe **asegurar conformidad en la evolución de los modelos a lo largo de todo el proceso de desarrollo**. Eso es posible permitiendo que los modelos **se refinen** mediante la inclusión de atributos nuevos —de comportamiento y estructurales— adquiridos durante las fases de diseño e implementación.

```
   REQUISITOS ──► ANÁLISIS ──► DISEÑO ──► IMPLEMENTACIÓN ──► SISTEMA
        │             │            │             │
        └─────────────┴────────────┴─────────────┘
              el MISMO modelo, refinado
              (no reescrito en cada etapa)
```

**Una condición sobre el primer modelo:** debe ser **independiente de la implementación**, permitiendo que los desarrolladores se enfoquen en el modelado del comportamiento del sistema. Al construir la primera especificación **hay que evitar las decisiones de diseño o implementación y las restricciones innecesarias**.

**Y una limitación admitida.** Dentro de un enfoque de continuidad total, sería deseable que **la síntesis automática de la solución se base completamente en la especificación del sistema**. Pero esa técnica de síntesis, llevada al nivel de sistema, **todavía no es suficientemente eficiente**: se basa usualmente en las características estructurales de las especificaciones y tiene la desventaja de **limitar la exploración del espacio de diseño**, generando soluciones no óptimas para la implementación.

---

## 2. Los requisitos no funcionales 🔴

Esta sección es corta y es la que más te sirve del bloque.

Arranca con una afirmación fuerte:

> **Los requisitos no funcionales limitan la exploración del espacio de diseño**, porque típicamente **imponen, en etapas tempranas del desarrollo, soluciones particulares de diseño e implementación.**

Eso es una manera distinta de mirarlos de la habitual. No son "los otros requisitos": son los que **cierran puertas** antes de que empiece el diseño.

Y los clasifica en **tres grupos**.

### 2.1 Objetivos de diseño 🔴

Están relacionados con **requisitos generales de rendimiento cualitativo** del sistema. Aparecen típicamente con esta forma:

- *"debe ser lo más rápido posible"*
- *"debe ser barato"*
- *"debe ser fácil de adaptar"*

Y acá viene la sentencia que conviene retener:

> **Aunque estos objetivos de diseño no son realmente requisitos**, pueden transformarse en **restricciones de diseño** si se logra idear alguna métrica para ellos.

Si no se puede idear esa métrica, **los objetivos de diseño solo deberían usarse para elegir entre alternativas funcionalmente equivalentes**, cuando no hay ningún criterio más firme para decidir.

> ⚠️ **Cruce con la cátedra — importante.** Esto es la fundamentación teórica de por qué te van a corregir "el sistema debe ser rápido" como requisito mal escrito. El libro va más lejos que decir que está mal redactado: dice que **no es un requisito en absoluto** hasta que se le encuentre una métrica. "Debe ser rápido" no es un requisito; "debe responder en menos de 2 segundos para el 95% de las consultas" sí lo es, porque ya es medible.
>
> Y te da además la salida elegante cuando la métrica no existe: ese objetivo sirve como **criterio de desempate** entre soluciones que hacen lo mismo, no como requisito exigible.
>
> Conecta directo con el léxico de calidad de Laura: **verificable**. Lo que no se puede medir no se puede verificar, y lo que no se puede verificar no es un requisito.

### 2.2 Decisiones de diseño 🟡

Pueden estar relacionadas, por ejemplo, con:

- la inclusión del sistema **dentro de una familia dada de productos comerciales**,
- o con su **incorporación a un producto más grande**.

Estos requisitos no funcionales **pueden afectar las decisiones tecnológicas o interferir con la funcionalidad** del sistema. Por eso, dicen los autores, **siempre deberían cuestionarse y justificarse**.

**Cómo se documentan:** el **OCL de UML** (*Object Constraint Language*, lenguaje de restricción de objetos) puede usarse para describir decisiones de diseño arquitectónicas o funcionales.

> 🕳️ **OCL** — un lenguaje textual de UML para escribir restricciones que los diagramas no pueden expresar gráficamente: reglas del tipo "el saldo de una cuenta nunca puede ser negativo". Complementa a los diagramas, no los reemplaza. Volvé al camino.

### 2.3 Restricciones de diseño 🔴

Incluyen, por ejemplo: **rendimiento, confiabilidad, costo y tamaño**.

Los **requisitos temporales** se clasifican en tres tipos:

| Tipo | |
|---|---|
| **Tiempo de respuesta** | Cuánto tarda en contestar |
| **Tasa de repetición** | Cada cuánto ocurre |
| **Tiempo de correlación** | Relación temporal entre eventos |

**Su propiedad distintiva:** este tipo de decisiones no funcionales **es típicamente cuantificable**, y se incorpora sintácticamente en los modelos del sistema como **valores etiquetados** o **estampas de objeto**.

**Cómo se documentan:** los **diagramas de secuencia de UML** pueden soportar la inscripción de requisitos temporales y de rendimiento.

### Las tres, comparadas 🔴

```
   OBJETIVOS DE DISEÑO ──► "lo más rápido posible"
     · NO son requisitos propiamente dichos
     · se vuelven restricciones SI se les encuentra métrica
     · si no, sirven solo para desempatar

   DECISIONES DE DISEÑO ──► "debe integrarse a la familia X"
     · afectan tecnología o funcionalidad
     · SIEMPRE hay que cuestionarlas y justificarlas
     · se documentan con OCL

   RESTRICCIONES DE DISEÑO ──► "responde en < 2 s"
     · CUANTIFICABLES
     · entran al modelo como valores etiquetados
     · se documentan en diagramas de secuencia
```

---

## 3. Transformación de requisitos 🔴

### 3.1 Por qué el problema es difícil

Obtener modelos de **requisitos de sistema** a partir de **requisitos de usuario**, que puedan usarse directamente en la fase de diseño, **no es simple ni fácil** y enfrenta varias dificultades.

Genéricamente, involucra **varias decisiones que no pueden tomarse mediante un método o una herramienta**, debido a **la discontinuidad natural entre los modelos funcionales y los estructurales**. Hay un salto que ninguna receta cubre del todo.

El capítulo cita a Holland y Lieberherr, para quienes **la identificación de los objetos** y **la descripción de las relaciones entre ellos** son dos de los tres desafíos del diseño orientado a objetos.

Existen muchas propuestas para atacar esto, principalmente **guiando la transformación de modelos de casos de uso en modelos de objetos y clases**. Algunos enfoques proponen una **justificación de los casos de uso basada en la identificación de metas**, lo que ayuda a la transición hacia el diseño arquitectónico — aunque, señalan los autores, **les falta un marco explícito de escenarios** para capturar la intencionalidad semántica de cada caso de uso.

### 3.2 El modelado de requisitos de usuario 🔴

Identificar los componentes del sistema requiere primero **un modelo que capture las funcionalidades que el sistema ofrece a sus usuarios**.

Y acá el capítulo argumenta a favor de los casos de uso con una razón que vale la pena tener a mano:

> **Los casos de uso son una de las técnicas más adecuadas para ese propósito, porque son simples y fáciles de leer. De hecho, incluyen solo tres conceptos principales: casos de uso, actores y relaciones. Ese número bajo de conceptos es una característica fundamental para involucrar a los interesados no técnicos en el proceso de captura de requisitos.**

> ⚠️ **Cruce con la cátedra.** Guardá ese argumento: **la simplicidad del caso de uso no es una limitación, es su función**. Tres conceptos y nada más, para que alguien que no sabe de sistemas pueda leerlo y corregirte. Si te preguntan por qué se modela con casos de uso y no con algo más expresivo, esa es la respuesta.
>
> Y notá que los tres conceptos que enumera —casos de uso, actores y relaciones— son exactamente los tres ejes de la clase 02 de tu cronograma.

Una observación más, que resuelve un malentendido común:

> **Aunque los casos de uso se usan en muchos proyectos orientados a objetos, no tienen ninguna característica intrínseca que pueda clasificarse como "puramente" orientada a objetos.** Sin embargo, hay amplio consenso en reconocerlos como una técnica apropiada para proyectos orientados a objetos, sobre todo para descubrir —y luego especificar— el comportamiento del sistema durante la fase de análisis. Que formen parte de UML lo refuerza.

Adoptar casos de uso para los requisitos de usuario es entonces **indudablemente una técnica válida**, pero plantea el problema de **cómo transformarlos en objetos o componentes**. Ese es el tema de lo que sigue.

**Cómo se describe un caso de uso.** Después de identificar todos los casos de uso del sistema, el paso siguiente es describir su comportamiento. Las alternativas que menciona el capítulo:

- texto informal,
- pasos numerados con precondiciones y postcondiciones,
- pseudocódigo,
- diagramas de actividad.

### 3.3 La técnica 4SRS 🔴

Transformar casos de uso en modelos arquitectónicos que representen requisitos de sistema es una tarea difícil. Para eso se propuso una técnica llamada **4SRS** — *4 Step Rule Set*, conjunto de reglas en cuatro pasos.

```
   PASO 1 ──► CREACIÓN de objetos
   PASO 2 ──► ELIMINACIÓN de objetos
   PASO 3 ──► EMPAQUETADO y AGREGACIÓN de objetos
   PASO 4 ──► ASOCIACIÓN de objetos
```

#### Paso 1 — Creación de objetos

**Cada caso de uso debe transformarse en tres objetos:** uno de **interfaz**, uno de **datos** y uno de **control**.

Cada objeto recibe la referencia de su caso de uso correspondiente, con un sufijo agregado (**i**, **d**, **c**) que indica su categoría. En este enfoque, las referencias de objeto empiezan con "O".

**Es un paso completamente automático**: no hace falta ninguna decisión ni razonamiento particular sobre el contexto de cada caso de uso.

Y una nota de método: **de este paso en adelante, las únicas entidades de diseño son objetos**. Los casos de uso se siguen usando en los pasos siguientes, pero solo para **introducir los requisitos dentro del modelo de objetos**.

```
   {U0a.1}  ──►  {O0a.1.i}   objeto de interfaz
   caso de       {O0a.1.d}   objeto de datos
   uso           {O0a.1.c}   objeto de control
```

#### Paso 2 — Eliminación de objetos

Hay que decidir **cuáles de los tres objetos deben mantenerse** para representar plenamente, en términos computacionales, al caso de uso — **teniendo en cuenta el sistema entero y no cada caso de uso aislado**.

**Esas decisiones deben basarse en la descripción textual de cada caso de uso.**

Este paso hace tres cosas a la vez:

1. Decide **cuáles de los objetos creados en el paso 1 se conservan** en el modelo.
2. **Elimina redundancia** en la elicitación de requisitos de usuario.
3. **Detecta requisitos faltantes.**

Los autores lo declaran **el paso más importante de toda la técnica**, porque es donde **se deciden las entidades definitivas a nivel de sistema**.

Por su complejidad, está descompuesto en **siete micro-pasos**:

| | Micro-paso |
|---|---|
| **2i** | Identificación de casos de uso |
| **2ii** | Eliminación local |
| **2iii** | Nombrado de objetos |
| **2iv** | Descripción de objetos |
| **2v** | Representación de objetos |
| **2vi** | Eliminación global |
| **2vii** | Renombrado de objetos |

*(El capítulo declara que la descripción detallada de estos micro-pasos queda fuera de su alcance.)*

> Fijate en la lógica: hay una **eliminación local** (mirando el caso de uso solo) y después una **eliminación global** (mirando el sistema entero). Un objeto que parecía necesario visto de cerca puede resultar redundante visto de lejos. Ese es el mismo movimiento de la regla del café con leche: granular primero, unificación después.

#### Paso 3 — Empaquetado y agregación

Los objetos que sobrevivieron al paso 2, **cuando hay ventaja en tratarlos de manera unificada**, deben dar origen a **agregaciones o paquetes de objetos semánticamente consistentes**.

Este paso soporta la construcción de un modelo de objetos verdaderamente coherente, porque **introduce una capa semántica adicional a un nivel de abstracción más alto**, que funciona como un **"pegamento funcional"** entre los objetos.

La distinción entre las dos formas de pegar es lo importante acá:

| | **Empaquetado** | **Agregación** |
|---|---|---|
| **Cohesión que introduce** | **Muy leve** | **Fuerte** |
| **¿Se puede revertir?** | Sí, **fácilmente**, dentro de la fase de diseño | **Difícil** de revertir en etapas posteriores |
| **Cuándo usarlo** | Libremente, para obtener modelos más comprensibles y abarcativos | **Solo cuando se asume explícitamente** que el conjunto de objetos está afectado por una decisión de diseño consciente |
| **Casos típicos** | — | Cuando hay una parte del sistema que constituye un **subsistema heredado**, o cuando el diseño tiene una **arquitectura de referencia predefinida** que restringe el modelo |

El criterio general que se desprende: **usá el pegamento débil por defecto y el fuerte solo cuando estés seguro**, porque el fuerte no se despega después.

#### Paso 4 — Asociación de objetos

Soporta la introducción de **asociaciones** en el modelo de objetos, **completamente basadas en la información del modelo de casos de uso** generada en el micro-paso 2i.

Dos fuentes de asociaciones:

1. **Las descripciones textuales de los casos de uso**, si contienen pistas sobre el tipo de secuencias en que los casos de uso están insertos. Esa información debe usarse para incluir asociaciones.
2. **Las relaciones UML entre casos de uso.** El ejemplo del capítulo: si el caso de uso `{U0a.1.1}` **usa** al caso de uso `{U0a.1.2}`, eso justifica una asociación entre los objetos derivados de ambos.

> ⚠️ **Cruce con la cátedra.** Ese ejemplo del paso 4 es el punto donde este capítulo toca directamente el contenido de tu clase 02. **Las relaciones entre casos de uso —inclusión, extensión— no son decoración del diagrama: propagan información al modelo de objetos.** Una inclusión mal dibujada no es un error de dibujo; genera asociaciones equivocadas río abajo.
>
> Esto le da fundamento técnico a la exigencia de Laura de que la notación sea impecable. El diagrama es un insumo de procesamiento, no una ilustración.

### 3.4 Qué produce la técnica 🟡

El modelo arquitectónico resultante expresa los requisitos de sistema, pero también **una descripción informal de los objetos**.

La 4SRS ayuda a definir una **arquitectura lógica** del sistema, capturando:

- **todos sus requisitos funcionales** → dan origen a las descripciones textuales de cada objeto del modelo;
- **sus intenciones no funcionales** → clasificadas como **decisiones de diseño** y **restricciones de diseño**.

Y una regla explícita que cierra el círculo con la sección 2:

> **Los objetivos de diseño no están permitidos en los modelos de requisitos de sistema generados por la técnica 4SRS.**

Coherente: si un objetivo de diseño no es un requisito hasta tener métrica, no puede entrar a un modelo que va a alimentar el diseño.

**Qué muestra el modelo generado.** El modelo de objetos muestra **cómo se distribuyen las propiedades significativas del sistema entre sus partes constituyentes**. La 4SRS genera un **diagrama de objetos en bruto** que identifica:

- las entidades a nivel de sistema,
- sus responsabilidades,
- y las relaciones entre ellas.

**Su propósito:** dirigir la atención hacia **una descomposición apropiada del sistema, sin meterse en los detalles**. Cada paquete usado define **una región de descomposición distinta**, que contiene varios objetos semánticamente muy conectados entre sí. En las fases de diseño siguientes, esos paquetes deben especificarse más, en cuanto a su estructura arquitectónica, **usando patrones de diseño**.

**Cómo se usa después.** El diagrama de objetos en bruto puede usarse en las fases siguientes para soportar la definición de subproyectos específicos, mediante **técnicas de colapso y filtrado**. Esas técnicas permiten **redefinir los límites del sistema**, dando origen, por ejemplo, al proyecto de base de datos, a la formalización de servicios, o al análisis de patrones de plataforma.

El **diagrama de objetos colapsado** se obtiene del diagrama en bruto **ocultando los detalles de los paquetes**. Así las asociaciones aparecen a un nivel de abstracción más alto y el diagrama resultante es más legible.

---

## 4. Conclusión del capítulo 🟡

Los autores cierran retomando su tesis:

**La derivación correcta de requisitos de sistema a partir de requisitos de usuario es un tema importante** de la investigación en IR. Esa actividad asegura que la fase de diseño se base en las necesidades efectivas del cliente, **sin ningún juicio errado introducido arbitrariamente por los desarrolladores** durante la especificación.

Un enfoque para sostener esa derivación es **transformar modelos de requisitos de usuario en modelos de requisitos de sistema**, manipulando las especificaciones correspondientes. Y repiten el contraste:

| Requisitos de usuario | Requisitos de sistema |
|---|---|
| Lenguaje natural y diagramas informales | Modelos abstractos del sistema |
| Nivel de detalle relativamente bajo | Nivel de detalle relativamente alto |
| Enfocados en el **dominio del problema** | Primera representación del sistema, al comienzo del **diseño** |

Dos afirmaciones finales:

- **Los metamodelos juegan un papel importante**, porque definen **la capacidad semántica** de las vistas de modelado que se adopten para un sistema dado.
- **La continuidad de modelos es una cuestión clave**, y de ahí la importancia de tener un proceso bien definido para **relacionar, mapear y transformar** los modelos de requisitos.

Y el remate:

> **El diseño de sistemas es una tarea altamente abstracta**, que se enfoca en los requisitos funcionales y no funcionales de los sistemas basados en computadora. Tanto los diseñadores como los ingenieros de requisitos se benefician de **un enfoque basado en modelos** para la especificación de requisitos, que permita la evolución correcta de las representaciones del sistema durante los proyectos de desarrollo.

---

## Mapa de la Parte 2

```
   METODOLOGÍA DE ESPECIFICACIÓN — 3 cuestiones clave
   ├─ LENGUAJE ──────► análisis formal (necesita base matemática)
   │                   ejecución (permite prototipos tempranos)
   ├─ COMPLEJIDAD ───► representacional: jerarquía, ortogonalización,
   │                   esquema (UML = gráfico)
   │                   de desarrollo: diferir detalles, top-down /
   │                   bottom-up / middle-out
   └─ CONTINUIDAD ───► el modelo se REFINA, no se reescribe

   ─────────────────────────────────────────────────────

   REQUISITOS NO FUNCIONALES — 3 grupos
   OBJETIVOS  ──► cualitativos, NO son requisitos sin métrica
   DECISIONES ──► afectan tecnología, hay que justificarlas (OCL)
   RESTRICCIONES ► cuantificables, entran al modelo (secuencia)

   ─────────────────────────────────────────────────────

   4SRS — casos de uso ──► objetos
   1. CREAR      cada CU → 3 objetos (i, d, c)   [automático]
   2. ELIMINAR   cuáles quedan  [el paso clave, 7 micro-pasos]
   3. EMPAQUETAR paquete (débil) vs agregación (fuerte)
   4. ASOCIAR    de las descripciones y de las relaciones UML
```

---

## Preguntas para chequear que quedó

1. ¿Qué es la "ingeniería de métodos situacional"?
2. ¿Cuáles son las tres cuestiones clave a considerar al definir una metodología de especificación?
3. ¿Qué verifica el análisis formal de una especificación, y qué NO verifica?
4. ¿Qué condición debe cumplir un lenguaje para permitir análisis formal?
5. ¿De qué depende principalmente la complejidad de un sistema, según el capítulo? ¿Cuántas interacciones posibles hay entre 4 partes?
6. Nombrá las tres técnicas de control de la complejidad representacional.
7. ¿Qué efecto tiene adoptar un nivel de abstracción más alto?
8. ¿Por qué UML adopta un enfoque gráfico y no textual?
9. ¿Qué significa "continuidad de modelos" y qué evita?
10. ¿Qué debe evitarse al construir la primera especificación?
11. ¿Por qué se dice que los requisitos no funcionales limitan la exploración del espacio de diseño?
12. "El sistema debe ser lo más rápido posible": ¿en qué grupo cae, es un requisito, y qué habría que hacer para que lo sea?
13. Si un objetivo de diseño no puede convertirse en métrica, ¿para qué sirve entonces?
14. ¿Por qué las decisiones de diseño deberían siempre cuestionarse y justificarse?
15. Nombrá los tres tipos de requisito temporal y el diagrama UML donde se documentan.
16. ¿Cuáles son los tres conceptos de un modelo de casos de uso, y por qué ese número bajo es una virtud y no una limitación?
17. ¿Son los casos de uso una técnica intrínsecamente orientada a objetos? Justificá.
18. En el paso 1 de la 4SRS, ¿en qué tres objetos se transforma cada caso de uso? ¿Por qué es un paso automático?
19. ¿Por qué el paso 2 es el más importante de la 4SRS, y qué tres cosas logra?
20. Diferenciá empaquetado de agregación: cohesión, reversibilidad y cuándo usar cada uno.
21. ¿De qué dos fuentes salen las asociaciones en el paso 4?
22. ¿Por qué la 4SRS prohíbe los objetivos de diseño en los modelos de requisitos de sistema?

---

**FIN DEL CAPÍTULO 3 — PARTE 2**

**FIN DEL CAPÍTULO 3**

*Sigue el capítulo 4: priorización de requisitos, en 2 partes.*
