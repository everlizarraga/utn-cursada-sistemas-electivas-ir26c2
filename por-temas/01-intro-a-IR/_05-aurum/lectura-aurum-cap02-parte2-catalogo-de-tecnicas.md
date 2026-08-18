# Lectura en español — Catálogo de técnicas y enfoques de elicitación

> **Qué es este archivo.** Parte 3 de la serie. Contiene la sección 2.3 completa del capítulo 2 de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005) — el catálogo de veinte técnicas de elicitación más las dos tablas de comparación que cierran la sección. Capítulo de **Didar Zowghi y Chad Coulin**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 2.** Se asume que ya sabés qué es elicitar, cuáles son las cinco actividades del proceso y cuáles los roles del ingeniero de requisitos.

---

## Cómo leer este archivo

Son veinte técnicas. El libro las presenta en una lista corrida; acá están en el mismo orden pero agrupadas en seis familias, porque veinte ítems planos no se retienen. La agrupación es mía, el orden y el contenido son del libro.

De cada técnica te vas a llevar tres cosas, que es lo que el capítulo da: **qué es**, **cuándo conviene** y **qué la limita**. Esa tercera parte es la más valiosa y la que menos se estudia.

Al final están las dos tablas de los autores: una que cruza técnicas contra actividades, y otra que dice cuáles se combinan entre sí y cuáles son intercambiables.

---

## Preámbulo: técnica no es lo mismo que enfoque 🔴

Desde hace más de dos décadas, buena parte de la investigación y de la práctica en IR apunta a mejorar la elicitación mediante la aplicación y el desarrollo de técnicas, enfoques y herramientas. Muchos de esos métodos **fueron tomados prestados y adaptados de otras disciplinas** —las ciencias sociales, sobre todo—, y solo unos pocos se desarrollaron específicamente para elicitar requisitos de software.

Los autores se detienen a definir dos palabras, porque en la práctica se usan de maneras distintas y en la literatura hay definiciones múltiples:

| Término | Definición |
|---|---|
| **Técnica** | Una **manera de hacer algo**, o un método práctico aplicado a alguna tarea particular |
| **Enfoque** | Una **disposición sistemática, usualmente en pasos**, de ideas o acciones destinadas a tratar un problema o una situación |

La diferencia práctica: una técnica es una herramienta, un enfoque es una **secuencia organizada** que puede usar varias herramientas. La entrevista es una técnica. El modelado basado en metas es un enfoque.

Y una advertencia de escala: **hay literalmente cientos** de técnicas y enfoques distintos, de fuentes muy variadas, que se pueden usar y se han usado para elicitación. Lo que sigue son solo los más usados. Los autores aclaran que la selección **no es exhaustiva**, pero sí representativa del rango descrito en la literatura y practicado en la industria.

---

# FAMILIA 1 — Técnicas conversacionales

## 1. Entrevistas 🔴

Son **probablemente la técnica más tradicional y más comúnmente usada** para elicitar requisitos.

Como son en esencia actividades sociales entre personas, resultan **inherentemente informales**, y su efectividad depende en gran medida de la **calidad de la interacción** entre los participantes.

**A favor:** proveen una manera eficiente de recolectar **grandes cantidades de datos rápidamente**.

**En contra:** los resultados —por ejemplo, cuán útil resulta la información obtenida— **pueden variar significativamente según la habilidad del entrevistador**. La técnica no compensa al que la ejecuta mal.

### Los tres tipos 🔴

Hay fundamentalmente tres tipos de entrevista: **no estructurada**, **estructurada** y **semiestructurada** — esta última siendo generalmente una combinación de las dos primeras.

**Entrevista no estructurada.** Es de naturaleza conversacional: el entrevistador ejerce **solo un control limitado** sobre la dirección de la discusión. Como no sigue una agenda predeterminada ni una lista de preguntas, aparecen dos riesgos concretos:

- que algunos temas queden **completamente desatendidos**;
- que se ponga **demasiado detalle en algunas áreas y no suficiente en otras** — problema común y documentado de este formato.

**Cuándo conviene:** para **exploración**, cuando el entendimiento del dominio es limitado; o como **precursora** de entrevistas estructuradas más enfocadas y detalladas.

**Entrevista estructurada.** Se conduce usando un **conjunto predeterminado de preguntas** para reunir información específica.

Su éxito depende de saber tres cosas: **cuáles son las preguntas correctas**, **cuándo hacerlas** y **quién debería responderlas**. Existen plantillas que dan guía sobre entrevistas estructuradas para elicitación —el capítulo menciona **Volere**— que pueden usarse para apoyar la técnica.

**Cuándo conviene:** cuando ya sabés qué buscar. **Su límite:** tienden a **limitar la investigación de ideas nuevas** — no hay lugar para lo que no anticipaste. A cambio, se las considera generalmente **rigurosas y efectivas**.

```
   NO ESTRUCTURADA          SEMIESTRUCTURADA         ESTRUCTURADA
   ┌──────────────┐         ┌──────────────┐        ┌──────────────┐
   │ conversación │         │  combinación │        │ cuestionario │
   │ libre        │         │  de ambas    │        │ predefinido  │
   ├──────────────┤         ├──────────────┤        ├──────────────┤
   │ + descubre   │         │              │        │ + rigurosa   │
   │   lo que no  │         │              │        │ + efectiva   │
   │   esperabas  │         │              │        │ − no descubre│
   │ − deja temas │         │              │        │   lo nuevo   │
   │   afuera     │         │              │        │              │
   └──────────────┘         └──────────────┘        └──────────────┘
        EXPLORAR                                       PROFUNDIZAR
        (primero)                                       (después)
```

> ⚠️ **Cruce con la cátedra.** La clase 04 se titula *"Entrevistas y cuestionarios: pros y contras. Simulacro de entrevista"*, y el TP integrador arranca con el diseño de una entrevista (entregable de la clase 04). Este bloque **es** los pros y contras, con la ventaja de que el capítulo da el criterio de *cuándo* usar cada tipo, no solo la lista. La secuencia no estructurada → estructurada es una respuesta defendible si te preguntan cómo diseñarías el proceso de elicitación de un caso.

## 2. Cuestionarios 🔴

Se usan principalmente en las **etapas tempranas** de la elicitación, y pueden constar de preguntas **abiertas, cerradas, o ambas**.

**Condición para que sirvan:** los términos, los conceptos y **los límites del dominio** tienen que estar bien establecidos y ser bien entendidos, tanto por los participantes como por quien diseña el cuestionario. Las preguntas deben estar **enfocadas**, para evitar juntar grandes cantidades de información redundante e irrelevante.

**A favor:** manera eficiente de recolectar información de **múltiples interesados, rápido**.

**En contra** — y acá el capítulo es duro, porque son tres límites encadenados:

1. Están **limitados en la profundidad** del conocimiento que pueden elicitar.
2. **No hay oportunidad de ahondar** en un tema ni de expandir sobre ideas nuevas.
3. Del mismo modo, **no proveen mecanismo alguno** para que los participantes **pidan aclaraciones o corrijan malentendidos**.

Ese tercer punto es el más serio, y conecta directo con la brecha cultural de la Parte 2: si el que responde entendió mal la pregunta, nadie se entera nunca.

**Veredicto de los autores:** generalmente se consideran **más útiles como listas de verificación informales**, para asegurar que los elementos fundamentales se aborden temprano y para establecer la base de las actividades de elicitación posteriores.

> Es decir: el cuestionario no es la técnica que produce los requisitos. Es la que se asegura de que no te olvidaste de preguntar por algo grande antes de empezar en serio.

> ⚠️ **Cruce con la cátedra.** El cuestionario es entregable de la clase 06. Y ojo con la condición de entrada: para que un cuestionario sirva, **el vocabulario del dominio ya tiene que estar establecido**. Un cuestionario prematuro produce respuestas a preguntas que el que responde entendió a su manera.

---

# FAMILIA 2 — Técnicas analíticas y de documentos

## 3. Análisis de tareas 🟡

Emplea un **enfoque descendente**: las tareas de alto nivel se descomponen en subtareas, y estas eventualmente en secuencias detalladas, hasta que todas las acciones y eventos quedan descritos.

**Objetivos primarios:**

- Construir una **jerarquía de las tareas** que realizan los usuarios y el sistema.
- Determinar **el conocimiento que se usa o se requiere** para llevarlas a cabo.

**Qué aporta:** información sobre las interacciones tanto del usuario como del sistema respecto de las tareas, más una **descripción contextual** de las actividades que ocurren.

**Su costo:** en la mayoría de los casos se requiere **esfuerzo considerable** para hacer un análisis de tareas exhaustivo. Por eso es importante establecer **qué nivel de detalle hace falta** y **cuándo un componente de la tarea necesita explorarse más a fondo**. Sin ese corte, la descomposición no termina nunca.

## 4. Análisis del dominio 🔴

Examinar la documentación y las aplicaciones existentes y relacionadas es una manera **muy útil** de reunir requisitos tempranos, entender y capturar conocimiento del dominio, e identificar conceptos y componentes reutilizables.

**Cuándo es particularmente importante:** cuando el proyecto implica **reemplazar o mejorar un sistema heredado**.

**Qué documentación sirve:**

- documentos de diseño y manuales de instrucciones de los sistemas existentes;
- **formularios en papel y archivos** usados en los procesos de negocio actuales.

Los estudios de aplicaciones suelen incluir además mirar los **sistemas aguas arriba y aguas abajo** —los que alimentan al nuestro y los que se alimentan de él— así como **soluciones competidoras o similares**.

**Casi nunca va solo:** en la mayoría de los casos estos estudios involucran otras técnicas, como observar el sistema existente en uso y entrevistar a los usuarios actuales.

### Por qué el conocimiento del dominio pesa tanto 🔴

El capítulo le dedica un párrafo aparte. El conocimiento de dominio, en forma de **descripciones detalladas y ejemplos**, juega un papel importante en el proceso de elicitación. Los enfoques basados en este tipo de información **se usan a menudo junto con otras técnicas, y como insumo de ellas**. Ejemplos concretos que da:

- Los analistas usan **experiencia previa en dominios similares** como plantilla de discusión para facilitar trabajo grupal y conducir entrevistas.
- Las **analogías y abstracciones** de dominios de problema existentes sirven como línea de base para adquirir información específica y detallada, identificar y describir sistemas solución posibles, y **ayudar a crear un entendimiento común entre el analista y los interesados**.
- Estos enfoques también dan la oportunidad de **reutilizar especificaciones** y de **validar requisitos nuevos** contra otras instancias del dominio.

Menciona además los **Marcos de Problema** (*Problem Frames*), que proveen un método para examinar problemas en detalle e identificar patrones que puedan dar pistas hacia soluciones potenciales.

> ⚠️ **Cruce con la cátedra.** Retené el último ítem del primer bloque: crear **entendimiento común entre analista e interesados**. Esa es, otra vez, la respuesta a la brecha cultural. Y para el TP integrador —donde el negocio te lo asigna la cátedra y probablemente no lo conozcas— el análisis del dominio es la técnica de arranque casi obligada: es lo que hacés antes de tener a quién entrevistar.

## 5. Introspección 🔴

Requiere que el analista **desarrolle requisitos a partir de lo que él o ella cree** que los usuarios y otros interesados quieren y necesitan del sistema.

Y acá el capítulo dice algo incómodo: **pese a ser empleada en alguna medida por la mayoría de los analistas**, esta técnica se usa principalmente **solo como punto de partida** para otros esfuerzos de elicitación.

**Cuándo es realmente efectiva:** solo cuando el analista no solo está muy familiarizado con el dominio y con las metas del sistema, sino que además es **experto en los procesos de negocio** que realizan los usuarios. Dos condiciones, no una.

**Qué hacer cuando no queda otra:** en casos donde el analista se ve forzado a apoyarse más en ella —por ejemplo, cuando **los usuarios tienen poca o ninguna experiencia previa con sistemas de software** en su ambiente de trabajo— debería producirse una especie de **introspección facilitada**, mediada por otras técnicas como entrevistas y análisis de protocolo.

> ⚠️ **Cruce con la cátedra.** Esta es la técnica más peligrosa del catálogo y la que más te conviene tener identificada, porque **es la que todos usan sin darse cuenta**. Cuando un equipo se sienta a "pensar los requisitos" del sistema asignado sin haber hablado con nadie ni haber analizado el dominio, está haciendo introspección pura — y el capítulo dice que eso solo se sostiene si sos experto en el negocio. En un TP, presentar requisitos introspectivos como si fueran elicitados es exactamente lo que una corrección con criterio va a marcar.

---

# FAMILIA 3 — Técnicas de estructuración del conocimiento

Las tres que siguen vienen de la ingeniería del conocimiento y comparten un objetivo: **no obtener requisitos directamente, sino ordenar y clarificar** cómo el interesado entiende su propio dominio.

## 6. Grillas de repertorio 🟢

Consisten en pedirle a los interesados que **desarrollen atributos y asignen valores** a un conjunto de entidades del dominio.

**Resultado:** el sistema queda modelado en forma de **matriz** — categorizando los elementos del sistema, detallando las instancias de esas categorías, y asignando variables con sus valores correspondientes a cada una.

**Objetivo:** identificar y representar **las similitudes y las diferencias** entre las distintas entidades del dominio.

**Su límite principal es de público:** estas matrices representan **un nivel de abstracción que a la mayoría de los usuarios le resulta ajeno**. Por eso la técnica se usa típicamente para elicitar **de expertos del dominio**, no de usuarios comunes.

**Segundo límite:** aunque es más detallada que la clasificación de tarjetas, y en menor grado que el escalamiento, las grillas de repertorio están **algo limitadas en su capacidad de expresar características específicas de requisitos complejos**.

## 7. Clasificación de tarjetas 🟡

Requiere que los interesados **ordenen en grupos una serie de tarjetas** que contienen los nombres de las entidades del dominio, **según su propio entendimiento**.

Y —esto es lo importante— se le requiere además al interesado que **explique la justificación** del modo en que ordenó las tarjetas. El agrupamiento es el dato visible; **el razonamiento detrás es el dato valioso**.

**Condición para que funcione:** que **todas las entidades estén incluidas** en el proceso. Eso solo es posible si el dominio ya es suficientemente entendido por el analista y por los participantes. Si el dominio todavía no está establecido, **se puede usar trabajo grupal para identificar primero esas entidades**.

**Una derivación conocida:** las tarjetas **CRC** (*Class Responsibility Collaboration*), que también se usan para determinar clases de programa en el código. En esa variante las tarjetas sirven para **asignar responsabilidades** a usuarios y a componentes del sistema.

**Su límite:** como las entidades representan un nivel de abstracción tan alto del sistema, la información que se obtiene **está limitada en su nivel de detalle**.

> ⚠️ **Cruce con la cátedra.** Pedir la justificación del agrupamiento es la misma lógica que la regla del café con leche: primero las piezas sueltas, después el criterio con el que se juntan — y el criterio queda explícito y discutible, no implícito.

## 8. Escalamiento 🟢

*(En inglés,* laddering *— "hacer escalera". No hay traducción asentada al español.)*

A los interesados se les hace una serie de **preguntas breves de sondeo**, llamadas *probes*, y se les pide que **acomoden las respuestas resultantes en una estructura organizada**.

**Supuesto de base —y es un supuesto fuerte:** que el conocimiento a elicitar **efectivamente puede acomodarse de forma jerárquica**. Si el conocimiento del dominio no es jerárquico, la técnica fuerza una forma que no le corresponde.

**Condición para que sea efectiva:** que los interesados sean capaces de **expresar su entendimiento del dominio y luego acomodarlo de manera lógica**. No todo el mundo puede hacer eso sobre su propio trabajo.

**Cómo se maneja:** el conocimiento resultante, que suele mostrarse con **diagramas de árbol**, se **revisa y modifica dinámicamente** a medida que se agrega más.

**Para qué se usa, igual que la clasificación de tarjetas:** principalmente para **clarificar requisitos y categorizar entidades** del dominio.

---

# FAMILIA 4 — Técnicas grupales

## 9. Trabajo grupal 🔴

El trabajo grupal —reuniones colaborativas, por ejemplo— es una técnica **muy común y a menudo la técnica por defecto** para elicitar requisitos.

**Por qué es efectiva:** porque **involucra y compromete a los interesados directamente**, y **promueve la cooperación**.

**Sus dificultades**, y son varias:

- **Organizarlas puede ser difícil**, por la cantidad de interesados distintos que puede haber en el proyecto.
- **Gestionarlas efectivamente requiere pericia y experiencia**, para asegurar que las personalidades individuales **no dominen la discusión**.
- Los factores clave del éxito son **la composición de los participantes** y **la cohesión dentro del grupo**.

Y una condición que conviene subrayar: los interesados **deben sentirse cómodos y confiados para hablar abierta y honestamente**. De ahí se sigue la advertencia más filosa de la sección:

> **El trabajo grupal es menos efectivo en situaciones altamente politizadas.**

Si la gente tiene algo que perder por lo que dice delante de quien lo dice, la reunión produce discurso, no requisitos.

## 10. Tormenta de ideas 🔴

Es un proceso donde participantes de **distintos grupos de interesados** entablan una **discusión informal** para generar rápidamente **tantas ideas como sea posible**, sin enfocarse en ninguna en particular.

**Reglas de conducción** que el capítulo remarca:

- Es importante **evitar explorar o criticar las ideas con gran detalle**.
- **No suele ser el propósito** de una sesión de tormenta de ideas **resolver cuestiones mayores ni tomar decisiones clave**.

**Uso típico:** desarrollar la **declaración de misión preliminar** del proyecto y del sistema objetivo — justo el artefacto con el que, según la Parte 2, arranca todo el proceso.

**Su ventaja:** promueve el **pensamiento y la expresión libres**, y permite el descubrimiento de **soluciones nuevas e innovadoras** a problemas existentes.

## 11. Desarrollo Conjunto de Aplicaciones (JAD) 🟡

*(Del inglés* Joint Application Development*.)*

Involucra a **todos los interesados disponibles** investigando, mediante discusión general, tanto **los problemas a resolver** como **las soluciones disponibles** para esos problemas.

**Su ventaja estructural:** con todas las partes representadas, **las decisiones pueden tomarse rápido y las cuestiones resolverse rápido**. No hay que ir y volver entre grupos.

**Las dos diferencias con la tormenta de ideas** —y el capítulo las marca explícitamente:

1. En JAD, **las metas principales del sistema ya fueron establecidas** antes de que los interesados participen.
2. Las sesiones JAD son típicamente **bien estructuradas**, con pasos, acciones y roles definidos para los participantes — incluyendo un **facilitador especialista**.

**Su foco:** tiende a estar en **las necesidades y los deseos del negocio y de los usuarios**, más que en cuestiones técnicas.

```
   TORMENTA DE IDEAS              JAD
   ┌────────────────────┐    ┌────────────────────┐
   │ metas TODAVÍA NO   │    │ metas YA           │
   │ establecidas       │    │ establecidas       │
   │ informal           │    │ estructurado       │
   │ sin roles          │    │ roles definidos +  │
   │                    │    │ facilitador        │
   │ genera ideas       │    │ toma decisiones    │
   └────────────────────┘    └────────────────────┘
           ANTES          →          DESPUÉS
```

## 12. Talleres de requisitos 🟡

Es un **término genérico** dado a varios tipos distintos de reuniones grupales donde el énfasis está en **desarrollar y descubrir requisitos** para un sistema de software.

Las formas que menciona el capítulo:

| Variante | Qué la caracteriza |
|---|---|
| **Interfuncional** (*cross functional*) | Involucra **distintos tipos de interesados de diversas áreas del negocio** |
| **Captura Cooperativa de Requisitos** (CRC) | Como JAD, tiene un **conjunto definido de actividades**, y **la comunidad de desarrollo está especialmente involucrada** |
| **Creatividad** | Fomenta el **pensamiento y la expresión innovadores** |
| **Grupo focal** (*focus group*) | Variante usada a menudo en **análisis de mercado** |

> 🕳️ **Ojo con la sigla CRC.** En este capítulo aparece dos veces con significados distintos: en clasificación de tarjetas es *Class Responsibility Collaboration*; acá es *Co-operative Requirements Capture*. No están relacionadas. Volvé al camino.

---

# FAMILIA 5 — Técnicas observacionales

## 13. Etnografía 🟡

Es **el estudio de las personas en su entorno natural**. Involucra al analista participando **activa o pasivamente** en las actividades normales de los usuarios **durante un período extendido de tiempo**, mientras recolecta información sobre las operaciones que se realizan.

**Cuándo es especialmente útil:**

- Al abordar **factores contextuales** como la usabilidad.
- Al investigar **entornos de trabajo colaborativo**, donde entender **las interacciones entre distintos usuarios y el sistema** es fundamental.

**En la práctica es particularmente efectiva** en dos situaciones:

1. Cuando la necesidad de un sistema nuevo **surge de problemas existentes con los procesos y procedimientos**.
2. Para **identificar patrones sociales y relaciones complejas** entre los interesados humanos.

> Ese segundo punto es el que ninguna otra técnica del catálogo cubre bien. Quién le pide favores a quién, qué proceso oficial en realidad se saltea todos los días, qué pasa cuando el sistema falla — eso no aparece en una entrevista, porque nadie lo declara.

## 14. Observación 🟡

Es **una de las técnicas etnográficas más ampliamente usadas**. Como su nombre sugiere, el analista **observa la ejecución real de los procesos existentes** por parte de los usuarios, **sin interferencia directa**.

**Casi nunca va sola:** se usa a menudo junto con otras, como entrevistas y análisis de tareas.

**Su costo:** como regla general, las técnicas etnográficas como la observación son **muy caras de realizar** y **requieren habilidad y esfuerzo significativos** por parte del analista **para interpretar y entender** las acciones que se están realizando. Mirar es fácil; leer lo que estás mirando, no.

**Su límite más conocido:** la efectividad puede variar porque **los usuarios tienen tendencia a ajustar la forma en que realizan las tareas cuando saben que están siendo observados**.

## 15. Análisis de protocolo 🟡

Los participantes **realizan una actividad o tarea mientras la van hablando en voz alta**, describiendo las acciones que ejecutan **y el proceso de pensamiento detrás de ellas**.

**Qué aporta:** información específica sobre los procesos que el sistema objetivo debe soportar, **y la justificación de esos procesos**. Ese "por qué" es lo que la distingue de la observación pura.

**Sus dos límites**, y ambos son sutiles:

1. En la mayoría de los casos, **hablar una operación mientras se la ejecuta no es la forma normal de realizarla**. Como resultado, lo verbalizado **puede no representar el proceso verdadero de manera completa ni correcta**.
2. Los **pasos menores que se realizan de forma frecuente y repetitiva** suelen ser **dados por sentado** por los usuarios, y por lo tanto **pueden no explicarse y no quedar registrados** como parte del proceso.

> El segundo límite es el más traicionero: lo que la persona hace mil veces por día es exactamente lo que se le olvida mencionar, porque para ella ya no es un paso.

## 16. Aprendizaje por acompañamiento 🟡

*(En inglés,* apprenticing *— literalmente, hacer de aprendiz.)*

El analista **efectivamente aprende y realiza las tareas actuales** bajo la instrucción y supervisión de un usuario experimentado.

**La diferencia con el análisis de protocolo** está en la vía: acá al analista **se le enseñan** las operaciones y los procesos de negocio **observando, preguntando y haciendo físicamente**, en vez de que se los informen. Aprende con las manos, no de oído.

Es similar al juego de roles pero **más comprometido**.

**Cuándo es muy útil** — dos casos, y el segundo es el interesante:

1. Cuando **el analista es inexperto en el dominio**.
2. Cuando **los usuarios tienen dificultad para explicar sus acciones**. Si no lo pueden decir, se lo pueden mostrar.

**Una variante que va más lejos:** la **inmersión** (*emersion*), donde el analista **se involucra activamente en las actividades reales del negocio**.

---

# FAMILIA 6 — Técnicas sintéticas y basadas en modelos

## 17. Prototipado 🔴

Darles a los interesados **prototipos del sistema** para sostener la investigación de soluciones posibles es una manera efectiva de reunir **información detallada y retroalimentación relevante**.

**Casi nunca va solo:** es común que los prototipos se usen junto con otras técnicas, como entrevistas y JAD.

**De dónde salen:** típicamente se desarrollan a partir de **requisitos preliminares** o de **ejemplos existentes de sistemas similares**.

**Cuándo es particularmente útil:**

- al desarrollar **interfaces persona-computadora**;
- cuando **los interesados no están familiarizados con las soluciones disponibles** — no saben qué pedir porque no saben qué es posible.

**Métodos disponibles**, con niveles de esfuerzo variables: guiones gráficos (*storyboards*), ejecutable, descartable (*throwaway*) y evolutivo.

**Su costo:** en muchos casos los prototipos son **caros de producir en tiempo y dinero**.

**Su ventaja principal:** **alientan a los interesados —y más específicamente a los usuarios— a tomar un rol activo** en el desarrollo de los requisitos. Dejan de opinar sobre una abstracción y empiezan a reaccionar sobre algo.

**El peligro, y es específico de esta técnica:**

> Los usuarios **pueden encariñarse con el prototipo** y, a partir de ahí, **volverse resistentes a soluciones alternativas**.

Lo que era un instrumento para explorar se convierte en la respuesta. Pese a ese riesgo, la técnica es **extremadamente útil al desarrollar sistemas nuevos para aplicaciones enteramente nuevas**.

## 18. Enfoques basados en metas 🟡

**Premisa fundamental:** las **metas de alto nivel** que representan los objetivos del sistema se **descomponen** —usualmente usando relaciones **Y** y **O**— y se **elaboran** —por ejemplo con preguntas de tipo **"¿Por qué?"** y **"¿Cómo?"**— en submetas, que luego se refinan de tal manera que **los requisitos individuales quedan elicitados**.

```
                    META DE ALTO NIVEL
                           │
              ┌──── ¿Cómo? ────┐
              ▼                ▼
          Submeta A   Y    Submeta B
              │                │
         ┌─── O ───┐           │
         ▼         ▼           ▼
      Submeta   Submeta    Submeta
         │         │           │
         ▼         ▼           ▼
     REQUISITO REQUISITO   REQUISITO
              ▲
              └──── ¿Por qué? ────┘  (sube de vuelta)
```

Las preguntas funcionan en los dos sentidos: **"¿cómo?" baja** hacia el detalle, **"¿por qué?" sube** hacia la justificación. Ese segundo movimiento es el que produce la trazabilidad — cada requisito sabe de qué meta cuelga.

**Qué lo distingue:** el resultado es **significativamente más complicado y más completo** que los métodos tradicionales de representar metas del sistema con diagramas de estructura de árbol. Estos enfoques son capaces de representar **relaciones detalladas entre entidades del dominio, requisitos y objetivos del sistema**.

**Sus riesgos generales**, y son dos:

1. **Los errores en las metas de alto nivel cometidos temprano pueden tener un efecto de arrastre mayor y perjudicial.** Si la raíz está mal, todo el árbol está mal.
2. **Las metas cambiantes son difíciles de gestionar.**

**Trabajos concretos** en esta línea que menciona el capítulo: el proyecto **F3**, el metamodelo **KAOS** y el marco ***i\**\* *(i-estrella)*. El uso de metas **en conjunto con escenarios** para elicitar requisitos también atrajo considerable atención.

**Cuándo son particularmente útiles en la práctica:** en situaciones donde **solo las necesidades de alto nivel del sistema son bien conocidas**, y hay una falta general de entendimiento sobre los detalles específicos de los problemas a resolver y sus soluciones posibles.

## 19. Escenarios 🔴

Son **ampliamente usados** en elicitación. Como el nombre sugiere, son **descripciones narrativas y específicas de procesos actuales y futuros**, incluyendo **las acciones e interacciones entre los usuarios y el sistema**.

**Dos propiedades que comparten con los casos de uso:**

1. **No consideran típicamente la estructura interna del sistema.**
2. **Requieren un enfoque incremental e interactivo** para su desarrollo.

**Una regla operativa que el capítulo destaca:** es importante, al usar escenarios, **recolectar todas las excepciones potenciales de cada paso**. El camino feliz es la parte fácil; el valor está en lo que puede salir mal.

**Trabajos estructurados** en esta línea: **CREWS**, el **Ciclo de Indagación** (*The Inquiry Cycle*), **SBRE** y **Scenario Plus**.

**Usos adicionales:** los escenarios son además muy útiles para **entender y validar requisitos**, y para el **desarrollo de casos de prueba**.

> ⚠️ **Cruce con la cátedra — importante, leelo.** La palabra "escenario" acá **no significa lo mismo** que en tu materia. Este capítulo usa *escenario* en el sentido genérico de la literatura anglosajona: una descripción narrativa usada como técnica de elicitación. Los **escenarios** que vas a construir en las clases 10 a 14 son un **artefacto formal con estructura definida**, de la tradición de Leite y Doorn, y vienen atados al LEL. **No los estudies de acá.** Este capítulo te sirve para entender por qué la narrativa funciona como técnica; la mecánica del artefacto que te van a evaluar viene del material de la cátedra.
>
> Lo que sí es aprovechable: la regla de recolectar todas las excepciones de cada paso, y la observación de que escenarios y casos de uso comparten el ignorar la estructura interna del sistema.

## 20. Puntos de vista 🟡

Los enfoques de puntos de vista (*viewpoints*) apuntan a **modelar el dominio desde perspectivas diferentes**, para desarrollar una descripción **completa y consistente** del sistema objetivo.

**Ejemplos de perspectivas:** un sistema puede describirse en términos de su **operación**, su **implementación** y sus **interfaces**. Del mismo modo, puede modelarse desde el punto de vista de **distintos usuarios** o desde la **posición de sistemas relacionados**.

**Cuándo son particularmente efectivos:** en proyectos donde **las entidades del sistema tienen relaciones detalladas y complicadas entre sí**.

**Uso adicional:** sirven también como forma de sostener **la organización y la priorización** de los requisitos.

**Las dos críticas comunes:**

1. **No permiten representar fácilmente los requisitos no funcionales.**
2. Son **caros de usar** en términos del esfuerzo requerido.

Algunos enfoques de esta familia proveen un **modelo flexible multiperspectiva**, usando distintos puntos de vista para elicitar y ordenar requisitos provenientes de varias fuentes. Con ellos, analistas e interesados pueden organizar el proceso y **derivar requisitos detallados para un sistema completo desde múltiples puntos de vista específicos del proyecto**.

---

# Las dos tablas de comparación 🔴

Los autores plantean las dos preguntas que hay que responder durante la elicitación:

1. **¿Qué técnicas y enfoques deberían usarse** para una actividad de elicitación dada?
2. **¿Cuáles de esas técnicas y enfoques son complementarios**, o pueden usarse como alternativas entre sí?

Su propia advertencia antes de responder: en última instancia **cada situación es única**, y las respuestas dependen fuertemente del contexto del proyecto y del sistema. Reconocen explícitamente que **siempre hay posibilidad de excepciones** a cualquier regla trazada en esta línea. Las tablas se ofrecen como **apoyo de alto nivel**, no como receta.

**Cómo eligieron qué incluir:** en vez de meter las veinte técnicas de la sección, seleccionaron un **grupo núcleo de ocho** que consideran que cubre adecuadamente el espectro —por ejemplo, la etnografía incluye a la observación, y JAD es un ejemplo de trabajo grupal— y que representa apropiadamente tanto el estado del arte como el estado de la práctica. La información de las tablas se basa mayormente en **su evaluación de la literatura y en su experiencia y observación prácticas**.

## Tabla 1 — Qué técnica sirve para qué actividad

Las cinco filas son las cinco actividades del proceso de elicitación que viste en la Parte 2. Una **X** marca que la técnica está entre las mejor adaptadas para esa actividad.

| Actividad | Entrevistas | Dominio | Trabajo grupal | Etnografía | Prototipado | Metas | Escenarios | Puntos de vista |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| **Entender el dominio de aplicación** | X | X | X | X | | X | X | X |
| **Identificar fuentes de requisitos** | X | X | X | | | X | X | X |
| **Analizar a los interesados** | X | X | X | X | X | X | X | X |
| **Seleccionar técnicas y enfoques** | X | X | X | | | | | |
| **Elicitar los requisitos** | X | X | X | X | X | X | X | X |

**Cómo la leen los autores:**

- Para cada actividad hay **varias técnicas adecuadas**. Nunca una sola.
- **Entrevistas, análisis de dominio y trabajo grupal** son las tres **genéricas y flexibles**: son las únicas que dan soporte a **todas** las actividades listadas.
- Los enfoques basados en **metas, escenarios y puntos de vista** también pueden usarse extensamente a lo largo del proceso.
- Que **todas** las técnicas del núcleo sirvan para la actividad de *elicitar los requisitos* es natural: ya las clasificamos como técnicas de elicitación.

> Mirá la fila cuatro, **seleccionar técnicas y enfoques**, que es la más pobre de la tabla: solo tres marcas. Tiene sentido y es revelador — para decidir **cómo** vas a elicitar, primero tenés que hablar con gente y mirar documentos. No podés elegir el instrumento desde el escritorio.

## Tabla 2 — Cuáles se combinan y cuáles se reemplazan

**C** = se pueden usar **en cooperación** (son complementarias). **A** = se pueden usar como **alternativas** una de la otra.

| | Entrevistas | Dominio | Trabajo grupal | Etnografía | Prototipado | Metas | Escenarios | Puntos de vista |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| **Entrevistas** | — | C | A | A | A | C | C | C |
| **Dominio** | C | — | C | A | A | A | A | A |
| **Trabajo grupal** | A | C | — | A | C | C | C | C |
| **Etnografía** | A | A | A | — | C | C | A | A |
| **Prototipado** | A | A | C | C | — | C | C | C |
| **Metas** | C | A | C | C | C | — | C | C |
| **Escenarios** | C | A | C | A | C | C | — | A |
| **Puntos de vista** | C | A | C | A | C | C | A | — |

**Por qué importa cada categoría:**

**Las complementarias (C).** En la mayoría de los proyectos va a hacer falta usar más de una técnica, así que conviene **seleccionar las que se complementan** para obtener el mejor resultado posible. El ejemplo que da el capítulo es bueno: cuando **los usuarios operan un prototipo bajo la observación del analista**, la combinación tiene el potencial de dar información **mucho más rica y detallada** sobre los procesos de negocio y sobre las necesidades de los usuarios, que cualquiera de las dos por separado.

**Las alternativas (A).** Dan **mayor flexibilidad** al proceso y **más opciones** al analista y a los interesados. Son útiles en tres situaciones:

1. Si por alguna razón la técnica elegida **no está resultando tan efectiva** como se esperaba.
2. Cuando el analista **no está familiarizado o cómodo** con una técnica particular.
3. Cuando el analista está **imposibilitado de usarla**.

El ejemplo del tercer caso es elocuente: **puede no ser posible observar a los usuarios realizando sus operaciones normales** por el ambiente **físicamente peligroso** en el que trabajan. En ese caso el analista puede optar por **usar escenarios** para elicitar ese mismo tipo de información.

> ⚠️ **Cruce con la cátedra.** Esta tabla es probablemente el objeto más directamente aprovechable de todo el capítulo. Si en un TP tenés que justificar por qué elegiste una técnica —o por qué descartaste otra y con qué la reemplazaste—, acá tenés el respaldo: no es que la entrevista sea "mejor" que la etnografía; son **alternativas** entre sí, y la elección se argumenta contra las restricciones del caso. Eso es exactamente el criterio fundamentado que la cátedra valora por encima de la respuesta canónica.

---

## Mapa de las veinte técnicas

```
CONVERSACIONALES        Entrevistas (no estruct. / estruct. / semi)
   preguntar             Cuestionarios

ANALÍTICAS              Análisis de tareas       ┐
   estudiar             Análisis del dominio     ├─ no requieren
                        Introspección            ┘   interesados presentes
                                                     (la última, peligrosa)

ESTRUCTURACIÓN          Grillas de repertorio    ┐
   ordenar el           Clasificación de tarjetas├─ no producen requisitos:
   conocimiento         Escalamiento             ┘   clarifican y categorizan

GRUPALES                Trabajo grupal           ┐
   reunir               Tormenta de ideas        ├─ ojo con la política
                        JAD                      │   y con quien monopoliza
                        Talleres de requisitos   ┘

OBSERVACIONALES         Etnografía               ┐
   mirar / hacer        Observación              ├─ caras, lentas, y las
                        Análisis de protocolo    │   únicas que ven lo que
                        Aprendizaje acompañado   ┘   nadie declara

SINTÉTICAS              Prototipado              ┐
   construir un         Enfoques por metas       ├─ producen un artefacto
   objeto para          Escenarios               │   sobre el cual se
   discutir sobre él    Puntos de vista          ┘   discute
```

---

## Preguntas para chequear que quedó

Sin respuestas — si alguna te traba, tirámela por chat.

1. ¿Cuál es la diferencia entre "técnica" y "enfoque" según el capítulo? Dé un ejemplo de cada uno.
2. Nombrá los tres tipos de entrevista y decí para qué sirve mejor cada uno.
3. ¿Por qué la entrevista no estructurada conviene *antes* que la estructurada, y no al revés?
4. El cuestionario tiene tres límites encadenados. ¿Cuáles son, y cuál de los tres conecta con el problema de la brecha cultural?
5. ¿Cuál es la condición de entrada para que un cuestionario sirva? ¿Qué pasa si se aplica antes de que se cumpla?
6. ¿Por qué la introspección es la técnica más peligrosa del catálogo? ¿Bajo qué dos condiciones se sostiene?
7. En clasificación de tarjetas, ¿qué es más valioso: el agrupamiento resultante o la justificación del agrupamiento? ¿Por qué?
8. ¿Qué supuesto fuerte hace la técnica de escalamiento, y qué pasa si el dominio no lo cumple?
9. ¿En qué situación el trabajo grupal es poco efectivo, y por qué?
10. Nombrá las dos diferencias entre tormenta de ideas y JAD.
11. ¿Qué tipo de información captura la etnografía que ninguna otra técnica del catálogo captura bien?
12. ¿Cuál es el problema conocido de la observación como técnica?
13. Análisis de protocolo tiene dos límites. Explicá por qué el segundo —los pasos dados por sentado— es especialmente traicionero.
14. ¿En qué se diferencia el aprendizaje por acompañamiento del análisis de protocolo?
15. ¿Cuál es el peligro específico del prototipado, y por qué es difícil de revertir una vez que ocurre?
16. En los enfoques basados en metas, ¿qué hace la pregunta "¿cómo?" y qué hace la pregunta "¿por qué?"?
17. ¿Cuáles son los dos riesgos de los enfoques basados en metas?
18. ¿Cuáles son las dos críticas comunes a los enfoques de puntos de vista?
19. Según la tabla 1, ¿qué tres técnicas sirven para las cinco actividades? ¿Por qué la actividad de "seleccionar técnicas" es la que menos opciones tiene?
20. Un ambiente de trabajo físicamente peligroso impide observar a los usuarios. Según la tabla 2, ¿con qué técnica podrías reemplazar la observación, y por qué esa y no otra?

---

**FIN DE LA PARTE 3 — Catálogo de técnicas y enfoques de elicitación**

*Sigue en la Parte 4, la última: elicitación basada en metodologías (análisis estructurado, orientación a objetos y UML, casos de uso), herramientas de soporte, los problemas y trampas más comunes del proceso, las tendencias y desafíos actuales, y las direcciones de investigación futura.*
