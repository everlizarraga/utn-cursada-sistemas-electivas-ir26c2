# Clase desde cero — Escenarios — Roadmap

**Materia:** Ingeniería de Requisitos · **Cubre:** clase10 (15/10), la introducción del 1/10 y la parte de escenarios de la clase13 (5/11) · **Serie:** `clase-cero-escenarios-moduloN-*.md`
**Para qué sirve este archivo:** es el plan de la serie. Te dice qué vas a aprender, en qué orden, cuánto pesa cada parte para el parcial y qué queda afuera a propósito. No es material de estudio: el estudio está en los módulos.

---

## Sobre este documento

- **Qué es un escenario, en una línea:** el relato, escrito con una estructura fija, de una situación que pasa en el negocio del cliente. Por ejemplo: "un socio se inscribe a una clase del gimnasio", paso por paso, con quién participa, qué se necesita y qué puede salir mal.
- **Por qué existe esta serie:** la introducción la dio la profe el día del parcial (vos no estabas) y la clase del 15/10 fue casi toda ejercicio en salas. Acá el tema se enseña desde cero.
- **Qué asume que ya sabés:** casos de uso (clase02): actor, flujo normal, flujo alternativo, inclusión y extensión. Y el LEL (serie anterior): símbolo, sujeto, objeto. Si todavía no hiciste la serie de LEL, hacela primero.
- **Qué viene después:** la autoevaluación tipo parcial y la práctica pre parcial del 12/11.

**Palabras que usa este plan:**
- **Módulo:** un archivo de estudio, pensado para una sesión de 40 a 60 minutos.
- **Peso:** cuánto importa para el parcial. 🔴 central y evaluable · 🟡 secundario · 🟢 mencionado al pasar.
- **Hilo:** una pregunta que un módulo deja abierta a propósito y otro módulo responde más adelante.
- **Checkpoint:** las preguntas del final de cada módulo. Van sin respuestas para que las intentes solo; las respuestas se juntan después en el complemento.
- **Madriguera 🕳️:** una nota de 2 líneas sobre algo que existe en las lecturas pero que la profe no da ni evalúa.
- **"La consigna de tu equipo":** el ejercicio que le tocó al equipo 6 el 15/10: modificar el escenario "inscribir a clase" para que el socio se inscriba en varias clases. "Equipo 3" es el que tuvo que completar un escenario que integra otros dos.

## Paso 0 — Cuánto hay que aprender, en serio

- **Conceptos nuevos de verdad:** 5. Las partes de un escenario, los tipos de episodio, el subescenario y el integrador, escenario actual vs. futuro, y la lista de control para validar uno.
- **Lo que ya sabés con otro nombre:** episodios ≈ pasos del flujo de un caso de uso; precondición, actores y cursos alternativos ya los viste. Eso baja mucho la dificultad.
- **Lo demás son reglas de escritura:** sujeto + verbo en presente + objeto, un verbo por episodio, condicional con "Si…", bucle con "Mientras…".
- **Dificultad real:** 5 sobre 10. El punto más fino es la diferencia entre caso de uso y escenario, que la profe trabajó toda una clase y va a preguntar.
- **Tiempo estimado:** 5 módulos de 40 a 60 minutos cada uno, más checkpoint. Unas 5 horas. (Son 5 y no 4 porque la parte de "actual vs. futuro" y "no es un caso de uso" es la que más va a preguntar y merece módulo propio.)

## Qué evalúa la profe (esto calibra todo)

Lo dijo con todas las letras el 15/10: **"este cuatrimestre no vamos a armar un escenario; vamos a validar que esté completo"**. Señales:

1. **Dado un escenario, decir qué le falta o qué está mal.** Su lista, dicha en clase: tiene recursos, tiene precondición y es para *iniciar* (no para terminar), tiene contexto, tiene objetivo. Más sus correcciones de siempre: todo "verificar" abre dos caminos; el escenario grande es coherente con sus subescenarios.
2. **Redacción de episodios:** sujeto, verbo activo conjugado, un solo verbo; condicional con "Si…"; ella prefiere eso antes que los corchetes.
3. **El bucle:** cómo se escribe que algo se repite. Ella lo escribe "Mientras…" al principio, o "si quedan…, vuelve al paso N" al final. No está en la PPT; ella sostiene que está en el apunte. Tu forma, "se repiten los episodios 2 a 11", la aceptó como legible pero menos formal: **en el parcial usá la de ella.**
4. **Subescenarios en MAYÚSCULA** y coherencia entre el escenario grande y los chicos (recursos, contexto, objetivo).
5. **Caso de uso ≠ escenario:** la conclusión de la clase. Van a pedir compararlos, y el TP con IA sale de ahí.
6. **Escenario actual vs. futuro:** qué cambia cuando entra el software (recursos, contexto, actores) y qué no. Las dos ideas que repitió: "ubicuidad" (con una app, cualquier lugar y cualquier momento) y "sistema de información ≠ sistema de software" (el gimnasio con carpetas ya tiene un sistema de información).

## Los 5 módulos

| # | Módulo | Al terminarlo vas a poder… | Peso | Ejemplo trabajado |
|---|---|---|---|---|
| 1 | Qué es un escenario y de qué partes se compone | Leer un escenario y decir qué va en cada parte; detectar un objetivo o una precondición mal puestos | 🔴 | Anular la reunión (el ejemplo de la cátedra), campo por campo |
| 2 | Cómo se escriben los episodios | Escribir episodios simples, condicionales, optativos y con bucle; escribir excepciones | 🔴 | Inscribir a clase (Vida Sana) y la consigna de tu equipo, resuelta bien |
| 3 | Subescenarios e integradores | Partir un escenario largo; armar uno que integre otros; chequear que el grande sea coherente con los chicos | 🔴 | Cambiar inscripción a clase (equipo 3, tres versiones) y Administrar la agenda de reuniones |
| 4 | Actual vs. futuro, y por qué no es un caso de uso | Pasar un escenario de hoy a uno con software; explicar en qué se parecen y en qué no un caso de uso y un escenario; seguir la cadena LEL → escenario → requisito | 🔴 | La app del gimnasio; lo que hizo cada equipo al convertir a casos de uso; el pasaporte |
| 5 | Validar que un escenario esté completo | Revisar un escenario ajeno con una lista de control y entregar las correcciones | 🔴 | Taller resuelto: el escenario de Vida Sana de la cátedra y tu Word del ejercicio |

## Detalle de cada módulo

### Módulo 1 — Qué es un escenario y de qué partes se compone 🔴

**Cubre**
- Qué es una "situación" del negocio: tiene un fin, actores y recursos, un tiempo continuo, un lugar, condiciones, es independiente y concreta, y puede tener caminos alternativos. Se mira el negocio "de lejos", no la pantalla.
- Para qué sirve: capturar requisitos, capturar conocimiento del negocio, comunicarse con el cliente, trazar de dónde salió cada requisito.
- Las partes: título, objetivo, contexto (lugar, tiempo, precondición), recursos, actores, episodios, excepciones y restricción. Más la parte provisoria "Dudas", que se usa mientras se arma y tiene que quedar vacía al validar. Qué va en cada una y el error típico de cada una (objetivo ≠ título; la precondición es para empezar, no para terminar).
- Una sola regla de notación, adelantada porque es la que la profe llamó fundamental: un episodio en MAYÚSCULA es otro escenario completo, como una inclusión en casos de uso. Cuándo conviene usarlo se ve en el módulo 3.
- Lo que ya conocés de casos de uso y cómo se corresponde (y dónde no).

**No cubre:** cómo se redacta cada episodio (módulo 2).

**Ejemplo trabajado:** Anular la reunión, el de la PPT. Se lee parte por parte: por qué el objetivo dice "liberar la agenda" y no "anular la reunión", por qué la precondición es "ya fue agendada", por qué el medio de comunicación es un recurso.

**Hilos que abre:** (a) en el ejemplo hay un episodio que empieza con "Si…" y otro entre corchetes: ¿qué significan? (b) el ejemplo no tiene la parte "Excepciones": ¿falta algo?

**Checkpoint:** 6 preguntas.

### Módulo 2 — Cómo se escriben los episodios 🔴

**Cubre**
- La oración: sujeto + verbo activo en presente + objeto. Un solo verbo. Verbos concretos (no "gestionar", no "usar").
- Los tipos: simple, condicional ("Si… entonces"), optativo (entre corchetes), no secuencial (entre #). Cuál prefiere la profe y por qué.
- Todo "verificar / validar / controlar" abre dos caminos: hay que escribir qué pasa si da mal.
- El bucle: "Mientras haya…" al principio, o "si quedan…, vuelve al paso N" al final. La forma de la profe, y por qué la tuya se entiende pero conviene la de ella.
- Excepciones: causa (solución). Con número de episodio si pasa en un punto; sin número si puede pasar en cualquier momento. Restricción: un requisito de calidad pegado a un episodio.
- La plantilla que usa la cátedra en Vida Sana y en qué se aparta del modelo: junta precondición con restricción en un campo, escribe "FIN DEL ESCENARIO", numera 4.1, 4.2. No son errores para la profe: para el parcial, se escribe como ella.

**Ejemplo trabajado:** Inscribir a clase / Reservar cupo en clase (Vida Sana), leído episodio por episodio; tiene tres subescenarios, que ya sabés reconocer por la MAYÚSCULA. Después, la consigna de tu equipo: modificarlo para varias clases, con el bucle bien puesto. Es la versión corregida de lo que entregaste.

**Hilos que cierra:** las marcas de notación del módulo 1 ("Si…" y corchetes). **Abre:** el episodio "4. Existe cupo disponible en la clase": ¿está bien escrito?

**Checkpoint:** 7 preguntas.

### Módulo 3 — Subescenarios e integradores 🔴

**Cubre**
- Subescenario: cuándo conviene partir (comportamiento repetido, camino alternativo complejo, situación con objetivo propio). La regla de la profe: el escenario grande tiene que ser coherente con los chicos en recursos (suma los de ellos), lugar, tiempo y objetivo.
- Integrador: un escenario cuyos episodios son títulos de otros escenarios. Da la visión global ("administrar", "gestionar" sirven acá, no como caso de uso). Según la profe tiene todos los componentes y sus recursos son la unión de los de sus subescenarios. 🕳️ En la lectura de Hadad el integrador deja actores y recursos vacíos; para el parcial, como la profe.
- El orden de los episodios en un integrador: primero intentar, después anular (el caso "cambiar inscripción").

**Ejemplo trabajado:** Cambiar inscripción a clase, el del equipo 3, con las tres versiones que se discutieron en clase y por qué la última es mejor. Administrar la agenda de reuniones, el integrador de la cátedra.

**Hilos que cierra:** ninguno nuevo; profundiza la MAYÚSCULA del módulo 1.

**Checkpoint:** 6 preguntas.

### Módulo 4 — Actual vs. futuro, y por qué no es un caso de uso 🔴

**Cubre**
- Escenario actual (qué pasa hoy) vs. futuro (qué va a pasar con el software). Misma estructura, distinto contenido. El actual sale del LEL; el futuro sale de los actuales y de los objetivos. El actual puede tener algunos requisitos; el futuro tiene los requisitos acordados. En el futuro el software es un actor principal.
- Qué cambia: recursos, contexto (ubicuidad: cualquier lugar y momento), actores (la recepcionista puede desaparecer). Qué suele no cambiar: la funcionalidad abstracta.
- Sistema de información ≠ sistema de software: el gimnasio con planillas ya es un sistema de información.
- Caso de uso ≠ escenario: parecidos (actores, pasos, objetivo) y diferencias (el escenario describe una situación con continuidad en el tiempo; el caso de uso modela una función abstracta). Por qué al pasar un escenario a casos de uso se pierde la lógica que decide el camino. No hay relación uno a uno.
- La cadena LEL → escenario actual → escenario futuro → RF / RNF, con el ejemplo del pasaporte de la cátedra. Es la trazabilidad que la profe nombra en las dos PPTs.

**Ejemplo trabajado:** la app del gimnasio (el mockup que mostró la profe) como escenario futuro de "inscribir a clase". Y lo que hizo cada equipo al convertir a casos de uso: el sobrediseño, los subescenarios como extensiones que no convencieron, la relación rara entre "contratar plan" y "ofrecer plan", y qué les corrigió la profe.

**Hilos que cierra:** "¿para qué sirve el LEL después?", de la serie anterior.

**Checkpoint:** 7 preguntas.

### Módulo 5 — Validar que un escenario esté completo 🔴

**Cubre**
- **La lista de la profe (🔴):** tiene objetivo y no repite el título; tiene recursos; tiene precondición y es para iniciar; tiene contexto; todo "verificar" abre dos caminos; los subescenarios son coherentes con el grande; "Dudas" quedó vacío; los episodios son acciones con sujeto y un verbo.
- **La lista de Hadad, para afinar (🟡):** sintaxis (cada parte completa, más de un episodio); relación entre partes (todo actor aparece en algún episodio, todo recurso se usa, todo lo usado está listado); sentido (los episodios logran el objetivo); entre escenarios (todo subescenario nombrado existe, excepciones tratadas, contexto coherente). Heurísticas de redacción de Hadad: recursos implícitos (la planilla que nadie nombró), recursos triviales (la lapicera no va), actores que se mencionan pero no actúan, evitar "puede / debe / podría".
- Contra el LEL: actores = sujetos, recursos = objetos del LEL.
- Dos columnas que hay que tener claras: **lo que la profe corrige** y **lo que Hadad corregiría pero la cátedra tolera** (por ejemplo "FIN DEL ESCENARIO", o "profesora" en actores y "profesor" en episodios: en clase dijo "no importa, está bien").

**Ejemplo trabajado 1:** el escenario Inscribir a clase que repartió la cátedra, revisado con las dos listas: el episodio 4 describe un estado y no una acción; faltan la grilla de clases y la lista de espera en recursos; la precondición contradice los episodios 4.4 a 4.8; no hay excepciones. Cada hallazgo marcado en la columna que corresponde.

**Ejemplo trabajado 2:** tu Word del ejercicio. Qué estaba bien (la validación inicial, el 1.3 como condicional), qué no (el bucle que no se alcanza, los dos episodios 12, objetivo y precondición en singular, la contradicción 1.3 vs. 4.4) y la versión final.

**Hilos que cierra:** "4. Existe cupo" y "¿faltan las excepciones?".

**Checkpoint:** 8 preguntas.

## Mapa de hilos que se cierran

| Hilo | Se abre en | Se cierra en |
|---|---|---|
| "Si…" y corchetes en el ejemplo | M1 | M2 (tipos de episodio) |
| ¿Faltan las excepciones en el ejemplo? | M1 | M5 (lista de control) |
| "4. Existe cupo disponible": ¿está bien? | M2 | M5 (episodios son acciones) |
| Tu ejercicio entregado: ¿qué tenía mal? | M2 | M5 (taller 2) |
| ¿Para qué sirve el LEL después? | Serie LEL, M4 | M4 (trazabilidad) |

## Lo que queda afuera a propósito (madrigueras)

Están en las lecturas del aula, pero la profe no las dio ni las evalúa:
- Las operaciones para reorganizar escenarios (aplanar, factorizar, consolidar, dividir, fusionar, separar).
- Los 5 pasos para construir jerarquías e integradores a partir de órdenes parciales.
- La gramática formal de los episodios (BNF) y los diagramas entidad-relación del modelo.
- El integrador sin actores ni recursos, versión Hadad (módulo 3).
- Historias de usuario: la profe las nombró como posible comparación en el TP con IA, pero no las enseñó.

## Cómo usar la serie

1. Un módulo por sesión. Leé, hacé el checkpoint sin mirar el material, anotá lo que no te cierre.
2. Las dudas van al chat; después se juntan en el complemento.
3. **Calendario:** módulos 1 y 2 el 9/11; módulo 3 el 10/11; módulos 4 y 5 el 11/11. El módulo 5 se genera después de la clase del jueves 5/11, que es de verificación de LEL y escenarios, para incorporar lo que la profe corrija ahí. **Grabá esa clase.** Llegás a la práctica del 12/11 con las dos series cerradas y una semana para la autoevaluación antes del 19/11.

## Insumos de la serie (para la generación)

PPT "Escenarios" de la cátedra (manda sobre el resto) · transcripciones del 1/10 (introducción), del 15/10 (teoría, tu sala y puesta en común) y del 5/11 (cuando esté) · capturas de la clase 10 (trabajos de los equipos, app del gimnasio) · enunciado del ejercicio y tu Word · Hadad cap. 5 y cap. 6 (heurísticas de descripción y verificación) · PPT de LEL (slide de trazabilidad).

---

**FIN DEL ROADMAP — Clase desde cero — Escenarios**
