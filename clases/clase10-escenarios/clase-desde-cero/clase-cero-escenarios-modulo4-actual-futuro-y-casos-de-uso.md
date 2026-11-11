# Clase desde cero — Escenarios — Módulo 4: Actual vs. futuro, y por qué no es un caso de uso

**Serie:** Clase desde cero — Escenarios (módulo 4 de 5) · **Materia:** Ingeniería de Requisitos · **Unidad:** clase10

---

## Sobre este documento

**Qué cubre:** la diferencia entre escenario actual y futuro, qué cambia cuando entra el software y qué no, la "ubicuidad", la diferencia entre sistema de información y sistema de software; la comparación entre caso de uso y escenario, con lo que pasa cuando se intenta convertir uno en otro; y la cadena de trazabilidad LEL → escenario → requisito. Es el módulo con más preguntas de parcial.

**Qué NO cubre:** la revisión de completitud (módulo 5).

## De dónde venís

De los módulos 1 a 3: partes, episodios, subescenarios e integradores; Inscribir a clase y Cambiar inscripción. De la clase02: casos de uso, inclusión, extensión, actor. De la serie de LEL, módulo 4: los impactos de los sujetos y verbos originan escenarios.

---

## 1. 🔴 Escenario actual y escenario futuro

Todos los escenarios que viste hasta acá describen **lo que pasa hoy**: Marcela, la profesora, la carpeta de papel. Son **escenarios actuales**. Cuando el proyecto avanza y se decide qué software va a haber, se escriben **escenarios futuros**: lo que **va a pasar** con el software.

| | **Actual** | **Futuro** |
|---|---|---|
| **La pregunta** | ¿Qué pasa hoy en el negocio? | ¿Qué esperamos del negocio con el software? |
| **Qué refleja** | Situaciones que hoy ocurren | La expectativa sobre el proyecto |
| **De dónde sale** | Del LEL (los impactos de sujetos y verbos) | De los escenarios actuales y de los objetivos del proyecto |
| **Actores** | Sujetos del LEL y los sistemas que ya existen | El software planificado es un actor principal |
| **Requisitos** | Puede contener algunos | Contiene los requisitos elicitados y negociados |

**Misma estructura, distinto contenido.** Un escenario futuro tiene exactamente las mismas partes que uno actual. Lo que cambia es lo que dice cada parte. Y "futuro" quiere decir "futuro esperado": describe algo que todavía no existe, que se planea, y que va a cambiar a medida que el proyecto avance.

**Dos ideas que la cátedra repite:**

- **Sistema de información ≠ sistema de software.** Vida Sana hoy no tiene software, pero **tiene un sistema de información**: carpetas, fichas, resaltadores, una forma de decidir quién tiene cupo y quién no. Con eso toman decisiones. El escenario actual describe ese sistema. Lo que el proyecto hace es *digitalizar* una parte, no crear un sistema de la nada.
- **Ubicuidad.** Hoy, inscribirse pasa en el centro, en horario de clases: contexto geográfico y temporal acotados. Con una app, pasa en cualquier lugar y en cualquier momento. Eso tiene nombre, **ubicuidad**, y es el cambio de contexto más típico entre un escenario actual y uno futuro. En el futuro, el campo Contexto puede decir "en cualquier lugar con conexión, en cualquier momento".

## 2. 🔴 Qué cambia y qué no: Inscribir a clase con una app

Imaginate que Vida Sana adopta una app. El socio ve las clases del día, cada una con su cupo, toca una y reserva. Si está llena, se anota en lista de espera desde el teléfono. El escenario actual de Inscribir a clase (módulo 2) se convierte en algo así:

> **Título:** INSCRIBIR A CLASE (futuro)
> **Objetivo:** El socio se asegura un cupo en una clase para asistir a ella.
> **Contexto:** En cualquier lugar, en cualquier momento, con la aplicación disponible. Precondición: el socio tiene un plan activo y está registrado en la aplicación.
> **Recursos:** teléfono del socio, grilla de clases, plan del socio, lista de espera.
> **Actores:** socio, aplicación.
> **Episodios:**
> 1. El socio consulta en la aplicación las clases disponibles de un día.
> 2. El socio selecciona una clase.
> 3. La aplicación muestra el cupo disponible y las clases que le quedan al socio en su plan.
> 4. Si al socio no le quedan clases en el plan, la aplicación le ofrece contratar un plan nuevo.
> &nbsp;&nbsp;4.1. Si el socio acepta, CONTRATAR PLAN DE CLASES.
> &nbsp;&nbsp;4.2. Si el socio no acepta, FIN DEL ESCENARIO.
> 5. Si hay cupo en la clase, el socio reserva su lugar.
> 6. Si no hay cupo en la clase, el socio se anota en la lista de espera de la clase.
> 7. La aplicación registra la reserva o la inscripción en la lista de espera.
> 8. La aplicación confirma al socio el resultado.
> 9. FIN DEL ESCENARIO

Un detalle: la aplicación está en **actores**, porque actúa (muestra, registra, confirma). En el modelo, el software planificado es un actor principal del escenario futuro. Algunos la listan también como recurso, porque además tiene que estar disponible; la cátedra admite las dos cosas. Acá va como actor, que es lo que la distingue de un recurso pasivo como la grilla.

Compará con el actual, parte por parte:

| Parte | Actual | Futuro | ¿Cambió? |
|---|---|---|---|
| Objetivo | Asegurarse un cupo | Asegurarse un cupo | **No.** La necesidad del negocio es la misma |
| Actores | Socio, profesor | Socio, aplicación | **Sí.** El profesor desapareció de este escenario; apareció el software como actor |
| Recursos | Carpeta de clases, fichas, carnet | Teléfono, grilla, plan, lista de espera | **Sí.** Los papeles se fueron; aparecieron recursos nuevos |
| Contexto | En el centro, en horario de clases | Cualquier lugar, cualquier momento | **Sí.** Ubicuidad |
| Episodios | 12, con el profesor consultando carpetas | 9, con el socio operando la app | **Sí, en parte.** Algunos pasos son los mismos (elegir clase, ver cupo, reservar); otros desaparecieron (dar el nombre, el profesor consulta la ficha) |
| Estructura | Las mismas partes | Las mismas partes | **No** |

Una aclaración que importa para el TP: que el profesor no esté en **este** escenario futuro no significa que la inscripción en el mostrador deje de existir. Puede ser que el negocio decida mantener las dos formas. Eso es una decisión del cliente, y daría dos escenarios futuros, no uno.

**En el modelo:** la decisión que hoy toma el socio pero que anota el profesor en una planilla, mañana queda plasmada en una interacción del socio con la aplicación. Cambia el recurso, cambia el contexto, cambia la información que el socio ve. Y como los escenarios futuros son los que contienen los requisitos, de los episodios nuevos salen requisitos: del 3, por ejemplo, "la aplicación debe mostrar el cupo disponible de cada clase y las clases restantes del plan del socio".

> 🎓 **Para el parcial, si te preguntan: ¿qué diferencia hay entre un escenario actual y uno futuro?**
> Tienen la misma estructura y distinto contenido. El actual refleja situaciones que hoy ocurren en el negocio y se deriva del LEL; el futuro refleja la expectativa sobre el proyecto, se deriva de los escenarios actuales y los objetivos, y tiene al software planificado como actor principal. El futuro contiene los requisitos elicitados y negociados; en él suelen cambiar los recursos, el contexto (ubicuidad) y los actores.

## 3. 🔴 Caso de uso ≠ escenario

Es la pregunta a la que la cátedra dedicó una clase entera, con un ejercicio a propósito tramposo: convertir escenarios en casos de uso y ver qué pasa. La conclusión: **se parecen mucho, pero no son la misma herramienta, y no hay una correspondencia uno a uno.**

### 3.1 En qué se parecen

Tienen actores. Tienen un objetivo. Tienen pasos ordenados con alternativas. Tienen precondición. Se puede usar la misma estructura, la misma nomenclatura, los mismos elementos, y escribir el flujo de un caso de uso como si fuera un escenario. De lejos, parecen lo mismo con otro nombre.

### 3.2 En qué no

| | Caso de uso | Escenario |
|---|---|---|
| **Qué modela** | Una **función** que el sistema ofrece a un actor | Una **situación** del negocio, con continuidad en el tiempo de principio a fin |
| **Nivel** | Más abstracto: "inscribir a clase" es una función, sin importar cómo se dé cada vez | Más concreto: describe cómo se da la situación, con sus condiciones y sus caminos |
| **El sistema** | Está en el centro: el límite del sistema separa actores de funciones | Puede no haber sistema de software: el gimnasio con carpetas tiene escenarios |
| **Lo que se pierde al convertir** | — | **La lógica que decide el camino.** Si pasás los subescenarios a casos de uso, ¿dónde queda el "si logró inscribirse, anula"? En ningún lado |

La última fila es la clave, y es lo que descubrieron los equipos al convertir. Vale la pena ver qué les pasó.

### 3.3 Qué pasa cuando se convierte

**Inscribir a clase → casos de uso.** Primera versión que sale: tomar los tres subescenarios (REGISTRAR RESERVA, CONTRATAR PLAN, INGRESAR A LISTA DE ESPERA) y hacerlos casos de uso, cada uno con su actor. Resultado: tres óvalos sueltos y un actor profesor. Tiene lógica, cada uno tiene sus pasos adentro. Pero se perdió lo principal: **qué los une**. Nada dice que primero se mira el cupo, y que según haya o no se va por uno u otro.

Segunda versión: un caso de uso padre, "Inscribir a clase", y los tres subescenarios como **extensiones**. Mejor, porque ahora están conectados. Pero si después escribís el flujo normal y los alternativos de ese caso de uso, **no queda lo mismo que el escenario**: el caso de uso dice "extiende a…" y el escenario decía "si no hay cupo, ofrece lista de espera; si acepta, anota; si no, busca otro horario". La secuencia de decisiones no entra en un diagrama. Y lo que sí entra, el "módulo de inscripción" con todo lo que está adentro del cuadrado, es el alcance del caso de uso padre, no el escenario.

**Anular inscripción → casos de uso.** Primera versión: cinco casos de uso ("validar registro", "validar que el horario esté dentro del rango", "anular", "avisar cupo libre"…). Cada paso del escenario convertido en función. Es **sobrediseño**: funciones demasiado granulares, que no son algo que un actor necesite por sí mismo. Nadie "necesita validar un horario"; necesita darse de baja. Segunda versión: el equipo lo redujo a "anular inscripción" con "avisar cupo libre" como extensión y una inclusión para notificar al socio. La cátedra no la discutió en detalle; pasó a lo que importaba, comparar criterios entre equipos.

**La relación rara.** Otro equipo dejó "contratar nuevo plan" y "ofrecer nuevo plan" unidos por una línea sin nombre, como si uno dependiera del otro. ¿Es una generalización (un caso de uso que es un tipo de otro)? No. Son **casos de uso independientes**: ofrecer es una cosa (queda muy granular) y contratar es otra; el socio decide si contrata. Lo que pasaba es que en el escenario la respuesta "sí, contrato" estaba adentro de inscribirse, y al convertir, esa dependencia de la secuencia se quiso dibujar como relación entre casos de uso. No se puede: el caso de uso no tiene "después de".

### 3.4 Lo que la cátedra concluyó

1. **No son la misma herramienta.** Trabajan parecido, tienen muchas similitudes, pero una modela situaciones específicas y la otra un modelo más abstracto de funciones.
2. **No hay relación uno a uno.** Un escenario no se convierte en un caso de uso ni en N casos de uso sin perder algo, y al revés.
3. **Lo que se pierde al convertir es la lógica del camino.** Los episodios simples y condicionales que están entre las llamadas a subescenarios (módulo 3, Cambiar inscripción) no tienen dónde ir en un diagrama de casos de uso.
4. **Sí puede haber una relación útil:** la cátedra sugirió que si partís de un **buen** caso de uso y le escribís su escenario, el escenario sale mejor. Las herramientas se complementan; no se reemplazan.
5. **El actor es quien tiene la necesidad.** No solo quien toca el sistema. Eso vale para las dos herramientas y es lo que hace que un escenario actual, sin software, tenga actores igual.

**Cuándo usar cada uno:** el escenario para **entender el negocio** (el actual) y para **acordar con el cliente** qué va a cambiar (el futuro: el cliente ve dónde está el cambio en su proceso). El caso de uso para **modelar el alcance del sistema**: qué funciones ofrece y a quién. En un proyecto se usan los dos.

> 🎓 **Para el parcial, si te preguntan: ¿un caso de uso y un escenario son lo mismo?**
> No. Comparten elementos (actores, objetivo, pasos con alternativas, precondición), pero el caso de uso modela una función abstracta del sistema y el escenario describe una situación concreta del negocio con continuidad en el tiempo. No hay correspondencia uno a uno: al convertir un escenario en casos de uso se pierde la lógica que decide el camino entre subescenarios; son herramientas complementarias, no intercambiables.

🕳️ **Madriguera — historias de usuario.** En metodologías ágiles, la unidad es la historia de usuario, con su criterio de aceptación. Tienen puntos en común con escenarios y casos de uso, y en algunos trabajos de la materia se las compara; pero no se enseñan ni se evalúan acá. *Volvé al camino.*

## 4. 🔴 La cadena: LEL → escenario actual → escenario futuro → requisito

Todo lo de las dos series cierra en una cadena. Con el caso de la oficina de pasaportes:

```
┌──────────────────────┐   ┌─────────────────────────┐   ┌─────────────────────────┐   ┌──────────────────────────┐
│ LEL                  │   │ ESCENARIO ACTUAL        │   │ ESCENARIO FUTURO        │   │ REQUISITO                │
│ SOLICITANTE (sujeto) │ → │ COBRAR EL TRÁMITE       │ → │ COBRAR EL TRÁMITE       │ → │ RF: El cajero COBRA EL   │
│ Impacto: paga el     │   │ Actores: solicitante,   │   │ El cajero consulta el   │   │ TRÁMITE.                 │
│ trámite.             │   │ cajero. El cajero       │   │ importe ingresando el   │   │ RNF: El número de control│
│                      │   │ informa el importe.     │   │ número de control.      │   │ es único por trámite.    │
└──────────────────────┘   └─────────────────────────┘   └─────────────────────────┘   └──────────────────────────┘
```

1. **Del LEL salen los escenarios candidatos.** El sujeto `Solicitante` tiene el impacto "paga el trámite". Cada impacto de un sujeto (y de un verbo) es una situación: candidata a escenario.
2. **El escenario actual se escribe con el vocabulario del LEL.** Actores = sujetos (solicitante, cajero). Recursos = objetos. Y se escribe desde el punto de vista del negocio: "COBRAR el trámite", no "pagar el trámite".
3. **El escenario futuro cambia lo que el software cambia.** El cajero ya no informa el importe él: lo consulta ingresando un número de control. Apareció un recurso nuevo (el número de control) y una interacción con el sistema.
4. **Del escenario futuro salen los requisitos.** Un RF (el cajero cobra el trámite) y un RNF (el número de control es único). Los dos escritos con símbolos del LEL.

Eso es la **trazabilidad**: desde un requisito podés ir hacia atrás hasta el símbolo del LEL que lo originó, y desde un símbolo hacia adelante hasta los requisitos que dependen de él. Si el cliente cambia de idea sobre cómo se cobra, sabés qué escenarios y qué requisitos tocar.

> 🎓 **Para el parcial, si te preguntan: ¿cómo se relacionan el LEL, los escenarios y los requisitos?**
> Los impactos de los símbolos sujeto y verbo del LEL originan los escenarios actuales candidatos; de los escenarios actuales y los objetivos se derivan los escenarios futuros; y de los escenarios futuros se derivan los requisitos funcionales y no funcionales. Como todos se escriben con los símbolos del LEL, se puede rastrear hacia atrás y hacia adelante: el LEL es el ancla de la trazabilidad.

## 5. Hilos

**Cerrado:** "¿para qué sirve el LEL después?", de la serie anterior: sección 4.
**Siguen abiertos:** "4. Existe cupo" y la precondición de Inscribir a clase. Módulo 5, el último.

---

## Checkpoint del módulo 4

Respondé sin mirar el texto. Sin respuestas acá: van al complemento.

1. Vida Sana no tiene software. ¿Tiene un sistema de información? Justificá con dos ejemplos del enunciado.
2. ¿Qué es la ubicuidad y en qué parte del escenario se refleja? Escribí el contexto de "Avisar ausencia" en su versión actual y en una futura con app.
3. Entre el escenario actual y el futuro de Inscribir a clase, nombrá dos partes que cambian y una que no. ¿Por qué el objetivo no cambia?
4. Un equipo convirtió los tres subescenarios de Inscribir a clase en tres casos de uso sueltos. ¿Qué se perdió? ¿Y qué faltaba todavía en la versión con extensiones?
5. ¿Por qué "validar que el horario esté dentro del rango" no es un buen caso de uso, si sí es un buen episodio?
6. Explicá con tus palabras la frase "el actor es quien tiene la necesidad, no solo quien interactúa con el sistema". ¿Qué implica para un escenario actual?
7. Tomá el impacto "Realiza [[Avisar ausencia]]" del sujeto `Socio` del LEL de Vida Sana y recorré la cadena: qué escenario actual sale, cómo cambiaría en el futuro con app, y un RF y un RNF que se derivarían.

## Qué viene en el módulo 5

El último: cómo revisar que un escenario esté completo, que es lo que la cátedra dijo que se evalúa este cuatrimestre. La lista de la cátedra, la lista de la lectura para afinar, qué corrige la cátedra y qué tolera, y dos talleres: el escenario de Vida Sana que repartió la cátedra, y tu Word del ejercicio.

---

**FIN DEL MÓDULO 4 — Clase desde cero — Escenarios**
