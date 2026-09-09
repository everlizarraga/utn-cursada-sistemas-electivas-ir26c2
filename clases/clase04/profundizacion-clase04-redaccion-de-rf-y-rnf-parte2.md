# 🔬 PROFUNDIZACIÓN — Clase 04 · Redacción de RF y RNF — Parte 2: Los errores

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Unidad:** `clase04` · **Tema único:** cómo se escriben requerimientos funcionales y no funcionales que la cátedra da por bien escritos.
**Parte 2:** los errores que se corrigen, cómo se ven, cómo se arreglan; checklist de revisión; ejercicios de corrección con respuestas.

---

## Sobre esta parte

La Parte 1 te dio el método para escribir. Esta te da el ojo para revisar: los errores concretos que la cátedra marca, con el requerimiento tal como se escribió y como quedó. Al final, un checklist para pasar antes de entregar, y ejercicios donde el requerimiento mal escrito lo corregís vos.

**Marcas:** 🔴 central, evaluable · 🟡 secundario · 🕳️ madriguera.

---

## 1. 🔴 Errores de sujeto: quién hace la cosa

Los tres errores más frecuentes son el mismo error con tres caras: **el requerimiento no dice quién ejecuta la acción.** Y el "quién" es lo que después define el actor del caso de uso. Sin sujeto claro, el requerimiento no se puede modelar.

### 1.1 "El sistema" como sujeto

> ❌ *El sistema registrará el ingreso de socios.*
> ✅ *El socio registrará su ingreso al establecimiento.*

**Cómo se ve:** la oración empieza con "El sistema", "La aplicación", "La solución".
**Por qué está mal:** "el sistema" no es un rol; es lo que estás especificando. Oculta quién dispara la acción. Y en un proyecto de selección de software, el sistema es justamente lo que todavía no existe.
**Cómo se arregla:** preguntá *¿quién hace que esto pase?* y ponelo de sujeto. Si la respuesta es "nadie, es un proceso automático" (un recordatorio nocturno, por ejemplo), nombrá el componente concreto que lo ejecuta y el evento que lo dispara: *"El módulo de notificaciones enviará a las 20:00 el recordatorio de clase a los inscriptos del día siguiente."* Componente con nombre, no "el sistema" genérico.

Un caso derivado del mismo par:

> ❌ *El socio tendrá una credencial para poder ingresar.*
> ✅ *El medio de acceso es una credencial.*

**Cómo se ve:** parece un RF (tiene rol y verbo) pero el verbo no es una acción del sistema: "tendrá" describe una condición.
**Cómo se arregla:** reconocé que es un RNF —una restricción sobre cómo se ingresa— y escribilo como tal: objeto (medio de acceso) + valor (credencial).

### 1.2 Forma impersonal: "se necesita", "se registra", "se envía"

> ❌ *Se necesita conexión de internet para completar la operación.*
> ✅ *El socio necesita conexión de internet para completar el pago.*

**Cómo se ve:** el verbo va con "se" y no hay sujeto.
**Por qué está mal:** *¿quién necesita?* No se sabe. Podría ser el socio, el centro, la plataforma de pago — y cada uno da un requerimiento distinto (ver 3.3).
**Cómo se arregla:** reemplazá el "se" por el rol. Y aprovechá para revisar el objeto: "la operación" era ambiguo (¿cuál?); se cambió a "el pago".

La misma regla aplica a las preguntas de entrevista: *"¿De qué forma **se** controlaban los ingresos?"* no releva quién controla, que es exactamente lo que querés saber.

### 1.3 Voz pasiva: "serán registrados", "será notificado"

> ❌ *Los socios serán registrados.*
> ✅ *El profesor registrará al socio.* / *El socio se registrará.*

**Cómo se ve:** "ser" + participio. Sujeto tácito.
**Por qué está mal:** no sé quién registra, no sé de quién es el caso de uso, y la oración pasa el filtro de "suena formal" sin decir nada.
**Cómo se arregla:** dala vuelta. El que recibe la acción pasa a objeto; el que la hace pasa a sujeto. Si no sabés quién la hace, **todavía no tenés el requerimiento**: volvé al relevamiento.

**Y el verbo *usar*, que ya conocés:** *"El socio usará la aplicación para…"* no dice qué hace. Es ambiguo por diseño. Reemplazalo por la acción concreta.

## 2. 🔴 Errores de objeto: sobre qué recae la cosa

### 2.1 Objeto suelto, sin verbo

> ❌ *Plataforma de pago.*
> ✅ *La integración con el medio de pago es por medio de APIs.*

**Cómo se ve:** un sustantivo o frase nominal sola. "Plataforma de pago." "Base de datos centralizada." "Módulo de reportes."
**Por qué está mal:** no tiene verbo, no tiene propósito. ¿Qué pasa con la plataforma de pago? ¿Se necesita, se elige, se integra?
**Cómo se arregla:** preguntá *¿qué quería decir el que lo escribió?* Casi siempre es una restricción tecnológica (RNF): que la solución tiene que integrarse con algo, soportar algo, correr sobre algo. Escribila con verbo **es**: *"La integración con X es por medio de Y."*

### 2.2 Objeto ambiguo

> ❌ *…para completar la operación.*
> ✅ *…para completar el pago.*

**Cómo se ve:** "la operación", "el proceso", "la tarea", "la información", "los datos".
**Por qué está mal:** admite más de una lectura. ¿Qué operación?
**Cómo se arregla:** nombrá la cosa del dominio: el pago, la inscripción, la asistencia, el reporte de morosos.

### 2.3 Vocabulario del dominio sin definir

Al escribir *"notificación de clases disponibles"*, apareció *"¿y si la clase se canceló?"*. "Disponible" estaba tapando tres estados distintos:

| Estado | Significa | Dispara |
|---|---|---|
| Disponible | tiene al menos un lugar libre | avisar a la lista de espera |
| No disponible | está completa | anotar en lista de espera |
| Cancelada | no se da (menos de 3 inscriptos) | avisar a los inscriptos |

**Cómo se ve:** una palabra del negocio que cubre situaciones distintas con consecuencias distintas.
**Cómo se arregla:** antes de escribir, listá los estados de las cosas del dominio (clase, socio, plan, pago) y usá una palabra por estado. Un requerimiento que avisa "hay lugar" a alguien que ya estaba inscripto es un error de este tipo.

### 2.4 Redundancia

> ❌ *Los socios deberán poder ingresar y registrarse en el establecimiento…*
> ✅ *Los socios deberán poder registrarse en el establecimiento…*

**Cómo se ve:** dos verbos unidos por "y" donde uno implica al otro.
**Por qué está mal:** abre la duda de si son dos acciones separadas (¿se puede ingresar sin registrarse?).
**Cómo se arregla:** un verbo por requerimiento. Si de verdad son dos acciones, son dos RF.

## 3. 🔴 Errores de clasificación: qué cosa es

### 3.1 RF que en realidad es una decisión de implementación

> ⚠️ *El socio podrá pagar con tarjeta de crédito.*

No está mal escrito. Pero "con tarjeta de crédito" no es lo que el socio *hace*: es *cómo* lo hace. El RF a nivel alto, bien macro, es **"El socio pagará las cuotas."** Tarjeta, efectivo, transferencia o plataforma virtual son formas de implementarlo.

**Cómo se arregla:** dejá el RF en la acción (*pagar cuotas*) y bajá el medio a RNF si es una restricción real del cliente (*"El medio de pago aceptado es tarjeta de crédito o débito"*). Si el cliente **exige** tarjeta, entonces es un RNF de restricción; si lo mencionó como ejemplo, no es requerimiento.

### 3.2 Regla de negocio escrita como requerimiento

> ❌ *RF: El sistema no permitirá realizar actividades sin la cuota paga.*
> ✅ *Regla de negocio: El socio debe tener la cuota paga para realizar actividades.*
> ✅ *RF asociado: El profesor podrá verificar el estado de cuota del socio al registrar su asistencia.*

**Cómo se ve:** "el sistema no permitirá", "el sistema validará que", "solo si".
**Por qué está mal:** la política existe sin sistema. Al escribirla como RF la mezclás con lo que el sistema hace, y pierde trazabilidad (no sabés que es una norma del negocio que puede cambiar por decisión de la Junta).
**Cómo se arregla:** la regla va a su lista. El RF describe la acción que la respeta.

### 3.3 RNF con el objeto equivocado: ¿de quién es la restricción?

El RNF *"El socio necesita conexión de internet para completar el pago"* es correcto **si el socio paga desde su casa**. Pero si el pago se cobra en el mostrador, la conexión no es del socio: es del centro. Y entonces el RNF cambia de objeto:

> *La conectividad a internet del centro es redundante (dos enlaces independientes).*

— "para que nadie se vaya sin pagar". Mismo relevamiento, dos RNF distintos según quién ejecuta el escenario.

**Cómo se arregla:** al elegir el objeto (Paso 2 de la Parte 1), preguntá *¿quién está ejecutando el RF cuando esta restricción aplica?*

## 4. 🔴 Errores de forma en el RNF

### 4.1 "Debe ser" en vez de "es"

> ❌ *El tiempo máximo de registro debe ser de 30 seg.*
> ✅ *El tiempo máximo de registro es de 30 seg.*

El RNF afirma una propiedad que el sistema tiene. Verbo **ser**, presente. "Debe ser", "deberá", "tiene que ser" suenan a deseo o recomendación, no a especificación.

### 4.2 Palabras que suenan técnicas y no miden nada

> ❌ *…en tiempo real.* · *…online.* · *…automáticamente.* · *…rápido.* · *…ágil.* · *…eficiente.* · *…intuitivo.* · *…moderno.*

Ninguna es verificable. ¿Cuánto es tiempo real: 2 segundos o 200 milisegundos? ¿Automáticamente sin intervención de quién?

**Cómo se arregla:** cada una se reemplaza por valor + unidad + condición:
- *tiempo real* → *el tiempo máximo entre el evento y la notificación es de 2 segundos*
- *automáticamente* → *sin intervención del personal del centro*
- *intuitivo* → *el tiempo máximo de la primera inscripción sin asistencia es de 5 minutos para el 80% de los socios*
- *ágil* → tachalo y medí el tiempo (fue el primer RF que se tachó en la mesa)

### 4.3 Falta la condición de medición

> ⚠️ *La disponibilidad del sistema es de al menos el 99,9%.*
> ✅ *La disponibilidad del sistema es de al menos el 99,9% del tiempo, de lunes a sábado de 8 a 20.*

Sin horario, 99,9% anual admite casi 9 horas de caída al año, en cualquier momento — incluido el pico de las 18. Con horario, la exigencia es otra. Igual con tiempos: *desde qué evento* se cuenta. Y con usabilidad: *para qué porcentaje de usuarios*, *sin qué ayuda*.

### 4.4 Restricción de canal sin métrica

> ⚠️ *Los medios de las notificaciones son WhatsApp o email.*
> ✅ *Los medios de las notificaciones son WhatsApp o email.* + *El porcentaje de notificaciones recibidas con éxito es de al menos 99%.*

Legítima como restricción, no medible sola. Siempre con métrica al lado (Parte 1 §3, tercer ejemplo).

### 4.5 🟡 Objeto y atributo cruzados

En algún material vas a ver el ejemplo de disponibilidad descompuesto como *objeto: disponibilidad · atributo: tiempo*. Es la misma estructura con los rótulos cruzados. Por la regla, el objeto es lo que se mide (el sistema) y el atributo es su cualidad (la disponibilidad). Aplicá la regla; si te muestran la otra versión, reconocela.

## 5. 🔴 Checklist de revisión — pasalo antes de entregar

Para cada RF:
- [ ] ¿Empieza con un rol (no "el sistema", no "se", no voz pasiva)?
- [ ] ¿El verbo es una acción concreta (no "usar", "gestionar", "manejar")?
- [ ] ¿El objeto es una cosa del dominio con nombre (no "la información", "la operación")?
- [ ] ¿Tiene los datos de entrada, si es nivel detallado?
- [ ] ¿Es una sola acción (un verbo)?
- [ ] ¿Es lo que el usuario hace, o cómo se implementa? Si es cómo, bajalo a RNF.
- [ ] ¿Es una acción del sistema o una política del negocio? Si es política, va a reglas.
- [ ] ¿Se puede probar en pasos finitos?

Para cada RNF:
- [ ] ¿Está pegado a un RF concreto?
- [ ] ¿Tiene objeto, atributo, valor y unidad, señalables con el dedo?
- [ ] ¿El verbo es "es" / "son", presente?
- [ ] ¿Tiene condición de medición (desde qué evento, en qué horario, para quién)?
- [ ] ¿El objeto es de quien ejecuta el escenario?
- [ ] Si el atributo es un canal/tecnología, ¿tiene métrica al lado?
- [ ] ¿No contiene "tiempo real", "online", "automáticamente", "rápido", "intuitivo"?
- [ ] ¿El atributo se ubica en una característica de la ISO 25010?

Para cada regla de negocio:
- [ ] ¿Existiría sin el sistema?
- [ ] ¿Está en su propia lista, con origen?
- [ ] ¿Está asociada al RF que la respeta?

> **Para el parcial, si te preguntan:** *Indicá los errores de este requerimiento y corregilo: "Se enviará automáticamente una notificación a los socios."*
> Errores: forma impersonal (no dice quién envía), voz pasiva implícita, "automáticamente" no verificable, objeto incompleto (¿notificación de qué?). Corregido — RF: "El módulo de notificaciones enviará al socio en lista de espera el aviso de lugar disponible en la clase." RNF: "El tiempo máximo de envío del aviso, desde que se libera el lugar, es de 2 segundos."

---

## 6. ✏️ Ejercicios — Parte 2

Dominio: **una biblioteca de barrio** con socios, préstamos de hasta 14 días, un bibliotecario y una encargada que cobra multas.

**Ejercicio 1 — Corregí cada uno y nombrá el error.**
- a) *El sistema registrará los préstamos.*
- b) *Se devolverán los libros en el mostrador.*
- c) *Los socios serán notificados del vencimiento.*
- d) *Catálogo online.*
- e) *El bibliotecario podrá gestionar la información de los socios.*
- f) *La búsqueda de libros debe ser rápida.*
- g) *El socio usará la app para renovar el préstamo.*
- h) *El sistema no permitirá prestar a socios con multas impagas.*

**Ejercicio 2 — Clasificá y reescribí.** *"El bibliotecario podrá prestar un libro con lector de código de barras."* ¿Es RF, RNF o mezcla? Separalo.

**Ejercicio 3 — Completá el RNF.** *"La disponibilidad del catálogo es de al menos 99%."* ¿Qué le falta? Completalo para el horario de la biblioteca (lunes a viernes de 9 a 19).

**Ejercicio 4 — Canal + métrica.** La encargada quiere que los avisos de vencimiento lleguen por email. Escribí la restricción y su métrica.

**Ejercicio 5 — ¿De quién es la restricción?** *"Se necesita el libro escaneado para registrar la devolución."* Reescribilo dos veces: si la devolución la registra el bibliotecario en el mostrador, y si la registra el socio en un buzón de autodevolución.

**Ejercicio 6 — Integrador.** Del relevamiento: *"queremos que los socios renueven solos, que no puedan renovar si alguien más lo reservó, y que la renovación no tarde nada."* Escribí: 1 RF detallado, 1 RNF descompuesto, 1 regla de negocio.

---

## Respuestas — Parte 2

**Ejercicio 1**
- a) **"El sistema" como sujeto.** → *El bibliotecario registrará el préstamo de un libro a un socio indicando libro, socio y fecha.*
- b) **Forma impersonal**, y además es más regla que requerimiento. Regla de negocio: *Las devoluciones se reciben en el mostrador.* RF: *El bibliotecario registrará la devolución de un libro.*
- c) **Voz pasiva.** → *El módulo de notificaciones enviará al socio el aviso de vencimiento del préstamo.* (Y RNF asociado: *El tiempo máximo de envío del aviso es de 24 horas antes del vencimiento.*)
- d) **Objeto suelto.** Lo que quería decir es una restricción de acceso: *El acceso al catálogo es por medio de un sitio web.* + RNF de disponibilidad.
- e) **Verbo vago ("gestionar") y objeto vago ("la información").** → Son varios RF: *El bibliotecario podrá registrar un socio con DNI, nombre, apellido, domicilio y teléfono.* / *El bibliotecario podrá modificar los datos de un socio.* / *El bibliotecario podrá dar de baja a un socio.*
- f) **"Rápida" no mide.** → *El tiempo máximo de respuesta de una búsqueda de libros, desde que el socio la ejecuta, es de 2 segundos.*
- g) **"Usar" ambiguo.** → *El socio podrá renovar un préstamo vigente indicando el libro.*
- h) **Regla de negocio escrita como RF.** Regla: *Un socio con multas impagas no puede retirar libros.* RF asociado: *El bibliotecario podrá consultar el estado de multas de un socio al registrar un préstamo.*

**Ejercicio 2**
Mezcla. **RF:** *El bibliotecario registrará el préstamo de un libro a un socio.* **RNF (restricción tecnológica):** *El medio de identificación del libro es un código de barras.* — o, más preciso como interoperabilidad: *La lectura de códigos de barras es compatible con lectores estándar EAN-13.*

**Ejercicio 3**
Le falta la **condición de medición**: horario y período. → *La disponibilidad del catálogo es de al menos el 99% del tiempo, de lunes a viernes de 9 a 19.* Descomposición: objeto: catálogo · atributo: disponibilidad · valor: 99 · unidad: %.

**Ejercicio 4**
Restricción: *El medio de los avisos de vencimiento es email.*
Métrica: *El porcentaje de avisos de vencimiento entregados con éxito es de al menos 98%.* (O de tiempo: *El tiempo máximo de envío del aviso es de 48 horas antes del vencimiento.*)

**Ejercicio 5**
- Mostrador: *El bibliotecario necesita el lector de código de barras operativo para registrar la devolución.* → objeto: el puesto de mostrador; la restricción es del centro.
- Buzón: *El socio necesita que el buzón de autodevolución tenga lector de código de barras operativo.* → objeto: el buzón; la restricción es del equipamiento de autoservicio. Y aparece un RNF de disponibilidad del buzón que en el mostrador no existía.

**Ejercicio 6**
- **RF:** *El socio podrá renovar un préstamo vigente indicando el libro, por un período de hasta 14 días.*
- **RNF:** *El tiempo máximo de confirmación de la renovación, desde que el socio la solicita, es de 3 segundos.* Objeto: confirmación de renovación · atributo: tiempo máximo de respuesta · valor: 3 · unidad: segundos.
- **Regla de negocio:** *Un préstamo no puede renovarse si el libro tiene una reserva pendiente de otro socio.* Existe con o sin sistema; el RF la respeta.
- (Y "que no tarde nada" se tradujo en el RNF — nunca se escribe como "sin demora".)

---

## Cierre

El método de la Parte 1 escribe; el ojo de esta parte revisa. En el parcial y en cada entregable hacé las dos pasadas: primero armá con los pasos, después pasá el checklist. Los errores que la cátedra marca son siempre los mismos ocho o nueve; si el checklist da limpio, el requerimiento se defiende.

**FIN DE LA PARTE 2 — FIN DE LA PROFUNDIZACIÓN**
