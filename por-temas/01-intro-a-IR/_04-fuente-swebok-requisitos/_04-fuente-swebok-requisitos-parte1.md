# SWEBOK Guide V3.0 — Capítulo 1: Requisitos de Software (Parte 1 de 4)

> Traducción al español, fiel y completa, de `04-SWEBOOK_v3_Chap1.pdf` (18 páginas). Esta parte cubre las páginas 1-1 a 1-5: acrónimos, introducción, descomposición de tópicos, tópico 1 (Fundamentos de los requisitos de software) y tópico 2 (Proceso de requisitos).

**Notas de conversión**

- **Es una traducción, no una transcripción.** El original está en inglés. Se tradujo la sintaxis al español natural, pero no se agregó, quitó, resumió ni reordenó contenido. Donde el original es vago o ambiguo, la traducción queda igual de vaga: no se lo corrigió. Ante cualquier duda, prevalece el PDF original.
- **Capa de texto dañada en el original.** El PDF fue generado con PrimoPDF en 2016 con fuentes de codificación `Identity-H` sin mapa de caracteres, y tiene el copiado deshabilitado. Al extraer el texto, buena parte sale ilegible. Se reconstruyó resolviendo los índices de glifo carácter por carácter y se verificó contra la página rasterizada. La reconstrucción quedó sin residuos.
- **Términos mantenidos en inglés** por ser los de uso corriente en el ámbito hispanohablante: *stakeholder*, *throughput*, *tradeoff*, *benchmarking*. La sigla KA (área de conocimiento) se mantiene porque el documento la usa como referencia interna constante.
- **"Shall"** se tradujo uniformemente como **"deberá"**, siguiendo la convención de las versiones en español de IEEE 830.
- **Nombres de las otras áreas de conocimiento** del SWEBOK (Diseño de Software, Pruebas de Software, etc.) se tradujeron. En el volumen original figuran en inglés.
- **Tabla de acrónimos:** se conserva la expansión en inglés junto a la traducción, porque las siglas se forman a partir del inglés y no tendrían sentido de otro modo.
- **Referencias entre corchetes** del tipo `[1*, c4, c4s1]` se transcriben tal cual: remiten a capítulos y secciones de la bibliografía de referencia del capítulo (Sommerville y Wiegers). Su clave completa está en la parte 4.
- **Figura 1.1** verificada visualmente sobre la página rasterizada a 200 dpi; las 38 etiquetas del diagrama se transcribieron desde la imagen.
- El documento no contiene hipervínculos: se revisaron las anotaciones del PDF y no hay ninguno.
- **En el original, el exponente de la página 1-3** (`1 * 10−8`) se compone con un superíndice. Se transcribe como 1 × 10⁻⁸.

---

# CAPÍTULO 1 — REQUISITOS DE SOFTWARE

## ACRÓNIMOS

| Sigla | Expansión (inglés) | Traducción |
|---|---|---|
| CIA | Confidentiality, Integrity, and Availability | Confidencialidad, integridad y disponibilidad |
| DAG | Directed Acyclic Graph | Grafo dirigido acíclico |
| FSM | Functional Size Measurement | Medición del tamaño funcional |
| INCOSE | International Council on Systems Engineering | Consejo Internacional de Ingeniería de Sistemas |
| UML | Unified Modeling Language | Lenguaje unificado de modelado |
| SysML | Systems Modeling Language | Lenguaje de modelado de sistemas |

## INTRODUCCIÓN

El área de conocimiento (KA) de Requisitos de Software se ocupa de la elicitación, el análisis, la especificación y la validación de los requisitos de software, así como de la gestión de los requisitos durante todo el ciclo de vida del producto de software. Existe amplio reconocimiento, tanto entre investigadores como entre profesionales de la industria, de que los proyectos de software quedan críticamente vulnerables cuando las actividades relacionadas con los requisitos se ejecutan de manera deficiente.

Los requisitos de software expresan las necesidades y restricciones impuestas sobre un producto de software que contribuye a la solución de algún problema del mundo real.

El término "ingeniería de requisitos" se usa ampliamente en el campo para designar el tratamiento sistemático de los requisitos. Por razones de consistencia, en esta KA el término "ingeniería" no se usará salvo para referirse a la ingeniería de software propiamente dicha.

Por la misma razón, tampoco se usará "ingeniero de requisitos", término que aparece en parte de la literatura. En su lugar se usará "ingeniero de software" o, en ciertos casos específicos, "especialista en requisitos"; este último cuando el rol en cuestión suele desempeñarlo alguien que no es un ingeniero de software. Esto no implica, sin embargo, que un ingeniero de software no pueda cumplir esa función.

Un riesgo inherente a la descomposición propuesta es que se infiera de ella un proceso similar al modelo en cascada. Para prevenirlo, el tópico 2, Proceso de requisitos, está diseñado para dar una visión general de alto nivel del proceso de requisitos, exponiendo los recursos y las restricciones bajo los cuales opera y que lo configuran.

Una descomposición alternativa podría usar una estructura basada en productos: requisitos de sistema, requisitos de software, prototipos, casos de uso, etcétera. La descomposición basada en procesos refleja el hecho de que el proceso de requisitos, para tener éxito, debe considerarse como un proceso que involucra actividades complejas y fuertemente acopladas —tanto secuenciales como concurrentes—, y no como una actividad discreta y única que se realiza al comienzo de un proyecto de desarrollo de software.

La KA de Requisitos de Software se relaciona estrechamente con las KA de Diseño de Software, Pruebas de Software, Mantenimiento de Software, Gestión de la Configuración del Software, Gestión de la Ingeniería de Software, Proceso de Ingeniería de Software, Modelos y Métodos de Ingeniería de Software, y Calidad del Software.

## DESCOMPOSICIÓN DE TÓPICOS DE REQUISITOS DE SOFTWARE

La descomposición de tópicos de la KA de Requisitos de Software se muestra en la Figura 1.1.

### Figura 1.1 — Descomposición de tópicos de la KA de Requisitos de Software

```
                                    ┌─────────────────────┐
                                    │      Requisitos     │
                                    │      de Software    │
                                    └──────────┬──────────┘
        ┌──────────────┬──────────────┬────────┴─────┬──────────────┬──────────────┬──────────────┬──────────────┐
        │              │              │              │              │              │              │              │
┌───────┴──────┐┌──────┴──────┐┌──────┴──────┐┌──────┴──────┐┌──────┴──────┐┌──────┴──────┐┌──────┴──────┐┌──────┴──────┐
│ Fundamentos  ││  Proceso de ││ Elicitación ││  Análisis   ││Especificación││ Validación  ││Consideracio-││Herramientas │
│    de los    ││  requisitos ││     de      ││     de      ││     de      ││     de      ││nes prácticas││de requisitos│
│ requisitos   ││             ││ requisitos  ││ requisitos  ││ requisitos  ││ requisitos  ││             ││ de software │
│ de software  ││             ││             ││             ││             ││             ││             ││             │
└───────┬──────┘└──────┬──────┘└──────┬──────┘└──────┬──────┘└──────┬──────┘└──────┬──────┘└──────┬──────┘└─────────────┘
        │              │              │              │              │              │              │
    Definición     Modelos de     Fuentes de     Clasificación   Documento de   Revisiones     Naturaleza
    de requisito    proceso       requisitos     de requisitos   definición     de requisitos  iterativa del
    de software                                                  del sistema                   proceso de
        │              │              │              │              │              │           requisitos
    Requisitos     Actores del    Técnicas de     Modelado      Especificación  Prototipado        │
    de producto     proceso       elicitación    conceptual     de requisitos               Gestión de
    y de proceso                                                 del sistema                  cambios
        │              │                             │              │              │              │
    Requisitos     Soporte y                    Diseño arqui-  Especificación   Validación    Atributos de
    funcionales    gestión del                  tectónico y    de requisitos    de modelos     requisitos
    y no funcio-     proceso                    asignación de   de software
      nales                                      requisitos                          │              │
        │              │                             │                          Pruebas de     Trazabilidad
    Propiedades    Calidad y                    Negociación                     aceptación    de requisitos
    emergentes     mejora del                   de requisitos
                     proceso                                                                        │
        │                                            │                                        Medición de
    Requisitos                                    Análisis                                     requisitos
    cuantificables                                 formal

    Requisitos de
    sistema y de
    software
```

**Descripción del diagrama.** Es un árbol jerárquico de tres niveles. En la raíz está "Requisitos de Software". De ella cuelgan ocho ramas de primer nivel, dibujadas como cajas alineadas horizontalmente, que se corresponden con los ocho tópicos del capítulo, en este orden: Fundamentos de los requisitos de software · Proceso de requisitos · Elicitación de requisitos · Análisis de requisitos · Especificación de requisitos · Validación de requisitos · Consideraciones prácticas · Herramientas de requisitos de software. De cada una de las siete primeras ramas cuelga hacia abajo una lista de subtópicos, unidos por flechas. "Herramientas de requisitos de software" es la única rama sin subtópicos. El reparto de subtópicos es: Fundamentos tiene seis (definición de requisito de software; requisitos de producto y de proceso; requisitos funcionales y no funcionales; propiedades emergentes; requisitos cuantificables; requisitos de sistema y requisitos de software). Proceso de requisitos tiene cuatro (modelos de proceso; actores del proceso; soporte y gestión del proceso; calidad y mejora del proceso). Elicitación tiene dos (fuentes de requisitos; técnicas de elicitación). Análisis tiene cinco (clasificación de requisitos; modelado conceptual; diseño arquitectónico y asignación de requisitos; negociación de requisitos; análisis formal). Especificación tiene tres (documento de definición del sistema; especificación de requisitos del sistema; especificación de requisitos de software). Validación tiene cuatro (revisiones de requisitos; prototipado; validación de modelos; pruebas de aceptación). Consideraciones prácticas tiene cinco (naturaleza iterativa del proceso de requisitos; gestión de cambios; atributos de requisitos; trazabilidad de requisitos; medición de requisitos). El diagrama no indica secuencia temporal: solo pertenencia jerárquica.

---

## 1. Fundamentos de los requisitos de software

`[1*, c4, c4s1, c10s1, c10s4] [2*, c1, c6, c12]`

### 1.1. Definición de un requisito de software

En su forma más básica, un requisito de software es una propiedad que algo debe exhibir para resolver algún problema del mundo real. Puede apuntar a automatizar parte de una tarea para alguien, a dar soporte a los procesos de negocio de una organización, a corregir deficiencias de software existente o a controlar un dispositivo, por nombrar apenas unos pocos de los muchos problemas para los cuales hay soluciones de software posibles. Los modos en que funcionan los usuarios, los procesos de negocio y los dispositivos son típicamente complejos. Por extensión, entonces, los requisitos sobre un software particular son típicamente una combinación compleja proveniente de diversas personas de distintos niveles de una organización, que de un modo u otro están involucradas o conectadas con esa funcionalidad desde el entorno en el que el software operará.

Una propiedad esencial de todos los requisitos de software es que sean verificables: como funcionalidad individual, si se trata de un requisito funcional, o a nivel del sistema, si se trata de un requisito no funcional. Verificar ciertos requisitos de software puede resultar difícil o costoso. Por ejemplo, verificar el requisito de *throughput* de un centro de atención telefónica puede exigir el desarrollo de software de simulación. El personal de requisitos de software, de pruebas y de calidad debe asegurar que los requisitos puedan verificarse dentro de las restricciones de recursos disponibles.

Los requisitos tienen otros atributos además de las propiedades de comportamiento. Ejemplos habituales son una calificación de prioridad, que permite establecer *tradeoffs* frente a recursos finitos, y un valor de estado, que permite monitorear el avance del proyecto. Típicamente, los requisitos de software se identifican de manera unívoca, de modo que puedan someterse a la gestión de la configuración del software durante todo el ciclo de vida de la funcionalidad y del software.

### 1.2. Requisitos de producto y requisitos de proceso

Un requisito de producto es una necesidad o restricción sobre el software que se va a desarrollar. Por ejemplo: "El software deberá verificar que un estudiante cumpla con todas las correlativas antes de que se inscriba a una materia".

Un requisito de proceso es, en esencia, una restricción sobre el desarrollo del software. Por ejemplo: "El software deberá desarrollarse usando un proceso RUP".

Algunos requisitos de software generan requisitos de proceso implícitos. La elección de la técnica de verificación es un ejemplo. Otro podría ser el uso de técnicas de análisis particularmente rigurosas —como los métodos formales de especificación— para reducir defectos que puedan derivar en una confiabilidad inadecuada. Los requisitos de proceso también pueden ser impuestos directamente por la organización que desarrolla, por su cliente, o por un tercero como un organismo regulador de seguridad.

### 1.3. Requisitos funcionales y no funcionales

Los requisitos **funcionales** describen las funciones que el software debe ejecutar; por ejemplo, dar formato a un texto o modular una señal. A veces se los conoce como capacidades o *features*. Un requisito funcional también puede describirse como aquel para el cual se puede escribir un conjunto finito de pasos de prueba que validen su comportamiento.

Los requisitos **no funcionales** son los que actúan restringiendo la solución. A veces se los conoce como restricciones o requisitos de calidad. Pueden clasificarse aún más según sean requisitos de rendimiento, de mantenibilidad, de seguridad física, de confiabilidad, de seguridad informática, de interoperabilidad, o alguno de los muchos otros tipos de requisitos de software (ver Modelos y características de calidad, en la KA de Calidad del Software).

### 1.4. Propiedades emergentes

Algunos requisitos representan propiedades emergentes del software: es decir, requisitos que no pueden ser satisfechos por un único componente, sino que dependen de cómo interoperan todos los componentes del software. El requisito de *throughput* de un centro de atención telefónica, por ejemplo, dependería de cómo interactúan el sistema telefónico, el sistema de información y los operadores bajo condiciones reales de operación. Las propiedades emergentes dependen de manera crucial de la arquitectura del sistema.

### 1.5. Requisitos cuantificables

Los requisitos de software deberían enunciarse de la manera más clara y menos ambigua posible y, cuando corresponda, cuantitativamente. Es importante evitar requisitos vagos y no verificables, cuya interpretación dependa del juicio subjetivo ("el software deberá ser confiable"; "el software deberá ser amigable para el usuario"). Esto es particularmente importante para los requisitos no funcionales. Dos ejemplos de requisitos cuantificados son los siguientes: el software de un centro de atención telefónica debe incrementar el *throughput* del centro en un 20 %; y un sistema deberá tener una probabilidad de generar un error fatal, durante cualquier hora de operación, menor a 1 × 10⁻⁸. El requisito de *throughput* está formulado a un nivel muy alto y habrá que usarlo para derivar una cantidad de requisitos detallados. El requisito de confiabilidad restringirá fuertemente la arquitectura del sistema.

### 1.6. Requisitos de sistema y requisitos de software

En este tópico, "sistema" significa

> una combinación de elementos que interactúan para cumplir un objetivo definido. Estos incluyen hardware, software, firmware, personas, información, técnicas, instalaciones, servicios y otros elementos de soporte,

según la definición del Consejo Internacional de Ingeniería de Software y de Sistemas (INCOSE) [3].

Los requisitos **de sistema** son los requisitos del sistema tomado como un todo. En un sistema que contiene componentes de software, los requisitos **de software** se derivan de los requisitos de sistema.

Esta KA define los "requisitos de usuario" de manera restringida, como los requisitos de los clientes o usuarios finales del sistema. Los requisitos de sistema, en cambio, abarcan los requisitos de usuario, los requisitos de otros stakeholders (como las autoridades regulatorias) y los requisitos sin una fuente humana identificable.

---

## 2. Proceso de requisitos

`[1*, c4s4] [2*, c1–4, c6, c22, c23]`

Esta sección introduce el proceso de requisitos de software, orientando los cinco tópicos restantes y mostrando cómo el proceso de requisitos encastra con el proceso general de ingeniería de software.

### 2.1. Modelos de proceso

El objetivo de este tópico es transmitir la comprensión de que el proceso de requisitos

- no es una actividad discreta de arranque dentro del ciclo de vida del software, sino un proceso que se inicia al comienzo de un proyecto y se sigue refinando a lo largo de todo el ciclo de vida;
- identifica a los requisitos de software como ítems de configuración y los gestiona con las mismas prácticas de gestión de la configuración del software que se aplican a los demás productos de los procesos del ciclo de vida del software;
- debe adaptarse a la organización y al contexto del proyecto.

En particular, el tópico se ocupa de cómo se configuran las actividades de elicitación, análisis, especificación y validación para distintos tipos de proyectos y restricciones. El tópico incluye también las actividades que aportan insumos al proceso de requisitos, como los estudios de marketing y de factibilidad.

### 2.2. Actores del proceso

Este tópico introduce los roles de las personas que participan en el proceso de requisitos. Este proceso es fundamentalmente interdisciplinario, y el especialista en requisitos necesita mediar entre el dominio del stakeholder y el de la ingeniería de software. A menudo hay muchas personas involucradas además del especialista en requisitos, cada una de las cuales tiene un interés en el software. Los stakeholders varían según el proyecto, pero siempre incluirán a usuarios/operadores y a clientes (que no tienen por qué ser los mismos).

Ejemplos típicos de stakeholders del software incluyen, sin limitarse a ellos, los siguientes:

- **Usuarios.** Este grupo comprende a quienes operarán el software. Suele ser un grupo heterogéneo, con personas de distintos roles y requisitos.
- **Clientes.** Este grupo comprende a quienes encargaron el software o a quienes representan el mercado objetivo del software.
- **Analistas de mercado.** Un producto de mercado masivo no tendrá un cliente que lo encargue, de modo que a menudo hacen falta personas de marketing para establecer qué necesita el mercado y actuar como clientes sustitutos.
- **Reguladores.** Muchos dominios de aplicación, como la banca y el transporte público, están regulados. El software de esos dominios debe cumplir con los requisitos de las autoridades regulatorias.
- **Ingenieros de software.** Estas personas tienen un interés legítimo en obtener beneficio del desarrollo del software: por ejemplo, reutilizando componentes en otros productos o tomándolos de ellos. Si, en ese escenario, el cliente de un producto en particular tiene requisitos específicos que comprometen el potencial de reutilización de componentes, los ingenieros de software deben sopesar cuidadosamente su propio interés frente al del cliente. Los requisitos específicos, y particularmente las restricciones, pueden tener un impacto mayor sobre el costo o los plazos del proyecto, porque encajan bien o mal con el conjunto de habilidades de los ingenieros. Los *tradeoffs* importantes entre esos requisitos deberían identificarse.

No será posible satisfacer perfectamente los requisitos de cada stakeholder, y es tarea del ingeniero de software negociar *tradeoffs* que resulten aceptables para los stakeholders principales y que se mantengan dentro de las restricciones presupuestarias, técnicas, regulatorias y de otro tipo. Un prerrequisito para esto es que todos los stakeholders estén identificados, que se analice la naturaleza de su "interés" y que se eliciten sus requisitos.

### 2.3. Soporte y gestión del proceso

Esta sección introduce los recursos de gestión de proyectos que el proceso de requisitos requiere y consume. Establece el contexto para el primer tópico (Iniciación y definición del alcance) de la KA de Gestión de la Ingeniería de Software. Su propósito principal es vincular las actividades del proceso identificadas en 2.1 con las cuestiones de costo, recursos humanos, capacitación y herramientas.

### 2.4. Calidad y mejora del proceso

Este tópico se ocupa de la evaluación de la calidad y de la mejora del proceso de requisitos. Su propósito es enfatizar el rol clave que juega el proceso de requisitos en términos del costo y de los plazos de un producto de software, y de la satisfacción del cliente con él. Ayudará a orientar el proceso de requisitos con respecto a los estándares de calidad y a los modelos de mejora de procesos para software y sistemas. La calidad y mejora del proceso se relaciona estrechamente tanto con la KA de Calidad del Software como con la de Proceso de Ingeniería de Software, y comprende

- en qué medida los estándares y modelos de mejora de procesos cubren el proceso de requisitos;
- las mediciones y el *benchmarking* del proceso de requisitos;
- la planificación e implementación de la mejora;
- la planificación e implementación de la mejora de seguridad/CIA.

---

*Continúa en la Parte 2: tópico 3 (Elicitación de requisitos) y tópico 4 (Análisis de requisitos).*

**FIN DEL ARCHIVO FUENTE — SWEBOK Guide V3.0, Capítulo 1: Requisitos de Software (Parte 1 de 4)**
