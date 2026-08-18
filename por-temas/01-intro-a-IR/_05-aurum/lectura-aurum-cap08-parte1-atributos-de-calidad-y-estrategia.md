# Lectura en español — Cap. 8 · Parte 1: Los atributos de calidad y la estrategia

> **Origen.** Capítulo 8, secciones 8.1 y 8.2, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Christian Denger y Thomas Olsson**, Instituto Fraunhofer de Ingeniería de Software Experimental, Alemania.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.

---

## Leé este capítulo con atención

De los ocho que llevamos, **este es el que más directamente te explica cómo te corrigen.**

La tabla de la sección 3 contiene **diez atributos de calidad de los requisitos**, y entre ellos están, con esos nombres exactos: **no ambiguo, verificable, trazable, completo, consistente, comprensible**. Son las palabras del léxico con el que Laura corrige, definidas una por una, con su justificación y con la vista de calidad a la que responde cada una.

Hasta ahora venías juntando esas palabras de a pedazos por los capítulos anteriores. Acá están todas juntas y definidas.

---

## 1. Por qué la calidad se asegura temprano 🔴

### El argumento de arranque

> **La ingeniería de requisitos es la parte inicial del proceso de desarrollo, y todos los pasos posteriores están influidos por los requisitos** — lo que vuelve a la calidad de los requisitos **un factor importante para la calidad general del sistema desarrollado.**

Y una crítica a la práctica habitual:

> **Tradicionalmente, las técnicas de aseguramiento de calidad se enfocaron principalmente en las fases tardías** —la implementación y las actividades de prueba relacionadas. **Sin embargo, el aseguramiento de calidad puede y debería empezar antes.**

### Por qué detectar temprano 🔴

> **Un problema que se origina en los requisitos corre el riesgo de afectar no solo a otros requisitos, sino también a las fases posteriores, y puede causar defectos derivados en arquitectura, diseño, codificación y pruebas.**

```
   ORIGEN:   REQUISITOS
                 │
                 ▼
   IMPACTO:  REQUISITOS → DISEÑO → CÓDIGO → PRUEBAS → MANTENIMIENTO
                                              └──── aseguramiento
                                                    OPORTUNISTA ────┘
```

**Qué pasa si solo se asegura calidad en pruebas y mantenimiento.** Los autores lo dicen con precisión:

> Se depende **de la capacidad de los ingenieros de requisitos, diseñadores y programadores de producir buenos productos de trabajo**. Es decir: **se confía en su capacidad de no cometer ningún error crucial. Pero eso reflejaría un caso ideal que en casi todos los casos no puede alcanzarse** — es natural que los humanos cometan errores.
>
> **Sin un aseguramiento intermedio —una compuerta de calidad para los productos de trabajo intermedios— lo más probable es que el diseño y la implementación se basen en los requisitos equivocados.** Eso lleva a un esfuerzo alto de retrabajo, porque **no solo el código sino también, la mayoría de las veces, la arquitectura y el diseño generales tienen que revisarse.**

Y sin embargo, dicen, **parece bastante común hacer aseguramiento de calidad solo mediante pruebas** — lo cual es, por eso, **un enfoque oportunista**.

### Los números 🔴

- **Las pruebas y el retrabajo pueden dar cuenta de hasta el 40-50 % del esfuerzo de desarrollo.**
- **Un problema de requisitos puede volverse hasta 100 veces más caro si se detecta en operación**, comparado con detectarlo en la fase de requisitos.
- **Las deficiencias en los requisitos son la fuente principal de fracaso de los proyectos.**
- **Más del 40 % de los problemas del ciclo de desarrollo resultan de requisitos de baja calidad.**

**La conclusión de los autores:**

> **Las técnicas de aseguramiento de calidad para requisitos son una de las técnicas más prometedoras y costo-efectivas** para asegurar un desarrollo exitoso y prevenir retrabajo evitable en fases posteriores. **Independientemente de si se requiere alta calidad o no, el aseguramiento de calidad en la fase de requisitos rinde.** Pero se vuelve aún más importante si la alta calidad es un factor clave de éxito.

---

## 2. Qué significa "calidad" acá 🔴

### El problema de definirla

> **La calidad es difícil de definir porque es un concepto complejo, dependiente de los puntos de vista organizacionales y de las características del contexto.**

El ejemplo que dan es filoso: **¿menos defectos por línea de código equivale a alta calidad? ¿Y si uno de esos defectos causa la pérdida de una vida?** En un procesador de texto son importantes criterios de calidad distintos que en la unidad de control electrónico de un auto o un avión.

Y con los requisitos se vuelve todavía más difícil, **porque la noción de calidad depende a menudo de las opiniones de los diversos interesados**:

> **Si no entendiste correctamente las necesidades de los interesados, estás condenado a terminar con un sistema que no va a considerarse de buena calidad**, porque puede no apoyar al usuario en cumplir ciertas tareas.

### "Problema" en vez de "defecto" 🔴

Los autores hacen una aclaración terminológica que importa:

> En este capítulo se usa el término **problema** (*issue*) como **término paraguas para todos los asuntos que deberían resolverse** en el contexto de requisitos.

**Por qué no "defecto":** porque en el caso de los requisitos, **a veces no está claro si un problema realmente es un defecto**. El ejemplo:

> **Si dos interesados están en desacuerdo sobre un aspecto de un requisito, eso es un problema que debería resolverse — pero no se lo llamaría normalmente un defecto en el sentido tradicional. Si no se resuelve, al menos un interesado va a rechazar el sistema en la prueba de aceptación.**
>
> En cambio, **los requisitos contradictorios están más cerca de la interpretación convencional de defecto.**

> ⚠️ **Cruce con la cátedra.** Esta distinción es útil para una revisión de TP: **no todo lo que hay que arreglar es un error.** Un desacuerdo no resuelto entre interesados no es una equivocación de nadie, pero si queda sin resolver se paga igual — y más caro, porque se paga en la aceptación. Nombrarlo "problema" en vez de "defecto" permite registrarlo sin acusar a nadie, que es exactamente lo que necesitás en una minuta.

### Las cinco vistas sobre la calidad 🟡

Para definir qué significa calidad en un contexto hay que considerar varias vistas:

| Vista | Qué considera |
|---|---|
| **Trascendental** | La calidad como **algo a lo que siempre aspiramos como ideal, pero que nunca vamos a poder implementar**. Su objetivo es expresar la complejidad del concepto |
| **Del usuario** | Evalúa la calidad respecto de su **aptitud para el propósito** de cumplir ciertas tareas del usuario |
| **De manufactura** | Se enfoca en el producto **durante la producción y después de la entrega**. Foco en **la adherencia a estándares** y en evaluar si **el producto se construyó bien la primera vez** |
| **Del producto** | Foco en los **aspectos internos de calidad que pueden medirse**. Se asume que asegurar ciertos aspectos internos impacta la calidad externa y la calidad en uso |
| **Basada en el valor** | **Relaciona calidad con costo.** Considera la calidad como **algo que el cliente está dispuesto a pagar** |

**Cómo se mapean sobre los requisitos:**

```
   los requisitos deben DESCRIBIR LO QUE EL USUARIO REQUIERE
   del sistema final ─────────────────────► vista del usuario

   deben describirse de modo que los desarrolladores puedan
   PRODUCIR EL SOFTWARE eficaz y eficientemente
                       ─────────────────────► vista del producto

   los ingenieros de requisitos deben SEGUIR ESTÁNDARES al
   especificarlos ─────────────────────────► vista de manufactura

   los clientes deben decidir el VALOR de cada requisito y si
   el costo de implementación está justificado
                       ─────────────────► vista basada en el valor
```

Y una observación de fondo: **la naturaleza inherentemente humana de la IR, y la necesidad de considerar no solo aspectos técnicos sino también sociales al elicitar, negociar y especificar, vuelve la definición de características de calidad todavía más difícil.**

---

## 3. Los diez atributos de calidad 🔴🔴

Esta es **la tabla más importante del capítulo y probablemente de todo el libro para tu materia**. Los primeros siete vienen del **estándar IEEE para especificación de requisitos**; los tres últimos son extensiones que agregan los autores.

Cada atributo indica además **a qué vista de calidad responde**.

### Los siete del estándar IEEE

| Atributo | Definición | Vista |
|---|---|---|
| **Corrección** | **Los requisitos implementados tienen que reflejar el comportamiento esperado (intencionado) de usuarios y clientes.** Es decir: todo lo enunciado como requisito es algo que el sistema final debe cumplir para satisfacer cierto propósito (aptitud) | Usuario |
| **No ambigüedad** | **Los requisitos deberían tener solo una interpretación posible.** Nota: un requisito puede ser no ambiguo para cierto grupo de interesados **pero tener otro significado en otro grupo**. Es importante involucrar a todos los interesados para ganar un entendimiento común | Producto |
| **Completitud** | **Deben considerarse todos los elementos importantes** relevantes para cumplir las distintas tareas del usuario. Incluye: requisitos funcionales y no funcionales relevantes, **interfaces con otros sistemas**, **la definición de las respuestas a todas las entradas potenciales**, todas las referencias a figuras y tablas, **y la definición de todos los términos y medidas relevantes** | Producto |
| **Consistencia** | Los requisitos enunciados deberían ser **consistentes con todos los demás requisitos** y con **otras restricciones importantes** — restricciones de hardware, de presupuesto, etc. | Producto, manufactura |
| **Ordenado por importancia / estabilidad** | Cada requisito **especifica su importancia y/o su estabilidad.** La **estabilidad** expresa **la probabilidad de que el requisito cambie**; la **importancia** especifica **cuán esencial es el requisito para el éxito del proyecto** | Producto, valor, usuario |
| **Verificabilidad** | Todos los requisitos deberían ser verificables. Es decir: **existe un proceso, para una máquina o un humano, que permite chequear —de manera costo-efectiva— si el requisito se cumple o no** | Producto |
| **Modificabilidad** | Todos los requisitos deberían ser modificables: **la estructura de los requisitos y de la especificación permite integrar cambios de manera fácil, consistente y completa** | Producto |
| **Trazabilidad** | Todos los requisitos deberían ser trazables: **debería ser posible referenciar el requisito de manera fácil.** Además, **es posible identificar el origen de un requisito** | Manufactura |

### Los tres que agregan los autores 🔴

| Atributo | Definición | Vista |
|---|---|---|
| **Comprensibilidad** | Los requisitos están especificados y redactados **de una manera que todos los interesados involucrados entienden** | Manufactura, usuario, valor |
| **Factibilidad** | **Todos los requisitos pueden implementarse con la tecnología, los recursos humanos y el presupuesto disponibles.** Además, **todos los requisitos contribuyen al éxito monetario del sistema** — es decir, **vale la pena incluirlos** | Valor, producto |
| **Nivel de detalle correcto** | La información dada en los requisitos **es adecuada para ganar el entendimiento correcto del sistema y para empezar la implementación. No hay detalles innecesarios de implementación o diseño especificados en los requisitos** | Usuario, manufactura, valor |

### Por qué agregaron esos tres 🔴

**Comprensibilidad** es esencial porque **hay muchos interesados distintos involucrados**. Es importante que los requisitos puedan ser entendidos fácilmente por todos y que **todos tengan un entendimiento común**.

**Factibilidad** importa especialmente porque **un requisito solo tiene valor si puede transformarse en un diseño y una implementación con esfuerzo y costo razonables.**

**Nivel de detalle correcto** — y acá está la definición más fina de las tres:

> Los requisitos deberían estar especificados en un nivel de detalle adecuado: **concreto lo suficiente para permitir que el diseño y la implementación puedan empezar, pero por otro lado abstracto lo suficiente para permitir la discusión entre todos los interesados involucrados** — que en muchos casos tienen trasfondos técnicos y no técnicos.

### Los atributos no son independientes 🔴

Los autores advierten:

> **Hay relaciones entre los atributos.** Por ejemplo, **los requisitos ambiguos son también difíciles de entender.** Además, **si los requisitos no son trazables, la verificabilidad, la modificabilidad y la comprensibilidad pueden verse afectadas.**
>
> Aunque la clasificación **no es ortogonal**, cada atributo refiere a un aspecto especial de la calidad que debería considerarse.

```
   AMBIGUO ──────► difícil de ENTENDER

   NO TRAZABLE ──┬─► afecta la VERIFICABILIDAD
                 ├─► afecta la MODIFICABILIDAD
                 └─► afecta la COMPRENSIBILIDAD
```

> ⚠️ **Cruce con la cátedra — esta sección es el mapa completo de cómo te corrigen.** Compará la tabla con las palabras que usa Laura: **específico, concreto, no ambiguo, sin doble interpretación, verificable, trazable.** Están todas acá, con definición formal y origen en un estándar IEEE.
>
> Tres cosas que conviene destacar:
>
> **1. La nota de la no ambigüedad es la más útil de toda la tabla.** Dice que un requisito puede ser **no ambiguo para un grupo de interesados y significar otra cosa para otro grupo**. O sea: **la no ambigüedad no es una propiedad del texto solo — es una propiedad del texto respecto de sus lectores.** Por eso la solución que propone no es escribir mejor, es **involucrar a todos los interesados para ganar entendimiento común**. Es la brecha cultural del capítulo 2, vista como criterio de calidad.
>
> **2. Fijate qué exige la completitud**: la definición de **todos los términos y medidas relevantes**. Eso es, textualmente, la justificación de construir un léxico del dominio — está listado como componente de la completitud de una especificación.
>
> **3. "Nivel de detalle correcto" te da el argumento para las dos direcciones.** Un requisito puede estar mal **por poco detalle** (no se puede empezar a implementar) y también **por demasiado** (mete decisiones de diseño que no le corresponden). Esta es la formulación precisa de por qué "qué, no cómo" importa.

---

## 4. La estrategia de calidad 🟡

### El punto de partida realista

> **Desarrollar software sin ningún defecto es imposible.** Es, sin embargo, **posible alcanzar un compromiso óptimo entre la calidad deseada y los recursos disponibles**, considerando los factores de contexto específicos y las necesidades de calidad de una empresa o proyecto.

Y una observación incómoda pero cierta:

> En ciertos dominios **es más importante ser el primero en el mercado que tener productos de alta calidad** en el sentido de pocos defectos. **Hay mucho software tremendamente exitoso, desde el punto de vista comercial, que es cualquier cosa menos de alta calidad.**
>
> Por otro lado, **el costo de un solo defecto puede ser fatal e increíblemente caro** — el ejemplo que dan es el desastre del Ariane 5.

**La regla que se desprende:**

> **La minuciosidad y el presupuesto para aseguramiento de calidad tienen que relacionarse con el costo de una implementación errónea**, que puede llevar a costos financieros o humanos.

### Qué hay que decidir durante la fase de requisitos 🔴

> **Es importante definir una estrategia de calidad que aborde aquellos problemas de calidad que pueden verificarse y validarse fácilmente en la fase de requisitos. Los otros aspectos de calidad, que no pueden abordarse eficientemente durante esta fase, deberían dejarse para fases posteriores.**

**Qué es una estrategia de calidad:**

> Define **cómo, cuándo y dónde** se usan los distintos enfoques de aseguramiento, en combinación con otros enfoques del proceso, para asegurar alta calidad. Incluye **la planificación de recursos** —qué enfoque se aplica cuándo y cuánto esfuerzo se le dedica— y **la definición de una combinación optimizada** de los distintos enfoques, con el objetivo de lograr la calidad deseada al costo deseado.

Definirla **no es trivial**: requiere conocimiento detallado del contexto de la empresa y el proyecto, del nivel de aseguramiento requerido para cada atributo, y de qué enfoques son aplicables.

### Los cinco elementos de contexto 🟡

| Elemento | Qué aporta |
|---|---|
| **1. La calidad de los requisitos** | Los criterios de qué es un buen requisito. **Pueden variar de empresa a empresa y de proyecto a proyecto.** Especifican **qué debería lograrse** con la estrategia. Es importante **definir conjuntos óptimos y mínimos** de características |
| **2. Los recursos disponibles** | Esfuerzo, presupuesto, hardware y personal. Además, **la disponibilidad de expertos adicionales** — para ciertos enfoques hacen falta interesados de fuera del proceso de requisitos, como el arquitecto principal en una revisión. **Impacta directamente qué enfoques son aplicables**: si hay poco esfuerzo, **no se puede hacer una inspección formal completa con muchos participantes, sino solo una revisión entre pares** |
| **3. Los riesgos** | Especialmente el riesgo de **no realizar un requisito o de implementarlo de la manera equivocada**. Riesgo se define como **no poder cumplir con las metas de calidad**. Es un factor importante para decidir **sobre qué parte de los requisitos debe enfocarse cada enfoque**. Ejemplo: **no cumplir un requisito importante para proteger vidas humanas conlleva un riesgo alto y debería chequearse con cuidado extra** |
| **4. El cronograma general** | Define **el tiempo disponible** para el aseguramiento en general y dentro de la fase de requisitos en particular. Especialmente importante porque **relaciona las actividades de calidad de requisitos con las demás actividades** |
| **5. Los aspectos organizacionales** | El proceso de desarrollo —dirigido por plan o ágil— y el dominio del producto. **Ciertos enfoques pueden no ser aplicables por restricciones organizacionales.** Ejemplo: **en un proceso ágil las revisiones de requisitos son casi imposibles**, porque los requisitos no se documentan de una manera que permita inspeccionarlos — las historias de usuario a menudo no tienen más de una oración |

### Los tres elementos técnicos 🟡

| Elemento | Qué es |
|---|---|
| **Estrategias básicas** | Las que **ya están en uso** en la empresa o el proyecto — el estado actual de la práctica. Por falta de estrategias sofisticadas, **lo más frecuente son enfoques improvisados**. La más simple y menos sistemática es declarar que **todo en la especificación debe verificarse**, o que **todos los problemas de calidad se atacarán en fases posteriores**. Las **estrategias basadas en experiencia** dan pistas sobre qué atender según proyectos anteriores. **Deben considerarse al crear una estrategia más sofisticada: dan una entrada valiosa sobre por dónde empezar y qué rindió en el pasado** |
| **Criterios de cobertura** | Definen **qué aspectos de los requisitos deben cubrirse**. Un ejemplo: **que todos los requisitos estén cubiertos por al menos un caso de prueba**. Relacionado está **la profundidad**: el nivel de detalle al que se verifican los requisitos, o el nivel de calidad a alcanzar. **A mayor profundidad, más recursos y enfoques más sofisticados hacen falta** |
| **Los enfoques y métodos disponibles** | **El elemento más importante.** Son **el núcleo técnico de la estrategia**, porque representan los medios concretos para lograr buena calidad |

Y una recomendación de orden:

> **El elemento más esencial del marco son las técnicas de aseguramiento que pueden aplicarse. Ese es el elemento que debería considerarse primero:** antes de definir una estrategia detallada, **es importante investigar los enfoques potenciales para verificar los atributos de calidad de los requisitos.**

Los autores insisten además en que **para instanciar el marco en una estrategia concreta es esencial la recolección continua de datos**, que debería responder a **qué problemas de requisitos son los más caros y qué técnicas funcionan mejor en ese contexto específico**.

---

## 5. Las dos familias de enfoques 🔴

Todos los enfoques de aseguramiento se dividen en dos clases:

```
                 ASEGURAMIENTO DE CALIDAD
                            │
           ┌────────────────┴────────────────┐
           ▼                                 ▼
     CONSTRUCTIVOS                      ANALÍTICOS
     PREVIENEN que los                  DETECTAN problemas
     problemas se introduzcan           en el artefacto ya hecho
     · técnicas de elicitación          │
     · técnicas de especificación   ┌───┴────┐
       (estándares, procesos)       ▼        ▼
     · prototipado              DINÁMICOS  ESTÁTICOS
                                (validación) (verificación)
                                pruebas     inspecciones
                                    ▲
                             requieren una versión
                             EJECUTABLE del sistema
```

| | **Constructivos** | **Analíticos** |
|---|---|---|
| **Cuándo actúan** | **Durante la creación** del producto de trabajo | **Sobre el artefacto completo** o una parte autocontenida |
| **Qué hacen** | **Aseguran que los errores se minimicen** — es decir, **previenen que los problemas se introduzcan** | **Detectan problemas** ya introducidos |
| **Ejemplos** | Guías de estilo sobre cómo especificar requisitos · plantillas · enfoques de elicitación · prototipado | Inspecciones · pruebas · verificaciones formales |

**La subdivisión de los analíticos:**

- **Dinámicos** — **requieren una versión ejecutable del sistema.** Las pruebas son el ejemplo.
- **Estáticos** — **pueden realizarse sin ejecutar código.** Inspecciones y verificaciones formales.

Y la consecuencia práctica:

> **En la mayoría de los casos no hay código ejecutable disponible durante la fase de requisitos. Por lo tanto, usualmente solo son aplicables los enfoques estáticos.**

### Análisis vs. validación 🔴

Los autores marcan una distinción final que ordena todo:

| Fase | Qué se hace | Con qué enfoques |
|---|---|---|
| **Análisis de requisitos** | **Se previene que los problemas se introduzcan** — durante la elicitación se atacan las omisiones y los requisitos ambiguos | **Constructivos** |
| **Validación de requisitos** | Se parte de **un documento de requisitos** y se intenta **resolver los problemas dentro de ese documento** | **Analíticos** |

---

## Mapa de la Parte 1

```
   POR QUÉ TEMPRANO
   un problema de requisitos cuesta hasta 100 VECES MÁS
   si se detecta en operación
   pruebas + retrabajo = 40-50 % del esfuerzo
   >40 % de los problemas vienen de requisitos de baja calidad

   ─────────────────────────────────────────────

   LOS 10 ATRIBUTOS DE CALIDAD

   del IEEE                     agregados por los autores
   · corrección                 · comprensibilidad
   · NO AMBIGÜEDAD              · factibilidad
   · completitud                · nivel de detalle correcto
   · consistencia
   · ordenado por importancia/estabilidad
   · VERIFICABILIDAD
   · modificabilidad
   · TRAZABILIDAD

   NO SON INDEPENDIENTES:
   ambiguo → difícil de entender
   no trazable → afecta verificabilidad, modificabilidad
                 y comprensibilidad

   ─────────────────────────────────────────────

   ESTRATEGIA DE CALIDAD
   contexto: calidad buscada · recursos · riesgos ·
             cronograma · organización
   técnico:  estrategias básicas · criterios de cobertura ·
             ENFOQUES DISPONIBLES (empezar por acá)

   ─────────────────────────────────────────────

   DOS FAMILIAS
   CONSTRUCTIVOS → previenen (durante el análisis)
   ANALÍTICOS ───► detectan (durante la validación)
        dinámicos: necesitan código ejecutable
        estáticos: no lo necesitan ← los únicos
                   aplicables en requisitos
```

---

## Preguntas para chequear que quedó

1. ¿Por qué la calidad de los requisitos afecta la calidad general del sistema?
2. ¿Qué se está suponiendo cuando solo se asegura calidad en la fase de pruebas?
3. ¿Cuánto más caro puede ser un problema de requisitos detectado en operación?
4. ¿Qué porcentaje del esfuerzo de desarrollo pueden consumir las pruebas y el retrabajo?
5. ¿Por qué la calidad es difícil de definir? Dé el ejemplo del procesador de texto y el control de un avión.
6. ¿Por qué los autores usan "problema" en vez de "defecto"? Dé el ejemplo del desacuerdo entre interesados.
7. Nombrá las cinco vistas sobre la calidad y qué considera cada una.
8. Enumerá los diez atributos de calidad de los requisitos.
9. Definí "no ambigüedad". ¿Por qué la nota aclaratoria de ese atributo es importante? ¿Qué solución propone?
10. ¿Qué exige la completitud, además de los requisitos funcionales y no funcionales?
11. Definí verificabilidad. ¿Qué agrega la expresión "de manera costo-efectiva"?
12. ¿Qué dos cosas exige la trazabilidad?
13. ¿Qué diferencia hay entre importancia y estabilidad?
14. ¿Por qué agregaron los autores el atributo de factibilidad?
15. Explicá "nivel de detalle correcto" en sus dos direcciones: ¿un requisito puede fallar por poco detalle y también por mucho?
16. ¿Por qué los atributos no son independientes? Dé dos ejemplos de relación.
17. ¿Por qué desarrollar software sin defectos es imposible, y qué se busca en su lugar?
18. ¿Con qué debe relacionarse el presupuesto de aseguramiento de calidad?
19. Nombrá los cinco elementos de contexto de una estrategia de calidad.
20. ¿Por qué en un proceso ágil las revisiones de requisitos son casi imposibles?
21. ¿Cuál es el elemento más importante del marco y por dónde recomiendan empezar?
22. Diferenciá enfoques constructivos de analíticos, y dinámicos de estáticos.
23. ¿Por qué en la fase de requisitos solo son aplicables los enfoques estáticos?
24. ¿Qué enfoques corresponden a la fase de análisis y cuáles a la de validación?

---

**FIN DEL CAPÍTULO 8 — PARTE 1**

*Sigue en la Parte 2: los enfoques constructivos (elicitación, especificación, prototipado) y los analíticos —inspecciones de requisitos con sus técnicas de lectura, creación temprana de casos de prueba, herramientas automáticas y métodos formales—, más las preguntas abiertas del área.*
