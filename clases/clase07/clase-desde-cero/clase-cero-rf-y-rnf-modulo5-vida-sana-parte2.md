# Clase desde cero — RF y RNF — Módulo 5: Vida Sana párrafo por párrafo — Parte 2

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Eje:** Centro de Entrenamiento Vida Sana
**Marcas:** 🔴 central · 🟡 secundario · 🟢 al pasar · 🕳️ madriguera · ✏️ tu turno

---

## Sobre este documento

**Qué cubre:** los párrafos 7 a 12 del enunciado con el mismo método de la Parte 1 · la **consolidación**: lista completa de RF, RN, RNF y preguntas · la tabla de trazabilidad RF ↔ RNF · el pase por las ocho preguntas de M4 sobre el conjunto (omisiones y consistencia) · qué se hace con el conflicto entre socios y profesores.

**Qué NO cubre:** los casos de uso (M6).

## De dónde venís

De la Parte 1: RF-01 a RF-17, RN-01 a RN-17, RNF-01 a RNF-08, P-01 a P-15. Los identificadores continúan.

---

## Párrafo 7 🔴 — Los sectores sin profesor, hoy

📄 *Para el caso de los sectores sin profesor, la gestión de inscripciones y presencialidad, es realizada por cualquiera de los profesores que estén presentes en el centro de entrenamiento, que muchas veces están dando la clase y no prestan atención u olvidan anotar lo que pasa en el sector de musculación o de cardio (los dueños del gimnasio, que conforman la Junta Directiva, no están de acuerdo con contratar personal extra para el registro de alumnos).*

🔍 **Qué hay acá.** Descripción de **cómo se hace hoy** (los profesores anotan) y **dolor** (se olvidan). Y una decisión de la Junta que no es regla del negocio operativo sino **restricción del proyecto**: no se contrata personal. Eso tiene una consecuencia enorme sobre los RF: si nadie va a estar en el mostrador, **el socio tiene que poder hacerlo solo**. Es lo que ya decidimos en RF-01, RF-02 y RF-03 al ponerle "socio" como actor; este párrafo lo confirma.

✅ **RF:** ninguno nuevo. El párrafo **justifica el actor** de RF-01 a RF-03.

📏 **RN:** ninguna.

⚙️ **RNF:** uno transversal, del pedido de no contratar personal, con la condición de medición típica de usabilidad:
```
RNF-09  El tiempo máximo para que un socio complete la reserva de un turno en un sector de
        uso libre, la primera vez y sin asistencia del personal, es de 2 minutos para el 80%
        de los socios.                                                       [supuesto]
```
"Sin asistencia del personal" es la traducción verificable de "no contratar personal extra": el sistema tiene que ser usable sin nadie al lado.

❓ **Preguntas:**
- P-16. ¿Los socios de sectores libres también tienen plan (RN-13), o el uso de sectores es aparte?

🚫 **Lo que NO sale de acá:** "el profesor registra la presencialidad en los sectores". Es lo que pasa hoy y lo que **no quieren** que pase. Si lo escribís como RF, estás especificando el problema en vez de la solución.

---

## Párrafo 8 🔴 — Los cuatro registros en papel

📄 *Los dueños han observado que el control de todo ese circuito implica para los profesores muchos registros cruzados, ya que disponen de: una carpeta con una ficha por socio, donde se anotan sus planes, presentismo y pagos realizados. Una carpeta con el control de caja diario (que socio pagó, cuanto y qué –adelanto, saldo o plan completo). Una ficha que lleva cada socio donde se detalla inicio y fin del plan, y las clases en que estuvo presente (muchos se olvidan de llevar su ficha). Una carpeta con las clases y los socios anotados, donde se pinta con resaltador verde los presentes y con resaltador naranja los ausentes, los socios fijos están además anotados en color azul, y el resto en rojo.*

🔍 **Qué hay acá.** El párrafo más útil de todo el enunciado para encontrar **funciones de consulta**, y el que más gente saltea porque "es descripción". Cada registro en papel es **información que alguien necesita ver**. La pregunta para cada uno: **¿quién consulta esto y para qué?**

```
   ficha por socio (planes, presentismo, pagos)  → profesor y Junta la consultan
   caja diaria (quién pagó, cuánto, qué)         → la Junta la consulta
   ficha del socio (inicio/fin, presentes)       → el socio la consulta
   planilla de clase (presentes, ausentes,       → el profesor la consulta y
      fijos, resto)                                 el profesor registra el presente
```

Y aparece **vocabulario nuevo** que no está definido: *socio fijo*, *adelanto*, *saldo*. Y un dato de presentismo que necesita un RF que todavía no tenías: **alguien registra el presente en una clase con profesor**. Para los sectores libres ya está (RF-02); para las clases, no.

✅ **RF:**
```
RF-18  El profesor registra el presente de los socios de su clase.
RF-19  El socio registra su asistencia a una clase.                   ← alternativa a RF-18
RF-20  El profesor consulta la ficha de un socio (plan, presentismo, pagos).
RF-21  La Junta Directiva consulta la ficha de un socio.
RF-22  La Junta Directiva consulta la caja diaria (pagos por socio, monto y concepto).
RF-23  El socio consulta las clases en las que estuvo presente.
RF-24  El profesor consulta la planilla de su clase (anotados, presentes, ausentes, fijos).
```
RF-18 y RF-19 son la discusión de M2 §3.1: a nivel alto es "Registrar asistencia a clase"; a nivel detallado puede ser el profesor, el socio, o los dos. El enunciado no lo define (hoy lo hace el profesor, pero quiere dejar de hacerlo). Los dos van a la lista, y P-17 lo pregunta. RF-23 es el complemento de RF-13 (el socio consulta su plan): el plan y los presentes eran la misma ficha.

📏 **RN:**
```
RN-18  Un pago de plan puede ser un adelanto (seña), un saldo o el plan completo.
```

⚙️ **RNF** (supuestos):
```
RNF-10  El tiempo máximo de respuesta de la consulta de la ficha de un socio, desde que el
        profesor la solicita, es de 3 segundos.                              [supuesto]
RNF-11  La caja diaria es visible únicamente para la Junta Directiva.       [confidencialidad]
RNF-12  La cantidad máxima de pasos para que el profesor acceda a la planilla de su clase
        es de 3.                                                             [supuesto]
```
RNF-11 no es un supuesto arbitrario: los pagos son información de los dueños; que un profesor no la vea es la lectura razonable, pero se confirma (P-18).

❓ **Preguntas:**
- P-17. El presente en una clase con profesor: ¿lo registra el profesor, el socio al entrar, o el socio con un dispositivo en la sala?
- P-18. ¿Quién puede ver los pagos? ¿Solo la Junta, o también los profesores?
- P-19. ¿Qué es un **socio fijo**? ¿Uno con horario reservado permanente? ¿Cambia algo en la inscripción?
- P-20. ¿Qué diferencia hay entre adelanto y seña? ¿Son lo mismo?

🚫 **Lo que NO sale de acá:** los resaltadores. "Los presentes se muestran en verde y los ausentes en naranja" es un RNF de estética que **copia el medio actual**. Podés proponerlo como RNF de usabilidad si el cliente lo pide, pero no sale del enunciado: el enunciado describe el papel, no la pantalla.

---

## Párrafo 9 🟡 — Los roces

📄 *Además, como los profesores son 10, han surgido roces entre ellos y con los dueños por omisiones en las anotaciones, lo que a su vez generó discusiones con algunos socios, en especial respecto de los pagos.*

🔍 **Qué hay acá.** Dolor, puro. Ni un verbo de objetivo, ni una política. Test de tres preguntas: nada. Pero el dolor **dice qué calidad se espera**: si el problema son las omisiones y las discusiones sobre quién anotó qué, la solución tiene que dejar rastro de **quién registró cada cosa y cuándo**.

✅ **RF:** ninguno.

📏 **RN:** ninguna.

⚙️ **RNF** transversal, de seguridad (responsabilidad):
```
RNF-13  Cada registro de asistencia y cada registro de pago conserva el usuario que lo realizó
        y la fecha y hora en que se realizó.
```
No tiene número y es verificable por inspección: abrís un registro y está o no está. Es el RNF que **resuelve el dolor** del párrafo sin inventar una función.

❓ **Preguntas:** ninguna nueva.

🚫 **Lo que NO sale de acá:** "el sistema evita los roces entre profesores". Es un objetivo de negocio, no un requisito; no se puede verificar.

---

## Párrafo 10 🔴 — La identificación de socios

📄 *Los socios infieren en que tal vez sea porque no todos los profesores los conocen, sumado a que usan un criterio de identificación de socios al parecer poco fiable: las 3 primeras letras del nombre y las 2 primeras del apellido. Dos alumnos homónimos podrán tener códigos iguales..... y dos con nombres parecidos también!*

🔍 **Qué hay acá.** Un **cómo actual** que está mal (el código de 3+2 letras) y que hay que reemplazar. Es el caso de M1 §4.3 y M3 §4.2: no describe qué quiere lograr nadie; describe **una propiedad** del medio de identificación. RNF, transversal.

✅ **RF:** ninguno. (Registrar un socio nuevo, donde se le asigna el identificador, ya está implicado en RF-11: contratar un plan requiere existir como socio. Ver omisiones, más abajo.)

📏 **RN:** ninguna.

⚙️ **RNF:**
```
RNF-14  El identificador de socio es único por socio y lo asigna el sistema al alta.
```

❓ **Preguntas:**
- P-21. ¿El socio se identifica con credencial, con el celular, con DNI? Define el objeto del RNF siguiente (el medio de identificación) y afecta RF-02 y RF-19.

🚫 **Lo que NO sale de acá:** "el identificador es el DNI". Es una decisión de diseño razonable, pero no está en el enunciado y hay socios sin DNI argentino, menores, etc. Lo que sale es la **propiedad** (único, asignado por el sistema), no la implementación.

---

## Párrafo 11 🔴 — El pedido de los profesores

📄 *Los profesores han pedido a la Junta desentenderse de todo tipo de registro y acción, así como de la convocatoria a los socios en lista de espera, y poder así dedicarse solamente a dar las clases, porque entienden que así evitaran pérdidas de socios, y errores en el registro de clases.*

🔍 **Qué hay acá.** Ningún requisito nuevo, y sin embargo es un párrafo decisivo: es una **decisión de alcance** sobre el actor de casi todos los RF. "Desentenderse de todo registro y de la convocatoria" quiere decir que las funciones que hoy hace el profesor pasan al socio (autogestión) o a un aviso que el socio recibe. Ya lo aplicaste en RF-01 a RF-09 al poner "socio". Este párrafo es la **justificación** de esa elección; anotala como trazabilidad: si alguien pregunta "¿por qué el socio y no el profesor?", la respuesta está acá.

Y pone en duda RF-18: si los profesores quieren desentenderse de *todo* registro, ¿registran el presente? Refuerza P-17.

✅ **RF:** ninguno nuevo.

📏 **RN:** ninguna.

⚙️ **RNF:** ninguno. "Evitar pérdidas de socios" es objetivo de negocio, no medible en este nivel.

❓ **Preguntas:**
- P-22. ¿"Todo registro" incluye el presente en la clase? Si el profesor no registra nada, ¿cómo se sabe quién estuvo en una clase de pilates?

🚫 **Lo que NO sale de acá:** "el profesor no interactúa con el sistema". Sigue teniendo objetivos propios (RF-10, RF-16, RF-20, RF-24): consultar y cancelar no es "registro".

---

## Párrafo 12 🔴 — El conflicto y el bono

📄 *Los socios en general también se quejan por la anticipación con que deben informar una ausencia, ya que a veces faltan por imprevistos (por ej. cuando se sienten mal o se enfermó un familiar), y quisieran poder avisar una ausencia hasta una hora antes de la clase. Pero en ese caso, los profesores quieren que quienes están en la lista de espera se puedan enterar del lugar libre y solicitar ese cupo si así lo desean (tener en cuenta que los profesores pueden ganar un bono por el porcentaje de clases con cupo completo que dan en un mes).*

🔍 **Qué hay acá.** Tres cosas. **Un conflicto** entre RN-16 (avisar el día anterior) y lo que piden los socios (una hora antes). **Un RF** nuevo: el socio en lista de espera *solicita* el cupo (en RF-07 recibía el ofrecimiento; acá además puede pedirlo por iniciativa propia). Y **una regla de negocio** sobre el bono, con un umbral que no está.

✅ **RF:**
```
RF-25  El socio en lista de espera solicita un lugar liberado en la clase.
RF-26  La Junta Directiva consulta, por profesor y por mes, el porcentaje de clases dictadas
       con cupo completo.
```
RF-26 es el de M4 §6, ya corregido.

📏 **RN:**
```
RN-19  Un profesor cobra un bono mensual cuando su porcentaje de clases dictadas con cupo
       completo alcanza el umbral base.                          [valor del umbral: relevar]
RN-16' El socio debe informar su ausencia hasta una hora antes de la clase.   [propuesta de los socios;
                                                                               en conflicto con RN-16]
```

⚙️ **RNF** (del RF-25):
```
RNF-15  El tiempo máximo entre la liberación de un lugar por ausencia y su visibilidad para
        los socios en lista de espera es de 1 minuto.                        [supuesto]
```
Si el aviso es de una hora antes, el lugar se tiene que ver **rápido**, o nadie llega. Fijate cómo un RNF sale de la lógica del negocio, no de un número del enunciado.

❓ **Preguntas:**
- P-23. ¿La Junta acepta una hora de anticipación? ¿O un valor intermedio (por ejemplo, 3 horas)?
- P-24. ¿Cuál es el umbral del bono?
- P-25. Si dos socios en lista solicitan el mismo cupo, ¿gana el primero en solicitar, o el primero en la lista (RN-11)? Las dos reglas pueden chocar.

🚫 **Lo que NO sale de acá:** **la resolución del conflicto.** Vos no decidís si son 24 horas o una hora. Eso se **negocia** entre la Junta, los profesores y los socios, con vos como mediador: cada parte explica por qué pide lo que pide (los socios, imprevistos; los profesores, el bono y las clases completas), se buscan valores intermedios, y decide quien paga. Lo que sí hacés como ingeniero de requisitos es **detectarlo, documentarlo (RN-16 vs. RN-16') y llevarlo a la mesa**. Un requisito que elige una de las dos versiones sin negociación es un error que va a explotar en la validación.

> **Para el parcial, si te preguntan:** *Dos stakeholders piden requisitos incompatibles (por ejemplo, avisar con 24 horas vs. con 1 hora). ¿Qué hace el ingeniero de requisitos?*
> Detecta y documenta el conflicto, entiende la justificación de cada pedido, y convoca una reunión de negociación entre las partes en la que actúa como mediador para llegar a un acuerdo (un valor intermedio, una condición, o la prevalencia de una de las partes). No resuelve el conflicto por su cuenta ni redacta una de las dos versiones sin acuerdo; la decisión final la toma quien tiene la autoridad sobre el proyecto, típicamente el cliente que paga.

---

## Consolidación 🔴

### C.1 La lista completa

**Requerimientos funcionales (26)**

| ID | Actor | RF |
|---|---|---|
| RF-01 | Socio | reserva un turno en un sector de uso libre |
| RF-02 | Socio | registra su ingreso a un sector de uso libre |
| RF-03 | Socio | registra su salida de un sector de uso libre |
| RF-04 | Socio | se anota en una clase |
| RF-05 | Socio | se da de baja de una clase en la que está anotado |
| RF-06 | Socio | se anota en la lista de espera de una clase completa |
| RF-07 | Socio (en lista) | recibe el ofrecimiento del lugar liberado en la clase |
| RF-08 | Socio (en lista) | acepta o rechaza el ofrecimiento de un lugar liberado |
| RF-09 | Socio (anotado) | recibe el ofrecimiento de otro turno cuando su clase tiene menos de tres inscriptos |
| RF-10 | Profesor | consulta la cantidad de inscriptos y la lista de espera de su clase |
| RF-11 | Socio | contrata un plan de clases |
| RF-12 | Socio | paga su plan (seña o totalidad) |
| RF-13 | Socio | consulta el estado de su plan |
| RF-14 | Socio | informa su ausencia a una clase en la que está anotado |
| RF-15 | Socio | recupera una clase en la que informó su ausencia |
| RF-16 | Profesor | cancela una clase |
| RF-17 | Socio (anotado) | recibe el aviso de cancelación de su clase |
| RF-18 | Profesor | registra el presente de los socios de su clase |
| RF-19 | Socio | registra su asistencia a una clase (alternativa a RF-18, según P-17) |
| RF-20 | Profesor | consulta la ficha de un socio |
| RF-21 | Junta Directiva | consulta la ficha de un socio |
| RF-22 | Junta Directiva | consulta la caja diaria |
| RF-23 | Socio | consulta las clases en las que estuvo presente |
| RF-24 | Profesor | consulta la planilla de su clase |
| RF-25 | Socio (en lista) | solicita un lugar liberado en la clase |
| RF-26 | Junta Directiva | consulta el porcentaje de clases con cupo completo por profesor y mes |

**Reglas de negocio (19 + 1 en conflicto):** RN-01 a RN-19, y RN-16' como propuesta en conflicto con RN-16.

**Requerimientos no funcionales (15):**

| ID | Restringe a | RNF | Atributo (ISO 25010) |
|---|---|---|---|
| RNF-01 | RF-02 | tiempo máx. de confirmación del ingreso: 2 s | comportamiento temporal |
| RNF-02 | RF-07 | tiempo máx. baja → ofrecimiento: 5 min | comportamiento temporal |
| RNF-03 | RF-07 | medio del ofrecimiento: WhatsApp | (canal; + métrica de entrega) |
| RNF-04 | RF-12 | medios de pago: efectivo, débito, crédito | (medio) |
| RNF-05 | RF-12 | integración con plataforma de pago: APIs | interoperabilidad |
| RNF-06 | RF-14 | tiempo máx. de confirmación del aviso: 2 s | comportamiento temporal |
| RNF-07 | RF-17 | tiempo máx. cancelación → aviso: 2 min | comportamiento temporal |
| RNF-08 | RF-17 | medio del aviso de cancelación: WhatsApp | (canal) |
| RNF-09 | RF-01 | reserva sin asistencia: 2 min, 80% de socios | aprendizaje |
| RNF-10 | RF-20 | tiempo máx. de respuesta de la ficha: 3 s | comportamiento temporal |
| RNF-11 | RF-22 | caja diaria visible solo para la Junta | confidencialidad |
| RNF-12 | RF-24 | máx. 3 pasos hasta la planilla | operabilidad |
| RNF-13 | transversal | cada registro conserva usuario, fecha y hora | responsabilidad |
| RNF-14 | transversal | identificador de socio único, asignado por el sistema | corrección funcional / integridad |
| RNF-15 | RF-25 | liberación → visibilidad: 1 min | comportamiento temporal |

**Preguntas para la entrevista (27):** P-01 a P-25, más P-26 y P-27 que aparecen al buscar omisiones en C.3.

### C.2 Trazabilidad: qué RF no tiene RNF

La tabla de arriba se lee al revés para encontrar huecos. RF sin ningún RNF: RF-03, RF-04, RF-05, RF-06, RF-08, RF-09, RF-10, RF-11, RF-13, RF-15, RF-16, RF-18, RF-19, RF-21, RF-23, RF-26. Dieciséis. Eso no está mal en un primer pase, pero si te piden "al menos un RNF por RF", acá está la lista de trabajo. Muchos comparten el mismo RNF de tiempo de respuesta (anotarse, darse de baja, consultar); podés escribir uno por objeto. Ver "Tu turno".

### C.3 Las ocho preguntas sobre el conjunto

**Consistencia (pregunta 6).** RN-16 vs. RN-16': documentado como conflicto, no resuelto. RN-11 (orden de la lista) vs. RF-25 (solicitar por iniciativa): posible choque, es P-25. RF-18 vs. RF-19: no es inconsistencia, es una decisión pendiente (P-17); a nivel alto son el mismo "Registrar asistencia a clase".

**Errores (pregunta 7).** Recorré la lista buscando algo que contradiga una regla: ¿algún RF permite anotarse sin plan vigente? No, porque RN-14 se aplica en el escenario de RF-04. ¿Algún RF permite recuperar sin haber avisado? RF-15 dice "en la que informó su ausencia": respeta RN-17. Sin errores detectados.

**Omisiones (pregunta 8).** Esta es la que más rinde. Buscá complementos obvios y derivados:

- **Alta de socio.** RF-11 (contratar plan) presupone que el socio existe. ¿Quién lo registra la primera vez? Es el "encender el televisor" de esta lista. Se agrega:
  ```
  RF-27  El socio se registra en el centro de entrenamiento con sus datos personales.
         (o: El profesor registra un socio nuevo. → decide P-17/P-22)
  ```
  Consistente con RNF-14: al alta se asigna el identificador.
- **Baja de socio / baja de plan.** Complemento de RF-11. Se anota como pregunta (P-26: ¿un socio puede cancelar un plan? ¿con devolución?) más que como RF, porque el enunciado no lo insinúa.
- **Modificación de datos del socio.** Complemento de RF-27. Ídem, P-27.
- **Consulta de clases disponibles.** Para anotarse (RF-04) primero hay que **ver qué clases hay con lugar**. Derivado:
  ```
  RF-28  El socio consulta las clases y turnos con lugar disponible.
  ```
- **Alta de clases y turnos.** Alguien define qué clases existen, con qué profesor y en qué turno. La Junta, probablemente. Derivado:
  ```
  RF-29  La Junta Directiva registra una clase con su tipo, profesor, turno y capacidad.
  ```
  Consistente con RN-01 a RN-06.

Tres RF que no estaban en ningún párrafo y sin los cuales el resto no funciona. **Eso es lo que la lista DEO detecta**, y es lo que quien corrige busca primero.

### C.4 Qué se hace con el conflicto

RN-16 (24 horas) y RN-16' (1 hora) no pueden convivir. El camino:

1. **Documentarlo** como está acá: las dos versiones, quién pide cada una, y por qué (socios: imprevistos; profesores: bono y clases completas; Junta: probablemente ambas cosas).
2. **Buscar el costo oculto de cada opción**: con una hora, la lista de espera tiene que reaccionar en minutos (RNF-15) y probablemente haya lugares que se pierden igual; con 24 horas, socios que faltan sin avisar y no recuperan, y discusiones.
3. **Llevarlo a una reunión de negociación** con las tres partes y proponer alternativas: un plazo intermedio; "una hora antes, pero la clase se pierde igual si nadie toma el lugar"; "24 horas para recuperar, una hora para liberar el lugar".
4. **Registrar el acuerdo con nombre y apellido** de quién lo tomó, porque después alguien lo va a reclamar.

Nada de eso es redacción. Es el rol de mediador del ingeniero de requisitos, y en el parcial lo que se evalúa es que lo reconozcas y sepas qué hacer, no que elijas un número.

---

## ✏️ Tu turno

1. Escribí un RNF para cada uno de estos RF sin RNF, con la estructura completa, valor supuesto marcado y atributo del catálogo: **RF-04, RF-11, RF-13, RF-16, RF-26.**
2. Volvé al párrafo 8 y escribí el RNF de estética que **no** sacamos (los colores de la planilla), como si el cliente lo hubiera pedido. Objeto, atributo, valor.
3. Pasá RF-27 a RF-29 por las ocho preguntas de M4 §6 y marcá si alguno viola algo.

## ✅ Checkpoint

1. ¿Por qué el párrafo 7 no genera RF pero cambia el actor de varios?
2. ¿Qué pregunta le hacés a cada registro en papel del párrafo 8 para sacar funciones?
3. ¿Qué RNF resuelve el dolor del párrafo 9, y por qué es un RNF y no un RF?
4. ¿Por qué "el identificador es el DNI" no sale del párrafo 10?
5. ¿Qué tipo de decisión es el párrafo 11, si no genera requisitos?
6. ¿Cuáles son las tres omisiones que aparecieron en la consolidación y cómo las encontraste?
7. ¿Qué hacés con RN-16 y RN-16'? ¿Qué NO hacés?
8. De 26 RF, ¿cuántos son del socio? ¿Qué dice eso sobre el enunciado?
9. Si te piden "al menos un RNF por RF", ¿por dónde empezás?

## Qué viene en el Módulo 6

Con la lista consolidada, el paso siguiente es el diagrama: los RF de nivel alto son los nombres de los casos de uso, los actores ya están, los RNF no dibujan nada pero restringen los escenarios, y las reglas de negocio son precondiciones. El M6 arma el diagrama del gimnasio y explica cada decisión.

**FIN DEL MÓDULO 5 — PARTE 2**
