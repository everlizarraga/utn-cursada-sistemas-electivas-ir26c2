# 📘 APUNTE MAESTRO — Clase 06
## Parte 4: La lista DEO y el ejercicio de la clase

**Materia:** Ingeniería de Requisitos · **Unidad:** clase06 · **Parte:** 4 de 4

---

### Qué cubre esta parte

La herramienta para encontrar los requerimientos que no cumplen con las características de calidad: la **lista DEO**. Y el ejercicio de la clase, que es donde todo lo anterior se vuelve tangible — porque no se trabajó sobre un enunciado inventado, sino sobre un documento producido por otro equipo de la cursada.

Cierra con la información operativa que salió de la clase.

**Leyenda de marcas:** 🔴 central, altamente evaluable · 🟡 secundario, puede aparecer · 🟢 mencionado al pasar.

---

## 1. El ejercicio: te toca construir sobre el documento de otro 🔴

El planteo es simple de enunciar y tiene una trampa adentro.

Cada equipo recibe un documento con la parte de requerimientos extraída de **la minuta de reunión de otro equipo** — una minuta real, producida durante esta cursada, a partir de la entrevista con la junta directiva y los profesores del centro de entrenamiento. Se eligieron tres minutas y se repartieron entre los equipos, dos equipos por minuta.

Nadie sabe de qué equipo es el documento que le tocó.

**La consigna, primera parte:** armar el diagrama de casos de uso en base a esos requerimientos, y después responder dos preguntas:

- ¿Pudieron identificar los actores de cada caso de uso, o los asumieron en función del requerimiento?
- ¿Pudieron identificar los casos de uso y sus relaciones de inclusión, extensión y con el o los actores?

> **Precisión que conviene tener clara:** cuando se pide "el caso de uso" en este contexto, se pide **el diagrama**. No la especificación textual con todos los pasos, precondiciones y flujos alternativos. Es el diagrama.

### El objetivo real no era el caso de uso

Acá está la trampa, y entenderla es entender la clase entera.

**El caso de uso era la excusa.** El objetivo era que cada equipo experimentara en carne propia **qué pasa cuando tenés que construir un artefacto a partir de un documento que tiene defectos de calidad**.

La secuencia es esta:

```
   EQUIPO A                          EQUIPO B
   ────────                          ────────
   Entrevista a la junta
   directiva y profesores
        │
        ▼
   Produce una minuta con
   los requerimientos  ──────────►   Recibe ese documento
                                          │
                                          ▼
                                     Tiene que armar un
                                     caso de uso con eso
                                          │
                                          ▼
                                     ¿Pudo? ¿Cuánto tuvo
                                     que inventar?
```

Podría haber sido cualquier otro artefacto: un diagrama de actividades, un diagrama de clases, un diagrama de estados de la inscripción a una clase. Se eligió el caso de uso porque es lo que corresponde a esta materia, pero el fenómeno es el mismo con cualquiera.

**Y una aclaración que vale la pena retener, porque marca el espíritu con el que se corrige en esta materia:** el objetivo no es darle palos al compañero que escribió la minuta. Es darse cuenta de que **esto me puede pasar con el producto que yo produzca**. El documento que sale de mis manos va a ser el insumo del trabajo de otro.

### Lo que pasó, previsiblemente

Los requerimientos de las minutas estaban escritos así: *el sistema debe organizar*, *el sistema debe controlar*, *el sistema debe gestionar*, *el sistema debe notificar*.

Y los equipos hicieron lo esperable: pusieron al **sistema como actor** en el diagrama.

Ya sabemos por la Parte 3 que eso está mal. Pero lo interesante es **por qué pasó**: no fue por no saber la teoría. Fue porque **el documento de entrada estaba escrito de esa forma**, y el defecto se propagó al artefacto de salida sin que nadie lo decidiera.

```
   Defecto en la redacción         →    Defecto en el modelo
   del requerimiento                    que se construye encima

   "El sistema debe                     [Sistema] como actor
    controlar..."                        acaparando todas las
                                         funcionalidades
```

**Esa propagación es el contenido de la clase.** La calidad de lo que producís no es un tema de prolijidad: determina la calidad de todo lo que se construya después.

**La reacción correcta frente a un documento así** no es replicar el defecto. Es decir: *"pará, el sistema no es un actor. Acá tengo que reescribir esto, porque entiendo que los actores son estos otros."* Detectar el defecto, nombrarlo, y corregir el insumo antes de construir encima.

---

## 2. El signo de pregunta: qué hacer cuando el documento no alcanza 🟡

Situación concreta: leés un requerimiento, entendés que ahí hay una funcionalidad, pero **no lográs identificar quién la hace**. El documento no lo dice.

Tenés dos salidas, y las dos son válidas:

**Salida 1 — El signo de pregunta.** Ponés el caso de uso en el diagrama y en el actor ponés `?`.

```
        ( Organizar uso de instalaciones )
                      │
                      │
                     [?]   ← no logro identificar de quién es
```

Esto es **totalmente válido** y es una convención que se arrastra de Análisis de Sistemas. No es una rendición: es documentar con precisión que ahí hay un hueco en el relevamiento.

**Salida 2 — Asumir y dejar constancia.** *"Conociendo el contexto, entiendo que esto lo necesita el profesor."* Lo asumís, lo modelás con ese actor, **pero registrás que el requerimiento no lo decía.**

**Lo que no es válido** es asumir en silencio. Si inferís sin dejar rastro, el hueco del relevamiento desaparece y nadie va a volver a preguntarlo. Por eso las dos preguntas de la consigna apuntan justo ahí: *¿los identificaron o los asumieron?* La respuesta honesta es el dato que importa.

**El criterio de evaluación es coherente con esto:** no se evalúa la calidad del diagrama. Se evalúa si el relevamiento que se hizo permitió entender las funcionalidades y modelarlas. Un diagrama lleno de signos de pregunta puede ser un trabajo excelente, si esos signos están bien puestos.

---

## 3. La lista DEO 🔴

Acá viene la herramienta formal. Es el contenido más evaluable de esta parte.

Cuando hacemos la **verificación** de un producto —revisar si lo que produjimos cumple con lo que tiene que cumplir— existe un instrumento llamado **lista DEO**:

> **DEO = Defectos, Errores y Omisiones.**

Son tres categorías distintas de problema. No son sinónimos, y la gracia está en distinguirlas, porque **cada una se resuelve de manera diferente**.

```
   ┌──────────────┬────────────────────────────┬─────────────────────┐
   │  CATEGORÍA   │  QUÉ ES                    │  CÓMO SE RESUELVE   │
   ├──────────────┼────────────────────────────┼─────────────────────┤
   │  DEFECTO     │  Está, pero NO CUMPLE      │  Se reescribe — o   │
   │              │  alguna característica     │  se vuelve a la     │
   │              │  de calidad                │  fuente, si falta   │
   │              │                            │  un dato            │
   ├──────────────┼────────────────────────────┼─────────────────────┤
   │  ERROR       │  Está, y dice algo que     │  Se corrige contra  │
   │              │  NO ES CIERTO              │  la regla de        │
   │              │                            │  negocio            │
   ├──────────────┼────────────────────────────┼─────────────────────┤
   │  OMISIÓN     │  NO ESTÁ                   │  Se agrega,         │
   │              │                            │  sin romper la      │
   │              │                            │  consistencia       │
   └──────────────┴────────────────────────────┴─────────────────────┘
```

### 3.1 Defecto — está mal escrito

**Definición:** el requerimiento existe y es conceptualmente válido, pero **está redactado de una forma que no es concisa, no es consistente o no es clara**. Incluye no estar escrito desde el punto de vista del actor.

**Ejemplos:**

- *"El sistema debe..."* — el defecto más frecuente de todos.
- Dos verbos o dos funcionalidades en una misma sentencia (el problema de cohesión de la Parte 3).
- Ambigüedad: términos que admiten más de una lectura.
- Incompletitud: falta un dato sin el cual no se puede construir (un plazo, un umbral, un alcance).

**Cómo se resuelve:** la mayoría se reescribe, y por eso es la categoría más benigna — la información está, solo hay que expresarla bien. **La excepción es la incompletitud:** si el dato que falta nunca se relevó, no lo podés inventar en el escritorio. Ahí la corrección no es de redacción; hay que volver a preguntarle a la fuente. Distinguir uno de otro es parte del análisis: *¿esto lo sé y lo escribí mal, o directamente no lo sé?*

### 3.2 Error — dice algo que no es cierto

**Definición:** el requerimiento afirma algo que **conceptualmente está mal**, porque **contradice una regla de negocio**.

**Ejemplos:**

- *"El socio puede tomar clases sin haber pagado la cuota."*
- *"El socio puede reservar un cupo sin tener el plan pago."*
- *"El socio puede reservar aunque no le queden clases disponibles en su plan."*

En los tres casos el problema no es la redacción: está impecablemente escrito. El problema es que **la regla de negocio dice otra cosa**. Si esto llega a desarrollo, se construye un sistema que hace algo que el negocio no permite.

**Cómo se resuelve:** volviendo a la regla de negocio real y corrigiendo lo que el requerimiento afirma. Es la categoría más traicionera, porque un defecto salta al leerlo y un error **pasa la lectura sin problema**: hay que conocer el negocio para detectarlo. Si nadie lo hace, sobrevive hasta que el sistema está andando.

### 3.3 Omisión — falta

**Definición:** **falta un requerimiento.** La lista está incompleta.

**El ejemplo del dominio del centro de entrenamiento:** falta el **alta del socio a una clase** — la reserva del cupo. Hay requerimientos sobre darse de baja, sobre avisar ausencias y sobre la lista de espera, pero en ningún lado se dijo cómo un socio se anota en primer lugar.

**La analogía que lo fija:** *"me dijiste que tengo que poder encender el televisor. No me dijiste que lo tengo que apagar."* El requerimiento que falta muchas veces es el complemento obvio del que sí está — obvio para el que lo escribió, invisible para el que lo lee.

**Requerimientos derivados.** Hay un tipo particular de omisión que aparece por dependencia: me dijiste que el socio puede darse de baja de una clase o avisar una ausencia, pero **para poder darse de baja primero se tuvo que anotar**. Ese requerimiento de alta lo necesito para resolver los otros. Se llama derivado porque surge de lo que ya está pedido.

**Cómo se resuelve:** se agrega el requerimiento faltante. Con una precaución: **al agregarlo hay que ser consistente con lo que ya está**. No sirve tapar el agujero con algo que contradiga el resto del conjunto — ahí convertís una omisión en una inconsistencia.

### Dónde vuelve a aparecer esta herramienta

La lista DEO no es exclusiva de los requerimientos. Es una herramienta de **verificación de contenido** en general: sirve para evaluar la completitud y la calidad de cualquier producto del análisis.

Va a reaparecer más adelante, cuando se trabaje el **Léxico Extendido del Lenguaje**, aplicada a verificar la completitud de ese artefacto. Es la misma herramienta, otro objeto.

> **📌 Para el parcial, si te preguntan**
> **¿Qué es la lista DEO y qué distingue a cada una de sus categorías?**
> Es un instrumento de verificación que clasifica los problemas de un producto del análisis en defectos, errores y omisiones. El defecto es un requerimiento mal redactado —no conciso, no consistente, no claro, o no escrito desde el punto de vista del actor— y se resuelve reescribiéndolo. El error es un requerimiento que afirma algo que contradice una regla de negocio. La omisión es un requerimiento que falta, y al agregarlo debe mantenerse la consistencia con el conjunto existente.

---

## 4. El documento de trabajo 🔴

Estos son los requerimientos sobre los que se trabajó. Provienen de una entrevista con la junta directiva y los profesores de un centro de entrenamiento, y están transcriptos tal como llegaron — con sus defectos incluidos, porque los defectos son el objeto de estudio.

### Requerimientos funcionales

| ID | Requerimiento |
|---|---|
| RF-01 | El profesor debe registrar cuando un cliente/socio presente algún tipo de limitación física durante o previo a un entrenamiento. |
| RF-02 | El sistema debe permitir al gerente visualizar, para cada profesor, el porcentaje de clases dictadas con cupo completo en el mes, a fin de identificar quiénes alcanzan el porcentaje base definido y corresponden al pago del bono. |
| RF-03 | El socio podrá registrar sus asistencias al momento de ingresar al establecimiento. |
| RF-04 | El socio podrá darse de baja de una clase desde el sistema. |
| RF-05 | El sistema debe notificar la baja de asistencia a una clase mediante WhatsApp al profesor/es asignado/s a esa clase. |
| RF-06 | Los profesores deben poder emitir comunicaciones (avisos, cupos, plantillas) por WhatsApp a los socios desde el sistema. |
| RF-07 | El sistema debe organizar el uso de las instalaciones diferenciando entre clases con profesor asignadas a un turno fijo, y sectores de uso libre (cardio y musculación). |
| RF-08 | Los profesores deben ser alertados cuando se excede el tiempo límite de uso de las instalaciones. |
| RF-09 | El sistema debe controlar la capacidad máxima de cada clase/sector según el tipo (8 pilates, 7 cardio, 5 musculación, 8 yoga/funcional/stretching). |
| RF-10 | El sistema debe gestionar automáticamente la lista de espera de una clase completa, ofreciendo el lugar por orden de inscripción cuando un socio se da de baja. |
| RF-11 | El sistema debe alertar a los profesores cuando una clase tenga menos de 3 socios anotados, para ofrecerles cambiar de turno. |
| RF-12 | El sistema debe gestionar los planes mensuales de los socios (4, 6, 8 o 12 clases), controlando su vigencia desde la primera clase hasta la misma fecha del mes siguiente. |
| RF-13 | El sistema debe registrar avisos de ausencia de los socios y habilitar la recuperación de clase solo a quienes avisaron con una anticipación de 1 día. |
| RF-14 | El sistema debe notificar a los socios en lista de espera cuando se libere un cupo por ausencia avisada. |
| RF-15 | El sistema debe controlar el tiempo mínimo (30 min) y máximo (120 min) de uso en los sectores sin profesor, dentro del horario de 8 a 20 hs de lunes a sábados. |

### Requerimientos no funcionales

| ID | Requerimiento | Categoría |
|---|---|---|
| RNF-01 | El sistema debe confirmar un registro de asistencia en un tiempo no mayor a 2 segundos. | Rendimiento |
| RNF-02 | El sistema debe procesar la actualización de una lista de espera (baja de un socio y oferta del cupo al siguiente inscripto) en un tiempo no mayor a 5 segundos. | Rendimiento |
| RNF-03 | El sistema debe permitir que el 80% de los profesores puedan registrarse en el sistema en menos de 30 segundos. | Usabilidad |
| RNF-04 | El sistema debe garantizar la exactitud de los registros de horario, con una tasa de error del 0.1% en la asignación de turnos, evitando inconsistencias que afecten la confiabilidad de los datos de asistencia. | Confiabilidad |
| RNF-05 | El inicio de sesión de los clientes debe realizarse en menos de 3 clicks. | Usabilidad |
| RNF-06 | El presente de las clases debe estar disponible en todo el horario de apertura del gimnasio. | Confiabilidad |
| RNF-07 | Las notificaciones de cancelación de clase deberán ser enviadas por WhatsApp a los clientes en menos de 2 minutos desde la cancelación de la misma. | Rendimiento |
| RNF-08 | El presente de las clases debe ser testeado mediante pruebas E2E para verificar la correcta implementación. | Mantenibilidad |
| RNF-09 | La cantidad de interacciones para acceder a la ficha del socio y planillas de clases debe ser menor a 5. | Usabilidad |

### Una observación sobre los no funcionales 🟡

Al intentar modelar el caso de uso aparece algo que conviene dejar fijado: **los requerimientos no funcionales no generan casos de uso.**

> ⚠️ Esta conclusión salió del razonamiento de los equipos durante la actividad y no fue enunciada como definición de cátedra. Es consistente con todo lo demás y con la práctica estándar, pero conviene confirmarla antes de darla por doctrina en un parcial.

Que el sistema confirme un registro de asistencia en menos de dos segundos no es una funcionalidad: es una **característica de cómo** se ejecuta una funcionalidad que ya existe en otro lado. Rendimiento, usabilidad, confiabilidad y mantenibilidad describen atributos de calidad, no cosas que un actor hace.

El caso que genera duda es RNF-06: *"el presente de las clases debe estar disponible en todo el horario de apertura"*. Probablemente exista un caso de uso de tomar presente o registrar asistencia — pero ese caso de uso sale del funcional correspondiente. El no funcional solo dice en qué ventana horaria tiene que estar disponible. Sigue sin ser un caso de uso.

---

## 5. Cómo se evalúa un requerimiento: tres ejemplos trabajados 🔴

La segunda parte de la consigna pide, para cada requerimiento, indicar si cumple con las condiciones de calidad justificando el caso, y después **reescribirlo cuando corresponda**. Hay una tabla con seis columnas: no ambiguo, consistente, completo, realista, rastreable, verificable.

Van tres ejemplos del método, uno de cada categoría DEO. **El resto del análisis es trabajo tuyo** — acá está el procedimiento, no la solución.

### Ejemplo 1 — Un defecto de punto de vista y de completitud

```
RF-02: El sistema debe permitir al gerente visualizar, para cada
profesor, el porcentaje de clases dictadas con cupo completo en el
mes, a fin de identificar quiénes alcanzan el porcentaje base
definido y corresponden al pago del bono.
```

| Característica | Evaluación | Justificación |
|---|---|---|
| No ambiguo | ⚠️ | "Porcentaje base definido" — ¿definido dónde? No se dice cuál es |
| Consistente | ✅ | No contradice otros requerimientos |
| Completo | ❌ | Falta el valor del porcentaje base, sin el cual no se puede desarrollar |
| Rastreable | ⚠️ | El gerente está nombrado, así que el interés es identificable — pero como el protagonista de la sentencia es el sistema, la responsabilidad queda de costado en vez de explícita |
| Verificable | ⚠️ | Sin el valor umbral no hay procedimiento de comprobación completo |

**Reescritura, resolviendo punto de vista:**

```
El gerente consulta, para cada profesor y por mes, el porcentaje
de clases dictadas con cupo completo.
```

**Nota de criterio:** el *"a fin de identificar quiénes corresponden al pago del bono"* es la **justificación de negocio** del requerimiento, no parte de la funcionalidad. Y si hay un umbral que define quién cobra bono, eso es una **regla de negocio** que merece su propio lugar, no una cláusula subordinada.

### Ejemplo 2 — Un defecto de cohesión

```
RF-13: El sistema debe registrar avisos de ausencia de los socios
y habilitar la recuperación de clase solo a quienes avisaron con
una anticipación de 1 día.
```

Es el caso de la Parte 3. Hay **dos funcionalidades** en una sola sentencia, unidas por una "y": registrar un aviso de ausencia, y habilitar una recuperación. Las hace gente distinta en momentos distintos.

**Por qué importa acá y no es una discusión de estilo:** si lo dejás junto, no podés asignarle **un** actor (el socio avisa; la habilitación la resuelve el sistema según una regla), no podés verificarlo por separado, y cualquier cambio en la política de recuperación te obliga a tocar el requerimiento del aviso.

**Reescritura, separando:**

```
RF-13a: El socio informa su ausencia a una clase en la que está anotado.
RF-13b: El socio recupera una clase perdida cuando informó su ausencia
        con al menos 1 día de anticipación.
```

### Ejemplo 3 — Una omisión

Recorré la lista buscando lo que **no está**.

Hay requerimientos sobre darse de baja de una clase (RF-04), sobre avisar ausencias (RF-13), sobre la lista de espera cuando alguien se da de baja (RF-10), sobre notificar a los que están en lista de espera (RF-14).

**Pregunta:** ¿dónde dice cómo un socio **se anota** a una clase?

En ningún lado. Es el televisor que se enciende y no se apaga, al revés: toda la lista habla de lo que pasa después de la inscripción, y la inscripción nunca se pidió.

Es una **omisión**, y además es un **requerimiento derivado**: lo necesito para que los otros cuatro tengan sentido.

**Al agregarlo, consistencia:** el nuevo requerimiento tiene que respetar lo que ya está — el control de capacidad de RF-09, la vigencia del plan de RF-12, y el mecanismo de lista de espera de RF-10.

### El método, resumido

```
   Para cada requerimiento:

   1. ¿Está escrito desde el punto de vista del actor?  → si no, DEFECTO
   2. ¿Tiene una sola funcionalidad?                    → si no, DEFECTO (cohesión)
   3. ¿Admite una sola interpretación?                  → si no, DEFECTO (ambigüedad)
   4. ¿Tiene todo lo necesario para desarrollarlo?      → si no, DEFECTO (completitud)
   5. ¿Puedo comprobar su cumplimiento?                 → si no, DEFECTO (verificable)
   6. ¿Contradice otro requerimiento?                   → si sí, DEFECTO (consistencia)
   7. ¿Contradice una regla de negocio?                 → si sí, ERROR

   Para el conjunto:

   8. ¿Falta algún requerimiento para que los otros
      tengan sentido?                                   → si sí, OMISIÓN
```

**Sobre la reescritura:** no hay plantilla obligatoria. Se arma como a cada equipo le parezca — poner el requerimiento reescrito al lado del original es una opción razonable. Cada equipo lo va a reescribir distinto, y eso es esperable y deseable: es material para discutir.

> ⚠️ **Frontera.** El análisis de los 24 requerimientos y su reescritura son entrega evaluable. Lo que está acá es el método y tres casos trabajados como muestra. El resto lo hacés vos.

---

## 6. Herramienta: Lucidchart 🟢

El diagrama se pide preferentemente en **Lucidchart** (herramienta web de diagramación colaborativa) por un motivo práctico: permite entrar al documento y hacer observaciones directamente sobre él, en vez de devolver comentarios por separado.

**Un detalle que ahorra tiempo:** en el panel de formas, buscar **"UML"** en la lupita y usar ese conjunto de formas. Trae las figuras y las flechas correctas de la notación, y evita mezclarlas con formatos de otros tipos de diagrama.

> ⚠️ **En esta materia la notación UML se corrige.** Un actor mal dibujado o una relación de inclusión mal representada se penaliza, independientemente de que el contenido esté bien. Usar el set correcto de formas no es cosmética.

---

## 7. Información operativa de la clase 🔴

### Fechas del primer parcial

| Fecha | Qué es | Modalidad |
|---|---|---|
| **1 de octubre** | Parte de **entrevista**, grupal | Presencial |
| **8 de octubre** | Parte **escrita**, individual | Presencial |

**Sobre el 1 de octubre:** hay que agendarlo, reservarlo, cancelar reuniones y pedir el día de estudio si hace falta. Recuperarlo es muy complicado — organizar otra entrevista no es algo que se pueda repetir con facilidad.

El **tema de la entrevista se entrega una semana antes** (jueves 24 de septiembre después de clase, o el viernes), junto con la distribución de roles, para poder prepararlo.

### El trabajo sobre los requerimientos

- No tiene fecha de entrega fija. Se avanza de forma iterativa **sobre el mismo documento del Drive**.
- Conviene avanzar aunque sea parcialmente para la semana siguiente, así hay algo sobre lo cual recibir devolución.
- Se avisa por el foro de consulta o por mensaje que se avanzó, y se recibe feedback sobre eso.
- Las minutas propias de cada equipo reciben corrección por separado.

### TP de investigación

Un trabajo con **más de un mes de plazo**, con nota, complementario a los parciales. Consigna en la carpeta de Drive de cada equipo.

Se investiga un **proyecto de software que fracasó** pese a parecer viable — tenía presupuesto, stakeholders y requerimientos definidos. Tres casos, dos equipos por caso:

- **Aeropuerto de Denver** — contexto atravesado por cambios de gobierno. Es el caso que ya se trabajó en cuatrimestres anteriores, así que hay más material disponible.
- **Sistema de ambulancias de Londres** — contexto de alta sensibilidad, con vidas involucradas.
- **Sistema del FBI** — contexto de secreto y seguridad informática.

**Dos entregables:**

1. **Documento de investigación**, con redacción académica. No es un paper, y explícitamente **no es un raconto histórico**: lo que se pide es **criterio propio**. Dónde empezó el efecto dominó, en qué momento se pudo frenar, qué decisiones se habrían tomado distinto con las herramientas de ingeniería de requisitos vistas en la materia. Si no se tuvo en cuenta a los stakeholders, qué se les podría haber preguntado. Enriquecer con recursos (videos, bibliografía, testimonios) suma.
2. **Recurso didáctico** para presentarlo a la clase. Formato libre y creativo. Se sugieren herramientas de IA (NotebookLM), o Canva o Gamma. Ejemplos de cuatrimestres anteriores: una mesa de decisiones donde la clase elige el camino y se ve a dónde lleva; una comparación con un proyecto equivalente que sí funcionó; una línea de tiempo de decisiones.

> ⚠️ **Tener en cuenta el contexto tecnológico de la época.** Son soluciones desarrolladas cuando la tecnología disponible era otra — en algunos casos, previa a la difusión de los lenguajes orientados a objetos. Juzgar esas decisiones con las herramientas de hoy, sin situarlas, distorsiona el análisis.

Se pueden mandar entregas preliminares o ideas de enfoque para recibir devolución temprana.

### Otros datos 🟡

- La **modalidad de la clase previa al parcial** se define por encuesta en el aula virtual. Dato a considerar: en cuatrimestres anteriores, hacer los casos de uso en papel por primera vez recién en el parcial les cambió bastante el tiempo de resolución a los estudiantes acostumbrados a la herramienta digital.
- Las **mesas de final** se movieron al 29 y 30.
- Las entregas se piden en **Word**, no en PDF, para poder corregirlas sobre el documento.

---

## ✅ Checkpoint — Parte 4

1. ¿Cuál era el objetivo real de la actividad de armar un caso de uso a partir de la minuta de otro equipo? ¿Por qué el caso de uso era solo la excusa?

2. La mayoría de los equipos puso al sistema como actor. Explicá por qué ocurrió y por qué eso ilustra el punto central de la clase.

3. ¿Qué dos salidas válidas hay cuando no podés identificar el actor de una funcionalidad? ¿Cuál es la salida no válida?

4. ¿Qué significa DEO y cuáles son sus tres categorías?

5. Diferenciá defecto de error con un ejemplo de cada uno. ¿Cuál de los dos es más grave y por qué?

6. ¿Qué es una omisión? Explicá qué es un requerimiento derivado y dar un ejemplo.

7. Al agregar un requerimiento omitido, ¿qué precaución hay que tomar y qué problema se evita con ella?

8. ¿Por qué los requerimientos no funcionales no generan casos de uso? Argumentá con un ejemplo de rendimiento.

9. Tomá RF-09 del documento de trabajo y evaluálo contra las seis características de calidad, justificando cada una.

10. Tomá RF-07 y reescribilo desde el punto de vista del actor. Explicá qué decisión tuviste que tomar y qué información te faltó.

11. ¿En qué otro artefacto de la materia vuelve a aplicarse la lista DEO y para verificar qué?

---

## Cierre de la unidad

El hilo de las cuatro partes, en una línea: **la calidad de un artefacto no se mide por sí misma, sino por lo que permite construir encima.**

Un cuestionario con opciones ambiguas produce datos que no se pueden analizar (Parte 1). Una técnica elegida sin criterio produce información que no sirve para decidir (Parte 2). Un requerimiento escrito desde el sistema produce un caso de uso sin actor (Parte 3). Y un documento con defectos, errores y omisiones produce un modelo defectuoso en manos del equipo que lo reciba — aunque ese equipo sepa perfectamente la teoría (Parte 4).

Es la misma idea cuatro veces, en cuatro escalas distintas.

---

**FIN DE LA PARTE 4 — Clase 06**
**FIN DEL APUNTE MAESTRO — Clase 06**
