# 📘 APUNTE MAESTRO — Clase 06
## Parte 2: Elegir la técnica de elicitación

**Materia:** Ingeniería de Requisitos · **Unidad:** clase06 · **Parte:** 2 de 4

---

### Qué cubre esta parte

En la Parte 1 dimos por sentado que el cuestionario era la herramienta correcta y nos concentramos en armarlo bien. Ahora damos un paso atrás: **cómo se decide qué técnica usar**, qué etapas atraviesa cualquiera de ellas, y qué ventajas, desventajas y riesgos trae cada una.

**Leyenda de marcas:** 🔴 central, altamente evaluable · 🟡 secundario, puede aparecer · 🟢 mencionado al pasar.

---

## 1. El caso: dos grupos, dos herramientas 🔴

Tenés que relevar requerimientos para una solución en un centro de entrenamiento. Hay dos grupos de los que necesitás información:

| Grupo | Cuántos son | Qué sabés de ellos |
|---|---|---|
| Junta directiva y profesores | Un puñado de personas | Están identificados, tienen nombre y apellido, se puede coordinar con ellos |
| Socios | Cientos | No los conocés, no sabés quiénes son ni cómo piensan |

Con el primer grupo hacés **entrevistas**. Con el segundo, un **cuestionario**.

La pregunta obvia: ¿por qué no entrevistar también a los socios? Serían entrevistas mucho más ricas.

**Porque es imposible.** Entrevistar a cada socio, uno por uno, no se puede hacer. No hay tiempo tuyo ni disponibilidad de ellos. Cuando el universo a relevar es muy amplio, la entrevista deja de ser una opción y el cuestionario pasa a ser la herramienta que conviene aplicar, aunque te dé información más pobre.

Ahí está la decisión de fondo: **la técnica no se elige por cuál es mejor en abstracto, sino por cuál es aplicable a ese grupo, con ese tamaño, en ese contexto.**

Entrevista, cuestionario y observación son tres técnicas de elicitación: tres formas distintas de hacer lo mismo, cada una con su terreno. Lo que sigue es el criterio para elegir entre ellas.

---

## 2. Las etapas de toda técnica de elicitación 🔴

Cualquiera sea la técnica, el trabajo tiene tres momentos. Aplicarla no es solo ejecutarla.

```
   ┌─────────────────────────────────────────────────────────┐
   │  1. PLANIFICAR                                          │
   │     ¿A quién voy a entrevistar?                         │
   │     ¿A quién le mando el cuestionario?                  │
   │     ¿Por qué elijo ESTA herramienta y no otra?          │
   └────────────────────────┬────────────────────────────────┘
                            ▼
   ┌─────────────────────────────────────────────────────────┐
   │  2. DISEÑAR Y EJECUTAR                                  │
   │     Armar el instrumento de modo que el tiempo          │
   │     invertido rinda — el mío Y el de la otra persona,   │
   │     que también tiene que dar su tiempo para responder. │
   └────────────────────────┬────────────────────────────────┘
                            ▼
   ┌─────────────────────────────────────────────────────────┐
   │  3. ANALIZAR                                            │
   │     Sacar de todo eso información de relevancia para    │
   │     tomar decisiones respecto del proyecto.             │
   └─────────────────────────────────────────────────────────┘
```

Las tres etapas tienen el mismo peso, y la tercera es la que justifica a las otras dos. Una técnica bien ejecutada que no produce información útil para decidir fue tiempo tirado — tuyo y de la otra persona.

Fijate que la etapa 1 incluye una pregunta que es fácil saltearse: **¿por qué elijo esta herramienta?** No alcanza con "hago una entrevista porque es lo que se hace". La elección se justifica, y se justifica con el tamaño del grupo, con lo que necesito obtener y con lo que tengo disponible.

---

## 3. Ventaja, desventaja y riesgo no son lo mismo 🔴

Esto es una distinción que conviene tener afilada, porque se pregunta y porque ordena todo lo que viene después.

| Concepto | Qué es | Ejemplo |
|---|---|---|
| **Ventaja** | Algo bueno que la técnica te da por definición. Es seguro. | La entrevista te da información cualitativa |
| **Desventaja** | Un costo inherente a la técnica. Viene con el paquete, no se elimina. | La entrevista no escala a cientos de personas |
| **Riesgo** | Algo malo que *puede* pasar. No es seguro. **Y se puede mitigar.** | Entrevistar a la persona equivocada |

La diferencia operativa está en la última columna: **todo lo que sea riesgo se puede mitigar.** Un riesgo no es una condena, es algo sobre lo que podés actuar antes de que ocurra. Una desventaja no: si elegiste la técnica, la desventaja te la comés.

Por eso, cuando te pidan analizar una técnica, no alcanza con listar cosas malas. Hay que separar qué es costo inevitable y qué es riesgo, y para cada riesgo decir **cómo se mitiga**.

> **📌 Para el parcial, si te preguntan**
> **¿Qué diferencia hay entre una desventaja y un riesgo de una técnica de elicitación?**
> La desventaja es un costo inherente a la técnica, que se asume al elegirla y no se puede eliminar. El riesgo es un evento potencial que puede ocurrir o no, y que siempre admite alguna forma de mitigación mediante acciones previas. Por eso todo análisis de riesgos debe incluir la mitigación correspondiente.

---

## 4. La entrevista 🔴

### Ventajas

- **Información cualitativa.** Es la gran ventaja. El entrevistado explica, matiza, cuenta el caso raro, se contradice y vos lo ves contradecirse. Nada de eso aparece en un formulario.
- **Presencial o remota.** No exige coincidir en el mismo lugar físico, lo cual amplía a quién podés entrevistar.

### Desventaja

- **No escala.** Requiere tiempo tuyo y tiempo del entrevistado, uno por uno. Con un universo grande, es inaplicable.

### El riesgo principal: entrevistar a quien no puede responderte

Este es el riesgo que hay que saber nombrar.

Apuntás a un stakeholder o a un usuario que, en definitiva, **no te puede dar respuesta** — porque lo que preguntás no tiene que ver con lo que esa persona resuelve o conoce. Se invierte tiempo de él y tiempo tuyo en una conversación que no produce nada.

**De dónde sale:** del **desconocimiento del negocio**. Todavía no entendés bien cómo funciona la organización, quién decide qué, y elegís mal al interlocutor.

> **Al pie, para tenerlo fresco:** el riesgo alcanza tanto a stakeholders como a usuarios, y la distinción entre ambos importa acá — a un stakeholder que no usa el sistema no le podés preguntar por la operación diaria, y a un usuario no le podés preguntar por decisiones que no toma. Elegir mal el tipo de interlocutor es una forma concreta de este riesgo.

### Cómo se mitiga

**Mitigación 1 — Estudio previo.** Entender el negocio antes de entrar a preguntar. Quién hace qué, cómo está organizado, dónde se toman las decisiones.

**Mitigación 2 — Validar el interlocutor con quien corresponda.** Antes de sentarte con alguien, confirmar con quien te contactó, con el sponsor o con quien está a cargo del proyecto que esa es efectivamente la persona que puede darte la información que buscás.

> **Término:** el **sponsor** es quien impulsa y respalda el proyecto dentro de la organización — típicamente quien lo pide y consigue el presupuesto. Es la puerta de entrada natural para validar con quién hay que hablar.

**Mitigación 3 — Elegir el momento.** No es solo *quién*, es *cuándo*. Si vas a hablar con alguien del área de impuestos justo en una fecha cercana a un vencimiento, no va a tener ni el tiempo ni la predisposición para escucharte: va a estar con la cabeza en lo operativo que tiene que resolver. La persona es la correcta y la entrevista igual sale mal.

```
   RIESGO: la entrevista no produce información útil
        │
        ├─► causa: interlocutor equivocado
        │   └─► mitigación: estudio previo + validar con sponsor
        │
        └─► causa: momento equivocado
            └─► mitigación: coordinar fuera de los picos operativos
```

> **📌 Para el parcial, si te preguntan**
> **¿Cuál es el principal riesgo de la entrevista y cómo se mitiga?**
> No identificar correctamente al interlocutor: se entrevista a un stakeholder o usuario que no puede dar respuesta sobre lo que se pregunta, y se desperdicia su tiempo y el nuestro. Surge del desconocimiento del negocio. Se mitiga con estudio previo del dominio y validando con el sponsor o con quien está a cargo del proyecto que esas son las personas adecuadas, además de coordinar en un momento en que tengan disponibilidad real.

---

## 5. El cuestionario 🔴

### Ventaja

- **Llega a muchos.** Es su razón de ser. Cuando el universo es amplio, es la única herramienta que permite alcanzar a un público diverso en un tiempo razonable.

### Desventajas

- **Información más pobre.** No hay repregunta, no hay matiz, no hay lenguaje corporal. Lo que preguntaste es lo que obtenés.
- **El diseño es todo.** Como no podés corregir sobre la marcha, un error de diseño se propaga a todas las respuestas. (Toda la Parte 1 es sobre esto.)

### Los riesgos

**Riesgo 1 — No conocés al público.** No sabés a quién le estás mandando el cuestionario ni cómo está compuesto ese conjunto. Es el espejo exacto de la ventaja: llegás a muchos justamente porque no los conocés uno por uno.

*Mitigación:* las variables de segmentación de la Parte 1 — no eliminan el desconocimiento, pero te permiten reconstruir a posteriori de qué población vinieron las respuestas.

**Riesgo 2 — Que no quieran responder.** Simplemente lo ignoran. Siempre está la opción de posponerlo *"en otro momento"*, y ese otro momento nunca llega.

**Riesgo 3 — Que respondan sin compromiso.** Completan por completar, marcan cualquier cosa para sacárselo de encima. Tenés respuestas registradas que no representan nada.

**Riesgo 4 — Que se sientan observados y no sean sinceros.** Este ya lo trabajamos en profundidad en la Parte 1: el anonimato percibido determina la sinceridad.

### Las formas de distribuirlo 🟡

Hay más canales que el formulario web, y cada uno tiene su propio sesgo.

| Canal | Cómo se ve en la práctica | Qué trae |
|---|---|---|
| Formulario web | Un link que se difunde | El más usado; permite volumen |
| Llamado telefónico | Un encuestador te llama y pregunta | Alta tasa de respuesta, **anonimato nulo** |
| Mail post-uso | "¿Nos das tu opinión sobre el servicio?" | Llega justo después de la experiencia |
| Consulta dentro de una app | El banco te pregunta qué tan conforme estás | Muy cortas, en el momento de uso |
| Pop-up en una web | "¿Encontraste la información que buscabas?" | Una o dos preguntas, contexto inmediato |

**El caso del llamado telefónico merece atención**, porque muestra dos problemas juntos. En un club, durante un período de elecciones internas, llamaban a los socios al celular y les hacían el cuestionario por teléfono: si está de acuerdo con tal cosa, si va a la cancha, qué deporte hace, cuántos años hace que es socio.

Dos cosas pasan ahí:

1. **Ellos sabían perfectamente quién estaba respondiendo.** Te llamaron a tu número. El anonimato no existe, y con él se va la sinceridad.
2. **El socio no sabía quién preguntaba.** ¿Era el oficialismo o la oposición? Sin saber quién recolecta y para qué, no podés calibrar tu respuesta — y del otro lado, quien analiza los datos no puede descartar que el respondente haya contestado en función de una suposición equivocada.

Esto engancha directo con la introducción de contexto de la Parte 1: decir quién sos y para qué preguntás no es formalidad, es condición para que el dato valga.

**Un riesgo lateral, la fatiga.** Cuando una empresa te hace la misma pregunta cada vez que usás una funcionalidad, la respuesta deja de tener sentido: la gente la completa en automático o la ignora. Repetir el mismo instrumento sobre el mismo público lo degrada.

---

## 6. La observación 🟡

Es la tercera técnica que aparece en escena, y funciona distinto de las dos anteriores: **no preguntás nada.**

Te ubicás en el lugar donde ocurre la actividad —típicamente un punto de atención al público— y mirás qué está pasando, **sin intervenir**, con quienes pueden estar siendo afectados por el problema.

**Qué se ve ahí que no aparece ni en una entrevista ni en un cuestionario:**

- **Demoras reales.** No cuánto dice la gente que espera, sino cuánto espera efectivamente.
- **Interfaces poco amigables.** Dónde la persona se traba con el sistema con el que tiene que interactuar.

**La ventaja de fondo:** eliminás el filtro de la percepción y del relato. En la Parte 1 vimos el problema de la espera — dos minutos son mucho para el apurado y media hora no se siente para el distraído. La observación mide lo que pasó, no lo que la persona cree que pasó.

---

## 7. El cuadro completo 🔴

```
              ENTREVISTA          CUESTIONARIO         OBSERVACIÓN
             ─────────────       ──────────────       ─────────────
  Alcance    pocos               muchos               pocos
  Profund.   alta                baja                 media
  Dato       lo que dicen        lo que dicen         lo que HACEN
  Cuándo     grupo chico e       universo amplio,     hay actividad
             identificable       inabordable 1 a 1    observable
             
  Riesgo     interlocutor        no conocés al        no explica
  clave      equivocado          público / no         el porqué
                                 responden / no
                                 son sinceros
```

**La conclusión que ordena todo:** ninguna técnica es mejor que otra en abstracto. Se combinan, y se combinan **para contrastarse entre sí** — que es exactamente el mecanismo de ratificación y rectificación que vimos en la Parte 1. Lo que dicen los directivos en la entrevista se contrasta con lo que responden los socios en el cuestionario, y las dos cosas se contrastan con lo que efectivamente pasa cuando alguien se para a mirar.

> **📌 Para el parcial, si te preguntan**
> **¿Por qué se elige un cuestionario en lugar de entrevistas para relevar a los socios de un centro de entrenamiento?**
> Porque el universo es muy amplio y entrevistar a cada socio es inviable en tiempo y disponibilidad. El cuestionario permite llegar a un público diverso, asumiendo como costo una información más pobre y los riesgos de falta de respuesta, respuestas sin compromiso y falta de sinceridad. La técnica se elige por su aplicabilidad al grupo y al contexto, no por su calidad en abstracto.

---

## ✅ Checkpoint — Parte 2

1. Nombrá las tres etapas que atraviesa toda técnica de elicitación y explicá qué se decide en la primera.

2. ¿Qué diferencia hay entre una desventaja y un riesgo de una técnica? ¿Qué propiedad tiene todo riesgo que la desventaja no tiene?

3. ¿Cuál es el principal riesgo de la entrevista? Explicá de dónde surge y nombrá dos mitigaciones distintas.

4. Además de elegir bien al interlocutor, ¿qué otra variable puede arruinar una entrevista con la persona correcta? Dar un ejemplo.

5. Enumerá los cuatro riesgos del cuestionario.

6. Un club llama por teléfono a sus socios para encuestarlos durante un período electoral. Identificá los dos problemas distintos que tiene ese diseño.

7. ¿Qué tipo de información permite obtener la observación que ninguna de las otras dos técnicas puede dar? Relacionalo con el problema de la percepción que vimos en la Parte 1.

8. Justificá, con el criterio de la clase, por qué a la junta directiva se la entrevista y a los socios se les manda un cuestionario.

9. ¿Para qué sirve aplicar más de una técnica sobre el mismo problema?

---

## Qué viene en la Parte 3

Ya tenemos los requerimientos relevados. Ahora la pregunta cambia: **¿están bien escritos?** En la Parte 3 vienen las características de calidad de un requerimiento, de dónde salen, y el defecto de redacción más frecuente de todos — escribir desde el punto de vista del sistema en lugar del actor. Con la discusión completa sobre por qué el sistema no es un actor y qué se hace con las notificaciones.

---

**FIN DE LA PARTE 2 — Clase 06**
