# Lectura en español — Cap. 20 · Parte 2: Las cuatro tendencias y el cierre

> **Origen.** Capítulo 20, secciones 20.3 y 20.4, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Christof Ebert y Roel J. Wieringa**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1.** Se asumen conocidos el marco, los seis riesgos y el diagnóstico sobre transferencia tecnológica.

---

## Última parte de la serie

Cuatro tendencias, y después el cierre del libro. **De las cuatro, la que más te sirve es la cuarta —las habilidades del ingeniero de requisitos—** porque es un retrato de qué hace falta para hacer bien este trabajo, y sirve de espejo para el estudiante.

Las tendencias, en orden:

```
   1. el uso creciente de COMPONENTES COMERCIALES
      y cómo hay que ajustar las actividades de requisitos
   2. la GESTIÓN DEL CICLO DE VIDA del producto y la
      necesidad de colaborar entre comunidades muy
      heterogéneas
   3. cómo INTRODUCIR efectivamente la IR en una
      organización
   4. el interés creciente en LAS HABILIDADES del
      ingeniero de requisitos
```

---

## 1. Componentes comerciales 🟡

### El cambio de escenario

> **Un producto comercial listo para usar es una pieza de software comercialmente disponible que un proyecto puede REUTILIZAR E INTEGRAR en sus propios productos.** Incluye el software de código abierto empaquetado.
>
> **Hoy, LA MAYOR PARTE DEL DESARROLLO se basa en componentes comerciales, y un número creciente de proyectos consiste SOLAMENTE EN COMBINARLOS.**

**La motivación:** **acelera el desarrollo y reduce el tiempo al mercado**, y los productos son **más fáciles de desarrollar porque algunos o todos los componentes vienen ya hechos.**

### Los costos escondidos 🔴

Pero los principios de ingeniería son distintos:

> **La experiencia muestra que hay CAMBIOS FRECUENTES en los productos comerciales, SOBRE LOS QUE EL USUARIO TIENE POCO CONTROL, porque están impulsados por el mercado, no por ningún usuario particular.**

Los números que dan:

```
   · un producto comercial promedio saca UNA VERSIÓN
     NUEVA CADA 8 A 9 MESES, con soporte SOLO PARA LAS
     ÚLTIMAS TRES VERSIONES
   · los cambios pueden hacer que la funcionalidad
     EVOLUCIONE HACIA LO QUE NO NECESITÁS, lo que te
     obliga a escribir ENVOLTORIOS COSTOSOS
   · mantener ese código es TRES VECES MÁS CARO POR LÍNEA
     que mantener código propio
```

**Por qué es tan caro:** el que mantiene **tiene que lidiar con parches y correcciones del producto comercial, con el pegamento que lo conecta a otros sistemas, y con SUPOSICIONES QUE EL PRODUCTO HACE Y QUE EL SISTEMA QUE LO INCORPORA NO SATISFACE.**

**Y una advertencia sobre modificarlos:**

> **Algunos clientes grandes tienen la fea costumbre de tomar un producto comercial y pedir TANTAS MODIFICACIONES que el riesgo sube inconmensurablemente.**
>
> Sugerimos que los profesionales sean **agudamente conscientes de que HACER MODIFICACIONES ELEVA LOS RIESGOS A NIVELES QUE PUEDEN ACERCARSE A LOS DE UN DESARROLLO NUEVO.**

### La lección de requisitos 🔴🔴

Y acá está lo aprovechable de la sección:

> **La intuición básica es que NO TIENE SENTIDO primero recolectar todos los requisitos y después buscar un producto que los satisfaga.**
>
> **NINGÚN producto va a satisfacer todos esos requisitos, porque todos están desarrollados PARA UN MERCADO y no van a satisfacer requisitos específicos del sistema que estás desarrollando.**

**Y el razonamiento sobre qué especificar:**

> Dado el tipo general de sistema que necesitás, **TODOS los productos del mercado van a proveer más o menos LA MISMA funcionalidad con más o menos la misma calidad. Compiten entre sí y VAN A TENER PROPIEDADES SIMILARES.**
>
> **La manera de encarar los requisitos es determinarlos primero A UN NIVEL GENERAL, lo bastante específico para determinar EN QUÉ MERCADO vas a buscar, PERO SIN especificar funciones y atributos detallados.**
>
> **Una vez que sabés en qué parte del mercado buscar, comparás los productos disponibles POR LAS PROPIEDADES QUE LOS DIFERENCIAN, NO POR LAS QUE COMPARTEN.**
>
> **Por lo tanto, SOLO NECESITÁS ESPECIFICAR EN DETALLE LOS REQUISITOS QUE DIFERENCIAN a los productos entre sí.**

> ⚠️ **Cruce con la cátedra — esta idea es transferible más allá del contexto de comprar software.** Es un principio de economía del esfuerzo: **detallá solo lo que sirve para decidir.**
>
> Si dos alternativas comparten una propiedad, **especificarla en detalle no aporta información para la decisión** — todas la cumplen. El detalle rinde donde hay diferencia.
>
> Conecta con lo que viste en el capítulo 16 (*la prioridad decide también cuánto se investiga*) y en el capítulo 5 (*no toda relación de trazabilidad vale su costo*). **Es la misma economía aplicada a la especificación.**

### Los tres procesos en paralelo 🟡

Una vez especificados los requisitos generales, **tres procesos se realizan en paralelo y se influyen mutuamente:**

```
   INGENIERÍA DE REQUISITOS ←→ INVESTIGACIÓN DE MERCADO
              ↕
       DISEÑO DE ARQUITECTURA
```

**Y las influencias cruzadas:**

> **Los requisitos determinan la dirección en la que buscamos productos; PERO A LA INVERSA, UN REQUISITO QUE NINGÚN PRODUCTO DEL MERCADO SATISFACE SE DESCARTA.**
>
> **La arquitectura restringe qué productos podemos usar; PERO A LA INVERSA, UNA ARQUITECTURA INCOMPATIBLE CON TODOS LOS PRODUCTOS DEL MERCADO SE CAMBIA.**

**Y un hallazgo empírico incómodo:**

> Se observó que **en la práctica LOS DESARROLLADORES RARA VEZ USAN LOS REQUISITOS PARA SELECCIONAR productos comerciales: LA FAMILIARIDAD con el producto o con su arquitectura genérica fue EL FACTOR DOMINANTE en la selección.**

### La técnica de tarea y soporte 🔴

Y acá hay una técnica muy elegante que vale la pena:

> En este estilo **NO SE ESPECIFICAN REQUISITOS DE PRODUCTO EN ABSOLUTO: se especifican LAS TAREAS QUE EL PRODUCTO DEBE SOPORTAR y, posiblemente, LOS PROBLEMAS ESPECÍFICOS A RESOLVER.**
>
> **Esas descripciones se les envían a los proveedores, QUE ENTONCES INDICAN CÓMO SOPORTARÍAN LAS TAREAS Y RESOLVERÍAN LOS PROBLEMAS.**

**Los tres beneficios:**

```
   · enfoca la selección en las propiedades que
     DIFERENCIAN a los productos
   · y en particular en las diferencias RELEVANTES PARA
     EL CLIENTE, porque resuelven SUS problemas
   · dirige la atención del proveedor A LAS NECESIDADES
     DE SU CLIENTE, y PUEDE HACER AFLORAR MANERAS DE USAR
     EL PRODUCTO QUE EL CLIENTE NO VEÍA pero el proveedor
     conoce de otros clientes
```

**Y su generalización para sistemas muy grandes:** dejar que el cliente **enuncie requisitos blandos EN FORMA DE LA META a alcanzar, en vez de la funcionalidad precisa requerida. Al proveedor se le pide entonces que explique CÓMO SU SISTEMA LOGRARÍA ESA META.**

> ⚠️ **Cruce con la cátedra — esta técnica es muy buena y muy robable.** Fijate lo que hace: **en vez de decir qué tiene que hacer el sistema, decís qué tenés que lograr vos y dejás que el otro proponga el cómo.**
>
> Es exactamente la distinción del capítulo 2 entre **requisito y solución**: cuando el cliente propone una solución en vez de un requisito, se pierde el espacio de alternativas. Acá se lo evita **por diseño del proceso**: no se pregunta por soluciones, se enuncian tareas y metas.
>
> Y el tercer beneficio es el más interesante: **el proveedor puede mostrarte usos que vos no habías imaginado.** Especificar de más te cierra esa puerta.

---

## 2. Gestión del ciclo de vida 🟡

### El síndrome de la parálisis por análisis 🔴

Esta sección tiene un diagnóstico muy bueno.

**El punto de partida:**

> **La regla empírica tradicional indica una tasa de cambio del 1 al 3 % POR MES** en términos de esfuerzo relacionado con los requisitos asignados. **Eso se traduce en MÁS DEL 30 % de tasa de cambio total para un proyecto de dos años de duración.**

**Y la reacción que produce:**

> Con gerentes de producto, analistas e ingenieros **volviéndose paranoicos** sobre esos cambios eternos, **observamos una DURACIÓN CRECIENTE DE LA FASE DE ANÁLISIS, es decir, ANTES DEL ARRANQUE REAL DEL PROYECTO.**
>
> **Ese síndrome de tratar de resolver todas las incertidumbres y fijar todos los requisitos —lo cual por supuesto es difícilmente posible y ES UN DESPERDICIO DE TIEMPO— llamado a menudo "PARÁLISIS POR ANÁLISIS", contribuyó a la duración y al costo del proyecto, PERO NO MEJORÓ MUCHO en reducir o lidiar con los cambios.**

### Las cinco causas raíz 🔴

Y esta lista es la más aprovechable de la sección:

**1. El proceso se percibe como demasiado técnico.**

> **La gestión de requisitos, y específicamente las técnicas formales de elicitación y análisis, SE PERCIBEN COMO EXCESIVAMENTE "TÉCNICAS". Los interesados, especialmente fuera del dominio de ingeniería, TIENEN POCO ENTENDIMIENTO de los pasos del proceso y de los resultados intermedios.**

**2. Las incertidumbres desaparecen en las fronteras.**

> **Las incertidumbres tienden a "DESAPARECER" en la interfaz entre comercialización, gestión de producto e ingeniería.** Eso está típicamente causado **por la necesidad de lograr consenso sobre contenidos bien definidos y accesibles. A menudo la actitud predominante es EMPEZAR Y ARREGLARLO DESPUÉS, con las demoras consiguientes.**

**3. Los clientes no tienen tiempo.**

> **Los clientes no tienen mucho tiempo ni recursos para contribuir activamente más allá de lo necesario para contratar y monitorear. LAS TÉCNICAS ÁGILES Y EVOLUTIVAS TIENEN ASÍ SUS LÍMITES para conseguir suficiente apoyo del cliente.**

**4. Los ingenieros adivinan.**

> **Al no conseguir todos los requisitos especificados con suficiente detalle, los ingenieros y jefes de proyecto TIENDEN A ADIVINAR las necesidades reales y así DAN RESPUESTAS EQUIVOCADAS a las incertidumbres.**

**5. Cada uno mira los riesgos que entiende.**

> **Los gerentes de producto y de proyecto se enfocan en los riesgos QUE LES RESULTAN SIGNIFICATIVOS. Ciertos tipos de riesgo —por ejemplo los de comercialización— NO SE ATIENDEN PORQUE NO PUEDEN ABORDARSE CON EL "LENGUAJE" de la gestión de producto o de proyecto.**

> ⚠️ **Cruce con la cátedra.** La causa 2 es la más fina de las cinco: **las incertidumbres no se resuelven en las fronteras entre áreas — SE PIERDEN.** Porque para pasar el asunto de un área a la siguiente hay que presentarlo como algo cerrado, y en ese acto la duda se borra del registro.
>
> Y la causa 4 es la consecuencia directa: **si el requisito no llega con suficiente detalle, alguien lo completa.** Es exactamente lo que el capítulo 11 llamaba **desambiguación inconsciente** — el 57 % de las ambigüedades se resolvían sin preguntarle a nadie.
>
> Y la causa 5 explica por qué ciertos riesgos nunca se atienden: **no es que se los descarte, es que no hay quien los sepa nombrar.**

### La sobre-ingeniería 🔴

Otra sección con un diagnóstico concreto:

> **La ausencia de vínculos claros con el valor de negocio INVITA A LA SOBRE-INGENIERÍA** — es decir, implementar funciones que pueden usarse rara vez, **o agregar funciones excesivas que no son necesarias para alcanzar los resultados de negocio deseados.**
>
> **Esa sobre-ingeniería no solo desperdicia recursos: MÁS IMPORTANTE AÚN, PRODUCE UNA PROLIFERACIÓN DE VARIANTES Y COMPLEJIDAD, ya que cada mejora adicional tiene efectos colaterales no deseados sobre otras funcionalidades.**

**Y la única salida que proponen:**

> **La única resolución de este problema es ADHERIR TERCAMENTE AL PRINCIPIO DE QUE LOS PEDIDOS DE CAMBIO DE INGENIERÍA DEBEN BASARSE EN REQUISITOS ASIGNADOS.**

### Sobre el desarrollo global 🟡

Una observación honesta sobre las desventajas:

> Mientras el lado positivo cuenta con **tiempo de ciclo más rápido, efectividad por zonas horarias y costo reducido**, no deberíamos cerrar los ojos ante las desventajas severas.
>
> **Trabajar en un proyecto distribuido globalmente significa SOBRECARGA de planificación y gestión de personas. Significa BARRERAS DE IDIOMA Y CULTURALES. Crea CELOS entre los ingenieros más caros, que temen perder sus trabajos mientras se los obliga a entrenar a sus contrapartes mucho más baratas.**

### El equipo núcleo 🔴

Y una recomendación concreta sobre roles:

> **Tres roles deben estar presentes en el equipo núcleo: un GERENTE DE PRODUCTO, un GERENTE DE COMERCIALIZACIÓN y un JEFE DE PROYECTO TÉCNICO.**
>
> Representan no solo a los principales interesados internos, **sino que también representan suficientemente la perspectiva de ventas y del cliente. Ese equipo núcleo DEBE TENER UN MANDATO CLARO PARA "SER DUEÑO" DEL PROYECTO.**
>
> **Encontramos que si ese equipo existe PERO LOS COMPROMISOS SUBYACENTES NO ESTÁN ESTABLECIDOS COMO LÍNEA BASE, NO TIENE NINGÚN VALOR.**

### Y una constatación que cierra el círculo 🔴

> **Un ciclo de vida útil TIENE QUE RECONOCER QUE LOS REQUISITOS PUEDEN NO ESTAR NUNCA COMPLETOS y de hecho pueden estar en un estado de "CONTINUO". A veces los requisitos son DELIBERADAMENTE INCOMPLETOS, y la ingeniería de requisitos DEBE LIDIAR CON ESA SITUACIÓN.**
>
> **El ciclo de vida debería guiar DEFINIENDO CRITERIOS DE DETENCIÓN — es decir, determinando QUÉ ES SUFICIENTEMENTE BUENO o SUFICIENTEMENTE ESTABLE.**

> ⚠️ **Cruce con la cátedra.** *"Criterios de detención"* es un concepto que la serie viene rozando sin nombrar: en el capítulo 16 (*puede no estar nunca completa en todos los aspectos*), en el capítulo 11 (*no hace falta encontrar todas las ambigüedades*), en el capítulo 12 (*una decisión satisfactoria, no la óptima*).
>
> **Acá se lo nombra y se lo vuelve responsabilidad del proceso:** no es que cada uno decida cuándo parar por intuición — **el proceso debería decir cuándo es suficiente.** Es la diferencia entre "sé que en algún momento hay que parar" y "sé cuándo".

### Cómo evaluar los requisitos 🔴

Y un criterio práctico muy bueno para no gastar esfuerzo parejo:

> Mientras cada requisito individual debe justificarse para sostener el caso de negocio, **se recomienda UNA EVALUACIÓN BASADA EN PARETO PARA ENFOCARSE DONDE TIENE SENTIDO.**
>
> Por ejemplo: **se seleccionan los requisitos MÁS PESADOS en términos de costo, impacto o valor de negocio, y se los analiza más específicamente sobre su propuesta de valor.**

**Y una advertencia sobre los casos de negocio:**

> **A menudo los casos de negocio ESTÁN VICIADOS DEL LADO DEL VALOR, y NUNCA SE LES HACE SEGUIMIENTO para ver si un requisito individual efectivamente contribuyó tanto valor como esperaban los que lo pidieron.**

**Y una regla de calidad de datos:**

> **Las inconsistencias y errores en los requisitos A MENUDO LOS ENCUENTRAN MEJOR LOS PROBADORES, PORQUE PIENSAN EN TÉRMINOS DE VERIFICABILIDAD.**
>
> **Si hay requisitos inconsistentes o vagos, DEBERÍAN CORREGIRSE EN EL ACTO.**

---

## 3. Introducir la IR en una organización 🔴

### El caso de negocio

Los autores reúnen los números que justifican invertir en requisitos:

```
   · el porcentaje de defectos del producto final que SE
     ORIGINARON EN REQUISITOS se estima en torno al 50 %
     (estimaciones bajas: 40 %; altas: 60 %)

   · los defectos introducidos en requisitos IMPACTAN
     CASI TODAS las demás actividades: alcance,
     arquitectura, diseño e implementación, pruebas, y
     propiedades no funcionales como seguridad,
     reutilización y capacitación

   · reparar un defecto de requisitos cuesta AL MENOS
     10 VECES MÁS una vez que el sistema está desplegado
     (algunas estimaciones llegan a 100 o 200 veces)

   · rehacer defectos de requisitos puede llevar EL 40 %
     DEL COSTO TOTAL del proyecto (algunas estimaciones
     llegan al 80 %)
```

### Y sin embargo 🔴

> **A pesar de esas estimaciones, la ingeniería de requisitos SE VE A MENUDO COMO UNA ACTIVIDAD AJENA, fuera de los intereses de los ingenieros, Y COMO UNA PÉRDIDA DE TIEMPO POR PARTE DE LOS GERENTES.**
>
> **Si los requisitos se especifican, la gestión de requisitos a menudo VA POR EL MISMO CAMINO QUE LA DOCUMENTACIÓN: una actividad para hacer DESPUÉS, cuando el "trabajo real" esté terminado.**
>
> **Los gerentes ven a menudo la IR como una actividad IMPRODUCTIVA, DISTINTA DEL DESARROLLO.**

**Y el problema de la coordinación entre áreas:**

> **Extrañamente, la misma perspectiva la comparten ventas, comercialización y gestión de producto.** La IR es claramente una actividad **INTERDISCIPLINARIA**, y eso **a menudo AGRAVA, en vez de reducir, las dificultades para introducir un proceso estándar.**
>
> Las dificultades **surgen a más tardar al mirar los aspectos de COORDINACIÓN ENTRE GRUPOS, que son muy pesados. Si no se acuerda con la función de ventas, SIEMPRE VA A HABER TENSIONES, porque los ingenieros tratan de ANALIZAR ANTES DE COMPROMETERSE, mientras que ventas...**

> ⚠️ **Cruce con la cátedra.** Esa última tensión es estructural y vale nombrarla: **ventas necesita comprometerse rápido para no perder al cliente; ingeniería necesita analizar antes de comprometerse para no prometer imposibles.** Los dos tienen razón desde su lugar.
>
> Es exactamente el **abismo entre comercialización y desarrollo** que el capítulo 13 listaba entre los siete desafíos. Y notá que no se resuelve con mejores técnicas de requisitos: **se resuelve acordando, o no se resuelve.**

---

## 4. Las habilidades del ingeniero de requisitos 🔴🔴

Esta es la sección más aprovechable del capítulo, y una buena manera de cerrar la serie.

**La distinción de base:**

> Distinguimos **HABILIDADES TÉCNICAS, que pueden aprenderse y aplicarse de manera reproducible entre personas distintas, de HABILIDADES PERSONALES, que son ÚNICAS DE CADA PERSONA.**
>
> **Ambas pueden desarrollarse, pero el desarrollo de las personales REQUIERE UNA REFLEXIÓN DEL INGENIERO SOBRE SU PROPIA PERSONA que no hace falta para las técnicas.**

### Las habilidades técnicas 🔴

| Grupo | Qué incluye |
|---|---|
| **De ingeniería de requisitos** | Siguiendo la división en elicitación, especificación y validación: **para elicitar hay que dominar técnicas de entrevista y de observación; la especificación requiere habilidades de MODELADO; y la validación, habilidades de validación empírica y formal** |
| **De ingeniería de sistemas** | La IR ocurre dentro de un proceso mayor donde se desarrollan hardware y otro software **y donde procesos de negocio y estructuras organizacionales pueden cambiarse.** Incluye: **gestionar la trazabilidad, determinar prioridades y hacer compromisos, innovación de producto, e integración de sistemas** |
| **De gestión** | El ingeniero **debe al menos CONOCER varias habilidades de gestión**: planificación de políticas, estrategia de producto, comercialización de producto, financiamiento y gestión de proyectos |

### Las habilidades personales 🔴🔴

Y estas son las que más valen.

#### Comunicación

> **Es característico de todo ingeniero en ejercicio la necesidad de comunicarse con ingenieros y especialistas de otras disciplinas. LA COMUNICACIÓN A TRAVÉS DE FRONTERAS DISCIPLINARIAS PUEDE OCUPAR HASTA EL 70 % DEL TIEMPO DE UN INGENIERO.**
>
> **PARA LOS INGENIEROS DE REQUISITOS, ESA ACTIVIDAD OCUPA DISCUTIBLEMENTE EL 100 % DE SU TIEMPO.**

**Las habilidades necesarias:** **escuchar, preguntar, presentar y escribir técnicamente.**

#### Cognitivas 🔴

> **Los ingenieros de requisitos SON CONSTRUCTORES DE PUENTES, porque deben conectar el mundo del usuario con el del desarrollador del sistema.**

Lo que eso exige:

```
   · poder APRENDER RÁPIDO los contornos de un dominio
     de conocimiento NUEVO
   · poder MANEJAR GRANDES VOLÚMENES de documentación
     y ABSTRAER LA ESENCIA de una masa de detalles
   · CONSTRUIR UNA VISIÓN HOLÍSTICA del sistema y su
     contexto
   · Y SABER CUÁNDO OMITIR DETALLES
```

#### Sociales 🔴

> Como todos los ingenieros, trabajan en equipos. **Pero AÚN MÁS QUE OTROS INGENIEROS, deben CERRAR DIFERENCIAS Y JUNTAR A PERSONAS CON TRASFONDOS DISTINTOS.**
>
> **El ingeniero de requisitos DEBE SER UN JUGADOR DE EQUIPO. Al mismo tiempo, DEBE PODER MANEJAR Y SUAVIZAR CONFLICTOS, y poder NEGOCIAR requisitos y prioridades con interesados QUE PUEDEN TENER INTERESES EN CONFLICTO.**

> ⚠️ **Cruce con la cátedra — leé esta sección pensando en vos.** Dos cosas:
>
> **1. El dato del 100 % del tiempo comunicándose** es el resumen más brutal de todo el libro. **No hay una parte del trabajo que sea "técnica y a solas".** Si te gusta la idea de un rol donde te sentás a modelar tranquilo, este no es.
>
> **2. Y "saber cuándo omitir detalles"** es la habilidad cognitiva más difícil de la lista, porque **no se puede enseñar con una regla.** Es lo mismo que el capítulo 2 decía de los expertos en elicitación —eligen bien y no saben explicar cómo— y lo que este mismo capítulo dijo en la Parte 1: los analistas experimentados mezclan técnicas sin reglas transmisibles.
>
> **Es la parte del oficio que se construye haciendo.** Y es también la razón por la cual la cátedra evalúa criterio fundamentado por encima de la respuesta canónica: **lo que se está entrenando es el juicio, no el procedimiento.**

**Y una observación de los autores sobre cómo se adquieren:**

> **Los programas académicos POR SÍ SOLOS NO PUEDEN CREAR NI FORMAR estas habilidades. DEBEN ADQUIRIRSE MEDIANTE AÑOS DE PRÁCTICA Y REFLEXIÓN sobre las prácticas efectivas en contextos variados.**

---

## 5. Hacia dónde va la disciplina 🔴

El cierre del libro. Cinco líneas de trabajo futuro:

**1. Predecir mejor los cambios a nivel de cada requisito.**

> **¿Qué requisitos son los MÁS VOLÁTILES y al mismo tiempo exponen al proyecto AL MAYOR RIESGO? ¿Cómo pueden atenderse con una arquitectura de solución suficientemente flexible?**

**2. Ingeniería de requisitos orientada al valor.**

> Mejorar la evaluación de los requisitos dentro de un caso de negocio, desde una perspectiva de gestión de portafolio. **¿Cuál es el caso de negocio detrás de los requisitos recolectados? ¿ES VÁLIDO ese caso de negocio? ¿Cuál es la CONTRIBUCIÓN de los requisitos a ese caso?**

**3. Reducir el tiempo hasta el arranque del proyecto.**

> **¿Qué es SUFICIENTEMENTE BUENO para el análisis de requisitos? ¿Qué nivel de cambio es factible manejar en escenarios y mercados dados?**

**4. Introducir técnicas de gestión del conocimiento** para la recolección, evaluación, modelado y recuperación de requisitos **y de las decisiones subyacentes.**

**5. Desarrollar más la perspectiva de ingeniería de sistemas**, cubriendo el uso de componentes comerciales, la variedad de socios o proveedores, **la gestión de la calidad que entregan esos socios externos**, y la adaptación de los requisitos de calidad **a medida que cambian las necesidades del negocio.**

---

## 6. El cierre del libro 🔴

Los autores resumen lo que hicieron, y de paso resumen el arco entero:

> Primero dimos **un marco de qué es la ingeniería de requisitos** en el contexto de una disciplina en evolución. Miramos **algunos riesgos específicos de proyecto tal como se materializan** y que frecuentemente señalan a la ingeniería de requisitos como inadecuada.
>
> **La ELICITACIÓN se describió como un área mayor QUE NECESITA MÁS MEJORA para manejar mejor las incertidumbres y así mitigar los riesgos de proyecto.**
>
> El ejemplo de las soluciones web se discutió **para subrayar la necesidad de lidiar con incertidumbres tanto en la dimensión del uso del producto COMO EN NO CONOCER A LOS INTERESADOS o a los usuarios potenciales.**

---

## Mapa de la Parte 2

```
   TENDENCIA 1 — COMPONENTES COMERCIALES
   ══► no recolectes todos los requisitos y después
       busques el producto ◄══
   especificá EN DETALLE SOLO LO QUE DIFERENCIA a los
   productos; lo que todos comparten no aporta a la
   decisión
   TÉCNICA DE TAREA Y SOPORTE: no especifiques el
   producto — especificá LA TAREA y dejá que el proveedor
   proponga el cómo

   ─────────────────────────────────────────────

   TENDENCIA 2 — CICLO DE VIDA
   "PARÁLISIS POR ANÁLISIS": tratar de fijar todo antes
   de empezar → más costo y duración, SIN reducir
   los cambios

   5 causas raíz:
   · el proceso se percibe como demasiado TÉCNICO
   · las incertidumbres DESAPARECEN en las fronteras
     entre áreas
   · los clientes NO TIENEN TIEMPO
   · los ingenieros ADIVINAN lo que falta
   · cada uno mira solo los riesgos que SABE NOMBRAR

   + CRITERIOS DE DETENCIÓN: el proceso debería decir
     cuándo es suficientemente bueno

   ─────────────────────────────────────────────

   TENDENCIA 3 — INTRODUCIR LA IR
   ~50 % de los defectos del producto final se originan
   en requisitos · repararlos cuesta 10 a 200 veces más
   tarde · rehacerlos puede llevar el 40 % del costo total

   y aun así se la ve como PÉRDIDA DE TIEMPO, "algo para
   hacer después, cuando el trabajo real esté terminado"

   ─────────────────────────────────────────────

   ══► TENDENCIA 4 — LAS HABILIDADES ◄══

   TÉCNICAS: de requisitos · de ingeniería de sistemas
             · de gestión

   PERSONALES:
   COMUNICACIÓN ─► otros ingenieros dedican hasta el 70 %
                   del tiempo a comunicarse;
                   EL INGENIERO DE REQUISITOS, EL 100 %
   COGNITIVAS ───► CONSTRUCTOR DE PUENTES: aprender rápido
                   un dominio nuevo · abstraer la esencia
                   de una masa de detalles · Y SABER
                   CUÁNDO OMITIR DETALLES
   SOCIALES ─────► cerrar diferencias · suavizar conflictos
                   · negociar con intereses encontrados

   "los programas académicos POR SÍ SOLOS no pueden
    formar estas habilidades: se adquieren con AÑOS DE
    PRÁCTICA Y REFLEXIÓN"
```

---

## Preguntas para chequear que quedó

1. Nombrá las cuatro tendencias que analiza el capítulo.
2. ¿Cada cuánto saca versión nueva un producto comercial promedio y para cuántas da soporte?
3. ¿Por qué mantener código que envuelve un producto comercial es más caro que mantener código propio?
4. ¿Por qué no tiene sentido recolectar todos los requisitos y después buscar el producto?
5. ¿Qué requisitos hay que especificar en detalle al evaluar productos comerciales y por qué?
6. Nombrá los tres procesos que corren en paralelo y cómo se influyen mutuamente.
7. ¿Qué factor domina en la práctica la selección de productos comerciales?
8. Explicá la técnica de tarea y soporte. Nombrá sus tres beneficios.
9. ¿Con qué distinción del capítulo 2 se conecta esa técnica?
10. ¿Qué es la "parálisis por análisis" y por qué no resuelve el problema que intenta resolver?
11. Nombrá las cinco causas raíz de ese síndrome.
12. ¿Por qué las incertidumbres "desaparecen" en las fronteras entre áreas?
13. ¿Qué hacen los ingenieros cuando el requisito no llega con suficiente detalle? ¿Con qué hallazgo del capítulo 11 se conecta?
14. ¿Por qué ciertos riesgos nunca se atienden, según la quinta causa?
15. ¿Qué invita a la sobre-ingeniería y qué consecuencia tiene además de desperdiciar recursos?
16. ¿Cuál es la única resolución que proponen para la sobre-ingeniería?
17. Nombrá los tres roles del equipo núcleo. ¿Qué pasa si el equipo existe pero los compromisos no están establecidos?
18. ¿Qué son los "criterios de detención" y por qué son responsabilidad del proceso?
19. ¿Qué criterio proponen para no evaluar todos los requisitos con el mismo esfuerzo?
20. ¿Por qué los probadores encuentran mejor las inconsistencias?
21. ¿Qué porcentaje de los defectos del producto final se origina en requisitos? ¿Cuánto cuesta repararlos tarde?
22. ¿Cómo se ve la ingeniería de requisitos desde la gerencia, a pesar de esos números?
23. ¿Por qué hay tensión estructural entre ingeniería y ventas?
24. Diferenciá habilidades técnicas de personales. ¿Qué requiere el desarrollo de las segundas?
25. Nombrá los tres grupos de habilidades técnicas.
26. ¿Qué porcentaje del tiempo dedica a comunicarse un ingeniero común? ¿Y un ingeniero de requisitos?
27. ¿Por qué se llama "constructor de puentes" al ingeniero de requisitos? Nombrá las cuatro habilidades cognitivas.
28. ¿Cuál de esas cuatro es la más difícil de enseñar y por qué?
29. ¿Qué habilidades sociales se le piden más que a otros ingenieros?
30. Según los autores, ¿cómo se adquieren realmente estas habilidades?
31. Nombrá las cinco líneas de trabajo futuro.
32. Según el cierre, ¿qué área necesita más mejora y para qué?

---

**FIN DEL CAPÍTULO 20 — PARTE 2**

**FIN DEL CAPÍTULO 20**

---

# 🏁 FIN DE LA SERIE

**Aurum, A. y Wohlin, C. (eds.) (2005). *Engineering and Managing Software Requirements*. Springer.**

**Los veinte capítulos completos, en español, con redacción propia.**

*Volvé al índice (`lectura-aurum-00-INDICE.md`) para el mapa completo y para ubicar qué capítulo corresponde a cada clase de tu cronograma.*
