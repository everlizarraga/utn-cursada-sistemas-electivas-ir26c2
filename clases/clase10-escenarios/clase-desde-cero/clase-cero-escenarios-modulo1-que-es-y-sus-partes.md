# Clase desde cero — Escenarios — Módulo 1: Qué es un escenario y de qué partes se compone

**Serie:** Clase desde cero — Escenarios (módulo 1 de 5) · **Materia:** Ingeniería de Requisitos · **Unidad:** clase10

---

## Sobre este documento

**Qué cubre:** qué es una "situación" del negocio y por qué conviene escribirla con estructura; para qué sirven los escenarios; las partes de un escenario, qué va en cada una y el error típico de cada una; la relación con los casos de uso que ya conocés. Todo sobre un ejemplo completo: Anular la reunión.

**Qué NO cubre:** cómo se redacta cada paso (módulo 2), cómo se parte un escenario largo (módulo 3), el escenario del futuro con software y la comparación con casos de uso (módulo 4), cómo se revisa que esté completo (módulo 5).

**Notación de la serie:** las palabras que son símbolos del LEL deberían ir marcadas; en estos módulos no se marcan para no cargar el texto, salvo cuando el punto es justamente ese.

## De dónde venís

- De la serie de LEL: qué es un símbolo, qué es un sujeto y qué es un objeto. Los actores de un escenario son sujetos del LEL; los recursos son objetos.
- De la clase02 de la materia: casos de uso. Actor, flujo normal, flujo alternativo, precondición, inclusión y extensión. Vas a ver que mucho de eso reaparece con otro nombre.

---

## 1. 🔴 Una situación del negocio

Un martes a las 9 de la mañana, en el centro de entrenamiento Vida Sana:

> Marcela, socia, entra y le dice a la profesora que quiere reservar lugar en la clase de pilates del jueves a las 10. La profesora abre la carpeta de clases, busca el jueves a las 10 y ve que hay siete anotados de ocho. Le pide a Marcela el apellido, mira en la ficha si le quedan clases en el plan, le quedan tres, y la anota. Marcela se va con su lugar reservado.

Eso es una **situación**: algo que pasa en el negocio, con un principio y un fin, con gente, con cosas, con un objetivo. Pasa todos los días, con distintas personas y distintos resultados: a veces no hay cupo, a veces a la socia no le quedan clases en el plan.

No se puede escribir una historia por cada vez que pasa. Lo que se hace es escribir **una descripción de ese tipo de situación**, que cubra el camino normal y las variantes. Esa descripción, escrita en lenguaje común pero con una estructura fija, es un **escenario**.

Para que algo sea una situación, y merezca un escenario, tiene que cumplir siete cosas. Compará con la historia de Marcela:

| La situación tiene… | En el ejemplo |
|---|---|
| Un **fin establecido** | Marcela quiere un lugar en la clase |
| **Actores y recursos** identificables | Marcela y la profesora; la carpeta de clases y la ficha |
| Un **tiempo continuo** | Empieza cuando Marcela entra y termina cuando se va anotada. No queda "en espera" dos días |
| Un **contexto geográfico** definido | En el centro, en la recepción |
| **Condiciones** que la restringen | Hay que tener clases en el plan; hay cupo de ocho |
| Es **independiente y concreta** | Se entiende sola, sin leer otra situación; y es algo real, no una idea |
| **Cursos alternativos** de acción | No hay cupo; no quedan clases en el plan |

Dos consecuencias de "tiempo continuo" que la cátedra corrige: una vez que el escenario arranca, tiene que terminar; si se interrumpe por algo, eso es una excepción o es otro escenario. Y un escenario no se queda esperando en el medio: no se escribe "y tres días después…". Si hay una espera larga, son dos escenarios.

**Se mira el negocio "de lejos".** Un escenario describe lo que pasa en el negocio, con o sin software: Marcela y la profesora con una carpeta de papel. No describe una pantalla ni una interacción con un sistema. Eso es lo que lo distingue de otras cosas parecidas, y vuelve en el módulo 4.

## 2. 🔴 Para qué sirve

Un escenario no es la especificación de requisitos. Es la **fuente** de donde salen los requisitos. Cuatro usos:

| Uso | Qué quiere decir |
|---|---|
| **Capturar requisitos** | Las situaciones del negocio son el punto de partida donde aparecen los requisitos: de "la profesora busca en la carpeta si hay cupo" sale "el sistema debe mostrar el cupo disponible de cada clase" |
| **Capturar conocimiento del negocio** | Registran cómo funciona hoy: quiénes, con qué, en qué orden |
| **Comunicar** | Están en lenguaje natural con estructura simple: el cliente lo lee y dice "sí, así es" o "no, es al revés". No hace falta saber ninguna notación |
| **Anclar la trazabilidad** | Se puede rastrear hacia atrás (de qué símbolos del LEL salió) y hacia adelante (qué requisitos salieron de él) |

El precio: hay que mantenerlos. Un escenario desactualizado comunica mal. Por eso no se escriben para todo: se escriben para las situaciones que importan.

> 🎓 **Para el parcial, si te preguntan: ¿qué es un escenario?**
> Es una narrativa estructurada de una situación del negocio, escrita en lenguaje natural con los símbolos del LEL. No reemplaza la especificación de requisitos: es la fuente donde se encuentran y de donde se derivan. Describe el negocio "de lejos", no solo la interacción usuario–sistema.

## 3. 🔴 Las partes de un escenario

Todo escenario tiene la misma estructura. Primero el ejemplo entero, después parte por parte.

> **Título:** ANULAR LA REUNIÓN
> **Objetivo:** Liberar la agenda de una reunión cancelada.
> **Contexto:** Debe realizarse antes de la fecha de la reunión.
> **Precondición:** la reunión ya ha sido agendada.
> **Recursos:** agenda, cronograma de reuniones, espacio físico, material físico, listado para convocatoria, medio de comunicación.
> **Actores:** convocante, secretaria, convocados.
> **Episodios:**
> 1. El convocante o la secretaria buscan la reunión en la agenda.
> 2. El convocante o la secretaria registran la cancelación en la agenda.
> 3. El convocante o la secretaria registran la cancelación en el cronograma de reuniones.
> 4. Si la convocatoria ya existe, la secretaria DA EL AVISO DE CANCELACIÓN a cada convocado.
> 5. La secretaria anula la reserva de espacio físico.
> 6. [La secretaria ANULA LA RESERVA DE MATERIAL FÍSICO.]

Es el escenario de una oficina donde alguien ("el convocante") organiza reuniones con ayuda de una secretaria. Leelo una vez de corrido y después seguí con la tabla.

| Parte | Qué va | En el ejemplo | El error típico |
|---|---|---|---|
| **Título** | El nombre de la situación: verbo + qué, desde el punto de vista del negocio | ANULAR LA REUNIÓN | Ponerlo desde el punto de vista de una persona en vez del negocio ("Pedir que cancelen la reunión") |
| **Objetivo** | La finalidad: **para qué** se hace. El escenario describe cómo se logra | Liberar la agenda de una reunión cancelada | Repetir el título ("anular la reunión"). El objetivo tiene una vuelta más: ¿para qué anulás? Para liberar la agenda |
| **Contexto** | Dónde (ubicación geográfica), cuándo (ubicación temporal) y en qué estado inicial (precondición). Al menos uno de los tres | Cuándo: antes de la fecha de la reunión. Precondición: la reunión ya fue agendada | Precondición que es en realidad el final ("la reunión queda cancelada"). La precondición es **para iniciar**, no para terminar |
| **Recursos** | Elementos físicos o información que tienen que estar disponibles | agenda, cronograma, espacio físico, material físico, listado, medio de comunicación | Olvidar un recurso que los episodios usan (acá, el medio de comunicación está porque el episodio 4 avisa por algún medio) |
| **Actores** | Personas, dispositivos o áreas con un rol en la situación | convocante, secretaria, convocados | Listar a alguien que se nombra pero no hace nada, u olvidar a alguien que sí actúa |
| **Episodios** | Las acciones, en orden, que detallan el comportamiento. Un episodio puede ser a su vez otro escenario | Los seis pasos | Escribir estados en vez de acciones, o pasos sin sujeto. Es el tema del módulo 2 |
| **Excepciones** | Lo que impide lograr el objetivo, con su tratamiento. Suele ser la falta o falla de un recurso | Este ejemplo no tiene. 🧵 ¿Falta algo? Se ve en el módulo 5 | Confundir una excepción con un camino alternativo normal (que no hay cupo no es una excepción, es una alternativa prevista) |
| **Restricción** | Un atributo de un episodio: un requisito de calidad o alcance pegado a ese paso (un RNF) | Este ejemplo no tiene | Ponerla como episodio en vez de como atributo |

Y una parte más, **transitoria**: **Dudas**. Texto libre donde se anotan las cosas que no quedaron claras mientras se escribe el escenario ("¿la secretaria siempre avisa, o a veces el convocante?"). Se usa durante la construcción y **tiene que quedar vacía al validar** con el cliente: cada duda se resolvió o pasó a otro lado.

**Dos cosas de notación que ya ves en el ejemplo** y que se explican después:
- Los episodios 4 y 6 tienen una forma especial: uno empieza con "Si…", el otro está entre corchetes. 🧵 Son tipos de episodio; módulo 2.
- "DA EL AVISO DE CANCELACIÓN" y "ANULA LA RESERVA DE MATERIAL FÍSICO" están en **MAYÚSCULA**. Es la única regla de notación que la cátedra llama fundamental: un episodio en mayúscula es **otro escenario completo**, con sus propias partes, que se "llama" desde este. Como una inclusión en casos de uso (o una extensión, si está bajo condición). Se llama **subescenario**. Cuándo conviene usarlo y qué tiene que cumplir se ve en el módulo 3; por ahora, alcanza con reconocerlo.

Un detalle sobre el contexto: en el modelo, la precondición es parte del contexto, junto con el lugar y el tiempo. En la plantilla que usa la cátedra en los ejercicios, aparecen como dos renglones, "Contexto" y "Precondición", o incluso como un campo "Restricciones/precondición". Es lo mismo; escribilo como venga la plantilla.

> 🎓 **Para el parcial, si te preguntan: ¿cuáles son los componentes de un escenario?**
> Título, objetivo, contexto (ubicación geográfica, ubicación temporal y precondición; al menos una), recursos, actores, episodios, excepciones y el atributo restricción. Durante la construcción se agrega el componente transitorio Dudas, que debe quedar vacío al validar.

## 4. 🔴 Lo que ya conocés de casos de uso

Mucho de esto lo viste en casos de uso con otro nombre. La correspondencia, para que no empieces de cero:

| Caso de uso | Escenario | Qué cambia |
|---|---|---|
| Nombre del caso de uso | Título | Igual idea: verbo + objeto |
| Actor principal (y a veces uno secundario) | Actores | En el escenario **puede haber varios**, y participan de ida y vuelta: convocante, secretaria, convocados |
| Precondición | Precondición (dentro del contexto) | Igual: estado para poder empezar |
| Flujo normal + flujos alternativos | Episodios, con condicionales y opcionales | Parecido: pasos en orden, con bifurcaciones |
| Postcondición | Objetivo | El escenario no tiene postcondición: el último episodio tiene que haber cumplido el objetivo |
| Inclusión | Subescenario (MAYÚSCULA) | Igual idea: una parte reutilizable, descripta aparte |
| *(no existe)* | Recursos | Nuevo: qué cosas hacen falta |
| *(no existe)* | Contexto geográfico y temporal | Nuevo: dónde y cuándo |
| *(no existe)* | Excepciones, Restricción | Nuevo: qué puede impedirlo; qué calidad se exige |

Lo que **no** cambia: la regla de que cada uno es independiente. Así como dos casos de uso no se encadenan, dos escenarios tampoco: cada uno arranca y termina solo. Y así como no se modelan "procesos" con casos de uso, tampoco con escenarios: un escenario no es un flujo que alimenta a otro a través de los datos.

Lo que se parece tanto que confunde: un caso de uso con su flujo completo y un escenario describen situaciones muy similares. ¿Son lo mismo? No, y la respuesta larga es el módulo 4. Por ahora quedate con esto: el caso de uso modela **una función** del sistema; el escenario describe **una situación** del negocio.

## 5. 🟡 Dónde se usan

Los escenarios sirven en dos momentos:
- **Escenario actual:** describe lo que pasa hoy en el negocio. Marcela y la profesora con la carpeta.
- **Escenario futuro:** describe lo que va a pasar cuando entre el software. Marcela con una app.

Tienen la misma estructura y distinto contenido. Es el tema del módulo 4; acá solo para que sepas que los ejemplos de los módulos 1 a 3 son escenarios **actuales**.

## 6. Hilos abiertos

- (a) Los episodios 4 y 6 de Anular la reunión: "Si…" y corchetes. ¿Qué significan y cuándo se usa cada uno? → módulo 2.
- (b) Anular la reunión no tiene excepciones. ¿Está incompleto o es válido? → módulo 5.

---

## Checkpoint del módulo 1

Respondé sin mirar el texto. Sin respuestas acá: van al complemento.

1. Explicá con la historia de Marcela qué quiere decir que una situación tiene "tiempo continuo" y qué pasaría si la profesora le dijera "pasá el jueves y vemos".
2. ¿Por qué el escenario no es la especificación de requisitos? ¿Qué relación tiene con ella?
3. En Anular la reunión, ¿por qué el objetivo no es "anular la reunión"? Escribí un objetivo malo y uno bueno para el escenario "Inscribirse a una clase".
4. Un compañero puso como precondición de "Inscribirse a una clase": "El socio queda anotado en la clase". ¿Qué está mal? Proponé una precondición correcta.
5. Mirá los seis episodios de Anular la reunión y la lista de recursos. ¿Por qué está "medio de comunicación"? ¿Qué episodio lo usa?
6. Hacé la tabla de correspondencia entre caso de uso y escenario de memoria: tres cosas que son iguales con otro nombre y tres que el escenario tiene y el caso de uso no.

## Qué viene en el módulo 2

Cómo se escribe cada episodio: la oración, los cuatro tipos (simple, condicional, optativo, no secuencial), el bucle, las excepciones y la restricción. Con el escenario de Vida Sana "Inscribir a clase" leído paso a paso, y el ejercicio de tu equipo resuelto bien.

---

**FIN DEL MÓDULO 1 — Clase desde cero — Escenarios**
