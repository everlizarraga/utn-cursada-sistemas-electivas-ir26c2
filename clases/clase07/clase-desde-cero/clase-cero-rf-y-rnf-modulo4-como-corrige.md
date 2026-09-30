# Clase desde cero — RF y RNF — Módulo 4: Cómo se corrige

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Eje:** Centro de Entrenamiento Vida Sana
**Marcas:** 🔴 central · 🟡 secundario · 🟢 al pasar · 🕳️ madriguera · ✏️ tu turno

---

## Sobre este documento

**Qué cubre:** las seis características de calidad de un requisito, con su pregunta guía y qué se rompe si falla · la cohesión como séptima · por qué verificable y completo son propiedades independientes · la lista DEO (defectos, errores, omisiones) y cómo se resuelve cada una · el método de ocho preguntas para evaluar un requisito y un conjunto · el checklist para pasar antes de entregar.

**Qué NO cubre:** producir requisitos (M2, M3). Acá se evalúan los que ya están escritos, que es lo que hace quien corrige, y lo que tenés que hacer vos antes de que corrijan.

## De dónde venís

Del M2 y el M3: sabés la forma de un RF y de un RNF. Este módulo es el filtro por el que pasan antes de darse por escritos.

---

## 1. 🔴 El caso: un requisito que "suena bien"

Leé este, que salió de una entrevista con la Junta y los profesores:

```
El sistema debe notificar la baja de asistencia a una clase
mediante WhatsApp al profesor asignado a esa clase.
```

Suena razonable. Está claro, dice qué pasa y por qué canal. Ahora pasalo por preguntas:

- ¿Quién es el protagonista? El sistema. **Punto de vista** mal.
- ¿"Baja de asistencia" quiere decir que un socio se dio de baja, o que hay poca asistencia a la clase? Dos lecturas. **Ambiguo.**
- ¿En qué plazo se notifica? No dice. **Incompleto.**
- Sin plazo, ¿cómo compruebo que se cumplió? No puedo. **No verificable.**
- ¿Tiene una sola funcionalidad? Sí. **Cohesivo.**

Reescrito, resolviendo lo que se puede resolver en el escritorio:

```
RF:   El profesor asignado a una clase recibe el aviso de que un socio
      se dio de baja de esa clase.
RNF:  El medio del aviso de baja al profesor es WhatsApp.
```

Y lo que **no** se puede arreglar reescribiendo: el plazo sigue sin estar. Ese dato **no está en el relevamiento** y no se inventa: hay que volver a preguntarlo. Esa es la diferencia entre un defecto de redacción, que se corrige en el escritorio, y una **falta de información**, que obliga a volver a la fuente. Tenela presente, porque es la primera decisión que tomás al corregir.

## 2. 🔴 Las seis características

Son el filtro por el que pasa todo requisito, funcional o no funcional, y son casi palabra por palabra el vocabulario con el que se corrige. No son un invento de la materia: vienen de la normativa (el estándar IEEE 830, el clásico de especificación de requisitos, y más recientemente la ISO 25010).

| Característica | Pregunta guía | Qué se rompe si falla |
|---|---|---|
| **No ambiguo** (específico) | ¿Existe una única interpretación posible? | Dos personas leen lo mismo y construyen cosas distintas |
| **Consistente** (coherente) | ¿Se contradice consigo mismo, con otros requisitos o con las reglas de negocio? ¿Está expresado desde el actor correspondiente? | El conjunto no se puede satisfacer entero |
| **Completo** | ¿Contiene todo lo necesario para comprenderlo y desarrollarlo sin adivinar? | Falta información y alguien la inventa |
| **Realista** | ¿Se puede implementar con el tiempo, presupuesto, gente y tecnología del proyecto? | Se compromete algo que no se va a entregar |
| **Rastreable** (trazable) | ¿Puedo seguirlo hasta su origen (quién lo pidió) y hasta su validación (qué caso de uso, qué prueba)? | No se sabe de quién era ni con quién validarlo |
| **Verificable** (testeable / medible) | ¿Puedo comprobar su cumplimiento? ¿Existe un procedimiento? | No hay forma de decir si está hecho |

Una por una, con lo que hay que saber de cada una.

### 2.1 No ambiguo

Al leerlo tiene que haber **un solo entendimiento posible**. La fuente típica de ambigüedad son los adverbios y adjetivos sin métrica: *rápido*, *frecuentemente*, *mucho*, *ágil*. Y las palabras del dominio usadas sin definir: "clase disponible" quería decir tres cosas distintas (con lugar libre, completa, cancelada), y cada una dispara algo distinto. Avisarle "hay lugar" a alguien que ya estaba anotado es un error que nace de esa palabra.

### 2.2 Consistente

No se contradice. Se verifica en **dos niveles**: entre requisitos (uno dice que la recuperación se habilita avisando un día antes; otro dice que siempre: no pueden convivir), y con las reglas de negocio (el conjunto tiene que ser coherente con cómo funciona el negocio de verdad). Y además, **está expresado desde el actor correspondiente**: consistente también significa que se sabe de quién es.

### 2.3 Completo

Tiene **todos los elementos** para comprenderlo y desarrollarlo. En dos escalas que no hay que confundir:

- **Del requisito individual:** *"el sistema controla el tiempo máximo de uso"*. ¿Máximo de cuánto? ¿En qué sectores? ¿En qué horario? Falta información para construirlo.
- **Del conjunto:** ¿están todos los requisitos que hacen falta, o falta alguno? Esto tiene nombre propio y va en §5.

### 2.4 Realista 🟡

Es alcanzable con los recursos que hay. Esta característica es distinta de las otras cinco: las otras se evalúan con el material a la vista; esta exige conocer **los recursos del proyecto**, y eso muchas veces no está disponible en el momento del análisis. Cuando evalúes un conjunto sin conocer los recursos, es válido dejar esta columna sin responder y decir por qué. Su evaluación formal se llama **análisis de factibilidad**.

### 2.5 Rastreable 🟡

Se puede seguir el hilo hacia atrás (¿quién lo pidió? ¿de dónde salió?) y hacia adelante (¿en qué caso de uso quedó? ¿qué prueba lo valida?). Escribir desde el actor es lo que la hace posible: si el requisito no dice de quién es, el hilo se corta en el primer eslabón.

### 2.6 Verificable

Puedo comprobar su cumplimiento y **existe un procedimiento** para hacerlo. La pregunta práctica: *si alguien me dice "ya está", ¿cómo lo compruebo?* Si no tenés respuesta, no es verificable. Para un RF, la comprobación es **ejecutar la función en una cantidad finita de pasos**; para un RNF, **medir el valor o verificar la propiedad**.

```
❌  El sistema debe ser rápido.            → ¿cómo lo compruebo? No hay procedimiento.
✅  El tiempo máximo de confirmación del
    registro de asistencia es de 2 s.      → cronómetro. Hay procedimiento.
```

> **Para el parcial, si te preguntan:** *¿Qué características debe cumplir un requerimiento bien especificado?*
> Debe ser no ambiguo (una única interpretación), consistente (no se contradice y está expresado desde el actor correspondiente), completo (no obliga a adivinar información faltante), realista (implementable con los recursos del proyecto), rastreable (se conoce su origen, solicitante e impactos) y verificable (existe una forma objetiva de comprobar su cumplimiento: pasos finitos para un RF, medición para un RNF).

## 3. 🔴 Cohesión: una funcionalidad por requisito

No está en la tabla de arriba pero aparece apenas empezás a mirar requisitos reales.

> **Cohesión:** cada requisito corresponde a **una** funcionalidad. Una sola.

```
❌  El sistema debe registrar avisos de ausencia de los socios y habilitar
    la recuperación de clase solo a quienes avisaron con 1 día de anticipación.
```

Dos funcionalidades en una oración: registrar un aviso y habilitar una recuperación. Cuando mezclás funcionalidades, el resultado son requisitos poco cohesivos, y esos casi seguro tienen **alto acoplamiento**: tocar uno obliga a tocar otros. La regla es siempre la misma: **alta cohesión, bajo acoplamiento**. Cada pieza hace una cosa y depende lo menos posible de las demás.

Por qué importa acá y no solo en diseño: si el requisito empaqueta dos funcionalidades, el caso de uso que salga de ahí también las va a empaquetar, y después no podés asignarle un actor claro, ni verificarlo por separado, ni cambiar la política de recuperación sin tocar el aviso. El defecto nace en la redacción y se propaga.

> **Para el parcial, si te preguntan:** *¿Qué significa que un requerimiento sea cohesivo?*
> Que corresponde a una única funcionalidad. Un requerimiento que mezcla varias funcionalidades en una misma sentencia es poco cohesivo y genera alto acoplamiento, lo que impide asignarle un actor único, verificarlo de forma independiente y modificarlo sin afectar a otras partes.

## 4. 🔴 Verificable no es lo mismo que completo

Una trampa de examen: *"este requisito es correcto porque podemos probarlo; por lo tanto está completo"*. **Falso.** Son propiedades independientes.

Pensalo con un contraejemplo, como en Discreta: *"El socio inicia sesión con sus credenciales."* ¿Lo puedo probar? Sí: entro con mis credenciales y funciona. ¿Está completo? No: ¿qué credenciales? ¿mail y contraseña? ¿usuario? ¿quién las crea? Tengo muchas preguntas. Lo puedo probar y a la vez me falta información. Verificable y no completo.

Y al revés: un requisito puede tener todos los datos y no ser verificable, porque el atributo no tiene valor ("con buena disponibilidad").

Las seis características se evalúan **una por una, independientes**. Que cumpla una no dice nada de las otras. Y sí hay un par que va casi siempre de la mano: **no ambiguo y verificable**. Lo que no se puede interpretar de una sola manera, tampoco se puede comprobar.

> **Para el parcial, si te preguntan:** *Un requisito verificable, ¿es necesariamente completo?*
> No. Son propiedades independientes. "El socio inicia sesión con sus credenciales" se puede probar (verificable) pero no dice qué credenciales ni quién las crea (incompleto). Cada característica de calidad se evalúa por separado.

## 5. 🔴 La lista DEO: defectos, errores y omisiones

Cuando revisás un conjunto de requisitos, los problemas que encontrás son de **tres naturalezas distintas**, y cada una se resuelve de otra forma. El instrumento se llama **lista DEO**.

```
   ┌──────────────┬────────────────────────────┬─────────────────────────┐
   │  CATEGORÍA   │  QUÉ ES                    │  CÓMO SE RESUELVE       │
   ├──────────────┼────────────────────────────┼─────────────────────────┤
   │  DEFECTO     │  Está, pero NO CUMPLE      │  Se reescribe — o se    │
   │              │  alguna característica     │  vuelve a la fuente si  │
   │              │  de calidad                │  falta un dato          │
   ├──────────────┼────────────────────────────┼─────────────────────────┤
   │  ERROR       │  Está, y dice algo que     │  Se corrige contra la   │
   │              │  NO ES CIERTO              │  regla de negocio       │
   ├──────────────┼────────────────────────────┼─────────────────────────┤
   │  OMISIÓN     │  NO ESTÁ                   │  Se agrega, sin romper  │
   │              │                            │  la consistencia        │
   └──────────────┴────────────────────────────┴─────────────────────────┘
```

### 5.1 Defecto: está mal escrito

El requisito existe y es conceptualmente válido, pero no es claro, conciso o consistente. Incluye no estar escrito desde el actor. Ejemplos: *"el sistema debe…"* (el más frecuente de todos); dos funcionalidades en una; ambigüedad; un plazo o umbral que falta.

Se resuelve **reescribiendo**, y por eso es la categoría más benigna: la información está, solo hay que expresarla bien. **La excepción es la incompletitud:** si el dato que falta nunca se relevó, no lo inventás en el escritorio; volvés a preguntar. Distinguir uno de otro es parte del análisis: *¿esto lo sé y lo escribí mal, o directamente no lo sé?*

### 5.2 Error: dice algo que no es cierto

El requisito está impecablemente escrito y afirma algo que **contradice una regla de negocio**:

```
❌  El socio puede reservar un cupo sin tener el plan pago.
❌  El socio puede recuperar una clase aunque no haya avisado su ausencia.
```

Es la categoría más traicionera: un defecto salta al leerlo, un error **pasa la lectura sin problema**. Hay que conocer el negocio para detectarlo. Si nadie lo hace, sobrevive hasta que el sistema está andando y hace algo que el negocio no permite. Se resuelve volviendo a la regla de negocio real.

### 5.3 Omisión: falta

**Falta un requisito.** La lista está incompleta. El ejemplo del gimnasio: hay requisitos sobre darse de baja de una clase, sobre avisar ausencias, sobre la lista de espera, sobre notificar a los que están en lista, y en ningún lado dice cómo un socio **se anota** a una clase en primer lugar. *"Me dijiste que tengo que poder encender el televisor. No me dijiste que lo tengo que apagar."* Lo que falta muchas veces es el complemento obvio de lo que sí está: obvio para el que lo escribió, invisible para el que lo lee.

Un tipo particular es el **requisito derivado**: lo necesito para que otros tengan sentido (para darse de baja, primero hubo que anotarse). Se resuelve agregando el faltante, **con una precaución**: consistente con lo que ya está. El nuevo "anotarse" tiene que respetar el control de cupo, la vigencia del plan y el mecanismo de lista de espera. Si no, convertiste una omisión en una inconsistencia.

> **Para el parcial, si te preguntan:** *¿Qué es la lista DEO y qué distingue a cada categoría?*
> Es un instrumento de verificación que clasifica los problemas de un producto del análisis en defectos, errores y omisiones. El defecto es un requerimiento mal redactado (no conciso, no consistente, no claro o no escrito desde el actor) y se resuelve reescribiéndolo. El error es un requerimiento que afirma algo que contradice una regla de negocio y se corrige contra ella. La omisión es un requerimiento que falta, y al agregarlo debe mantenerse la consistencia con el conjunto.

## 6. 🔴 El método: ocho preguntas

Todo lo anterior, como procedimiento. Es lo que hace quien corrige; hacelo vos primero.

```
   Para cada requisito:
   1. ¿Está escrito desde el punto de vista del actor?   → si no: DEFECTO (punto de vista)
   2. ¿Tiene una sola funcionalidad?                     → si no: DEFECTO (cohesión)
   3. ¿Admite una sola interpretación?                   → si no: DEFECTO (ambigüedad)
   4. ¿Tiene todo lo necesario para desarrollarlo?       → si no: DEFECTO (completitud)
                                                            ¿lo sé y lo escribí mal, o no lo sé?
   5. ¿Puedo comprobar su cumplimiento?                  → si no: DEFECTO (verificable)
   6. ¿Contradice otro requisito?                        → si sí: DEFECTO (consistencia)
   7. ¿Contradice una regla de negocio?                  → si sí: ERROR

   Para el conjunto:
   8. ¿Falta algún requisito para que los otros tengan
      sentido, o el complemento obvio de alguno?         → si sí: OMISIÓN
```

### Ejemplo trabajado: un defecto de punto de vista y de completitud

```
RF-02: El sistema debe permitir al gerente visualizar, para cada
profesor, el porcentaje de clases dictadas con cupo completo en el
mes, a fin de identificar quiénes alcanzan el porcentaje base
definido y corresponden al pago del bono.
```

| Pregunta | Evaluación | Justificación |
|---|---|---|
| 1. Punto de vista | ❌ | El protagonista es el sistema; el gerente está, pero de costado |
| 2. Cohesión | ✅ | Una sola funcionalidad: consultar un porcentaje |
| 3. No ambiguo | ⚠️ | "Porcentaje base definido": ¿definido dónde? ¿cuál es? |
| 4. Completo | ❌ | Falta el valor del umbral, sin el cual no se puede desarrollar el bono |
| 5. Verificable | ⚠️ | Sin umbral no hay procedimiento completo |
| 6. Consistente | ✅ | No contradice otros |
| 7. Regla de negocio | ✅ | No contradice ninguna |

**Reescritura:**

```
RF:  La Junta Directiva consulta, por profesor y por mes, el porcentaje
     de clases dictadas con cupo completo.
RN:  Un profesor cobra el bono mensual cuando su porcentaje de clases con
     cupo completo alcanza el umbral base.   ← valor del umbral: a relevar
```

El *"a fin de identificar quiénes corresponden al pago del bono"* era la justificación de negocio, y el umbral es una regla de negocio con su propio renglón, cuyo valor no está en el enunciado y hay que preguntar. Fijate cómo un requisito se abrió en un RF limpio, una regla, y una pregunta para la entrevista.

## 7. 🔴 El checklist antes de entregar

Pasalo sobre cada requisito de tu lista, y después sobre la lista entera. Es la versión operativa de todo el módulo.

**Por cada RF:**
- [ ] El sujeto es un rol del negocio (socio, profesor, Junta), no "el sistema".
- [ ] Un solo verbo, en presente indicativo, no hueco (nada de usar, interactuar, gestionar, controlar).
- [ ] El objeto no admite dos lecturas; tiene los datos si hacen falta.
- [ ] No hay "se" impersonal ni voz pasiva.
- [ ] No hay un medio, un valor ni una tecnología colados (van a un RNF).
- [ ] No hay una política colada (va a una regla de negocio).
- [ ] No hay justificación ("a fin de", "para mejorar").
- [ ] Una sola funcionalidad.

**Por cada RNF:**
- [ ] Puedo señalar con el dedo objeto, atributo, valor y unidad (o la propiedad verificable, si no hay unidad).
- [ ] Tiene la condición de medición cuando hace falta (desde qué evento, en qué horario, para qué población).
- [ ] El verbo es "ser".
- [ ] Ni el actor ni el sistema son el sujeto.
- [ ] No contiene "tiempo real", "online", "automáticamente", "rápido", "intuitivo", "seguro" sin valor.
- [ ] El valor es realista, y si lo inventé, está marcado como supuesto.
- [ ] Sé a qué RF restringe, o sé que es transversal.

**Por cada regla de negocio:**
- [ ] Existiría con carpetas y resaltadores.
- [ ] No está disfrazada de RF ("el socio debe avisar el día anterior").

**Por el conjunto:**
- [ ] Ningún par se contradice.
- [ ] Ninguno contradice una regla de negocio (error).
- [ ] Cada RF tiene al menos un RNF, o está declarado que no lo necesita.
- [ ] Están los complementos obvios (anotarse / darse de baja, alta / baja, encender / apagar) y los derivados.
- [ ] Anoté aparte lo que **no sé** y tengo que preguntar, en vez de inventarlo.

---

## ✏️ Tu turno

Evaluá estos tres con las ocho preguntas de §6, en una tabla como la del ejemplo. Clasificá cada problema como defecto, error u omisión, y reescribí cuando corresponda. Si algo falta y no está en el enunciado, anotalo como pregunta, no lo inventes.

1. "El sistema debe controlar el tiempo mínimo (30 min) y máximo (120 min) de uso en los sectores sin profesor, dentro del horario de 8 a 20 hs de lunes a sábados."
2. "El socio puede anotarse en una clase aunque tenga la cuota impaga, siempre que la pague antes de la clase."
3. Recorré esta lista y decí qué falta: *el socio se anota en una clase · el socio se da de baja de una clase · el socio informa su ausencia · el socio se anota en lista de espera · el socio recupera una clase perdida.*

Pista para el 2, sin respuesta: está muy bien escrito. Ese es justamente el problema.

## ✅ Checkpoint

1. Nombrá las seis características con su pregunta guía.
2. ¿Por qué "realista" se evalúa distinto que las otras cinco?
3. ¿En qué dos niveles se verifica la consistencia?
4. ¿Cuáles son las dos escalas de la completitud?
5. ¿Qué es la cohesión y qué se propaga si se viola?
6. Dá un contraejemplo que muestre que verificable no implica completo.
7. ¿Qué diferencia un defecto de un error? ¿Cuál es más difícil de detectar y por qué?
8. ¿Qué es un requisito derivado? Dá el del gimnasio.
9. Al agregar un requisito que faltaba, ¿qué precaución hay que tomar?
10. Cuando un requisito es incompleto, ¿cuándo se reescribe y cuándo se vuelve a la fuente?

## Qué viene en el Módulo 5

Ya tenés todo el equipamiento: clasificar (M1), escribir RF (M2), escribir RNF (M3), corregir (M4). El módulo 5 es la aplicación completa sobre el enunciado del gimnasio, **párrafo por párrafo**: de cada uno, qué RF, qué RNF, qué regla de negocio, qué se pregunta en la entrevista, y qué no sale de ahí aunque parezca. Es el tramo más largo y el que más rinde. Leelo dos veces: la segunda, tapando la solución.

**FIN DEL MÓDULO 4**
