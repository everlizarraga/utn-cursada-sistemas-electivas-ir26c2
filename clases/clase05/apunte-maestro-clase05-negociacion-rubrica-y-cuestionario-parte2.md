# 📘 APUNTE MAESTRO — Clase 05 · Negociación de cambios, rúbrica y cuestionario — Parte 2

**Materia:** Ingeniería de Requisitos (IR) — UTN FRBA · 2C 2026
**Clase:** 05 · jueves 10/09/2026 · virtual
**Parte 2 de 2:** la rúbrica de casos de uso · el cuestionario a socios · kernel sentences · información operativa · checkpoint final de la unidad

**Leyenda:** 🔴 central, evaluable · 🟡 secundario · 🟢 mencionado al pasar · 🕳️ madriguera (tangente que se saltea sin culpa)

---

## Sobre esta parte

**Qué cubre:** cómo se construye la rúbrica con la que vas a autoevaluar tus casos de uso en el parcial, qué es un criterio medible y qué no. Dónde entra el cuestionario a los socios después de la negociación, cómo se diseñan sus preguntas y cómo se defiende cada una. Kernel sentences en una línea, y todo lo operativo de la clase.

**Qué NO cubre:** el rol del ingeniero de requisitos, la reunión de negociación y el caso Vida Sana están en la Parte 1.

## De dónde venís

De la Parte 1: la negociación de Vida Sana terminó con acuerdos, pendientes y una parte interesada que nadie había convocado, los socios. De la clase 04: la rúbrica existe, la armás vos a partir del feedback acumulado y la llevás al parcial. De la clase 03: qué es un cuestionario, formato libre y fijo, los tres tipos de pregunta cerrada, los cinco pasos para diseñarlo, y que no se pregunta nada fuera del alcance. De la clase 04: el cuestionario a los socios va después de la entrevista, en Google Forms. Todo eso se asume.

---

## 6. 🔴 La rúbrica de casos de uso

### 6.1 Empezá por un caso de uso tuyo

Tomá el diagrama del museo. Supongamos que tiene un caso de uso que se llama **Registrar obra de arte**, asociado al actor **Encargado de catálogo**. ¿Está bien? Fijate: el nombre define una funcionalidad que responde a un requerimiento del actor (el encargado de catálogo pretende, justamente, registrar la obra). Tiene un solo verbo, en infinitivo. Tiene un solo objeto. No es una acción física. Está bien.

Ahora mirá estos otros nombres:

| Nombre del caso de uso | Qué falla |
|---|---|
| **Leer documentación de la obra** | Es una acción física, no una funcionalidad del sistema. |
| **Transcribir nombre de la obra** | Ídem: describe algo que hace una persona, no algo que resuelve el sistema. |
| **Registrar obras y empleados del museo** | Un solo verbo, pero **dos objetos**: mezcla dos tipos de registro. |
| **Registrar** | Sin objeto: no se sabe qué se registra. Ambiguo, aunque esté conectado a un actor. |

Y un actor que se llama **Usuario**: no tiene un nombre que represente los requerimientos que tiene frente al sistema ni las funcionalidades que pretende resolver. No logrado.

Eso que acabás de hacer, mirar un elemento del diagrama, compararlo contra una condición y decidir si está logrado o no, es **evaluar la calidad de un producto**. La rúbrica es la herramienta que lo hace sistemático.

### 6.2 Qué es la rúbrica y cómo se lee

Para cada uno de los **elementos que componen un diagrama de casos de uso**, la rúbrica describe qué se evalúa y con qué nivel de logro. En función de lo que hayas logrado respecto de ese elemento, te ponés un puntaje. Cada vez que producís un artefacto, podés evaluar su calidad; la rúbrica es la práctica de definir con qué criterios.

La estructura, con el ejemplo completo del nombre del caso de uso:

| CRITERIO | Logrado cuando… (A) | Medianamente logrado cuando… (B) | No logrado cuando… (C) | Puntaje |
|---|---|---|---|---|
| El nombre del caso de uso… | Define una funcionalidad asociada a un requerimiento del actor. Tiene un solo verbo y está en infinitivo. Tiene un objeto. No es una acción física. | Está definido desde la perspectiva de los objetivos del actor, pero no tiene una vinculación directa con una funcionalidad del sistema. | NO está definido desde el punto de vista del actor y no tiene vinculación directa con una funcionalidad del sistema. Tiene más de un verbo (en infinitivo o conjugados). Tiene más de un objeto. Es una acción física. | A: 5 · B: 2 · C: 0 |
| El nombre del caso de uso… | Tiene un solo verbo y está en infinitivo. Tiene un objeto. No es una acción física. | Tiene un solo verbo conjugado. Tiene más de un objeto o ninguno. No es una acción física. | Tiene más de un verbo (en infinitivo o conjugados). Tiene más de un objeto o ninguno. Es una acción física. | A: 5 · B: 2 · C: 0 |

Las dos filas miran el mismo elemento desde dos lados. La primera evalúa el **sentido**: si el nombre expresa una funcionalidad que responde a lo que el actor necesita del sistema. La segunda evalúa la **forma**: un verbo, en infinitivo, un objeto, sin acciones físicas. Un nombre puede tener la forma perfecta y no responder a ningún requerimiento del actor; por eso son dos criterios.

Las filas que faltan completar, una por elemento del diagrama:

- Actor
- Herencia de actores
- Relación de inclusión
- Relación de extensión
- Relación de generalización
- Cantidad de casos de uso
- Otros (a especificar)

Cómo se lee la escala: si lo que lográs es lo de la columna C (no logrado), no sumás puntos y tenés que corregir para acercarte a lo que la rúbrica propone como trabajo de excelencia. La columna A es la meta; B y C te dicen cuánto te falta.

### 6.3 Un criterio se puede verificar; un adverbio, no

El error más común al armar la rúbrica es escribir los criterios con **adverbios**: *la herencia se utiliza correctamente*, *las relaciones están adecuadamente definidas*, *hay una cantidad ideal de casos de uso*, *las relaciones están bien dibujadas*.

¿Cómo sabés si una herencia es "correcta"? ¿Cuándo una relación está "bien dibujada"? Lo que para uno es correcto, para otro no lo es. Esos adverbios no son cuantitativos, son subjetivos: dan una idea, pero no una pauta para **comparar lo que propone la rúbrica con lo que vos hiciste**. Un criterio sirve cuando dos personas distintas, mirando el mismo diagrama, llegan al mismo puntaje.

Es el mismo problema de la ambigüedad de toda la materia, ahora aplicado al instrumento con el que te corregís: **específico, concreto, no ambiguo, verificable**.

```text
  ❌ "El nombre del caso de uso está bien puesto."
        → ¿bien según quién? No se puede verificar.

  ✅ "Tiene un solo verbo, en infinitivo, y un solo objeto. No es una acción física."
        → se cuenta, se compara, da el mismo resultado para cualquiera.
```

Lo que importa es la propiedad: **cada criterio describe algo que se puede contar o constatar en el diagrama.** Las filas que faltan (actor, herencia, relaciones, cantidad) se escriben con esa misma lógica.

### 6.4 Cómo se construye y para qué te sirve

La rúbrica es **grupal**: hay un archivo por equipo en la carpeta de Drive, abierto hasta el **miércoles 30/09 a las 21 h**, un día antes del parcial práctico, para que llegue la devolución a tiempo. Se puede ir completando y avisando por el foro de consultas, por mensaje o en el mismo documento, y se corrige en línea durante esos veinte días.

Para completarla hay que **repasar**: el documento de pitfalls (glosa: errores típicos a evitar al armar casos de uso), las correcciones recibidas, las resoluciones de los ejercicios. Ahí está el doble valor del trabajo: primero, la práctica de tener que evaluar un producto y decidir qué características evaluar; segundo, terminás repasando todos los ejercicios, aunque en alguno hayas intervenido menos. Las correcciones que se repiten de entrega en entrega van al Padlet, para que no se repitan en la siguiente.

Después de la entrega, la cátedra revisa cada versión, corrige lo que corresponda, y arma un **compilado** con lo mejor de cada rúbrica. Cada cuatrimestre produce una rúbrica distinta, porque cada cuatrimestre resuelve los casos de uso de manera distinta, aunque algunos ejercicios se repitan. Y una rúbrica de casos de uso sirve para cualquier trabajo o proyecto donde uses UML, no solo para esta materia.

**En el parcial.** La rúbrica va **impresa**. Antes de entregar el caso de uso, lo revisás contra ella y corregís lo que no cumple. Y además hacés una **autoevaluación**: resolvés con birome azul o negra, y con otra de **otro color** anotás qué nota te ponés en cada criterio según la rúbrica. Sirve para dos cosas: comprobar que la usaste y la entendiste (a veces la rúbrica no se lee, o se pone una nota baja sin saber qué otro nombre o qué otra relación iría), y mejorar la rúbrica más adelante con esa información.

La consecuencia práctica: **si querés que la rúbrica te sirva, participá en la confección**. Si no interviniste, no la leíste y no sabés dónde está cada cosa, en el parcial no te va a ayudar.

> **Para el parcial, si te preguntan:** *¿Qué condiciones debe cumplir el nombre de un caso de uso?*
> Define una funcionalidad asociada a un requerimiento del actor; tiene un solo verbo en infinitivo y un solo objeto; no es una acción física.

> **Para el parcial, si te preguntan:** *¿Por qué no deben usarse adverbios como "correctamente" o "adecuadamente" en los criterios de una rúbrica?*
> Porque son subjetivos y no cuantitativos: no dan una pauta para comparar lo que propone la rúbrica con lo realizado, y lo que es correcto para uno puede no serlo para otro. Un criterio debe ser específico, concreto y verificable.

> **Para el parcial, si te preguntan:** *¿Qué mide una rúbrica de casos de uso y cómo está estructurada?*
> Mide la calidad de cada elemento del diagrama (nombre del caso de uso, actor, herencia, inclusión, extensión, generalización, cantidad de casos de uso). Para cada criterio define tres niveles de logro (logrado, medianamente logrado, no logrado) con un puntaje asociado.

---

## 7. 🔴 El cuestionario a los socios

### 7.1 Dónde estás parado

Recapitulá el recorrido del integrador con Vida Sana:

```text
  ENTREVISTAS               NEGOCIACIÓN                CUESTIONARIO
  Junta + profesores   ──►  Junta vs. profesores  ──►  a los socios
        │                         │                         │
     minuta                 minuta actualizada        ratificar o
                            (si algo cambió)          rectificar
```

Tenés una minuta de las entrevistas. La negociación pudo haberla modificado: si se decidió algún cambio, **actualizás la minuta**. Y ahora falta la pata que apareció en la reunión y nadie había convocado: los **socios**.

Los socios son un universo **numeroso y que no conocés**: no hay posibilidad de entrevistarlos uno por uno. Son quienes van a usar un servicio del gimnasio, quienes reservan clases, asisten, pagan sus planes, se enteran de que se liberó un lugar o avisan una ausencia. Lo que quieren es poder usar el servicio, no que vengan a reclamarles pagos o clases no tomadas. Para ese universo, la técnica es el **cuestionario**.

### 7.2 Para qué sirve: ratificar o rectificar

El cuestionario tiene un objetivo concreto: **validar el éxito que tendrían las propuestas de la minuta** con quienes van a usarlas. Todo lo que en la negociación se decidió sobre los socios sin preguntarles, ahora se les pregunta:

- ¿Se van a instalar una aplicación?
- ¿Pretenden otros canales de comunicación?
- ¿Usan Mercado Pago?
- ¿Cuál es su rango etario?
- ¿Ven la misma problemática que los profesores al momento de pagar las cuotas?
- ¿Ven un problema con el ausentismo?
- Si se pone una cámara, ¿no viene nadie más? ¿O vienen más, porque la zona es fea y se sienten más seguros?
- ¿Reclaman que se demora mucho en atender los pagos, y por eso no quieren esa interacción?

Con las respuestas, las definiciones que salieron de las entrevistas y la negociación se **ratifican o se rectifican**. El riesgo que esto evita: tener una expectativa de uso sobre una solución, invertir dinero y tiempo, y descubrir después que no tiene llegada.

### 7.3 Cuestionario y entrevista: mismo trabajo, distinto ritmo

Las dos técnicas se **preparan** y se **realizan**. La entrevista es presencial y **sincrónica**: pasa en el momento. El cuestionario se **dispara** y las respuestas van llegando. Después viene un tiempo de **análisis** para validar o no lo que se relevó en las entrevistas.

Para que ese análisis exista, hacen falta respuestas. En el integrador son ficticias, pero se necesitan: con **tres o cuatro respuestas** por cuestionario ya se puede analizar qué resultado dio y si apareció alguna novedad respecto de los requerimientos.

### 7.4 Cómo se escriben las preguntas

La herramienta es Google Forms. Pero el formato de las preguntas **no es el de la entrevista**, por una razón de volumen: vas a tener que analizar *n* respuestas. Si todas son abiertas, obtener información se vuelve tedioso y complicado. Por eso el cuestionario va con **preguntas de respuesta discreta**: ¿cuántas clases tomás por mes? ¿Cuánto hace que estás en el gimnasio? ¿Cuál es tu rango de edad?

Antes de dar por buena una pregunta, hacé el ejercicio: **pensá cuáles serían las posibles respuestas, y qué información te daría cada una**. Si todas las preguntas se responden con "poco, más o menos, mucho, medio", la información es subjetiva y no sirve para tomar una decisión. Los rangos numéricos y las opciones concretas, sí.

Y las preguntas son **de este caso**, no genéricas de gimnasio. Salen de la información de la minuta y de lo que apareció en la negociación: "¿te molestaría que te graben?" es una pregunta de Vida Sana; "¿qué te gusta de tu gimnasio?" no le sirve a nadie. Todo apunta al objetivo, que es **definir un sistema**.

El cuestionario **se corrige en clase**. Para cada pregunta tenés que poder defender el criterio: si es abierta o cerrada, por qué, y qué esperabas que el socio te responda. Va dirigido a los socios solamente; a los profesores y a la Junta ya los entrevistaste.

Las reglas de diseño de la clase 03 siguen valiendo (formato fijo para tabular, escalas balanceadas, nada fuera del alcance, probar antes de distribuir).

### 7.5 Variante: el cuestionario complementario

Hay un segundo uso del cuestionario, distinto del anterior. Después de las entrevistas quedan puntos sin resolver, o datos que no surgieron: cuántos socios tiene el centro, cuántas sucursales piensa abrir, cuántos docentes tiene el plantel. Esa información no se puede preguntar a los socios, y no amerita otra entrevista. Se arma un cuestionario **complementario a la entrevista**, dirigido a los mismos entrevistados, para que completen esas preguntas en un documento y **terminar el dimensionamiento** del negocio.

No es un cuestionario para recolectar cantidades de respuestas: es una **entrevista asincrónica**. "Te mando esto, me lo respondés, y después ahondamos."

> **Para el parcial, si te preguntan:** *¿Para qué sirve el cuestionario a los socios después de la negociación?*
> Para validar con los usuarios finales las propuestas de la minuta: ratificar o rectificar lo decidido en las entrevistas y la negociación antes de invertir en una solución que podría no tener llegada.

> **Para el parcial, si te preguntan:** *¿Por qué las preguntas de un cuestionario deben tener respuestas discretas?*
> Porque hay que analizar muchas respuestas: las preguntas abiertas son tediosas de procesar, y las escalas subjetivas ("poco", "mucho") no dan información para tomar decisiones. Las respuestas discretas (rangos, opciones concretas) se tabulan y se comparan.

> **Para el parcial, si te preguntan:** *¿Qué diferencia hay entre el cuestionario a los usuarios y el cuestionario complementario a la entrevista?*
> El cuestionario a los usuarios se dispara a un universo numeroso para validar propuestas con muchas respuestas. El complementario se envía a los mismos entrevistados para obtener datos específicos que no surgieron en la entrevista (cantidades, dimensionamiento); funciona como una entrevista asincrónica.

---

## 8. 🟢 Kernel sentences

Una **kernel sentence** (glosa: sentencia núcleo) es una oración con un único sujeto y un único verbo. Hay un trabajo de investigación, hecho con colegas de La Plata, sobre escribir requerimientos con sentencias núcleo. Sirve como práctica de escritura, y sobre todo más adelante, cuando se avance con escenarios. Lo que ya sabés de rol + verbo + objeto va en la misma dirección.

---

## 9. 🟡 Información operativa de la clase

**Material en el aula virtual**
- En la solapa de introducción a la ingeniería de requisitos está el **documento de buenas prácticas** de escritura de requerimientos (el que se trabajó impreso la clase anterior) y el paper de kernel sentences.
- El **compilado de RF y RNF** corregidos en clase (las fotos del pizarrón, consolidadas) va al Drive de cada equipo.
- Se van a subir ejercicios individuales **opcionales** para quien quiera más práctica, y un cuestionario de autoevaluación en el aula, cuando esté probado.

**Tareas para la clase siguiente (17/09)**
- **Cuestionario a socios** en Google Forms (cuenta de la facultad o personal, a elección). Entregar el link. Conseguir tres o cuatro respuestas ficticias. Se corrige en clase: tener el criterio de cada pregunta.
- **Minuta actualizada**, si la negociación cambió algo. Los equipos documentadores entregan la minuta de la negociación en el aula.
- **Caso de uso del Metro de Madrid**: a diferencia de otros enunciados, el material es un video donde una persona le explica a los usuarios cómo usar las nuevas máquinas expendedoras de billetes de las estaciones principales. El caso de uso se arma a partir de cómo se le cuenta al usuario.
- Los equipos que recibieron la indicación con la devolución del museo: **rehacer los RF del museo** siguiendo las pautas de escritura, en un documento de Drive (no en imagen), y mandar el link.
- Seguir cargando en el **Padlet** las correcciones que se repiten, para tenerlas a mano antes de la próxima entrega.

**Rúbrica de casos de uso**
- Archivo en la carpeta de Drive de cada equipo. Grupal. Cierra el **miércoles 30/09, 21 h**. Corrección en línea a pedido; compilado de la cátedra después de la entrega. Va impresa al parcial, con autoevaluación en birome de otro color.

**Parcial**
- Primera fecha: **jueves 01/10**. Incluye una parte de **role playing** (reunión o entrevista), individual. Es casi imposible armar un recuperatorio de esa parte: no faltar. El enunciado llega **una semana antes**, para preparar la entrevista.
- El parcial es por partes: si te va mal en casos de uso, recuperás solo casos de uso.

**TP de investigación**
- La cátedra está seleccionando casos (el aeropuerto de Denver u otro problema similar). El producto se hace con una herramienta de inteligencia artificial, con miras a producir material para compartir. Lleva nota, pero corre en paralelo: no es tema de parcial. Se presenta antes o después del parcial, a definir.

---

## 10. ✅ Checkpoint — cierre de la unidad

Sin respuestas: van al complemento.

1. ¿Qué dos cosas distintas evalúan las dos filas de la rúbrica sobre el nombre del caso de uso?
2. Dado el nombre "Registrar obras y empleados del museo", ¿en qué nivel de logro cae y por qué?
3. ¿Qué tiene que cumplir un criterio de rúbrica para que dos personas lleguen al mismo puntaje?
4. ¿Por qué la rúbrica se arma en equipo y no la entrega la cátedra?
5. ¿Qué se hace con la rúbrica el día del parcial, y para qué sirve la birome de otro color?
6. ¿Por qué a los socios de Vida Sana se les hace un cuestionario y no una entrevista?
7. ¿Qué relación hay entre la minuta de la negociación y el cuestionario a los socios?
8. ¿Qué ejercicio hay que hacer con cada pregunta antes de darla por buena?
9. ¿Qué tiene de malo una pregunta cuyas opciones son "poco / más o menos / mucho"?
10. ¿Cuándo corresponde un cuestionario complementario a la entrevista, y a quién va dirigido?
11. ¿Qué es una kernel sentence y con qué tema futuro de la materia se relaciona?

---

## Cierre de la unidad

Esta clase te mostró al ingeniero de requisitos en su momento más difícil: cuando los que deciden no se ponen de acuerdo. La respuesta no es elegir un bando, es **mediar** con conocimiento técnico, **documentar** cada acuerdo como un requerimiento verificable y **cerrar** lo que se pueda cerrar sin dejar a nadie afuera. Y cuando la mesa se queda sin datos, porque apareció una parte interesada que nadie convocó, se vuelve a las técnicas de elicitación: el cuestionario para los muchos, el complementario para los pocos. La rúbrica es la misma lógica aplicada a tu propio trabajo: criterios que se puedan verificar, para que la calidad no dependa de la opinión.

**FIN DE LA PARTE 2 — FIN DEL APUNTE MAESTRO CLASE 05**
