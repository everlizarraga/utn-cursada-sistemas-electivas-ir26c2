# Clase desde cero — RF y RNF — Módulo 2: El requerimiento funcional

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Eje:** Centro de Entrenamiento Vida Sana
**Marcas:** 🔴 central · 🟡 secundario · 🟢 al pasar · 🕳️ madriguera · ✏️ tu turno

---

## Sobre este documento

**Qué cubre:** la anatomía de un RF (rol + verbo + objeto, y los datos cuando hacen falta) · por qué el sujeto es el actor y no el sistema · el tiempo verbal · los dos niveles de redacción · las nueve trampas que aparecen en los primeros intentos, cada una con su ❌/✅ del gimnasio · un método de cinco pasos para pasar de una frase del enunciado a un RF.

**Qué NO cubre:** el RNF (M3), ni cómo evaluar si un RF ya escrito cumple las características de calidad (M4). Acá aprendés a **producir** RF bien formados; corregirlos es el paso siguiente.

## De dónde venís

Del M1: sabés que el sistema no es actor, que un actor es un rol, que los actores del gimnasio son socio, profesor y Junta Directiva, y sabés separar RF, RNF y regla de negocio con el test de tres preguntas. Acá se asume todo eso.

---

## 1. 🔴 El caso: dos frases que se caen con tres preguntas

Un equipo, cinco minutos después de terminar la entrevista con los profesores, escribió esto:

```
RF: Agilizar el registro de asistencias.
```

Y lo tachó casi enseguida. ¿Por qué? Hacéle tres preguntas: **¿agilizar cuánto? ¿quién lo registra? ¿cómo sé si lo logré?** No sobrevive a ninguna. *Agilizar* no se puede verificar; no hay actor; no hay objeto preciso. Suena a objetivo de negocio, y lo es, pero no es un requisito.

Segundo intento del mismo equipo:

```
RF: El sistema registrará el ingreso de socios.
```

Mejor. Tiene verbo, tiene objeto. Tres preguntas otra vez: **¿quién registra? ¿el socio se registra solo, o lo registra el profesor? ¿de quién es esta función?** Y ahí se cae, más despacio pero se cae. "El sistema" como sujeto **esconde al actor**, y sin actor no sabés de quién es el caso de uso que va a salir de acá, ni a quién preguntarle después si la solución cumple lo que esperaba.

Y en la misma mesa alguien dijo: *"el registro de asistencia tiene que tardar poco"*. ¿Cuánto es poco? Nadie sabía. Eso no es un RF, es un RNF mal armado, y se resuelve en M3. Por ahora, guardalo.

Lo que quedó escrito, después de discutirlo:

```
✅ El socio registra su ingreso al establecimiento.
```

Actor, verbo, objeto. Sobrevive a las tres preguntas. Ahora vamos a ver por qué esa forma, pieza por pieza.

## 2. 🔴 Anatomía del RF: rol + verbo + objeto

### 2.1 Las piezas

```
   El socio        registra        su ingreso al establecimiento
   └───┬───┘       └───┬────┘      └─────────────┬─────────────┘
      ROL            VERBO                    OBJETO
   quién lo        qué acción              sobre qué recae
   quiere lograr   (en presente)            la acción
```

**Rol.** El actor que quiere lograr esto. Siempre uno de los roles del negocio (socio, profesor, Junta Directiva). Es lo que vuelve al requisito **consistente desde el punto de vista del actor**, y lo que después va a decir de quién es el caso de uso.

**Verbo.** La acción, **en presente del indicativo, afirmativo**: registra, avisa, consulta, paga, se anota. Un solo verbo por requisito.

**Objeto.** Sobre qué recae la acción, con la precisión suficiente para que no haya dos lecturas: no "su ingreso" a secas si puede confundirse con el ingreso a una clase; "su ingreso al establecimiento".

**Datos (cuando hacen falta).** Los parámetros que entran, para que el requisito sea testeable: *el profesor registra un socio con su DNI, apellido, nombre, teléfono, email, fecha de ingreso y plan*. Eso vuelve el requisito completo: sabés exactamente qué tiene que aceptar el sistema.

### 2.2 Por qué el sujeto es el rol y no el sistema

No es una preferencia de estilo. Escribir "el sistema debe…" rompe tres cosas río abajo:

1. **Se pierde la responsabilidad.** No podés responder: ¿a qué actor le interesa esta función? ¿a quién se la doy? Y esas preguntas son justo las que necesitás para armar el caso de uso. Sin actor, el caso de uso queda huérfano.
2. **Se rompe la validación.** Al final del proyecto vas a preguntarle a alguien "¿esto cumple lo que esperabas?". ¿A quién? Al sistema no. Al actor. Si el requisito no dice de quién es, no sabés a quién ir a buscar.
3. **Se rompe la trazabilidad.** Es la capacidad de seguir el hilo del requisito hacia atrás (quién lo pidió) y hacia adelante (en qué caso de uso quedó, cómo se validó). Sin actor registrado, el hilo se corta en el primer eslabón.

Además, que el sistema "permita", "controle" o "gestione" **se da por descontado**: para eso lo vas a construir. Escribirlo no agrega información; solo corre el foco de quien importa.

```
❌  El sistema debe permitir al socio darse de baja de una clase.
✅  El socio se da de baja de una clase.

❌  El sistema debe registrar la limitación física del socio.
✅  El profesor registra la limitación física que presenta un socio.
```

Mirá el segundo par. Al obligarte a poner el rol, apareció una decisión que "el sistema" escondía: **¿quién registra la limitación, el profesor o el socio mismo?** Son dos requisitos distintos, de dos actores. Eso es lo que hace la forma: te obliga a decidir lo que hay que decidir.

> **Para el parcial, si te preguntan:** *¿Por qué los requerimientos deben expresarse desde el punto de vista del actor?*
> Porque permite asignar la responsabilidad de cada funcionalidad a un actor concreto, lo cual es condición para modelar los casos de uso y, más adelante, para validar con ese actor si la solución cumple sus expectativas. Escribir "el sistema debe" oculta a quién le interesa la función y rompe la trazabilidad del requerimiento hasta su origen.

### 2.3 El tiempo verbal

**Presente del indicativo, afirmativo:** *el socio se anota*, *el profesor consulta*. Con presente no hay margen de error: rol, verbo, objeto, y nada más.

⚠️ **Atención.** Vas a encontrar en material escrito de la materia formas en futuro (*registrará*) y con "poder" (*podrá registrar*, *debe poder consultar*). Están aceptadas: no son defecto. Pero el futuro abre la puerta a la voz pasiva (*deberá ser validado*) y a formas impersonales que después sí se corrigen. **Para el parcial:** usá presente indicativo afirmativo; si te sale "podrá", no está mal, pero no lo necesitás.

Lo que **no** va: "deberá", "debe" y "tendrá que" cuando el sujeto es el sistema (*el sistema deberá…*), porque arrastran al sistema como protagonista. "Debe" con el actor como sujeto (*el socio debe avisar…*) tiene otro problema: suena a obligación del socio, y eso normalmente es una **regla de negocio**, no un RF. Fijate: *el socio debe avisar el día anterior* es una regla; *el socio avisa su ausencia* es el RF.

## 3. 🔴 Dos niveles de redacción

Un mismo requisito se puede escribir en dos niveles, y los dos son válidos para cosas distintas.

**Nivel alto: definición de capacidad.** Estructura: **verbo en infinitivo + objeto**.

```
Registrar socio.
Avisar ausencia.
Consultar socios que no están al día.
```

Es la forma más abstracta. Nombra la capacidad sin decir quién ni con qué datos. Y tiene una particularidad que vas a usar en M6: **es el nombre del caso de uso**.

**Nivel detallado: especificación.** Estructura: **rol + verbo + objeto + datos**.

```
El profesor registra un socio con su DNI, apellido, nombre, teléfono,
email, fecha de ingreso y plan contratado.
```

Es el nivel que vuelve al requisito testeable y consistente desde el actor.

### 3.1 El nivel alto resuelve una discusión típica

Cuando un equipo quiso escribir el requisito de socio con limitación física, apareció la duda: ¿queremos que el **profesor** registre al socio con limitación, o que el **socio** se autoregistre? Parecía que había que elegir.

No hay que elegir todavía. A nivel alto, **"Registrar socio con limitación física"** cubre las dos: la capacidad existe sin importar quién la ejecute. Después, a nivel detallado, sí aparece el rol, y un requisito de nivel alto puede abrirse en varios, uno por rol:

```
Nivel alto:      Registrar limitación física.
Nivel detallado: El profesor registra la limitación física que presenta un socio.
                 El socio registra su propia limitación física al contratar el plan.
```

Los dos detallados pueden convivir. Cuál va y cuál no, lo decide el negocio (o la entrevista), no vos en el escritorio.

> **Para el parcial, si te preguntan:** *¿Cómo se redacta un requerimiento funcional?*
> A nivel alto, con verbo en infinitivo + objeto ("Registrar socio"), que define la capacidad y es el nombre del caso de uso. A nivel detallado, con rol + verbo + objeto más los datos de entrada ("El profesor registra un socio con su DNI, apellido, nombre…"), en presente indicativo, que lo vuelve testeable y consistente desde el actor.

> 🕳️ **Madriguera — historias de usuario**
> "Como [rol], quiero [acción] para [beneficio]" es otra plantilla para escribir lo mismo, muy usada en metodologías ágiles. Se menciona como alternativa; no es la forma que se pide en esta materia.
> *Volvé al camino: rol + verbo + objeto.*

## 4. 🔴 Las nueve trampas

Estas son las que aparecen en casi todos los primeros intentos. Cada una viene con el ❌ tal como se escribe y el ✅ como queda, siempre del gimnasio. Aprendé a reconocerlas porque **son exactamente lo que se corrige**.

### Trampa 1 — El sistema como sujeto

```
❌  El sistema debe organizar el uso de las instalaciones diferenciando entre
    clases con profesor y sectores de uso libre.
```

Además de esconder al actor, "organizar" no es una acción que nadie quiera lograr: es una descripción de lo que el sistema hace por dentro. Preguntate: **¿quién quiere lograr qué, con esto?** El socio quiere anotarse en un turno de un sector libre; el profesor quiere ver qué sector está en uso.

```
✅  El socio reserva un turno en un sector de uso libre.
✅  El profesor consulta la ocupación de los sectores en un turno.
```

De un "el sistema organiza" salieron dos RF de dos actores. Pasa siempre.

### Trampa 2 — "Se" impersonal

```
❌  Se necesita registrar quién pagó, cuánto y qué.
```

"Se necesita" → **¿quién?** El "se" borra al actor. Y "registrar quién pagó" → **¿quién registra?** Si hoy lo anotan los profesores y quieren dejar de hacerlo, ¿es el socio al pagar? ¿la Junta al controlar la caja?

```
✅  El socio paga su plan.
✅  La Junta Directiva consulta los pagos realizados por socio.
```

### Trampa 3 — Voz pasiva

```
❌  Los socios en lista de espera serán notificados cuando se libere un cupo.
```

Voz pasiva es sujeto tácito: no sé quién notifica, y "cuando se libere" tiene otro "se". Dado vuelta:

```
✅  El socio en lista de espera recibe el aviso de un cupo liberado en la clase.
```

Fijate que el actor del RF es **el que recibe**: es el socio quien tiene el objetivo (enterarse). No hace falta un "sistema que notifica".

### Trampa 4 — Objeto suelto, sin verbo

```
❌  Ficha del socio.
❌  Plataforma de pago.
```

Un sustantivo no es un requisito. ¿Qué pasa con la ficha? ¿Se consulta? ¿Se imprime? ¿Se edita? Poné el verbo y el rol, y vas a descubrir que muchas veces era un RNF disfrazado (el segundo lo retomamos en M3).

```
✅  El profesor consulta la ficha de un socio.
```

### Trampa 5 — Componente disfrazado de función

```
❌  El socio tendrá una credencial para poder ingresar.
```

Tiene rol, tiene verbo. Pero "tener una credencial" no es algo que el socio **haga**: es una condición sobre **cómo** ingresa. Es un RNF sobre el medio de acceso, y su forma correcta te la debo hasta M3 §4. Por ahora: **si el verbo es "tener" o "contar con" seguido de una cosa, sospechá**.

### Trampa 6 — Verbo hueco

```
❌  El socio interactúa con la app.
❌  El profesor usa el sistema para gestionar sus clases.
```

*Interactuar*, *usar*, *gestionar*, *controlar*, *manejar*: no describen ninguna acción concreta. Preguntate **¿para lograr qué?** Interactuar con la app no es un objetivo; anotarse a una clase sí.

```
✅  El socio se anota en una clase.
✅  El profesor registra el presente de los socios de su clase.
```

### Trampa 7 — Dos funcionalidades en una

```
❌  El sistema debe registrar avisos de ausencia de los socios y habilitar la
    recuperación de clase solo a quienes avisaron con una anticipación de 1 día.
```

Hay una "y" y dos cosas distintas: avisar una ausencia y recuperar una clase. Las hace el mismo actor pero en momentos distintos, y la segunda depende de una regla. Un requisito, una funcionalidad. A esto se lo llama **cohesión**, y se retoma en M4.

```
✅  El socio informa su ausencia a una clase en la que está anotado.
✅  El socio recupera una clase perdida.
    (regla de negocio, aparte: solo puede recuperarla si informó la ausencia
     con al menos 1 día de anticipación)
```

### Trampa 8 — El "cómo" colado en el "qué"

```
❌  El socio se da de baja de una clase desde la app.
❌  El profesor recibe por WhatsApp el aviso de que un socio se dio de baja.
```

"Desde la app" y "por WhatsApp" son **medios**: restricciones sobre cómo. Se sacan del RF y se escriben aparte como RNF (M3). El RF queda independiente de la tecnología, que es una de sus propiedades.

```
✅  El socio se da de baja de una clase.
✅  El profesor recibe el aviso de que un socio se dio de baja de su clase.
    (RNF aparte: el medio del aviso es WhatsApp)
```

### Trampa 9 — La justificación colada

```
❌  La Junta Directiva consulta el porcentaje de clases con cupo completo por
    profesor, a fin de identificar quiénes corresponden al pago del bono.
```

"A fin de identificar…" es **por qué** existe el requisito, no parte de la funcionalidad. Se saca. Y si hay un umbral que define quién cobra bono, eso es una **regla de negocio** que merece su propio renglón.

```
✅  La Junta Directiva consulta, por profesor y por mes, el porcentaje de
    clases dictadas con cupo completo.
```

### Las nueve, en una tabla para tener a mano

| # | Trampa | Cómo la reconocés | Qué hacés |
|---|---|---|---|
| 1 | El sistema como sujeto | "El sistema debe/permite/gestiona…" | Preguntá ¿quién quiere lograr qué? y poné ese rol |
| 2 | "Se" impersonal | "Se necesita", "se registra" | Preguntá ¿quién? |
| 3 | Voz pasiva | "serán notificados", "será validado" | Dá vuelta la oración: el que recibe o el que hace, como sujeto |
| 4 | Objeto suelto | Un sustantivo sin verbo | Poné rol y verbo; puede ser RNF |
| 5 | Componente como función | "tendrá / contará con [cosa]" | Es RNF sobre un componente (M3) |
| 6 | Verbo hueco | interactuar, usar, gestionar, controlar | Preguntá ¿para lograr qué? |
| 7 | Dos en una | Una "y" entre dos acciones | Separá en dos RF |
| 8 | El cómo colado | "desde la app", "por WhatsApp", "en 2 segundos" | Sacalo a un RNF |
| 9 | Justificación colada | "a fin de", "para mejorar", "porque" | Sacalo; si hay una política, es regla de negocio |

## 5. 🔴 El método: de una frase del enunciado a un RF

Ahora todo junto, como procedimiento. Lo vas a aplicar párrafo por párrafo en M5.

```
   Paso 1 — ¿Quién quiere lograr qué?
            Leé la frase y buscá el objetivo de un actor.
            Si no hay actor con un objetivo, no es RF (volvé al test del M1).

   Paso 2 — Rol
            Nombrá al actor con el rol del negocio: socio, profesor, Junta Directiva.
            Si hay dos posibles, son dos RF.

   Paso 3 — Verbo
            Un solo verbo, en presente indicativo, que describa la acción.
            Sin huecos (usar, interactuar, gestionar). Sin "el sistema".

   Paso 4 — Objeto
            Sobre qué recae, con la precisión que evite dos lecturas.
            Agregá los datos si el requisito los necesita para ser testeable.

   Paso 5 — Limpieza
            ¿Quedó un medio o un valor adentro? → afuera, es RNF.
            ¿Quedó una política adentro?         → afuera, es regla de negocio.
            ¿Quedó una justificación?            → afuera, es contexto.
            ¿Quedaron dos verbos?                → dos RF.
```

### Ejemplo resuelto completo

Frase del enunciado:

> *"cuando las inscripciones a una clase están completas, pueden anotarse socios en lista de espera. Si un socio inscripto se baja de la clase, los profesores llaman al primer socio inscrito en la lista de espera para ofrecerle el lugar, y así sucesivamente hasta completar la clase."*

**Paso 1 — ¿Quién quiere lograr qué?** Hay dos objetivos: el socio quiere quedar en lista de espera cuando la clase está llena; y el socio en lista quiere enterarse cuando se libera un lugar (hoy lo llama el profesor; los profesores quieren dejar de hacerlo).

**Paso 2 — Rol.** Socio, en los dos. El profesor aparece como quien *hoy* llama, pero no es su objetivo: es su carga.

**Paso 3 — Verbo.** *Se anota* (en lista de espera) y *recibe* (el ofrecimiento). Presente, uno por requisito.

**Paso 4 — Objeto.** "la lista de espera de una clase completa" y "el ofrecimiento del lugar liberado en la clase".

**Paso 5 — Limpieza.** "cuando las inscripciones están completas" es la condición para que exista la lista: regla de negocio. "al primer socio inscrito… y así sucesivamente" es el orden de ofrecimiento: regla de negocio. Nada de medios ni valores todavía (¿en cuánto tiempo recibe el ofrecimiento? Eso sería un RNF, y el enunciado no lo dice: hay que preguntarlo).

**Resultado:**

```
RF-a  El socio se anota en la lista de espera de una clase completa.
RF-b  El socio en lista de espera recibe el ofrecimiento del lugar liberado en la clase.

RN-1  Solo puede haber lista de espera cuando la clase está completa.
RN-2  El lugar liberado se ofrece por orden de inscripción en la lista de espera.

Pendiente de relevar (RNF): ¿en cuánto tiempo, desde la baja, recibe el
ofrecimiento el primero de la lista? ¿por qué medio?
```

Un párrafo de cuatro renglones dio dos RF, dos reglas y dos preguntas para la entrevista. Eso es lo normal. Si de un párrafo te sale un solo RF gigante, probablemente cayó en la trampa 7.

### 5.1 🟡 Cuando el actor es un subsistema

Un caso especial del Paso 2. Si el objetivo se dispara **por tiempo, sin que nadie haga nada** (el vencimiento del plan a los 30 días), el actor es un subsistema:

```
✅  El subsistema notificador avisa al socio el vencimiento de su plan.
```

Acá vuelve a aparecer un "sistema" como sujeto y **no es la trampa 1**: es un componente acotado con una responsabilidad específica que dispara por sí mismo, y en el modelo es un actor. La regla no dice "nunca un sistema como sujeto": dice "el sujeto es el actor". Cuando el actor es un subsistema, escribirlo la cumple. Usalo solo cuando de verdad no hay disparo humano; si el socio se da de baja y el profesor recibe el aviso, el actor es el socio y no hace falta subsistema.

---

## ✏️ Tu turno

Reescribí estos seis como RF bien formados, aplicando el método de §5. Si de uno salen dos, escribí dos. Si algo sobra (medio, valor, regla, justificación), anotalo aparte con su etiqueta. Sin mirar §4.

1. "El sistema debe controlar la capacidad máxima de cada clase/sector según el tipo (8 pilates, 7 cardio, 5 musculación, 8 yoga/funcional/stretching)."
2. "Los profesores deben poder emitir comunicaciones (avisos, cupos, plantillas) por WhatsApp a los socios desde el sistema."
3. "Los profesores deben ser alertados cuando se excede el tiempo límite de uso de las instalaciones."
4. "El sistema debe gestionar los planes mensuales de los socios (4, 6, 8 o 12 clases), controlando su vigencia desde la primera clase hasta la misma fecha del mes siguiente."
5. "El sistema debe alertar a los profesores cuando una clase tenga menos de 3 socios anotados, para ofrecerles cambiar de turno."
6. "El socio podrá registrar sus asistencias al momento de ingresar al establecimiento."

Pista para el 6, sin respuesta: ya está casi bien. Preguntate solo si "al momento de ingresar" es parte del qué o es un cómo.

## ✅ Checkpoint

1. ¿Cuáles son las tres piezas de un RF y qué aporta cada una?
2. ¿Qué tres cosas se rompen río abajo cuando el sujeto es "el sistema"?
3. ¿Qué diferencia hay entre el nivel alto y el nivel detallado? ¿Para qué sirve cada uno?
4. "Registrar limitación física" a nivel alto: ¿cuántos RF de nivel detallado pueden salir de ahí? ¿Quién decide cuáles van?
5. ¿Por qué "el socio interactúa con la app" no es un RF, aunque tenga rol y verbo?
6. ¿Qué tiempo verbal usás en un RF y por qué el futuro trae problemas?
7. "El socio debe avisar su ausencia el día anterior": ¿es RF o regla de negocio? ¿Cómo lo separás en dos cosas?
8. ¿Cuándo es correcto que un "sistema" aparezca como sujeto de un RF?
9. Del párrafo de la lista de espera salieron dos RF. ¿Por qué no uno solo?

## Qué viene en el Módulo 3

Ya tenés RF con actor, verbo y objeto. Pero en cada uno quedó algo afuera: "por WhatsApp", "en 2 segundos", "con una credencial", "el registro tiene que tardar poco". Todo eso es **cómo**, y tiene su propia forma: objeto + atributo + valor + unidad, con el verbo "ser" y **sin actor**. En M3 vas a ver esa forma, qué hacer cuando no hay unidad (la credencial, el canal), cómo se escribe un RNF sobre un componente, de dónde salen los atributos, y las tres palabras que suenan técnicas y no miden nada.

**FIN DEL MÓDULO 2**
