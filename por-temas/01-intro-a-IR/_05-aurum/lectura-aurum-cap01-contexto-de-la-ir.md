# Lectura en español — Contexto de la Ingeniería de Requisitos

> **Qué es este archivo.** El contenido del capítulo 1 de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005), reescrito completo en español. La cobertura es fiel: están todas las secciones, todos los conceptos y todos los datos del original, en el mismo orden. La redacción es propia — el objetivo es que se lea, no que calque la sintaxis del inglés académico.
>
> **Qué NO es.** No es un apunte de la cursada ni refleja lo que dicta la cátedra. Es material de la bibliografía, leído por tu cuenta. Donde el libro y la materia usan vocabulario distinto o se contradicen, hay una nota ⚠️ marcada. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Las marcas** 🔴🟡🟢 indican relevancia para *tu* materia (🔴 se cruza directo con el cronograma · 🟡 contexto útil · 🟢 propio del ámbito de investigación, leelo si te interesa). No son señales de la cátedra.

---

## Sobre el capítulo

El capítulo 1 es la puerta de entrada del libro y tiene dos trabajos: dar un panorama breve de la ingeniería de requisitos, y fijar un vocabulario común que los otros diecinueve capítulos van a dar por sabido.

Los autores son también los editores del libro. Aybüke Aurum es investigadora de la Universidad de Nueva Gales del Sur, en Australia, donde fundó un grupo de investigación dedicado a requisitos. Claes Wohlin es profesor de ingeniería de software en el Instituto Tecnológico de Blekinge, en Suecia. El libro completo es una compilación: cada capítulo lo escribe un equipo distinto, y este primero existe para que los demás se apoyen sobre una base común.

Un aviso de tono que vale para todo el archivo: este es un libro dirigido a investigadores y a profesionales con experiencia. Cuando dice algo como "no hay consenso en la comunidad", no está siendo evasivo — está describiendo un estado real de la disciplina, que es joven y todavía discute sus propios fundamentos. Vas a encontrar bastante de eso.

---

## 1. Por qué esto importa 🔴

La ingeniería de requisitos —de acá en más, **IR**— se considera una de las etapas más críticas del diseño y desarrollo de software, porque ataca el problema de fondo: construir *el software correcto* para el cliente. No el software bien construido; el correcto. Son cosas distintas y se pueden fallar por separado.

La justificación de por qué importa tanto es, en este capítulo, casi enteramente empírica. Los autores acumulan estudios:

**El informe Standish de 1995.** De los proyectos que clasificó como "en problemas", el 52,7 % terminó costando el 189 % de su presupuesto original, y solo el 42 % de las funcionalidades originalmente previstas llegó a implementarse. Mirando el universo completo de proyectos de software en Estados Unidos, apenas el 16,1 % se desarrolló en fecha, en presupuesto y con todas las funcionalidades planeadas. El 31,1 % se canceló antes de terminar. El proyecto promedio se entregó a aproximadamente el triple del presupuesto y el triple del plazo.

**Una encuesta a 350 organizaciones estadounidenses**, cubriendo más de 8.000 proyectos: un tercio nunca se completó y la mitad tuvo éxito solo parcial. Cerca de la mitad de los gerentes entrevistados identificó los requisitos deficientes como fuente principal de problemas, junto con la baja participación de los usuarios y los objetivos poco claros.

**Una encuesta europea** sobre 3.800 organizaciones de más de 17 países ubicó la mayor concentración de problemas en dos áreas: la especificación de requisitos (50 %) y la gestión de requisitos (50 %).

**Standish otra vez, 1999:** tres de las diez razones principales de fracaso o dificultad de proyectos eran falta de involucramiento del usuario, requisitos inestables y mala gestión de proyecto. En el informe de 2001 el involucramiento del usuario ya había dejado de ser preocupación central, pero los requisitos inestables y la mala gestión seguían entre las causas primarias.

**Doce empresas del Reino Unido:** los problemas de requisitos explicaron el 48 % de todos los problemas de software registrados.

**Un caso puntual, del ámbito de la salud:** los investigadores Tveito y Hasvold observaron un abismo entre la operación cotidiana de un hospital y el conocimiento que los desarrolladores tenían de ese dominio, pese a que las organizaciones de salud vuelcan cada año enormes cantidades de dinero y recursos en sistemas de información. Su lectura del problema es que la brecha nace de una elicitación insuficiente y de malinterpretar requisitos por falta de conocimiento del dominio.

### El dato que más se cita de todos 🔴

Un estudio de Boehm y Papaccio midió cuánto cuesta encontrar y arreglar un mismo error según en qué momento del ciclo de vida se lo detecte:

```
Etapa donde se detecta el error        Costo relativo
────────────────────────────────────   ──────────────
Definición de requisitos               US$   1
Diseño                                 US$   5
Codificación                           US$  10
Pruebas unitarias                      US$  20
Después de entregado el sistema        US$ 200
```

Doscientas veces más caro arreglarlo después de la entrega que al momento de definirlo. El estudio tiene más de quince años al momento en que se escribió el libro, y los autores aclaran explícitamente que la *proporción* se mantiene aunque los montos absolutos hayan cambiado.

> 💡 Este es el argumento central de la materia entera, comprimido en cinco números. Si alguna vez tenés que justificar en un parcial o en una entrevista laboral por qué la IR merece tiempo y plata, esta escalera es la respuesta.

### Qué hace la IR, en una definición

Los autores la caracterizan así: la ingeniería de requisitos se ocupa de **identificar las metas** de un sistema propuesto, **convertir esas metas en servicios y restricciones**, y **asignar la responsabilidad** de cada requisito resultante a algún agente — que puede ser una persona, un dispositivo o el propio software.

Y agregan un cambio de posición importante: la IR **dejó de ser la primera fase** del ciclo de vida del desarrollo para pasar a ser, en muchas organizaciones, una actividad clave que **atraviesa el ciclo de vida completo**. La razón es de mercado: los productos nuevos y las nuevas versiones salen a un ritmo cada vez más rápido, y no hay lugar para congelar los requisitos al principio y no volver a mirarlos.

### Lo que todavía no está resuelto 🟡

Hay acuerdo entre los investigadores en que el proceso de IR debería consistir en actividades estructuradas y repetibles, manejando correctamente tanto los aspectos de ingeniería como los de gestión.

No hay acuerdo, en cambio, sobre **qué modelo de proceso usar**. La oferta disponible va desde modelos basados en actividades hasta paradigmas orientados a la toma de decisiones, cada uno con su propia estructura interna, y ninguno se impuso como estándar de la industria.

---

## 2. Fundamentos 🔴

### 2.1 ¿Qué es un requisito? 🔴

Todo proyecto arranca con un enunciado de requisitos. Los requisitos son **descripciones de cómo debe comportarse un producto de software**. Un requisito típicamente refiere a algún aspecto de un producto o servicio nuevo o mejorado.

La definición más citada es la del estándar **IEEE 610.12-1990** (el glosario estándar de terminología de ingeniería de software). Tiene tres partes, y define un requisito como:

1. Una **condición o capacidad que un usuario necesita** para resolver un problema o alcanzar un objetivo.
2. Una **condición o capacidad que un sistema o componente debe cumplir o poseer** para satisfacer un contrato, un estándar, una especificación u otro documento formalmente impuesto.
3. La **representación documentada** de una condición o capacidad de los tipos (1) o (2).

Vale la pena detenerse en la estructura de esa definición, porque es más astuta de lo que parece a primera vista. El punto (1) mira desde el usuario: lo que alguien necesita. El punto (2) mira desde la obligación externa: lo que el sistema está forzado a cumplir aunque nadie lo haya pedido. Y el punto (3) separa la *cosa* del *papel*: un requisito existe como condición y además existe como documento, y no son lo mismo.

De ahí se desprende una consecuencia que el capítulo remarca: **los requisitos no salen solamente de los usuarios**. Salen también de estándares organizacionales, de normativa gubernamental y de estándares de la industria. Un requisito es un conjunto de necesidades provenientes del usuario y de varios otros interesados —la organización en general, la comunidad, organismos estatales, estándares sectoriales— y todas deben satisfacerse.

> ⚠️ **Cruce con la cátedra.** El punto (2) es la razón por la que las normativas ISO y la regulación de organismos como ARCA aparecen en clase como fuente de requisitos y no como decoración. Un requisito que nace de una norma legal es un requisito de pleno derecho, aunque ningún usuario lo haya pedido nunca.

#### El "qué" y el "cómo" 🔴

Idealmente los requisitos son **independientes del diseño**: describen *qué* debe hacer el sistema, no *cómo* debe hacerlo.

El capítulo agrega inmediatamente la salvedad honesta: **en la práctica esto no siempre es posible**. Y da la razón, que es más incómoda de lo que parece — el significado de "qué" y de "cómo" **cambia de persona a persona**. Lo que para un analista es un "qué" limpio, para un arquitecto ya es una decisión de diseño encubierta. No hay una línea objetiva; hay un acuerdo que se negocia.

### 2.2 Cómo se clasifican los requisitos 🔴

Los requisitos se pueden clasificar de muchas maneras. Estas son las clasificaciones que el capítulo enumera:

**Por naturaleza:**

| Tipo | Qué captura |
|---|---|
| **Funcionales** | Qué va a hacer el sistema |
| **No funcionales** | Restricciones sobre los *tipos de solución* que pueden satisfacer a los funcionales. Ejemplos: exactitud, rendimiento, seguridad, modificabilidad |

**Por nivel de abstracción:**

| Tipo | Qué captura |
|---|---|
| **De nivel de meta** (*goal level*) | Ligados a los objetivos de negocio |
| **De nivel de dominio** | Ligados al área del problema |
| **De nivel de producto** | Ligados al producto |
| **De nivel de diseño** | Qué construir |

**Por origen:**

| Tipo | Qué captura |
|---|---|
| **Primarios** | Elicitados directamente de los interesados |
| **Derivados** | Deducidos a partir de los primarios |

**Otras clasificaciones que menciona:**

- Requisitos de **negocio** frente a requisitos **técnicos**.
- Requisitos de **producto** frente a requisitos de **proceso** — es decir, las necesidades del negocio por un lado, y cómo las personas van a interactuar con el sistema por el otro.
- Requisitos **basados en rol**: de cliente, de usuario, de IT, de sistema, de seguridad.

#### La advertencia que viene con la tabla 🔴

La literatura traza distinciones nítidas entre tipos de requisitos. **En la práctica no es tan fácil**, y el capítulo lo dice con un ejemplo concreto que conviene tener a mano:

Un requisito de usuario relacionado con **seguridad** se clasificaría, a primera vista, como **no funcional**. Pero durante la implementación empiezan a desprenderse de él otros requisitos que son inequívocamente **funcionales** — por ejemplo, la autorización de usuarios. La seguridad como cualidad es no funcional; el mecanismo concreto de autorización que la materializa es funcional.

> ⚠️ **Cruce con la cátedra.** Esto se cruza de lleno con lo que vas a trabajar en las clases 01, 06 y 07. El libro te está diciendo que la frontera RF / RNF es difusa en casos reales, no un checkbox. Ojo con el uso que le des: la cátedra evalúa la clasificación con criterio propio y espera fundamentación. Que la frontera sea difusa **no es excusa para no clasificar** — es la razón por la que hay que justificar la clasificación elegida.

### 2.3 El proceso de ingeniería de requisitos 🔴

La IR abarca **todas las actividades del ciclo de vida relacionadas con requisitos**: principalmente reunirlos, documentarlos y gestionarlos.

Las actividades comunes de la IR, según el capítulo, son:

1. **Elicitación** — obtener los requisitos de sus fuentes.
2. **Interpretación y estructuración** — que engloba análisis y documentación.
3. **Negociación**.
4. **Verificación y validación**.
5. **Gestión de cambios**.
6. **Trazabilidad de requisitos**.

> 🕳️ **Elicitación.** El término viene del inglés *elicit*, "sacar a la luz", y no significa simplemente "recolectar". Se usa deliberadamente en vez de "relevar" o "capturar" porque los requisitos muchas veces **no existen formulados** en la cabeza de nadie antes de la conversación: hay que hacerlos emerger. El capítulo 2 del libro está enteramente dedicado a esto, y es la Parte 2 de esta serie de lecturas.

#### Los modelos de proceso 🟡

El proceso se representa de formas distintas según el autor: lineal, incremental, no lineal, y en espiral. El capítulo repasa las posiciones:

- **Kotonya y Sommerville** proponen un modelo lineal conceptual que sí indica iteraciones entre actividades. Además ofrecen una segunda versión con las mismas actividades dispuestas en espiral: las actividades del modelo lineal se repiten en iteraciones, y al final de cada vuelta se decide si se acepta el documento de requisitos o se hace otra iteración.
- **Macaulay** propone un modelo puramente lineal, sin solapamiento ni iteración.
- **Loucopoulos y Karakostas** representan el proceso como iterativo y cíclico.
- **El modelo en espiral de Boehm** describe una secuencia de actividades ejecutadas en iteraciones, con progreso gradual. Aplicado a requisitos, implica que hay que manejar requisitos en cada vuelta.

#### Qué pasa cuando se va a mirar la realidad 🟡

Acá el capítulo se pone interesante, porque los estudios de campo no confirman los modelos:

- **Martin y otros** examinaron el proceso caso por caso. Encontraron que los proyectos en general seguían un modelo lineal con algo de iteración: lineal hasta la fase de prototipado, y de ahí en adelante iterativo. Su conclusión sobre los modelos: el de Loucopoulos y Karakostas representa bien el carácter *ad hoc* y la naturaleza iterativa del prototipado, pero no muestra la progresión de fases.
- **Nguyen y Swatman** encontraron algo bastante más desordenado: en su caso de estudio el proceso **no ocurría de manera sistemática, suave ni incremental**. Era oportunista, con episodios esporádicos de simplificación y reestructuración del modelo de requisitos cada vez que este alcanzaba un punto de alta complejidad.
- **Houdek y Pohl** directamente **no pudieron producir un modelo monolítico** del proceso. Las actividades estaban demasiado entrelazadas, y los propios participantes del estudio no las percibían como tareas separadas.

#### Y sobre si las organizaciones usan un proceso estándar, tampoco hay acuerdo 🟢

Los estudios se contradicen entre sí, lo que para los autores indica que el área todavía no maduró:

- **Kotonya y Sommerville** sostienen que no son muchas las organizaciones que tienen una definición de proceso de IR estándar.
- **Hofmann y Lehner** examinaron quince equipos de IR en la industria: la mayoría veía la IR como *ad hoc*, y solo algunos proyectos usaban un proceso explícitamente definido o adaptaban un estándar de toda la empresa.
- Los estudios sobre proyectos de desarrollo web confirmaron ese carácter *ad hoc*.
- **En contra de todo lo anterior**, El Emam y Madhavji concluyeron que las organizaciones sí tienden a usar procesos estándar, porque los ven como buenas prácticas.
- **Chatzoglou** encuestó 64 proyectos en tres tandas, con foco en los recursos humanos. Sus conclusiones: debería usarse una metodología de proceso estándar, pero **adaptada a las necesidades específicas de cada proyecto**; y deberían volcarse recursos en la **iteración inicial** del proceso de IR.

---

## 3. El rol de los interesados 🔴

En esencia, dice el capítulo, la IR apunta a **transformar metas de los interesados que son potencialmente incompletas, inconsistentes y contradictorias entre sí, en un conjunto completo de requisitos de alta calidad**.

Vale la pena leer esa frase despacio, porque define el trabajo entero. El insumo es un desastre y el producto tiene que ser coherente. Ese es el oficio.

### La definición de interesado 🔴

Los investigadores de sistemas de información —el capítulo cita a Pouloudi y Whitley— definen a los **interesados** (*stakeholders*) como los participantes del proceso de desarrollo, más cualquier individuo, grupo u organización **cuyas acciones puedan influir, o ser influidas por**, el desarrollo y el uso del sistema, ya sea directa o indirectamente.

Los dos ejes de esa definición son los que hacen el trabajo:

```
                    INFLUYE sobre el sistema
                              ↑
                              │
   indirectamente  ←──────────┼──────────→  directamente
                              │
                              ↓
                    ES INFLUIDO por el sistema
```

Cualquiera que caiga en cualquiera de los cuatro cuadrantes es un interesado. No hace falta que use el sistema. No hace falta que lo pague. Alcanza con que lo afecte o lo afecten.

**Interesados típicos:** jefes de producto, distintos tipos de usuarios y administradores del lado del cliente, y miembros del equipo de software del lado del desarrollo.

### Dónde esa visión se queda corta 🟡

El capítulo señala que esa lista típica es **limitada**, porque está pensada para un solo modo de desarrollo. Distingue dos:

| Modo | Situación |
|---|---|
| **A medida** (*bespoke*) | El software se desarrolla pensando en **un cliente específico**, y muchas veces es posible tener contacto directo con ese único usuario o cliente. Es la visión tradicional de la IR |
| **Dirigido por el mercado** (*market-driven*) | El software se desarrolla para un mercado o para un conjunto de clientes, y **muchas veces no todos los clientes se conocen** al momento de desarrollar |

La segunda situación cambia el problema de raíz: identificar y manejar interesados cuando no sabés todavía quiénes son es un desafío distinto. De ahí nació toda una línea de estudios sobre desarrollo dirigido por el mercado.

> ⚠️ **Cruce con la cátedra.** Los sistemas que asigna la cátedra para analizar en equipo suelen ser productos masivos con millones de usuarios anónimos. Eso los ubica del lado *market-driven*, donde no hay un cliente al que entrevistar. Es una tensión que vale tener consciente: se practican técnicas pensadas para el modo a medida sobre casos que son de mercado.

### Dos problemas que el capítulo destaca 🔴

**El software es invisible.** Puede ser muy difícil representar los requisitos esenciales de un software de una forma que resulte accesible a *todos* los interesados, porque el software no tiene forma física que mostrar. A esto se suma que, a medida que los proyectos se vuelven más complejos, los desarrolladores enfrentan el desafío de identificar las metas de interesados que vienen de trasfondos muy diversos.

La importancia de involucrar a los interesados está ampliamente aceptada, y la razón es directa: **la identificación precisa de sus necesidades determina en gran medida la calidad del producto final**.

**Las inconsistencias.** Uno de los problemas mayores de la IR es la gestión de los distintos tipos de inconsistencia que resultan de las actividades de elicitación, modelado, especificación y priorización. Se vuelven especialmente visibles cuando hay múltiples interesados y múltiples puntos de vista, porque cada interesado tiene su forma de expresarse, sus opiniones y sus prioridades.

Y acá aparece una posición que puede sorprender: **algunos investigadores sostienen que ciertas inconsistencias entre modelos de requisitos son deseables**, porque habilitan más elicitación — la contradicción es una señal de que hay algo que todavía no se entendió, y sirve de disparador para seguir indagando. Esos autores recomiendan **tolerar algunas inconsistencias internas durante el modelado**.

Dicho eso, el capítulo cierra con la posición de sus autores: el éxito de los proyectos de IR depende del análisis preciso de esas perspectivas para detectar incompletitud e inconsistencia. Por eso los requisitos **deben negociarse y validarse antes de documentarse** y antes de que los desarrolladores se comprometan a implementarlos.

---

## 4. Los tres niveles de requisitos 🟡

Esta sección es la contribución más propia de los editores, y es la que explica el título del libro: *engineering* **y** *managing*.

### De dónde sale la idea

El punto de partida es un modelo clásico de la teoría de la administración: el de **Anthony (1965)**, que distingue tres tipos de decisión gerencial — **estratégica**, **táctica** y **operativa**. En trabajo previo, Aurum y Wohlin aplicaron ese marco a la IR, y en este libro adoptan la misma óptica: la gestión de requisitos de software está sujeta a actividades orientadas a la organización, al producto y al proceso, y esas actividades hay que manejarlas en los tres niveles decisorios.

Cruzando ambos ejes sale una matriz de 3 × 3.

### La matriz completa

|  | **Gestión estratégica** | **Gestión táctica** | **Gestión operativa** |
|---|---|---|---|
| **Nivel organizacional** | Estrategia de negocio · Competitividad · Tecnología · Marketing · Valor económico del producto | Beneficios planificados del producto | Balance entre el empuje de la tecnología (*technology-push*) y el tirón del mercado (*market-pull*) |
| **Nivel de producto** | Requisitos de empaquetado para una versión específica · Arquitecturas de producto | Gestión de recursos · Implementación de una versión específica | Gestión de cambios · Volatilidad de requisitos, por ejemplo si un requisito está sujeto a cambio sintáctico o semántico |
| **Nivel de proyecto** | Planificación del proyecto · Estudio de factibilidad · Incorporación de personal | Gestión del proyecto · Control de calidad | Validación en términos de qué requisitos van a la próxima versión |

> 🕳️ ***Technology-push* y *market-pull*.** Dos maneras opuestas de que nazca un producto. En el empuje tecnológico, la organización tiene una capacidad técnica y busca dónde aplicarla. En el tirón del mercado, el mercado pide algo y la organización sale a construirlo. El trade-off operativo es cuánto de cada uno.

### Los tres niveles, uno por uno 🟡

**a) Requisitos a nivel organizacional.** La alta gerencia tiene objetivos estratégicos y metas de largo plazo — cuota de mercado, por ejemplo. Esas metas y estrategias inevitablemente influyen sobre **qué productos debería desarrollar** la organización. Por eso los requisitos que se plantean sobre un producto tienen que evaluarse **primero a nivel organizacional**, para garantizar que estén alineados con las metas y estrategias de la organización. Uno de los desafíos principales acá es determinar cómo el producto final va a sostener los objetivos de negocio.

**b) Requisitos a nivel de producto.** Los requisitos de los productos de software deben alinearse con las metas de negocio de la organización que desarrolla. Una de las preguntas cruciales es **cómo balancear las preocupaciones de los clientes con las de los desarrolladores**. Las técnicas de modelado de metas sirven de mecanismo para vincular los requisitos con objetivos estratégicos anclados en el modelo de negocio general. En este nivel los requisitos son típicamente tanto funcionales como no funcionales. La gestión de producto tiene que asegurar el alineamiento — lo que en la práctica suele significar **seleccionar los requisitos mejor alineados** con las metas generales.

**c) Requisitos a nivel de proyecto.** Los requisitos del nivel de producto tienen que **empaquetarse en partes** que van a proyectos o versiones específicas del software. Acá es importante que se **prioricen y seleccionen** según cuánto cumplen tanto las metas de producto como las organizacionales. Un requisito puede elegirse para implementación porque satisface la necesidad de un cliente específico e importante, o porque potencialmente abre un segmento de mercado nuevo. Estos requisitos definen las condiciones bajo las cuales corre el proyecto: planificación, gestión de riesgos, presupuesto y costo.

### Por qué los autores insisten con esto 🟢

El argumento de fondo: el crecimiento de la importancia estratégica de la tecnología implica que las herramientas, técnicas y procesos **necesitan integrarse con los requisitos del sistema** para quedar alineados con los objetivos de negocio de las organizaciones a las que sirven.

El capítulo señala también una crítica —de Edwards y otros— a los enfoques de diseño contemporáneos: mezclan las cuestiones de negocio con las de implementación tecnológica, formando sistemas monolíticos **que no responden mejor al cambio que sus predecesores**.

Y remata: el cambio del negocio es parte del desarrollo de sistemas. A medida que los sistemas se integran más y suman usuarios de trasfondos más diversos, los desarrolladores quedan presionados a entender las implicancias de sus decisiones en términos de costo-beneficio, especialmente en las actividades tempranas del ciclo de vida.

---

## 5. Gestión de requisitos 🔴

Premisa de arranque: **la calidad de un producto de software está determinada en gran medida por la calidad del proceso de desarrollo que se usó para crearlo.**

El capítulo distingue dos formas distintas de fracasar:

- Proyectos que fallan por **errores en la elucidación** de los requisitos — es decir, se entendió mal desde el principio.
- Proyectos que fallan porque los requisitos **quedaron obsoletos** para cuando el proyecto se entregó. Se entendió bien, pero para cuando llegó ya no servía.

Y un desafío específico que menciona aparte, porque es especialmente difícil: determinar **cuáles cambios de requisitos van a causar un problema mayor** en el proyecto o en el producto. No todo cambio es igual de peligroso, y saber cuál lo es antes de que muerda es un problema abierto.

Gestionar requisitos implica, en el fondo, **establecer un entendimiento compartido** entre los interesados y los requisitos que especificaron para el producto.

### Las cinco prácticas esenciales 🔴

**1. Elicitación, especificación y modelado.**
Entender las necesidades de los interesados, elicitar los requisitos, modelarlos y recolectarlos en un repositorio. Es una etapa importante del desarrollo, y el capítulo agrega la razón por la que casi siempre sale imperfecta: por motivos **cognitivos, comunicativos y motivacionales**, los requisitos tienden a resultar incompletos e inconsistentes. Siempre hay margen de mejora en estas actividades.

> Esos tres adjetivos merecen desarmarse, porque son un buen diagnóstico. *Cognitivo*: la gente no tiene acceso completo a su propio conocimiento — sabe hacer su trabajo pero no sabe explicarlo. *Comunicativo*: aun sabiéndolo, transmitirlo a alguien de otro dominio introduce pérdida. *Motivacional*: a veces el interesado tiene razones para no decir todo lo que sabe.

**2. Priorización.**
No siempre es fácil para los desarrolladores decidir qué requisitos son importantes para los clientes. Esta actividad ayuda a los jefes de proyecto a resolver conflictos —con clientes y desarrolladores colaborando en la priorización—, a planificar entregas escalonadas y a tomar las decisiones de compromiso necesarias.

**3. Dependencias entre requisitos y análisis de impacto.**
Hay que asumir que **los requisitos cambian** y que eso puede impactar significativamente el proyecto. El capítulo declara varios asuntos todavía sin resolver: cómo registrar las decisiones tomadas, cómo entender el efecto de los cambios del negocio, y cómo aprovechar los modelos de dominio.

**4. Negociación.**
La IR es esencialmente un **proceso complejo de comunicación y negociación** que involucra clientes, diseñadores, jefes de proyecto y personal de mantenimiento. Las personas involucradas son responsables de decidir qué hacer, cuándo hacerlo, qué información hace falta y qué herramientas usar. En muchas situaciones **el conflicto es inherente a los requisitos**, y por eso hay que negociarlos entre los interesados. Existen herramientas de soporte para esto — el capítulo menciona *Win-Win Groupware*, desarrollada para acompañar a los interesados durante el proceso de negociación.

Dos aclaraciones que hace sobre la negociación y conviene retener: es **una de las actividades más cruciales** del desarrollo, porque tiene gran impacto en el producto final; y en la realidad **se ejecuta en paralelo** con todas las demás y **continúa hasta que los requisitos están implementados**. No es una etapa que se abre y se cierra.

**5. Aseguramiento de calidad.**
El objetivo es garantizar que los requisitos registrados en el documento de especificación sean de alta calidad. Su propósito, dicho con más precisión: **establecer niveles de confianza razonables y realistas** al escribir y gestionar requisitos.

El capítulo insiste en dos puntos:

- Es importante que **tanto los clientes como los desarrolladores** participen de las actividades de aseguramiento de calidad, porque ambos influyen en el éxito del proyecto.
- El aseguramiento de calidad de los requisitos **no es solo una actividad de la fase de requisitos**. Tiene que abordarse a lo largo de todo el ciclo de vida: los requisitos deben trazarse durante todo el desarrollo y asegurarse su calidad mediante inspecciones, revisiones y pruebas.

> ⚠️ **Cruce con la cátedra.** Este último punto —calidad y trazabilidad como actividad continua, no como control de una sola vez— es la base conceptual del vocabulario con el que te van a corregir: *verificable*, *trazable*, *no ambiguo*. El capítulo 8 del libro desarrolla esto en detalle; el 11 se ocupa específicamente de la ambigüedad.

---

## 6. Tendencias nuevas y la práctica que viene 🟢

Esta sección es la más fechada del capítulo — está escrita en 2005 y mira hacia adelante desde ahí. Vale leerla sabiendo eso.

Las mejoras tecnológicas del mercado global están estrechamente ligadas a los entornos de negocio. Conceptos entonces nuevos —sistemas empresariales, comercio electrónico, telecomunicaciones— generaron líneas de investigación nuevas. A eso se suma la complejidad de trabajar en entornos distribuidos y heterogéneos, que cambia profundamente las habilidades necesarias y la tecnología usada para desarrollar y mantener aplicaciones.

En ese contexto, dicen los autores, la IR **empezó a evolucionar desde su rol tradicional** —un mero preámbulo del ciclo de vida— hacia convertirse en un foco central del proceso de desarrollo. Y ese nuevo rol exige entender la disciplina con más precisión que antes.

El eje que los autores destacan es **la decisión**: el proceso de IR es una actividad de resolución de problemas rica en decisiones. La complejidad de las actividades involucradas exige que las organizaciones coordinen el proceso decisorio y **aumenten la visibilidad** de las decisiones y de los roles que participan en ellas. En otras palabras: los desarrolladores necesitan entender mejor el abanico de decisiones que se toman en los niveles organizacional, de producto y de proyecto.

Cierran con dos observaciones:

- Los desarrolladores necesitan entender mejor **qué hace falta para generar apoyo gerencial adecuado y participación de los interesados**. Gestionar el proceso de IR con eficacia exige procedimientos y herramientas, pero también tomar en cuenta cuestiones **sociales, políticas y culturales**.
- Los enfoques emergentes de desarrollo —mencionan explícitamente los **métodos ágiles**— y las tendencias del negocio y la tecnología están forzando a la IR a expandir su rol dentro del ciclo de vida.

---

## 7. Evidencia empírica 🟢

La investigación empírica apunta a capturar evidencia cuantitativa y a **comparar la teoría con la realidad**, ayudando a sacar conclusiones y a evaluar métodos y herramientas nuevos.

Por qué importa en este campo específicamente: los resultados de esos estudios sirven para dos cosas a la vez — **caracterizar los problemas potenciales** de los que se ocupa la disciplina (en los tres niveles: negocio, producto y proyecto) y **evaluar técnicas nuevas en un contexto relevante**. Además, tanto los académicos como los profesionales necesitan evidencia de respaldo antes de adoptar tecnologías nuevas.

El capítulo reconoce la dificultad práctica: recolectar evidencia empírica en la industria suele ser lento y puede volverse muy complicado. Aun así, es necesario para cuantificar y demostrar los méritos relativos de cada propuesta.

### Las tres estrategias de investigación cuantitativa 🟢

Según el propósito de la evaluación —si se evalúan técnicas, métodos o herramientas— y según las condiciones de la investigación, los tres tipos más comunes son:

| Estrategia | Cómo funciona |
|---|---|
| **Experimento** | Suele ser **altamente controlado** —por eso a veces se lo llama experimento controlado— y correrse en entorno de laboratorio. Los sujetos se asignan a los distintos tratamientos **al azar** |
| **Caso de estudio** | Normalmente se conduce **estudiando un proyecto real**. Sirve para monitorear proyectos, actividades o asignaciones. Los datos se recolectan con un propósito específico a lo largo del estudio |
| **Encuesta** (*survey*) | Es una investigación hecha **en retrospectiva**, cuando una herramienta o técnica lleva ya un tiempo en uso. Los medios principales de recolección son **entrevistas o cuestionarios** |

> ⚠️ **Ojo con este cuadro.** Entrevistas y cuestionarios aparecen acá como instrumentos de *investigación empírica sobre la disciplina*, que es un uso distinto del que les vas a dar en la materia — donde son **técnicas de elicitación** aplicadas a un proyecto concreto. Mismo instrumento, propósito diferente. En el parcial, entrevista y cuestionario son técnicas de elicitación.

---

## 8. Cierre del capítulo

Los autores resumen dos aportes: desde lo teórico, una introducción breve al área; desde lo práctico, orientación sobre los aspectos que hacen falta para aprovechar el resto del libro.

Y explican cómo se organiza el libro en tres partes:

- **Parte 1** — capítulos del estado del arte, que cubren las actividades clave enumeradas en la sección 5: elicitación, especificación y modelado, priorización, dependencias entre requisitos, análisis de impacto, negociación y aseguramiento de calidad.
- **Parte 2** — las tendencias nuevas de la IR, señalando sus ventajas y sus riesgos.
- **Parte 3** — evidencia empírica, tanto de investigación académica como de casos industriales.

---

## Mapa de lo que leíste

```
                    ¿QUÉ ES UN REQUISITO?
                    (IEEE 610.12: necesidad + obligación + documento)
                              │
              ┌───────────────┼───────────────┐
              ▼               ▼               ▼
        CLASIFICACIONES   ACTIVIDADES     INTERESADOS
        · RF / RNF        · Elicitación   · influyen o son influidos
        · meta/dominio/   · Análisis      · a medida vs. mercado
          producto/diseño · Negociación   · inconsistencia inevitable
        · primarios /     · V&V
          derivados       · Cambios
        (fronteras        · Trazabilidad
         difusas)               │
                                ▼
                        SE GESTIONAN EN 3 NIVELES
                        organizacional → producto → proyecto
                        × estratégico / táctico / operativo
                                │
                                ▼
                        5 PRÁCTICAS DE GESTIÓN
                        elicitar · priorizar · impacto
                        negociar · asegurar calidad
                                │
                                ▼
                        POR QUÉ TODO ESTO
                        US$1 ahora vs. US$200 después
```

---

## Preguntas para chequear que quedó

Sin respuestas — si alguna te traba, tirámela por chat.

1. ¿Por qué el estándar IEEE necesita tres cláusulas para definir "requisito" en vez de una? ¿Qué captura cada una que las otras no?
2. Un requisito que nace de una norma legal y que ningún usuario pidió, ¿es un requisito? ¿Con qué parte de la definición lo justificás?
3. ¿Por qué la distinción entre "qué" y "cómo" no es objetiva según el capítulo?
4. Explicá con el ejemplo de la seguridad por qué la frontera entre requisito funcional y no funcional se vuelve difusa durante la implementación.
5. Alguien que nunca va a usar el sistema, ¿puede ser interesado? Justificá con la definición.
6. ¿Qué cambia en la identificación de interesados entre desarrollo a medida y desarrollo dirigido por el mercado?
7. ¿Cuál es el argumento a favor de *tolerar* inconsistencias durante el modelado de requisitos? ¿Y cuál es la posición de los autores del capítulo?
8. Nombrá las tres razones por las que los requisitos elicitados tienden a salir incompletos e inconsistentes.
9. ¿Por qué el aseguramiento de calidad no puede ser solo una actividad de la fase de requisitos?
10. Ubicá en la matriz de tres niveles: ¿en qué celda cae decidir si un requisito entra en la próxima versión del producto?

---

**FIN DE LA PARTE 1 — Contexto de la Ingeniería de Requisitos**

*Sigue en la Parte 2: qué es la elicitación de requisitos, cómo es el proceso y qué roles asume el ingeniero de requisitos mientras lo conduce.*
