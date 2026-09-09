# 📘 APUNTE MAESTRO — Clase 04 · Entrevistas y redacción de requisitos — Parte 5

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Unidad:** `clase04` · Jueves 03/09/2026 · Presencial (Campus)
**Parte 5:** La defensa — escribir requerimientos y romper los mal escritos.

---

## Sobre esta parte

**Qué cubre:** la dinámica de defensa de requerimientos y para qué sirve · las reglas de redacción que salieron de las correcciones, cada una con su versión antes y después · los seis casos trabajados, completos · el caso especial del canal de notificación y la unidad vacía · la rúbrica de casos de uso · el cierre operativo de la clase · el checkpoint de toda la unidad.

**Marcas:** 🔴 central, evaluable · 🟡 secundario · 🟢 mencionado al pasar · 🕳️ madriguera.

## De dónde venís

De la Parte 3: las seis características de calidad, los dos niveles del RF, la estructura objeto + atributo + valor + unidad, y las reglas de negocio. De la Parte 4: el catálogo de atributos. De la Parte 2: lo relevado en la mesa. De la clase 02: casos de uso y su notación.

Una aclaración honesta sobre esta parte: las versiones "después" son las que quedaron aceptadas en la puesta en común. En algún caso pudieron seguir puliéndose en voz alta. Ante cualquier duda entre lo que ves acá y el marco de la Parte 3, **manda el marco.**

---

## 1. 🔴 La dinámica: defender a muerte, y romper

Cinco minutos después de la entrevista, cada equipo tenía que tener escritos dos o tres RF y al menos un RNF que restrinja a cada uno. Y después de eso, un juego.

Cada equipo pasa y escribe uno de sus requerimientos funcionales y su no funcional. Los tiene que **defender a muerte**: son los que eligió. Y otro equipo pasa a hacer de **super ingeniero de requisitos**, cuya tarea es **tirarlos abajo**: encontrar falencias en cómo está escrito.

El ejemplo de arranque:

> *"El fondo tiene que ser azul."*

¿Qué fondo? ¿El fondo de pantalla? ¿El de una tipografía? ¿Qué azul? ¿Azul Francia? ¿Celeste? ¿"Todo" azul? ¿Todo qué, todo de una página web? Es imposible defenderlo, porque cada pregunta muestra una interpretación posible distinta. **Eso es la ambigüedad hecha ejercicio**: un requerimiento que no sobrevive a tres preguntas no era un requerimiento.

Para qué sirve el juego: entrenar los dos roles a la vez. El que escribe aprende a anticipar las preguntas; el que rompe aprende a hacerlas. En el parcial vas a estar en el primer rol, y quien corrige en el segundo.

## 2. 🔴 Las reglas de redacción, con sus casos

Estas reglas no estaban escritas en ningún lado: salieron una por una de las correcciones hechas en vivo. Cada una viene con el requerimiento tal como se escribió y como quedó. Todas son aplicaciones de las seis características de la Parte 3, y te conviene ver cuál viola cada "antes".

### Regla 1 — El sujeto es el rol, no "el sistema"

> ❌ *El sistema registrará el ingreso de socios.*
> ✅ *El socio registrará su ingreso al establecimiento.*

"El sistema" como sujeto oculta **quién** ejecuta la acción — el actor —, y el actor es lo que después va a definir el caso de uso. Además, en este proyecto "el sistema" es justamente lo que estás eligiendo entre tres: no podés poner como sujeto algo que todavía no existe. El requerimiento se expresa desde el punto de vista del actor (característica *consistente*).

Y el segundo requerimiento del mismo par cambió de forma:

> ❌ *El socio tendrá una credencial para poder ingresar.*
> ✅ *El medio de acceso es una credencial.*

"Tendrá una credencial" parece un RF pero no describe una acción del sistema; describe una **condición** sobre cómo se ingresa. Reescrito como RNF: objeto (medio de acceso) + atributo/valor (es una credencial).

### Regla 2 — Nada de forma impersonal

> ❌ *Se necesita conexión de internet para completar la operación.*
> ✅ *El socio necesita conexión de internet para completar el pago.*

Dos correcciones en una oración. **"Se necesita" → ¿quién?** La forma impersonal deja sin responsable: ¿el socio necesita la conexión? ¿el centro? ¿la plataforma? Y **"la operación" → ¿cuál?** El objeto era ambiguo; el requerimiento habla del pago, entonces dice "el pago". Es exactamente el criterio 5 de la corrección del diseño de entrevista (Parte 2 §5): en preguntas y en requerimientos, el "se" borra al actor.

### Regla 3 — Nada de voz pasiva

> ❌ *Los socios serán registrados.*

Voz pasiva es sujeto tácito: no sé quién registra, no sé qué hace, y no sé de quién es el caso de uso que sale de acá. **Olvidate de la voz pasiva.** Es una regla de sintaxis que ya conocés de la escuela; acá tiene consecuencia directa en el modelo. La forma correcta es la de la Regla 1: rol + verbo + objeto.

Ya sabés desde la clase 01 que el verbo *usar* tampoco entra, por ambiguo. Misma familia.

### Regla 4 — Un objeto suelto no es un requerimiento

> ❌ *Plataforma de pago.*
> ✅ *La integración con el medio de pago es por medio de APIs.*

"Plataforma de pago" es un sustantivo. No tiene verbo, no tiene propósito: ¿qué pasa con la plataforma de pago? ¿Se necesita? ¿Se elige? ¿Se integra? Lo que el equipo quería decir era que el pago con tarjeta requiere un proveedor externo —una pasarela de pago— y que la solución tiene que **integrarse** con él. Escrito: objeto (integración con el medio de pago) + atributo/valor (es por medio de APIs). Y ahora sí es un RNF, de interoperabilidad (Parte 4 §2.3).

**API** (*Application Programming Interface*): conjunto de operaciones que un sistema expone para que otro sistema le pida cosas por programa, sin pasar por una pantalla.

### Regla 5 — Sacar lo redundante

> ❌ *Los socios deberán poder ingresar y registrarse en el establecimiento sin requerir la asistencia del personal.*
> ✅ *Los socios deberán poder registrarse en el establecimiento sin requerir la asistencia del personal.*

"Ingresar y registrarse": si el registro es lo que habilita el ingreso, "ingresar" no agrega nada y abre la duda de si son dos acciones distintas. Un verbo por requerimiento. Lo mismo en su RNF: *"El tiempo máximo de ingreso/registro…"* quedó *"El tiempo máximo de registro…"*.

### Regla 6 — El RNF afirma: "es", no "debe ser"

> ❌ *El tiempo máximo de registro debe ser de 30 seg.*
> ✅ *El tiempo máximo de registro es de 30 seg.*

El RNF describe una propiedad que el sistema **tiene**; se escribe como afirmación de un valor: **el verbo ser**. "Debe ser" suena a deseo o a recomendación; "es" es la especificación. Fijate que los cinco ejemplos de la Parte 4 §4 están todos en "es" o "son".

### Regla 7 — Cuidado con las palabras que suenan técnicas y no miden nada

Tres quedaron marcadas: **"tiempo real", "online", "automáticamente".** Las tres suenan a RNF y ninguna lo es, porque ninguna se puede verificar: ¿cuánto es tiempo real, 2 segundos o 200 milisegundos? ¿"online" respecto de qué? ¿"automáticamente" quiere decir sin intervención de quién? Cada una se reemplaza por su valor con unidad: "el tiempo máximo entre el evento y la notificación es de 2 segundos"; "sin intervención del personal".

### Regla 8 — Precisar el vocabulario del dominio

Al escribir el requerimiento de notificación de clases disponibles, apareció una pregunta: *"¿y si la clase se canceló?"*. Resultó que "disponible" se estaba usando para tres cosas distintas, y hubo que separarlas: una clase **disponible** es la que tiene un lugar libre; **no disponible** la que está completa; **cancelada** la que no se da. Un mismo requerimiento no puede cubrir los tres estados, porque cada uno dispara algo distinto — y avisarle a alguien que ya estaba anotado que "hay lugar" es un error.

Hay que ver bien los estados de las cosas del dominio antes de escribir. Y hay un segundo aviso ahí: *"después de esto hay que ver bien los estados de las clases"* — es el tipo de precisión de vocabulario que se va a formalizar más adelante en la materia.

### Regla 9 — Objeto + atributo + valor + unidad, siempre; y qué hacer cuando falta la unidad

Este es el caso especial y merece su propia sección.

## 3. 🔴 El caso del canal de notificación

El requerimiento tal como se escribió:

> *El sistema enviará notificaciones / avisos de las clases disponibles a los socios*
> *— a través de: WhatsApp · Mail*

Primer problema, el de siempre: "el sistema" como sujeto, y "a través de" mezclando el RF (notificar) con el RNF (por qué canal). Hubo que separarlos.

Segundo problema, el interesante. Se intentó descomponer el RNF:

> - Objeto: notificación
> - Atributo: medio / canal de comunicación
> - Valor: WhatsApp / email
> - Unidad: **….**

La unidad quedó vacía. Porque WhatsApp o email **es un medio, un canal de comunicación** — no es un número. Y ahí vino la pregunta: *¿cómo hago para medir este requerimiento no funcional? ¿Qué puedo mirar para decir si estoy cumpliendo que las notificaciones se adecúan a esta restricción?*

Las respuestas que salieron son las métricas que lo vuelven verificable:

- **Cantidad de mensajes enviados.** Es una métrica, aunque floja: si mandé 120 y uno fue a una dirección falsa, "lo mandé" no alcanza.
- **Enviados contra recibidos con éxito.** Mejor: mide que el socio efectivamente lo tuvo.
- **Cantidad de notificaciones por minuto.** *"La cantidad de notificaciones por minuto es de 100."* Ahora hay valor y unidad, y si el sistema no logra mandar 100 por minuto, hay algo que ajustar — seguramente en la arquitectura — para que se dé. Es capacidad (Parte 4 §2.2).

Y una tercera consideración: el canal puede ser una **preferencia**, del socio o del tipo de notificación. Hay quien pide "avisame por WhatsApp, el mail no lo miro", y hay avisos urgentes que no pueden ir por un canal que se lee tarde. Ese dato es relevable en la entrevista y puede convertirse en un atributo más del requerimiento.

Lo que quedó aceptado en la puesta en común:

> ✅ *Los medios de comunicación de las notificaciones a los socios de clases disponibles son WhatsApp o email.*

⚠️ **Atención.** Esa versión aceptada nombra objeto, atributo y valor, pero sigue sin unidad numérica: es una **restricción de canal**, y como tal es legítima — restringe la solución. Pero por sí sola no es medible. Para el examen: cuando el atributo es un canal, un formato o una tecnología, escribí la restricción **y acompañala con una métrica de cumplimiento** (tasa de entrega, notificaciones por minuto). Eso cierra las dos cosas: la restricción y su verificación.

Del mismo equipo, el segundo par quedó limpio:

> ✅ *El socio recibirá una notificación de su registro de asistencia presencial a las instalaciones.*
> ✅ *El tiempo máximo de la notificación de registro de asistencia es de 2 segundos.*

Fijate "presencial a las instalaciones": es la precisión que se agregó para que el registro no se confunda con otra cosa (¿asistencia a una clase? ¿al centro?). Y el 2 segundos es del sistema, no del socio (Parte 3 §3.2).

> **Para el parcial, si te preguntan:** *"Las notificaciones se enviarán por WhatsApp" — ¿es un RNF bien escrito?*
> Es una restricción legítima sobre el canal, pero está en voz pasiva (no dice quién envía) y no es medible por sí sola. Bien escrito: "El medio de las notificaciones a los socios es WhatsApp", acompañado de una métrica verificable, por ejemplo "la cantidad de notificaciones por minuto es de 100" o "el porcentaje de notificaciones recibidas con éxito es de al menos 99%".

## 4. 🔴 Los casos completos

Los seis requerimientos que pasaron por la mesa, con lo que se discutió de cada uno.

### Caso A — Notificación de clases disponibles
Ya visto en la sección 3. Se le sumó la discusión de a quién notificar cuando se libera un lugar en una clase con lista de espera: ¿al primero de la lista —el que espera hace más tiempo— o a todos, y el primero que responde se anota? Son dos definiciones distintas, válidas ambas, y hay que elegir una: *hay escenarios, un montón.* Lo que no se puede es dejarlo sin definir, porque de eso depende cómo se inscribe el socio.

### Caso B — Registro de asistencia y tiempo de respuesta
> ✅ *El socio podrá registrar su asistencia.*
> ✅ *El tiempo máximo de la notificación de registro de asistencia es de 2 segundos.*

La discusión del valor (10 → 5 → 3 → 2) y la aclaración de que el tiempo es del sistema están en la Parte 3 §3.2. Al lado, el RF de discapacidad del mismo equipo:
> ✅ *El socio podrá registrarse como socio con discapacidad.*
Nació como "el sistema debe registrar y señalar cuando un cliente tiene algún tipo de discapacidad" y pasó por dos correcciones: el sujeto (Regla 1) y el término — *cliente* → *socio*, porque en este dominio el que viene a hacer la clase es el socio, y "cliente" es la Junta (Parte 2 §5).

### Caso C — Ingreso con credencial
> ✅ *El socio registrará su ingreso al establecimiento.*
> ✅ *El medio de acceso es una credencial.*
Regla 1, dos veces.

### Caso D — Consulta de la Junta
> ✅ *La junta directiva debe poder consultar los asociados que no están al día.*
> ✅ *El tiempo máximo desde que la junta directiva solicita el reporte de los socios que no están al día hasta una respuesta es de 3 segundos.*

Este RNF está bien armado y vale la pena mirarlo: nombra el **rol**, el **evento que dispara la medición** (desde que solicita), el **objeto** (el reporte) y el **valor con unidad**. Es la forma completa del ejemplo 1 de la Parte 4 §4.

Del mismo equipo salió otra idea: *"que esté disponible las 24 horas"*. Se lo llevó a su forma general: eso es disponibilidad del sistema, y se escribe como *"la aplicación está disponible el 99,9% del tiempo"* (Parte 4 §2.5) — con la advertencia de que 99,9% compromete una contingencia (Parte 3 §3.3).

### Caso E — Pago con tarjeta
> *RF: El socio podrá pagar con tarjeta de crédito.*
> *RNF 1: Se necesita conexión de internet para completar la operación.*
> *RNF 2: Plataforma de pago.*

El caso más rico, porque abrió tres discusiones.

**¿Es "con tarjeta de crédito" un RF?** No del todo. El RF a nivel alto, bien macro, es **"el socio pagará las cuotas"**. Tarjeta de crédito, efectivo o una plataforma virtual son **distintas formas de implementar** ese pago: especificaciones del medio. Si querés el RF a nivel detallado, "el socio podrá pagar con tarjeta de crédito" se sostiene — ¿de quién es el requerimiento? del socio — pero sabiendo que estás un nivel abajo del caso de uso.

**¿Qué es regla de negocio acá?** *"Las cuotas se cobran del 1 al 10 de cada mes"* y *"el socio debe tener la cuota paga para poder realizar actividades"*. Existen con o sin sistema (Parte 3 §5). Alguien las llamó "precondición" — es lo mismo dicho desde el caso de uso.

**Los dos RNF.** El primero, corregido por la Regla 2: *"El socio necesita conexión de internet para completar el pago."* Y ojo con de quién es la conexión: si el socio paga desde su casa, la conexión es un **recurso que él necesita** para ejecutar el escenario. Pero si el pago se cobra en el centro, con un posnet en el mostrador, entonces la conectividad es del centro — y ahí la característica a escribir es **conectividad redundante**, "para que nadie se vaya sin pagar": dos conexiones, una que respalda a la otra. Mismo requerimiento, dos objetos posibles, según quién ejecuta. El segundo, por la Regla 4: *"La integración con el medio de pago es por medio de APIs."*

### Caso F — Registro sin asistencia del personal
> ✅ *Los socios deberán poder registrarse en el establecimiento sin requerir la asistencia del personal.*
> ✅ *El tiempo máximo de registro es de 30 seg.*
Reglas 5 y 6. Y fijate "sin requerir la asistencia del personal": es la condición de medición, igual que "sin asistencia externa" en el ejemplo 3 de la Parte 4.

## 5. 🔴 La rúbrica de casos de uso

Cerró la clase con algo que ya sabías que existía y ahora tiene forma.

Una **rúbrica** es una tabla que dice, para cada elemento a evaluar, cuándo está **bien logrado**, **más o menos logrado** o **sin lograr**. La rúbrica de casos de uso evalúa los elementos del diagrama: **actores, generalizaciones (herencias), inclusiones, relaciones**. Para cada uno, qué tiene que cumplir para estar bien.

Tres cosas sobre ella:

- **Es similar a la que se usa para corregir.** No idéntica, pero mide lo mismo.
- **La armás vos.** No la da la cátedra: no tendría sentido, porque el ejercicio de armarla es lo que te hace internalizar los criterios. Se construye a partir del feedback acumulado.
- **La llevás al parcial.** Antes de entregar el caso de uso, la leés, mirás tu diagrama y verificás que cumplís. Es tu autocorrección.

Todo el feedback que recibiste hasta acá —los seis criterios de la Parte 2, las nueve reglas de esta parte, las correcciones de notación de las entregas de casos de uso— es insumo de esa rúbrica. Y una observación que se hizo sobre las últimas entregas: la notación mejoró mucho en los equipos que usaron herramientas adecuadas para dibujar, en vez de hacerlo a mano.

> **Para el parcial, si te preguntan:** *¿Qué es una rúbrica de evaluación de casos de uso y para qué sirve?*
> Es una tabla que define, para cada elemento del diagrama (actores, generalizaciones, inclusiones, relaciones), los criterios que determinan si está bien logrado, parcialmente logrado o sin lograr. Sirve como instrumento de corrección y de autocorrección: se verifica el diagrama contra ella antes de entregarlo.

---

## Cierre operativo de la clase

- **Entregable de la semana siguiente:** la minuta de lo trabajado en la entrevista (ver Parte 2). Alimenta la definición de requerimientos del integrador y el diseño del cuestionario a los socios.
- **El parcial tiene una parte de casos de uso y una segunda parte de RF y RNF.** Se va a trabajar con enunciados de parciales anteriores como práctica (por ejemplo, el del museo).
- **TP de investigación** (asignación en las próximas clases): a cada equipo se le da un caso **real y paradigmático de fracaso** de un proyecto de software — proyectos en los que se puso mucha plata, se avanzó el desarrollo y por alguna circunstancia no salió. La tarea es analizar qué pasó desde la ingeniería de requisitos: si falló al principio o se fue dando en el camino, para no repetirlo. Se hace con apoyo de IA y se presenta en clase.
- **Equipos diezmados:** repartir tareas entre los presentes para poder avanzar.

---

## ✅ Checkpoint — Unidad clase04

Respondé sin mirar. Las respuestas van al complemento.

1. ¿Por qué la entrevista es una técnica cara, y qué dos consecuencias tiene eso sobre a quién se entrevista y qué se pregunta?
2. ¿Qué convierte a una minuta en el acuerdo de alcance, y qué tres condiciones tiene que cumplir?
3. En el centro de entrenamiento, ¿quién es el cliente de la consultora, quiénes son usuarios y quiénes stakeholders? ¿Por qué los socios no son clientes?
4. Los profesores pidieron penalizar a los socios que faltan. ¿Cuál era la necesidad detrás, y cómo se llegó a ella?
5. Nombrá las seis características de calidad de un requerimiento y decí cuál viola "el sistema debe agilizar el registro de asistencias".
6. Escribí "Registrar socio" a nivel detallado, para el rol profesor, con al menos tres datos de entrada.
7. ¿Qué es un RNF, de dónde salen sus restricciones según la factibilidad, y con qué estructura se escribe para que sea medible?
8. Descomponé en objeto, atributo, valor y unidad: "El tiempo máximo desde que la junta directiva solicita el reporte hasta la respuesta es de 3 segundos."
9. Enumerá las ocho características del modelo de calidad del producto de la ISO/IEC 25010 y ubicá "notificaciones por minuto = 100" y "integración por APIs" en la que corresponda.
10. ¿Qué cambió en la ISO 25010:2023, y qué diferencia hay entre *safety* y *security*?
11. Corregí: "Se necesita que los socios sean notificados automáticamente." Nombrá cada regla que aplicaste.
12. "Las cuotas se cobran del 1 al 10 de cada mes" — ¿RF, RNF o regla de negocio? ¿Por qué?
13. ¿Por qué "las notificaciones son por WhatsApp o email" no es medible por sí sola, y qué le agregarías?
14. ¿Quién arma la rúbrica de casos de uso, qué elementos evalúa y en qué momento se usa?

---

## Cierre de la unidad

La clase 04 fue la primera en la que la materia dejó de describir técnicas y te sentó a ejecutarlas: entrevistaste, relevaste, escribiste requerimientos y los defendiste. Lo que queda de acá es un método de tres pasos que se repite en cada entregable de acá al final: **entender la necesidad detrás del pedido → escribirla con rol, verbo y objeto → restringirla con algo que se pueda medir.** Todo lo demás —la ISO, las reglas, la rúbrica— es el equipamiento para hacer esos tres pasos sin ambigüedad.

**FIN DE LA PARTE 5 — FIN DE LA UNIDAD clase04**
