# Lectura en español — Elicitación de requisitos: el proceso y los roles

> **Qué es este archivo.** Parte 2 de la serie. Contiene las secciones 2.1 y 2.2 del capítulo 2 de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005), reescritas completas en español. El capítulo 2 lo firman **Didar Zowghi y Chad Coulin**, de la Universidad Tecnológica de Sídney.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1** (contexto de la IR). Se asume que ya sabés qué es un requisito, qué es un interesado y cuáles son las actividades generales de la IR.

---

## Antes de empezar: por qué este capítulo pesa distinto

El capítulo 1 era un panorama escrito por los editores. Este es otra cosa: un **relevamiento sistemático de la literatura** hecho por dos investigadores especializados, y es el capítulo más largo y más denso de la primera parte del libro.

También es el que más directamente se cruza con tu cursada. El cronograma dedica tres clases a elicitación —la 03, la 04 y la 05— y los temas que anuncia coinciden casi renglón por renglón con lo que hay acá, incluido el título de la clase 05: *"Rol del IR (mediador, documentador)"*. Esos dos roles se definen en este archivo, en la sección 4.

---

## 1. Qué es la elicitación, en una línea 🔴

El resumen del capítulo la define así: **el proceso de buscar, descubrir, adquirir y elaborar requisitos** para sistemas basados en computadora.

Y agrega inmediatamente la aclaración terminológica que sostiene todo el capítulo: se entiende generalmente que los requisitos **se elicitan, no simplemente se capturan o se recolectan**. Esa elección de palabra no es cosmética. Implica que en el proceso hay elementos de **descubrimiento, emergencia y desarrollo** — cosas que no estaban ahí antes y que aparecen durante el trabajo.

> Comparalo con "recolectar". Recolectás algo que ya existe y está tirado en algún lado; solo hay que ir a buscarlo. Elicitás algo que todavía no tiene forma, que está implícito en cómo trabaja la gente, o que directamente no existe hasta que alguien pregunta bien. Toda la disciplina descansa sobre esa distinción.

---

## 2. Introducción 🔴

### De dónde salen las técnicas, y por qué eso importa 🔴

La elicitación representa una etapa **temprana pero continua y crítica** del desarrollo. Los requisitos de un sistema pueden estar **dispersos en muchas fuentes**: los dueños del problema, los interesados, la documentación, y otros sistemas ya existentes.

Acá viene una de las afirmaciones más interesantes del capítulo. Por la naturaleza intensamente comunicacional de la elicitación, **muchas de las técnicas efectivas no se originan en la ingeniería de software ni en la investigación en ciencias de la computación**. Las técnicas de elicitación derivan principalmente de:

- las **ciencias sociales**,
- la **teoría organizacional**,
- la **dinámica de grupos**,
- la **ingeniería del conocimiento**,
- y muy a menudo, de la **experiencia práctica**.

> 💡 Esto explica algo que si no puede resultar desconcertante: cuando en la materia aparezcan etnografía, análisis de protocolo o grillas de repertorio —cosas que suenan a psicología o antropología y no a sistemas— no es que la cátedra se fue de tema. Es que la disciplina fue a buscar herramientas a donde estaban.

### Qué tan importante es 🟡

El capítulo se apoya en el mismo estudio de campo que ya apareció en la Parte 1: **Hofmann y Lehner**, quince equipos de IR, identificando las prácticas clave que deberían conducir al éxito de un proyecto. La elicitación efectiva de requisitos estaba, discutiblemente, entre las más importantes de las buenas prácticas resultantes.

Contra eso, los autores plantan una crítica directa: **pese a su importancia, se le prestó atención insuficiente** a esta área tanto en la industria como en la investigación en ingeniería de software hasta la fecha.

### Por qué sale mal tan seguido 🔴

La elicitación es un proceso muy complejo: muchas actividades, múltiples técnicas disponibles para cada una, y una naturaleza multidisciplinaria que solo suma complejidad. Está **sujeta a un grado alto de error**, y los autores señalan de dónde viene ese error: de **factores arraigados en problemas de comunicación**.

En la realidad es una actividad multifacética e iterativa que descansa fuertemente sobre dos cosas: **las habilidades comunicativas del ingeniero de requisitos** y **el compromiso y la cooperación de los interesados del sistema**. Si falta cualquiera de las dos, el resto de la técnica no alcanza.

Y acá está el diagnóstico central del capítulo, que conviene leer con atención porque reaparece varias veces:

> Uno de los problemas principales que enfrentan los equipos de desarrollo son las **barreras de comunicación** y el acuerdo sobre los requisitos. **El punto de fondo es que conceptos que están claramente definidos para una comunidad de participantes pueden ser completamente opacos para los miembros de otra.**

Y el remate, que es lo verdaderamente peligroso:

> **El hecho de que esta situación exista suele pasar desapercibido** en el transcurso de la elicitación, a menos que se le preste atención específica al problema.

Nadie se da cuenta de que no se están entendiendo. Las dos partes salen de la reunión convencidas de haber acordado algo, y acordaron dos cosas distintas.

> ⚠️ **Cruce con la cátedra.** Este párrafo es la justificación conceptual de la mitad de la materia. La ambigüedad que Laura penaliza, el vocabulario controlado que vas a construir en la segunda mitad de la cursada, la insistencia en *no ambiguo* y *sin doble interpretación* — todo eso son respuestas a este problema. La misma palabra significa cosas distintas de un lado y del otro del mostrador, y nadie lo nota.

### El contexto cambia todo 🟡

El tipo de sistema y el propósito del proyecto afectan significativamente **cómo** se conduce la elicitación. El ejemplo que da el capítulo: el método empleado para un sistema de control embebido hecho a medida va a ser sustancialmente distinto del de un sistema comercial de gestión de inventario.

Los escenarios posibles que enumera:

- desarrollo de sistemas de información basados en web,
- líneas de producto dirigidas por el mercado,
- implementación de grandes sistemas empresariales,
- selección de productos **COTS**,
- mantenimiento de sistemas existentes y heredados.

> 🕳️ **COTS** — sigla de *commercial off the shelf*, "comercial listo para usar". Software que se compra ya hecho en vez de desarrollarlo. Cuando el proyecto es elegir un COTS, la elicitación cambia de naturaleza: no elicitás para construir, elicitás para **evaluar cuál de los productos existentes se acerca más**.
>
> 🕳️ **Sistema heredado** (*legacy*) — un sistema viejo que sigue en producción porque el negocio depende de él, típicamente con tecnología obsoleta y sin documentación. Volvé al camino.

A eso se suma que los equipos de proyecto pueden estar **repartidos en distintas ubicaciones geográficas y venir de trasfondos culturales diversos**.

Y por último, la elección de técnica para una situación particular depende de una serie de factores adicionales:

| Factor | |
|---|---|
| **Tiempo y costo** | El más determinante en la práctica |
| **Disponibilidad de recursos** | Gente, acceso a los interesados |
| **Criticidad de seguridad del sistema** | Un sistema donde una falla mata gente exige otro rigor |
| **Restricciones legales o regulatorias** | Normativa que condiciona qué y cómo se puede relevar |

---

## 3. ¿Qué es la elicitación de requisitos? 🔴

Primera advertencia de los autores, y es honesta: **actualmente hay muy poca uniformidad** en la investigación y en la práctica respecto de una definición estándar de elicitación. No existe *la* definición; existen definiciones.

La que ellos proponen: la elicitación se ocupa de **aprender y entender las necesidades de los usuarios y de los patrocinadores del proyecto**, con el objetivo último de **comunicar esas necesidades a los desarrolladores del sistema**.

Fijate en la estructura de esa definición, porque tiene dos mitades y la segunda se olvida seguido. No alcanza con entender: hay que **lograr que el que va a construir entienda**. Una elicitación perfecta que no se transmite no sirve de nada.

Una parte sustancial del trabajo está dedicada a **descubrir, extraer y sacar a la superficie los deseos** de los interesados potenciales.

### Pescar con red 🔴

Los autores citan a **Robertson y Robertson**, que se refieren a este proceso con la imagen de **pescar con red de arrastre** (*trawling*). La metáfora resalta un hecho: a través de este proceso es probable que obtengas **más requisitos de los que esperabas**.

Y de ahí sacan una regla práctica que vale la pena retener:

> **Juntar unos cuantos requisitos de más al principio es siempre mejor que juntar de menos.**

Esa es también una de las razones por las que la **priorización** y la **negociación** son partes importantes de la IR — porque si vas a juntar de más, después hay que decidir qué entra. Y el problema se agrava en la IR dirigida por el mercado, donde la **sobrecarga por la afluencia constante de grandes cantidades de requisitos** es un problema serio en sí mismo.

> ⚠️ **Cruce con la cátedra.** Esto rima directo con la regla del café con leche: **arrancar granular y unir después, nunca al revés.** Son el mismo principio visto desde dos ángulos. La red trae de más, y recién en una segunda pasada se agrupa, se prioriza y se descarta. Lo que ninguna de las dos reglas te permite es empezar agrupado y después intentar desagregar, porque lo que se perdió en el camino no vuelve.

### Inventar requisitos 🟡

Un giro más reciente que el capítulo menciona: se empezaron a usar los conceptos de **inventar** y **crear** requisitos, para destacar el rol de la **creatividad** y para enfatizar qué es lo que realmente ocurre durante la elicitación.

Es un paso más allá de "elicitar". Elicitar todavía sugiere que algo estaba latente y lo sacaste a la luz. Inventar admite abiertamente que parte de los requisitos **no existían en ninguna cabeza** hasta que la conversación los produjo.

---

## 4. El proceso de elicitación 🔴

### Qué tiene que permitir el proceso

Un proceso de elicitación involucra un conjunto de actividades que **debe permitir**:

- comunicación,
- priorización,
- negociación,
- y colaboración con todos los interesados relevantes.

Y además debe **dar bases sólidas para la emergencia, el descubrimiento y la invención** de requisitos, como parte de un proceso altamente interactivo.

### La brecha cultural 🔴

Las actividades de elicitación son intensamente comunicativas, y su peso aumenta cuando se considera lo que el capítulo llama la **"brecha cultural"** (*culture gap*): las **diferencias semánticas básicas** que separan a la comunidad que **posee el problema** de la comunidad que **lo resuelve**, cuando intentan entablar un diálogo con sentido.

```
   COMUNIDAD QUE POSEE          COMUNIDAD QUE RESUELVE
      EL PROBLEMA                    EL PROBLEMA
   ┌──────────────────┐          ┌──────────────────┐
   │ Vocabulario del  │          │ Vocabulario      │
   │ negocio          │          │ técnico          │
   │ Supuestos        │  ←──?──→ │ Supuestos        │
   │ implícitos       │          │ implícitos       │
   │ Sabe hacer, no   │          │ Sabe construir,  │
   │ sabe explicar    │          │ no sabe el       │
   │                  │          │ dominio          │
   └──────────────────┘          └──────────────────┘
              ↑                            ↑
              └──── la misma palabra ──────┘
                  significa cosas distintas
```

Otra vez la advertencia de que no hay nombres unificados: **hay muy poca uniformidad en la literatura y en la práctica sobre cómo se llaman las actividades** que se realizan durante la elicitación. Lo que sí está generalmente aceptado es que **la elicitación es la etapa inicial del proceso de IR** — aunque una etapa iterativa e integrada, no un bloque que se abre y se cierra.

### Las cinco actividades fundamentales 🔴

Las actividades típicas se pueden dividir en cinco tipos.

#### 4.1 Entender el dominio de aplicación

Al comenzar el proceso es importante **investigar y examinar en detalle la situación o "mundo real"** donde el sistema va a residir finalmente — lo que a veces se llama el *dominio de aplicación*.

El entorno actual necesita explorarse a fondo, incluyendo los aspectos **políticos, organizacionales y sociales** relacionados con el sistema, además de cualquier restricción que esos aspectos puedan imponer sobre el sistema y sobre su desarrollo.

Los procesos de trabajo existentes y los problemas relacionados que el sistema va a resolver deben describirse **en relación con las metas y las cuestiones clave del negocio**.

> Reparen en el orden: primero el mundo, después el sistema. Y en que "político" figura antes que "organizacional" y "social". No es un descuido — quién tiene poder para bloquear el proyecto es información de elicitación.

#### 4.2 Identificar las fuentes de requisitos

Los requisitos pueden estar **dispersos en muchas fuentes y existir en variedad de formatos**. En todo proyecto se pueden identificar varias fuentes posibles:

| Fuente | Qué aporta |
|---|---|
| **Los interesados** | La fuente más obvia del sistema |
| **Usuarios y expertos del dominio** | Información detallada sobre los problemas y las necesidades de los usuarios |
| **Sistemas y procesos existentes** | Otra fuente de elicitación, particularmente cuando el proyecto implica **reemplazar** un sistema actual o heredado |
| **Documentación existente** — manuales, formularios, informes — sobre los sistemas actuales y los procesos de negocio | Información útil sobre la organización y el entorno, y además requisitos para el sistema nuevo junto con **su justificación y su importancia** |

> 🕳️ **Experto del dominio** (*subject matter expert*, SME) — la persona que domina el área del negocio, no la tecnología. El contador que sabe cómo se liquida realmente, la enfermera que sabe cómo se ordena realmente la guardia. Suele ser la fuente más valiosa y la más difícil de agendar.

Vale detenerse en la última fila. Los formularios y los informes que ya usa la organización son fuente de requisitos **y también de su justificación**. Un campo que existe en un formulario en papel desde hace veinte años está ahí por alguna razón, y esa razón es un requisito.

#### 4.3 Analizar a los interesados 🔴

Los interesados son las personas que **tienen un interés en el sistema o son afectadas de algún modo** por su desarrollo e implementación, y por eso deben ser consultadas durante la elicitación.

Típicamente incluyen grupos e individuos **internos y externos** a la organización.

Sobre quién es el más importante, el capítulo hace una distinción fina que vale la pena tener presente:

- **El cliente** —y más específicamente el **patrocinador del proyecto**, el que lo paga y lo respalda— es usualmente el interesado **más aparente**.
- **Pero en algunos casos los usuarios reales del sistema pueden ser los más importantes.**

Más aparente no es lo mismo que más importante. Son dos ejes distintos y confundirlos es un error clásico.

También deben considerarse interesados otras partes cuya **esfera de interés** se extienda a alguna parte de las operaciones del sistema, si están afectadas: los responsables de los estándares de procesos de trabajo, los clientes, los socios.

Uno de los primeros pasos de la elicitación es, por lo tanto, **analizar e involucrar a todos los interesados relevantes**. Existen en la literatura listas extensas de interesados potenciales que conviene consultar durante esta actividad.

El proceso de análisis de interesados también suele incluir la identificación de **representantes clave de los usuarios** y de **campeones de producto**.

> 🕳️ **Campeón de producto** (*product champion*) — la persona dentro de la organización cliente que adopta el proyecto como propio, lo empuja hacia adentro y le abre puertas. No es un rol formal, es una alianza. Los proyectos que no tienen uno suelen morir de indiferencia.

> ⚠️ **Cruce con la cátedra.** Analizar interesados es actividad de elicitación **y** contenido del entregable grupal de la clase 01 (usuarios y stakeholders). Retené la distinción cliente / patrocinador / usuario: es exactamente el tipo de granularidad que la cátedra pide y el tipo de confusión que penaliza. "Usuario" a secas suele ser demasiado grueso.

#### 4.4 Seleccionar las técnicas, los enfoques y las herramientas 🔴

Hay quien sostiene que una sola técnica de elicitación, o una sola metodología, alcanza y se puede aplicar a todos los casos. La posición generalmente aceptada es la contraria: **ninguna técnica o enfoque individual puede ser adecuado para todos los proyectos**.

La elección depende del **contexto específico del proyecto**, y suele ser un **factor crítico del éxito** del proceso de elicitación.

Y acá viene lo mejor de la sección. **Hickey y Davis** investigaron cómo se eligen realmente las técnicas, y encontraron que una técnica particular puede resultar seleccionada por razones como estas:

| | Razón por la que se eligió la técnica |
|---|---|
| **(a)** | Es la **única que el analista conoce** |
| **(b)** | Es **la favorita** del analista |
| **(c)** | Es la que **prescribe la metodología** que se está siguiendo para el desarrollo |
| **(d)** | La elección se rige **únicamente por la intuición** del analista sobre qué será efectivo en el contexto actual |

Leé esa lista de nuevo y fijate qué es lo que **no** figura en ninguna de las cuatro opciones: *"porque es la técnica adecuada para este problema"*. Ese es el hallazgo. Las cuatro razones documentadas son razones del analista, no del proyecto.

La conclusión de los autores: claramente, **la elicitación se hace mejor usando una variedad de técnicas**. En la mayoría de los proyectos se emplean varios métodos, en distintas etapas del ciclo de vida, y a menudo en cooperación cuando son complementarios.

> ⚠️ **Cruce con la cátedra.** Este es el punto de este archivo que más directamente te puede sumar puntos. Laura valora el **criterio fundamentado por encima de la respuesta canónica** y acepta soluciones distintas si están justificadas. Cuando en un TP elijas una técnica de elicitación, **justificá la elección contra las características del caso** — el tipo de sistema, el acceso a los interesados, el tiempo disponible, la criticidad. Elegir entrevista porque es lo que todos eligen cae exactamente en la casilla (b) de Hickey y Davis.

#### 4.5 Elicitar los requisitos de los interesados y otras fuentes

Una vez identificadas las fuentes y los interesados específicos, **empieza la elicitación propiamente dicha** de los requisitos centrales, usando las técnicas, enfoques y herramientas seleccionadas.

Durante esta actividad es importante:

- **Establecer el nivel de alcance** del sistema.
- Investigar en detalle **las necesidades y los deseos** de los interesados, especialmente de los usuarios.
- **Determinar los procesos futuros** que el sistema va a realizar respecto de las operaciones del negocio.
- **Examinar las formas en que el sistema puede apoyar** esas operaciones, para satisfacer los objetivos principales y atender los problemas clave del negocio.

> Notá el desdoblamiento entre **necesidades** y **deseos** (*needs and wants*). No son sinónimos y la distinción es operativa: lo que alguien necesita para hacer su trabajo y lo que le gustaría tener son dos listas distintas, y solo una de las dos es obligatoria.
>
> Y notá también que se pide determinar **los procesos futuros**, no los actuales. La elicitación no es solo fotografiar cómo se trabaja hoy: es proyectar cómo se va a trabajar con el sistema puesto.

### La elicitación no ocurre en el vacío 🟡

El capítulo insiste con esto: el proceso está **fuertemente relacionado con el contexto** en que se conduce y con las características específicas del proyecto, la organización y el entorno.

En la práctica:

- **El presupuesto y el cronograma** del proyecto tienen efecto significativo sobre el proceso y sobre la forma en que se ejecuta.
- **La estructura y la madurez de la organización** determinan cómo se elicitan los requisitos.
- También lo determina **la forma en que el sistema va a interactuar** con los usuarios y con otros sistemas.
- Hay que considerar **el nivel de volatilidad** dentro del proyecto, porque afecta directamente la calidad de los requisitos y el proceso mismo.

> 🕳️ **Volatilidad** — cuánto y cuán rápido cambian los requisitos durante el proyecto. Un proyecto de alta volatilidad no es un proyecto mal gestionado necesariamente; puede ser un negocio que se mueve rápido. Pero exige otro tipo de elicitación.

### Cómo arranca, en la práctica 🟡

Típicamente el proceso **empieza con una declaración de misión de alto nivel, informal e incompleta** para el proyecto.

Esa declaración puede tomar la forma de un conjunto de **metas, funciones y restricciones fundamentales** del sistema objetivo, o de una **explicación de los problemas a resolver**.

Para desarrollar esa descripción se identifican los interesados y las otras fuentes de requisitos, y se los usa para elicitar. Los resultados preliminares **forman la base de la investigación y el refinamiento posteriores**, de manera típicamente iterativa e incremental.

### Los modelos de proceso, y por qué no alcanzan 🟢

Se propusieron a lo largo de los años varios modelos de proceso para la elicitación. En su mayoría ofrecen **solo una hoja de ruta genérica**, con flexibilidad suficiente para acomodar las diferencias contextuales básicas de cada proyecto.

Los autores explican por qué esos modelos **no pueden dar directrices definitivas**, y la explicación tiene dos partes:

1. El **rango amplísimo de tareas** que pueden realizarse durante la elicitación.
2. Que **la secuencia de esas actividades depende de las circunstancias específicas** de cada proyecto.

A eso se suma la variedad de problemas que pueden enfrentarse y la cantidad de técnicas disponibles, que solo lo complican más.

### Cómo se ejecuta realmente 🔴

En la mayoría de los casos, el proceso de elicitación se realiza:

- **incrementalmente**, a lo largo de múltiples sesiones,
- **iterativamente**, a niveles crecientes de detalle,
- y **al menos parcialmente en paralelo** con otras actividades del desarrollo del sistema.

Y después viene una de las frases más crudas del capítulo:

> **En la realidad, su finalización suele determinarse por restricciones de tiempo y costo, más que por haber alcanzado el nivel requerido de calidad y completitud de los requisitos.**

La elicitación no termina cuando está lista. Termina cuando se acabó el plazo.

> ⚠️ **Cruce con la cátedra.** Esa frase describe cómo es afuera, no cómo se evalúa adentro. En un parcial, un proceso de elicitación se juzga por su calidad y su completitud, no por haber cerrado a tiempo. Tenelo como conocimiento de contexto, no como criterio de resolución.

### Qué queda al final 🔴

El resultado típico del proceso es un **conjunto detallado de requisitos**, expresados en:

- **texto en lenguaje natural**,
- y **representaciones diagramáticas simples**,

acompañados de información adicional que incluye la **descripción de las fuentes**, las **prioridades** y las **justificaciones** (*rationales*) de cada requisito.

> ⚠️ **Cruce con la cátedra.** Retené los tres metadatos: de dónde salió, cuánto importa, por qué existe. La trazabilidad —una de las palabras del vocabulario con el que te van a corregir— empieza exactamente acá: un requisito que no registra su fuente no se puede trazar hacia atrás.

---

## 5. Los roles del ingeniero de requisitos 🔴

Esta sección es la que da título a la clase 05 de tu cronograma. Vale leerla despacio.

Primero, una aclaración de nombres: al ingeniero de requisitos **también se lo llama analista de sistemas o analista de negocio**. Son etiquetas para la misma función según la organización.

Los roles y responsabilidades que asume **dependen del proyecto, de las personas, del contexto y de la organización** involucrados. No hay una descripción de puesto universal.

Dos cosas atraviesan todos los roles:

- Una **parte sustancial** del trabajo consiste en **explorar el dominio del problema** y los requisitos situados en ese dominio.
- Con frecuencia necesita realizar **aspectos típicos de la gestión de proyectos**: no solo gestionar el proceso de elicitación, sino **comunicarlo efectivamente a los interesados**. Eso implica, entre otras cosas, tomar decisiones, priorizar y negociar.

Los roles concretos:

### 5.1 Facilitador 🔴

Cuando se elicitan requisitos mediante **sesiones de trabajo grupal**, el ingeniero de requisitos no solo tiene que hacer preguntas y registrar respuestas. Tiene que:

- **guiar y asistir a los participantes** para que aborden las cuestiones relevantes, de modo de obtener información correcta y completa;
- garantizar que los participantes **se sientan cómodos y confiados** con el proceso;
- y asegurar que **todos tengan oportunidad suficiente de contribuir**.

Los autores subrayan que este rol representa **una parte significativa de la habilidad y la experiencia** que se le requieren al analista para hacer elicitación efectiva. No es un extra blando sobre la competencia técnica: es parte de la competencia.

> El tercer punto es el más subestimado. En una reunión, el que más habla no es necesariamente el que más sabe. Si el jefe monopoliza y el operario que conoce el proceso real no abre la boca, la sesión produjo la opinión del jefe, no los requisitos del sistema.

### 5.2 Mediador 🔴

Durante la elicitación, **los conflictos son inevitables** — tanto entre los requisitos elicitados como entre los propios interesados.

En muchos casos, **la priorización de requisitos provenientes de distintos grupos de interesados es fuente de mucho debate y disputa**.

Cuando esas situaciones ocurren, el analista **hace de mediador** y es responsable de encontrar una resolución adecuada mediante **negociación y compromiso**.

Y una condición que los autores destacan: es importante que el analista sea **sensible a todos los aspectos políticos y organizacionales** del proyecto al mediar discusiones relacionadas con el sistema.

> ⚠️ **Cruce con la cátedra.** Este rol es contenido de la clase 05, y el entregable asociado es una **minuta de reunión de mediación**. Es decir: no vas a leer sobre mediación, vas a ejecutarla y documentarla. Lo que este capítulo te da es el marco de por qué el conflicto es estructural y no un accidente — los interesados **tienen** intereses distintos, y la disputa no significa que la elicitación salió mal.

### 5.3 Documentador 🔴

Con frecuencia el ingeniero de requisitos es responsable de **documentar los requisitos elicitados**.

El capítulo argumenta por qué este rol es particularmente importante, y el argumento tiene tres escalones:

1. **Representa la producción de los resultados** del proceso de elicitación. Es donde el trabajo se vuelve algo.
2. **Forma la base de las fases subsiguientes** del proyecto. Todo lo que viene después se para sobre esto.
3. **La evaluación del proceso de elicitación y del trabajo del analista se basa en esos artefactos resultantes** — y en algunos casos esos artefactos pueden constituir la base de **acuerdos contractuales**.

El tercer punto es el que muerde. Al analista **no se lo juzga por lo que entendió, sino por lo que documentó**. Y si el documento tiene valor contractual, una ambigüedad deja de ser un problema de comunicación y pasa a ser un problema legal.

> ⚠️ **Cruce con la cátedra.** Acá se cierra el círculo con todo el vocabulario de calidad de la materia. *No ambiguo*, *verificable*, *trazable* no son preferencias estéticas de la cátedra: son las propiedades que necesita un documento del cual pueden colgar obligaciones contractuales. Si te preguntan por qué importa tanto cómo se redacta un requisito, la respuesta corta es esta.

### 5.4 Suplente de la comunidad de desarrollo 🟡

Con frecuencia se le requiere al analista **asumir los diversos roles de la comunidad de desarrolladores** durante la elicitación. Esto incluye:

arquitectos de sistema · diseñadores · programadores · testers · personal de aseguramiento de calidad · consultores de implementación · administradores de mantenimiento del sistema

¿Por qué le toca a él? Porque en la etapa de elicitación **esos interesados todavía no fueron asignados al proyecto**. Nadie los contrató aún.

Y sin embargo —remarcan los autores— **las decisiones que se toman en esta fase van a afectarlos significativamente**, a ellos y a las fases subsiguientes del desarrollo. Alguien tiene que representar sus intereses en una mesa donde no están sentados.

### La validación de lo elicitado 🔴

Cierra la sección con la contracara del proceso. **Todos los requisitos elicitados deben validarse contra:**

- los otros interesados,
- otros sistemas,
- **entre sí**,
- y luego compararse con **las metas previamente establecidas** para el sistema.

Lo que eso significa, dicho por los autores: que los requisitos **describan apropiadamente las características deseadas** del sistema, y que **provean las funciones necesarias para cumplir los objetivos especificados**.

Este proceso típicamente **involucra a todos los grupos de interesados identificados** y **resulta en más actividades de elicitación**.

Esa última línea es la que cierra el bucle: validar no es un control final que aprueba o rechaza. Validar **genera más elicitación**. Es lo que hace que el proceso sea iterativo en serio y no solo en el diagrama.

```
        ┌──────────────────────────────────────┐
        │                                      │
        ▼                                      │
   ELICITAR ───→ DOCUMENTAR ───→ VALIDAR ──────┘
                                  │
                          (descubre huecos,
                           contradicciones,
                           supuestos falsos)
```

---

## Mapa de lo que leíste

```
   ELICITAR ≠ RECOLECTAR
   (hay descubrimiento, emergencia e invención)
              │
              ▼
   EL PROBLEMA DE FONDO: LA BRECHA CULTURAL
   mismo término, distinto significado,
   y nadie se da cuenta
              │
              ▼
   ┌──── LAS 5 ACTIVIDADES ────────────────────┐
   │ 1. Entender el dominio de aplicación      │
   │ 2. Identificar las fuentes                │
   │ 3. Analizar a los interesados             │
   │ 4. Seleccionar técnicas  ← Hickey y Davis │
   │ 5. Elicitar                               │
   └───────────────────────────────────────────┘
              │
              ▼
   ┌──── LOS 4 ROLES DEL ANALISTA ─────────────┐
   │ Facilitador   → que todos hablen          │
   │ Mediador      → resolver el conflicto     │
   │ Documentador  → por esto lo evalúan       │
   │ Suplente      → representa a los ausentes │
   └───────────────────────────────────────────┘
              │
              ▼
   SALIDA: requisitos en lenguaje natural
   + diagramas simples
   + fuente, prioridad y justificación de cada uno
              │
              ▼
   VALIDAR → genera más elicitación (bucle)
```

---

## Preguntas para chequear que quedó

Sin respuestas — si alguna te traba, tirámela por chat.

1. ¿Por qué los autores insisten en "elicitar" y rechazan "recolectar" o "capturar"? ¿Qué se pierde con las otras dos palabras?
2. ¿De qué disciplinas provienen mayormente las técnicas de elicitación, y por qué no de la ingeniería de software?
3. Explicá la brecha cultural. ¿Por qué es más peligrosa que un desacuerdo abierto?
4. ¿Qué significa "pescar con red" y qué regla práctica se desprende de la metáfora?
5. Enumerá las cinco actividades fundamentales del proceso de elicitación.
6. Un formulario en papel que la empresa usa hace veinte años, ¿es fuente de requisitos? ¿De qué tipo de información, además de los requisitos mismos?
7. ¿Qué diferencia hay entre el interesado *más aparente* y el *más importante*? Dé un caso donde no coincidan.
8. Las cuatro razones de Hickey y Davis por las que se elige una técnica, ¿qué tienen en común? ¿Qué razón brilla por su ausencia?
9. ¿Por qué la elicitación "no ocurre en el vacío"? Nombrá al menos tres factores del contexto que la condicionan.
10. Los tres metadatos que acompañan a cada requisito en la salida del proceso, ¿cuáles son y para qué sirve cada uno?
11. En el rol de facilitador, ¿por qué es responsabilidad del analista que todos tengan oportunidad de contribuir? ¿Qué pasa si no lo hace?
12. ¿Por qué el rol de documentador es el que más pesa sobre la evaluación del analista?
13. ¿Por qué el analista termina representando a arquitectos, testers y programadores durante la elicitación?
14. ¿Por qué se dice que la validación "genera más elicitación" en vez de cerrar el proceso?

---

**FIN DE LA PARTE 2 — Elicitación: el proceso y los roles**

*Sigue en la Parte 3: el catálogo completo de técnicas y enfoques de elicitación — entrevistas, cuestionarios, análisis de tareas, análisis de dominio, introspección, grillas de repertorio, clasificación de tarjetas, escalamiento, trabajo grupal, tormenta de ideas, JAD, talleres de requisitos, etnografía, observación, análisis de protocolo, aprendizaje por acompañamiento, prototipado, enfoques basados en metas, escenarios y puntos de vista. Es la parte más larga de la serie y la que más se cruza con las clases 03 a 05.*
