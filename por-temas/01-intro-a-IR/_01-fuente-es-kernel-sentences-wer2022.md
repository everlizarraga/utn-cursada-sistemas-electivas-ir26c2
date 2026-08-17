# Un enfoque colaborativo para especificar Kernel Sentences usando lenguaje natural

> **Traducción al español** del archivo fuente `fuente-kernel-sentences-wer2022.md` (conversión fiel de Kernel-Sentences-WER_2022_Camera_ready_paper_2.pdf, 13 páginas). **Documento derivado para estudio: ante cualquier duda o discrepancia, manda el archivo fuente en inglés (y en última instancia el PDF original).**

**Notas de traducción:**
- **Términos técnicos establecidos se mantienen en inglés**, con traducción entre paréntesis en su primera aparición (kernel sentences, requirements engineering, Use Cases, User Stories, stakeholders, business rules, etc.). Es el vocabulario que vas a encontrar en la bibliografía y en la cátedra.
- **Los ejemplos de las figuras van bilingües**: traducción al español + original en inglés en cursiva. Importante: **los análisis gramaticales del paper (verbos, conjunciones, voz pasiva) se refieren siempre a las oraciones originales en inglés** — por ejemplo, el verbo "to be" de "when it is hot" no aparece en la traducción "cuando hace calor".
- Los errores tipográficos y gramaticales del inglés original ("Symphony framework", "contribuation", "assement", etc.) no sobreviven a la traducción por naturaleza; están documentados en las Notas de conversión del archivo fuente. El nombre "Symphony" se mantuvo tal cual porque es un error de contenido, no de gramática (la referencia [23] es Symfony).
- Los rótulos del diagrama de la Figura 4 y el contenido de las capturas de pantalla (Figuras 9–11) se mantienen en inglés porque reproducen la figura y la interfaz reales; las descripciones están en español.
- Las referencias bibliográficas no se traducen (son citas).
- El puntaje SUS conserva la coma decimal del original: "71,07".

---

**Autores:** Leandro Antonelli¹, Alejandro Fernandez¹ ², Nicolas Ruffolo¹, Emiliano Sansone¹, Diego Torres¹ ² ³

¹ Lifia, Fac. de Informática, UNLP, La Plata, Bs As, Argentina
² Comisión de Investigaciones Cientificas (CICPBA)
³ Departamento de Ciencia y Tecnología, UNQ

{leandro.antonelli, alejandro.fernandez, nicolas.ruffolo, emiliano.sansone, diego.torres}@lifia.info.unlp.edu.ar

**Resumen** — La requirements engineering (ingeniería de requerimientos) es una parte crítica del desarrollo de software. Los errores en los requerimientos, si no se encuentran y corrigen temprano en el proceso de ingeniería, se convierten en problemas costosos más adelante. Los analistas suelen apoyarse en Use Cases (casos de uso) o User Stories (historias de usuario) para capturar los requerimientos. Sin embargo, hay conocimiento del dominio que estos artefactos no capturan bien (por ejemplo, las business rules —reglas de negocio— y los escenarios given-then-when). Ese conocimiento del dominio generalmente está distribuido entre múltiples stakeholders (interesados) y expertos del dominio con perspectivas que se complementan. Por lo tanto, es importante usar una técnica colaborativa con un artefacto simple para adquirir y validar su conocimiento. Kernel sentences (oraciones núcleo o básicas) es una definición lingüística sobre oraciones pequeñas (con un solo verbo) escritas en voz activa. Algunos autores relacionan las kernel sentences con las business rules. Sostenemos que las kernel sentences son adecuadas para usarse en la adquisición colaborativa y que pueden servir como insumo para producir artefactos más complejos. Este paper propone un enfoque colaborativo para adquirir y validar kernel sentences. El proceso tiene tres actividades principales: adquisición de las kernel sentences, validación de las mismas, y evaluación de la actividad de los expertos que participan. Este paper también describe un prototipo para dar soporte al proceso. Finalmente, se muestra el resultado de una evaluación preliminar con resultados prometedores sobre la aplicabilidad del proceso.

**Palabras clave** — requerimientos; especificaciones; kernel sentences; colaboración; lenguaje natural

## 1. Introducción

La requirements engineering es una etapa crítica del desarrollo de software. Los errores cometidos en esta etapa pueden costar hasta 200 veces más repararlos cuando el software ya fue entregado al cliente [3]. Hay dos filosofías principales de ciclo de vida del desarrollo de software: clásica y ágil. Ambas estrategias organizan el proceso de desarrollo y tratan los requerimientos de maneras distintas. En un ciclo de vida clásico se produce y consume una documentación extensa. Consiste, por ejemplo, en una especificación de requerimientos de software con cientos de Use Cases. En el desarrollo ágil, la comunicación de los requerimientos descansa en un rol específico dentro del equipo, el product owner (dueño del producto), y en un artefacto de documentación simple, la User Story. Las User Stories tienen información mínima y constituyen "una invitación a conversar" [1].

Los requerimientos descriptos como Use Cases o como User Stories definen los objetivos, el alcance y la funcionalidad del sistema de software. Sin embargo, las aplicaciones de software son "conocimiento empaquetado sobre el dominio" [7]. Este conocimiento necesita capturarse en un artefacto complementario a los Use Cases y las User Stories, por ejemplo en business rules [17] o en escenarios given-then-when [22].

Mientras que los objetivos y requerimientos de la aplicación de software pueden elicitarse de un grupo chico de personas (el cliente o el sponsor), el conocimiento del dominio reside en un grupo más amplio de stakeholders, los expertos del dominio, que generalmente tienen puntos de vista distintos y complementarios sobre el dominio. Por eso es importante involucrar a la mayor cantidad de expertos posible para adquirir su conocimiento de manera colaborativa [14].

Los expertos y el equipo de desarrollo pertenecen a mundos distintos y usan lenguajes distintos [20]. Los expertos usan el lenguaje del dominio mientras que el equipo de desarrollo usa un lenguaje de ciencias de la computación. Para lidiar con esta brecha de comunicación es importante usar artefactos en lenguaje natural que sean legibles por ambas partes [14].

El concepto de kernel sentence fue introducido en 1957 por el lingüista Z.S. Harris [12] y figuró en los primeros trabajos del lingüista Noam Chomsky [8]. Las kernel sentences también se conocen como oraciones básicas. Son construcciones declarativas, en voz activa, siempre afirmativas y con un solo verbo. Boyd [4] sugiere el uso de kernel sentences para describir modelos en el desarrollo de software.

Este artículo propone un proceso colaborativo para especificar kernel sentences. Consiste en tres actividades principales. La primera actividad consiste en la especificación de kernel sentences por parte de los expertos. La segunda actividad consiste en la validación de las kernel sentences especificadas en la primera actividad por parte de los demás expertos. Finalmente, la tercera actividad consiste en evaluar el comportamiento de los expertos para determinar qué tan confiables son sus contribuciones. Este artículo también describe un prototipo que puede usarse para dar soporte al proceso propuesto. Finalmente, el paper presenta una evaluación preliminar usando la encuesta SUS [5] [6] que muestra la aplicabilidad del proceso.

Creemos que este enfoque puede usarse en ambas filosofías de desarrollo de software: ágil y clásica. El esfuerzo de ejecutar el proceso está más relacionado con el ciclo de desarrollo clásico y puede integrarse con las etapas tempranas de la requirements engineering, antes de definir el alcance del sistema de software y los requerimientos. No obstante, pensamos que el enfoque propuesto también puede usarse en ágil, porque la herramienta prototipo propuesta puede lidiar con la complejidad y reducir el esfuerzo. Además, el conocimiento consolidado es un buen complemento de las User Stories.

El resto del paper se organiza de la siguiente manera. La Sección 2 describe algo de contexto sobre las kernel sentences. La Sección 3 detalla nuestra contribución, es decir, el proceso colaborativo propuesto. La Sección 4 describe la herramienta que da soporte al proceso. La Sección 5 presenta la evaluación preliminar. La Sección 6 repasa trabajos relacionados. Finalmente, la Sección 7 discute algunas conclusiones.

## 2. Kernel Sentences

Una kernel sentence es una construcción simple con un solo verbo. Es además activa, positiva y declarativa. Esta oración básica no contiene ningún modo. Se la denomina "kernel" (núcleo) porque es la base sobre la cual se forman otras oraciones más complejas. Por ejemplo, la Figura 1 describe dos kernel sentences. La primera oración establece que el sujeto "farmer" (agricultor) realiza una acción ("fertilizes", fertiliza) sobre cierto objeto ("tomatoes", tomates). La segunda oración tiene la misma estructura pero describe una acción distinta ("water", regar) y además agrega la descripción de "cuándo" se realiza la acción. Es importante mencionar que el verbo "to be" (ser/estar) no tiene significado semántico. Por eso el segundo ejemplo tiene dos verbos: "to water" y "to be". La Figura 2 muestra dos oraciones que no son kernel, ya que ambas tienen dos verbos. La primera usa los verbos "to fertilize" y "to add", mientras que la segunda usa "to water" y "to prevent". La primera oración puede reescribirse como dos kernel sentences (Figura 3). El agricultor es el sujeto del primer verbo, es decir, "the farmer fertilizes…". Y la actividad de fertilización es el sujeto de la segunda acción, es decir, "the fertilization adds nutrient". Este ejemplo muestra cómo la oración original (Figura 2), con dos verbos, saca una conclusión sobre el rol del agricultor que fertiliza y agrega nutrientes. Sin embargo, las responsabilidades correctas quedan expresadas en la Figura 3, que describe que el agricultor fertiliza y, a causa de esa actividad, los nutrientes se agregan. Esta precisión en la descripción es muy importante para entender el dominio.

> El agricultor fertiliza los tomates
> *(The farmer fertilizes the tomatoes)*
> El agricultor riega los tomates cuando hace calor
> *(The farmer waters the tomatoes when it is hot)*
>
> **Figura 1.** Kernel Sentences

> El agricultor fertiliza los tomates para agregar nutrientes que no están presentes en el suelo.
> *(The farmer fertilizes the tomatoes to add nutrients that are not present in the soil.)*
> El agricultor riega los tomates para evitar que se sequen.
> *(The farmer waters the tomatoes to prevent them of drying out.)*
>
> **Figura 2.** Oraciones que no son kernel

> El agricultor fertiliza los tomates
> *(The farmer fertilizes the tomatoes)*
> La fertilización agrega nutrientes al suelo
> *(The fertilization adds nutrient to the soil)*
>
> **Figura 3.** Oraciones reescritas como kernel sentences

## 3. El enfoque propuesto

El proceso propuesto tiene el objetivo de obtener kernel sentences de manera colaborativa a partir de los expertos del dominio, para consolidar el conocimiento del dominio de la aplicación. El proceso es colaborativo porque muchos expertos pueden participar al mismo tiempo. Las personas contribuyen con kernel sentences distintas, ya que distintos stakeholders pueden tener puntos de vista distintos sobre el dominio. Y esa visión complementaria es muy importante para producir una descripción integrada y completa del dominio.

El proceso considera dos roles distintos: los expertos del dominio y los analistas. Los expertos del dominio proveen las kernel sentences y validan las kernel sentences propuestas por otros expertos. Así se refuerza la característica colaborativa. Los analistas participan como moderadores del proceso. Tienen una visión completa del conjunto de kernel sentences provistas por todos los expertos y del alcance del sistema de software. De este modo, los analistas pueden identificar kernel sentences que no pertenecen al dominio y quitarlas del proceso. Los analistas también pueden identificar kernel sentences duplicadas propuestas por distintos expertos. Finalmente, los analistas monitorean la actividad del experto identificando expertos con algún comportamiento sesgado particular. Por ejemplo, un experto que acepta como válida toda kernel sentence, o que las rechaza todas como inválidas, no está comprometido con la actividad y su contribución debería omitirse porque no es confiable. El analista no necesariamente debe ser un experto del dominio. Es más: creemos que no debería ser un experto, para evitar sesgos basados en su subjetividad.

Así, el proceso propuesto considera tres actividades distintas: (i) especificación de kernel sentences, (ii) validación de kernel sentences, y (iii) evaluación de los expertos. Estas tres actividades se llevan a cabo en paralelo. Es decir, mientras se especifican oraciones, otras oraciones pueden validarse y al mismo tiempo pueden evaluarse los expertos.

La primera actividad (especificación de kernel sentences) descansa en la definición de kernel sentences por parte de algún experto (que se convierte en su autor). Luego, debe hacerse alguna revisión para verificar que la kernel sentence satisface las condiciones para ser considerada una kernel sentence (desde la perspectiva gramatical). Finalmente, algún analista debe revisar el conocimiento enunciado por la kernel sentence para determinar si es valioso o no para la descripción del dominio.

La segunda actividad (validación de kernel sentences) descansa en recolectar la opinión (acuerdo) de los expertos (distintos del autor) sobre las kernel sentences de la primera actividad. Finalmente, el analista decide si aceptar una kernel sentence como válida, en base a las opiniones de los expertos.

La tercera actividad (evaluación de los expertos) descansa en monitorear las contribuciones de los expertos, para identificar qué tan confiable es cada participante. Si una persona no es confiable, el analista debería excluirla de la actividad, junto con sus contribuciones. La Figura 4 resume el proceso completo.

```
┌───────────────────┐
│ Kernel Sentences  │
│  Specification    │───────┐
└───────────────────┘       │
         ↓                  ▼
       Kernel          ┌──────────┐      ┌────────────┐
      Sentences        │ Experts  │ ───► │   Expert   │
         ↓             │ assement │      │ evaluation │
┌───────────────────┐  └──────────┘      └────────────┘
│ Kernel Sentences  │       ▲
│    Validation     │───────┘
└───────────────────┘
         ↓
   Validated Kernel
      Sentences
```

**Figura 4.** El enfoque propuesto

*Descripción del diagrama (rótulos en inglés, tal cual el original):* diagrama de cajas y flechas del proceso. Una cadena vertical a la izquierda: la caja "Kernel Sentences Specification" (especificación) produce (flecha hacia abajo) el artefacto "Kernel Sentences", que entra (flecha hacia abajo) a la caja "Kernel Sentences Validation" (validación), la cual produce (flecha hacia abajo) el artefacto final "Validated Kernel Sentences" (kernel sentences validadas). Además, tanto desde la zona de especificación como desde la de validación salen flechas hacia la derecha que convergen en la caja "Experts assement" (evaluación de expertos; el rótulo tiene un error tipográfico en el original), de la cual sale una flecha hacia la derecha con el resultado "Expert evaluation" (evaluación del experto).

### 3.1. Especificación de kernel sentences

La actividad de especificación de kernel sentences se compone de tres pasos: (i) la descripción de la kernel sentence, (ii) la verificación de su calidad como kernel sentence, y (iii) la revisión de la kernel sentence, para confirmar que es significativa para el alcance del sistema de software.

El primer paso, la descripción de la kernel sentence, lo realiza algún experto. El experto se convierte en el autor de la oración. Es importante poder rastrear cada kernel sentence hasta su autor, porque los demás expertos (distintos del autor) deben indicar si están de acuerdo o no con la contribución. Además, identificar al autor también es importante para monitorear su participación durante la actividad de evaluación de expertos.

El segundo paso, la verificación, chequea si la kernel sentence es realmente una kernel sentence. También proponemos algunas verificaciones extra para asegurar que la contribución del experto sea lo más simple y clara posible. Los siguientes párrafos describen los tres pasos de verificación que proponemos.

La primera verificación consiste en chequear que la oración tenga la estructura sujeto + verbo + objeto, para verificar que tiene un solo verbo y que está escrita en voz activa. La Figura 5 provee algunos ejemplos de esta verificación.

> Los tomates son fertilizados por el agricultor (voz pasiva, incorrecta)
> *(The tomatoes are fertilized by the farmer — passive voice, not correct)*
> Es necesario fertilizar los tomates (sujeto nulo, incorrecta)
> *(It is necessary to fertilize the tomatoes — null subject, not correct)*
> El agricultor fertiliza y riega los tomates (dos verbos, incorrecta)
> *(The farmer fertilizes and waters the tomatoes — two verbs, not correct)*
> El agricultor fertiliza los tomates (correcta)
> *(The farmer fertilizes the tomatoes — correct)*
>
> **Figura 5.** Revisión de la estructura sujeto + verbo + objeto

La segunda verificación consiste en chequear la presencia de conjunciones. Hay distintos tipos de conjunciones: (i) conjunciones coordinantes como 'and' (y), 'or' (o), 'for', 'but' (pero), etc., (ii) conjunciones correlativas como 'not only' (no solo), 'but also' (sino también), 'either', 'neither', etc., (iii) y conjunciones subordinantes como 'after' (después de), 'as long as' (siempre que), 'if only', 'where' (donde), 'according to' (según), etc. La presencia de conjunciones no determina que la contribución no sea una kernel sentence. Sin embargo, puede dar una pista de que hay demasiada información contenida en una sola oración. La Figura 6 provee algunos ejemplos de esta revisión. Es importante mencionar que la tercera oración de la Figura 6 ("The farmer assesses the humidity of the soil") provee conocimiento que está implícito en la segunda oración de la misma figura ("The farmer waters the tomatoes according to the humidity of the soil"). Es decir, "according to" significa que el agricultor debería "evaluar la humedad". Además, el agricultor tiene algún criterio para decidir cuándo la humedad es suficiente y no hace falta regar.

> El agricultor fertiliza y riega los tomates (conjunción "and" para expresar dos verbos)
> *(The farmer fertilizes and waters the tomatoes — conjunction "and" to express two verbs)*
> El agricultor riega los tomates según la humedad del suelo (correcta, pero "according to" sugiere la presencia de más conocimiento).
> *(The farmer waters the tomatoes according to the humidity of the soil — correct, but "according to" suggests the presence of more knowledge.)*
> El agricultor evalúa la humedad del suelo (correcta, se infiere de la anterior)
> *(The farmer assesses the humidity of the soil — correct, it is inferred from the previous one)*
>
> **Figura 6.** Revisión de presencia de conjunciones

La tercera verificación consiste en chequear la presencia de adjetivos y adverbios. Aunque su presencia no confirma que la contribución no sea una kernel sentence, estos tipos de palabras caracterizan sustantivos y verbos, y su presencia puede dar una pista de que podría agregarse más información en otra kernel sentence. La Figura 7 provee algunos ejemplos de esta revisión. La primera oración usa la palabra "carefully" (cuidadosamente) y el agricultor sabe qué significa "carefully". Sin embargo, es importante enunciar explícitamente su significado. Así, la segunda oración describe que "carefully" significa "riega el suelo de los tomates" (evitando verter el agua directamente sobre la planta).

> El agricultor riega cuidadosamente los tomates (es una kernel sentence, pero usa el adverbio "carefully", que debería describirse)
> *(The farmer carefully waters the tomatoes — it is a kernel sentence, but it uses the adverb "carefully", that should be describe)*
> El agricultor riega el suelo de los tomates ("carefully" significa evitar verter el agua directamente sobre los tomates)
> *(The farmer waters the soil of the tomatoes — "carefully" means avoiding pouring the water directly to the tomatoes)*
>
> **Figura 7.** Revisión de presencia de adjetivos y adverbios

El tercer (y último) paso de la actividad de especificación de kernel sentences consiste en analizar si la oración es significativa para el dominio o no. Este análisis lo realiza el analista y, como no es un experto, su criterio podría no ser preciso. Sin embargo, es importante realizar algún análisis preliminar de la pertinencia de la oración antes de involucrar al resto de los expertos en la validación. La Figura 8 provee un ejemplo de esta revisión. Los analistas saben que la seguridad de los trabajadores es prioritaria, por eso "the farmer uses sun protection" (el agricultor usa protección solar) es importante. Sin embargo, está fuera del alcance del sistema de software. Por lo tanto, esta oración debería rechazarse.

> El agricultor usa protección solar (esto es importante para la salud del agricultor, pero está fuera del límite de la aplicación de software a desarrollar)
> *(The farmer uses sun protection — this is important for the farmer health, but it is out of the boundary of the software application to develop)*
>
> **Figura 8.** Revisión de pertinencia para el dominio

### 3.2. Validación de kernel sentences

La actividad de validación de kernel sentences tiene el objetivo de decidir si aceptar o no las kernel sentences especificadas en la primera actividad. Las aceptadas integrarán el conocimiento sobre el dominio. Esta actividad se compone de dos pasos: (i) los expertos dan su opinión sobre las kernel sentences especificadas por otro autor, y (ii) el analista toma una decisión sobre la kernel sentence (aceptarla o no) considerando las opiniones de los expertos.

El primer paso, la opinión de los expertos, consiste en elegir una de tres alternativas posibles: "accept" (aceptar), si el experto considera que la kernel sentence debería aceptarse (porque está de acuerdo con el autor); "reject" (rechazar), si el experto considera que la kernel sentence debería rechazarse (porque no está de acuerdo con el autor); (iii) y "don't have opinion" (no tengo opinión), si el experto no tiene conocimiento sobre lo que enuncia la kernel sentence.

El segundo paso, decidir sobre la kernel sentence, consiste en analizar las opiniones y, si son concluyentes, tomar una decisión: aceptar o rechazar. Si no, el analista puede esperar hasta que se recolecten más opiniones para decidir. Como sugerencia: más de la mitad de los expertos debería haber dado su opinión, y más de la mitad de las opiniones debería coincidir en aceptar o rechazar.

### 3.3. Evaluación de los expertos

La razón principal de la actividad de evaluación de expertos es monitorear la contribución de los expertos para identificar personas que no están comprometidas con la actividad y cuyas contribuciones no son confiables. Por ejemplo: (i) personas que contribuyen con información basura (porque finalmente no se acepta), (ii) personas con una tendencia sistemática a contradecir (es decir, que proveen siempre información falsa), (iii) personas que no piensan a fondo y aceptan o rechazan todo automáticamente. En nuestra experiencia hemos identificado dos comportamientos extremos. Uno representado por expertos que especificaron muchas kernel sentences, pero solo pocas fueron aceptadas por sus colegas. El otro comportamiento correspondió a personas que opinaron a favor de aceptar la mayoría de las kernel sentences, pero muchas de ellas fueron finalmente rechazadas por sus colegas.

Es importante identificar a estos contribuyentes no confiables y tomar acciones para evitar sesgar el resultado de la actividad. La medida más simple consiste en excluir a la persona de la actividad, ya que no está comprometida con ella. Según la cantidad de personas excluidas de la actividad, podría ser necesario revisar las kernel sentences en las que estuvieron involucradas, ya que habrían quedado sesgadas por opiniones no confiables.

Más allá del proceso propuesto, la evaluación de los expertos puede usarse en etapas posteriores del proceso de requirements engineering. Por ejemplo, la información recolectada sobre el comportamiento del experto puede identificar expertos que prefieren escribir o validar, o personas que tienen mucho conocimiento y cuyas contribuciones son mayormente aceptadas. Por ejemplo, la proporción entre kernel sentences validadas y kernel sentences escritas puede identificar si el experto es un "escritor" ("writer") o un "validador" ("validator"). Luego, la proporción entre kernel sentences escritas y kernel sentences aceptadas sugiere que la persona es un experto entre los demás expertos. Así, esta información puede usarse para planificar etapas posteriores del proceso de requirements engineering. Por ejemplo, para discutir algún tema particular con alguna persona específica, o para darle cierta información al "validador" y obtener su feedback.

## 4. Soporte de herramienta

Se implementó un prototipo de software que puede usarse para dar soporte a la aplicación del enfoque propuesto. El prototipo es una aplicación web implementada siguiendo una arquitectura orientada a servicios. Los servicios están implementados en PHP [19] usando el framework Symphony [23]. Además, también se usa Python [21] para comunicarse con la biblioteca SpaCy [25], usada para el procesamiento de lenguaje natural.

La aplicación es responsive, es decir, la interfaz de la aplicación se adapta al dispositivo usado: una computadora (de escritorio o laptop) o un dispositivo móvil (teléfono o tablet). Así, la aplicación ofrece una variedad de plataformas y los expertos tendrán un rango amplio de posibilidades para contribuir con la adquisición de conocimiento.

El prototipo implementa dos roles de usuario: (i) expertos y (ii) analistas. Todos los participantes pueden trabajar de manera asincrónica. Los expertos pueden agregar contribuciones (kernel sentences) y validar otras contribuciones. La Figura 9 muestra la interfaz para dar la opinión sobre las kernel sentences escritas por los demás expertos. Los analistas pueden verificar las contribuciones de los expertos y, finalmente, aceptarlas o rechazarlas considerando la opinión de los expertos. La Figura 10 muestra la interfaz donde se ven las kernel sentences con la opinión que los expertos dieron sobre ellas. Se muestran los porcentajes de "accepts" y "rejects", así como la cantidad de opiniones dadas. Los analistas también pueden monitorear la actividad de los expertos. La Figura 11 muestra la interfaz con la contribución de un experto. Muestra las kernel sentences que aportó, así como las kernel sentences sobre las que dio su opinión. La interfaz muestra la opinión del experto y la decisión final. Y hay algunas estadísticas sobre esta actividad. Así, el analista puede evaluar la actividad de los expertos e identificar contribuyentes no confiables.

**Figura 9.** Interfaz del rol de experto

*Descripción de la captura (contenido de la interfaz en inglés, tal cual el original; las tres oraciones son las de las Figuras 1 y 3):* pantalla de la aplicación web (marco de dispositivo negro, fondo degradado verde claro). Tabla con dos columnas — "Kernel sentences" y "Opinion" — y tres filas; cada fila ofrece tres radio buttons: Accept / Reject / Don't have opinion.

| Kernel sentences | Opinion |
|---|---|
| The farmer fertilizes the tomatoes | ○ Accept ○ Reject ○ Don't have opinion |
| The farmer waters the tomatoes when it is hot | ○ Accept ○ Reject ○ Don't have opinion |
| The fertilization adds nutrient to the soil | ○ Accept ○ Reject ○ Don't have opinion |

Debajo, botones "Submit" (enviar, azul) y "Cancel" (cancelar, blanco con borde rojo). Al pie: el rótulo "Ruem Requirements" y dos banderas (España y Reino Unido) como selector de idioma.

**Figura 10.** Interfaz del rol de analista

*Descripción de la captura:* misma aplicación, vista del analista. Tabla con columnas "Kernel sentences", "Author" (autor), "Accept" (% de aceptación), "Reject" (% de rechazo), "Opinions" (cantidad de opiniones) y "Decision" (decisión, con radio buttons Accept / Reject por fila).

| Kernel sentences | Author | Accept | Reject | Opinions | Decision |
|---|---|---|---|---|---|
| The farmer fertilizes the tomatoes | Clark | 60% | 10% | 10 | ○ Accept ○ Reject |
| The farmer waters the tomatoes when it is hot | Jim | 15% | 70% | 16 | ○ Accept ○ Reject |
| The fertilization adds nutrient to the soil | John | 95% | 0% | 14 | ○ Accept ○ Reject |

Debajo, botones "Submit" y "Cancel". Al pie: "Ruem Requirements" y las dos banderas.

**Figura 11.** Interfaz de la evaluación de expertos

*Descripción de la captura:* vista de evaluación de un experto. Arriba, tres indicadores circulares amarillos con métricas: "proposed / accepted 100%" (propuestas / aceptadas), "opinion agreed with decision 0%" (opiniones coincidentes con la decisión) y "Opinion provided 50%" (opiniones dadas). Debajo, tabla con columnas "Kernel sentences", "Role" (rol), "Decision" (decisión final) y "Opinion" (opinión del experto).

| Kernel sentences | Role | Decision | Opinion |
|---|---|---|---|
| The farmer fertilizes the tomatoes | Author | Accepted | |
| The farmer waters the tomatoes when it is hot | Validator | Rejected | Accept |
| The fertilization adds nutrient to the soil | Validator | Accepted | Don't have opinion |

Al pie: "Ruem Requirements" y las dos banderas.

Así, el flujo de trabajo completo de una kernel sentence, desde su contribución hasta su inclusión final en la base de datos de conocimiento consolidado, es el siguiente. Algún experto escribe una contribución y se convierte en su autor. La herramienta verifica si la contribución es una kernel sentence o no (es decir, verifica las reglas descriptas en la sección del enfoque). El analista chequea si la kernel sentence describe conocimiento dentro del alcance del sistema. Puede descartarla (reject) o considerar que la kernel sentence es elegible (accept) para mostrársela a los expertos y que expresen su opinión.

La aplicación muestra las kernel sentences aceptadas por los analistas a los expertos, para pedirles su opinión sobre la corrección del hecho que la kernel sentence enuncia. Así, los expertos pueden responder "accept", "reject" o "don't have opinion". Cuando la mayoría de los expertos dio su opinión, los analistas evalúan los porcentajes de "accept / reject / don't have opinion" para finalmente aceptar o descartar la kernel sentence.

## 5. Evaluación

El proceso colaborativo propuesto fue evaluado. La evaluación se realizó usando herramientas colaborativas generales, como hojas de cálculo de Google, en vez de usar la herramienta prototipo presentada en este paper, porque el objetivo de la evaluación era evaluar la aplicabilidad del proceso y no la usabilidad de la herramienta. Además, solo se evaluaron las dos actividades principales: especificación y evaluación, porque confiamos en el compromiso de los participantes, y por lo tanto no fue necesario evaluar la confiabilidad de sus contribuciones.

Los participantes de la evaluación fueron 14 estudiantes de un curso de posgrado sobre requirements engineering. Todos tienen experiencia en la industria, en desarrollo de software. Sin embargo, la característica más importante de ellos es la experiencia con el tema del caso de estudio. Jugaron el rol de expertos del dominio, y tuvieron que especificar y validar kernel sentences siguiendo el enfoque propuesto. Todos los participantes contribuyeron a especificar y validar kernel sentences para la misma base de conocimiento. Se les pidió contribuir con un rango de entre 10 y 20 kernel sentences, y tuvieron una semana para realizar la tarea. En general, todas las kernel sentences fueron definidas correctamente, aunque hubo muchas contribuciones repetidas, porque cuando los expertos contribuyen no conocen las contribuciones de los demás (salvo que reciban la contribución para validar). Uno de los autores de este paper fue el docente del curso y jugó el rol del analista. Chequeó que las kernel sentences cumplieran las condiciones para ser consideradas en la primera actividad (especificación de kernel sentences) y también asignó las kernel sentences a los participantes para obtener su opinión y finalmente aceptarlas o rechazarlas.

El dominio de aplicación usado en la evaluación fue el dominio de las aplicaciones de market-place (mercado en línea). Todos los participantes tenían experiencia como usuarios con distintos roles (compradores y vendedores) y algunos como desarrolladores de alguna aplicación del dominio. Para resolver algunas ambigüedades, se definió un sitio web específico del dominio de market-place para seguir su funcionalidad.

La System Usability Scale (SUS, escala de usabilidad de sistemas) se usó para evaluar los resultados del caso de estudio [5] [6] en términos de la aplicabilidad del enfoque propuesto. Aunque la SUS se usa principalmente para evaluar la usabilidad de sistemas de software, se demostró efectiva para evaluar productos y procesos [2].

La System Usability Scale (SUS) consiste en un cuestionario de 10 ítems; cada pregunta debe responderse en una escala de cinco opciones, que va de "1" ("Totalmente en desacuerdo") a "5" ("Totalmente de acuerdo"). Aunque hay 10 preguntas, están relacionadas de a pares, preguntando lo mismo pero desde un punto de vista complementario, para obtener un resultado de alta confianza.

El cálculo del puntaje SUS se realiza de la siguiente manera. Primero, los ítems 1, 3, 5, 7 y 9 se puntúan considerando el valor marcado menos 1. Luego, los ítems 2, 4, 6, 8 y 10 se puntúan considerando 5 menos el valor marcado. Después, los puntajes de cada participante se suman y se multiplican por 2,5 para obtener un nuevo valor que va de 0 a 100. Finalmente, se calcula el promedio. El enfoque puede tener uno de los siguientes resultados: "No aceptable" 0-64, "Aceptable" 65-84 y "Excelente" 85-100 [15]. El puntaje obtenido fue 71,07. Por lo tanto, el enfoque puede considerarse "aceptable".

## 6. Trabajos relacionados

Garner et al. [9] plantean lo importante que es la interacción humana, y asocian el compartir en actividades de resolución de problemas como el desarrollo de software. Así, nuestro enfoque propuesto descansa en una construcción colaborativa y una validación del conocimiento.

Giraldo et al. [10] proponen un enfoque para transformar modelos BPMN a un modelo con más precisión llamado CIAM. Enfatizan la importancia de capturar el conocimiento lo antes posible, por ejemplo en reuniones tempranas, como proponemos nosotros.

Vijayan et al. [26] coinciden en la importancia de elicitar el conocimiento del dominio y proponen una herramienta basada en StakeRare [14]. Como trabajan en una fase muy temprana, su método necesita como entrada una definición del alcance del sistema. Luego, construye una red de stakeholders basada en recomendaciones. Finalmente, elicita el conocimiento a partir de ellos. Es interesante la idea de construir la red usando una técnica de bola de nieve ("snowball rolling"). Nuestro enfoque propuesto no sugiere cómo involucrar a los stakeholders. Sin embargo, Meng et al. [16] describen sus hallazgos en la identificación de usuarios clave para extraer conocimiento en un entorno de crowdsourcing (colaboración abierta). Evalúan algunas características con las que coincidimos: el valor del conocimiento del usuario y la disposición a intercambiar conocimiento. Zhang et al. [28] realizaron una revisión bibliográfica sobre las características de los participantes para hacer la mejor selección de ellos. Coinciden con las características definidas por Meng et al. [16] y agregan más: interés, habilidades, expertise, voluntad de logro y reputación. Es una contribución muy interesante, aunque incrementaría el esfuerzo de aplicar nuestro enfoque si quisiéramos agregar algunas de ellas.

Unkelos et al. [24] proponen un proceso gamificado de requirements engineering colaborativa. En particular, desarrollaron una herramienta para dar soporte a su enfoque. Definieron tres roles que se relacionan con nuestros roles propuestos: el creador (es el experto en nuestro enfoque), el revisor (es el experto en nuestro enfoque, ya que revisa el conocimiento) y el consumidor (es el analista en nuestro enfoque, ya que va a consumir el conocimiento obtenido). También evalúan a los participantes, pero lo hacen con un objetivo distinto al de nuestra evaluación. Ellos evalúan a los participantes para fomentar y recompensar su participación, de acuerdo con la filosofía de las técnicas de gamificación. Kifetew et al. [13] también coinciden en la necesidad de gamificar las prácticas colaborativas de requerimientos. En particular, proponen una herramienta para priorizar requerimientos.

Nejad et al. [18] presentan un método colaborativo para la gestión de conocimiento en el diseño arquitectónico. Aunque el objetivo de su método es distinto al nuestro, las dos propuestas coinciden en recolectar, verificar y validar conocimiento de manera colaborativa. Usan un cómputo de "confianza" ("trust") con fines de validación. Gonçalves et al. [11] también coinciden con el método general y consideran además la importancia de las business rules para consolidar el conocimiento del dominio. Aunque nosotros usamos kernel sentences, algunos autores señalan sus similitudes [4]. Wen et al. [27] hacen una propuesta interesante de una plataforma para elicitar requerimientos definidos mediante 4 atributos: stakeholder, contexto, requerimientos funcionales y no funcionales. Es similar a nuestro enfoque el vínculo entre el stakeholder y los requerimientos funcionales. Y es interesante la definición del contexto. Creemos que puede ayudar a mejorar la descripción.

## 7. Conclusiones y trabajo futuro

Este paper propone un proceso para consolidar el conocimiento del dominio de la aplicación capturando, de manera colaborativa, kernel sentences directamente de los expertos. El proceso propuesto consiste en tres actividades: (i) especificación de kernel sentences, (ii) validación de kernel sentences, y (iii) evaluación de los expertos. Dos roles participan en este proceso: (i) los expertos, que describen y validan las kernel sentences, y (ii) los analistas, que realizan validaciones adicionales y toman la decisión final sobre las kernel sentences.

Aunque el proceso propuesto tiene el objetivo de consolidar el conocimiento del dominio, el proceso y las kernel sentences pueden considerarse un primer paso de una estrategia más grande para gestionar requerimientos. Las kernel sentences pueden usarse en artefactos más complejos de especificación de conocimiento, así como en requerimientos. Además, la evaluación de los participantes es útil para trazar un perfil de las personas involucradas y planificar etapas posteriores del proceso de requirements engineering.

Los resultados del caso de estudio son prometedores, aunque queda mucho trabajo por hacer. Es necesaria una implementación completa de la herramienta con una evaluación completa de ambos: la herramienta y el proceso. Además, deberían hacerse más experimentos sobre los rangos de valores y porcentajes, para obtener una definición precisa de los valores para aceptar o rechazar kernel sentences y definir el perfil de los participantes. También consideramos muy interesante incluir algún tipo de glosario u ontología en el enfoque, para lidiar con ambigüedades y dar una definición más precisa.

## Agradecimientos

Este paper está parcialmente financiado por el programa STIC AmSud, Proyecto 22STIC-01.

## Referencias

*(Se transcriben sin traducir, tal cual el archivo fuente.)*

1. Alexander, I. and Maiden, N.: Scenarios, Stories, Use Cases, through the system development life cycle, West Sussex: John Wiley & Sons, 2004.
2. Bangor, A., Kortum, P. T., Miller, J. T.: "An empirical evaluation of the system usability scale." Intl. Journal of Human–Computer Interaction 24.6, pp. 574-594, 2008.
3. Boehm, B.W.: Software Engineering, Computer society Press, IEEE, 1997.
4. Boyd, N. S.: "Using Natural Language in Software Development." In: Journal of Object-Oriented Programming - Report on Object Analysis and Design, 11-9, 1999 [link embebido en el PDF sobre esta referencia: http://www.educery.com/papers/rhetoric/road/]
5. Brooke, J.: "SUS-A quick and dirty usability scale" Usability evaluation in industry, 189(194), pp. 4-7, 1996.
6. Brooke, J: "SUS: a retrospective", Journal of usability studies 8.2, pp.29-40, 2013.
7. Brooks, F., The Mythical Man-Month: Essays on Software Engineering, Addison-Wesley Professional, 2 edition 1995.
8. Chomsky, N.: The Logical Structure of Linguistic Theory. Plenum Press, New York, 1975.
9. Garner, B. J.: "Collaborative knowledge management requirements for experiential learning (CKM)," Proceedings IEEE International Conference on Advanced Learning Technologies, doi: 10.1109/ICALT.2001.943989, pp. 488-489, 2001.
10. Giraldo, F., Alzate, A., Duarte, L., Tobón, M. and Hoyos, B.: "Deriving collaborative models from business process models," 2011 6th Colombian Computing Congress (CCC), doi: 10.1109/COLOMCC.2011.5936278, pp. 1-5, 2011.
11. Gonçalves, J. C. de A.R., Santoro, F. M. and Baião, F. A.: "Collaborative narratives for business rule elicitation," 2011 IEEE International Conference on Systems, Man, and Cybernetics, doi: 10.1109/ICSMC.2011.6083954, pp. 1926-1931, 2011.
12. Harris, Z. S.: Co-occurrence and transformation in linguistic structure. (Linguistic Society of America) pp. 390- 457, 1957.
13. Kifetew, F., Munante, D., Perini, A., Susi, A., Siena, A. and Busetta, P.: "DMGame: A Gamified Collaborative Requirements Prioritisation Tool," 2017 IEEE 25th International Requirements Engineering Conference (RE), doi: 10.1109/RE.2017.46, pp. 468-469, 2017.
14. Lim, S. L., Finkelstein, A.: "StakeRare: Using Social Networks and Collaborative Filtering for Large-Scale Requirements Elicitation", IEEE transactions on software engineering, Volume 38, Issue 3, May-Jun 2012, DOI 10.1109/TSE.2011.36 (link embebido: http://dx.doi.org/10.1109/TSE.2011.36), pp 707-735, 2012
15. McLellan, S., Muddimer, A., Peres, S. C.: "The effect of experience on System Usability Scale ratings." Journal of usability studies 7.2, pp. 56-67, 2012.
16. Meng, Q,. and Guo, X.: "Identification of key user knowledge source in crowdsourcing innovation mode," 2015 12th International Conference on Service Systems and Service Management (ICSSSM), doi: 10.1109/ICSSSM.2015.7170263, pp. 1-6, 2015.
17. Meservy, T. O., Zhang, C., Lee, E. T. and Dhaliwal, J.: "The Business Rules Approach and Its Effect on Software Testing," in IEEE Software, vol. 29, no. 4, doi: 10.1109/MS.2011.120, pp. 60-66, July-Aug, 2012.
18. Nejad, M. S., Moaven, S., Habibi, J. and Alidousti, R.: "Toward a collaborative method for knowledge management of software architectural decisions based on trust," 2015 12th International Conference on Fuzzy Systems and Knowledge Discovery (FSKD), doi: 10.1109/FSKD.2015.7382050, pp. 828-834, 2015.
19. PHP, https://www.php.net/, accessed: 2022-03-05
20. Potts, C.: "Using schematic scenarios to understand user needs," in Proceedings of the 1st conference on Designing interactive systems: processes, practices, methods, & techniques, 1995
21. Python, https://www.python.org/, accessed: 2022-03-05
22. Rose, S., Nagy, G.: Formulation: Document examples with Given/When/Then, Independently published, 979-8723395015, 2021.
23. Symfony, https://symfony.com/, accessed: 2022-03-05
24. Unkelos-Shpigel, N. and Hadar, I.: "Inviting everyone to play: Gamifying collaborative requirements engineering," 2015 IEEE Fifth International Workshop on Empirical Requirements Engineering (EmpiRE), doi: 10.1109/EmpiRE.2015.7431301, pp. 13-16, 2015.
25. Vasiliev, Y.: Natural Language Processing with Python and SpaCy: A Practical Introduction. No Starch Press, 2020.
26. Vijayan, J., Raju, G. and Joseph, M.: "Collaborative requirements elicitation using elicitation tool for small projects," 2016 International Conference on Signal Processing, Communication, Power and Embedded System (SCOPES), doi: 10.1109/SCOPES.2016.7955848, pp. 340-344, 2016.
27. Wen, B., Luo, Z. and Liang, P.: "Distributed and Collaborative Requirements Elicitation Based on Social Intelligence," 2012 Ninth Web Information Systems and Applications Conference, doi: 10.1109/WISA.2012.14, pp. 127-130, 2012.
28. Zhang, X., Gong, B., Ni, H., Liang, Z. and Su, J.: "Identifying Participants' Characteristics Influencing Participant Estimation in Knowledge-Intensive Crowdsourcing," 2019 8th International Conference on Industrial Technology and Management (ICITM), doi: 10.1109/ICITM.2019.8710681, pp. 358-363, 2019.

---

**FIN DE LA TRADUCCIÓN — Un enfoque colaborativo para especificar Kernel Sentences usando lenguaje natural**
