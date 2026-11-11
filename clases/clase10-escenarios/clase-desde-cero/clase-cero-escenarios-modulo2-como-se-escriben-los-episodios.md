# Clase desde cero — Escenarios — Módulo 2: Cómo se escriben los episodios

**Serie:** Clase desde cero — Escenarios (módulo 2 de 5) · **Materia:** Ingeniería de Requisitos · **Unidad:** clase10

---

## Sobre este documento

**Qué cubre:** la oración de un episodio; los cuatro tipos (simple, condicional, optativo, no secuencial); la regla "todo verificar abre dos caminos"; el bucle; las excepciones y la restricción; la plantilla que usa la cátedra en Vida Sana y en qué se aparta del modelo. Con dos ejemplos trabajados: el escenario "Inscribir a clase" leído episodio por episodio, y la consigna de tu equipo (modificarlo para varias clases) resuelta.

**Qué NO cubre:** subescenarios en detalle (módulo 3), escenario futuro y casos de uso (módulo 4), la revisión completa de un escenario (módulo 5).

## De dónde venís

Del módulo 1: las partes de un escenario; la MAYÚSCULA es un subescenario; el ejemplo Anular la reunión con sus episodios 4 ("Si…") y 6 (entre corchetes).

---

## 1. 🔴 La oración de un episodio

Un episodio es una acción. Se escribe como una oración con tres cosas: **quién** la hace, **qué** hace y **sobre qué**.

> El convocante **busca** la reunión en la agenda.
> *sujeto* · *verbo* · *objeto*

Reglas, con el error al lado:

| Regla | ❌ Mal | ✅ Bien | Por qué |
|---|---|---|---|
| **Siempre con sujeto** | "Buscar la reunión en la agenda." | "El convocante busca la reunión en la agenda." | Sin sujeto no sabés quién lo hace, y el actor tiene que estar en la lista de actores |
| **Verbo activo, conjugado, en presente** | "Buscando la reunión…", "Buscó la reunión…", "Buscar la reunión" | "busca" | Un escenario describe lo que pasa, no una instrucción ni un recuerdo |
| **Un solo verbo por episodio** | "El socio se presenta, pide la clase y da su nombre." | Tres episodios | Cada acción puede tener su condición, su excepción, su recurso |
| **Verbo concreto** | "El socio gestiona su inscripción." / "El socio usa la carpeta." | "El socio solicita la inscripción." / "El profesor consulta la carpeta." | "Gestionar", "administrar", "usar" no dicen qué pasa. La cátedra los corrige también en casos de uso |
| **Alguien hace algo concreto, no "el sistema permite"** | "El sistema permite anotar al socio." | "El profesor anota al socio en la carpeta." (actual) / "El sistema registra la reserva." (futuro) | "Permite" no es una acción: nadie hizo nada. Si hay un sistema, hoy o en el futuro, es un actor y hace algo concreto |
| **Sin "puede", "debe", "podría"** (lectura 🟡) | "El profesor debería verificar el cupo." | "El profesor verifica el cupo." | El episodio dice lo que pasa; las obligaciones van en la restricción |

Una excepción a "siempre con sujeto": si el episodio es solo el título de un subescenario ("4.3.1. REGISTRAR RESERVA DE CUPO EN CLASE"), puede ir sin sujeto; el sujeto está adentro del subescenario.

Y una regla de alcance que la cátedra da para casos de uso y que conviene llevar a los episodios: se actúa sobre un **objeto**, no sobre un dato. "Registra al socio", no "cambia el campo nombre del socio".

## 2. 🔴 Los cuatro tipos de episodio

Volvé al ejemplo del módulo 1. Hay episodios que pasan siempre, uno que pasa "si…", y uno entre corchetes. Son tipos distintos.

| Tipo | Cómo se escribe | Ejemplo | Qué significa |
|---|---|---|---|
| **Simple** | La oración sola | "El convocante consulta la agenda." | Pasa siempre. Es necesario para concluir el escenario |
| **Condicional** | "Si *condición*, *acción*." | "Si existen fechas comunes, el convocante selecciona la más cercana." | Pasa solo si se cumple la condición. Si no se cumple, se saltea y se sigue con el siguiente |
| **Optativo** | Entre corchetes: [ *acción* ] | "[El convocante define el temario.]" | Puede pasar o no, **sin una condición que se pueda escribir** |
| **No secuencial** | Entre numerales: # *episodio A* / *episodio B* # | "# El convocante consulta la disponibilidad de espacio. El convocante consulta la agenda. #" | Los episodios del grupo pasan en paralelo o en cualquier orden |

Dos aclaraciones que la cátedra hace siempre:

**Condicional vs. optativo.** La diferencia es si podés escribir la condición. "[La secretaria ANULA LA RESERVA DE MATERIAL FÍSICO.]" está como optativo porque a veces hay material reservado y a veces no. Pero en este caso la condición **sí se puede escribir**: "Si hay material físico reservado, la secretaria ANULA LA RESERVA DE MATERIAL FÍSICO." Y si se puede escribir, ya no es optativo: es condicional, y es más claro. El optativo de verdad es el que no tiene una condición nombrable ("[El convocante define el temario.]": a veces lo hace y a veces no, sin regla).

> ⚠️ **Nota de cátedra.** En la materia se **prefiere el condicional al corchete**. El corchete es válido, pero no todo el mundo sabe qué significa; "Si tal cosa, …" lo entiende cualquiera. En el parcial, si dudás, escribí la condición.

> ⚠️ **Nota de cátedra.** En la lectura del aula los tipos son tres (simple, condicional, optativo) y el no secuencial es un agrupamiento de episodios, no un tipo. La cátedra lo lista como cuarto tipo. Para el parcial, cuatro. Aparece poco.

**Todo "verificar" abre dos caminos.** Si un episodio dice "el profesor verifica si hay cupo", hay dos resultados posibles, y el escenario tiene que decir qué pasa en cada uno. Lo mismo con "controla", "valida", "consulta si…". Un "verifica" seguido de un solo camino está incompleto.

> 10. El profesor verifica si al socio le quedan clases en el plan.
> 11. Si le quedan clases, el profesor lo anota en la clase.
> 12. Si no le quedan clases, el profesor le ofrece contratar un nuevo plan.

Y si el resultado negativo no tiene nada que hacer, igual se dice: "Si no hay cupo, FIN DEL ESCENARIO."

🕳️ **Madriguera — la gramática formal.** El modelo original define la sintaxis de los episodios con una gramática BNF (la notación que viste en Sintaxis y Semántica). La cátedra no la pide; con la tabla alcanza. *Volvé al camino.*

> 🎓 **Para el parcial, si te preguntan: ¿qué tipos de episodio hay?**
> Simple (ocurre siempre y es necesario para concluir el escenario), condicional (ocurre si se cumple una condición: "Si… entonces"), optativo (puede ocurrir o no sin condición explícita; va entre corchetes) y no secuencial (un grupo entre numerales cuyos episodios ocurren en paralelo o en orden indistinto). Un episodio puede además ser otro escenario (subescenario, en mayúscula).

## 3. 🔴 El bucle: cuando algo se repite

Mirá el episodio 4 de Anular la reunión: "la secretaria DA EL AVISO DE CANCELACIÓN a cada convocado". Si hay veinte convocados, eso pasa veinte veces. Es una **repetición**, y en un escenario hay que poder escribirla.

Hay dos formas, y las dos las acepta la cátedra:

**Al principio, con "Mientras":**
> 4. Mientras haya convocados sin avisar, la secretaria DA EL AVISO DE CANCELACIÓN al siguiente convocado.

**Al final, con "vuelve al paso":**
> 4. La secretaria DA EL AVISO DE CANCELACIÓN a un convocado.
> 5. Si quedan convocados sin avisar, vuelve al paso 4.

Otro ejemplo, tomar lista: "Mientras haya alumnos en la lista, el profesor pregunta por el siguiente alumno." Y el que vas a necesitar en este módulo: un socio que quiere inscribirse en varias clases.

Las repeticiones aparecen mucho más de lo que parece: avisar a cada uno, revisar cada ítem, cobrar cada cuota. Cuando veas "cada", "todos", "varios", pensá en un bucle.

> ⚠️ **Nota de cátedra.** El bucle no figura en la tabla de tipos de episodio, pero la cátedra lo usa y lo pide. Escribilo como arriba: "Mientras…" al principio o "si quedan…, vuelve al paso N" al final. Una forma más suelta, tipo "se repiten los episodios 2 a 11 para cada clase", se entiende y la cátedra la aceptó, pero la consideró menos formal. **En el parcial usá "Mientras…".**

## 4. 🔴 Excepciones y restricción

**Excepción:** algo que impide lograr el objetivo. Casi siempre es la falta o la falla de un recurso: no hay espacio físico, no hay conexión, no está la carpeta. Se escribe aparte de los episodios, en el componente Excepciones, con esta forma:

> **Causa.** *(Episodio donde puede ocurrir.)* **(Solución)**

Ejemplo, de un escenario de organizar una reunión:

> Conflictos en la disponibilidad de espacio. Episodio: 11. (SOLICITAR ESPACIO FÍSICO EN EDIFICIO ANEXO)

Se lee: en el episodio 11 puede pasar que no haya espacio; si pasa, se resuelve con otro escenario, SOLICITAR ESPACIO FÍSICO EN EDIFICIO ANEXO. La solución puede ser un escenario (en mayúscula) o una acción simple ("el convocante solicita autorización a Mantenimiento"). Si **no** se pone número de episodio, la excepción puede ocurrir en cualquier momento del escenario.

La diferencia con un condicional: el condicional es un camino **previsto** del negocio (no hay cupo → lista de espera). La excepción es algo que **rompe** el escenario y hay que tratarlo aparte.

**Restricción:** no es un episodio. Es un **atributo** de un episodio: una exigencia de calidad o de alcance sobre ese paso. En la práctica, un requisito no funcional pegado al episodio. Por ejemplo, sobre "el profesor anota al socio en la carpeta": *restricción: debe hacerse antes de que empiece la clase*. Se escribe al lado del episodio o en una columna aparte, según la plantilla.

> 🎓 **Para el parcial, si te preguntan: ¿qué es una excepción en un escenario?**
> Es un obstáculo que impide cumplir el objetivo del escenario, generalmente la falta o el mal funcionamiento de un recurso. Se escribe como Causa (Solución), indicando el número de episodio donde puede ocurrir; sin número, puede ocurrir en cualquier momento. La solución puede ser un escenario o una acción simple.

## 5. 🔴 La plantilla que usa la cátedra

En los ejercicios de la materia, el escenario viene en una tabla con estos campos: **Nombre Escenario · Rol/es/Actor/es · Objetivo · Restricciones/precondición · Episodios · Contexto Geográfico/Temporal · Recursos**. Es el mismo modelo con tres diferencias de forma:

1. **"Restricciones/precondición" en un solo campo.** En el modelo son dos cosas distintas (la precondición es contexto; la restricción es un atributo de un episodio). En la plantilla van juntas. No es un error: escribilo ahí.
2. **"FIN DEL ESCENARIO" como último episodio** de cada camino. En el modelo no existe; el escenario termina cuando se acaban los episodios. En la plantilla se escribe, y sirve para marcar dónde termina cada rama.
3. **Numeración anidada:** 4, 4.1, 4.2, 4.3.1… Los episodios que dependen de una condición se numeran debajo de ella. La cátedra tolera encabezar la rama con un estado ("4. Existe cupo disponible"); lo correcto es "Si existe cupo, …" con su acción. Módulo 5.
4. **No tiene campo Excepciones.** Si tenés que escribir una, agregá el renglón al final de la tabla.

> ⚠️ **Nota de cátedra.** Estas cosas **no son errores para la cátedra**. En el parcial, escribí como la plantilla que te den. Si te dan una tabla con "Restricciones/precondición", poné ahí la precondición.

## 6. 🔴 Ejemplo trabajado: Inscribir a clase, episodio por episodio

El escenario de Vida Sana tal como lo da la cátedra (con un "FIN DE ESCENARIO" del original unificado a "FIN DEL ESCENARIO"). Leelo entero primero.

> **Nombre Escenario:** INSCRIBIR A CLASE / RESERVAR CUPO EN CLASE
> **Rol/es/Actor/es:** Socio, Profesora
> **Objetivo:** El socio se asegura un cupo en una clase determinada para asistir a la misma.
> **Restricciones/precondición:** Debe haber disponibilidad de cupo en la clase deseada. El socio debe tener clase disponible en su plan de clases.
> **Episodios:**
> 1. El Socio se presenta en el centro de entrenamiento.
> 2. El Socio consulta al profesor la disponibilidad de una clase, práctica, día y horario de la clase.
> 3. El profesor consulta disponibilidad en la grilla de la clase.
> 4. Existe cupo disponible en la clase.
> &nbsp;&nbsp;4.1. El Socio brinda apellido y nombre al profesor.
> &nbsp;&nbsp;4.2. El profesor consulta disponibilidad de clase en el plan del socio.
> &nbsp;&nbsp;4.3. El Socio tiene clase disponible en su plan.
> &nbsp;&nbsp;&nbsp;&nbsp;4.3.1. REGISTRAR RESERVA DE CUPO EN CLASE
> &nbsp;&nbsp;&nbsp;&nbsp;4.3.2. FIN DEL ESCENARIO
> &nbsp;&nbsp;4.4. El Socio no tiene clase disponible en su plan.
> &nbsp;&nbsp;4.5. El profesor le ofrece al Socio contratar un nuevo plan de clases.
> &nbsp;&nbsp;4.6. El Socio acepta contratar un nuevo plan de clases.
> &nbsp;&nbsp;&nbsp;&nbsp;4.6.1. CONTRATAR PLAN DE CLASES
> &nbsp;&nbsp;&nbsp;&nbsp;4.6.2. REGISTRAR RESERVA DE CUPO EN CLASE
> &nbsp;&nbsp;&nbsp;&nbsp;4.6.3. FIN DEL ESCENARIO
> &nbsp;&nbsp;4.7. El Socio no acepta contratar un nuevo plan de clases.
> &nbsp;&nbsp;4.8. FIN DEL ESCENARIO
> 5. El profesor le ofrece al socio ingresar en la lista de espera.
> 6. El Socio acepta ingresar en la lista de espera.
> &nbsp;&nbsp;6.1. El Socio brinda apellido y nombre al profesor.
> &nbsp;&nbsp;6.2. El profesor anota al Socio en la lista de espera.
> &nbsp;&nbsp;6.3. FIN DEL ESCENARIO
> 7. El Socio NO acepta ingresar en la lista de espera.
> 8. El profesor consulta disponibilidad en la práctica para otro día y horario.
> 9. El profesor le ofrece al Socio reservar clase en otro día y horario.
> 10. El Socio acepta reservar clase en otro día y horario.
> &nbsp;&nbsp;10.1. REGISTRAR RESERVA DE CUPO EN CLASE
> 11. El Socio no acepta reservar clase en otro día y horario.
> 12. FIN DEL ESCENARIO
> **Contexto Geográfico/Temporal:** En el Centro de Entrenamiento Vida Sana. En el horario de clases del Centro de Entrenamiento Vida Sana.
> **Recursos:** Carpeta de clases. Carpeta de fichas de socios. Carnet ficha del socio.

**Cómo se lee.** Es un árbol de caminos. El tronco son los episodios 1 a 3: el socio llega, pregunta, el profesor mira la grilla. Ahí se abre la primera bifurcación:

- **Hay cupo (4 y sus hijos).** El socio da su nombre, el profesor mira el plan. Segunda bifurcación: *tiene clases* (4.3: se registra la reserva, subescenario en mayúscula, y termina) o *no tiene* (4.4 a 4.8: se le ofrece un plan nuevo; si acepta, contrata y se registra; si no, termina).
- **No hay cupo (5 a 12).** Se le ofrece lista de espera. Si acepta (6), da su nombre, lo anotan, termina. Si no (7), el profesor busca otro día y horario (8 y 9); si acepta (10), se registra; si no (11), termina.

Fijate cómo cada "ofrece" y cada "consulta" abre dos caminos, y cómo cada camino termina en FIN DEL ESCENARIO o en un subescenario. Esa es la estructura que tiene que tener cualquier escenario con alternativas.

Tres cosas para notar, que vuelven en el módulo 5:
- El episodio 4 dice "Existe cupo disponible en la clase." 🧵 ¿Es una acción? ¿Quién la hace? Dejalo anotado.
- Los subescenarios en mayúscula (REGISTRAR RESERVA DE CUPO EN CLASE, CONTRATAR PLAN DE CLASES) son escenarios aparte que no están escritos acá. El módulo 3 explica qué tienen que cumplir.
- La precondición dice "debe haber cupo", pero los episodios 5 a 12 son justamente qué pasa cuando no hay. Algo no cierra. Módulo 5.

## 7. 🔴 Ejemplo trabajado: la consigna de tu equipo, resuelta

La consigna: *modificar el escenario para que el socio pueda inscribirse en más de una clase, y como máximo las del límite de su plan activo.*

**Qué hay que cambiar, de fondo.** Hoy el escenario inscribe en una clase y termina. Para varias clases, el bloque "elegir clase → ver cupo → registrar" tiene que **repetirse** una vez por clase. Eso es un bucle. Y antes de empezar a repetir, hay que saber **cuántas** veces como máximo: las clases que le quedan en el plan. Eso es una validación al principio. Dos cambios, no diez.

**Qué cambia de forma.** Objetivo y precondición pasan al plural: "cupos en las clases". Y la precondición "debe haber cupo en la clase deseada" se saca: el cupo se verifica adentro, clase por clase; no es una condición para *empezar*. Lo que sí es condición para empezar: que al socio le quede al menos una clase en el plan.

**La versión corregida:**

> **Nombre Escenario:** INSCRIBIR A CLASES / RESERVAR CUPOS EN CLASES
> **Rol/es/Actor/es:** Socio, Profesor
> **Objetivo:** El socio se asegura cupos en las clases que elige, hasta el límite de su plan, para asistir a ellas.
> **Restricciones/precondición:** El socio debe tener al menos una clase disponible en su plan de clases.
> **Episodios:**
> 1. El Socio se presenta en el centro de entrenamiento.
> 2. El Socio brinda apellido y nombre al profesor.
> 3. El Socio indica al profesor en cuántas clases desea inscribirse.
> 4. El profesor consulta en la ficha del socio la cantidad de clases disponibles en su plan.
> 5. Si la cantidad deseada supera las clases disponibles, el profesor informa al Socio que lo inscribirá solo en la cantidad de clases disponibles.
> 6. Si la cantidad deseada no supera las clases disponibles, el profesor confirma al Socio la cantidad.
> 7. Mientras el Socio tenga clases disponibles en su plan y quiera inscribirse en otra clase:
> &nbsp;&nbsp;7.1. El Socio consulta al profesor la disponibilidad de una clase, práctica, día y horario.
> &nbsp;&nbsp;7.2. El profesor consulta disponibilidad en la grilla de la clase.
> &nbsp;&nbsp;7.3. Si existe cupo disponible en la clase, REGISTRAR RESERVA DE CUPO EN CLASE.
> &nbsp;&nbsp;7.4. Si no existe cupo disponible, el profesor le ofrece al Socio ingresar en la lista de espera.
> &nbsp;&nbsp;7.5. Si el Socio acepta ingresar en la lista de espera, el profesor anota al Socio en la lista de espera.
> &nbsp;&nbsp;7.6. Si el Socio no acepta ingresar en la lista de espera, el profesor consulta disponibilidad en la práctica para otro día y horario.
> &nbsp;&nbsp;7.7. Si hay disponibilidad en otro día y horario, el profesor le ofrece al Socio reservar clase en ese día y horario.
> &nbsp;&nbsp;7.8. Si el Socio acepta reservar clase en otro día y horario, REGISTRAR RESERVA DE CUPO EN CLASE.
> &nbsp;&nbsp;7.9. Si no hay disponibilidad en otro día y horario, o el Socio no acepta, el profesor informa al Socio que no queda inscripto en esa clase.
> 8. Si el Socio quiere inscribirse en más clases y no tiene clases disponibles en su plan, el profesor le ofrece contratar un nuevo plan de clases.
> 9. Si el Socio acepta contratar un nuevo plan, CONTRATAR PLAN DE CLASES.
> 10. Si el Socio contrató un nuevo plan, vuelve al episodio 7.
> 11. Si el Socio no acepta contratar un nuevo plan, FIN DEL ESCENARIO.
> 12. FIN DEL ESCENARIO
> **Contexto Geográfico/Temporal:** En el Centro de Entrenamiento Vida Sana. En el horario de clases del Centro de Entrenamiento Vida Sana.
> **Recursos:** Carpeta de clases. Grilla de clases. Carpeta de fichas de socios. Carnet ficha del socio. Lista de espera.

**Por qué está escrito así:**
- **El nombre se da una sola vez** (episodio 2), antes del bucle. En el original se pedía en 4.1 y en 6.1, en cada rama. Si el socio va a anotarse en cuatro clases, no tiene sentido pedírselo cuatro veces.
- **La validación del plan va al principio** (3 a 6), una vez. Es lo que marca el tope del bucle. "Te quedan cuatro: te anoto en cuatro." Y el "consulta" del 4 tiene sus dos caminos (5 y 6), como pide la regla.
- **El bucle (7)** repite exactamente lo que el original hacía para una clase: elegir, ver cupo, registrar o lista de espera u otro horario. Lo que cambió es que ahora está adentro de un "Mientras", y que cada "consulta" y cada "ofrece" de adentro tiene sus dos caminos (7.3/7.4, 7.5/7.6, 7.7/7.9, 7.8/7.9). El original dejaba sin escribir qué pasa si no hay otro horario.
- **Los FIN DEL ESCENARIO intermedios desaparecieron.** En el original cada rama terminaba el escenario. Con un bucle no pueden: si después de registrar una clase el escenario termina, nunca se llega a la segunda. Cada rama del bucle termina en una acción (registrar, anotar, informar) y vuelve al "Mientras". Este es el error más común al meter un bucle: dejar los FIN de antes.
- **Ofrecer un plan nuevo (8 a 11)** quedó **después** del bucle, no adentro. Tiene sentido: cuando se le acabaron las clases y quiere más. Si contrata, vuelve al bucle (10); si no, termina (11). Un ofrece, dos caminos.
- **Los recursos** suman la grilla de clases y la lista de espera, que el original usaba en sus episodios sin listarlas. 🧵 Eso es un hallazgo del módulo 5.
- Escribí "Si existe cupo…" (7.3) en vez del "4. Existe cupo…" del original. 🧵 Por qué, en el módulo 5.

**Sobre las dos formas de bucle:** acá conviven. El "Mientras" (7) escribe el bucle principal; el "vuelve al episodio 7" (10) sirve para **reentrar** al bucle desde afuera, después de contratar el plan. Lo que no conviene es escribir el mismo bucle de las dos formas a la vez. Si preferís no usar "Mientras", el bloque 7 se escribe sin encabezado y al final va: *"7.10. Si el Socio tiene clases disponibles en su plan y quiere inscribirse en otra clase, vuelve al episodio 7.1."* Es equivalente.

## 8. Hilos

**Cerrados:** "Si…" y corchetes del módulo 1 (condicional y optativo).
**Abiertos:** "4. Existe cupo disponible en la clase": ¿está bien escrito como episodio? Y la precondición de Inscribir a clase que contradice sus propios episodios. Los dos van al módulo 5.

---

## Checkpoint del módulo 2

Respondé sin mirar el texto. Sin respuestas acá: van al complemento.

1. Corregí estos episodios y decí qué regla rompía cada uno: (a) "Consultar la carpeta de clases." (b) "El profesor gestiona la inscripción." (c) "El socio llega, pide una clase y da su nombre." (d) "El sistema permite anotar al socio."
2. ¿Cuál es la diferencia entre un episodio condicional y uno optativo? ¿Cuál prefiere la cátedra y por qué?
3. "7. El profesor verifica si el socio avisó su ausencia el día anterior." ¿Qué le falta a este escenario después del 7? Escribí los episodios que faltan.
4. Escribí de las dos formas (con "Mientras" y con "vuelve al paso") la repetición de este caso: el profesor llama uno por uno a los socios de la lista de espera hasta que alguno acepte el cupo.
5. ¿Qué diferencia hay entre "Si no hay cupo, el profesor ofrece la lista de espera" y una excepción? Da un ejemplo de excepción para Inscribir a clase, escrita con la forma Causa (Solución).
6. En la versión corregida, ¿por qué no pueden quedar los FIN DEL ESCENARIO de las ramas 4.3.2, 4.6.3 y 6.3 del original? ¿Qué pasaría con un socio que quiere anotarse en dos clases?
7. La plantilla de la cátedra junta precondición y restricción en un campo. ¿Qué es cada cosa en el modelo? Da un ejemplo de restricción para Inscribir a clase.

## Qué viene en el módulo 3

Los episodios en MAYÚSCULA: qué es un subescenario, cuándo conviene partir un escenario, qué tiene que cumplir el escenario grande respecto de los chicos, y el escenario integrador, que junta varios para dar la visión global. Con el ejercicio del equipo 3 (Cambiar inscripción a clase) en sus tres versiones.

---

**FIN DEL MÓDULO 2 — Clase desde cero — Escenarios**
