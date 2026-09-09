# 🔬 PROFUNDIZACIÓN — Clase 04 · Redacción de RF y RNF — Parte 1: El método

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Unidad:** `clase04` · **Tema único:** cómo se escriben requerimientos funcionales y no funcionales que la cátedra da por bien escritos.
**Parte 1:** clasificar, redactar un RF, redactar un RNF, plantillas, ejemplos resueltos, ejercicios con respuestas.

---

## Sobre este documento

Esto no es la clase. Es el método que la clase te pidió aplicar, aislado, en el orden en que lo usás. Leés, hacés los ejercicios, y salís sabiendo armar un RF y un RNF. La clase completa —entrevista, puesta en común, ISO entera— está en el apunte maestro de `clase04`; volvé ahí para el parcial.

**Marcas:** 🔴 central, evaluable · 🟡 secundario · 🕳️ madriguera.

**Alcance:** lo que la cátedra enseñó y corrige. Nada más.

---

## 1. 🔴 Las tres cosas que salen de una entrevista, y cómo distinguirlas en diez segundos

De cualquier relevamiento salen frases. Cada frase es una de tres cosas, o basura. Antes de escribir nada, clasificá.

| Es… | Si la frase… | Ejemplo |
|---|---|---|
| **RF** — requerimiento funcional | describe **una acción que el sistema ejecuta** o permite ejecutar. Responde *¿qué hace?* | El socio registrará su asistencia. |
| **RNF** — requerimiento no funcional | describe **una cualidad o restricción medible** de cómo se ejecuta esa acción. Responde *¿qué tan bien? ¿bajo qué condición?* | El tiempo máximo de registro de asistencia es de 2 segundos. |
| **Regla de negocio** | describe una política del negocio que **existiría aunque no hubiera sistema**. | Con menos de tres inscriptos, la clase se cancela. |

**El test de tres preguntas**, en orden:

1. *¿Esto pasaría igual si el centro siguiera en papel?* → Sí: **regla de negocio.** Se documenta aparte; no es requerimiento.
2. *¿Describe algo que alguien hace con el sistema?* → Sí: **RF.**
3. *¿Describe cuánto, cuán rápido, cuán seguro, por qué medio se hace algo del sistema?* → Sí: **RNF.** (Y tiene que estar pegado a un RF.)

Si no pasa ninguna, es una opinión, un deseo o un dato duro. No se escribe como requerimiento.

> **Para el parcial, si te preguntan:** *¿Cómo distinguís un RF de un RNF y de una regla de negocio?*
> El RF describe qué hace el sistema (una acción o servicio); el RNF describe cualidades o restricciones medibles sobre cómo lo hace; la regla de negocio es una política del dominio que existe independientemente del sistema y que el sistema debe respetar.

## 2. 🔴 Cómo se escribe un RF, paso a paso

### La estructura final

**Nivel alto:** `verbo en infinitivo + objeto`
**Nivel detallado:** `ROL + VERBO + OBJETO + (variable: datos de entrada)`

El nivel alto nombra una capacidad y es el nombre del caso de uso. El nivel detallado es el que va en el documento de requisitos y el que se corrige.

### Los cinco pasos

**Paso 1 — Sacá la capacidad del pedido.** Del relevamiento tomá el pedido y reducilo a *verbo en infinitivo + objeto*. El verbo es una acción concreta: registrar, consultar, pagar, notificar, inscribir, cancelar. El objeto es sobre qué recae.

> Pedido de los profesores: *"necesitamos saber de antemano si viene alguien con discapacidad."*
> Capacidad: **Registrar socio** (con su condición de discapacidad).

**Paso 2 — Identificá el rol que la ejecuta.** ¿Quién hace esto en el sistema? Si hay más de una respuesta, no elijas: **un RF por rol.** La capacidad de nivel alto los cubre a todos.

> ¿El profesor registra al socio? ¿El socio se registra solo? Las dos. Dos RF detallados, misma capacidad.

**Paso 3 — Escribí rol + verbo + objeto.** El verbo va en futuro ("registrará") o con "podrá" ("podrá registrar"). Las dos formas son válidas.

> *El socio podrá registrarse como socio con discapacidad.*
> *El profesor registrará al socio con discapacidad.*

**Paso 4 — Agregá la variable: los datos de entrada.** Es lo que vuelve al RF completo y testeable: sabés exactamente qué tiene que aceptar el sistema.

> *El profesor registrará al socio con su DNI, apellido, nombre, teléfono y tipo de discapacidad.*

**Paso 5 — Pasalo por el filtro.** Seis preguntas, una por característica:

| ¿…? | Si la respuesta es no |
|---|---|
| ¿Una única interpretación posible? | Ambiguo. Precisá el objeto o el verbo. |
| ¿Se sabe quién lo ejecuta? | Inconsistente. Poné el rol. |
| ¿Se sabe qué datos entran? | Incompleto. Agregá la variable. |
| ¿Se puede construir con lo que hay? | Irrealista. Bajá la pretensión. |
| ¿Se sabe de qué pedido salió? | No rastreable. Anotá el origen. |
| ¿Se puede probar en pasos finitos? | No verificable. Reescribí hasta que sí. |

### Ejemplo resuelto completo

Relevamiento: *"la Junta quiere saber quién está atrasado con la cuota."*

1. Capacidad: **Consultar socios morosos.**
2. Rol: la junta directiva. (Solo uno.)
3. Rol + verbo + objeto: *La junta directiva podrá consultar los socios que no están al día.*
4. Variable: ¿qué entra? Un criterio de corte. *…consultar los socios que no están al día **a una fecha dada**.*
5. Filtro: ¿"no están al día" es unívoco? Casi — depende de la regla de negocio que define "al día" (cuota paga del 1 al 10). Se anota como regla asociada. Pasa.

**Resultado:** *La junta directiva podrá consultar los socios que no están al día a una fecha dada.*
**Nivel alto (caso de uso):** *Consultar socios morosos.*
**Regla de negocio asociada:** *El socio está al día si pagó la cuota entre el 1 y el 10 del mes.*

> **Para el parcial, si te preguntan:** *Redactá un requerimiento funcional a nivel detallado.*
> Rol + verbo + objeto + datos de entrada: "La secretaría de alumnos registrará un alumno con su DNI, apellido, nombre, teléfono, email, fecha de ingreso y carrera." A nivel alto: "Registrar alumno."

## 3. 🔴 Cómo se escribe un RNF, paso a paso

### La estructura final

`El [ATRIBUTO] de [OBJETO] es de [VALOR] [UNIDAD] [condición de medición].`

Cuatro piezas obligatorias:

- **Objeto:** el componente o proceso afectado. Suele ser el objeto del RF, o el resultado de ejecutarlo (la notificación, el reporte, el registro).
- **Atributo:** la cualidad que se mide. Sale del catálogo de la ISO/IEC 25010 (tabla de la sección 5).
- **Valor:** el número.
- **Unidad:** la escala.

Y una quinta que separa un RNF correcto de uno defendible: la **condición de medición** — desde qué evento se cuenta, en qué horario, con qué usuarios, sin qué ayuda.

### Los seis pasos

**Paso 1 — Partí del RF que vas a restringir.** Un RNF nunca flota solo. Escribí al lado el RF.

> RF: *El socio podrá registrar su asistencia.*

**Paso 2 — Elegí el objeto.** ¿Qué cosa concreta se va a medir? Acá: el registro de asistencia, o la confirmación que el socio recibe.

> Objeto: **el registro de asistencia** (más precisamente, su confirmación al socio).

**Paso 3 — Elegí el atributo, del catálogo.** ¿Qué te importa de ese objeto? ¿Cuánto tarda? ¿Cuántos a la vez? ¿Qué tan seguro? Los profesores dijeron que tomar asistencia les llevaba 15-20 minutos: lo que importa es **el tiempo**.

> Atributo: **tiempo máximo de respuesta** (eficiencia de desempeño → comportamiento temporal).

**Paso 4 — Fijá valor y unidad. Negociá hasta que sea realista.** ¿10 segundos? Para un escaneo, mucho. ¿5? ¿3? La referencia: *"viste cuando aparecen los tres puntitos y decís ok"*. 2.

> Valor: **2** · Unidad: **segundos**.

**Paso 5 — Agregá la condición de medición.** ¿Desde cuándo se cuenta? Desde que el socio escanea. ¿De quién es el tiempo? **Del sistema, no del socio**: no es que el socio tiene 2 segundos para escanear; es que el sistema tarda como máximo 2 segundos en confirmar.

> Condición: **desde que el socio registra hasta que recibe la confirmación**.

**Paso 6 — Escribí en presente afirmativo.** Verbo **es**. Nada de "debe ser", "deberá", "tiene que".

**Resultado:**
> *El tiempo máximo de confirmación del registro de asistencia, desde que el socio lo registra, es de 2 segundos.*
> - Objeto: registro de asistencia (su confirmación)
> - Atributo: tiempo máximo de respuesta
> - Valor: 2
> - Unidad: segundos

### Segundo ejemplo resuelto

RF: *La junta directiva podrá consultar los socios que no están al día.*

1. RF: el de arriba.
2. Objeto: **el reporte** de socios que no están al día.
3. Atributo: la Junta va a consultarlo en el momento → **tiempo de respuesta**.
4. Valor y unidad: 3 segundos (un reporte, no una confirmación instantánea).
5. Condición: **desde que la junta directiva solicita el reporte hasta que obtiene respuesta.**
6. Presente afirmativo.

> *El tiempo máximo desde que la junta directiva solicita el reporte de socios que no están al día hasta obtener respuesta es de 3 segundos.*

Fijate que este RNF lleva el **rol** adentro (la junta directiva) y el **evento disparador** (solicita). Es la forma completa.

### Tercer ejemplo: cuando el atributo no es un número

RF: *El socio recibirá una notificación de las clases disponibles.*

Lo que se quiere restringir es **el canal**: WhatsApp o email. Objeto: notificación. Atributo: medio de comunicación. Valor: WhatsApp / email. Unidad: **no hay**. Es una restricción legítima —limita la solución— pero **no es medible sola**.

Regla: **cuando el atributo es un canal, un formato o una tecnología, escribí la restricción y pegale una métrica de cumplimiento.**

> *El medio de las notificaciones a los socios es WhatsApp o email.*
> *El porcentaje de notificaciones recibidas con éxito por el socio es de al menos 99%.*
> (o: *La capacidad de envío de notificaciones es de 100 por minuto.*)

Ahora hay algo que contar.

> **Para el parcial, si te preguntan:** *Redactá un RNF para "el huésped puede reservar una cochera" y descomponelo.*
> "El tiempo máximo de confirmación de una reserva de cochera, desde que el huésped la solicita, es de 2 segundos." Objeto: confirmación de reserva · Atributo: tiempo máximo de respuesta · Valor: 2 · Unidad: segundos.

## 4. 🔴 Plantillas

Copiá la forma, cambiá las piezas.

**RF nivel alto**
> `[Verbo infinitivo] [objeto]` — *Registrar asistencia. Consultar morosos. Pagar cuota. Notificar cupo.*

**RF nivel detallado**
> `El/La [rol] [verbo futuro / podrá + infinitivo] [objeto] con [dato1, dato2, dato3].`
> *El socio podrá cancelar su inscripción a una clase indicando clase, fecha y motivo.*

**RNF de tiempo**
> `El tiempo máximo de [proceso/resultado], desde [evento], es de [N] [segundos/minutos].`

**RNF de disponibilidad**
> `La disponibilidad de [sistema/módulo] es de al menos [N]% del tiempo, [horario].`

**RNF de capacidad**
> `La capacidad de [proceso] es de [N] [operaciones] por [minuto/hora].`
> `El sistema soporta [N] usuarios concurrentes [condición].`

**RNF de usabilidad**
> `El tiempo máximo de [tarea] en la primera ejecución sin asistencia es de [N] minutos, para el [N]% de los usuarios.`

**RNF de restricción tecnológica / canal** (siempre con métrica al lado)
> `El medio de [objeto] es [canal].` + `El porcentaje de [objeto] [recibidas/completadas] con éxito es de al menos [N]%.`
> `La integración con [sistema externo] es por medio de [APIs / protocolo].`

**Regla de negocio** (se documenta, no se numera como requisito)
> `[Sujeto del negocio] [condición del negocio].`
> *Solo los socios que avisaron una ausencia pueden recuperar la clase.*

## 5. 🔴 De qué característica sale cada atributo

La ISO/IEC 25010 tiene ocho características. Para redactar, esto es lo que necesitás de cada una: qué atributos típicos ofrece y en qué unidad se miden.

| Característica | Atributos que vas a usar | Unidad típica |
|---|---|---|
| **Eficiencia de desempeño** | tiempo de respuesta · transacciones por segundo · usuarios concurrentes · uso de CPU/memoria | segundos · ops/seg · cantidad · % |
| **Fiabilidad** | disponibilidad · tiempo medio entre fallos · tiempo de recuperación | % del tiempo · horas · minutos |
| **Usabilidad** | tiempo de aprendizaje de una tarea · % de usuarios que la completan sin ayuda · puntaje SUS | minutos · % · puntos |
| **Seguridad** | cifrado en tránsito/reposo · autenticación · trazabilidad de acciones · vulnerabilidades detectadas | sí/no + estándar · cantidad |
| **Compatibilidad** | integración con sistemas externos · conformidad con estándar | API/protocolo · % conformidad |
| **Mantenibilidad** | cobertura de pruebas · % de funcionalidades testeables automáticamente | % |
| **Portabilidad** | tiempo de instalación · entornos soportados · éxito de despliegues | minutos · cantidad · % |
| **Adecuación funcional** | % de casos de uso cubiertos · defectos por funcionalidad | % · cantidad |

Cuando no sepas qué atributo poner, mirá la columna del medio y preguntá: *¿cuál de estos le duele al cliente?* Los profesores: tiempo. La Junta: disponibilidad y reportes. Un socio que paga desde su casa: seguridad del pago.

🕳️ **Madriguera — el catálogo completo**
Cada característica tiene subcaracterísticas, formas de medición y errores comunes documentados en la norma; está entero en la Parte 4 del apunte maestro. Para redactar, la tabla de arriba alcanza. *Volvé al camino.*

## 6. 🔴 Reglas de negocio: qué hacer con ellas

No se convierten en RF ni en RNF. Se documentan **en su propia lista**, y se asocian al RF que las respeta. En un documento de requisitos van en una sección aparte ("Reglas de negocio") con su origen (quién la dijo).

Del centro de entrenamiento, las que salieron:

- Las cuotas se cobran del 1 al 10 de cada mes.
- El socio debe tener la cuota paga para realizar actividades.
- Con menos de tres inscriptos, la clase se cancela.
- Solo los socios que avisaron una ausencia pueden recuperar la clase.
- Los planes son de 4, 6, 8 o 12 clases por mes calendario.

Cuando escribas *"El socio podrá inscribirse a una clase"*, la regla *"con menos de tres inscriptos se cancela"* no va dentro del RF: va al lado, como regla que el caso de uso tiene que contemplar.

---

## 7. ✏️ Ejercicios — Parte 1

Dominio distinto al del TP, a propósito: **una veterinaria** con tres veterinarios, turnos, historia clínica por mascota, y una recepcionista que cobra.

**Ejercicio 1 — Clasificar.** Para cada frase: RF, RNF, regla de negocio, o ninguna.
- a) El veterinario registrará la consulta en la historia clínica de la mascota.
- b) No se atiende sin turno, salvo urgencias.
- c) El tiempo máximo para recuperar una historia clínica es de 3 segundos.
- d) Queremos que el sistema sea moderno.
- e) La recepcionista cobrará la consulta indicando medio de pago e importe.
- f) La historia clínica se conserva 10 años después del último turno.

**Ejercicio 2 — RF, cinco pasos.** Pedido de la recepcionista: *"los dueños nos llaman todo el día para pedir turno; queremos que lo saquen solos."* Escribí la capacidad de nivel alto, el o los roles, y el RF a nivel detallado con variable.

**Ejercicio 3 — RNF, seis pasos.** Para el RF del ejercicio 2, escribí un RNF de tiempo con su descomposición en objeto, atributo, valor, unidad y condición.

**Ejercicio 4 — RNF no numérico.** La veterinaria quiere que los recordatorios de turno lleguen por WhatsApp. Escribí la restricción y la métrica que la vuelve verificable.

**Ejercicio 5 — Del pedido al conjunto.** Pedido del dueño: *"quiero ver al final del día cuánto se cobró y de qué manera."* Escribí: 1 RF detallado, 1 RNF asociado, y la regla de negocio que se desprende si además dice *"y nadie cierra caja sin que cuadre".*

---

## Respuestas — Parte 1

**Ejercicio 1**
- a) **RF.** Rol (veterinario) + verbo (registrará) + objeto (consulta) + dónde (historia clínica).
- b) **Regla de negocio.** Existe aunque los turnos sean en un cuaderno.
- c) **RNF.** Objeto: historia clínica · atributo: tiempo de recuperación · valor 3 · segundos.
- d) **Ninguna.** "Moderno" no es verificable. Habría que repreguntar qué le duele para que quiera "moderno".
- e) **RF.** Rol + verbo + objeto + variable (medio de pago, importe).
- f) **Regla de negocio** (política de conservación, existe en papel también). Si el sistema debe hacerla cumplir, de ella se deriva un RNF de retención: *"El período de conservación de las historias clínicas es de 10 años desde el último turno."*

**Ejercicio 2**
- Nivel alto: **Solicitar turno.**
- Roles: el dueño de la mascota (se lo saca solo) y la recepcionista (sigue pudiendo cargarlo por teléfono). Dos RF.
- RF detallado: *El dueño podrá solicitar un turno para su mascota indicando mascota, veterinario, fecha y franja horaria.*
- (Segundo RF: *La recepcionista podrá registrar un turno para un dueño indicando dueño, mascota, veterinario, fecha y franja horaria.*)

**Ejercicio 3**
- RF: el del ejercicio 2.
- Objeto: la confirmación del turno.
- Atributo: tiempo máximo de respuesta (comportamiento temporal).
- Valor / unidad: 3 segundos (es una confirmación con verificación de disponibilidad, no un escaneo).
- Condición: desde que el dueño confirma la solicitud.
- RNF: *El tiempo máximo de confirmación de un turno, desde que el dueño confirma la solicitud, es de 3 segundos.*

**Ejercicio 4**
- Restricción: *El medio de los recordatorios de turno es WhatsApp.*
- Métrica: *El porcentaje de recordatorios recibidos con éxito por el dueño es de al menos 98%.* (Alternativa de tiempo: *El tiempo máximo de envío del recordatorio es de 24 horas antes del turno.*)

**Ejercicio 5**
- RF: *El dueño de la veterinaria podrá consultar el cierre de caja del día, discriminado por medio de pago.*
- RNF: *El tiempo máximo desde que el dueño solicita el cierre de caja hasta obtener respuesta es de 5 segundos.* (O de disponibilidad: *La disponibilidad del módulo de caja es de al menos 99% durante el horario de atención.*)
- Regla de negocio: *El cierre de caja se realiza solo cuando el total cobrado coincide con el total registrado.* No es RF ni RNF: es una política de la veterinaria. El RF de cierre la respeta.

---

## Qué viene en la Parte 2

Los errores que se corrigen en clase y en el parcial —"el sistema" como sujeto, la forma impersonal, la voz pasiva, el objeto suelto, "debe ser", las palabras que suenan técnicas y no miden— cada uno con su antes/después real y la regla para no cometerlo. Y ejercicios de corrección: te doy requerimientos mal escritos, los arreglás, comparás.

**FIN DE LA PARTE 1**
