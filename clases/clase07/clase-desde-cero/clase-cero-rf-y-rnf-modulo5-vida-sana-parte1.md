# Clase desde cero — RF y RNF — Módulo 5: Vida Sana párrafo por párrafo — Parte 1

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Eje:** Centro de Entrenamiento Vida Sana
**Marcas:** 🔴 central · 🟡 secundario · 🟢 al pasar · 🕳️ madriguera · ✏️ tu turno

---

## Sobre este documento

**Qué cubre:** el método completo aplicado al enunciado del gimnasio, **párrafo por párrafo**, del 1 al 6 (contexto, capacidades, horarios, lista de espera, planes y ausencias). De cada párrafo: qué hay adentro, qué RF salen, qué reglas de negocio, qué RNF, qué preguntas quedan para la entrevista, y qué **no** sale de ahí aunque parezca.

**Qué NO cubre:** los párrafos 7 a 12 y la consolidación final (Parte 2). Las plantillas y las reglas de forma (M2, M3) no se repiten: se aplican.

## De dónde venís

De M1 a M4, con todo el equipamiento: el test de tres preguntas, rol + verbo + objeto, objeto + atributo + valor + unidad, y las ocho preguntas de corrección. Tené el enunciado a mano.

## Cómo está armado cada párrafo

```
   📄 El párrafo, textual.
   🔍 Qué hay acá: el marcado. Verbos de un actor → RF. Números y políticas → RN.
      "Cómo" y componentes → RNF. Dolor y justificación → contexto.
   ✅ RF · 📏 RN · ⚙️ RNF (con supuestos marcados) · ❓ Preguntas para la entrevista
   🚫 Lo que NO sale de acá
```

Los identificadores (RF-01, RN-01, RNF-01, P-01) son correlativos a lo largo de las dos partes, para que en la Parte 2 se pueda consolidar y trazar.

---

## Párrafo 1 🔴 — El negocio y quiénes lo forman

📄 *Nos convoca la Junta Directiva del Centro de Entrenamiento Vida Sana, porque requieren llevar adelante el proyecto de selección de una solución de software adecuada para su negocio. En el Centro trabajan 10 profesores, dando clases de pilates, funcional training, streching y yoga. El centro de entrenamiento cuenta además con un sector de cardio (conformado por cinco bicicletas fijas y dos cintas de correr), y un sector de musculación.*

🔍 **Qué hay acá.** Ningún verbo de un actor queriendo lograr algo con el sistema. Lo que hay es **el mapa del dominio**: quién pide (la Junta Directiva: es el cliente), quién trabaja (profesores), qué se ofrece (cuatro tipos de clase y dos sectores sin profesor), y con qué elementos (5 bicicletas, 2 cintas). Es contexto, y es el párrafo que te da los **actores** y el **vocabulario**.

✅ **RF:** ninguno.

📏 **RN:** ninguna todavía (los números de este párrafo son inventario, no política).

⚙️ **RNF:** ninguno.

❓ **Preguntas:**
- P-01. "Selección de una solución": ¿quieren comprar algo existente, desarrollar a medida, o comparar opciones? Cambia qué tan detallados tienen que ser los RNF (si compran, los RNF son los criterios de comparación).

🚫 **Lo que NO sale de acá:** ningún requisito. Es tentador escribir "el sistema gestiona clases de pilates, funcional, stretching y yoga". No: eso es describir el negocio, no lo que alguien quiere lograr. Lo que sí sale son tres cosas para anotar aparte:

```
   Actores:      Socio · Profesor · Junta Directiva  (el cliente es la Junta)
   Vocabulario:  clase (con profesor) ≠ sector de uso libre (cardio, musculación)
                 tipos de clase: pilates, funcional, stretching, yoga
   Inventario:   10 profesores · 5 bicicletas · 2 cintas
```

> 🕳️ **Madriguera — el vocabulario que anotás**
> Más adelante en la materia, ese vocabulario del dominio se formaliza en un artefacto propio (el Léxico Extendido del Lenguaje). Por ahora, anotarlo evita el error de "clase disponible" con tres significados.
> *Volvé al camino.*

---

## Párrafo 2 🔴 — Las capacidades

📄 *La capacidad de cada clase está limitada a la cantidad de elementos que conforman el sector: 8 (ocho) "reformers" (ver imagen) para pilates; 7(siete) en el caso de cardio (bici y cinta), y 5 (cinco) en el caso de musculación. Por otra parte, las clases de yoga, funcional training y streching tienen una capacidad máxima de 8 (ocho) socios.*

🔍 **Qué hay acá.** Números, y una palabra clave: *limitada*. Test de tres preguntas: ¿esto existe sin sistema? **Sí.** Con carpetas y resaltadores, pilates igual tiene 8 reformers. Son **reglas de negocio**, todas. El error típico es escribir "el sistema debe controlar la capacidad máxima de cada clase": eso mete la regla adentro de un RF con el sistema como sujeto, y te deja sin saber **qué quiere lograr un actor**.

✅ **RF:** ninguno directo. Pero la regla necesita una función donde aplicarse: la inscripción a una clase, que va a salir del párrafo 4. La capacidad es lo que hace que una inscripción **se rechace o vaya a lista de espera**. Eso se ve en el escenario del RF, no en un RF propio.

📏 **RN:**
```
RN-01  La capacidad máxima de una clase de pilates es de 8 socios.
RN-02  La capacidad máxima de un turno de cardio es de 7 socios.
RN-03  La capacidad máxima de un turno de musculación es de 5 socios.
RN-04  La capacidad máxima de una clase de yoga, funcional o stretching es de 8 socios.
```

Podés escribirlas como una sola tabla ("la capacidad máxima por tipo es…"). Lo importante es que estén **separadas de los RF** y que **cada valor esté**.

⚙️ **RNF:** ninguno. Ojo con la tentación: "el sistema valida la capacidad en menos de 1 segundo" es un RNF del RF de inscripción, y ese RF todavía no existe. En orden.

❓ **Preguntas:**
- P-02. Cardio dice 7 (5 bicicletas + 2 cintas). ¿Un socio reserva "cardio" o reserva una bicicleta o una cinta específica? Cambia el objeto del RF de reserva.
- P-03. ¿La capacidad de pilates es 8 por turno, o puede haber dos profesores en simultáneo con 8 cada uno?

🚫 **Lo que NO sale de acá:** un RF. Ni un RNF. Solo reglas y dos preguntas.

---

## Párrafo 3 🔴 — Duración, turnos y horarios

📄 *Todas las clases duran una hora, y se dan en 3 turnos a la mañana y 4 a la tarde, más 2 turnos los sábados a la mañana. Para los sectores sin profesor el tiempo mínimo de uso es de 30min y el máximo es de 120min, de 8 a 20hs de lunes a sábados.*

🔍 **Qué hay acá.** Más políticas del negocio: duración, cantidad de turnos, tiempos mínimo y máximo, horario. Todo existe sin sistema. Y **una función implícita**: si los sectores sin profesor tienen un tiempo mínimo y máximo de uso, alguien **reserva un turno** en ellos y alguien **registra cuándo entra y cuándo sale**. Eso sí es de un actor.

✅ **RF:**
```
RF-01  El socio reserva un turno en un sector de uso libre.
RF-02  El socio registra su ingreso a un sector de uso libre.
RF-03  El socio registra su salida de un sector de uso libre.
```
Fijate el actor: socio, no profesor. El párrafo 7 y el 11 van a confirmar por qué (hoy lo anotan los profesores, y no quieren hacerlo más). Y fijate que ingreso y salida son **dos RF**: sin la salida no hay forma de saber si se cumplió el máximo de 120 minutos.

📏 **RN:**
```
RN-05  Toda clase dura una hora.
RN-06  Las clases se dictan en 3 turnos a la mañana y 4 a la tarde de lunes a viernes,
       y 2 turnos los sábados a la mañana.
RN-07  El tiempo mínimo de uso de un sector de uso libre es de 30 minutos.
RN-08  El tiempo máximo de uso de un sector de uso libre es de 120 minutos.
RN-09  Los sectores de uso libre funcionan de 8 a 20 hs, de lunes a sábados.
```

⚙️ **RNF:** ninguno del texto. Podés proponer uno del RF-02, marcado como supuesto:
```
RNF-01  El tiempo máximo de confirmación del registro de ingreso a un sector, desde que
        el socio se identifica, es de 2 segundos.                 [supuesto: a confirmar]
```

❓ **Preguntas:**
- P-04. ¿A qué hora empieza cada turno? El enunciado dice cuántos, no cuáles.
- P-05. Si un socio excede los 120 minutos, ¿qué pasa? ¿Se le avisa? ¿Se le cobra? ¿Se le impide la próxima reserva? Sin esto, RN-08 es una regla sin consecuencia.

🚫 **Lo que NO sale de acá:** "el profesor es alertado cuando se excede el tiempo". Suena natural, pero el enunciado **no lo dice**. La consecuencia de exceder el máximo es la pregunta P-05, no un requisito inventado. Si lo escribís, estás decidiendo por el cliente.

---

## Párrafo 4 🔴 — Clases poco concurridas y lista de espera

📄 *Algunas clases son más concurridas que otras, porque existen horarios de mayor demanda. Si no existen al menos tres socios anotados en una clase, entonces los profesores deben llamar a los únicos dos socios anotados para ofrecerles asistir en otro turno. Por otro lado, cuando las inscripciones a una clase están completas, pueden anotarse socios en lista de espera. Si un socio inscripto se baja de la clase, los profesores llaman al primer socio inscrito en la lista de espera para ofrecerle el lugar, y así sucesivamente hasta completar la clase.*

🔍 **Qué hay acá.** El párrafo más rico del enunciado. Tiene **verbos de actores** por todos lados: anotarse, bajarse, llamar, ofrecer. Tiene **políticas**: mínimo de 3, orden de la lista de espera. Y tiene una trampa: "los profesores llaman" describe cómo se hace **hoy**, a mano. El profesor no *quiere* llamar; es su carga (párrafo 11). El objetivo real es del **socio**: enterarse de que hay lugar, o de que le ofrecen otro turno.

También hay una función que **no está escrita y es obvia**: para bajarse de una clase o quedar en lista de espera, primero hubo que **anotarse**. Es el requisito derivado del que habla M4: sin él, nada de este párrafo tiene sentido.

✅ **RF:**
```
RF-04  El socio se anota en una clase.                                  ← derivado
RF-05  El socio se da de baja de una clase en la que está anotado.
RF-06  El socio se anota en la lista de espera de una clase completa.
RF-07  El socio en lista de espera recibe el ofrecimiento del lugar liberado en la clase.
RF-08  El socio acepta o rechaza el ofrecimiento de un lugar liberado.
RF-09  El socio anotado en una clase con menos de tres inscriptos recibe el ofrecimiento
       de asistir en otro turno.
RF-10  El profesor consulta la cantidad de inscriptos y la lista de espera de su clase.
```

Sobre RF-08: "ofrecer" implica una respuesta; si el primero de la lista no acepta, se sigue con el siguiente ("y así sucesivamente"). Sin RF-08, RF-07 no tiene cierre. Sobre RF-10: es el único que sí es del profesor, porque saber cuánta gente tiene es un objetivo suyo aunque deje de gestionar la lista.

📏 **RN:**
```
RN-10  Solo puede haber lista de espera cuando la clase está completa.
RN-11  Un lugar liberado se ofrece a los socios en lista de espera por orden de inscripción
       en la lista, uno a la vez, hasta que alguien lo acepte.
RN-12  Una clase con menos de tres socios anotados no se dicta; a los anotados se les
       ofrece otro turno.
```

RN-12 merece una aclaración: el enunciado dice "los únicos dos socios", pero el mínimo es tres, así que puede haber uno o dos. Escribí la regla general, no el caso literal.

⚙️ **RNF** (del RF-07; los valores son supuestos):
```
RNF-02  El tiempo máximo entre la baja de un socio y el ofrecimiento del lugar al primero
        de la lista de espera es de 5 minutos.                     [supuesto]
RNF-03  El medio del ofrecimiento de un lugar liberado al socio en lista de espera es
        WhatsApp.                                                  [supuesto: relevar preferencia]
```
El segundo es una restricción de canal sin unidad; según M3 §4.1, la acompañás con una métrica si te la piden: *el porcentaje de ofrecimientos recibidos con éxito es de al menos 99%*.

❓ **Preguntas:**
- P-06. ¿Cuánto tiempo tiene el socio para aceptar el ofrecimiento antes de que pase al siguiente?
- P-07. ¿En qué momento se decide que una clase tiene menos de tres? ¿El día anterior? ¿Una hora antes?
- P-08. ¿Puede un socio estar en lista de espera de varias clases a la vez?

🚫 **Lo que NO sale de acá:** "el sistema gestiona automáticamente la lista de espera". Es la trampa 1 y la trampa 6 juntas (sistema como sujeto, verbo hueco), y además "automáticamente" no mide nada. Todo lo que ese requisito quería decir está en RF-06, RF-07, RF-08 y RN-11.

---

## Párrafo 5 🔴 — Los planes

📄 *Los socios pueden contratar planes de 4, 6 ,8 o 12 clases por mes calendario. Esto es: si la primera clase es un día 15, el socio tiene hasta el 15 del mes siguiente para completar su plan. Para contratar el plan deben reservar su lugar pagando una seña o la totalidad el plan en la última clase el plan en curso.*

🔍 **Qué hay acá.** Un verbo del actor clarísimo: *contratar*. Una política de vigencia. Y una política de pago que el enunciado escribe mal (la última oración está incompleta; se lee como: para contratar el plan siguiente hay que pagar una seña o la totalidad **durante la última clase del plan en curso**). Cuando el enunciado está roto, **no lo arreglás por tu cuenta: lo anotás como pregunta y escribís la lectura más probable marcada como tal.**

✅ **RF:**
```
RF-11  El socio contrata un plan de clases.
RF-12  El socio paga su plan, en forma de seña o de totalidad.
RF-13  El socio consulta el estado de su plan (inicio, vencimiento, clases usadas y restantes).
```
RF-13 no está literal, pero el párrafo entero habla de un plan con inicio, vencimiento y cantidad de clases; que el socio pueda verlo es el complemento obvio (párrafo 8 lo confirma: hoy lo lleva en una ficha).

📏 **RN:**
```
RN-13  Los planes disponibles son de 4, 6, 8 o 12 clases.
RN-14  La vigencia de un plan es de un mes calendario, contado desde la primera clase.
RN-15  El plan siguiente se contrata pagando una seña o la totalidad durante la última
       clase del plan en curso.                                    [lectura probable: confirmar]
```

⚙️ **RNF** (del RF-12, supuestos):
```
RNF-04  Los medios de pago del plan son efectivo, tarjeta de débito y tarjeta de crédito.  [supuesto]
RNF-05  La integración con la plataforma de pago con tarjeta es por medio de APIs.          [supuesto]
```
Y uno que aparece en cuanto hay pago en línea, escrito con el objeto como sujeto (M3 §5.2): *El pago con tarjeta requiere conexión a internet del dispositivo del socio.* Si el pago fuera en el mostrador, el objeto cambia: *la conectividad del puesto de cobro es redundante.* No lo numero porque depende de P-10.

❓ **Preguntas:**
- P-09. La última oración: ¿"pagando una seña o la totalidad **en** la última clase del plan en curso"? ¿Qué pasa si no paga en esa clase: pierde el lugar?
- P-10. ¿Dónde se paga: en el mostrador, desde la app, ambos?
- P-11. ¿Cuánto es la seña? ¿Un porcentaje, un monto fijo?
- P-12. Si el plan vence con clases sin usar, ¿se pierden?

🚫 **Lo que NO sale de acá:** "el sistema gestiona los planes mensuales controlando su vigencia". Otra vez sistema + verbo hueco. La vigencia es RN-14; el control se hace **dentro** del escenario de RF-04 (anotarse): un socio sin plan vigente no se puede anotar.

> ⚠️ **Sobre el vencimiento.** Que un plan venza a los 30 días **no es algo que un actor haga**: pasa solo, por tiempo. Si el sistema tiene que avisar al socio que su plan vence, ese aviso lo dispara un subsistema (M2 §5.1): *el subsistema notificador avisa al socio el vencimiento próximo de su plan.* No está en el enunciado; si lo agregás, es un RF propuesto, declarado como tal.

---

## Párrafo 6 🔴 — Avisar ausencia y recuperar

📄 *Para comprometer a los socios en su asistencia, éstos deben avisar al menos el día anterior de su ausencia, así los profes tienen tiempo de ofrecer su lugar a un socio en lista de espera, o bien cancelar la clase si quedan menos de 3 inscritos. Sólo aquellos socios que avisaron de una ausencia, pueden recuperar su clase.*

🔍 **Qué hay acá.** Es el párrafo que ya trabajaste en M1 §4.1. "Para comprometer a los socios" es justificación: se saca. "Deben avisar el día anterior" es una política. "Avisar" y "recuperar" son verbos del socio. "Cancelar la clase" es un verbo del profesor, o de quien decida. Y "ofrecer el lugar a la lista de espera" ya está cubierto por RF-07.

✅ **RF:**
```
RF-14  El socio informa su ausencia a una clase en la que está anotado.
RF-15  El socio recupera una clase en la que informó su ausencia.
RF-16  El profesor cancela una clase.
RF-17  El socio anotado en una clase recibe el aviso de su cancelación.
```
RF-14 y RF-15 son dos, no uno (trampa 7). RF-16 sale de "cancelar la clase si quedan menos de 3": alguien la cancela. RF-17 es el complemento obvio: si la cancelan, el anotado tiene que enterarse.

📏 **RN:**
```
RN-16  El socio debe informar su ausencia a una clase al menos el día anterior.
RN-17  Solo el socio que informó su ausencia puede recuperar esa clase.
```
RN-12 (menos de tres, no se dicta) ya está.

⚙️ **RNF** (del RF-14 y RF-17, supuestos):
```
RNF-06  El tiempo máximo de confirmación del aviso de ausencia, desde que el socio lo envía,
        es de 2 segundos.                                                    [supuesto]
RNF-07  El tiempo máximo entre la cancelación de una clase y el aviso a los socios anotados
        es de 2 minutos.                                                     [supuesto]
RNF-08  El medio del aviso de cancelación es WhatsApp.                       [supuesto]
```

❓ **Preguntas:**
- P-13. "Recuperar la clase": ¿en qué plazo? ¿Dentro del mismo plan? ¿En cualquier turno con lugar?
- P-14. ¿Quién decide cancelar: el profesor de esa clase, cualquier profesor, la Junta?
- P-15. Si un socio no avisó y no fue, ¿pierde la clase del plan? (El enunciado lo implica, no lo dice.)

🚫 **Lo que NO sale de acá:** dos cosas. Primera, el aviso al profesor de que un socio se dio de baja: el párrafo habla de *ausencia*, no de *baja*; son dos cosas distintas (la baja es RF-05, la ausencia es RF-14), y mezclarlas es la ambigüedad de "baja de asistencia" de M4 §1. Segunda, y más importante: **RN-16 va a entrar en conflicto con el párrafo 12**, donde los socios piden avisar hasta una hora antes. No lo resolvés acá. Lo anotás, y en la Parte 2 vas a ver qué se hace con un conflicto entre stakeholders.

---

## Balance de la Parte 1

Seis párrafos, y esto es lo que salió:

| | Cantidad | IDs |
|---|---|---|
| RF | 17 | RF-01 a RF-17 |
| Reglas de negocio | 17 | RN-01 a RN-17 |
| RNF | 8 (todos con valor supuesto) | RNF-01 a RNF-08 |
| Preguntas para la entrevista | 15 | P-01 a P-15 |

Tres cosas para notar antes de seguir:

1. **Los RF salen de los verbos de un actor**, y casi siempre son del socio. El profesor aparece como quien hace las cosas *hoy*; el sistema se pide justamente para que deje de hacerlas.
2. **Las reglas de negocio salen de los números y las políticas**, y son muchas más de lo que parece. Si tu lista tiene 15 RF y 2 reglas, metiste las reglas adentro de los RF.
3. **Ningún RNF vino del enunciado con valor.** Todos son supuestos declarados. Eso es normal: el enunciado describe el negocio, no la calidad esperada; la calidad se releva o se propone.

> **Para el parcial, si te preguntan:** *¿Cómo se identifican los RF, los RNF y las reglas de negocio en un enunciado?*
> Los RF salen de los verbos con los que un actor quiere lograr algo a través del sistema (anotarse, avisar, pagar, consultar) y se escriben con ese actor como sujeto. Las reglas de negocio salen de los números y las políticas que existirían aunque no hubiera sistema (capacidades, plazos, condiciones) y se listan aparte. Los RNF salen de lo que restringe cómo se ejecuta una función (tiempos, medios, componentes, propiedades); cuando el enunciado no trae el valor, se propone uno razonable y se declara como supuesto a confirmar.

---

## ✏️ Tu turno

Antes de leer la Parte 2, hacé esto sobre los párrafos 7 a 12 del enunciado, por escrito: para cada uno, marcá **verbos de actor**, **números y políticas**, y **dolor**. No escribas todavía los requisitos; solo el marcado. Después compará con la Parte 2.

## ✅ Checkpoint

1. ¿Por qué del párrafo 1 no sale ningún requisito, y qué sí sale?
2. ¿Por qué las capacidades del párrafo 2 son reglas de negocio y no RF? ¿Dónde se aplican entonces?
3. ¿Por qué el ingreso y la salida de un sector de uso libre son dos RF?
4. ¿Cuál es el requisito derivado del párrafo 4 y por qué es derivado?
5. ¿Por qué el actor de "recibe el ofrecimiento del lugar" es el socio y no el profesor que hoy llama?
6. ¿Qué hacés cuando una oración del enunciado está rota, como la del pago del plan?
7. ¿Por qué el vencimiento de un plan no es un RF del socio?
8. ¿Qué diferencia hay entre "darse de baja" y "informar una ausencia"?
9. ¿Qué conflicto quedó abierto al final del párrafo 6?

## Qué viene en la Parte 2

Los párrafos 7 a 12: los registros en papel que hay que reemplazar, los roces, la identificación de socios, el pedido de los profesores de desentenderse, y el conflicto entre socios y profesores. Después, la consolidación: la lista completa, la tabla de trazabilidad RF ↔ RNF, el pase por las ocho preguntas de corrección para detectar omisiones, y qué se hace con el conflicto.

**FIN DEL MÓDULO 5 — PARTE 1**
