# 📘 APUNTE MAESTRO — Clase 06
## Parte 3: Calidad de los requerimientos y el punto de vista del actor

**Materia:** Ingeniería de Requisitos · **Unidad:** clase06 · **Parte:** 3 de 4

---

### Qué cubre esta parte

Los requerimientos ya están relevados. Ahora la pregunta es si están **bien escritos**. Acá vienen las características de calidad que un requerimiento tiene que cumplir, de dónde salen, y el defecto de redacción más frecuente de todos: escribirlos desde el punto de vista del sistema en lugar del actor.

Es el bloque más evaluable de la clase.

**Leyenda de marcas:** 🔴 central, altamente evaluable · 🟡 secundario, puede aparecer · 🟢 mencionado al pasar.

---

## 1. El caso: un requerimiento que parece bien y no lo está 🔴

Leé esto y decidí quién tiene que hacer algo:

```
El sistema debe notificar la baja de asistencia a una clase
mediante WhatsApp al profesor asignado a esa clase.
```

Suena perfectamente razonable. Está claro, se entiende, dice qué pasa y por qué canal.

Ahora respondé: **¿quién es el protagonista de esa oración?**

El sistema. El sistema notifica. El sistema es el que hace.

Y ahí está el problema, porque **el sistema no hace nada por sí mismo**. Esa frase está mal escrita, y el motivo no es de estilo: arrastra consecuencias concretas en todo lo que viene después.

Veamos por qué, y después volvemos a arreglarla.

---

## 2. Qué es un sistema (y por qué eso decide todo) 🔴

La definición es la que se viene usando desde el principio de la carrera:

> **Sistema:** conjunto de elementos interrelacionados entre sí para lograr un fin común.

Prestá atención a la última parte. **Un fin común.** ¿De quién es ese fin?

**El sistema en sí mismo no tiene objetivos.** Los objetivos son de quienes interactúan con él, de quienes lo definen, de quienes lo piensan, de quienes lo piden.

Un sistema por sí solo, sin interacción, no hace casi nada. Está ahí. Hace lo que hace porque alguien lo programó o lo diseñó para que lo haga, y lo hace en respuesta a algo:

- **Sistema que interactúa con usuarios:** responde en función del *input* que le da el usuario, o de las funcionalidades que el usuario elige para obtener cierta información y tomar decisiones.
- **Sistema de tiempo real:** tiene un sensor y un actuador. El actuador actúa en función del **contexto**, a partir de lo que el sensor censó. Si el sensor no censa nada, el sistema queda en *stand-by*.

En los dos casos el disparador viene de afuera. Nunca del sistema.

> **Término:** un **sistema de tiempo real** es uno que debe responder a eventos del entorno dentro de un plazo acotado. Se lo nombra acá solo como segundo ejemplo de que el disparo siempre es externo.

### La consecuencia directa

**El sistema no es un actor.**

Es la conclusión que se desprende de la definición, y es la que más cuesta aceptar cuando uno viene leyendo requerimientos donde el sistema aparece haciendo cosas en cada renglón.

El sistema es **la solución**. Los actores son **quienes tienen los objetivos** que esa solución resuelve.

```
   ❌ MAL                              ✅ BIEN

   [Socio]                            [Socio]
      │                                  │
      ▼                                  ▼
   ( El sistema registra            ( Registrar asistencia )
     la asistencia )                     
      ▲                              El socio es el protagonista.
      │                              El sistema es el medio por
   [Sistema]  ← no es actor          el cual lo resuelve.
```

> **📌 Para el parcial, si te preguntan**
> **¿Por qué el sistema no es un actor?**
> Porque un sistema es un conjunto de elementos interrelacionados para lograr un fin común, y ese fin no es propio del sistema: pertenece a quienes lo definen, lo piden y lo usan. El sistema no tiene objetivos ni inicia acciones por sí mismo, sino que responde a un input externo. Los actores son quienes tienen los objetivos que la solución resuelve.

---

## 3. El requerimiento se escribe desde el punto de vista del actor 🔴

De lo anterior sale la regla de redacción:

> **Todo requerimiento se expresa desde el punto de vista del actor. El protagonista es el usuario que resuelve a través del sistema, nunca el sistema.**

```
❌  El sistema debe permitir al socio darse de baja de una clase.
✅  El socio puede darse de baja de una clase.

❌  El sistema debe registrar la limitación física del socio.
✅  El profesor registra la limitación física que presenta un socio.
```

Que el sistema "permita", "controle" o "gestione" se da por descontado: **para eso lo vamos a diseñar y desarrollar.** Escribirlo no agrega información; lo único que hace es correr el foco del que importa.

### Por qué importa tanto (tres consecuencias concretas)

Esto no es una preferencia estética de redacción. Escribir desde el sistema rompe tres cosas río abajo:

**Consecuencia 1 — Se pierde la asignación de responsabilidad.**

Si el requerimiento dice "el sistema debe", después no podés responder estas preguntas:

- ¿A qué actor le interesa esta función?
- ¿A quién se la estoy dando?
- ¿Quién va a tener esa responsabilidad?

Y esas preguntas son exactamente las que necesitás para armar el caso de uso. Sin actor identificado en el requerimiento, el caso de uso queda huérfano.

**Consecuencia 2 — Se rompe la validación.**

Más adelante hay que validar si la solución cumple las **expectativas de calidad** de quienes la pidieron. Eso se hace preguntándole a alguien: *"vos me pediste poder hacer la inscripción de tal manera — ¿esto cumple con lo que esperabas?"*

¿A quién le preguntás eso? Al sistema no. Al **actor que tiene ese interés**. Si el requerimiento nunca dijo de quién era, no sabés a quién ir a buscar.

**Consecuencia 3 — Se rompe la trazabilidad.**

> **Trazabilidad.** En la Parte 1 apareció aplicada a un dato: la posibilidad de reconstruir quién lo produjo. Es la misma idea, ahora aplicada al requerimiento: **la capacidad de seguir su hilo hacia atrás y hacia adelante** — desde que alguien lo pidió hasta que se valida que la solución lo cumple.

Cuando llega el momento de validar con los actores y usuarios que las funcionalidades cumplen sus expectativas, tenés que **volver al momento en que se definieron los requerimientos**. Ese viaje de ida y vuelta es la trazabilidad. Y solo es posible si el requerimiento tiene registrado de quién era el interés.

```
   REQUERIMIENTO              DISEÑO Y            VALIDACIÓN
   (definido por              DESARROLLO          (¿cumple las
    un actor)                                      expectativas?)
        │                         │                     │
        └─────────────────────────┴─────────────────────┘
                     ▲                          │
                     └──── trazabilidad ────────┘
                      (volver al origen para
                       saber a quién preguntarle)
```

> **📌 Para el parcial, si te preguntan**
> **¿Por qué los requerimientos deben expresarse desde el punto de vista del actor?**
> Porque permite asignar la responsabilidad de cada funcionalidad a un actor concreto, lo cual es condición para modelar los casos de uso y, más adelante, para validar con ese actor si la solución cumple sus expectativas de calidad. Escribir "el sistema debe" oculta a quién le interesa la función y rompe la trazabilidad del requerimiento hasta su origen.

---

## 4. El caso difícil: las notificaciones 🔴

Acá es donde la regla se pone incómoda, y conviene tenerlo resuelto porque es la objeción natural.

**La objeción:** hay funcionalidades que el usuario no dispara. "El socio debe ser notificado cuando se vence su plan." Nadie apretó nada. El vencimiento ocurre solo. Ahí el sistema **sí** parece estar disparando la acción.

La respuesta no es una sola: depende de qué tipo de situación sea. Hay dos casos distintos.

### Caso A — La notificación es parte del mismo escenario

Hacés una transacción. Te llega un mail: "su transacción fue exitosa".

Acá **el actor sí disparó todo**. Vos hiciste la transacción, y la notificación es el cierre de ese mismo escenario. El escenario no termina cuando el sistema manda el mail: termina cuando **vos estás notificado**. Y no estás notificado hasta que abrís el mail.

Eso es **asincrónico**: la acción del actor y el efecto que le llega están separados en el tiempo, pero pertenecen al mismo hilo.

> **Término:** **asincrónico** significa que las dos partes de la interacción no ocurren en el mismo momento; el actor sigue con lo suyo y el efecto le llega después.

**Redacción:** desde el actor, porque el actor disparó el escenario.

### Caso B — Un proceso que corre solo

Ahora sí: un proceso en ejecución continua, mirando si se dan ciertas condiciones **temporales** para actuar. Nadie lo dispara desde afuera.

El ejemplo grande son los **procesos batch**: las empresas de servicios emiten lotes de doscientas mil facturas por día. No las emiten una por una cuando alguien aprieta algo; corre un proceso que procesa el lote. Y ese proceso manda notificaciones — a quienes lo controlan si hubo fallas, o la factura digital al usuario para que la pague.

> **Término:** un **proceso batch** (por lotes) procesa un conjunto grande de operaciones de una sola vez, sin intervención humana durante la corrida, típicamente en horarios de baja actividad.

> 🕳️ **Madriguera — el proceso temporal en DFD**
> En el Diagrama de Flujo de Datos, los procesos que se disparan por tiempo y no por un evento externo tienen un tratamiento propio, llamado proceso temporal. Es el mismo fenómeno visto con otra notación.
> *Volvé al camino — acá lo que importa es cómo se modela esto en casos de uso.*

**La solución de modelado:** se modela un **subsistema notificador**.

Es un módulo dentro del propio software, que se fija si se dan las condiciones y actúa. Se lo pone como actor, y es válido, porque —y esta es la clave— **un actor no es necesariamente una persona física**.

**Redacción posible:**

```
El sistema de notificaciones notificará a los socios
el vencimiento de su plan.
```

**Frená acá un segundo, porque esto parece contradecir todo lo de §3.** Vuelve a aparecer un "sistema" como sujeto de la oración, que es justo lo que veníamos persiguiendo.

No es lo mismo. En §3 el problema era usar *el sistema* —la solución entera, el software que estamos por construir— como protagonista. Acá el sujeto es **el sistema de notificaciones**: un componente acotado, con una responsabilidad específica, que en este modelo **es un actor**. La regla no dice "nunca escribas un sistema como sujeto": dice que el sujeto tiene que ser el actor. Cuando el actor es un sistema, escribirlo la cumple.

Y después, cuando armás el escenario, definís **qué precondición se tiene que dar** para que ese subsistema actúe.

### El principio general que queda

> **Un actor no es necesariamente una persona. Los actores pueden ser otros sistemas, o módulos que interactúan con la solución.**

Cuidado con el deslinde, porque acá es fácil confundirse y usar esto como excusa:

| ❌ El sistema como actor | ✅ Un subsistema como actor |
|---|---|
| Poner "Sistema" como actor genérico de cualquier funcionalidad | Modelar un componente acotado con una responsabilidad específica |
| Aparece porque el requerimiento decía "el sistema debe" | Aparece porque hay un proceso que corre sin disparo humano |
| Se come todas las funcionalidades del diagrama | Se limita a las que realmente no tienen actor humano |

El subsistema notificador es una excepción justificada, no la puerta de atrás para volver a poner al sistema como actor.

> **📌 Para el parcial, si te preguntan**
> **Si una notificación no la dispara ningún usuario, ¿quién es el actor?**
> Hay que distinguir dos casos. Si la notificación cierra un escenario que un actor disparó, el actor sigue siendo ese usuario y la notificación es el final asincrónico del mismo escenario. Si en cambio se trata de un proceso en ejecución continua que actúa al darse ciertas condiciones temporales, se modela un subsistema notificador como actor, ya que un actor no es necesariamente una persona física y puede ser otro sistema o módulo.

---

## 5. Actores y roles: la misma persona, varios sombreros 🔴

Un actor **no es una persona**: es un **rol** frente a la solución.

La misma persona física puede tener distintos roles según lo que vaya a hacer en cada momento.

**El caso concreto:** el aula virtual de la facultad. Una docente entra con su usuario y tiene rol **profesor** en las materias que dicta. Si quiere verificar cómo le quedó publicado algo a los alumnos, cambia a rol **estudiante**. Y si además está cursando una diplomatura, en ese curso es **alumna** de verdad, y recibe las mismas notificaciones que reciben sus estudiantes: que hay una tarea nueva, que hay contenido nuevo, que tiene una calificación.

**La plataforma es la misma. El usuario es el mismo. El legajo es el mismo. La contraseña es la misma. Lo que cambia es el rol frente a la solución.**

```
        Persona física: una sola
               │
      ┌────────┴────────┐
      ▼                 ▼
  [Profesor]       [Estudiante]
      │                 │
      └────────┬────────┘
               ▼
     dos actores distintos
        en el modelo
```

**Por qué importa en la práctica:** cuando armás el diagrama, no contás personas, contás roles. Si en el centro de entrenamiento hay un profesor que además es socio y entrena ahí, no es un actor: son dos, porque cuando registra una limitación física de un alumno está actuando como profesor, y cuando se anota a una clase está actuando como socio.

---

## 6. Las características de calidad de un requerimiento 🔴

Todo lo anterior es **una** de las características. Ahora va el conjunto completo.

Estas características no son una invención de la materia: **salen de la normativa**, y vienen de larga data.

- **IEEE 830** — el estándar clásico de especificación de requisitos de software. Es el origen histórico de esta lista.
- **ISO 25010** — más reciente, profundiza el modelo de características de calidad.

> **Término:** **IEEE** e **ISO** son organismos que publican estándares técnicos. Un estándar de este tipo no es ley: es un acuerdo de la industria sobre cómo se hacen bien las cosas, y las organizaciones lo adoptan como referencia.

### Las seis características

| Característica | Pregunta guía | Qué se rompe si falla |
|---|---|---|
| **No ambiguo** | ¿Existe una única interpretación posible? | Dos personas leen lo mismo y construyen cosas distintas |
| **Consistente** | ¿Se contradice consigo mismo o con otros requisitos? | El conjunto es imposible de satisfacer entero |
| **Completo** | ¿Contiene todos los elementos necesarios para comprenderlo y desarrollarlo? | Falta información y hay que inventarla |
| **Realista** | ¿Es alcanzable con los recursos disponibles? | Se compromete algo que no se puede entregar |
| **Rastreable** | ¿Puedo seguirlo hasta su origen y hasta su validación? | No se sabe de quién era ni con quién validarlo |
| **Verificable** | ¿Puedo comprobar su cumplimiento? ¿Existe un procedimiento? | No hay forma de decir si está hecho o no |

Vamos una por una con lo que hay que saber de cada una.

### 6.1 No ambiguo

**Definición:** al leerlo, tiene que haber **un solo entendimiento posible**. Todos los que lo lean tienen que interpretar lo mismo, con la menor diferencia posible.

Este es el criterio que ya trabajamos sin nombrarlo. En la Parte 1, cuando descartamos "muy frecuentemente" como opción de respuesta, estábamos aplicando exactamente esto: una palabra que cada uno interpreta a su manera no sirve. El mecanismo es idéntico, cambia el artefacto.

**La fuente de ambigüedad que ya identificamos:** los adverbios sin métrica — *frecuentemente*, *rápido*, *mucho*. Cada lector les pone su propia vara. En un cuestionario arruinan el dato; en un requerimiento arruinan lo que se va a construir.

### 6.2 Consistente (o coherente)

**Definición:** si tengo un conjunto de requerimientos, **no deben contradecirse entre sí**.

Ojo, porque la consistencia se verifica en dos niveles:

- **Entre requerimientos.** Uno dice que la recuperación de clase se habilita avisando con un día de anticipación; otro dice que se habilita siempre. No pueden convivir.
- **Con las reglas de negocio.** El conjunto tiene que ser coherente con cómo funciona realmente el negocio, no solo internamente.

### 6.3 Completo

**Definición:** contiene **todos los elementos necesarios** para comprenderlo y desarrollarlo.

Se aplica en dos escalas, y conviene no confundirlas:

- **Completitud del requerimiento individual:** *"el sistema controla el tiempo máximo de uso"* — ¿máximo de cuánto? ¿en qué sectores? ¿en qué horario? Falta información para poder construirlo.
- **Completitud del conjunto:** ¿están todos los requerimientos que hacen falta, o falta alguno? Esto lo retomamos en la Parte 4, porque tiene nombre propio.

### 6.4 Realista 🟡

**Definición:** es alcanzable con los recursos que efectivamente hay — tiempo, presupuesto, gente, tecnología.

**Por qué esta característica es distinta de las otras:** las cinco restantes se evalúan con el material del análisis a la vista — el requerimiento, el conjunto al que pertenece, y de dónde salió. Esta no. Para saber si algo es realista hay que conocer **los recursos del proyecto**: cuánto tiempo hay, cuánto presupuesto, qué gente, qué tecnología. Y eso muchas veces no está disponible en el momento del análisis.

Cuando se evalúa un conjunto de requerimientos sin conocer los recursos, es perfectamente válido dejar esta columna sin responder y decir por qué. La evaluación de si algo es realista tiene nombre propio: **análisis de factibilidad**.

### 6.5 Rastreable 🟡

**Definición:** se puede seguir el hilo del requerimiento hacia atrás (¿quién lo pidió? ¿de dónde salió?) y hacia adelante (¿en qué caso de uso se modeló? ¿cómo se valida?).

Es la característica que trabajamos en §3: escribir desde el punto de vista del actor es lo que la hace posible.

### 6.6 Verificable

**Definición:** puedo comprobar su cumplimiento, y **existe un procedimiento** para hacerlo.

La pregunta práctica es: *si alguien me dice que ya está hecho, ¿cómo lo compruebo?* Si no tenés respuesta, el requerimiento no es verificable.

```
❌  El sistema debe ser rápido.
    → ¿cómo lo compruebo? No hay procedimiento posible.

✅  El sistema confirma un registro de asistencia en un tiempo
    no mayor a 2 segundos.
    → cronómetro. Hay procedimiento.
```

Fijate que verificabilidad y no ambigüedad van casi siempre de la mano: lo que no se puede interpretar de una sola manera, tampoco se puede comprobar.

---

## 7. Cohesión y acoplamiento 🔴

Hay una característica más que no está en la tabla de arriba pero que aparece apenas empezás a mirar requerimientos reales.

> **Cohesión:** cada requerimiento que identifiquemos debe corresponder a **una** funcionalidad. Una sola.

**Qué pasa si se viola:**

```
❌ El sistema debe registrar los avisos de ausencia de los socios
   y habilitar la recuperación de clase solo a quienes avisaron
   con una anticipación de 1 día.
```

Ahí hay **dos funcionalidades** metidas en una oración: registrar un aviso de ausencia, y habilitar una recuperación. Son cosas distintas, que las hace gente distinta en momentos distintos.

Cuando mezclo funcionalidades, el resultado son **requerimientos poco cohesivos**, y esos requerimientos casi seguro van a tener **alto acoplamiento**.

> **Acoplamiento:** el grado en que un elemento depende de otros. Alto acoplamiento significa que tocar uno obliga a tocar varios más.

**La regla que se busca es siempre la misma:** alta cohesión, bajo acoplamiento. Cada pieza hace una cosa, y depende lo menos posible de las demás.

**Por qué importa acá y no solo en diseño:** si el requerimiento empaqueta dos funcionalidades, el caso de uso que sale de ahí también las va a empaquetar. Y después no podés asignarle un actor claro, ni verificarlo por separado, ni cambiarlo sin tocar lo otro. El defecto nace en la redacción y se propaga.

> **📌 Para el parcial, si te preguntan**
> **¿Qué significa que un requerimiento sea cohesivo?**
> Que corresponde a una única funcionalidad. Cuando un requerimiento mezcla varias funcionalidades en una misma sentencia resulta poco cohesivo y genera alto acoplamiento, lo que impide asignarle un actor único, verificarlo de forma independiente y modificarlo sin afectar a otras partes.

---

## 8. Volvamos al requerimiento del principio 🔴

Retomemos el de §1:

```
El sistema debe notificar la baja de asistencia a una clase
mediante WhatsApp al profesor asignado a esa clase.
```

Pasémoslo por todo lo que vimos:

| Característica | Diagnóstico |
|---|---|
| Punto de vista | ❌ El protagonista es el sistema |
| No ambiguo | ⚠️ ¿"baja de asistencia" es que el socio se dio de baja, o que hay poca asistencia a la clase? Dos lecturas posibles |
| Completo | ⚠️ ¿En qué plazo? ¿A todos los profesores asignados o a uno? |
| Verificable | ⚠️ Sin plazo, no hay procedimiento de comprobación |
| Cohesión | ✅ Una sola funcionalidad |

**Reescrito**, resolviendo el punto de vista y la ambigüedad:

```
El profesor asignado a una clase recibe por WhatsApp el aviso
de que un socio se dio de baja de esa clase.
```

Ahora el protagonista es el profesor y hay una sola interpretación posible.

**Lo que no se puede arreglar reescribiendo:** el plazo sigue sin estar, y sin plazo el requerimiento no es verificable. Ese dato **no está en el relevamiento** y no se inventa — hay que volver a preguntarlo. Es la diferencia entre un defecto de redacción, que se corrige en el escritorio, y una falta de información, que obliga a volver a la fuente.

**Un detalle sobre el modelado**, para que no se mezcle con lo de §4: quien dispara el escenario es el socio que se da de baja. El aviso al profesor es el cierre asincrónico de ese mismo escenario. No hace falta subsistema notificador acá — ese recurso se reserva para procesos que corren sin disparo humano, como el vencimiento de un plan.

---

## ✅ Checkpoint — Parte 3

1. Dar la definición de sistema y explicar, a partir de ella, por qué el sistema no puede ser un actor.

2. ¿Por qué se dice que un sistema no hace nada por sí solo? Dar los dos casos que se vieron y qué dispara la acción en cada uno.

3. Nombrá las tres consecuencias concretas de escribir un requerimiento desde el punto de vista del sistema en lugar del actor.

4. ¿Qué es la trazabilidad de un requerimiento y qué condición de redacción la hace posible?

5. Un requerimiento dice que hay que notificar al socio el vencimiento de su plan, y nadie dispara esa acción. ¿Cómo se modela? Distinguí este caso del de una notificación que cierra un escenario iniciado por un actor.

6. ¿Un actor es siempre una persona? Justificá y dar un contraejemplo.

7. Una misma persona puede corresponder a varios actores en el mismo modelo. Explicá por qué y dar un ejemplo.

8. Enumerá las seis características de calidad de un requerimiento con su pregunta guía.

9. ¿Por qué la característica "realista" no siempre se puede evaluar leyendo el requerimiento? ¿Cómo se llama el análisis que la aborda?

10. ¿Qué relación hay entre cohesión y acoplamiento? ¿Qué defecto de redacción produce requerimientos poco cohesivos?

11. Escribí un requerimiento no verificable y después reescribilo para que lo sea, explicando qué cambiaste.

---

## Qué viene en la Parte 4

Ya sabemos qué tiene que cumplir un requerimiento. En la Parte 4 viene la herramienta para **encontrar los que no cumplen**: la lista **DEO** — defectos, errores y omisiones. Y el ejercicio de la clase, que es donde todo esto se vuelve tangible: qué pasa cuando le pasás a otro equipo un documento con defectos y le pedís que construya algo encima.

---

**FIN DE LA PARTE 3 — Clase 06**
