# Clase desde cero — Escenarios — Módulo 5: Validar que un escenario esté completo

**Serie:** Clase desde cero — Escenarios (módulo 5 de 5) · **Materia:** Ingeniería de Requisitos · **Unidad:** clase10
**Versión provisoria (4/11):** se actualiza con lo que la cátedra corrija en la clase del 5/11, que es de verificación de LEL y escenarios.

---

## Sobre este documento

**Qué cubre:** la lista de control de la cátedra para un escenario (lo que se evalúa), la lista de la lectura para afinar, el control contra el LEL, qué corrige la cátedra y qué tolera, y dos talleres resueltos: el escenario Inscribir a clase tal como lo repartió la cátedra, y tu Word del ejercicio. Cierra los hilos que quedaron abiertos.

**Qué NO cubre:** nada nuevo de teoría. Es aplicación de todo lo anterior.

## De dónde venís

De toda la serie. Y de la cátedra, una frase: *este cuatrimestre no se arma un escenario de cero; se valida que esté completo.* Este módulo es eso.

---

## 1. 🔴 La lista de la cátedra

Lo que se revisa, en el orden en que conviene mirarlo. Cada punto es algo que la cátedra dijo o corrigió.

| # | Control | Cómo se mira |
|---|---|---|
| 1 | **Tiene objetivo, y no repite el título** | ¿Dice *para qué*? "Liberar la agenda", no "anular la reunión" |
| 2 | **Tiene recursos**, y son los que los episodios usan | Leé cada episodio: ¿qué cosa usa? ¿Está en la lista? ¿Hay algo en la lista que ningún episodio usa? |
| 3 | **Tiene precondición, y es para iniciar** | ¿Describe el estado *antes* de empezar? ¿O describe el final, o algo que se verifica adentro? |
| 4 | **Tiene contexto** (lugar, tiempo, o al menos uno) | ¿Dónde y cuándo pasa? |
| 5 | **Los episodios son acciones** con sujeto, verbo activo en presente y un solo verbo | ¿Cada línea dice quién hace qué? ¿Hay estados disfrazados de episodios? |
| 6 | **Todo "verificar" abre dos caminos** | Por cada verifica / consulta / controla, ¿están los dos resultados? |
| 7 | **Los subescenarios son coherentes con el grande** | Recursos, actores, contexto y objetivo (módulo 3, sección 2) |
| 8 | **Las repeticiones están escritas** como "Mientras…" o "vuelve al paso N" | ¿Hay un "cada", "todos", "varios" sin bucle? |
| 9 | **"Dudas" está vacío** | Si queda una duda, el escenario no está listo para validar |
| 10 | **Los episodios logran el objetivo** | El último paso de cada camino, ¿cumple lo que dice el objetivo? ¿No sobra ni falta un paso? |

## 2. 🟡 La lista de la lectura, para afinar

La lectura del aula agrega controles más finos. No son lo que la cátedra evalúa primero, pero sirven para encontrar lo que la lista de arriba deja pasar.

**Dentro de un escenario (intra-escenario)**
- Sintaxis: cada parte está completa; hay más de un episodio.
- Relación entre partes: todo actor participa en algún episodio; todo actor que aparece en un episodio está en la lista; lo mismo con los recursos.
- Sentido: el título es coherente con el objetivo; los episodios están dentro del contexto; las precondiciones son cosas ya satisfechas, no acciones; los episodios tienen el mismo nivel de detalle.

**Entre escenarios (inter-escenario)**
- Todo subescenario en mayúscula existe como escenario escrito.
- Los episodios de un subescenario no están repetidos adentro del escenario que lo llama.
- Toda excepción tiene tratamiento: un escenario que existe o una acción simple.
- Las precondiciones de los subescenarios son coherentes con las del escenario que los llama.

**Heurísticas de redacción** (también de la lectura)
- Recursos **implícitos**: "el cajero timbra el formulario" usa una máquina timbradora, aunque no la nombre. Va en recursos.
- Recursos **triviales**: "el contador firma el cheque" usa una lapicera. No va: no es relevante.
- Un recurso **no puede ser algo que se genera** en los episodios del mismo escenario. La lista para convocatoria que se arma en este escenario es recurso en otros, no en este.
- Actores **off-stage**: "el contador analiza la cuenta del cliente". El cliente se menciona, pero no hace nada. No va en actores.
- Evitar "podría", "puede", "debe", "debería" en los episodios.

**Contra el LEL**
- Los actores son sujetos del LEL; los recursos son objetos del LEL. Si un escenario usa una palabra que no está en el LEL, o falta un símbolo o sobra una palabra.

## 3. 🔴 Dos columnas: lo que la cátedra corrige y lo que tolera

Esto es lo que más conviene tener claro para el parcial. Hay cosas que la lectura marcaría como error y que la cátedra acepta porque son parte de su plantilla. Si las "corregís" en el parcial, no sumás; si las dejás, no restás.

| La cátedra **corrige** | La cátedra **tolera** (aunque la lectura lo objetaría) |
|---|---|
| Objetivo igual al título | "FIN DEL ESCENARIO" como episodio |
| Precondición que no es para iniciar | Precondición y restricción en un mismo campo |
| Recurso que los episodios usan y no está listado | Numeración anidada (4.1, 4.3.2) |
| Episodio que es un estado y no una acción | Corchetes para lo optativo (válidos, aunque prefiere "Si…") |
| Episodio sin sujeto, o con verbo no conjugado, o con dos verbos | "Se repiten los episodios 2 a 11" como bucle (aceptado, menos formal) |
| "Verifica" con un solo camino | |
| Subescenario incoherente con el escenario grande | "Profesora" en actores y "profesor" en episodios: la cátedra no lo corrigió cuando un equipo lo tenía así |
| | Excepciones y Dudas ausentes: la plantilla de la cátedra no tiene esos campos. Preguntate qué puede fallar; si aparece algo, agregalo; si no, no es error |

Y una fila que es de la lectura, no de la cátedra: un **verbo vago** en un episodio ("gestionar", "administrar", "usar"). La cátedra lo corrige en casos de uso y admite esos verbos como título de escenarios integradores; en un episodio, la lectura pide un verbo preciso y concreto. Escribilo concreto, pero no esperes que sea lo primero que te marquen.

El criterio: la cátedra corrige lo que afecta **la lógica y la completitud**; tolera lo que es **forma de la plantilla**.

## 4. 🔴 Taller resuelto 1: Inscribir a clase, el escenario de la cátedra

El escenario del módulo 2, sección 6, revisado con las dos listas. Cada hallazgo dice en qué columna cae.

| # | Dónde | Qué está mal | Columna | Corrección |
|---|---|---|---|---|
| 1 | Episodio 4: "Existe cupo disponible en la clase." | Es un **estado**, no una acción. No tiene sujeto ni verbo activo. Lo mismo en 4.3 ("El Socio tiene clase disponible") y 4.4. La plantilla anidada lo usa como encabezado de rama, pero como episodio no cumple la regla | **Corrige** | Condicional con la acción: "Si existe cupo disponible, el Socio brinda apellido y nombre al profesor." Y el 5 pasa a "Si no existe cupo disponible, el profesor le ofrece al socio ingresar en la lista de espera": al sacar el encabezado de rama, el otro camino también necesita su condición |
| 2 | Precondición: "Debe haber disponibilidad de cupo en la clase deseada." y "El socio debe tener clase disponible en su plan de clases." | La primera contradice los episodios 5 a 12, que describen qué pasa cuando **no** hay cupo. La segunda contradice los episodios 4.4 a 4.8, que son justamente el caso en que no tiene clases en el plan. Ninguna es para iniciar: las dos se verifican adentro (3 y 4.2) | **Corrige** | Sacarlas. Una precondición honesta: "El socio tiene un plan contratado" |
| 3 | Recursos: "Carpeta de clases. Carpeta de fichas de socios. Carnet ficha del socio." | El episodio 3 usa "la grilla de la clase" y el 6.2 usa "la lista de espera". Ninguna está en recursos | **Corrige** | Agregar grilla de clases y lista de espera (o aclarar que la grilla está en la carpeta de clases). Aparte: la carpeta de fichas y el carnet se usan en 4.2 sin nombrarlos, y **sí** están listados; eso es un recurso implícito bien resuelto, como pide la lectura |
| 4 | Actores: "Socio, Profesora". Episodios: "el profesor". | Inconsistencia de nombre | **Tolera** | Si querés, unificar. No es lo que se evalúa |
| 5 | Excepciones | No hay componente de excepciones, y la plantilla de la cátedra no lo tiene. Igual conviene preguntarse: ¿qué pasa si no está la carpeta de clases? | — (lectura) | Si aparece una falla real, agregarla: "La carpeta de clases no está disponible. Episodio: 3. (El profesor registra la reserva en una hoja provisoria y la pasa después)". Si no aparece, no es error |
| 6 | Episodio 1: "El Socio se presenta en el centro de entrenamiento." | Está bien como episodio, pero repite el contexto geográfico. No es error; es redundante | — | Dejar |
| 7 | "4.1 El Socio brinda apellido y nombre" y "6.1 El Socio brinda apellido y nombre" | El mismo paso en dos ramas. En el escenario original es válido (cada rama es un camino distinto). Se vuelve un problema solo al meter un bucle (módulo 2) | — | Dejar en el original; sacar en la versión con bucle |
| 8 | FIN DEL ESCENARIO en 4.3.2, 4.6.3, 4.8, 6.3, 12 | Marcan el fin de cada camino. Para la plantilla de la cátedra está bien | **Tolera** | Dejar |
| 9 | Dudas | No hay componente. Es transitorio: tiene que quedar vacío al validar, y ausente cuenta como vacío. La plantilla de la cátedra no lo tiene | — (lectura) | Nada que agregar. Si mientras revisás te queda una duda real, anotala y resolvela antes de dar el escenario por validado |

**El hilo "4. Existe cupo" queda cerrado:** no es una acción. Es la forma en que la plantilla anidada abre una rama, y la cátedra la usa, pero si te piden revisar un escenario, es lo primero que tenés que ver. La forma correcta es el condicional con su acción.

**El hilo de las excepciones de Anular la reunión (módulo 1) también:** un escenario sin excepciones no está incompleto por eso, pero al revisarlo hay que preguntarse "¿qué puede fallar?" en cada episodio. Para Anular la reunión: "no se puede contactar a un convocado. Episodio: 4. (La secretaria deja constancia y reintenta el día de la reunión)". Si después de preguntar no aparece nada, el componente queda vacío y es válido.

## 5. 🔴 Taller resuelto 2: tu Word del ejercicio

Lo que entregaste para la consigna de tu equipo (varias clases, con límite del plan), revisado. Primero lo bueno, porque hay.

**Lo que estaba bien:**
- **La validación al principio** (1.1 a 1.3): el socio dice en cuántas clases quiere anotarse, el profesor consulta cuántas le quedan, y si pide más de las que tiene, le avisa. Es exactamente la lógica que hace falta, y el 1.3 está escrito como condicional correcto: "Si la cantidad deseada supera las clases disponibles, el profesor informa…".
- **La idea del bucle** en el episodio 12: "Si el Socio desea inscribirse en otra clase y tiene clases disponibles en su plan, se repiten los episodios 2 a 11 para la siguiente clase." Se entiende, y la cátedra lo aceptó.

**Lo que estaba mal:**

| # | Qué | Por qué | Columna |
|---|---|---|---|
| 1 | **El bucle no se alcanza nunca.** Las ramas intermedias siguen terminando en FIN DEL ESCENARIO (4.3.2, 4.6.3, 4.8, 6.3). El socio reserva en 4.3.1, llega a 4.3.2 y el escenario termina. Nunca llega al 12 | Al meter un bucle, los fines de las ramas tienen que volver al bucle, no terminar. Es el error de fondo | **Corrige** |
| 2 | **Hay dos episodios 12.** Quedó el "12. FIN DEL ESCENARIO" original y después el 12 nuevo con el bucle, y un 13 | Por el camino del 11 se llega al primer 12 y termina; el bucle tampoco se alcanza por ahí | **Corrige** |
| 3 | **Objetivo y precondición en singular.** "Un cupo en una clase determinada" | El escenario ahora es de varias clases | **Corrige** |
| 4 | **La precondición "debe haber cupo en la clase deseada"** sigue | Se verifica clase por clase adentro del bucle; no es para iniciar. Y con varias clases, ¿en cuál? | **Corrige** |
| 5 | **Contradicción entre 1.3 y 4.4 a 4.6.** El 1.3 dice "te inscribo solo en las que tenés disponibles"; el 4.4 a 4.6, adentro, le ofrece contratar un plan nuevo cuando no tiene | Dos lógicas para el mismo caso. Hay que elegir una, o ponerlas en orden: primero el tope, y si quiere más, ofrecer plan | **Corrige** |
| 6 | 1.1 a 1.3 cuelgan del "1. El Socio se presenta" como subpasos | Presentarse no tiene subpasos; son episodios propios (2, 3, 4) | **Tolera** (forma) |
| 7 | "Profesora" en actores, "profesor" en episodios | Venía así del enunciado | **Tolera** |

**La versión final** es la del módulo 2, sección 7. Compará las dos y fijate que los cinco "corrige" están resueltos: el bucle con "Mientras" (6) sin FIN intermedios; un solo FIN al final; objetivo y precondición en plural y para iniciar; y el plan nuevo **después** del bucle (7 y 8), con lo que el 1.3 y el "ofrecer plan" dejan de contradecirse: primero el tope, y si quiere más, se le ofrece.

## 6. 🔴 El procedimiento, resumido

Cuando te den un escenario para validar:

1. **Leelo entero una vez**, sin corregir. Entendé la situación.
2. **Pasá la lista de la cátedra** (sección 1), punto por punto. Anotá cada hallazgo con: dónde, qué está mal, corrección.
3. **Pasá la lista de la lectura** (sección 2) solo para lo que la primera no cubrió: recursos implícitos, actores off-stage, excepciones.
4. **Marcá cada hallazgo** como "corrige" o "tolera". Lo que tolera, no lo "arregles" en el parcial; dejalo o mencionalo en una línea.
5. **Reescribí** lo que corresponda. El escenario corregido tiene que seguir siendo el mismo escenario: misma situación, mismos caminos; solo mejor escrito y completo.

> 🎓 **Para el parcial, si te preguntan: ¿qué significa que un escenario esté completo?**
> Que tenga todos sus componentes con contenido coherente: un objetivo que no repite el título, los recursos que los episodios usan, una precondición para iniciar, un contexto, episodios que son acciones con sujeto y verbo activo, los dos caminos de cada verificación, subescenarios coherentes con el escenario que los llama, repeticiones escritas, excepciones consideradas y el componente Dudas vacío. Y que el conjunto de episodios logre el objetivo.

## 7. Cierre de la serie

Todos los hilos están cerrados:
- "Si…" y corchetes: tipos de episodio (M2).
- MAYÚSCULA: subescenario (M3).
- "4. Existe cupo": un estado disfrazado de episodio (M5).
- Precondición que contradice los episodios: no era para iniciar (M5).
- Excepciones ausentes: válido si se preguntó qué puede fallar (M5).
- ¿Para qué sirve el LEL después?: la cadena de trazabilidad (M4).

---

## Checkpoint del módulo 5

Respondé sin mirar el texto. Sin respuestas acá: van al complemento.

1. ¿Por qué "Existe cupo disponible en la clase" no es un episodio válido, si la cátedra lo usa en su plantilla? ¿Cómo se escribe bien?
2. ¿Qué tiene de malo "Debe haber disponibilidad de cupo en la clase deseada" como precondición de Inscribir a clase? Proponé una precondición correcta.
3. Leé los episodios de Inscribir a clase y listá todos los recursos que usan. Compará con la lista de recursos del escenario. ¿Qué falta?
4. Nombrá tres cosas que la cátedra corrige y tres que tolera. ¿Cuál es el criterio que separa unas de otras?
5. Un escenario tiene "7. El profesor verifica si hay lugar en la lista de espera." y después "8. El profesor anota al socio." ¿Qué falta? ¿En qué punto de la lista de la cátedra cae?
6. ¿Cuál era el error de fondo del Word del ejercicio? Explicá con un socio que quiere anotarse en dos clases qué pasaba al recorrer los episodios.
7. Escribí una excepción para Cambiar inscripción a clase, con la forma Causa (Solución), y decí en qué episodio puede ocurrir.
8. Te dan un escenario de "Avisar ausencia" para validar. Escribí, sin el escenario delante, los cinco primeros controles de la lista de la cátedra, en orden, como preguntas que le harías al escenario.

## Qué viene después

Terminaste las dos series. Lo que sigue: la **autoevaluación** tipo parcial, con un escenario y un LEL para revisar, antes de la práctica pre parcial del 12/11. Y las dudas que te hayan quedado de los checkpoints, que van al complemento.

Este módulo se actualiza con lo que la cátedra corrija en la clase del 5/11.

---

**FIN DEL MÓDULO 5 — Clase desde cero — Escenarios**
