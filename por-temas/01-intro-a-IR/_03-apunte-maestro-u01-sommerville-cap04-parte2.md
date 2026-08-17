# 📚 APUNTE MAESTRO — U1: Ingeniería de Requisitos (fundamentos) — Parte 2

**Materia:** Ingeniería de Requisitos (electiva)
**Unidad:** 1
**Parte:** 2 de 2 — *El proceso: cómo se descubren, validan y gestionan los requerimientos*
**Requiere:** Parte 1 leída (requerimientos de usuario/sistema, funcionales/no funcionales, SRS, especificación). Todo lo de allá se asume y se usa.
**Alcance de esta parte:** el proceso de RE y su espiral · elicitación y análisis (entrevistas, escenarios, casos de uso, etnografía) · validación · gestión de requerimientos. Cierra con el **checkpoint de la unidad completa**.

---

## 0. Dónde estamos parados

En la Parte 1 quedó definido el **producto**: qué es un requerimiento, en qué niveles se escribe y con qué técnicas se especifica. Pregunta obvia que quedó flotando: ¿y de dónde **salen** los requerimientos? Nadie te entrega la tabla de la dosis de insulina hecha. Alguien tuvo que sentarse con médicos, enfermeros y gerentes, sacarles información que ni ellos sabían que tenían, negociar sus contradicciones, escribir el documento, chequear que dice lo que el cliente de verdad quiere — y después bancarse que todo eso **cambie**. Ese proceso completo es esta parte:

```
      ┌──────────────────────────────────────────────────────────┐
      │                  EL PROCESO DE RE (§1)                   │
      │                                                          │
      │   Estudio de      Elicitación      Especifi-   Valida-   │
      │   factibilidad ─► y análisis   ─►  cación  ─►  ción      │
      │                      (§2)         (Parte 1)     (§3)     │
      │         ▲                                        │       │
      │         └──────── iteración en espiral ◄─────────┘       │
      └──────────────────────────┬───────────────────────────────┘
                                 │ y por debajo de todo, siempre:
                                 ▼
                 GESTIÓN DE REQUERIMIENTOS (§4)
                 (los requerimientos VAN a cambiar)
```

---

## 1. El proceso de ingeniería de requisitos 🔴

### 1.1 Las cuatro actividades de alto nivel

El proceso de RE incluye cuatro actividades de alto nivel, cada una con su pregunta:

1. **Estudio de factibilidad** → ¿el sistema es útil para el negocio? ¿vale la pena encararlo?
2. **Elicitación y análisis** → ¿cuáles son los requerimientos? (descubrirlos)
3. **Especificación** → ¿cómo los convertimos a una forma estándar? (la Parte 1 entera fue esto)
4. **Validación** → ¿los requerimientos definen el sistema que el cliente realmente quiere?

*(Elicitación — término nuevo: del inglés "elicit", sonsacar/extraer; el arte de sacarle a la gente información que muchas veces no sabe explicitar. Es EL término de la materia, incorporalo ya.)*

### 1.2 El punto clave: NO es una secuencia, es una espiral 🔴

Dibujadas en fila parecen una cadena de montaje: primero factibilidad, después elicitación, después especificar, después validar, listo. **En la práctica, la RE es un proceso iterativo con las actividades intercaladas.** La forma correcta de visualizarlo es una **espiral**:

```
   Vuelta 1 (anillo interior — arranque del proceso):
   ┌─ Elicitar requerimientos DE NEGOCIO ─► Especificarlos ─► Revisarlos ─┐
   │                                                                      │
   ▼ Vuelta 2 (se gana detalle):                                          │
   ┌─ Elicitar requerimientos DE USUARIO ─► Especificarlos ─► Prototipar ─┤
   │                                                                      │
   ▼ Vuelta 3 (anillo exterior — detalle fino):                           │
   ── Elicitar requerimientos DE SISTEMA ─► Especificar y modelar ─► Validar
                                                       │
                                                       ▼
                                        DOCUMENTO DE REQUERIMIENTOS
                                              (la salida)
```

*(Descripción: las tres actividades — elicitación, especificación, validación — se recorren una y otra vez en vueltas; cada vuelta trabaja a un nivel más detallado que la anterior: de negocio → de usuario → de sistema. La espiral termina emitiendo el documento de requerimientos.)*

Lecturas importantes de este modelo, todas evaluables:

- **El esfuerzo se desplaza con las vueltas:** temprano en el proceso, la mayor parte del esfuerzo va a entender los requerimientos de negocio de alto nivel, los no funcionales y los de usuario; en las vueltas exteriores, a elicitar y entender los requerimientos de sistema detallados.
- **La espiral admite niveles de detalle variables:** la cantidad de vueltas varía y **se puede salir de la espiral antes** — después de elicitar parte o todos los requerimientos de usuario, según cuánto detalle necesite el proyecto (¿te acordás de §5.2 de la Parte 1? sistemas críticos y outsourcing necesitan más vueltas; desarrollo interno iterativo, menos).
- **El desarrollo ágil puede engancharse acá:** en lugar de prototipar, se puede desarrollar el sistema junto con los requerimientos.
- El tiempo y esfuerzo por actividad en cada vuelta depende de la etapa del proceso y del tipo de sistema.

### 1.3 El estudio de factibilidad 🟡

Estudio **corto y enfocado**, que debe ocurrir **temprano** en el proceso, y responde tres preguntas:

1. ¿El sistema **contribuye a los objetivos generales** de la organización?
2. ¿Puede implementarse **dentro del cronograma y presupuesto** con la tecnología actual?
3. ¿Puede **integrarse con los otros sistemas** que ya se usan?

Regla de decisión brutal y simple: **si la respuesta a cualquiera de las tres es "no", probablemente no haya que seguir adelante con el proyecto**. Barato de hacer, ahorra fortunas.

### 1.4 RE ≠ aplicar un método de modelado

Hay quien considera que la ingeniería de requisitos consiste en aplicar un método de análisis estructurado (por ejemplo, análisis orientado a objetos): analizar el sistema, producir un conjunto de modelos gráficos —como modelos de casos de uso— y que eso funcione como especificación, anotada con información extra (performance requerida, confiabilidad). Los métodos estructurados **tienen su rol** — pero la RE es **mucho más** que eso: la elicitación en particular es una actividad **centrada en humanos**, y a la gente **no le gustan las restricciones que un modelo rígido de sistema le impone** a la interacción. Vas a ver esta tensión en carne viva en la sección de entrevistas y etnografía.

Y el cierre de esta sección planta la semilla de la §4: **en virtualmente todos los sistemas los requerimientos cambian** — la gente involucrada entiende mejor qué quiere, la organización compradora cambia, el hardware/software/entorno organizacional se modifican. El proceso de manejar esos cambios es la **gestión de requerimientos**.

### 📝 Para el parcial, si te preguntan

**"Describa las actividades del proceso de ingeniería de requisitos y cómo se organizan."**
El proceso incluye cuatro actividades de alto nivel: estudio de factibilidad (¿el sistema es útil al negocio?), elicitación y análisis (descubrir los requerimientos), especificación (convertirlos a una forma estándar) y validación (chequear que definen el sistema que el cliente quiere). En la práctica no son secuenciales: la RE es un proceso iterativo donde elicitación, especificación y validación se intercalan en una espiral, cuyas vueltas van ganando detalle (requerimientos de negocio → de usuario → de sistema) y cuya salida es el documento de requerimientos.

**"¿Qué preguntas responde un estudio de factibilidad?"**
Es un estudio corto y temprano que responde: si el sistema contribuye a los objetivos generales de la organización, si puede implementarse en cronograma y presupuesto con la tecnología actual, y si puede integrarse con los demás sistemas en uso. Si alguna respuesta es negativa, probablemente el proyecto no deba continuar.

---

## 2. Elicitación y análisis de requerimientos 🔴

Después del estudio de factibilidad inicial, la siguiente etapa es la elicitación y análisis: los ingenieros de software trabajan con clientes y usuarios finales para averiguar sobre el **dominio de aplicación**, los **servicios** que el sistema debe proveer, la **performance** requerida, las **restricciones de hardware**, etcétera. Es la etapa más humana, más política y más resbaladiza de todo el proceso.

### 2.1 Stakeholders — la definición completa 🔴

En la Parte 1 la dejamos en una glosa; ahora sí:

> **Definición** — Un **stakeholder** del sistema es cualquier persona o rol que tiene alguna **influencia directa o indirecta sobre los requerimientos**: usuarios finales que van a interactuar con el sistema y cualquier otro en la organización que se vea **afectado** por él. También pueden serlo ingenieros que desarrollan o mantienen sistemas relacionados, gerentes de negocio, expertos de dominio y representantes gremiales.

**Los stakeholders del MHC-PMS**, para que veas lo lejos que llega la lista más allá de "los que lo usan":

1. **Pacientes** — su información se registra en el sistema (afectados, aunque jamás lo toquen).
2. **Médicos** — evalúan y tratan pacientes.
3. **Enfermeros** — coordinan consultas con los médicos y administran algunos tratamientos.
4. **Recepcionistas médicos** — gestionan los turnos de los pacientes.
5. **Personal de IT** — instala y mantiene el sistema.
6. **Gerente de ética médica** — debe asegurar que el sistema cumpla las pautas éticas vigentes de cuidado del paciente.
7. **Gerentes de salud** — obtienen información de gestión del sistema.
8. **Personal de registros médicos** — responsable de que la información pueda mantenerse y preservarse, y de que los procedimientos de registro se implementen correctamente.

Y además de los stakeholders, los requerimientos también vienen del **dominio de aplicación** (¿te suena de la madriguera de la Parte 1?) y de **otros sistemas** que interactúan con el que se especifica. Todas esas fuentes deben considerarse durante la elicitación.

🕳️ **Madriguera — Viewpoints (puntos de vista)**
Una forma de organizar todo eso: un *viewpoint* agrupa y estructura los requerimientos de un conjunto de stakeholders con algo en común (usuarios finales, gerentes, etc.). Cada fuente de requerimientos (stakeholders, dominio, sistemas) puede representarse como un viewpoint que muestra un subconjunto de los requerimientos; las perspectivas no son independientes — se **solapan** en requerimientos comunes. Sirven para identificar informantes y estructurar descubrimiento y documentación.
*Volvé al camino — con saber que existen y para qué sirven alcanza.*

### 2.2 El proceso de elicitación y análisis: cuatro actividades en ciclo 🔴

```
        ┌────────────────────────────────────────────────────┐
        │                                                    │
        ▼                                                    │
  1. DESCUBRIMIENTO  ──►  2. CLASIFICACIÓN   ──►  3. PRIORIZACIÓN │
     de requerimientos       y ORGANIZACIÓN          y NEGOCIACIÓN │
        ▲                                                    │    │
        │                                                    ▼    │
        └────────────────────  4. ESPECIFICACIÓN  ◄───────────────┘
                                  de requerimientos
```

*(Descripción: cuatro actividades dispuestas en ciclo con retroalimentación continua de cada una hacia las otras. El ciclo arranca en el descubrimiento y termina en la documentación; se recorre varias veces.)*

1. **Descubrimiento de requerimientos:** interactuar con los stakeholders para descubrir sus requerimientos; también se descubren acá los requerimientos de dominio (de stakeholders y documentación). Hay varias técnicas complementarias — §2.4 en adelante.
2. **Clasificación y organización:** tomar la colección **desestructurada** de requerimientos, agrupar los relacionados y organizarlos en clusters coherentes. La forma más común de agrupar: usar un **modelo de la arquitectura del sistema** para identificar subsistemas y asociar requerimientos a cada uno — otra prueba de que, en la práctica, ingeniería de requisitos y diseño arquitectónico **no pueden ser actividades completamente separadas** (ya lo habíamos visto desde el lado de la especificación, §6.1 de la Parte 1).
3. **Priorización y negociación:** con múltiples stakeholders, los requerimientos **van a entrar en conflicto** — inevitable. Esta actividad prioriza, y encuentra y resuelve los conflictos por **negociación**: usualmente los stakeholders tienen que reunirse para resolver diferencias y acordar requerimientos de **compromiso**.
4. **Especificación:** los requerimientos se documentan y **alimentan la próxima vuelta** de la espiral. Pueden producirse documentos formales o informales.

El proceso es **iterativo con retroalimentación continua** entre actividades: arranca en el descubrimiento, termina en la documentación, y **la comprensión del analista mejora con cada vuelta del ciclo**. El ciclo termina cuando el documento de requerimientos está completo.

Dos detalles finos de esta etapa, típicos de pregunta conceptual:

- En la especificación temprana puede producirse una **versión inicial incompleta** del documento (secciones faltantes), o documentarse de forma totalmente distinta: planillas, o **tarjetas** — muy efectivas porque los stakeholders pueden **manipularlas, cambiarlas y reorganizarlas** con las manos (¿te acordás de VOLERE y de las user stories? mismo espíritu).
- El costado político de la negociación: es **imposible satisfacer completamente a todos** los stakeholders — pero si algunos sienten que **sus vistas no fueron consideradas apropiadamente**, pueden deliberadamente intentar **socavar el proceso de RE**. Por eso las negociaciones se organizan **regularmente**, no una vez al final.

### 2.3 Por qué elicitar es difícil (las cinco razones) 🔴

Lista corta, jugosa, y de las más preguntables de la unidad. Elicitar y entender requerimientos de los stakeholders es difícil porque:

1. **Los stakeholders no saben lo que quieren** del sistema salvo en términos generales; les cuesta articular qué quieren que haga; pueden pedir cosas **irrealizables** porque no saben qué es factible y qué no.
2. **Lo expresan en sus propios términos y con conocimiento implícito de su trabajo.** Los ingenieros de requerimientos, sin experiencia en el dominio del cliente, pueden no entender esos requerimientos.
3. **Stakeholders distintos → requerimientos distintos, expresados de formas distintas.** Hay que descubrir todas las fuentes potenciales y detectar coincidencias y conflictos.
4. **Factores políticos:** un gerente puede exigir requerimientos específicos porque le **aumentan la influencia** dentro de la organización.
5. **El entorno económico y de negocio es dinámico:** cambia *durante* el propio análisis — la importancia de cada requerimiento se mueve, y aparecen requerimientos nuevos de stakeholders nuevos que no habían sido consultados.

Fijate el patrón sistémico: (1) y (2) son problemas de **comunicación individual**, (3) y (4) de **organización y poder**, (5) de **tiempo**. Las técnicas que siguen atacan distintos frentes de este mapa — ninguna los cubre todos, y por eso **se combinan**.

### 2.4 Técnica 1 — Entrevistas 🔴

Las entrevistas con stakeholders, formales o informales, son parte de la mayoría de los procesos de RE: el equipo hace preguntas sobre el sistema que se usa actualmente y el que se va a desarrollar; los requerimientos se derivan de las respuestas. Dos tipos:

- **Cerradas:** el stakeholder responde un conjunto **predefinido** de preguntas.
- **Abiertas:** sin agenda predefinida; el equipo explora un rango de temas y desarrolla una mejor comprensión de las necesidades.

En la práctica, las entrevistas son una **mezcla**: necesitás respuestas a ciertas preguntas, y esas respuestas abren temas que se conversan de forma menos estructurada. Ojo con el extremo: las discusiones **completamente abiertas rara vez funcionan** — hacen falta preguntas para arrancar y para mantener el foco en el sistema.

**Para qué sirven:** entendimiento general de **qué hacen los stakeholders**, cómo podrían **interactuar con el sistema nuevo** y las **dificultades que tienen con los sistemas actuales**. A la gente le gusta hablar de su trabajo, así que se suma a las entrevistas con gusto.

**Para qué NO sirven (y por qué)** — esto es lo más evaluable de la sección:

1. **Conocimiento del dominio de aplicación**, por dos motivos:
   - Los especialistas usan **jerga propia del dominio**, y no pueden discutir sus requerimientos sin ella; la usan de forma **precisa y sutil**, fácil de malinterpretar para un ingeniero de requerimientos.
   - Parte del conocimiento de dominio es **tan familiar que no se menciona**: al especialista le parece o muy difícil de explicar o demasiado obvio para decirlo. El ejemplo clásico: para un bibliotecario, es evidente que toda adquisición se cataloga **antes** de entrar a la biblioteca — tan evidente que no lo dice, el entrevistador no lo registra, y el requerimiento queda afuera.
2. **Requerimientos organizacionales**, por las **relaciones de poder sutiles** entre las personas: las estructuras organizacionales publicadas **rara vez coinciden** con cómo se decide en la realidad, pero los entrevistados no van a revelarle la estructura real (vs. la teórica) **a un extraño**. En general, la gente es reacia a discutir cuestiones políticas y organizacionales que afectan los requerimientos.

**El entrevistador efectivo** tiene dos características:

1. **Mente abierta:** sin ideas preconcebidas sobre los requerimientos, dispuesto a escuchar; si el stakeholder trae un requerimiento sorprendente, dispuesto a **cambiar su visión** del sistema.
2. **Sabe arrancar la conversación con un disparador:** una pregunta trampolín, una propuesta de requerimiento, o trabajar juntos sobre un prototipo. Decirle a la gente "**contame qué querés**" no produce información útil — a casi todos les resulta mucho más fácil hablar **en un contexto definido** que en términos generales.

**Cierre de balance:** la información de entrevistas **complementa** otras fuentes (documentación de procesos de negocio, sistemas existentes, observación de usuarios). A veces, fuera de la documentación del sistema, las entrevistas son la única fuente. Pero **por sí solas tienden a perder información esencial** → siempre en conjunto con otras técnicas.

### 2.5 Técnica 2 — Escenarios 🔴

La palanca psicológica de esta técnica: a la gente le resulta más fácil **relacionarse con ejemplos de la vida real** que con descripciones abstractas — puede **entender y criticar** un escenario de cómo interactuaría con el sistema. De esa discusión, el ingeniero de requerimientos formula los requerimientos reales.

> **Definición** — Un **escenario** es la descripción de una **sesión de interacción de ejemplo** con el sistema. Cada escenario cubre una o pocas interacciones posibles. Son particularmente útiles para **agregar detalle a un esbozo** de requerimientos.

Un escenario arranca como un bosquejo de la interacción y, durante la elicitación, se le agrega detalle hasta la descripción completa. En su forma más general incluye **cinco elementos**:

1. Descripción de lo que sistema y usuarios **esperan al inicio** del escenario.
2. Descripción del **flujo normal** de eventos.
3. Descripción de **qué puede salir mal** y cómo se maneja.
4. Información de **otras actividades** que puedan estar ocurriendo al mismo tiempo.
5. Descripción del **estado del sistema al finalizar**.

**El caso completo: cargar la historia clínica de un paciente nuevo en el MHC-PMS.** El contexto: cuando un paciente nuevo llega a una clínica, el recepcionista le crea el registro con los datos personales (nombre, edad, etc.); después un enfermero lo entrevista y recolecta la historia clínica; después viene la primera consulta con el médico, que diagnostica y recomienda tratamiento si corresponde. El escenario cubre el tramo del enfermero:

- **Supuesto inicial:** el paciente ya pasó por el recepcionista, que creó el registro y cargó la información personal. Un enfermero está logueado y va a recolectar la historia.
- **Flujo normal:** el enfermero busca al paciente **por apellido**; si hay más de uno con el mismo apellido, desambigua por **nombre de pila y fecha de nacimiento**. Elige la opción de menú de agregar historia clínica y sigue una serie de instrucciones del sistema para ir cargando: consultas previas por salud mental en otros lados (texto libre), condiciones médicas existentes (selección de menú), medicación actual (selección de menú), alergias (texto libre) y vida en el hogar (formulario).
- **Qué puede salir mal (y su manejo):**
  - El registro del paciente **no existe o no se encuentra** → el enfermero crea un registro nuevo y carga la información personal.
  - La condición o medicación **no figura en el menú** → opción "otro" + texto libre describiéndola.
  - El paciente **no puede o no quiere** dar información de su historia → el enfermero registra en texto libre esa imposibilidad/negativa, y el sistema **imprime el formulario estándar de exclusión** que declara que la falta de información puede limitar o demorar el tratamiento; se firma y se le entrega al paciente.
- **Actividades concurrentes:** mientras se carga la información, otros miembros del personal pueden **consultar** el registro, pero **no editarlo**.
- **Estado final:** el usuario sigue logueado; el registro del paciente, con su historia clínica, quedó en la base de datos; se agregó al log del sistema un registro con hora de inicio y fin de la sesión y el enfermero involucrado.

Releé el escenario buscando los cinco elementos: están **todos**, en orden. Y fijate cuánta información de requerimientos destila una sola historia: desambiguación de homónimos, catálogos con escape a texto libre, control de concurrencia lectura-sí/escritura-no, trazabilidad por log, y hasta un requerimiento legal-operativo (el formulario de exclusión firmado). Eso es lo que un stakeholder jamás te hubiera dictado en abstracto, y te lo cuenta natural cuando le preguntás "¿y qué pasa si el paciente no quiere contarte nada?".

Los escenarios pueden escribirse como texto, con diagramas, capturas de pantalla, etc.; o con enfoques más estructurados como escenarios de eventos o **casos de uso**. Las **user stories** de XP (madriguera de la Parte 1) son un tipo de escenario de requerimientos.

### 2.6 Técnica 3 — Casos de uso 🔴

> **Definición** — Los **casos de uso** son una técnica de descubrimiento de requerimientos que **identifica a los actores involucrados en una interacción y nombra el tipo de interacción**. Se complementan con información adicional que describe la interacción con el sistema (descripción textual, o modelos gráficos como diagramas de secuencia o de estados de UML).

*(Origen: se introdujeron en el método Objectory, uno de los métodos orientados a objetos que después confluyeron en UML — hoy son parte fundamental de UML y su uso para elicitación está masivamente difundido.)*

La gramática visual del diagrama de casos de uso de alto nivel:

- **Actores** (humanos **u otros sistemas**) → figuras de palo.
- Cada **clase de interacción** → una **elipse nombrada**.
- **Líneas** conectan actores con las interacciones; opcionalmente, **puntas de flecha** indican quién **inicia** la interacción.
- El **conjunto** de casos de uso representa **todas** las interacciones posibles que se describirán en los requerimientos del sistema.

**El diagrama del MHC-PMS:**

```
                          ┌─────────────────┐
   Recepcionista 🧍───────►  Registrar      │
        │                 │  paciente       │
        │                 └─────────────────┘
        │                 ┌─────────────────┐        🧍 Gerente
        └────────────────►│  Ver info.      │◄──────────┤
                          │  personal       │           │
                          └─────────────────┘           │
                          ┌─────────────────┐           │
                          │  Exportar       │◄──────────┤
                          │  estadísticas   │           │
                          └─────────────────┘           │
                          ┌─────────────────┐           │
                     ┌───►│  Generar        │◄──────────┘
                     │    │  reporte        │
                     │    └─────────────────┘
                     │    ┌─────────────────┐
   Enfermero 🧍──────┼───►│  Ver registro   │
        │            │    └─────────────────┘
        │            │    ┌─────────────────┐
        └────────────┼───►│  Editar         │
                     │    │  registro       │
                     │    └─────────────────┘
                     │    ┌─────────────────┐
   Médico 🧍─────────┴───►│  Configurar     │
   (conecta con Ver,      │  consulta       │
    Editar, Generar       └─────────────────┘
    reporte y Configurar
    consulta)
```

*(Descripción: cuatro actores. El Recepcionista se conecta con "Registrar paciente" y "Ver información personal". El Gerente, con "Ver información personal", "Exportar estadísticas" y "Generar reporte". El Enfermero, con "Ver registro" y "Editar registro". El Médico, con "Ver registro", "Editar registro", "Configurar consulta" y "Generar reporte".)*

**Cada caso de uso se documenta además con una descripción textual**, que puede vincularse a otros modelos UML que desarrollen el escenario en más detalle. El ejemplo del caso "Configurar consulta": permite que dos o más médicos, trabajando en oficinas distintas, vean el mismo registro al mismo tiempo. Un médico inicia la consulta eligiendo a los participantes de un menú de médicos conectados; el registro del paciente se muestra en las pantallas de todos, pero **solo el iniciador puede editarlo**; se crea además una ventana de chat de texto para coordinar acciones (la conferencia de voz se asume configurada por separado, por teléfono).

**¿Escenario y caso de uso son lo mismo?** No hay una distinción rígida, y las dos posturas conviven:

- Para algunos, **cada caso de uso ES un único escenario**.
- Para otros, un caso de uso **encapsula un conjunto de escenarios**, donde cada escenario es **un hilo único** a través del caso de uso: un escenario para la interacción normal + un escenario por cada excepción posible (¿ves cómo mapea al escenario del enfermero de §2.5? flujo normal + tres "qué puede salir mal" = cuatro hilos).

En la práctica podés usarlos de cualquiera de las dos formas.

**El límite compartido de escenarios y casos de uso:** son técnicas efectivas para elicitar requerimientos de stakeholders que **interactúan directamente** con el sistema — cada tipo de interacción se puede representar como caso de uso. Pero como se enfocan en interacciones, **no son tan efectivas** para elicitar: restricciones, requerimientos de negocio de alto nivel, **no funcionales**, o requerimientos de **dominio**.

🕳️ **Madriguera — UML más allá de los casos de uso**
UML incluye otros diagramas que van a aparecer en tu carrera: los de **secuencia** (qué mensajes se intercambian en respuesta a un evento, en orden temporal) y los de **estados** (cómo cambia el estado del sistema ante eventos) son los que típicamente desarrollan un caso de uso en detalle.
*Volvé al camino — acá alcanza con el diagrama de casos de uso; el resto de UML se profundiza en materias de diseño.*

### 2.7 Técnica 4 — Etnografía 🔴

El fundamento, que es una idea grande: **los sistemas de software no existen aislados** — se usan en un **contexto social y organizacional**, y de ese contexto pueden derivar (o verse restringidos) requerimientos del sistema. Satisfacerlos suele ser **crítico para el éxito**: una razón por la que muchos sistemas se entregan y **nunca se usan** es que sus requerimientos no tomaron en cuenta cómo el contexto social y organizacional afecta la operación práctica del sistema.

> **Definición** — La **etnografía** es una técnica **observacional**: un analista **se sumerge en el entorno de trabajo** donde se usará el sistema, observa el trabajo diario y toma notas de las **tareas reales** en las que los participantes están involucrados. Su valor: descubre **requerimientos implícitos** que reflejan cómo la gente **realmente** trabaja — y no los procesos formales que la organización define.

*(Etnografía — término nuevo: método de las ciencias sociales, literalmente "describir al pueblo": estudiar una comunidad observándola desde adentro, en su ambiente, en lugar de preguntarle desde afuera.)*

¿Por qué observar en vez de preguntar? Porque conecta directo con los límites de las entrevistas (§2.4): a la gente le resulta muy difícil articular los detalles de su trabajo porque es su **segunda naturaleza**; entiende su propio trabajo pero no siempre su relación con el resto del trabajo de la organización; y los factores sociales y organizacionales que afectan el trabajo, invisibles para los individuos, **se vuelven claros para un observador imparcial**. Ejemplo: un grupo de trabajo se **auto-organiza** para que todos conozcan el trabajo de los demás y puedan cubrir a un ausente — en una entrevista nadie lo menciona, porque el grupo no lo ve como parte integral de su trabajo.

**El respaldo empírico fundacional:** los estudios etnográficos pioneros del trabajo de oficina mostraron que las prácticas reales eran **mucho más ricas, complejas y dinámicas** que los modelos simples asumidos por los sistemas de automatización de oficinas — y esa diferencia entre trabajo supuesto y trabajo real fue **la razón principal** de que esos sistemas no tuvieran efecto significativo en la productividad. Desde entonces la etnografía se integró a la ingeniería de software vinculándola con métodos de RE y documentando patrones de interacción en sistemas cooperativos.

**Los dos tipos de requerimientos que la etnografía descubre especialmente bien** 🔴 (con su par de ejemplos de control de tráfico aéreo — el dominio estrella de estos estudios):

1. **Requerimientos derivados de cómo la gente realmente trabaja**, no de cómo las definiciones de proceso dicen que debería trabajar. El caso: los controladores aéreos a veces **apagan la alarma de conflicto** que detecta aviones con rutas que se cruzan, aunque el procedimiento normal diga que debe usarse — porque deliberadamente ponen aviones en rutas que se cruzan **por un corto tiempo** para gestionar el espacio aéreo, con una estrategia de control que garantiza separarlos antes de que haya problema, y la alarma **los distrae** de su trabajo.
2. **Requerimientos derivados de la cooperación y la conciencia de la actividad ajena.** El caso: los controladores usan la conciencia del trabajo de los controladores de **sectores adyacentes** para **predecir** cuántos aviones van a entrar a su sector, y modifican su estrategia según esa carga prevista. Consecuencia de requerimiento: un sistema automatizado de control aéreo debe permitir a los controladores de un sector tener **algo de visibilidad** del trabajo en los sectores vecinos.

**Etnografía + prototipado, el combo:**

```
Análisis      ─►  Prototipado   ─►  Evaluación del  ─►  Desarrollo
etnográfico       del sistema       prototipo           genérico del sistema
     ▲                                   │
     │       reuniones de debriefing     │
     └──── (el prototipo genera las ─────┘
            preguntas que enfocan la
            siguiente fase del estudio)
```

*(Descripción: la etnografía informa el desarrollo del prototipo, de modo que se requieren menos ciclos de refinamiento; a su vez, el prototipado enfoca la etnografía, identificando problemas y preguntas que se discuten con el etnógrafo, quien busca las respuestas durante la siguiente fase del estudio del sistema.)*

**Los límites de la etnografía** (siempre cerramos con los límites — es lo que te piden comparar): por su foco en el usuario final, no siempre es apropiada para descubrir requerimientos **organizacionales o de dominio**; no siempre puede identificar **features nuevas** que deban agregarse; no es un enfoque completo de elicitación por sí sola → **complementarla** con otros, como el análisis de casos de uso.

### 📝 Para el parcial, si te preguntan

**"¿Qué es un stakeholder? Dé ejemplos."**
Es cualquier persona o rol con influencia directa o indirecta sobre los requerimientos del sistema: desde usuarios finales hasta cualquier afectado por él — en un sistema de gestión de pacientes: los pacientes cuyos datos registra, médicos, enfermeros, recepcionistas, personal de IT, un gerente de ética, gerentes que extraen información y el personal de registros médicos.

**"Describa el proceso de elicitación y análisis."**
Es un ciclo iterativo de cuatro actividades con retroalimentación continua: descubrimiento de requerimientos (interactuar con stakeholders y documentación), clasificación y organización (agrupar en clusters coherentes, usualmente por subsistemas de la arquitectura), priorización y negociación (resolver los conflictos inevitables entre stakeholders y acordar compromisos) y especificación (documentar y alimentar la siguiente vuelta). La comprensión mejora en cada ciclo, y termina con el documento de requerimientos completo.

**"¿Por qué es difícil elicitar requerimientos?"**
Porque los stakeholders no saben qué quieren salvo en términos generales y pueden pedir cosas irrealizables; los expresan en sus propios términos con conocimiento implícito del dominio; distintos stakeholders tienen requerimientos distintos y conflictivos; hay factores políticos (requerimientos que aumentan la influencia de quien los pide); y el entorno de negocio cambia durante el propio análisis.

**"Compare las técnicas de elicitación."**
Las entrevistas (cerradas, abiertas o mixtas) dan un entendimiento general del trabajo y las dificultades de los stakeholders, pero fallan con el conocimiento de dominio (jerga, conocimiento tácito) y los requerimientos organizacionales (política, poder). Los escenarios y casos de uso funcionan porque la gente critica mejor ejemplos concretos que abstracciones, y capturan las interacciones directas con el sistema — pero son débiles para restricciones, no funcionales y requerimientos de dominio o de negocio de alto nivel. La etnografía observa cómo se trabaja realmente y descubre requerimientos implícitos, sociales y de cooperación, pero no releva requerimientos organizacionales/de dominio ni propone features nuevas. Ninguna es completa: se combinan.

---

## 3. Validación de requerimientos 🔴

> **Definición** — La **validación de requerimientos** es el proceso de chequear que los requerimientos efectivamente **definen el sistema que el cliente realmente quiere**. Se **solapa con el análisis** (ambos buscan problemas en los requerimientos), pero su momento y su pregunta son otros: el análisis trabaja sobre requerimientos crudos en descubrimiento; la validación, sobre el documento ya redactado.

### 3.1 Por qué importa tanto: la economía del error

Un error en el documento de requerimientos que se descubre **durante el desarrollo o ya en servicio** dispara costos de retrabajo enormes. La regla: **arreglar un problema de requerimientos mediante un cambio al sistema cuesta mucho más que reparar un error de diseño o de código**. ¿Por qué? Efecto dominó: un cambio de requerimientos normalmente implica cambiar **también el diseño y la implementación** — y después **re-testear** el sistema. Cuanto más tarde se detecta, más capas construidas encima hay que tocar.

```
  Error detectado en...      Hay que rehacer...
  ─────────────────────      ─────────────────────────────────
  Validación de reqs.   →    el requerimiento          (barato)
  Diseño                →    requerimiento + diseño
  Implementación        →    req. + diseño + código
  En servicio           →    req. + diseño + código + re-testeo
                             + el costo del sistema fallando   (carísimo)
```

### 3.2 Los cinco chequeos 🔴

Durante la validación se corren distintos tipos de chequeo sobre los requerimientos del documento:

1. **Validez:** ¿el sistema definido es el que de verdad se necesita? Un usuario puede creer que hace falta un sistema para ciertas funciones — pero más reflexión y análisis pueden identificar funciones **adicionales o distintas**. Y como los sistemas tienen stakeholders diversos con necesidades distintas, todo conjunto de requerimientos es inevitablemente un **compromiso** dentro de esa comunidad.
2. **Consistencia:** los requerimientos **no deben entrar en conflicto** — ni restricciones contradictorias ni descripciones distintas de la misma función.
3. **Completitud:** el documento debe incluir requerimientos que definan **todas** las funciones y restricciones que el usuario del sistema pretende.
4. **Realismo:** con el conocimiento de la **tecnología existente**, chequear que los requerimientos puedan realmente implementarse — considerando también el **presupuesto y el cronograma** del desarrollo.
5. **Verificabilidad:** los requerimientos deben escribirse de modo que sean **verificables**: que puedas escribir un conjunto de **tests** capaces de demostrar que el sistema entregado cumple cada requerimiento especificado. Motivo: **reducir el potencial de disputa** entre cliente y contratista. (¿Te suena? Es exactamente la campaña anti-metas de la Parte 1 §4.2 — "fácil de usar" no se verifica; "dos errores por hora tras cuatro horas de capacitación", sí.)

**Mnemotecnia:** los cinco chequeos preguntan si los requerimientos son **V**álidos, **C**onsistentes, **C**ompletos, **R**ealistas y **V**erificables — "VCCRV": *¿Vale? ¿Coherente? ¿Completo? ¿Realizable? ¿Verificable?*

### 3.3 Las tres técnicas de validación 🔴

Pueden usarse individualmente o en conjunto:

1. **Revisiones de requerimientos:** un equipo de revisores analiza los requerimientos **sistemáticamente**, buscando errores e inconsistencias. En su forma completa: un grupo con gente **del cliente y del desarrollador** lee el documento en detalle chequeando errores, anomalías e inconsistencias; lo detectado se **registra**, y después cliente y desarrollador **negocian** cómo resolver cada problema identificado.
2. **Prototipado:** se demuestra un **modelo ejecutable** del sistema a usuarios finales y clientes, que pueden **experimentar** con él y ver si satisface sus **necesidades reales**. Es la validación más directa: en lugar de imaginar el sistema leyendo, lo tocan.
3. **Generación de casos de prueba:** si los requerimientos deben ser testeables, **diseñar los tests como parte de la validación** suele **revelar problemas**: cuando un test es difícil o imposible de diseñar, usualmente significa que el requerimiento va a ser **difícil de implementar** — y conviene reconsiderarlo. (En XP este principio se lleva al extremo: los tests se desarrollan desde los requerimientos de usuario **antes de escribir código**.)

### 3.4 El límite honesto de la validación

No hay que **subestimar** los problemas de validar requerimientos. En última instancia, es **difícil demostrar** que un conjunto de requerimientos cumple las necesidades de un usuario: la gente tiene que **imaginarse el sistema en operación** y cómo encajaría en su trabajo — un análisis abstracto duro **incluso para profesionales** de computación experimentados, y más duro todavía para los usuarios. Consecuencia realista: **rara vez se encuentran todos los problemas** durante la validación; es **inevitable** que haya más cambios de requerimientos para corregir omisiones y malentendidos **después de acordado** el documento. Lo cual nos deja servida la última sección: si el cambio es inevitable, hay que **gestionarlo**.

### 📝 Para el parcial, si te preguntan

**"¿Qué chequeos se realizan durante la validación de requerimientos?"**
Cinco: validez (que definan el sistema que realmente se necesita, como compromiso entre stakeholders), consistencia (sin requerimientos en conflicto ni descripciones duplicadas contradictorias), completitud (que estén todas las funciones y restricciones pretendidas), realismo (implementables con la tecnología, presupuesto y cronograma disponibles) y verificabilidad (que pueda escribirse un conjunto de tests que demuestre que el sistema entregado cumple cada requerimiento).

**"¿Qué técnicas de validación existen?"**
Revisiones de requerimientos (un equipo con cliente y desarrollador analiza sistemáticamente el documento, registra errores e inconsistencias y negocia su resolución), prototipado (los usuarios experimentan con un modelo ejecutable para comprobar si satisface sus necesidades reales) y generación de casos de prueba (diseñar los tests de cada requerimiento; si un test es difícil o imposible de diseñar, el requerimiento probablemente sea difícil de implementar y deba reconsiderarse).

**"¿Por qué los errores de requerimientos son los más caros?"**
Porque un cambio de requerimientos arrastra cambios en el diseño y la implementación, y obliga a re-testear el sistema; cuanto más tarde se descubre el error, más artefactos construidos sobre él hay que rehacer.

---

## 4. Gestión de requerimientos 🔴

### 4.1 El hecho: los requerimientos SIEMPRE cambian

Los requerimientos de los sistemas de software grandes **cambian siempre**, y la primera razón es estructural: esos sistemas suelen desarrollarse para atacar problemas "**wicked**" *(término nuevo: literalmente "perversos" — problemas tan complejos que no pueden definirse por completo)*. Si el problema no puede definirse del todo, los requerimientos de software están **condenados a ser incompletos**. Y durante el proceso, la **comprensión del problema que tienen los stakeholders cambia constantemente** — los requerimientos deben evolucionar para reflejar esa visión cambiada:

```
   Tiempo ─────────────────────────────────────────────►

   Comprensión INICIAL              Comprensión CAMBIADA
   del problema                     del problema
        │                                │
        ▼                                ▼
   Requerimientos                   Requerimientos
   INICIALES        ──────────►     CAMBIADOS
```

*(Descripción: con el paso del tiempo, la comprensión inicial del problema se transforma en una comprensión distinta; los requerimientos iniciales, derivados de aquella comprensión, deben transformarse en requerimientos cambiados que reflejen la nueva.)*

Y una vez que el sistema **se instaló y se usa regularmente**, emergen requerimientos nuevos **inevitablemente**. A usuarios y clientes les resulta difícil anticipar qué efectos va a tener el sistema nuevo sobre sus procesos de negocio y su forma de trabajar; recién **con la experiencia de uso** descubren necesidades y prioridades nuevas. Tres razones de fondo de esa inevitabilidad 🔴:

1. **El entorno técnico y de negocio cambia después de la instalación:** hardware nuevo, necesidad de interfacear con otros sistemas, prioridades de negocio que mutan (con los consecuentes cambios en el soporte requerido), legislación y regulaciones nuevas que el sistema debe obligatoriamente cumplir.
2. **Los que pagan el sistema y los que lo usan rara vez son las mismas personas.** Los clientes-compradores imponen requerimientos por restricciones organizacionales y presupuestarias, que pueden **entrar en conflicto** con los requerimientos de los usuarios finales — y después de la entrega puede haber que agregar features de soporte al usuario si se quiere que el sistema cumpla sus metas.
3. **Los sistemas grandes tienen una comunidad de usuarios diversa**, con requerimientos y prioridades distintas, incluso conflictivas o contradictorias. Los requerimientos finales son inevitablemente un **compromiso**, y con la experiencia suele descubrirse que el **balance de soporte** dado a los distintos usuarios tiene que cambiar.

🕳️ **Madriguera — Requerimientos perdurables y volátiles**
No todos los requerimientos cambian igual: los **perdurables** se asocian a las actividades núcleo de la organización, lentas de cambiar (el trabajo fundamental en sí); los **volátiles** se asocian a actividades de soporte, que reflejan **cómo** la organización hace su trabajo — y cambian mucho más probablemente.
*Volvé al camino — el par de términos alcanza; sirve para argumentar qué partes del documento van a moverse más.*

### 4.2 Qué es gestionar requerimientos

> **Definición** — La **gestión de requerimientos** es el proceso de **entender y controlar los cambios** a los requerimientos del sistema. Implica **rastrear requerimientos individuales** y **mantener los vínculos entre requerimientos dependientes**, para poder evaluar el **impacto** de un cambio; y establecer un **proceso formal** para hacer propuestas de cambio y vincularlas a los requerimientos.

Dato de timing evaluable: el proceso **formal** de gestión arranca **apenas hay una versión borrador** del documento de requerimientos — pero la **planificación** de cómo gestionar los cambios debe arrancar **antes, durante la elicitación** misma.

### 4.3 Planificación de la gestión 🟡

La planificación es la primera etapa esencial, y establece el **nivel de detalle** de gestión necesario. Hay que decidir sobre cuatro cosas:

1. **Identificación de requerimientos:** cada requerimiento debe tener **identificación única**, para poder referenciarlo cruzado con otros y usarlo en evaluaciones de trazabilidad. (Los "RS-1.1", "RF-3" que venimos usando desde la Parte 1 no eran decoración: son esto.)
2. **Un proceso de gestión de cambios:** el conjunto de actividades que evalúan **impacto y costo** de los cambios (§4.4, ya mismo).
3. **Políticas de trazabilidad** *(término nuevo: trazabilidad = poder rastrear las relaciones de cada requerimiento — con otros requerimientos y con el diseño del sistema — para analizar por qué se propone un cambio y qué impacto en cadena va a tener)*: definen **qué relaciones registrar** entre requerimientos, y entre requerimientos y diseño, y **cómo mantener** esos registros.
4. **Soporte de herramientas:** gestionar requerimientos implica procesar **mucha** información. Las herramientas van desde sistemas especializados de gestión de requerimientos hasta **planillas de cálculo y bases de datos simples**.

Sobre las herramientas, tres necesidades concretas de soporte automatizado:

- **Almacenamiento:** los requerimientos en un repositorio de datos **seguro y gestionado**, accesible a todos los involucrados en el proceso de RE.
- **Gestión de cambios:** el proceso se simplifica con soporte activo de herramienta.
- **Gestión de trazabilidad:** herramientas que permiten **descubrir requerimientos relacionados** (algunas usan procesamiento de lenguaje natural para descubrir relaciones posibles entre requerimientos).

Calibre según tamaño: para sistemas **chicos** puede no hacer falta herramienta especializada — alcanza con procesador de texto, planilla y base de datos de PC; para sistemas **grandes**, se requieren herramientas especializadas.

### 4.4 El proceso de gestión del cambio 🔴

La gestión del cambio se aplica a **todas las propuestas de cambio** posteriores a la **aprobación** del documento de requerimientos. Su porqué económico: hay que decidir si los **beneficios** de implementar el requerimiento nuevo **justifican los costos**. Su ventaja procedimental: con un proceso formal, todas las propuestas se tratan **consistentemente** y los cambios al documento se hacen de forma **controlada**. Tres etapas principales:

```
  Problema             1. ANÁLISIS DEL        2. ANÁLISIS Y          3. IMPLEMENTACIÓN
  identificado    ─►   PROBLEMA Y        ─►   COSTEO           ─►    DEL CAMBIO         ─►  Requerimientos
  (o propuesta         ESPECIFICACIÓN         DEL CAMBIO             (documento y, si        revisados
   de cambio)          DEL CAMBIO             (impacto + costo,      hace falta, diseño
                       (¿es válido?)          ¿se procede?)          e implementación)
```

1. **Análisis del problema y especificación del cambio:** el proceso arranca con un problema identificado en los requerimientos o, a veces, directamente con una propuesta de cambio específica. Se analiza que el problema o la propuesta sea **válido**, y ese análisis **se devuelve a quien solicitó** el cambio — que puede responder con una propuesta más específica, o **retirar** el pedido.
2. **Análisis y costeo del cambio:** se evalúa el **efecto** del cambio usando la **información de trazabilidad** y el conocimiento general de los requerimientos del sistema; se estima el **costo** de hacer el cambio, tanto en modificaciones al documento como — si corresponde — al diseño y la implementación. Con ese análisis, se **decide** si se procede o no con el cambio.
3. **Implementación del cambio:** se modifica el documento de requerimientos y, donde haga falta, el diseño y la implementación. Regla de oro de redacción: organizá el documento para que sea **cambiable sin reescrituras masivas** — igual que en los programas, la cambiabilidad se logra **minimizando referencias externas** y haciendo las secciones **tan modulares como sea posible**, de modo que se puedan cambiar y reemplazar secciones individuales sin afectar el resto.

⚠️ **La tentación del cambio urgente.** Cuando un requerimiento nuevo urge, aparece siempre la tentación de **cambiar el sistema primero** y modificar el documento retroactivamente después. Evitala: **casi inevitablemente** la especificación y la implementación quedan **desalineadas** — una vez hecho el cambio en el sistema, es fácil olvidarse de reflejarlo en el documento, o agregarle información inconsistente con la implementación. **Para el examen:** el orden correcto es proceso de cambio → documento → sistema.

**El contraste ágil (cierre del círculo):** los procesos ágiles como XP se diseñaron justamente para bancarse requerimientos que cambian durante el desarrollo — y ahí un cambio propuesto por el usuario **no pasa por el proceso formal**: el usuario lo **prioriza**, y si es de alta prioridad, **decide qué features planificadas de la próxima iteración se caen** para hacerle lugar. Mismo problema (el cambio inevitable), dos filosofías de control opuestas.

### 📝 Para el parcial, si te preguntan

**"¿Por qué cambian inevitablemente los requerimientos de un sistema grande?"**
Porque atacan problemas que no pueden definirse por completo, así que los requerimientos nacen incompletos y la comprensión del problema evoluciona durante el proceso; y tras la instalación: el entorno técnico y de negocio cambia (hardware, interfaces, prioridades, legislación), quienes pagan el sistema no son quienes lo usan y sus requerimientos entran en conflicto, y la comunidad diversa de usuarios obliga a compromisos cuyo balance la experiencia demuestra que hay que ajustar.

**"¿Qué es la gestión de requerimientos y qué debe planificarse?"**
Es el proceso de entender y controlar los cambios a los requerimientos, manteniendo identificados los requerimientos y los vínculos entre dependientes para evaluar impacto. En la planificación se decide: cómo identificar unívocamente cada requerimiento, el proceso de gestión de cambios, las políticas de trazabilidad (qué relaciones requerimiento-requerimiento y requerimiento-diseño registrar y cómo mantenerlas) y el soporte de herramientas.

**"Describa las etapas del proceso de gestión del cambio."**
Tres etapas sobre toda propuesta posterior a la aprobación del documento: análisis del problema y especificación del cambio (validar el problema o propuesta, con devolución al solicitante, que puede precisar o retirar el pedido); análisis y costeo (evaluar el efecto con la información de trazabilidad y estimar el costo en documento, diseño e implementación, decidiendo si se procede); e implementación (modificar el documento — organizado modularmente para ser cambiable — y donde corresponda el diseño y la implementación).

---

## 5. Síntesis de la unidad — todo el capítulo en diez líneas

1. Los **requerimientos** definen qué debe hacer el sistema (servicios) y bajo qué restricciones opera; la **RE** es descubrirlos, analizarlos, documentarlos y verificarlos.
2. Se escriben en dos niveles para dos públicos: **de usuario** (abstractos, lenguaje natural) y **de sistema** (detallados, base del contrato y del diseño).
3. Los **funcionales** declaran servicios y comportamientos; los **no funcionales** restringen el sistema como un todo (producto / organizacionales / externos) y suelen ser más críticos: escribilos **cuantitativos y verificables**.
4. El **SRS** es la declaración oficial de lo que hay que implementar, con usuarios que van del cliente al mantenedor, y una estructura estándar adaptable.
5. La especificación combina **lenguaje natural disciplinado** (formato estándar + racionalidad), **plantillas estructuradas** y **tablas** para los casos múltiples.
6. El proceso de RE es una **espiral iterativa** — elicitación, especificación, validación — precedida por el **estudio de factibilidad** (tres preguntas, un "no" mata el proyecto).
7. La **elicitación** es un ciclo (descubrir → clasificar → negociar → especificar) plagado de dificultades humanas: conocimiento tácito, conflictos, política, cambio.
8. Las **técnicas se combinan** porque ninguna alcanza: entrevistas (panorama, no dominio ni política), escenarios y casos de uso (interacciones concretas, no NF ni negocio), etnografía (el trabajo real y la cooperación, no features nuevas).
9. La **validación** chequea validez, consistencia, completitud, realismo y verificabilidad — con revisiones, prototipos y generación de tests — porque el error de requerimientos es el más caro de arreglar.
10. Los requerimientos **van a cambiar**: la **gestión** los identifica, los traza y somete cada propuesta a un proceso de tres etapas (validar → costear → implementar), sin ceder a la tentación de cambiar el sistema antes que el documento.

---

## 6. ✅ Checkpoint de la unidad

*Preguntas conceptuales sobre las dos partes. Sin respuestas acá — respondelas por escrito como en un parcial (primera oración que ya responda, terminología de la materia) y después pedime el complemento para corregirte.*

1. Definí ingeniería de requisitos y explicá por qué el término "requerimiento" se usa de forma inconsistente en la industria.
2. Un requerimiento dice: "El acceso a los reportes de costos queda restringido a los usuarios autorizados". ¿Es funcional o no funcional? Justificá — y explicá qué revela este caso sobre la frontera entre ambas categorías.
3. ¿Por qué el incumplimiento de un requerimiento no funcional puede ser más grave que el de uno funcional? Ejemplificá.
4. Transformá esta meta en un requerimiento verificable: "El sistema de turnos debe ser rápido y cómodo para los recepcionistas". Explicá qué cambió y por qué importa.
5. ¿Qué información debe incluir un formulario estándar de especificación de requerimiento funcional? ¿Cuándo conviene complementarlo con una tabla?
6. Detectá al menos tres ambigüedades u omisiones en este requerimiento (inventado): "El sistema debe permitir a los enfermeros buscar pacientes rápidamente y notificar al médico cuando llegue un resultado de laboratorio importante."
7. Dibujá y explicá el modelo en espiral del proceso de RE. ¿Por qué es una espiral y no una secuencia? ¿Qué significa poder "salir" de la espiral en distintos puntos?
8. Enumerá las cinco razones por las que la elicitación es difícil, e indicá cuál de las cuatro técnicas de descubrimiento ataca mejor cada una (y cuál no la resuelve).
9. ¿Qué relación hay entre escenario y caso de uso? Describí los cinco elementos de un escenario completo usando un ejemplo propio (no el de la historia clínica).
10. ¿Qué descubrió la etnografía en el caso de los controladores aéreos que ninguna entrevista hubiera revelado, y qué requerimiento concreto derivó de la conciencia del trabajo ajeno?
11. Nombrá y explicá los cinco chequeos de la validación y las tres técnicas para llevarla a cabo. ¿Por qué aun así "rara vez se encuentran todos los problemas"?
12. Una gerente te pide implementar ya un cambio urgente "y después vemos el papelerío". Explicale, con las tres etapas del proceso de gestión del cambio, por qué ese orden es un problema y qué riesgo concreto corre el proyecto.

---

**FIN — Apunte Maestro U1 · Parte 2 de 2**
