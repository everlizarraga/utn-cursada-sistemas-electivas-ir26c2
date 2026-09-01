# 📘 APUNTE MAESTRO — Clase 03 · Técnicas de Elicitación — Parte 4

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Unidad:** `clase03` · Jueves 27/08/2026 · Virtual
**Parte 4:** Técnica 5 — Entrevistas.

---

## Sobre esta parte

**Qué cubre:** qué es una entrevista, sus roles y sus objetivos · ventajas y desventajas · los dos tipos (no estructurada y estructurada) y las preguntas abiertas y cerradas en detalle · el procedimiento completo: seleccionar a quién entrevistar, prepararse (la guía de entrevista y las preguntas que hay que evitar), conducirla en tres fases, y hacer el seguimiento con la minuta · escuchar · lenguaje corporal y distancia.

**Qué viene después:** Parte 5 — prototipos de descubrimiento, JRP y el plan de relevamiento.

**Marcas:** 🔴 central, evaluable · 🟡 secundario · 🟢 mencionado al pasar · 🕳️ madriguera.

## De dónde venís

De la Parte 1: el caso, el mapa (la entrevista es la 5: la información sale de **preguntar, cara a cara**), la diferencia entrevista/cuestionario y el eje abierta/cerrada. De la Parte 1 §6.1 y la Parte 3 §5.1: la documentación va **antes** de la entrevista, y el cuestionario **después**. De la Parte 2 §3: verificar con el usuario y no saltar a conclusiones.

---

## 1. 🔴 Qué es una entrevista, quiénes participan y para qué sirve

Volvé al caso. Ya leíste las planillas y los cuadernos. Ya investigaste cómo funcionan las playas con máquina de tickets. Ahora tenés una reunión de media hora con el administrador de la empresa: la persona que sabe cuántas playas hay de verdad, cómo se cobra, cuánto presupuesto hay y hasta dónde quiere llegar. No hay documento que reemplace esa media hora. Y no la podés desperdiciar.

**Entrevista** es la técnica en la que el analista **recolecta información de las personas a través de la interacción cara a cara**.

Es la técnica **más importante y más usada** del relevamiento. En la cátedra hay una imagen para esto: a la entrevista vas **con el termo y el mate** — y si no te gusta el mate, lo tomás igual. La idea es generar un espacio de confianza con el otro, donde se pueda dar la dinámica de que te cuente efectivamente cuál es su necesidad y vos la escuches.

### Los dos roles

- El **entrevistador** es el analista de sistemas: organiza y conduce la entrevista.
- El **entrevistado** es el usuario o el dueño del sistema: responde a una serie de preguntas.

Puede haber uno o varios de cada lado: uno a uno, o varios a varios. Muchos analistas son malos entrevistadores; esta parte es para que vos no lo seas.

### Para qué sirve

Con una entrevista podés lograr cualquiera de estos objetivos, o todos:

| Objetivo | En el caso |
|---|---|
| **Descubrir hechos** | Cuántas playas hay hoy |
| **Verificar hechos** | ¿El cobro es manual en las 20, o hay alguna con máquina? |
| **Aclarar hechos** | Qué quiere decir "abono mensual": ¿lugar fijo, o derecho a entrar? |
| **Generar entusiasmo** | Que el administrador sienta el proyecto como propio |
| **Involucrar al usuario final** | Que el encargado quiera que el sistema salga bien |
| **Identificar requisitos** | Qué necesita ver el administrador que hoy no ve |
| **Pedir ideas y opiniones** | Qué haría el encargado distinto si pudiera |

### Por qué requiere habilidades distintas

El elemento más importante de un sistema de información son las **personas**, y ninguna otra técnica pone tanto énfasis en ellas como la entrevista. Pero las personas tienen valores, prioridades, opiniones, motivaciones y personalidades distintas. Para entrevistar bien necesitás **habilidades de relación humana**: tratar eficazmente con gente distinta. Y como toda técnica, no es la mejor para todas las situaciones: sus ventajas se pesan contra las de las demás.

> **Para el parcial, si te preguntan:** *¿Qué es la entrevista y qué roles participan?*
> Es la técnica de relevamiento en la que el analista recolecta información de las personas mediante interacción cara a cara. Participan el entrevistador (el analista, que organiza y conduce) y el entrevistado (usuario o dueño del sistema, que responde).

---

## 2. 🔴 Ventajas y desventajas

### Ventajas

- **Podés motivar al entrevistado a responder libre y abiertamente.** Estableciendo un buen vínculo (*rapport*, glosa: sintonía, confianza mutua), la persona siente que está contribuyendo activamente al proyecto — y entonces cuenta.
- **Podés indagar** (*probe*): repreguntar, pedir más, ir más hondo cuando una respuesta abre algo.
- **Podés adaptar o reformular** las preguntas para cada persona. Lo que le preguntás al administrador no es lo que le preguntás al encargado, aunque el tema sea el mismo.
- **Podés observar la comunicación no verbal.** Un buen analista saca información de los movimientos del cuerpo y las expresiones de la cara, no solo de las palabras (§6).

### Desventajas

- **Consume mucho tiempo, y por lo tanto es costosa.** Media hora de entrevista son horas de preparación, traslado, minuta. Y el tiempo del entrevistado también cuesta.
- **Su éxito depende fuertemente de las habilidades humanas del analista.** Un mal entrevistador con buenas preguntas obtiene poco.
- **Puede ser impracticable por la ubicación** de los entrevistados. Veinte encargados en veinte playas repartidas por la ciudad.

Mirá las dos listas contra las del cuestionario (Parte 3 §2): son espejo. Lo que la entrevista tiene —repreguntar, adaptar, ver la cara— es lo que el cuestionario pierde; lo que el cuestionario tiene —barato, masivo, anónimo— es lo que la entrevista no puede.

> **Para el parcial, si te preguntan:** *Mencioná ventajas y desventajas de la entrevista.*
> Ventajas: permite motivar al entrevistado a responder abiertamente estableciendo un vínculo, indagar y repreguntar, adaptar las preguntas a cada persona, y observar la comunicación no verbal. Desventajas: consume mucho tiempo y por eso es costosa, depende mucho de las habilidades de relación humana del analista, y puede ser impracticable por la ubicación de los entrevistados.

---

## 3. 🔴 Tipos de entrevista, y preguntas abiertas y cerradas

### 3.1 No estructurada y estructurada

Una **entrevista no estructurada** se conduce con solo un objetivo o tema general en mente, y con pocas o ninguna pregunta específica. El entrevistador **cuenta con que el entrevistado** provea el marco y dirija la conversación.

Este tipo de entrevista **se va de tema con frecuencia**, y el analista tiene que estar preparado para redirigirla al objetivo. Por eso las entrevistas no estructuradas **no suelen funcionar bien** para análisis y diseño de sistemas.

En una **entrevista estructurada** el entrevistador tiene un **conjunto específico de preguntas** para hacerle al entrevistado. Según las respuestas, agrega preguntas adicionales para aclarar o ampliar — algunas planificadas de antemano, otras espontáneas.

En el caso: "vení, contame cómo funciona el negocio" es no estructurada; la media hora con el administrador tiene que ser estructurada, y la §4.2 te da la herramienta.

### 3.2 Abiertas y cerradas, en detalle

Ya sabés la diferencia (Parte 1 §5.2). Acá va el detalle para la entrevista.

Las **preguntas abiertas** permiten al entrevistado responder de la manera que le parezca apropiada. *"¿Por qué está disconforme con el reporte de cuentas incobrables?"* La persona elige por dónde arranca, qué prioriza, cuánto se extiende.

Las **preguntas cerradas** restringen las respuestas a opciones específicas o a respuestas cortas y directas. *"¿Recibe el reporte de cuentas incobrables a tiempo?" "¿El reporte contiene información precisa?"*

En la realidad, **la mayoría de las preguntas caen entre los dos extremos**. "¿Cómo se cobra hoy el abono mensual?" no es sí/no, pero tampoco es un ensayo: es una pregunta con respuesta acotada y varias repreguntas posibles.

> **Para el parcial, si te preguntan:** *Diferencia entre entrevista estructurada y no estructurada. ¿Cuál se usa en análisis de sistemas?*
> En la no estructurada el entrevistador tiene solo un objetivo general y pocas o ninguna pregunta específica, y depende del entrevistado para dirigir la conversación; se va de tema y no suele funcionar en análisis de sistemas. En la estructurada el entrevistador tiene un conjunto específico de preguntas, y agrega otras según las respuestas para aclarar o ampliar.

---

## 4. 🔴 Cómo se conduce una entrevista

Tu éxito como analista depende, al menos en parte, de tu capacidad para entrevistar. Una entrevista exitosa tiene **cuatro pasos**:

```text
 1. SELECCIONAR      2. PREPARARSE       3. CONDUCIR           4. SEGUIMIENTO
    a quién             (la guía de         (tres fases:          (la minuta)
    entrevistar         entrevista)         apertura, cuerpo,
                                            cierre)
```

Se asume que ya identificaste la **necesidad** de la entrevista y determinaste **exactamente qué hechos y opiniones necesitás** — el mismo paso 1 del cuestionario (Parte 3 §4). Si no sabés qué hueco de información querés llenar, no estás listo para agendar nada.

### 4.1 Seleccionar a quién entrevistar

Entrevistá a los **usuarios finales** del sistema. El **organigrama** que pediste en la Técnica 1 te ayuda a identificar a esas personas y sus responsabilidades.

Antes de la entrevista, **aprendé todo lo que puedas sobre cada persona**: sus fortalezas, sus miedos, sus sesgos, sus motivaciones. La entrevista se adapta a las características de quien tenés enfrente. Un gerente de operaciones que llega "seteado" en que está saturado, que el sistema no da abasto y que su equipo son tres personas, ya viene con su núcleo armado — tus preguntas tienen que meterte en su mundo, no chocar contra él.

Reglas de logística:

- **Siempre pedí una cita.** Nunca caigas de sorpresa.
- **Limitá la cita a entre media hora y una hora.** Cuanto **más alto el nivel gerencial** del entrevistado, **menos tiempo** deberías agendar.
- Si el entrevistado es personal administrativo, de servicio u operario, **pedí permiso a su supervisor** antes de agendar.
- Asegurate de que el **lugar** que querés esté disponible a esa hora.
- **Nunca entrevistes en presencia de tus compañeros de oficina ni de los pares del entrevistado.** Con el jefe al lado, nadie te dice que el procedimiento no se cumple; con los compañeros al lado, nadie dice que el compañero se saltea pasos.

Esa última regla decide algo del plan de relevamiento: si en el centro de extracción hay cinco recepcionistas y son ellas por las que pasan los dos problemas que te contrataron para resolver, la decisión correcta es **una entrevista a cada una**, no una reunión con las cinco. Es más tiempo — y es el único modo de que cada una te cuente lo suyo.

**El orden también se decide y se justifica.** Podés ir de lo macro a lo micro —líder del área, después supervisor, después las recepcionistas— para llegar a lo chico con el contexto puesto. O podés arrancar por las recepcionistas, que son las que conviven con el problema todos los días y te dan **el crudo**, y subir después: el líder quizás ni lo considera un problema, mientras que la que atiende te va a decir "sí, a tal hora es un caos". Las dos rutas son válidas; lo que se corrige es que **hayas tomado la decisión** y puedas decir por qué.

### 4.2 Prepararse: la guía de entrevista

**La preparación es la clave de una entrevista exitosa.** Un entrevistado detecta fácilmente a un entrevistador no preparado, y puede resentirlo — porque le está haciendo perder tiempo valioso. Cuando confirmás la cita, **avisale el tema** de la entrevista.

Para asegurarte de cubrir todos los aspectos pertinentes, preparás una **guía de entrevista**:

**Guía de entrevista** es la lista de preguntas específicas que el entrevistador le va a hacer al entrevistado.

Puede incluir también **repreguntas** (*follow-up*) que solo se hacen si la respuesta lo amerita. La agenda se arma con **un tiempo asignado a cada pregunta**, y se reserva tiempo para las repreguntas y para redirigir. Las preguntas se eligen y redactan con cuidado; la mayoría arrancan con **quién, qué, cuándo, dónde, por qué y cuánto**.

Así se ve una guía para la entrevista al administrador del caso:

```text
 ┌──────────────────────────────────────────────────────────────────────────────────┐
 │ GUÍA DE ENTREVISTA                                                               │
 │ Entrevistado:  Administrador general — Estacionamientos                          │
 │ Fecha:         martes 08/09/2026        Hora: 15:00      Lugar: oficina central  │
 │ Tema:          Operación actual de cobro y control de ingresos, egresos y abonos │
 ├─────────┬──────────────────────────────────────────────────────────┬─────────────┤
 │ Tiempo  │ Pregunta u objetivo del entrevistador                    │ Respuesta   │
 ├─────────┼──────────────────────────────────────────────────────────┼─────────────┤
 │ 1-2 min │ OBJETIVO — Abrir la entrevista:                          │             │
 │         │ · Presentarnos.                                          │             │
 │         │ · Agradecer su tiempo.                                   │             │
 │         │ · Enunciar el propósito: entender cómo funciona hoy el   │             │
 │         │   control de ingresos, egresos y abonos.                 │             │
 ├─────────┼──────────────────────────────────────────────────────────┼─────────────┤
 │ 5 min   │ P1  ¿Cuántas playas operan hoy y cuántas plazas tiene    │             │
 │         │     cada una?                                            │             │
 │         │ Repregunta: ¿las 20 nuevas se suman a esas o las         │             │
 │         │     reemplazan?                                          │             │
 ├─────────┼──────────────────────────────────────────────────────────┼─────────────┤
 │ 5 min   │ P2  ¿Cómo se cobra hoy en cada modalidad —hora, día,     │             │
 │         │     mensual— y quién registra cada cobro?                │             │
 │         │ Repregunta:                                              │             │
 ├─────────┼──────────────────────────────────────────────────────────┼─────────────┤
 │ 3 min   │ P3  ¿Qué información sobre ingresos y egresos necesita   │             │
 │         │     ver usted que hoy no puede ver?                      │             │
 │         │ Repregunta:                                              │             │
 ├─────────┼──────────────────────────────────────────────────────────┼─────────────┤
 │ 2 min   │ P4  ¿Qué medios de pago aceptan hoy y cuáles quieren     │             │
 │         │     agregar?                                             │             │
 ├─────────┼──────────────────────────────────────────────────────────┼─────────────┤
 │ 1 min   │ P5  ¿Quién es el encargado en cada playa y quién los     │             │
 │         │     supervisa?                                           │             │
 ├─────────┼──────────────────────────────────────────────────────────┼─────────────┤
 │ 2 min   │ P6  ¿Podemos hablar con los encargados y observar una    │             │
 │         │     playa en horario pico?                               │             │
 │         │ Repregunta: si es así, ¿cuándo sería un buen momento     │             │
 │         │     para cada uno?                                       │             │
 ├─────────┼──────────────────────────────────────────────────────────┼─────────────┤
 │ 1 min   │ OBJETIVO — Cerrar la entrevista:                         │             │
 │         │ · Agradecer su cooperación.                              │             │
 │         │ · Asegurarle que va a recibir una copia de lo tratado.   │             │
 ├─────────┴──────────────────────────────────────────────────────────┴─────────────┤
 │ 21 min   Tiempo asignado a preguntas base y objetivos                            │
 │  9 min   Tiempo asignado a repreguntas y redirección                             │
 │ 30 min   Tiempo total de la entrevista (15:00 a 15:30)                           │
 ├──────────────────────────────────────────────────────────────────────────────────┤
 │ Comentarios y notas generales:                                                   │
 │                                                                                  │
 └──────────────────────────────────────────────────────────────────────────────────┘
```

Cosas para leer en esa guía:

- **La apertura y el cierre son objetivos con tiempo asignado**, no improvisación.
- **Cada pregunta tiene su tiempo**, y las de más peso tienen más. P1 y P2 son el núcleo; P5 es un dato de un minuto.
- **Los 30 minutos no se llenan con preguntas.** 21 son de preguntas base; 9 quedan libres para repreguntar y para traer de vuelta la conversación cuando se vaya. Si llenás los 30 con preguntas, la primera repregunta te rompe la agenda.
- **P6 pide permiso para el paso siguiente** del plan: hablar con los encargados y observar. La entrevista al que decide es la puerta a las demás técnicas.
- **La columna de respuesta está vacía a propósito.** Se completa durante.

Esto es lo que se corrige cuando decís "vamos a hacer una entrevista larga al gerente de operaciones": la pregunta es *¿cuál es el núcleo de esa entrevista? ¿qué información? ¿cuáles son los ítems que la completan?* Una entrevista sin guía es una charla.

#### Preguntas que hay que evitar

Tres tipos de pregunta arruinan la respuesta antes de que llegue:

- **Cargadas** (*loaded*): transmiten la opinión personal del entrevistador sobre el tema. *"¿Necesitamos de verdad que el encargado anote la patente y además la hora?"* — ya le dijiste que te parece de más.
- **Inductoras** (*leading*): llevan al entrevistado a responder de una manera, sin importar su opinión real. *"Ustedes no van a seguir cobrando en efectivo, ¿no?"* — la respuesta es "no, claro que no", diga lo que diga la realidad.
- **Sesgadas** (*biased*): sesgan la respuesta con la tuya. *"¿Cuántos tipos de abono necesitan? Yo creo que con tres alcanza."* — ¿para qué preguntás?

Además, evitá especialmente las preguntas **amenazantes o críticas**. El propósito de la entrevista es **investigar, no evaluar ni criticar**. "¿Por qué nunca controlan los egresos?" cierra la conversación.

#### Guías para redactar preguntas

- Lenguaje **claro y conciso**.
- **No incluyas tu opinión** como parte de la pregunta.
- Evitá preguntas **largas o complejas**.
- Evitá preguntas **amenazantes**.
- No uses **"usted"** cuando te referís a un **grupo** de personas. "¿Usted controla los egresos?" acusa; "¿cómo se controlan los egresos en las playas?" pregunta.

### 4.3 Conducir la entrevista: tres fases

La entrevista en sí tiene **apertura, cuerpo y cierre**.

**La apertura** busca influir o motivar al entrevistado a participar y comunicarse, estableciendo el ambiente ideal. Para establecer un ambiente de **confianza y respeto mutuos**, identificás el **propósito** y la **duración** de la entrevista, y explicás **cómo se van a usar los datos** que juntes. Tres formas efectivas de empezar:

- **Resumir el problema aparente** y explicar cómo se descubrió.
- **Ofrecer un incentivo o recompensa** por participar.
- **Pedirle consejo o ayuda** al entrevistado. "Usted es el que mejor conoce esto; necesito que me explique cómo funciona." Pocas cosas abren más a una persona que sentirse la autoridad en el tema.

**El cuerpo** es la fase que más tiempo consume. Obtenés las respuestas a tu lista de preguntas. **Escuchá con atención y observá.** Tomá notas de las respuestas verbales **y** de las no verbales. Es muy importante **mantener la entrevista encaminada**. Anticipá la necesidad de **adaptar** la entrevista al entrevistado: muchas veces una pregunta se puede saltear porque ya la respondió dentro de otra, o se puede eliminar porque, con lo que ya aprendiste, se volvió irrelevante. Y **indagá** por más hechos cuando haga falta.

**El cierre** es donde expresás tu agradecimiento y respondés cualquier pregunta que el entrevistado te haya hecho. Es muy importante para **mantener el vínculo y la confianza**: la próxima entrevista con esa persona empieza en el cierre de esta.

Las habilidades humanas no se pueden sobreenfatizar. Reglas para toda la entrevista:

| **Hacer** | **Evitar** |
|---|---|
| Ser cortés | Continuar la entrevista innecesariamente |
| Escuchar con atención | Asumir que una respuesta terminó o que no lleva a nada |
| Mantener el control | Revelar pistas verbales y no verbales (de lo que pensás) |
| Indagar | Usar jerga |
| Observar gestos y comunicación no verbal | Revelar tus sesgos personales |
| Ser paciente | Hablar en lugar de escuchar |
| Mantener al entrevistado cómodo | Asumir cualquier cosa sobre el tema o sobre el entrevistado |
| Mantener el autocontrol | Grabar — es señal de malas habilidades de escucha |

> ⚠️ **Sobre grabar.** En la materia se enseña que grabar la entrevista es señal de malas habilidades de escucha: el que graba deja de escuchar porque "ya está registrado". En la práctica actual muchas entrevistas se graban con consentimiento del entrevistado, y después se transcriben. **Para el parcial: responder con lo enseñado** — no grabar, tomar notas.

### 4.4 Seguimiento: la minuta

Para mantener el buen vínculo y la confianza, después de la entrevista le mandás al entrevistado un **memo que resume la entrevista**. En la cátedra este documento se llama **minuta**.

La minuta cumple tres funciones:

- **Le recuerda al entrevistado sus contribuciones** al proyecto — refuerza que su tiempo valió.
- **Le da la oportunidad de aclarar cualquier malinterpretación** que hayas hecho durante la entrevista. Es tu primera verificación con el usuario (Parte 2 §3): lo que entendiste mal, lo corrige él antes de que se convierta en requisito.
- **Le da la oportunidad de agregar información** que no surgió durante la entrevista y que se le ocurrió después.

Es lo que prometiste en el cierre de la guía: "va a recibir una copia de lo tratado".

**El costo de una entrevista** no es solo la media hora: es la preparación, la agenda, el traslado, la minuta, y el tiempo del entrevistado. Por eso importa tanto llegar con la documentación leída (Parte 1 §6.1): cada cosa que preguntás y estaba en un documento es tiempo desperdiciado, y si te faltó algo, es **otra reunión, con otra agenda y otra minuta**. Una entrevista bien preparada evita la doble entrevista.

> **Para el parcial, si te preguntan:** *¿Cuáles son los pasos para conducir una entrevista?*
> Seleccionar a los entrevistados (usuarios finales, con ayuda del organigrama, conociendo a cada uno), prepararse (avisar el tema y armar la guía de entrevista con preguntas, repreguntas y tiempos), conducirla (apertura, cuerpo y cierre) y hacer el seguimiento (la minuta que resume la entrevista y permite aclarar y agregar).

> **Para el parcial, si te preguntan:** *¿Qué es la guía de entrevista?*
> Es la lista de preguntas específicas que el entrevistador le va a hacer al entrevistado, con el tiempo asignado a cada una y repreguntas que solo se hacen si la respuesta lo amerita. Incluye los objetivos de apertura y cierre y reserva tiempo para repreguntas y redirección.

> **Para el parcial, si te preguntan:** *¿Qué tipos de preguntas hay que evitar en una entrevista?*
> Cargadas (transmiten la opinión del entrevistador), inductoras (llevan al entrevistado a una respuesta determinada), sesgadas (sesgan la respuesta con la del entrevistador), y amenazantes o críticas (la entrevista investiga, no evalúa).

> **Para el parcial, si te preguntan:** *¿Para qué sirve la minuta?*
> Resume la entrevista y se envía al entrevistado: le recuerda sus contribuciones, le permite aclarar malinterpretaciones del analista y agregar información que no surgió en la entrevista.

---

## 5. 🟡 Escuchar

Cuando se habla de habilidades de comunicación, se piensa en hablar y escribir. Escuchar casi nunca se menciona — y puede ser la habilidad más importante de toda la entrevista. Hay que distinguir **oír** de **escuchar**: oír es reconocer que alguien está hablando; escuchar es **entender lo que el que habla quiere comunicar**.

Estamos condicionados a *no* escuchar: ignoramos a los hermanos que discuten mientras oímos música, estudiamos bloqueando el ruido. Aprendimos a no escuchar; también podemos aprender a escuchar bien. Cuando trabajás con usuarios para resolver sus problemas, lograr que se comuniquen puede ser difícil; estas guías abren la comunicación:

- **Andá con actitud positiva.** Encarar el proyecto o la persona con actitud negativa es pelear una batalla perdida. Tenés un trabajo que hacer: sacale lo mejor.
- **Poné cómoda a la otra persona.** Una actitud alegre relaja. Arrancá hablando de sus intereses o hobbies; mostrar interés en su vida sirve para romper el hielo. (El termo y el mate de §1.)
- **Hacele saber que estás escuchando.** Contacto visual, un asentimiento con la cabeza, un "ajá". Buena postura; incluso sentarte en el borde de la silla e inclinarte hacia adelante. Eso le dice al otro que lo que dice te interesa de verdad.
- **Hacé preguntas.** Para asegurarte de que entendiste, o para aclarar un punto. Muestra que escuchás y le da al otro la oportunidad de ampliar.
- **No asumas nada.** Una de las peores cosas que podés hacer es apurarte e impacientarte con el que habla: asumir que sabés qué va a decir, cortarlo y terminarle la frase — perdiéndote lo que iba a decir e irritándolo. O interrumpirlo porque "eso ya lo sé" o "no aplica", y perderte una pieza valiosa. Hay una anécdota clásica: un conductor de televisión le pregunta a un chico que quiere ser piloto qué haría si se le apagaran todos los motores sobre el océano. El chico responde: "primero le diría a todos que se abrochen el cinturón, y después me pondría el paracaídas y saltaría". El público se ríe; el conductor ve que al chico se le llenan los ojos de lágrimas y le pregunta por qué haría eso. "Voy a buscar nafta… y vuelvo." **No asumas nada.**
- **Tomá notas.** Sirve para dos cosas: le muestra al otro que lo que dice es lo suficientemente importante como para anotarlo, y te ayuda a recordar los puntos principales después.

---

## 6. 🟡 Lenguaje corporal y proxémica

¿Qué es el lenguaje corporal y por qué le importa a un analista de sistemas?

**Lenguaje corporal** es toda la información no verbal que comunicamos, en general sin darnos cuenta.

Hay investigación que dice que, de los sentimientos totales de una persona, solo el **7%** se comunica verbalmente (con palabras), el **38%** por el tono de voz, y el **55%** por las expresiones faciales y corporales. Si solo escuchás las palabras, te perdés la mayor parte de lo que la persona tiene para decir.

> ⚠️ **Sobre el 7-38-55.** Es una cifra muy citada y muy discutida: viene de un estudio acotado a la comunicación de actitudes y emociones, y se generaliza más de lo que el estudio permite. **Para el parcial: la cifra es esa.** Lo que no está en discusión es la idea de fondo — que lo no verbal comunica mucho y hay que mirarlo.

Tres aspectos del lenguaje corporal:

**Expresión facial.** A veces podés entender cómo se siente la gente mirándole la cara: muchas emociones comunes tienen expresiones reconocibles. Pero la cara es **una de las partes más controladas** del cuerpo: la gente que sabe que su expresión revela lo que piensa suele ser muy buena controlándola.

**Contacto visual.** Es **la parte menos controlada de la cara**. ¿Hablaste alguna vez con alguien que no te mira? ¿Cómo te hizo sentir? Una falta continua de contacto visual puede indicar **incertidumbre**. Una mirada normal dura de tres a cinco segundos, y el tiempo de contacto directo debería aumentar con la distancia. Como analista, cuidado con usar contacto visual excesivo con usuarios que se sienten amenazados — los intimidás más. El contacto visual directo genera sentimientos fuertes, positivos o negativos.

**Postura.** Es **el aspecto menos controlado del cuerpo**, y por eso guarda mucha información. Los miembros de un grupo que están de acuerdo tienden a mostrar la **misma postura**; un buen analista mira a la audiencia buscando cambios de postura que indiquen ansiedad, desacuerdo o aburrimiento. El analista normalmente mantiene una posición corporal **"abierta"** que señala accesibilidad, aceptación y receptividad. En circunstancias especiales puede elegir un ángulo de confrontación —de frente o a 90 grados— para establecer control y dominio.

Además del lenguaje corporal, las personas comunican por **proxémica**:

**Proxémica** es la relación entre las personas y el espacio que las rodea. Es un factor de la comunicación que el analista que lo conoce puede **controlar**.

La gente es muy territorial con su espacio. (Observá dónde se sienta cada uno en una cursada sin asientos asignados.) Hay **cuatro zonas espaciales**:

| Zona | Distancia | Uso |
|---|---|---|
| **Íntima** | menos de 45 cm (1,5 pies) | — |
| **Personal** | 45 cm a 1,2 m (1,5 a 4 pies) | **Acá se conduce la mayoría de las entrevistas** |
| **Social** | 1,2 m a 3,6 m (4 a 12 pies) | Retroceder acá si el usuario muestra señales de incomodidad |
| **Pública** | más de 3,6 m (12 pies) | — |

Ciertos tipos de comunicación ocurren solo en algunas zonas. Un analista conduce la mayoría de las entrevistas en la zona personal, pero puede necesitar retroceder a la zona social si el usuario muestra, con lenguaje corporal, señales de estar incómodo. A veces aumentar el contacto visual compensa una distancia larga que no se puede cambiar. Mucha gente usa el borde de la zona social como distancia "de respeto".

Un buen analista usa **toda** la información disponible, no solo la escrita o verbal de los demás.

> **Para el parcial, si te preguntan:** *¿Qué es la proxémica y cuáles son las cuatro zonas?*
> La proxémica es la relación entre las personas y el espacio que las rodea. Las zonas son íntima (menos de 1,5 pies / 45 cm), personal (1,5 a 4 pies / 45 cm a 1,2 m — donde se conducen la mayoría de las entrevistas), social (4 a 12 pies / 1,2 a 3,6 m) y pública (más de 12 pies / 3,6 m).

---

## 7. ✅ Checkpoint — Parte 4

Sin respuestas. Las respuestas van al complemento.

1. Nombrá los siete objetivos que puede tener una entrevista y dá un ejemplo del caso para tres de ellos.
2. ¿Por qué la entrevista exige habilidades distintas de las otras técnicas?
3. Compará ventajas y desventajas de entrevista y cuestionario. ¿Por qué se dice que son espejo?
4. ¿Por qué la entrevista no estructurada no funciona en análisis de sistemas?
5. "¿Cómo se cobra hoy el abono mensual?" — ¿es abierta, cerrada, o algo entre medio? Justificá.
6. ¿Por qué no se entrevista a alguien en presencia de sus pares? ¿Qué decisión del plan de relevamiento se deriva de esa regla?
7. Explicá las dos rutas posibles —macro a micro y micro a macro— y qué se corrige en la elección.
8. Armá una guía de entrevista de 20 minutos para un encargado de playa: tres preguntas con tiempo, una repregunta, apertura y cierre, y el reparto de minutos.
9. Reescribí cada una como pregunta correcta: (a) "¿No le parece que anotar a mano es un desastre?" (b) "Ustedes van a querer una app, ¿no?" (c) "¿Cuántas playas tienen? Yo diría que unas veinte."
10. ¿Cuáles son las tres formas de abrir una entrevista y por qué la tercera funciona tan bien?
11. ¿Qué tres funciones cumple la minuta, y con qué lección de la Parte 2 se conecta?
12. ¿Por qué el costo de una entrevista es mucho más que la media hora? ¿Qué decisión de la Técnica 1 lo reduce?
13. Un entrevistado deja de mirarte y cruza los brazos cuando preguntás por los egresos. ¿Qué te dicen el contacto visual y la postura, y qué hacés con la distancia?

## Qué viene en la Parte 5

Las dos técnicas que amplían el repertorio —prototipos de descubrimiento y JRP— y después, con las siete en la mano, la resolución del caso: cómo se arma un plan de relevamiento, qué tiene que tener, con qué criterios se corrige, y el plan de estacionamientos resuelto de punta a punta.

---

**FIN DE LA PARTE 4 — Apunte Maestro clase03 · Técnicas de Elicitación**
