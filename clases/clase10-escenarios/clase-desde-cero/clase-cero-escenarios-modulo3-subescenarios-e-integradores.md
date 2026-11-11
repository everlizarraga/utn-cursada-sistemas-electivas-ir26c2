# Clase desde cero — Escenarios — Módulo 3: Subescenarios e integradores

**Serie:** Clase desde cero — Escenarios (módulo 3 de 5) · **Materia:** Ingeniería de Requisitos · **Unidad:** clase10

---

## Sobre este documento

**Qué cubre:** qué es un subescenario y cuándo conviene partir un escenario; qué tiene que cumplir el escenario grande respecto de los chicos; qué es un escenario integrador y para qué sirve; y la diferencia entre las dos cosas. Con dos ejemplos trabajados: Cambiar inscripción a clase (el ejercicio del equipo 3, en sus tres versiones) y Administrar la agenda de reuniones.

**Qué NO cubre:** escenario actual vs. futuro y la comparación con casos de uso (módulo 4); la revisión completa (módulo 5).

## De dónde venís

Del módulo 1: un episodio en MAYÚSCULA es otro escenario completo. Del módulo 2: Inscribir a clase tiene dos subescenarios (REGISTRAR RESERVA DE CUPO EN CLASE y CONTRATAR PLAN DE CLASES) y la versión corregida de tu ejercicio los usa. De la clase02: inclusión y extensión en casos de uso.

---

## 1. 🔴 El subescenario

En Inscribir a clase, el episodio 4.3.1 dice solo:

> 4.3.1. REGISTRAR RESERVA DE CUPO EN CLASE

No dice cómo se registra. No dice que el profesor abre la carpeta de clases, busca la clase, escribe el nombre del socio, marca una clase menos en la ficha. Todo eso existe, pero está **en otro escenario**, uno que se llama REGISTRAR RESERVA DE CUPO EN CLASE y que tiene sus propias partes: objetivo, actores, recursos, episodios. Desde Inscribir a clase, se lo "llama" por el título.

Eso es un **subescenario**: un episodio que es, a su vez, un escenario. Se escribe el título en MAYÚSCULA, y el título de un subescenario es la misma oración que el episodio, sin las restricciones.

**¿Para qué?** Por tres motivos, y alcanza con uno:

1. **Hay un comportamiento común a varios escenarios.** Registrar la reserva pasa en Inscribir a clase y en Cambiar inscripción, y pasaría en cualquier otro escenario donde el socio consiga un lugar. Se escribe una vez y se llama desde todos.
2. **Aparece un camino alternativo o condicional complejo.** Si "contratar un plan nuevo" tiene diez pasos propios (elegir plan, pagar seña, registrar en la ficha…), meterlos adentro de Inscribir a clase lo haría ilegible. Se saca a CONTRATAR PLAN DE CLASES.
3. **Hay que resaltar una situación con objetivo propio dentro de otra.** Dar el aviso de cancelación a los convocados tiene un objetivo claro ("que todos sepan que no hay reunión") y vale la pena verla sola.

Es la misma idea que la inclusión en casos de uso, con una diferencia: en casos de uso la inclusión es una flecha en un diagrama; acá es una oración en el medio de la lista de episodios, y el subescenario puede ser condicional ("Si la convocatoria ya existe, la secretaria DA EL AVISO…") u optativo.

## 2. 🔴 La regla de coherencia

Si un escenario llama a otro, los dos tienen que ser compatibles. Es la regla que la cátedra más repite sobre subescenarios:

| El escenario grande… | …respecto del chico |
|---|---|
| **Recursos** | Tiene que tener disponibles los recursos que el chico usa. Si REGISTRAR RESERVA usa la carpeta de clases, Inscribir a clase tiene que listar la carpeta de clases. En la práctica: los recursos del grande **suman** los de sus subescenarios |
| **Actores** | Los actores que participan en el chico participan en el grande |
| **Contexto geográfico** | El chico pasa en el mismo lugar que el grande, o en uno compatible. No puede ser que Inscribir a clase pase en el centro y REGISTRAR RESERVA en la casa del socio |
| **Contexto temporal** | Mismo criterio: si el grande pasa en horario de clases, el chico también |
| **Objetivo** | El objetivo del chico tiene que estar **alineado** con el del grande. No podés llamar desde Anular la reunión a un escenario cuyo objetivo sea agendar una reunión |
| **Precondición** | La precondición del chico tiene que estar satisfecha en el punto donde se lo llama. Si REGISTRAR RESERVA pide "el socio tiene clases en el plan", Inscribir a clase lo verifica antes de llamarlo (y lo hace: episodio 4.2) |

La idea de fondo: **cuando la reunión se anuló, se anuló del todo**. Si Anular la reunión llama a ANULA LA RESERVA DE MATERIAL FÍSICO, y ese subescenario necesita el "material físico" como recurso, el escenario grande lo tiene en su lista. No puede ser que la reunión quede cancelada y el proyector quede bloqueado porque el recurso no estaba.

## 3. 🔴 El escenario integrador

Ahora el caso opuesto. No un escenario que *llama* a otros en el medio de sus pasos, sino uno **hecho enteramente de otros escenarios**:

> **Título:** ADMINISTRAR LA AGENDA DE REUNIONES
> **Objetivo:** Administrar la agenda de reuniones eficiente y efectivamente.
> **Contexto:** Precondición: existe un tema a tratar o resolver por dos o más personas.
> **Episodios:**
> 1. REQUERIR UNA REUNIÓN
> 2. DISEÑAR LA AGENDA DE REUNIONES
> 3. ORGANIZAR LA REUNIÓN
> 4. Si la reunión no se canceló, ASISTIR A LA REUNIÓN

Cada episodio es el **título de un escenario ya escrito**. Esto es un **escenario integrador**: da la **visión global**. Si tenés treinta escenarios de una oficina, el integrador te muestra en cuatro líneas cómo se suceden los principales. Es la operatoria de la secretaria vista desde arriba.

Dos cosas para notar:

- **"Administrar" acá está bien.** En casos de uso, "administrar" y "gestionar" están prohibidos porque no son una función concreta. En un integrador, es exactamente lo que se quiere decir: la vista general de un montón de situaciones. El integrador es el lugar donde esos verbos sirven.
- **El integrador no exige secuencia estricta.** Diseñar la agenda, organizar la reunión y asistir no pasan uno pegado al otro: pueden pasar días en el medio. El integrador junta situaciones **relacionadas en el tiempo**, no necesariamente consecutivas. Por eso un integrador puede abarcar lo que un escenario común (que tiene "tiempo continuo") no podría.

**¿Qué componentes lleva?** Los mismos que cualquier escenario. Sus recursos son la unión de los recursos de los escenarios que integra; sus actores, la unión de los actores; su objetivo y su contexto tienen que ser coherentes con los de todos ellos (la regla de la sección 2, aplicada a todos a la vez).

> ⚠️ **Nota de cátedra.** En la lectura del aula, el integrador deja actores y recursos vacíos ("--"), porque serían la lista completa de todo el conjunto. En la materia se enseña que el integrador **sí lleva todos los componentes** y que sus recursos son la suma de los de sus subescenarios. Para el parcial, como la cátedra: con recursos.

🕳️ **Madriguera — cómo se construyen los integradores.** La lectura del aula tiene un procedimiento de cinco pasos para armar integradores a partir de un conjunto grande de escenarios: agruparlos en jerarquías, detectar órdenes parciales, armar secuencias, construir esqueletos y completar componentes. La cátedra no lo pide. También hay seis operaciones para reorganizar escenarios (aplanar, factorizar, consolidar, dividir, fusionar, separar). Tampoco se evalúan. *Volvé al camino.*

> 🎓 **Para el parcial, si te preguntan: ¿qué es un escenario integrador?**
> Es un escenario cuyos episodios son títulos de otros escenarios ya descriptos. Da la visión global del negocio vinculando escenarios dispersos y relacionados en el tiempo, sin exigir continuidad entre ellos. Sus recursos, actores, objetivo y contexto deben ser coherentes con los de los escenarios que integra.

## 4. 🔴 Subescenario vs. integrador

Se confunden porque los dos usan MAYÚSCULA. La diferencia:

| | Escenario con subescenarios | Escenario integrador |
|---|---|---|
| **Qué es** | Una situación real, con pasos propios, que en algún punto llama a otra | Una vista de conjunto, armada solo con títulos de otros escenarios |
| **Sus episodios** | Mezcla de acciones simples y llamadas en mayúscula | Casi todos en mayúscula |
| **Tiempo** | Continuo: empieza y termina de una vez | Puede abarcar situaciones separadas en el tiempo |
| **Ejemplo** | Inscribir a clase (llama a REGISTRAR RESERVA) | Administrar la agenda de reuniones |

Un caso límite, que es justo el ejercicio que sigue: un escenario corto hecho casi solo de llamadas, pero que describe una situación real y continua. En la lectura, eso es un escenario con subescenarios, no un integrador. Lo que lo define no es cuántas mayúsculas tiene, sino si describe una situación concreta del negocio o una vista global.

> ⚠️ **Nota de cátedra.** En la materia, la palabra "integrador" se usa **también** para el escenario grande que llama subescenarios: la consigna del ejercicio que sigue dice "completar el siguiente escenario integrador", y en clase se habla de "el escenario que lo integra, el mayor". En la lectura, integrador es solo el de visión global. **En el parcial, si te nombran "integrador" a un escenario con subescenarios, no lo discutas:** lo que evalúan es la coherencia entre el grande y los chicos (sección 2), no la etiqueta.

## 5. 🔴 Ejemplo trabajado: Cambiar inscripción a clase

**La consigna del equipo 3:** "completar el siguiente escenario integrador" (CAMBIAR INSCRIPCIÓN A CLASE, con la tabla vacía) usando dos escenarios ya escritos: ANULAR INSCRIPCIÓN A CLASE e INSCRIBIR A CLASE / RESERVAR CUPO EN CLASE. La situación: un socio anotado los jueves quiere pasarse a los martes.

**Versión 1:**

> 1. El socio le comunica a la profesora que va a cambiar de clase.
> 2. ANULAR INSCRIPCIÓN A CLASE
> 3. INSCRIBIR A CLASE / RESERVAR CUPO EN CLASE
> 4. La profesora confirma la solicitud.

Es lo primero que se le ocurre a cualquiera: primero me borro del jueves, después me anoto el martes. Compila, digamos. Pero pensá qué pasa si el martes no hay cupo: el socio ya se borró del jueves y ahora no tiene ninguna clase. Se quedó peor que antes.

**Versión 2:**

> 1. El socio le comunica a la profesora que va a cambiar de clase.
> 2. La profesora revisa si se puede anotar en la clase que quiere.
> 3. ANULAR INSCRIPCIÓN A CLASE
> 4. INSCRIBIR A CLASE / RESERVAR CUPO EN CLASE
> 5. La profesora confirma la solicitud.

Mejor: se mira antes si hay lugar. Pero el episodio 2 es un "revisa" sin sus dos caminos (módulo 2: todo verificar abre dos caminos). Y además revisa algo que INSCRIBIR A CLASE ya revisa adentro (consulta la grilla, ve si hay cupo). Está duplicado.

**Versión 3:**

> 1. El socio le comunica a la profesora que va a cambiar de clase.
> 2. INSCRIBIR A CLASE / RESERVAR CUPO EN CLASE
> 3. ANULAR INSCRIPCIÓN A CLASE
> 4. La profesora confirma la solicitud.

Invertir el orden resuelve el problema de la versión 1 sin duplicar nada: primero me anoto el martes; si lo logré, me borro del jueves. Pero todavía le falta algo: ¿y si no logré anotarme el martes? ¿Anulo igual? Depende. A veces no: el socio prefiere quedarse en el jueves. A veces sí: "por más que quiera, no puedo venir el jueves". Las dos situaciones son reales, y el escenario tiene que contemplarlas.

**Versión final:**

> **Nombre Escenario:** CAMBIAR INSCRIPCIÓN A CLASE
> **Rol/es/Actor/es:** Socio, Profesora
> **Objetivo:** Cambiar la inscripción de un socio de una clase por otra clase en otro día y/u horario.
> **Restricciones/precondición:** El socio debe estar inscripto a una clase.
> **Episodios:**
> 1. El socio le comunica a la profesora que quiere cambiar de clase.
> 2. La profesora le pregunta al socio si mantendría la clase actual en caso de no conseguir cupo en la nueva.
> 3. INSCRIBIR A CLASE / RESERVAR CUPO EN CLASE
> 4. Si el socio obtuvo cupo en la nueva clase, ANULAR INSCRIPCIÓN A CLASE.
> 5. Si el socio no obtuvo cupo en la nueva clase y no mantiene la clase actual, ANULAR INSCRIPCIÓN A CLASE.
> 6. La profesora confirma al socio el resultado del cambio.
> 7. FIN DEL ESCENARIO
> **Contexto Geográfico/Temporal:** En el Centro de Entrenamiento Vida Sana. En el horario de clases.
> **Recursos:** Carpeta de clases. Grilla de clases. Carpeta de fichas de socios. Carnet ficha del socio. Lista de espera.

**Por qué está escrito así:**
- **Primero intentar, después anular.** El orden importa: anular sin tener lo nuevo deja al socio sin clase.
- **Los dos subescenarios se llaman sin condición y con condición.** INSCRIBIR se intenta siempre. ANULAR es condicional, y hay **dos** condiciones distintas que llevan a anular: logré la nueva (4) o no la logré pero igual no voy a ir (5). Si no se da ninguna, el socio se queda donde estaba y el escenario termina igual.
- **El episodio 2 existe para que el 5 tenga de dónde salir.** Si nadie le preguntó al socio si mantiene la clase actual, el escenario no puede decidir en el 5. Toda condición se apoya en algo que un episodio anterior averiguó.
- **Se sacó la precondición "debe haber cupo en la clase deseada"** que tenía la consigna: no es condición para *empezar*, es lo que INSCRIBIR verifica adentro.
- **Los recursos son la suma** de los de los dos subescenarios: INSCRIBIR usa la carpeta de clases, la grilla y la lista de espera (las dos últimas las usa en sus episodios aunque la versión original no las liste; módulo 5); ANULAR usa la ficha del socio y la carpeta de clases. Regla de coherencia (sección 2). La consigna traía además "Inscripción" como recurso; se sacó porque la inscripción es lo que este escenario modifica, no algo que tiene que estar disponible para empezar.
- **El objetivo es uno:** cambiar la inscripción. Si lo escribieras como "anular e inscribir", estarías diciendo dos cosas; el objetivo tiene que ser cohesivo.
- Para la lectura es un **escenario con subescenarios**: describe una situación concreta y continua (el socio en el mostrador), aunque casi todos sus episodios sean llamadas. La cátedra lo llama "integrador" en la consigna (ver la nota de la sección 4): las dos cosas conviven, y lo que importa es la coherencia.

**Lo que esto muestra:** entre dos llamadas en mayúscula puede y suele haber episodios simples o condicionales que **deciden el camino**. Esa lógica (cuándo anular, cuándo no) vive en el escenario grande. Guardá esta idea: en el módulo 4 es la clave de por qué un escenario no se puede convertir uno a uno en casos de uso.

## 6. Hilos

**Cerrado:** la MAYÚSCULA del módulo 1, ahora con cuándo usarla y qué tiene que cumplir.
**Siguen abiertos:** "4. Existe cupo" y la precondición contradictoria (módulo 5).

---

## Checkpoint del módulo 3

Respondé sin mirar el texto. Sin respuestas acá: van al complemento.

1. ¿Cuáles son los tres motivos para sacar una parte de un escenario a un subescenario? Da un ejemplo de Vida Sana para cada uno.
2. INSCRIBIR A CLASE llama a REGISTRAR RESERVA DE CUPO EN CLASE. Si ese subescenario usa como recurso la "carpeta de clases" y pasa "en el mostrador del centro", ¿qué tiene que cumplir INSCRIBIR A CLASE? Nombrá al menos tres cosas.
3. ¿Por qué "Administrar la agenda de reuniones" puede abarcar situaciones separadas por días, si un escenario tiene que tener tiempo continuo?
4. ¿Por qué "Gestionar socios" no sirve como caso de uso pero sí puede servir como escenario integrador?
5. Explicá qué tenía de malo la versión 1 de Cambiar inscripción (anular primero) con un ejemplo concreto. ¿Qué agrega la versión final que la 3 no tenía?
6. Cambiar inscripción a clase tiene tres de siete episodios en mayúscula. Según la lectura, ¿es un integrador o un escenario con subescenarios? ¿Y cómo lo llama la cátedra? Explicá por qué la diferencia de nombre no cambia lo que hay que verificar.

## Qué viene en el módulo 4

El escenario cuando entra el software: actual vs. futuro, qué cambia y qué no, la "ubicuidad" y la diferencia entre sistema de información y sistema de software. Y la pregunta que la cátedra dedicó una clase entera a contestar: ¿un escenario es lo mismo que un caso de uso? Con lo que hizo cada equipo al intentar convertirlos.

---

**FIN DEL MÓDULO 3 — Clase desde cero — Escenarios**
