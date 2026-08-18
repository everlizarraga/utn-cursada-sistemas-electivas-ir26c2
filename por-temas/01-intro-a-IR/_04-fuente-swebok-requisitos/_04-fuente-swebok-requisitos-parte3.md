# SWEBOK Guide V3.0 — Capítulo 1: Requisitos de Software (Parte 3 de 4)

> Traducción al español, fiel y completa, de `04-SWEBOOK_v3_Chap1.pdf` (18 páginas). Esta parte cubre las páginas 1-10 a 1-14: tópico 5 (Especificación de requisitos), tópico 6 (Validación de requisitos), tópico 7 (Consideraciones prácticas) y tópico 8 (Herramientas de requisitos de software). Cierra el cuerpo del capítulo.

**Notas de conversión**

- **Es una traducción, no una transcripción.** Se tradujo la sintaxis al español natural, pero no se agregó, quitó, resumió ni reordenó contenido. Ante cualquier duda, prevalece el PDF original.
- **Capa de texto dañada en el original.** Reconstruida resolviendo los índices de glifo carácter por carácter, sin residuos. Detalle completo en la Parte 1.
- **Términos mantenidos en inglés:** *stakeholder*, *tradeoff*, *feature*, *top-down*, *bottom-up*, *start-up*. Se suman a los declarados en las Partes 1 y 2.
- **"Shall"** traducido uniformemente como **"deberá"** (convención IEEE 830 en español).
- **Errata del original, conservada.** En la sección 5.3, la lista de indicadores de calidad del documento completo de especificación se enumera como `"size, readability, specification, depth, and text structure"` — con una coma entre *specification* y *depth*. Verificado visualmente sobre la página rasterizada: la coma está en el original. Casi con seguridad debería leerse *"specification depth"* (profundidad de la especificación), que es el indicador reconocido en la literatura, con lo cual la lista tendría cuatro elementos y no cinco. Se tradujo **preservando la coma**; no se la corrigió.
- **Énfasis del original preservado** en la sección 7.1: el autor destaca en cursiva que una proporción significativa de los requisitos *va a* cambiar. La cursiva es del original.
- **Referencias entre corchetes** del tipo `[1*, c4s6]` se transcriben tal cual. Su clave completa está en la Parte 4.
- Esta parte no contiene figuras ni diagramas.
- El documento no contiene hipervínculos: se revisaron las anotaciones del PDF y no hay ninguno.

---

## 5. Especificación de requisitos

`[1*, c4s2, c4s3, c12s2–5] [2*, c10]`

Para la mayoría de las profesiones de ingeniería, el término "especificación" se refiere a la asignación de valores numéricos o límites a los objetivos de diseño de un producto. En ingeniería de software, "especificación de requisitos de software" típicamente se refiere a la producción de un documento que puede ser revisado, evaluado y aprobado sistemáticamente. Para sistemas complejos, particularmente aquellos que involucran componentes sustanciales que no son software, se producen hasta tres tipos distintos de documentos: definición del sistema, requisitos del sistema y requisitos de software. Para productos de software simples, solo se requiere el tercero de estos. Los tres documentos se describen aquí, entendiéndose que pueden combinarse según corresponda. Una descripción de la ingeniería de sistemas puede encontrarse en el capítulo Disciplinas relacionadas con la ingeniería de software de esta *Guía*.

### 5.1. Documento de definición del sistema

Este documento (a veces conocido como documento de requisitos de usuario o documento de concepto de operaciones) registra los requisitos del sistema. Define los requisitos de sistema de alto nivel desde la perspectiva del dominio. Entre sus lectores se cuentan representantes de los usuarios/clientes del sistema (marketing puede desempeñar estos roles en software orientado al mercado), de modo que su contenido debe estar formulado en los términos del dominio. El documento lista los requisitos del sistema junto con información de trasfondo sobre los objetivos generales del sistema, su entorno de destino y un enunciado de las restricciones, los supuestos y los requisitos no funcionales. Puede incluir modelos conceptuales diseñados para ilustrar el contexto del sistema, los escenarios de uso y las principales entidades del dominio, así como los flujos de trabajo.

### 5.2. Especificación de requisitos del sistema

Los desarrolladores de sistemas con componentes sustanciales de software y de no software —un avión de línea moderno, por ejemplo— a menudo separan la descripción de los requisitos del sistema de la descripción de los requisitos de software. Bajo esta visión, se especifican los requisitos del sistema, los requisitos de software se derivan de los requisitos del sistema, y luego se especifican los requisitos de los componentes de software. Estrictamente hablando, la especificación de requisitos del sistema es una actividad de ingeniería de sistemas y queda fuera del alcance de esta *Guía*.

### 5.3. Especificación de requisitos de software

La especificación de requisitos de software establece la base del acuerdo entre clientes y contratistas o proveedores (en proyectos orientados al mercado, estos roles pueden ser desempeñados por las divisiones de marketing y de desarrollo) sobre qué debe hacer el producto de software, así como sobre qué no se espera que haga.

La especificación de requisitos de software permite una evaluación rigurosa de los requisitos antes de que pueda comenzar el diseño, y reduce el rediseño posterior. También debería proporcionar una base realista para estimar costos, riesgos y cronogramas del producto.

Las organizaciones pueden usar además un documento de especificación de requisitos de software como base para desarrollar planes efectivos de verificación y validación.

La especificación de requisitos de software proporciona una base informada para transferir un producto de software a nuevos usuarios o a nuevas plataformas de software. Finalmente, puede proporcionar una base para la mejora del software.

Los requisitos de software a menudo se escriben en lenguaje natural, pero, en la especificación de requisitos de software, esto puede complementarse con descripciones formales o semiformales. La selección de notaciones apropiadas permite que ciertos requisitos y aspectos de la arquitectura del software se describan de manera más precisa y concisa que con lenguaje natural. La regla general es que deberían usarse notaciones que permitan describir los requisitos con la mayor precisión posible. Esto es particularmente crucial para software crítico para la seguridad, software regulatorio y ciertos otros tipos de software confiable. Sin embargo, la elección de la notación a menudo está restringida por la formación, las habilidades y las preferencias de los autores y lectores del documento.

Se han desarrollado varios indicadores de calidad que pueden usarse para relacionar la calidad de la especificación de requisitos de software con otras variables del proyecto, tales como costo, aceptación, rendimiento, cronograma y reproducibilidad. Los indicadores de calidad para las sentencias individuales de una especificación de requisitos de software incluyen imperativos, directivas, frases débiles, opciones y continuaciones. Los indicadores para el documento completo de especificación de requisitos de software incluyen tamaño, legibilidad, especificación, profundidad y estructura del texto.

---

## 6. Validación de requisitos

`[1*, c4s6] [2*, c13, c15]`

Los documentos de requisitos pueden estar sujetos a procedimientos de validación y verificación. Los requisitos pueden validarse para asegurar que el ingeniero de software ha entendido los requisitos; también es importante verificar que un documento de requisitos se ajuste a los estándares de la empresa y que sea comprensible, consistente y completo. En los casos en que los estándares o la terminología documentados de la empresa sean inconsistentes con estándares ampliamente aceptados, debería acordarse un mapeo entre ambos y anexarse al documento.

Las notaciones formales ofrecen la importante ventaja de permitir que las dos últimas propiedades sean demostradas (en un sentido restringido, al menos). Distintos stakeholders, incluyendo representantes del cliente y del desarrollador, deberían revisar el o los documentos. Los documentos de requisitos están sujetos a las mismas prácticas de gestión de la configuración que los demás entregables de los procesos del ciclo de vida del software. Cuando es practicable, los requisitos individuales también están sujetos a gestión de la configuración, generalmente usando una herramienta de gestión de requisitos (ver tópico 8, Herramientas de requisitos de software).

Es normal planificar explícitamente uno o más puntos del proceso de requisitos en los que los requisitos se validen. El objetivo es detectar cualquier problema antes de que se comprometan recursos para atender los requisitos. La validación de requisitos se ocupa del proceso de examinar el documento de requisitos para asegurar que define el software correcto (es decir, el software que los usuarios esperan).

### 6.1. Revisiones de requisitos

Quizás el medio de validación más común sea la inspección o revisión del o los documentos de requisitos. A un grupo de revisores se le asigna la consigna de buscar errores, supuestos equivocados, falta de claridad y desviaciones de la práctica estándar. La composición del grupo que conduce la revisión es importante (al menos un representante del cliente debería incluirse en un proyecto impulsado por el cliente, por ejemplo), y puede resultar de ayuda proveer orientación sobre qué buscar, en forma de listas de verificación.

Las revisiones pueden constituirse al completarse el documento de definición del sistema, el documento de especificación del sistema, el documento de especificación de requisitos de software, la especificación de línea base para una nueva versión, o en cualquier otro paso del proceso.

### 6.2. Prototipado

El prototipado es comúnmente un medio para validar la interpretación que el ingeniero de software hace de los requisitos de software, así como para elicitar requisitos nuevos. Al igual que con la elicitación, hay un abanico de técnicas de prototipado y varios puntos del proceso en los que la validación por prototipo puede resultar apropiada. La ventaja de los prototipos es que pueden facilitar la interpretación de los supuestos del ingeniero de software y, cuando hace falta, dar retroalimentación útil sobre por qué esos supuestos son incorrectos. Por ejemplo, el comportamiento dinámico de una interfaz de usuario puede entenderse mejor a través de un prototipo animado que mediante una descripción textual o modelos gráficos. La volatilidad de un requisito que se define después de haber hecho el prototipado es extremadamente baja, porque hay acuerdo entre el stakeholder y el ingeniero de software; por lo tanto, para *features* críticas para la seguridad y cruciales, el prototipado sería de gran ayuda. Sin embargo, también hay desventajas. Entre ellas, el peligro de que la atención de los usuarios se distraiga de la funcionalidad central subyacente por cuestiones cosméticas o problemas de calidad del prototipo. Por esta razón, algunos abogan por prototipos que eviten el software, como las maquetas hechas sobre rotafolios. Los prototipos pueden ser costosos de desarrollar. Sin embargo, si evitan el desperdicio de recursos causado por intentar satisfacer requisitos erróneos, su costo puede justificarse más fácilmente. Los prototipos tempranos pueden contener aspectos de la solución final. Los prototipos pueden ser evolutivos, en contraposición a descartables.

### 6.3. Validación de modelos

Típicamente es necesario validar la calidad de los modelos desarrollados durante el análisis. Por ejemplo, en los modelos de objetos, es útil realizar un análisis estático para verificar que existan caminos de comunicación entre objetos que, en el dominio de los stakeholders, intercambian datos. Si se usan notaciones de análisis formal, es posible usar razonamiento formal para demostrar propiedades de la especificación. Este tópico se relaciona estrechamente con la KA de Modelos y Métodos de Ingeniería de Software.

### 6.4. Pruebas de aceptación

Una propiedad esencial de un requisito de software es que debería ser posible validar que el producto terminado lo satisface. Los requisitos que no pueden validarse son en realidad apenas "deseos". Una tarea importante es, por lo tanto, planificar cómo verificar cada requisito. En la mayoría de los casos, esto se logra diseñando pruebas de aceptación para el modo en que los usuarios finales típicamente conducen sus actividades usando el sistema.

Identificar y diseñar pruebas de aceptación puede resultar difícil para los requisitos no funcionales (ver sección 1.3, *Requisitos funcionales y no funcionales*). Para ser validados, primero deben analizarse y descomponerse hasta el punto en que puedan expresarse cuantitativamente.

Puede encontrarse información adicional en Pruebas de aceptación/calificación/conformidad, en la KA de Pruebas de Software.

---

## 7. Consideraciones prácticas

`[1*, c4s1, c4s4, c4s6, c4s7] [2*, c3, c12, c14, c16, c18–21]`

El primer nivel de descomposición de tópicos presentado en esta KA puede dar la impresión de describir una secuencia lineal de actividades. Esta es una visión simplificada del proceso.

El proceso de requisitos abarca todo el ciclo de vida del software. La gestión de cambios y el mantenimiento de los requisitos en un estado que refleje con exactitud el software que se va a construir, o que ha sido construido, son clave para el éxito del proceso de ingeniería de software.

No toda organización tiene una cultura de documentar y gestionar requisitos. Es común, en empresas *start-up* dinámicas, impulsadas por una fuerte "visión de producto" y con recursos limitados, ver la documentación de requisitos como una sobrecarga innecesaria. Sin embargo, lo más frecuente es que, a medida que estas empresas se expanden, su base de clientes crece y su producto empieza a evolucionar, descubran que necesitan recuperar los requisitos que motivaron las *features* del producto para poder evaluar el impacto de los cambios propuestos. En consecuencia, la documentación de requisitos y la gestión de cambios son clave para el éxito de cualquier proceso de requisitos.

### 7.1. Naturaleza iterativa del proceso de requisitos

Hay una presión general en la industria del software por ciclos de desarrollo cada vez más cortos, y esto es particularmente pronunciado en sectores altamente competitivos y orientados al mercado. Más aún, la mayoría de los proyectos están restringidos de alguna manera por su entorno, y muchos son actualizaciones o revisiones de software existente, donde la arquitectura viene dada. En la práctica, entonces, casi siempre resulta impracticable implementar el proceso de requisitos como un proceso lineal y determinista en el que los requisitos de software se elicitan de los stakeholders, se fijan como línea base, se asignan y se entregan al equipo de desarrollo de software. Es ciertamente un mito que los requisitos de proyectos de software grandes lleguen alguna vez a entenderse perfectamente o a especificarse perfectamente.

En cambio, los requisitos típicamente iteran hacia un nivel de calidad y detalle que resulta suficiente para permitir que se tomen decisiones de diseño y de adquisición. En algunos proyectos, esto puede dar como resultado que los requisitos se fijen como línea base antes de que todas sus propiedades se comprendan por completo. Esto arriesga un retrabajo costoso si los problemas emergen tarde en el proceso de ingeniería de software. Sin embargo, los ingenieros de software están necesariamente restringidos por los planes de gestión del proyecto y deben, por lo tanto, tomar medidas para asegurar que la "calidad" de los requisitos sea tan alta como sea posible dados los recursos disponibles. Deberían, por ejemplo, explicitar cualquier supuesto que sustente los requisitos, así como cualquier problema conocido.

Para productos de software que se desarrollan iterativamente, un equipo de proyecto puede fijar como línea base solo aquellos requisitos necesarios para la iteración actual. El especialista en requisitos puede continuar desarrollando requisitos para iteraciones futuras, mientras los desarrolladores avanzan con el diseño y la construcción de la iteración actual. Este enfoque les proporciona a los clientes valor de negocio rápidamente, minimizando al mismo tiempo el costo del retrabajo.

En casi todos los casos, la comprensión de los requisitos continúa evolucionando a medida que avanzan el diseño y el desarrollo. Esto a menudo conduce a la revisión de requisitos tarde en el ciclo de vida. Quizás el punto más crucial para entender los requisitos de software sea que una proporción significativa de los requisitos *va a* cambiar. Esto se debe a veces a errores en el análisis, pero frecuentemente es una consecuencia inevitable del cambio en el "entorno": por ejemplo, el entorno operativo o de negocio del cliente, los procesos regulatorios impuestos por las autoridades, o el mercado en el que el software debe venderse. Cualquiera sea la causa, es importante reconocer la inevitabilidad del cambio y tomar medidas para mitigar sus efectos. El cambio tiene que gestionarse asegurando que los cambios propuestos pasen por un proceso definido de revisión y aprobación, y aplicando trazabilidad cuidadosa de requisitos, análisis de impacto y gestión de la configuración del software (ver la KA de Gestión de la Configuración del Software). En consecuencia, el proceso de requisitos no es meramente una tarea de arranque en el desarrollo de software, sino que abarca todo el ciclo de vida del software. En un proyecto típico, las actividades de requisitos de software evolucionan con el tiempo desde la elicitación hasta la gestión de cambios. Una combinación de métodos *top-down* de análisis y diseño con métodos *bottom-up* de implementación y refactorización, que se encuentren en el medio, podría brindar lo mejor de ambos mundos. Sin embargo, esto es difícil de lograr en la práctica, ya que depende fuertemente de la madurez y la experiencia de los ingenieros de software.

### 7.2. Gestión de cambios

La gestión de cambios es central para la gestión de requisitos. Este tópico describe el rol de la gestión de cambios, los procedimientos que hace falta tener establecidos y el análisis que debería aplicarse a los cambios propuestos. Tiene vínculos fuertes con la KA de Gestión de la Configuración del Software.

### 7.3. Atributos de requisitos

Los requisitos deberían consistir no solo en una especificación de lo que se requiere, sino también en información auxiliar que ayude a gestionar e interpretar los requisitos. Los atributos de requisitos deben ser definidos, registrados y actualizados a medida que evoluciona el software en desarrollo o en mantenimiento. Esto debería incluir las diversas dimensiones de clasificación del requisito (ver sección 4.1, Clasificación de requisitos) y el método de verificación o la sección correspondiente del plan de pruebas de aceptación. Puede incluir además información adicional, como una justificación resumida de cada requisito, la fuente de cada requisito y un historial de cambios. El atributo de requisitos más importante, sin embargo, es un identificador que permita que los requisitos sean identificados de manera única e inequívoca.

### 7.4. Trazabilidad de requisitos

La trazabilidad de requisitos se ocupa de recuperar el origen de los requisitos y de predecir los efectos de los requisitos. La trazabilidad es fundamental para realizar el análisis de impacto cuando los requisitos cambian. Un requisito debería ser trazable hacia atrás hasta los requisitos y stakeholders que lo motivaron (por ejemplo, desde un requisito de software hacia el o los requisitos de sistema que ayuda a satisfacer). A la inversa, un requisito debería ser trazable hacia adelante hasta los requisitos y las entidades de diseño que lo satisfacen (por ejemplo, desde un requisito de sistema hacia los requisitos de software que se han elaborado a partir de él, y de ahí hacia los módulos de código que lo implementan, o los casos de prueba relacionados con ese código, e incluso una sección determinada del manual de usuario que describe la funcionalidad efectiva) y hasta el caso de prueba que lo verifica.

La trazabilidad de requisitos de un proyecto típico formará un grafo dirigido acíclico (DAG) complejo de requisitos (ver Grafos, en la KA de Fundamentos de Computación). Mantener actualizado ese grafo o matriz de trazabilidad es una actividad que debe considerarse durante todo el ciclo de vida de un producto. Si la información de trazabilidad no se actualiza a medida que los cambios en los requisitos siguen ocurriendo, la información de trazabilidad se vuelve poco confiable para el análisis de impacto.

### 7.5. Medición de requisitos

Como cuestión práctica, típicamente resulta útil tener alguna noción del "volumen" de los requisitos de un producto de software determinado. Este número es útil para evaluar el "tamaño" de un cambio en los requisitos, para estimar el costo de una tarea de desarrollo o de mantenimiento, o simplemente para usarlo como denominador en otras mediciones. La medición del tamaño funcional (FSM) es una técnica para evaluar el tamaño de un cuerpo de requisitos funcionales.

Puede encontrarse información adicional sobre medición de tamaño y estándares en la KA de Proceso de Ingeniería de Software.

---

## 8. Herramientas de requisitos de software

Las herramientas para tratar con requisitos de software caen, a grandes rasgos, en dos categorías: herramientas para modelar y herramientas para gestionar requisitos.

Las herramientas de gestión de requisitos típicamente dan soporte a un abanico de actividades —incluyendo documentación, trazabilidad y gestión de cambios— y han tenido un impacto significativo sobre la práctica. De hecho, la trazabilidad y la gestión de cambios son realmente practicables solo si están soportadas por una herramienta. Dado que la gestión de requisitos es fundamental para una buena práctica de requisitos, muchas organizaciones han invertido en herramientas de gestión de requisitos, aunque muchas más gestionan sus requisitos de maneras más ad hoc y, en general, menos satisfactorias (por ejemplo, usando planillas de cálculo).

---

*Continúa en la Parte 4: matriz de tópicos contra material de referencia, lecturas recomendadas y referencias.*

**FIN DEL ARCHIVO FUENTE — SWEBOK Guide V3.0, Capítulo 1: Requisitos de Software (Parte 3 de 4)**
