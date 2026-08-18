# Lectura en español — Cap. 8 · Parte 2: Enfoques constructivos y analíticos

> **Origen.** Capítulo 8, secciones 8.3 a 8.6, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Christian Denger y Thomas Olsson**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1.** Se asumen conocidos los diez atributos de calidad y la división entre enfoques constructivos y analíticos.

---

## 1. Enfoques constructivos 🔴

> **Los enfoques constructivos aseguran la calidad durante la creación de los requisitos. En ese sentido son preventivos: buscan minimizar que se cometan errores.**

Pero con una advertencia realista de arranque:

> **La ingeniería de requisitos es en gran medida una actividad basada en humanos. Aun si se usan métodos formales, en algún punto vas a estar interactuando con clientes y otros interesados. Como los humanos somos falibles, estamos condenados a cometer errores.**
>
> **Por lo tanto, aunque los métodos constructivos se apliquen según todas las reglas, va a seguir habiendo necesidad de chequear los resultados** — es decir, de aplicar enfoques analíticos.

### 1.1 Las técnicas de elicitación como aseguramiento de calidad 🔴

Durante la elicitación se capturan requisitos de fuentes diversas y los interesados trabajan juntos para derivar un conjunto apropiado. **Qué atributos de calidad quedan asegurados por elicitar bien:**

| Atributo asegurado | Cómo |
|---|---|
| **Comprensibilidad** | **Desarrollando una terminología común** y asegurando que los distintos interesados **hablen el mismo idioma** |
| **Completitud** | Si la elicitación se hace correctamente, **todos los interesados relevantes y sus intereses individuales deberían quedar identificados** |
| **Verificabilidad** | **Involucrando a los que prueban** (*testers*) |
| **Factibilidad** | **Involucrando a los desarrolladores** |
| **Corrección** | La elicitación **debería estar dirigida por las preocupaciones del negocio.** La aptitud, como parte de la corrección, se apoya en eso: es más probable que el software traiga un beneficio financiero real en el contexto de uso |

> ⚠️ **Cruce con la cátedra — muy aprovechable.** Fijate en las filas de verificabilidad y factibilidad: **son consecuencia directa de a quién invitás a la elicitación.** Si no hay nadie del lado de las pruebas, nadie va a notar que un requisito no se puede verificar. Si no hay desarrolladores, nadie va a notar que no se puede construir.
>
> Es un criterio concreto para justificar la composición de una reunión en un TP: **cada atributo de calidad que querés asegurar te dice a quién tenés que sentar en la mesa.** Y conecta con el capítulo 4, donde se pedía que estuvieran siempre representados clientes, desarrolladores y finanzas.
>
> Notá también que **"desarrollar una terminología común" figura como técnica de aseguramiento de calidad**, no como preparativo. Es la justificación de construir un léxico del dominio, dicha desde el ángulo de la calidad.

### 1.2 Las técnicas de especificación 🔴

El objetivo principal de la especificación es **documentar los requisitos de tal manera que puedan usarse como base para el desarrollo**. Su salida usual es un documento de requisitos que captura los aspectos relevantes del sistema a construir.

#### Estándares y plantillas

Los estándares —el capítulo menciona **IEEE 830-1998 e IEEE 1233-1998**— describen **qué elementos debería tener una "buena" especificación** y **qué atributos de calidad deberían cumplir los requisitos**. Las plantillas también proveen elementos que deberían especificarse: **plantillas de cómo especificar casos de uso, o cómo estructurar el documento de requisitos**.

**Qué atributos aseguran:**

| Atributo | Cómo |
|---|---|
| **Completitud** | Si los ingenieros adhieren a las recomendaciones del estándar y aplican las plantillas predefinidas, **puede asegurarse que se consideren todos los aspectos relevantes** del documento |
| **Comprensibilidad y modificabilidad** | **La estructura que proveen las plantillas y los estándares asegura que los documentos se parezcan entre proyectos distintos de una misma empresa.** La estandarización **previene ambigüedades dentro de los documentos** y mejora la comprensibilidad y la modificabilidad, **porque los elementos que hay que cambiar pueden encontrarse más fácilmente** |

#### Casos de uso y escenarios como técnica de calidad 🔴

Y acá viene el párrafo que más te sirve de esta sección:

> **Especificar los requisitos funcionales usando, por ejemplo, casos de uso y escenarios relacionados asegura también la comprensibilidad de los requisitos desde el principio**, porque **los casos de uso y los escenarios son fáciles de entender para interesados técnicos y no técnicos**. Esto sostiene también el atributo de **nivel de detalle correcto**.
>
> Además, **los casos de uso parecen ser una fuente valiosa para la definición de casos de prueba de aceptación y de sistema. Por lo tanto, especificar los requisitos de manera estructurada y orientada a escenarios mejora su verificabilidad.**

> ⚠️ **Cruce con la cátedra.** Este párrafo justifica, en el lenguaje de la calidad, **por qué la materia se estructura como se estructura**. Los casos de uso no se enseñan porque sí: aseguran **comprensibilidad** (los entienden técnicos y no técnicos), **nivel de detalle correcto**, y **verificabilidad** (de ellos salen los casos de prueba).
>
> Es el mismo argumento del capítulo 3 —tres conceptos nomás para que los no técnicos puedan leerlos— visto ahora como aseguramiento de calidad.

**Y la salvedad honesta del final:**

> **Básicamente sería posible abordar casi todos los atributos de calidad de manera constructiva, si ciertos procesos y estándares se siguieran y aplicaran rigurosamente. Sin embargo, la práctica muestra que esos enfoques rigurosos no siempre son razonables ni factibles** — por restricciones de tiempo, de presupuesto, regulaciones, etc.

### 1.3 El prototipado 🟡

> **Un prototipo es una versión ejecutable del sistema en desarrollo, aunque restringida de una manera u otra.** Un prototipo de interfaz de usuario implementa partes de la interfaz, la estructura y la navegación, pero **no va a tener toda la funcionalidad**; un prototipo de rendimiento se enfoca en la carga de memoria y CPU y **puede no tener interfaz alguna**.

**Su objetivo:** que los interesados **puedan probar el sistema y hacer sugerencias de mejora**. Al hacerlo, **tienen una mejor sensación de si el sistema representa lo que pidieron**, y eso **ayuda a identificar requisitos faltantes y detectar concepciones erróneas**.

Y el argumento de fondo:

> **El valor más importante de un prototipo es que cruza la brecha entre la descripción y la implementación.** Además, un problema bastante común con los requisitos es que **el cliente a menudo no sabe exactamente qué quiere.**

**Qué atributos asegura:**

| Atributo | Cómo |
|---|---|
| **Inconsistencias e incompletitud** | **El propio proceso de desarrollar un prototipo las revela**, y así mejora la calidad |
| **Corrección** | Se mejora **dejando que los interesados trabajen con un objeto concreto y lo evalúen, en vez de con los requisitos abstractos** |
| **Factibilidad** | **Probando distintas soluciones ya en la fase de requisitos.** Se puede ahorrar mucho tiempo y dinero **si los callejones sin salida se detectan en una etapa temprana** |

Y un dato experimental: **el prototipado puede reducir significativamente los errores de requisitos y de diseño, especialmente en las interfaces de usuario.**

---

## 2. Enfoques analíticos 🔴

Evalúan la especificación **para chequear si los requisitos cumplen los criterios de calidad especificados**. Y arrancan con la dificultad estructural del asunto:

> **El desafío principal de los enfoques analíticos es que no hay documentos de referencia contra los cuales chequear los requisitos** — es decir, **no hay una fuente documentada de verdad con la cual comparar.**
>
> **Esto enfatiza que el aseguramiento de calidad de los requisitos tiene que involucrar a todos los interesados relevantes.**

> Es una diferencia clave con las pruebas de código: cuando probás código, tenés la especificación como vara. Cuando "probás" la especificación, **la vara son las personas**. Por eso no se puede hacer solo.

---

## 3. Las inspecciones de requisitos 🔴

> **Las inspecciones son un medio valioso para asegurar la calidad de un producto de software justo después de su creación.** Apuntan a **minimizar que los problemas se propaguen a fases posteriores**, porque **los problemas se abordan en la misma fase en la que se introducen.**

Considerando el costo de un problema de requisitos, **las inspecciones de requisitos son uno de los enfoques de aseguramiento más costo-efectivos.**

### El beneficio lateral: transferencia de conocimiento 🔴

> **Muchas organizaciones reportan una transferencia de conocimiento mejorada al realizar actividades tempranas de aseguramiento** como inspecciones y creación de casos de prueba. Por ejemplo, **con la ayuda de los escenarios de lectura y las preguntas de las listas de verificación, es posible transferir conocimiento sobre patrones de defectos, buenas prácticas y trampas conocidas, desde los expertos hacia las personas menos experimentadas.**

> ⚠️ **Cruce con la cátedra.** Este beneficio describe con precisión **la rúbrica colaborativa** que construyen en tu materia: acumular el feedback de las correcciones en un formato compartido **es exactamente eso** — una lista de verificación que transfiere patrones de defecto y trampas conocidas del docente al grupo. Y que se pueda llevar impresa al parcial cierra el círculo: se estudia con la misma herramienta con la que se corrige.

### Las cuatro dimensiones de una inspección 🔴

Una inspección se caracteriza por: **el proceso**, **los roles** involucrados, **las técnicas de lectura** usadas, y **cómo se documentan los resultados**.

### 3.1 El proceso 🔴

Un proceso básico contiene **cuatro pasos principales**:

```
   1. PLANIFICACIÓN
      manejar las cuestiones organizativas de la inspección

   2. DETECCIÓN
      los inspectores buscan problemas en el documento

   3. RECOLECCIÓN / REUNIÓN
      reunión moderada que funde los resultados de los
      inspectores en una lista de defectos aprobada

   4. CORRECCIÓN
      el autor debe resolver todos los problemas identificados
```

Estos pasos son comunes a casi todas las instanciaciones. Algunos procesos mencionan pasos adicionales, como **una reunión de panorama general** o **una reunión de seguimiento**.

**Cada fase puede implementarse de maneras distintas** según el nivel de detalle deseado. Por ejemplo:

> Si los requisitos van a chequearse solo desde un punto de vista abstracto, **la fase de preparación individual podría saltearse** y los requisitos discutirse directamente en una reunión con ciertos expertos. Según el estándar IEEE 1028-1997, **ese proceso sería similar a un recorrido** (*walkthrough*) del documento.

**La empresa que aplica el enfoque tiene que decidir a qué nivel de detalle inspeccionar** — y eso depende principalmente de la estrategia de calidad (Parte 1).

### 3.2 Las técnicas de lectura 🔴

> **El paso más importante, pero también el más difícil, de una inspección de requisitos es el paso de detección.** Una **técnica de lectura** apoya al inspector en ese paso.

> **Una técnica de lectura representa una serie de pasos o procedimientos que guían al inspector en adquirir un entendimiento más profundo de los requisitos bajo inspección y en detectar problemas en ellos.**

Hay tres clases:

| Técnica | En qué consiste |
|---|---|
| **Lectura improvisada** (*ad-hoc*) | **Leer sin guía adicional, basándose en la propia experiencia** |
| **Lectura basada en lista de verificación** | Usar **una lista de preguntas** que apuntan a problemas potenciales |
| **Lectura basada en escenarios** | Usar **una descripción paso a paso** que guía al inspector durante la detección |

#### Lectura basada en lista de verificación 🔴

Se basa en listas con preguntas que deberían responderse durante la detección, enfocadas en **los aspectos de calidad relevantes** para los requisitos bajo inspección.

**Su fortaleza:** le dice al inspector **qué chequear**.

**Su debilidad más citada:** **da poco apoyo sobre CÓMO realizar el análisis.** Los revisores **no reciben orientación ni pistas sobre cómo responder las preguntas de la lista.**

**Y una advertencia importante sobre las listas:**

> **No existe una lista de verificación estándar que pueda aplicarse en todos los contextos. Una lista tiene que ser específica de la empresa y a veces incluso del proyecto.** Tiene que **adaptarse al contexto y a las características de la empresa y del proyecto.**

**De dónde salen las preguntas de una buena lista:**

- los elementos del marco de calidad (metas de calidad, restricciones organizacionales, atributos de importancia);
- las **listas de verificación ya existentes** (las estrategias básicas);
- **los defectos y problemas conocidos**;
- **el conocimiento experto**.

**Las tres debilidades básicas de las listas de verificación:**

```
   1. las preguntas son a menudo EXTREMADAMENTE GENERALES
   2. falta orientación concreta sobre CÓMO USAR la lista
   3. las preguntas a menudo NO ESTÁN ACTUALIZADAS
```

> ⚠️ **Cruce con la cátedra.** Las tres debilidades son un checklist para evaluar la propia rúbrica colaborativa. **Preguntas demasiado generales no detectan nada** ("¿es claro el requisito?" no ayuda a nadie); **sin criterio de cómo aplicarlas**, cada uno responde distinto; **y si no se actualizan con el feedback nuevo**, envejecen. Que la rúbrica se construya incrementalmente a lo largo de la cursada ataca justo la tercera.

#### Lectura basada en escenarios 🔴

Se desarrollaron para superar esas debilidades. Su idea básica:

> **Los inspectores son guiados por un escenario que les dice QUÉ buscar durante la inspección y CÓMO realizarla.** Además, **el escenario guía al inspector a trabajar activamente con los requisitos, lo que resulta en un entendimiento más profundo de los requisitos y de sus interrelaciones.**

**Por qué importa esa profundidad:**

> **Tener un entendimiento profundo de los requisitos es prerrequisito para encontrar defectos más sutiles y lógicos, que son a menudo críticos para el sistema final.**

Y una tercera ventaja: **los escenarios enfocan la atención de los inspectores en los aspectos de calidad esenciales y en las partes de los requisitos que necesitan la investigación más minuciosa.**

Las variantes disponibles: **lectura basada en perspectivas**, **lectura basada en trazabilidad**, **lectura basada en defectos** y **lectura basada en uso**.

### 3.3 Lectura basada en perspectivas 🔴

La más interesante de las cuatro, y la que mejor se puede robar para un TP.

> **Su aspecto especial es que los requisitos se inspeccionan desde el punto de vista de distintos interesados.** Los distintos interesados tienen intereses distintos en los requisitos.
>
> **El supuesto detrás: los requisitos son de buena calidad si todos los interesados que los usan para sus tareas específicas coinciden en su calidad** — es decir, **no encuentran problemas serios en ellos.**

```
                      usuario
                                    experto del
                                     dominio
        cliente        DOCUMENTO
                            DE      diseñador
                      REQUISITOS

                    quien prueba
```

**El primer paso al aplicarla:** **identificar las perspectivas potenciales y las preocupaciones de calidad que le interesan a cada una.** Porque en cada contexto de empresa **las perspectivas involucradas son distintas**.

> ⚠️ **Cruce con la cátedra — muy aplicable.** Esta técnica es directamente usable en tu equipo: **antes de entregar, que cada integrante lea el documento desde una perspectiva asignada distinta** — uno como usuario, uno como quien va a probar, uno como quien va a construir. Encuentra cosas distintas que si los tres leen "buscando errores".
>
> Y notá el supuesto de fondo, que es elegante: **la calidad no la certifica un experto; la certifica el acuerdo de todas las perspectivas.** Es la misma lógica de la no ambigüedad de la Parte 1 — que un texto sea claro para un grupo no alcanza.

### 3.4 La trazabilidad como guía de inspección 🔴

Los vínculos de trazabilidad pueden **guiar a los inspectores a través de los requisitos**. Concretamente:

**Para la consistencia.** El atributo de consistencia **está directamente relacionado con la capacidad de trazar un requisito hacia otro**. Con vínculos bien definidos, **el inspector puede seguirlos y chequear que los requisitos trabajen juntos de manera consistente y correcta**. La detección se vuelve más eficiente **porque los inspectores no tienen que imaginar las relaciones potenciales: pueden seguir los vínculos existentes.**

**Para la completitud.** Siguiendo los vínculos, el inspector puede **juzgar si ciertas funciones están completamente realizadas** por los distintos requisitos, evaluando **si la suma de los requisitos resulta en el apoyo deseado para el usuario**.

**Para la mantenibilidad.** Los vínculos **indican qué requisitos están muy relacionados entre sí**, y así ayudan a juzgar la mantenibilidad y la comprensibilidad.

**Y sin trazabilidad, igual sirven.** Aun sin ese apoyo, las inspecciones pueden abordar muchos de los atributos —asumiendo que se hagan minuciosamente:

```
   corrección · completitud · no ambigüedad ·
   comprensibilidad · factibilidad · modificabilidad ·
   verificabilidad
```

Eso se logra **con el conjunto correcto de preguntas** en los escenarios de lectura y las listas de verificación.

---

## 4. Pruebas basadas en requisitos 🔴

### El mito que hay que romper

Las pruebas se realizan usualmente al final, cuando hay partes ejecutables. **Esa percepción llevó al mito de que las pruebas solo pueden empezar al final del proceso.** Los autores lo corrigen:

> **Las pruebas son más que ejecutar los casos de prueba y buscar fallas en el software final. Al menos los dos pasos de planificación de pruebas y creación de casos de prueba pueden y deberían integrarse al proceso de desarrollo mucho antes de lo que se los integra habitualmente.**

**La recomendación:**

> **La planificación de pruebas y la creación de casos de prueba deberían realizarse apenas los requisitos —o un subconjunto autocontenido— estén definidos.**

### Por qué funciona 🔴

> La idea de la creación temprana de casos de prueba **es similar a la de las inspecciones basadas en perspectivas**. Mediante la construcción temprana de los casos, **los ingenieros de prueba ganan un mejor entendimiento de los requisitos y son capaces de identificar debilidades y problemas potenciales dentro de ellos.** Además, **traen una perspectiva completamente nueva sobre los requisitos.**

Y el mecanismo concreto, que es lo mejor de la sección:

> **Si los ingenieros de prueba tienen dificultades para derivar el caso de prueba de aceptación a partir de un requisito, puede ser necesario refinar el requisito, agregar información faltante, o eliminar/reformular el requisito porque no es posible probarlo.**

> ⚠️ **Cruce con la cátedra — esto es una herramienta, no solo teoría.** Es **el test operativo de la verificabilidad**, y podés aplicarlo vos mismo sobre cualquier requisito que escribas:
>
> **Intentá escribir el caso de prueba que lo verificaría. Si no podés, el requisito está mal.**
>
> No hace falta ser tester ni tener el sistema. Si no podés describir qué harías para comprobar que el requisito se cumple, es porque el requisito no dice lo suficiente, o dice algo que no se puede medir. Es el mismo criterio que "el sistema debe ser rápido" no es un requisito hasta tener métrica (capítulo 3), pero convertido en un procedimiento que podés correr.

**Qué atributos mejora la creación temprana de casos de prueba:**

```
   corrección · completitud · ambigüedad ·
   consistencia · verificabilidad
```

**Y qué pasa si se hace al final:**

> **Esos problemas se propagan de los requisitos a todas las fases posteriores, y los ingenieros de prueba pueden basar sus casos en los requisitos equivocados — porque para entonces los requisitos se dan por sentados**, como una fuente fija de verdad, que es algo distinto de lo que son al comienzo del proceso.

### La trazabilidad, otra vez 🟡

También acá los vínculos ayudan. Dan **mejor entendimiento de qué aspectos hay que probar juntos** y **qué requisitos ya están cubiertos** por los casos definidos. Según la granularidad de los vínculos, se puede juzgar:

- **qué requisitos están cubiertos** por uno o más casos de prueba;
- **qué casos prueban más de un requisito**;
- **si hay casos que cubren un solo requisito**.

Esa información **ayuda a identificar puntos que necesitan atención especial**. Y además, **la trazabilidad ayuda a seleccionar las partes que necesitan pruebas de regresión**, identificando qué requisitos se ven afectados por un cambio.

---

## 5. Enfoques automatizados y métodos formales 🟡

### Lo que las herramientas pueden hacer

> **Debido a la naturaleza abstracta e informal de la mayoría de los documentos de requisitos, es difícil aplicar herramientas automatizadas para asegurar su calidad.**

Para problemas simples —**gramática, ortografía**— hay herramientas disponibles, y eliminar esos problemas **típicamente mejora la comprensibilidad**.

### Las herramientas de detección de ambigüedad 🔴

Para **un** atributo hay más soporte disponible: **la no ambigüedad**. Y el mecanismo es simple y muy aprovechable:

> La idea es **identificar ciertos patrones y palabras clave en los requisitos que apuntan a áreas de riesgo potencial** — es decir, áreas donde es posible más de una interpretación.
>
> Estas herramientas identifican, **basándose en un glosario, frases marcadas como débiles o subjetivas** — por ejemplo: **"si es posible", "puede", "podría", "opcionalmente"**. Recorren el documento con ese glosario predefinido **y proveen una lista de todas las apariciones de las frases débiles.**

Los autores aclaran que **la aplicabilidad de estas herramientas en la práctica industrial todavía tiene que investigarse más**.

> ⚠️ **Cruce con la cátedra — robá esto directamente.** No hace falta la herramienta: **hacé la lista de palabras débiles y buscalas a mano en tu entregable antes de entregarlo.** Candidatas obvias en español: *si es posible · debería · podría · eventualmente · opcionalmente · adecuado · apropiado · rápido · amigable · fácil · flexible · robusto · entre otros · etc.*
>
> Cada una de esas palabras es un lugar donde el lector va a completar con su propia interpretación. Es el chequeo de ambigüedad más barato que existe y se hace con Ctrl+F.

### Los métodos formales 🟡

Cuando los requisitos se definen de manera formal se puede automatizar más. **El uso de lenguajes formales lidia con los problemas evitando la naturaleza imprecisa del lenguaje natural**: los requisitos se especifican de manera semánticamente bien definida, típicamente con base matemática.

**Los beneficios:**

- **La comunicación entre los interesados es más precisa**, y así se reducen los malentendidos y las ambigüedades.
- **Es posible chequear la completitud y la consistencia** del documento.
- Es posible la **prueba automatizada de propiedades de seguridad**.
- El ingeniero puede **realizar simulaciones del sistema futuro**, si el lenguaje tiene soporte de herramientas.

**Las desventajas —y son las que los vuelven poco usados:**

> **Son difíciles de aprender y difíciles de entender para una persona sin el trasfondo necesario. Específicamente, el cliente a menudo no está interesado en aprender el lenguaje formal, y hay que encontrar un compromiso.**
>
> **La primera versión de los requisitos podría formularse en lenguaje natural, en el idioma del cliente. Después habría que traducir los requisitos a la versión formal.**

---

## 6. Preguntas abiertas 🟢

Los autores enumeran lo que falta investigar.

**Sobre las pruebas tempranas:**

- **Falta evidencia empírica** de que los enfoques propuestos efectivamente ahorren dinero y mejoren la calidad. Es importante conseguir esos datos **para transferir los enfoques a la industria** — o sea, para convencer a los profesionales.
- **La creación de casos de prueba se hace sin involucrar al usuario final.** Casi todos los papers mencionan explícitamente que el usuario debería involucrarse, **pero no dicen cómo**.
- **Muchos enfoques dan poca orientación sobre cómo derivar los casos de prueba** de los requisitos o de sus modelos intermedios. A menudo hay solo descripciones de alto nivel.
- **La variedad de notaciones.** Dentro de una especificación se usan cada vez más notaciones distintas —texto puro, tablas, diagramas de casos de uso, diagramas de secuencia. **Cómo lidiar con esa variedad durante la creación de casos de prueba es una pregunta sin resolver**, porque **cada notación provee entrada relevante**.

**Sobre las inspecciones:**

- Hacen falta **enfoques para inspeccionar documentos heterogéneos** y un proceso para **integrar eficientemente a los diversos interesados**.
- Hace falta **soporte a la decisión**: orientación sobre **cuándo incluir qué interesados** y **cuándo es necesario realizar qué pasos del proceso**.
- Hace falta una guía sobre **qué técnica de lectura usar**. Y acá hacen una observación aguda sobre el enfoque de la investigación previa:

> **La investigación pasada se enfocó solo en qué técnica supera a cuál en eficiencia y efectividad. La pregunta más relevante parece ser CÓMO DEBERÍAN COMBINARSE las distintas técnicas de lectura** para lograr una inspección más eficiente. Es decir: **qué técnica es más apta para detectar qué tipos de problemas.**

**Y la pregunta abierta que consideran más importante:**

> **Cómo pueden combinarse los distintos enfoques de aseguramiento —constructivos y analíticos— en una estrategia comprensiva.**
>
> Se sabe que **distintos enfoques ayudan a abordar distintos problemas de calidad. Desafortunadamente, ni el estado del arte ni el estado de la práctica pueden declarar explícitamente qué enfoques son más eficientes para abordar qué problemas de calidad.**

Un segundo paso importante que señalan: **definir qué características de calidad externas o del sistema deberían abordarse** —seguridad, reusabilidad, mantenibilidad— **y cómo esas cualidades se manifiestan en los requisitos**. Si se puede trazar esa conexión, **es posible adaptar los enfoques para que se enfoquen en las cualidades del sistema más relevantes para el cliente.**

---

## 7. Conclusión del capítulo 🔴

> **La calidad es un tema escurridizo pero importante para los requisitos, especialmente porque la calidad de los requisitos va a afectar, más o menos, a todos los demás artefactos del desarrollo.**

El capítulo presentó un marco para el aseguramiento de calidad en la fase de requisitos, que describe **un conjunto de atributos usados para definir la calidad** y **qué hay que considerar** al armar una estrategia.

---

## Mapa de la Parte 2

```
   CONSTRUCTIVOS — previenen

   ELICITACIÓN ────► comprensibilidad (terminología común)
                     completitud (todos los interesados)
                     verificabilidad (invitar a los testers)
                     factibilidad (invitar a desarrolladores)
                     corrección (guiada por el negocio)

   ESPECIFICACIÓN ─► completitud (estándares y plantillas)
                     comprensibilidad y modificabilidad
                     CASOS DE USO: comprensibles para técnicos
                     y no técnicos + fuente de casos de prueba
                     → verificabilidad

   PROTOTIPADO ────► revela inconsistencias e incompletitud
                     corrección · factibilidad
                     ⚠ riesgo: el usuario se encariña (cap. 2)

   ─────────────────────────────────────────────

   ANALÍTICOS — detectan
   dificultad de base: NO HAY documento de referencia
   contra el cual comparar → hay que involucrar a la gente

   INSPECCIONES
   proceso: planificar → detectar → recolectar → corregir
   técnicas de lectura:
     improvisada · lista de verificación · por escenarios
   POR PERSPECTIVAS: cada uno lee desde un rol distinto
     supuesto: buena calidad = TODAS las perspectivas
     coinciden en que está bien

   PRUEBAS TEMPRANAS
   ══► EL TEST DE LA VERIFICABILIDAD:
       si no podés escribir el caso de prueba,
       el requisito está mal

   HERRAMIENTAS
   detectan FRASES DÉBILES: "si es posible", "puede",
   "podría", "opcionalmente" → hacelo a mano con Ctrl+F
```

---

## Preguntas para chequear que quedó

1. ¿Por qué, aunque los enfoques constructivos se apliquen bien, siguen haciendo falta los analíticos?
2. ¿Qué cinco atributos de calidad asegura una buena elicitación, y cómo cada uno?
3. ¿A quién hay que invitar a la elicitación para asegurar verificabilidad? ¿Y factibilidad?
4. ¿Cómo contribuyen los estándares y plantillas a la completitud, la comprensibilidad y la modificabilidad?
5. ¿Qué tres atributos de calidad aseguran los casos de uso y escenarios? Justificá cada uno.
6. ¿Por qué los enfoques rigurosos no siempre son razonables ni factibles?
7. ¿Qué es un prototipo y cuál es su valor más importante?
8. ¿Qué tres atributos mejora el prototipado?
9. ¿Cuál es el desafío estructural de los enfoques analíticos en requisitos? ¿Qué consecuencia tiene?
10. ¿Cuáles son las cuatro dimensiones de una inspección?
11. Nombrá los cuatro pasos del proceso de inspección.
12. ¿En qué se convierte una inspección si se saltea la preparación individual?
13. ¿Cuál es el paso más importante y difícil de una inspección, y qué lo apoya?
14. Nombrá las tres clases de técnica de lectura.
15. ¿Cuál es la fortaleza y cuál la debilidad de la lectura basada en lista de verificación?
16. ¿Por qué no existe una lista de verificación estándar aplicable a todos los contextos?
17. Nombrá las tres debilidades básicas de las listas de verificación.
18. ¿Qué agregan los escenarios de lectura respecto de las listas? Nombrá las tres ventajas.
19. Explicá la lectura basada en perspectivas y su supuesto de fondo.
20. ¿Cómo ayudan los vínculos de trazabilidad a inspeccionar la consistencia? ¿Y la completitud?
21. ¿Cuál es el mito sobre cuándo empiezan las pruebas y por qué es falso?
22. Explicá el test operativo de la verificabilidad: ¿qué hacés si no podés derivar el caso de prueba?
23. ¿Qué pasa si los casos de prueba se crean recién al final?
24. ¿Cómo funcionan las herramientas de detección de ambigüedad? Dé cuatro ejemplos de frase débil.
25. Nombrá cuatro beneficios y dos desventajas de los métodos formales.
26. ¿Cuál es, según los autores, la pregunta abierta más importante del área?

---

**FIN DEL CAPÍTULO 8 — PARTE 2**

**FIN DEL CAPÍTULO 8**

*Sigue el capítulo 9: modelado de metas y razonamiento con ellas, en 3 partes.*
