# 📗 COMPLEMENTO — Clase desde cero · RF y RNF — Parte 1 (Módulos 1 a 4)

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Complementa a:** `clase-cero-rf-y-rnf-modulo1` a `-modulo4`
**Contenido:** respuestas de los "Tu turno" y de los checkpoints, en formato de examen. No hubo dudas de sesión que destilar.

---

## Módulo 1 — Antes de escribir

### ✏️ Tu turno

1. **"Si un socio se baja, los profesores llaman al primero de la lista de espera para ofrecerle el lugar."** RF. No existiría sin sistema como acción del sistema (hoy se hace a mano y se quiere dejar de hacer), y hay un actor con un objetivo: el socio en lista quiere enterarse. "Los profesores llaman" es el cómo actual, no el actor del requisito.
2. **"Para contratar el plan deben reservar su lugar pagando una seña o la totalidad."** Mezcla: RF (el socio contrata un plan; el socio paga su plan) más una regla de negocio (la contratación se hace pagando seña o totalidad).
3. **"Tiempo mínimo 30 min y máximo 120 min en sectores sin profesor."** Regla de negocio: existe con carpetas y resaltadores.
4. **"Los profesores han pedido desentenderse de todo registro y acción."** Nada: no es requisito ni regla. Es una decisión de alcance que cambia el actor de varios RF (del profesor al socio).
5. **"Los socios quisieran avisar una ausencia hasta una hora antes."** Regla de negocio propuesta, en conflicto con la vigente (el día anterior). No se resuelve redactando: se negocia.
6. **"Los profesores pueden ganar un bono por el porcentaje de clases con cupo completo."** Regla de negocio (con un umbral que falta), y de ahí se deriva un RF de la Junta: consultar ese porcentaje por profesor.

### ✅ Checkpoint

1. Porque un sistema es un conjunto de elementos interrelacionados para lograr un fin común, y ese fin no es del sistema: es de quienes lo piden y lo usan. El sistema no tiene objetivos ni inicia acciones; responde a un disparo externo. Actor es quien tiene el objetivo.
2. Socio: anotarse a una clase. Profesor: consultar quién está anotado en su clase. Junta Directiva: consultar los pagos por socio.
3. Dos actores. Un actor es un rol, no una persona: cuando registra la limitación de un alumno actúa como profesor, cuando se anota a yoga actúa como socio.
4. Cuando el disparo es por tiempo, sin acción humana: un proceso que corre solo. Se modela como subsistema-actor. En el gimnasio, el vencimiento del plan al mes de la primera clase: un subsistema notificador avisa al socio.
5. ¿Existiría esta frase aunque no hubiera ningún sistema, con carpetas y resaltadores? Si sí, es regla de negocio.
6. Mezcla. Reglas de negocio: las capacidades por tipo (8, 7, 5, 8). RF: el socio se anota en una clase (donde la regla se aplica y, si está completa, deriva a lista de espera). No hay RNF ahí; "controlar" con el sistema como sujeto es la trampa.
7. Porque es justificación: explica por qué existe la regla de avisar el día anterior, pero no describe algo que un actor haga (RF), una restricción medible (RNF) ni una política en sí (RN). Es contexto.
8. Se parecen en que las dos parecen RF y no lo son. Se diferencian en el defecto: "tendrá una credencial" es un componente disfrazado de función (es RNF sobre el medio de acceso, sin unidad); "tarda poco" es un RNF sin valor (le falta el número y la unidad).

## Módulo 2 — El requerimiento funcional

### ✏️ Tu turno

1. **Capacidad máxima por tipo.** No hay RF adentro: son cuatro reglas de negocio (pilates 8, cardio 7, musculación 5, yoga/funcional/stretching 8). Se aplican en el escenario de *El socio se anota en una clase*: si está completa, no se anota, o pasa a lista de espera.
2. **Comunicaciones por WhatsApp.** RF: *El profesor envía un aviso a los socios de su clase.* RNF aparte: *El medio de los avisos del profesor a los socios es WhatsApp.* "Plantillas" queda como pregunta: ¿el profesor elige entre textos predefinidos?
3. **Alertados por exceso de tiempo.** Voz pasiva. RF: *El profesor recibe el aviso de que un socio excedió el tiempo máximo de uso de un sector.* Regla aparte: el máximo es de 120 minutos. Y ojo: el enunciado del gimnasio no pide este aviso; si se agrega, es una propuesta declarada.
4. **Gestionar planes.** RF: *El socio contrata un plan de clases.* Reglas aparte: los planes son de 4, 6, 8 o 12 clases; la vigencia es de un mes calendario desde la primera clase. "Controlar su vigencia" se aplica en el escenario de anotarse.
5. **Alertar cuando hay menos de 3.** Dos RF: *El profesor recibe el aviso de que su clase tiene menos de tres inscriptos* y *El socio anotado recibe el ofrecimiento de asistir en otro turno.* Regla aparte: con menos de tres no se dicta. "Para ofrecerles cambiar de turno" es justificación del primero y contenido del segundo.
6. **Registrar asistencias al ingresar.** Casi bien: *El socio registra su ingreso al establecimiento.* "Al momento de ingresar" no es un cómo: es el objeto mismo (el ingreso). Lo que sí se saca es el plural genérico "sus asistencias".

### ✅ Checkpoint

1. Rol (quién quiere lograrlo; hace al requisito consistente desde el actor y define el actor del caso de uso), verbo (la acción, en presente) y objeto (sobre qué recae, con precisión; con los datos si hacen falta para que sea testeable).
2. La asignación de responsabilidad (no se sabe de qué actor es la función, y el caso de uso queda huérfano), la validación (no se sabe a quién preguntarle si cumple) y la trazabilidad (el hilo del requisito se corta en el origen).
3. Nivel alto: verbo en infinitivo + objeto ("Registrar socio"); define la capacidad y es el nombre del caso de uso. Nivel detallado: rol + verbo + objeto + datos; vuelve al requisito testeable y consistente desde el actor.
4. Varios: uno por rol que pueda ejecutarlo (el profesor registra la limitación de un socio; el socio registra la propia). Cuáles van lo decide el negocio o la entrevista, no quien escribe.
5. Porque "interactuar" es un verbo hueco: no describe un objetivo concreto ni tiene escenario. El objetivo es anotarse a una clase; interactuar es cómo se llega.
6. Presente del indicativo, afirmativo. El futuro abre la puerta a la voz pasiva ("deberá ser validado") y a formas impersonales, y el "deberá" con el sistema como sujeto arrastra al sistema como protagonista.
7. Regla de negocio: es una obligación del socio que existe con o sin sistema. Se separa en RF (*el socio informa su ausencia a una clase*) y regla (*el aviso debe hacerse al menos el día anterior*).
8. Cuando el actor es un subsistema que dispara por sí mismo, sin acción humana (un subsistema notificador que avisa el vencimiento del plan). La regla no prohíbe un sistema como sujeto: exige que el sujeto sea el actor.
9. Porque hay dos objetivos distintos del socio, en momentos distintos: quedar en lista de espera cuando la clase está llena, y enterarse cuando se libera un lugar. Un solo RF los mezclaría (trampa de cohesión).

## Módulo 3 — El requerimiento no funcional

### ✏️ Tu turno

1. *El tiempo máximo de actualización de la lista de espera, desde la baja de un socio hasta el ofrecimiento del lugar al siguiente inscripto, es de 5 segundos.* Objeto: actualización de la lista de espera · atributo: tiempo máximo · valor: 5 · unidad: segundos · condición: desde la baja. El RF que restringe ya existe (el socio en lista recibe el ofrecimiento).
2. *El tiempo máximo para que un profesor complete su registro en el sistema, la primera vez y sin asistencia, es de 30 segundos para el 80% de los profesores.* Objeto: registro del profesor · atributo: tiempo de aprendizaje · valor: 30 · unidad: segundos · condición: primera vez, sin ayuda, 80%.
3. *La cantidad máxima de pasos del inicio de sesión del socio es de 3.* Objeto: inicio de sesión · atributo: cantidad de pasos (operabilidad) · valor: 3 · unidad: pasos/clicks. "Clientes" se corrige por "socios".
4. *La disponibilidad de la función de registro de presente es de al menos el 99,5% del tiempo en horario de apertura (lunes a sábados de 8 a 20).* [valor supuesto] Objeto: registro de presente · atributo: disponibilidad · valor: 99,5 · unidad: porcentaje · condición: horario de apertura. "Todo el horario" no admite margen; se necesita uno.
5. Dos RNF y una palabra del dominio corregida: *El medio de las notificaciones de cancelación de clase a los socios es WhatsApp* y *El tiempo máximo entre la cancelación de una clase y la notificación a los socios anotados es de 2 minutos.*
6. *La tasa máxima de error en la asignación de turnos es del 0,1%.* Objeto: asignación de turnos · atributo: tasa de error · valor: 0,1 · unidad: porcentaje. Se sacan "el sistema debe garantizar" (sujeto) y "evitando inconsistencias que afecten la confiabilidad" (justificación).

### ✅ Checkpoint

1. Restringe a un RF: bajo qué condiciones se logra esa función. Un RNF que no se puede medir no se puede verificar, y lo que no se verifica no se puede exigir.
2. Objeto: aplicación · atributo: disponibilidad · valor: 99,9 · unidad: porcentaje · condición: en horario de apertura.
3. Porque el atributo es del objeto, y cada objeto tiene su valor esperado. Tiempo máximo de confirmación de una inscripción: 2 segundos; tiempo máximo de respuesta de la consulta de ficha de socio: 3 segundos.
4. Sí, es una restricción legítima sobre el canal, verificable por inspección. Para el parcial se acompaña con una métrica de cumplimiento: "el porcentaje de notificaciones recibidas con éxito es de al menos 99%".
5. Como objeto con una característica: el componente es el objeto y se le fija un atributo verificable ("la resolución mínima de la cámara es de 8 megapíxeles"; "el lector de credenciales es de tecnología NFC").
6. Porque el RNF describe una propiedad que el sistema tiene: se escribe como afirmación de un valor. "Debe ser" suena a deseo; "es" es la especificación.
7. No como quien hace la acción. Sí como referencia del evento ("desde que el socio pasa la credencial") o como población de la condición ("para el 80% de los socios").
8. El de una función restringe un RF concreto y se cumple en su escenario (tiempo máximo de confirmación de la inscripción). El transversal restringe todo el sistema (disponibilidad general, identificador único, doble factor).
9. Como catálogo: se recorren sus ocho características preguntando qué tan rápido, qué tan fácil de usar, qué tan disponible, con qué se integra, quién puede verlo; de cada pregunta sale un RNF con su atributo nombrado y medible.
10. Porque nada actúa por sí solo cuando un socio llega: el profesor entra y consulta, es en línea. Queda como RF *el profesor consulta el presente de su clase*, y el RNF es el retardo: *el tiempo máximo entre el registro de un ingreso y su visualización en la lista de presentes es de 5 segundos*.

## Módulo 4 — Cómo corrige

### ✏️ Tu turno

1. **"El sistema debe controlar el tiempo mínimo (30) y máximo (120) de uso en sectores sin profesor, de 8 a 20 de lunes a sábados."** Punto de vista: ❌ (sistema). Cohesión: ❌, hay tres cosas (mínimo, máximo, horario), y ninguna es una función. No ambiguo: ✅. Completo: ❌, no dice qué pasa si se excede. Verificable: ⚠️, sin consecuencia no hay procedimiento. Todo es **defecto**. Reescritura: no queda RF; quedan tres reglas de negocio (mínimo 30, máximo 120, horario 8 a 20 de lunes a sábados) que se aplican en el escenario de *el socio registra su ingreso / su salida de un sector*; y una pregunta a la fuente: ¿qué pasa al exceder el máximo?
2. **"El socio puede anotarse con la cuota impaga si la paga antes de la clase."** Está impecablemente escrito, y es un **error**: contradice la regla de negocio de que para contratar el plan hay que pagar seña o totalidad, y de que el socio debe tener el plan pago para hacer actividades. Se corrige contra la regla: *el socio se anota en una clase* con precondición de plan vigente y pago.
3. **Lo que falta** en *anotarse · darse de baja · informar ausencia · lista de espera · recuperar*: el alta del socio y la contratación del plan (sin ellos nadie puede anotarse: derivados), la consulta de clases con lugar (previa a anotarse), y el cierre de la lista de espera (recibir y aceptar el ofrecimiento del lugar). Son omisiones; al agregarlas hay que respetar capacidad, vigencia y orden de la lista.

### ✅ Checkpoint

1. No ambiguo (¿una única interpretación?), consistente (¿se contradice consigo mismo, con otros o con las reglas de negocio?), completo (¿tiene todo para desarrollarlo sin adivinar?), realista (¿se puede con los recursos del proyecto?), rastreable (¿se conoce su origen y su validación?), verificable (¿puedo comprobar su cumplimiento con un procedimiento?).
2. Porque exige conocer los recursos del proyecto (tiempo, presupuesto, gente, tecnología), que muchas veces no están disponibles en el análisis. Es válido dejarla sin responder diciendo por qué; su evaluación formal es el análisis de factibilidad.
3. Entre requisitos (dos que no pueden convivir) y con las reglas de negocio (el conjunto tiene que ser coherente con cómo funciona el negocio).
4. La del requisito individual (¿tiene todos los datos para construirlo?) y la del conjunto (¿están todos los requisitos que hacen falta?).
5. Que cada requisito corresponde a una sola funcionalidad. Si se viola, el caso de uso que sale de ahí empaqueta dos funciones: no se le puede asignar un actor único, ni verificarlo por separado, ni cambiarlo sin tocar lo otro.
6. "El socio inicia sesión con sus credenciales": se puede probar (entro y funciona), pero no dice qué credenciales ni quién las crea. Verificable e incompleto.
7. El defecto está mal escrito pero es conceptualmente válido; el error está bien escrito y afirma algo que contradice una regla de negocio. El error es más difícil: pasa la lectura sin problema, hay que conocer el negocio para verlo.
8. Un requisito que falta y que otros necesitan para tener sentido. En el gimnasio, anotarse a una clase: hay baja, ausencia y lista de espera, pero nadie dijo cómo se anota.
9. Mantener la consistencia con el conjunto: el nuevo tiene que respetar las reglas y los requisitos existentes, o convertís una omisión en una inconsistencia.
10. Se reescribe cuando el dato existe y se expresó mal; se vuelve a la fuente cuando el dato nunca se relevó. La pregunta es "¿esto lo sé y lo escribí mal, o directamente no lo sé?".

---

**FIN DEL COMPLEMENTO — Clase desde cero · Parte 1**
