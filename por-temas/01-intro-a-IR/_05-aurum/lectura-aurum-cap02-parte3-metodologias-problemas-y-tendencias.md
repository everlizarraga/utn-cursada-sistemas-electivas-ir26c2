# Lectura en español — Metodologías, herramientas, problemas y tendencias de la elicitación

> **Qué es este archivo.** Parte 4 y última de la serie. Contiene las secciones 2.4 a 2.9 del capítulo 2 de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Didar Zowghi y Chad Coulin**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 3.** Se asume conocido el catálogo de veinte técnicas y las dos tablas de comparación.

---

## Qué queda por ver

Las tres partes anteriores cubrieron el qué y el cómo. Esta cubre cuatro cosas distintas:

1. **Metodologías** que integran la elicitación dentro de un marco más grande — acá aparecen el análisis estructurado, UML y los **casos de uso**.
2. **Herramientas** de software que dan soporte al proceso.
3. **Los problemas y trampas** más comunes, en siete categorías. Es la sección más útil de las cuatro.
4. **Tendencias, desafíos y direcciones futuras** — la parte más fechada del capítulo.

---

# 1. Elicitación basada en metodologías 🔴

Los enfoques dirigidos por metodologías y por modelos proveen **maneras de representar los procesos y sistemas existentes o futuros usando técnicas analíticas**, con la intención de investigar sus características y sus límites.

Las técnicas de modelado basadas en metas, escenarios y agentes —ya vistas en la Parte 3— también se usan para elicitación, además de los dos enfoques que siguen.

## 1.1 Análisis y Diseño Estructurado (SAD) 🟡

*(Del inglés* Structured Analysis and Design*.)*

Existe **desde mediados de la década de 1970** y fue ampliamente escrito, promovido y usado. El enfoque es **mayormente orientado a funciones** — piensa el sistema como un conjunto de funciones que transforman datos, no como un conjunto de objetos que colaboran.

Comprende una colección de técnicas:

| Técnica | Qué hace |
|---|---|
| **Diagramas de Flujo de Datos (DFD)** | Detallan la **descomposición funcional**, con énfasis en **los datos que entran y salen** del sistema y de los componentes relacionados |
| **Diagramas de Entidad-Relación (DER)** | Facilitan la representación de **las entidades del sistema, sus atributos y sus relaciones** entre sí |
| **Diccionarios de datos** | Otra técnica SAD usada durante la elicitación |
| **Listas de eventos** | Ídem |

## 1.2 Orientación a objetos y UML 🔴

Los enfoques **orientados a objetos**, y específicamente el **Lenguaje Unificado de Modelado (UML)**, contienen varias técnicas usadas a menudo para elicitación, con notaciones y formatos **establecidos pero flexibles**:

- **Diagramas de casos de uso**
- **Descripciones de casos de uso**
- **Diagramas de clases**

### Qué es un caso de uso, según este capítulo 🔴

Y acá viene la definición que más te conviene retener de todo el archivo:

> **Los casos de uso son esencialmente abstracciones de escenarios que describen el comportamiento funcional del sistema.**

Desarmemos esa frase, porque tiene tres piezas:

- **Abstracción** — no es un caso particular, es la forma general de una familia de casos particulares.
- **De escenarios** — el material del que están hechos es narrativo: secuencias de acciones e interacciones.
- **Que describen el comportamiento funcional** — lo que el sistema hace, visto desde afuera.

El capítulo agrega que **se volvieron especialmente aceptados** tanto en investigación como en práctica, **pese a sus deficiencias — como la imprecisión**.

**Por qué funcionan:** las representaciones **diagramáticas y tabulares** los hacen fáciles de entender y suficientemente flexibles para acomodar alguna información específica del contexto.

**Cuándo son especialmente efectivos:** en proyectos donde hay **alto nivel de incertidumbre**, o cuando **el analista no es experto en ese dominio particular**.

> ⚠️ **Cruce con la cátedra — el más directo de toda la serie.** La clase 02 es *"Casos de Uso: tipos de actores y relaciones"*, y la clase 11 del cronograma incluye explícitamente **"CU vs. Escenario"** como tema. La frase de arriba —los casos de uso son abstracciones de escenarios— es la respuesta corta a esa comparación, dicha por la literatura de referencia.
>
> Y hay una segunda lectura que vale oro. El capítulo admite que **la imprecisión es una deficiencia reconocida de los casos de uso**. Eso explica por qué Laura es innegociable con la notación UML y por qué corrige con el léxico de *no ambiguo*, *sin doble interpretación*, *verificable*: la herramienta tiene la imprecisión como debilidad estructural, y el rigor de notación y de redacción es lo único que la compensa. No es formalismo por formalismo.
>
> Cuidado con el alcance, igual: este capítulo te da el **qué es y por qué se usa**. Los **tipos de actores y las relaciones** —inclusión, extensión, generalización— se estudian del Fowler y de lo que dé la cátedra. Acá no están.

## 1.3 Metodologías que combinan técnicas 🟡

Se hicieron varios intentos de desarrollar metodologías que **combinan varias técnicas** con hojas de ruta y directrices de apoyo.

Un enfoque concreto de combinación que el capítulo describe propone esta secuencia:

```
   1. ESTUDIO ETNOGRÁFICO
      → descubrir los aspectos fundamentales de los
        patrones y comportamientos existentes
                    ↓
   2. ENTREVISTAS ESTRUCTURADAS
      → obtener percepción más profunda de las necesidades
        de los interesados y de las prioridades
                    ↓
   3. TÉCNICAS MÁS EXTENSIVAS
      → examinar en mayor detalle solo aquellas necesidades
        consideradas importantes
```

Fijate en la lógica del embudo: primero mirás sin preguntar, después preguntás con estructura, y recién al final gastás las técnicas caras **solo en lo que ya sabés que importa**.

## 1.4 Metodologías donde la elicitación está integrada 🟢

En otros ejemplos, la elicitación es una actividad definida pero **estrechamente integrada** dentro de otros aspectos del proceso de desarrollo:

| Metodología | Su foco |
|---|---|
| **Metodología de Sistemas Blandos (SSM)** | Aborda **problemas organizacionales y el cambio** |
| **Despliegue de la Función de Calidad (QFD)** | Se enfoca en lograr **satisfacción del cliente** mediante desarrollo basado en calidad |

Aparte, **Gause y Weinberg** desarrollaron una metodología **centrada en la elicitación** misma, que provee técnicas útiles y prácticas para el proceso, incluyendo conceptos como los **Puntos de Partida** (*Starting Points*) y las **Preguntas Libres de Contexto** (*Context-Free Questions*).

> 🕳️ **Preguntas libres de contexto.** Preguntas que se pueden hacer en cualquier proyecto porque no presuponen nada del dominio — del tipo "¿quién es el cliente de este sistema?", "¿qué pasa si esto no se construye?". Sirven para arrancar cuando todavía no sabés lo suficiente para formular preguntas específicas. Volvé al camino.

## 1.5 Métodos ágiles 🟡

Los métodos ágiles, en su mayor parte, **imponen muy poca elicitación por adelantado**. En cambio abogan por el **descubrimiento incremental e iterativo** a lo largo del ciclo de vida del desarrollo, e integrado con él.

Además de entrevistas y prototipos, soportan el uso de **Historias de Cliente o de Usuario**:

- Dan **descripciones básicas** de los procesos de negocio y de qué necesita hacer el sistema para soportarlos.
- Típicamente **las escribe el cliente en fichas** de cartulina.
- Se usan como **puntos de partida** del proceso de desarrollo.

Los requisitos adicionales que se elicitan como resultado del proceso —del cliente siempre presente— se agregan a un **Backlog de Producto**, que representa un **documento de requisitos vivo** consistente en características y funciones del sistema **priorizadas**.

> La expresión "documento de requisitos vivo" es la clave del contraste. En el enfoque tradicional el documento se escribe, se aprueba y se congela. Acá nunca se cierra: se reordena permanentemente.

---

# 2. Herramientas de soporte 🟢

Existe una amplia variedad de herramientas desarrolladas y usadas para dar soporte a la elicitación. Van:

- de **superficiales a profundas**, respecto del nivel de detalle y de formalidad;
- de **genéricas a específicas**, en propósito y operación.

Pueden dar soporte a una técnica o a un proceso específico, y tener niveles variables de **automatización y asistencia** de las tareas. Igual que con las técnicas, algunas se desarrollaron para otros propósitos y se aplicaron a esto, y otras se diseñaron específicamente.

**Definición de "herramienta" que usan los autores:** un implemento —software o artefacto— usado en la práctica para lograr algún acto, en este caso elicitar requisitos. Fijate que **incluye artefactos, no solo software**: una plantilla en papel es una herramienta.

### El veredicto general 🟡

> **En su mayor parte, el uso de herramientas para elicitación ha sido relativamente limitado**, y las aplicaciones más exitosas tendieron a ser específicas de un dominio o de un enfoque — con la excepción de las guías de proceso y las utilidades de prototipado.

### El catálogo

| Categoría | Ejemplos | Comentario del capítulo |
|---|---|---|
| **Plantillas** | **IEEE Std 830** (Especificación de Requisitos de Software), **Volere** | El **tipo más básico** de herramienta usada por los analistas |
| **Gestión de requisitos** | **DOORS**, **CaliberRM**, **RequisitePro** | Dan soporte **basado en formato** |
| **Modelado** | — | Muchos analistas las usan; típicamente con notación **gráfica o tabular fácil de usar** |
| **De enfoques específicos** | **Objectiver** (modelado por metas), **ART-SCENE** (elicitación por escenarios) | **La comunidad mainstream de ingeniería de software en gran medida no las adoptó** |
| **Con soporte cognitivo** al analista | **The Requirements Apprentice**, **ACME/PRIME**, **AbstFinder** | Pensadas para asistir el razonamiento del analista |
| **Soporte multimedia** para interesados distribuidos | **AMORE** | Responde al problema de los equipos repartidos geográficamente |
| **Groupware** | Foros de discusión, videoconferencia · software de mapas mentales y captura de ideas · entornos de colaboración virtual (**TeamWave**, **GroupSystems**) | Rango **muy amplio**: desde lo básico hasta entornos diseñados específicamente para sesiones grupales |

> ⚠️ **Cruce con la cátedra.** **IEEE 830** aparece acá como plantilla de especificación, y es contenido de la **unidad 7** del programa oficial de tu materia, junto con la norma ISO/IEC/IEEE 29148. Retené que su función es ser una plantilla — define **qué secciones tiene que tener** un documento de especificación de requisitos, no cómo elicitarlos.

---

# 3. Problemas y trampas de la elicitación 🔴

Esta es la sección más valiosa del cierre del capítulo. Los autores arrancan con una pregunta honesta: nunca hubo mucha duda sobre la complejidad y dificultad de la elicitación, **pero ¿por qué sigue siendo así hoy?**

Parte de la respuesta está en la **cantidad de problemas** que pueden tener que abordarse y superarse durante el proceso. En términos generales, hay un gran número de factores **contextuales, humanos, económicos y educativos** que afectan y pueden inhibir una elicitación efectiva.

Los autores categorizaron los problemas más frecuentes según el aspecto con el que más se relacionan. Los recolectaron de la literatura y de su propia experiencia y observación.

Son siete categorías.

## 3.1 Proceso y proyecto 🔴

Cada proyecto es único: **no hay dos situaciones de elicitación exactamente iguales**.

El proceso puede realizarse como parte de:

- un proyecto de desarrollo de software a medida,
- una actividad de selección de COTS,
- una definición de línea de producto,
- una operación de mantenimiento de un sistema existente.

Y los proyectos van desde **aplicaciones web simples a medida** hasta **líneas de producto de sistemas de información empresariales grandes y complejas**.

El entorno también varía mucho, incluyendo la **distribución geográfica de los interesados** y la **familiaridad de los usuarios con los sistemas de software**.

Además, el proceso es **inherentemente impreciso**, como resultado de tres cosas: los múltiples factores variables, el vasto abanico de opciones y decisiones, y su naturaleza comunicacional y socialmente rica.

**Y ahora el problema individual más importante de toda la sección:**

> **Discutiblemente, el problema más común de elicitación basado en proyecto es que el alcance inicial del proyecto no fue suficientemente definido**, y por lo tanto queda **abierto a interpretaciones y suposiciones**.

Por último: los proyectos, como todas las funciones de un negocio, están sujetos a cambio e influencia de factores internos o externos — **económicos, políticos, sociales, legales, financieros, psicológicos, históricos y geográficos**.

> ⚠️ **Cruce con la cátedra.** Alcance mal definido → interpretaciones y suposiciones → ambigüedad. Es la cadena causal completa detrás de lo que Laura penaliza. Cuando en un TP el enunciado no define el alcance con precisión, definirlo vos explícitamente —y declarar los supuestos que tomaste— no es rellenar: es atacar el problema número uno documentado de la disciplina.

## 3.2 Comunicación y entendimiento 🔴

Es común que **los interesados tengan dificultad para articular sus requisitos**. Las causas y variantes que enumera el capítulo:

- Analista e interesados **no comparten un entendimiento común de conceptos y términos**, o el analista **no está familiarizado con el problema**.
- Los interesados tienen **dificultad para ver formas nuevas de hacer las cosas**. Están anclados en el proceso que conocen.
- **No conocen las consecuencias de sus requisitos**, y por lo tanto pueden **no saber qué es factible o realista**.
- Pueden **entender muy bien el dominio del problema pero no estar familiarizados con las soluciones disponibles**, ni con las formas en que sus necesidades podrían satisfacerse.
- **A veces los interesados sugieren soluciones en vez de requisitos.**
- **Las cosas triviales o constantemente repetidas por los interesados suelen darse por supuestas y pasarse por alto**, aunque pueden no ser evidentes para el analista ni para los otros interesados.

> ⚠️ **Cruce con la cátedra.** Dos de estos merecen atención especial.
>
> **"Sugieren soluciones en vez de requisitos"** es el vicio clásico que vas a tener que detectar y corregir: cuando el interesado dice "necesito un botón que exporte a Excel", el requisito no es el botón — es que necesita llevarse los datos a otra herramienta. Confundir la solución propuesta con la necesidad real es cómo se construyen sistemas que hacen exactamente lo que se pidió y no sirven.
>
> **"Lo trivial se da por supuesto y se pasa por alto"** es el mismo fenómeno que en el análisis de protocolo (Parte 3): lo que se hace mil veces por día deja de percibirse como un paso. Es sistemático, no un descuido.

## 3.3 Calidad de los requisitos 🔴

Los requisitos elicitados pueden fallar de varias maneras:

- **No ser factibles, ni costo-efectivos, ni fáciles de validar.**
- Ser **vagos, carentes de especificidad, y no estar representados de manera que puedan medirse o probarse**.
- Estar definidos a **niveles de detalle diferentes e insuficientes** entre sí.
- Como el proceso de elicitación es **informal por naturaleza**, un conjunto de requisitos puede ser **incorrecto, incompleto, inconsistente y no claro para todos los interesados**.

### La paradoja de la volatilidad 🔴

Y después viene la observación más aguda de toda la sección. El contexto en que se elicitan los requisitos, y el proceso mismo, son **inherentemente volátiles**. A medida que el proyecto avanza y los interesados **se familiarizan más** con los dominios del problema y de la solución, las metas del sistema y los deseos de los usuarios **son susceptibles de cambiar**.

Conclusión de los autores:

> **De esta manera, el proceso de elicitación puede en realidad *causar* volatilidad de requisitos** — y por lo tanto afectar la calidad del conjunto de requisitos como un todo.

Leelo dos veces. Elicitar bien **hace que los requisitos cambien**, porque hacer pensar a la gente sobre su propio trabajo les cambia lo que quieren. El proceso genera parte del problema que intenta resolver. No es un fracaso del método: es una propiedad del método.

> ⚠️ **Cruce con la cátedra.** Esto justifica conceptualmente el modo de trabajo iterativo e incremental que declaró la cátedra: se rehace y se mejora sobre lo entregado, no se entrega una vez y se cierra. Si la elicitación genera volatilidad, un proceso de una sola pasada está garantizando quedarse con la versión más ignorante de los requisitos.

## 3.4 Interesados 🔴

- Los **conflictos entre interesados y entre sus requisitos son comunes y casi inevitables**.
- Los interesados **pueden no querer transigir ni priorizar** sus requisitos cuando esos conflictos ocurren.
- A veces **no saben realmente qué quieren** ni cuáles son sus necesidades reales, y por eso están limitados en su capacidad de apoyar la investigación de soluciones posibles.
- Pueden ser **adversos al cambio** que un sistema nuevo introduce, y tener por eso **niveles variables de compromiso y cooperación** hacia el proyecto.
- A menudo **no entienden ni valoran las necesidades de los otros interesados**, y pueden preocuparse solo por los factores que los afectan directamente.
- Como todos los humanos, **pueden cambiar de opinión** — de forma independiente, o **como resultado del propio proceso de elicitación**.

> Notá que el conflicto se presenta como **estructural, no como accidente**. Los interesados tienen intereses distintos; eso es lo que la palabra significa. Que aparezca conflicto no indica que la elicitación salió mal — indica que estás hablando con las personas correctas. Por eso el rol de mediador (Parte 2) es parte del oficio y no una contingencia.

## 3.5 Analista 🔴

Esta categoría es sobre las fallas del propio ingeniero de requisitos, y conviene leerla sin ponerse a la defensiva.

- Los analistas pueden **no estar equipados con suficiente pericia y experiencia** para preparar y realizar una elicitación efectiva — incluyendo la **selección apropiada de técnica** y la **identificación de todas las fuentes de requisitos**.
- Eso puede deberse a falta de formación en **la teoría** detrás de las técnicas y enfoques, o en **la práctica de las habilidades blandas**: **escuchar, comunicar y preguntar**.
- Los analistas con formación tradicional en ingeniería de software a veces **se enfocan en la solución y no en el problema**, y **se apoyan solo en las técnicas que ya conocen para todas las situaciones**.
- También ocurre que **muchos analistas no emplean ningún proceso estructurado ni riguroso** para abordar la elicitación dentro de los proyectos.

> ⚠️ **Cruce con la cátedra.** Escuchar, comunicar y preguntar aparecen acá listadas como **habilidades técnicas del oficio**, no como cualidades personales. Es la justificación de por qué la materia te evalúa en simulacros de entrevista, participación oral y minutas de reunión, y no solo en diagramas. Y el sesgo de "enfocarse en la solución y no en el problema" es el riesgo profesional específico del perfil que viene de programar: la cabeza salta a cómo construirlo antes de terminar de entender qué hay que construir.

## 3.6 Investigación 🟢

Problemas del campo académico, no de tu práctica, pero explican por qué la disciplina se ve como se ve:

- Es discutible que **muchas de las técnicas disponibles no son suficientemente útiles ni prácticas**, y que **la transferencia de conocimiento** requerida para introducirlas en la industria **es demasiado difícil**.
- La cantidad de **guías de proceso detalladas con soporte de herramientas apropiado es muy limitada**, especialmente en cuanto a la **selección de técnica** y al abordaje de los factores contextuales.
- Esto se atribuye en gran medida a la **ausencia de suficiente investigación empírica, casos de estudio y reportes de experiencia** sobre el tema específico de la elicitación.
- **No hay métricas acordadas** para medir el desempeño del proceso de elicitación dentro de un proyecto de desarrollo.

> Ese último punto es más grave de lo que parece. Si no hay métricas acordadas, no se puede demostrar que una técnica es mejor que otra — y sin esa demostración, la elección de técnica queda librada al criterio del analista. Que es exactamente lo que Hickey y Davis encontraron en la Parte 3.

## 3.7 Práctica 🟡

- Hay todavía **falta de suficiente conciencia, entendimiento y pericia** en la práctica de la elicitación.
- Existen **grandes brechas** entre la teoría y la práctica, **y entre analistas novatos y expertos**.
- El resultado: **muchos siguen cometiendo los mismos errores una y otra vez**, y **no reconocen los problemas reales ni sus efectos posteriores**.
- En muchos casos **las organizaciones y particularmente los clientes son resistentes a invertir el tiempo y el esfuerzo apropiados** en el proceso, pese a la necesidad creciente de que los proyectos salgan bien.

---

## Las siete categorías, de un vistazo 🔴

```
   PROCESO Y PROYECTO ──► alcance inicial mal definido
                          (el problema nº 1)

   COMUNICACIÓN ────────► no comparten vocabulario
                          proponen soluciones, no requisitos
                          lo trivial no se menciona

   CALIDAD ─────────────► vagos, no medibles, inconsistentes
                          + elicitar CAUSA volatilidad

   INTERESADOS ─────────► conflicto estructural
                          no saben qué quieren
                          cambian de opinión

   ANALISTA ────────────► no sabe elegir técnica
                          le faltan habilidades blandas
                          mira la solución, no el problema

   INVESTIGACIÓN ───────► sin métricas acordadas
                          poca evidencia empírica

   PRÁCTICA ────────────► brecha novato/experto
                          clientes que no quieren invertir
```

---

# 4. Tendencias y desafíos 🟢

Los autores dividen esta sección en cuatro, porque las tendencias de la investigación y las de la práctica **no son las mismas**.

## 4.1 Tendencias en la investigación

Cuando el campo de la IR empezó a desarrollarse, investigadores y profesionales identificaron que la elicitación tenía **características únicas y complicadas**, y que por lo tanto necesitaba abordarse como un tema **nuevo y separado de la adquisición de conocimiento** tradicional.

La evolución del foco, en tres tiempos:

```
   PRIMER MOMENTO          MEDIADOS-FINES DE LOS 90        RECIENTEMENTE
   ┌──────────────┐        ┌──────────────────────┐        ┌──────────────┐
   │ herramientas │        │ enfoques MANUALES    │        │ herramientas │
   │ y técnicas   │   →    │ estructurados y      │   →    │ otra vez —   │
   │ específicas  │        │ rigurosos, sobre     │        │ pero para    │
   │ para reducir │        │ paradigmas nuevos:   │        │ implementar  │
   │ complejidad  │        │ metas, escenarios,   │        │ esos enfoques│
   │              │        │ puntos de vista,     │        │ manuales     │
   │              │        │ conocimiento de      │        │              │
   │              │        │ dominio              │        │              │
   └──────────────┘        └──────────────────────┘        └──────────────┘
                            (se siguen usando hoy)
```

Esa vuelta a las herramientas incluye también **adaptar aplicaciones genéricas** a la elicitación: generación de documentación dirigida por plantillas, aplicaciones de groupware asistivo. Evolucionó así por la necesidad continua de mejora y por la complejidad persistente del proceso.

Además, se desarrollan enfoques nuevos para temas actuales y específicos: metodologías **orientadas a agentes y a aspectos**, **sistemas web**, **líneas de producto**. Y los **métodos ágiles** siguen ganando interés, con trabajo dirigido a investigar cómo implementar efectivamente la elicitación con ellos **manteniendo sus principios fundamentales**.

## 4.2 Tendencias en la práctica 🟡

Primera constatación, y es incómoda:

> **La IR no se practica universalmente como una fase distinta** del desarrollo de software.

Su adopción viene en aumento constante, particularmente durante la última década. Muchas organizaciones descubrieron que les conviene —a ellas y a sus clientes— invertir el tiempo y el esfuerzo requeridos, implementando un grado suficiente de estructura y rigor. **Pero eso vale, en su mayor parte, solo para las organizaciones más grandes y técnicamente maduras.**

Y sobre qué hacen realmente los analistas:

> **La mayoría de los analistas todavía usa técnicas genéricas y tradicionales** como entrevistas y reuniones grupales, y solo intenta usar otras con las que está familiarizado y cómodo, **sin importar las circunstancias**.

Es exactamente el hallazgo de Hickey y Davis de la Parte 3, confirmado desde otro ángulo.

Del lado positivo:

- Los enfoques **desarrollados específicamente para elicitación** —JAD, casos de uso, enfoques basados en metas y escenarios— **crecieron en popularidad y uso**, al menos entre profesionales experimentados.
- La adopción de métodos ágiles y de enfoques de modelado como **UML sigue creciendo**, con **aceptación generalizada de los diagramas y las descripciones de casos de uso**.
- El concepto de **"suficiente ingeniería de requisitos"** (*just enough RE*), propuesto por Davis, fue rápidamente aceptado por la industria. La expectativa de los autores es que lleve a adoptar una elicitación robusta **sin comprometerse innecesariamente con procesos caros y excesivamente detallados**.

## 4.3 Desafíos en la investigación 🟢

- El desafío clave sigue siendo **reducir la célebre brecha entre investigación y práctica** en cuanto a conciencia, aceptación y adopción. Solo se logra **estableciendo los resultados en la práctica** y haciendo los enfoques más atractivos, para dar la prueba y la motivación que los profesionales necesitan para usarlos.
- Para eso hay que **reducir la complejidad** de los enfoques y **la pericia requerida** para integrarlos. Empaquetarlos en **componentes manejables y flexibles** con soporte de herramientas apropiado facilita el proceso.
- Reducir la **brecha entre expertos y novatos** mediante hojas de ruta, marcos y directrices prácticas **que puedan enseñarse fácilmente a estudiantes y novatos**. Encontrar formas más eficientes de transferir conocimiento experto es parte del esfuerzo.
- **Los educadores necesitan abordar adecuadamente el amplio rango de habilidades y pericia requeridos** para producir ingenieros de requisitos efectivos, y **proveer ambientes de aprendizaje auténticos** para ganar experiencias realistas.

> ⚠️ **Cruce con la cátedra.** Ese último punto describe el diseño de tu materia: simulacros de entrevista, equipos con negocio asignado, TP integrador encadenado, rúbrica construida colaborativamente. Eso es "ambiente de aprendizaje auténtico". Saber que responde a un problema documentado de la disciplina —y no a un capricho del programa— ayuda a tomarse en serio las partes que parecen sobreactuadas.

## 4.4 Desafíos en la práctica 🟢

- La industria, como la academia, debe **reducir la brecha entre expertos y novatos**, invirtiendo en educación sobre lo que hay disponible y desarrollando procedimientos para la **transferencia de conocimiento de analistas senior a juniors**.
- **Saber cuándo y qué técnicas, enfoques y herramientas usar, combinado con el conocimiento de cómo**, va a mejorar las chances de satisfacción del cliente y de éxito del proyecto. *(Las tres preguntas: cuándo, cuál y cómo.)*
- Los profesionales necesitan poder **asignar tiempo y recursos suficientes** a la elicitación. Se logra en parte **educando a los clientes** sobre el valor de ser diligente en el proceso, y **presentándoles los riesgos de no serlo**.
- Es importante que **los propios interesados entiendan los beneficios** y estén comprometidos con el proceso.
- Las organizaciones necesitan estar **más abiertas a aceptar los resultados de la investigación**, y preparadas para unir fuerzas, juntar recursos y compartir información.
- La industria debería estar más preparada para abordar los **factores sociales y organizacionales**, y enfocarse en construir sistemas que **logren las metas del negocio y a la vez satisfagan las necesidades de los usuarios**, usando las técnicas apropiadas.

---

# 5. Direcciones futuras de la investigación 🟢

Pese a los éxitos y el progreso, quedan muchos temas abiertos: **asistencia específica para analistas novatos**, **soporte cognitivo mediante herramientas inteligentes**, y **métodos que involucren interacción directa con los interesados**.

Las áreas que los autores consideran que merecen atención:

1. **Reducir la brecha** entre teoría y práctica, y entre expertos y novatos.
2. **Aumentar la conciencia y la educación** de analistas e interesados en la industria.
3. **Desarrollar directrices para la selección de técnicas** y para gestionar el impacto de los factores contextuales sobre el proceso.
4. **Investigar formas de recolectar y reutilizar conocimiento** sobre elicitación.
5. **Integrar tecnologías nuevas** —arquitecturas web y basadas en agentes— en la próxima generación de herramientas de soporte.
6. **Producir y publicar casos de estudio y reportes de experiencia industrial** sobre cómo la elicitación contribuyó a los éxitos y fracasos de los proyectos.
7. **Explorar cómo se relaciona la elicitación con campos nuevos**: sistemas basados en agentes, metodologías ágiles, sistemas web.

Y el cierre de la sección, en tres frases que reparten responsabilidad:

- **Los estudiantes** necesitan que se les dé **experiencia práctica además de una base teórica sólida**.
- **Los profesionales** necesitan estar **equipados con variedad de técnicas, enfoques y herramientas** para usar según lo que mejor se adapte a la situación.
- **Los clientes** necesitan **entender la importancia del proceso, creer en él, y apoyar los esfuerzos** que implica hacerlo bien.

Los autores agregan que se requiere **más colaboración entre investigación y práctica**, y que muchos de los mejores resultados logrados hasta ahora vinieron de ese trabajo conjunto con la industria.

---

# 6. Resumen del capítulo 🔴

El resumen final de Zowghi y Coulin condensa todo el capítulo en cinco afirmaciones:

**1.** El proceso de elicitación —incluyendo **qué técnica, enfoque o herramienta usar**— **depende de un gran número de factores**: el tipo de sistema que se desarrolla, la etapa del proyecto y el dominio de aplicación, por nombrar solo algunos.

**2.** Por las **fortalezas y debilidades relativas** de los métodos disponibles y por el tipo de información que provee cada uno, la realidad es que **en casi todos los proyectos va a ser necesaria una combinación de varias técnicas distintas** para lograr un resultado exitoso. Esto se sostiene en el hecho de que muchas técnicas **están pensadas para usarse en conjunto** y tienen atributos complementarios.

**3.** **La mayoría de los enfoques requiere un nivel significativo de habilidad y pericia del analista** para usarse efectivamente.

**4.** Del rango de técnicas existentes, las que **siguen siendo las más ampliamente usadas y exitosas en la práctica** son variaciones de: **entrevistas**, **talleres grupales**, **observación**, **metas** y **escenarios**.

**5.** Y la frase con la que cierran el capítulo:

> **Pese a los intentos de automatizar partes del proceso y de desarrollar marcos y directrices, la elicitación de requisitos sigue siendo más un arte que una ciencia.**

---

## Preguntas para chequear que quedó

Sin respuestas — si alguna te traba, tirámela por chat.

1. ¿Qué es un caso de uso, según la definición de este capítulo? Desarmá la definición en sus tres partes.
2. ¿Cuál es la deficiencia reconocida de los casos de uso, y cómo se compensa?
3. ¿En qué dos situaciones son especialmente efectivos los casos de uso y los diagramas de clases?
4. ¿En qué se diferencia el enfoque de análisis estructurado del enfoque orientado a objetos, en cuanto a cómo piensa el sistema?
5. Describí la secuencia de tres pasos de la metodología que combina etnografía con entrevistas estructuradas. ¿Cuál es la lógica del orden?
6. ¿Qué es una historia de usuario y en qué se diferencia de un documento de requisitos tradicional?
7. ¿Por qué el uso de herramientas para elicitación ha sido, según el capítulo, relativamente limitado?
8. ¿Cuál es la función del IEEE 830 como herramienta? ¿Qué hace y qué no hace?
9. ¿Cuál es, según el capítulo, el problema de elicitación más común a nivel proyecto? ¿A qué da lugar?
10. Explicá el problema de que los interesados "sugieran soluciones en vez de requisitos". Dé un ejemplo propio.
11. ¿Por qué lo trivial y repetido tiende a no mencionarse? ¿Con qué límite del análisis de protocolo se conecta?
12. Explicá la paradoja de la volatilidad: ¿por qué el proceso de elicitación puede *causar* el problema que intenta resolver?
13. ¿Por qué el conflicto entre interesados se describe como estructural y no como accidente?
14. Nombrá las tres habilidades blandas que el capítulo lista como carencias formativas del analista. ¿Por qué son habilidades técnicas y no rasgos de personalidad?
15. ¿Cuál es el riesgo profesional específico de un analista con formación de programador?
16. ¿Por qué la ausencia de métricas acordadas es un problema grave para la disciplina? Conectalo con el hallazgo de Hickey y Davis.
17. ¿Qué técnicas usa realmente la mayoría de los analistas en la práctica, y por qué eso confirma un hallazgo anterior del capítulo?
18. ¿Qué propone el concepto de "suficiente ingeniería de requisitos"?
19. Según el resumen final, ¿cuáles son las cinco familias de técnicas más usadas y exitosas en la práctica?
20. ¿Qué quieren decir los autores con que la elicitación "sigue siendo más un arte que una ciencia"? ¿Es un elogio o una crítica?

---

**FIN DE LA PARTE 4 — Metodologías, herramientas, problemas y tendencias**

**FIN DE LA SERIE**

---

## Qué cubrió la serie completa

| | Contenido | Origen |
|---|---|---|
| **Parte 1** | Contexto de la IR: qué es un requisito, clasificaciones, proceso, stakeholders, tres niveles, gestión, evidencia empírica | Cap. 1 completo |
| **Parte 2** | Elicitación: definición, las cinco actividades del proceso, los cuatro roles del ingeniero de requisitos | Cap. 2, §2.1–2.2 |
| **Parte 3** | Catálogo de veinte técnicas + las dos tablas de comparación | Cap. 2, §2.3 |
| **Parte 4** | Metodologías (SAD, UML, casos de uso, ágil), herramientas, siete categorías de problemas, tendencias y cierre | Cap. 2, §2.4–2.9 |

**Lo que queda afuera del libro y hay que estudiar de la cátedra:** LEL, escenarios en la tradición de Leite y Doorn, tipos de actores y relaciones en UML, y todo lo específico de la notación.
