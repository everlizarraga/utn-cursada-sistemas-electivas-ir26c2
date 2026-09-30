# Clase desde cero — RF y RNF — Módulo 1: Antes de escribir

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Eje:** Centro de Entrenamiento Vida Sana
**Marcas:** 🔴 central · 🟡 secundario · 🟢 al pasar · 🕳️ madriguera · ✏️ tu turno

---

## Sobre este documento

**Qué cubre:** el negocio del gimnasio en una página, para tenerlo presente · qué es un sistema y dónde termina · quién es actor y quién no lo es (el sistema no, sus componentes tampoco, una persona puede ser dos actores) · las tres cosas distintas que salen de un enunciado —RF, RNF y regla de negocio— y un test de tres preguntas para distinguirlas.

**Qué NO cubre:** cómo se escribe cada una. Eso es M2 (RF) y M3 (RNF). Acá solo aprendés a **clasificar**, que es la mitad del trabajo y la mitad que casi nadie hace.

## De dónde venís

Se asume que sabés qué es un caso de uso y cómo se dibuja un actor en UML (es contenido de las primeras clases de la materia). No se asume nada sobre requisitos: si te suena todo, mejor; si no te suena nada, también sirve.

---

## 1. 🔴 El negocio, en una página

Antes de tocar teoría, tené el negocio en la cabeza. Todo lo que sigue sale de acá.

**Vida Sana** es un centro de entrenamiento. Tiene:

- **10 profesores**, que dan clases de pilates, funcional, stretching y yoga.
- **Dos sectores sin profesor:** cardio (5 bicicletas fijas y 2 cintas) y musculación.
- **Una Junta Directiva:** los dueños. Son quienes pidieron el sistema.
- **Socios**, que contratan planes de 4, 6, 8 o 12 clases por mes.

Y tiene reglas: cada clase tiene un cupo (8 reformers en pilates, 7 en cardio, 5 en musculación, 8 en yoga/funcional/stretching); si una clase tiene menos de 3 anotados, se llama a los que están para ofrecerles otro turno; si está llena, hay lista de espera; el socio tiene que avisar su ausencia el día anterior, y solo quien avisó puede recuperar la clase.

Y tiene **dolor**: los profesores llevan cuatro registros en papel (ficha por socio, caja diaria, ficha que lleva cada socio, planilla de clases con resaltadores), se olvidan de anotar, hay roces entre ellos y con los dueños, y los socios discuten los pagos. Los profesores quieren desentenderse de todo registro. Los socios quieren avisar ausencias hasta una hora antes. Los profesores quieren que, si se libera un lugar, la lista de espera se entere. Y los dueños no quieren contratar a nadie más.

Con eso en la cabeza, leé esta frase, que es del tipo de cosas que uno escribe cinco minutos después de leer el enunciado:

```
El sistema debe registrar la asistencia de los socios a las clases.
```

Suena perfecta. Está clara. Dice qué pasa. Ahora respondé, en serio, antes de seguir: **¿quién es el protagonista de esa oración?**

El sistema. El sistema registra.

Guardá esa respuesta. Al final de este módulo vas a saber por qué eso es un problema, y en M2 vas a saber cómo se arregla.

## 2. 🔴 Qué es un sistema, y dónde termina

La definición es la de toda la carrera:

> **Sistema:** conjunto de elementos interrelacionados entre sí para lograr un fin común.

Dos cosas salen de ahí, y las dos deciden cómo escribís requisitos.

### 2.1 El sistema no tiene objetivos propios

Fijate la última parte de la definición: *un fin común*. ¿De quién es ese fin? **No del sistema.** El sistema no quiere nada. Los objetivos son de quienes lo piden, lo usan y lo definen. Un sistema solo, sin nadie que interactúe, no hace casi nada: está ahí. Hace lo que hace porque alguien lo diseñó para responder a algo que viene de afuera:

- Si es un sistema que interactúa con personas, responde a lo que la persona hace o pide.
- Si es un sistema con sensores, responde a lo que el sensor midió.

En los dos casos el disparo viene de afuera. **Nunca del sistema.** Esto es lo que va a hacer caer la frase de §1, pero todavía no: falta un concepto.

### 2.2 El sistema es software + hardware, y tiene un límite

El software que vas a especificar **no funciona solo**. Corre sobre algo: un celular, una computadora, un lector de credenciales, una pantalla, una balanza. Todo eso, junto con el software, es *el sistema*. Cuando escribas un requisito tenés que saber qué está adentro del límite y qué está afuera.

En el gimnasio:

```
              ┌──────────────── SISTEMA ────────────────┐
              │                                          │
  [Socio] ────┤  app / web    lector de     pantalla     ├──── [Profesor]
              │  del socio    credencial    del mostrador│
              │                                          │
              │  software de gestión de clases, planes,  │
              │  asistencias, pagos, lista de espera     │
              │                                          │
              └──────────────────────────────────────────┘
                                   ▲
                             [Junta Directiva]
```

Adentro del límite: el software y los dispositivos por los que se usa (si el ingreso es con credencial, el lector es parte del sistema). Afuera: las personas, con sus roles. La credencial física del socio está en el borde: es un medio de acceso, y vas a ver en M3 que eso se especifica de una forma particular.

**Por qué esto importa ya:** porque una de las confusiones más comunes es tratar como "función" algo que en realidad es **un componente del sistema**. "Tiene que tener un lector de credenciales" no es algo que un socio haga: es una pieza. Dejá esa idea marcada; se resuelve en M3.

> **Para el parcial, si te preguntan:** *¿Por qué el sistema no es un actor?*
> Porque un sistema es un conjunto de elementos interrelacionados para lograr un fin común, y ese fin no es propio del sistema: pertenece a quienes lo definen, lo piden y lo usan. El sistema no tiene objetivos ni inicia acciones por sí mismo; responde a un disparo externo. Los actores son quienes tienen los objetivos que la solución resuelve.

## 3. 🔴 Quién es actor y quién no

### 3.1 Actor = rol, no persona

Un actor no es una persona: es **un rol frente al sistema**. La misma persona física puede ser dos actores distintos según lo que esté haciendo.

En Vida Sana: un profesor que además entrena ahí como socio **no es un actor, son dos**. Cuando registra la limitación física de un alumno, actúa como *profesor*. Cuando se anota a una clase de yoga, actúa como *socio*. Mismo cuerpo, misma persona, dos roles. En el diagrama se cuentan roles, no personas.

```
        una persona física
               │
      ┌────────┴────────┐
      ▼                 ▼
  [Profesor]         [Socio]      ← dos actores en el modelo
```

### 3.2 Los tres actores del gimnasio

Del enunciado salen tres roles con objetivos propios frente al sistema:

| Actor | Qué quiere lograr | Dónde aparece en el enunciado |
|---|---|---|
| **Socio** | Anotarse a clases, avisar ausencias, recuperar clases, pagar su plan, saber si tiene lugar | "Los socios pueden contratar planes…", "quisieran poder avisar una ausencia hasta una hora antes" |
| **Profesor** | Dar la clase, registrar presentes, saber quién viene, ofrecer lugares de lista de espera (o dejar de hacerlo) | "los profesores deben llamar…", "han pedido desentenderse de todo tipo de registro" |
| **Junta Directiva** | Controlar el circuito, saber quién pagó, no contratar personal extra, definir bonos | "Nos convoca la Junta Directiva…", "los dueños han observado…", "pueden ganar un bono" |

No hay más. No hay "administrador", no hay "recepcionista" (justamente los dueños no quieren contratar a nadie), no hay "usuario" genérico. Si en algún momento te aparece un cuarto actor, tiene que salir del enunciado o de una entrevista, no de tu imaginación.

### 3.3 Lo que NO es actor

Esto es lo que más se corrige, así que va con lista:

- **El sistema.** Por §2.1. El sistema es la solución, no quien tiene el objetivo.
- **Un componente del sistema.** El lector de credenciales, la pantalla, la app. Están adentro del límite. No "quieren" nada.
- **Un objeto del dominio.** La clase de pilates, el reformer, el plan de 8 clases, la lista de espera. Son cosas sobre las que se actúa, no quienes actúan.
- **Alguien que no interactúa con el sistema.** Si el familiar del socio nunca toca el sistema, no es actor, aunque aparezca en el enunciado.

### 3.4 🟡 La excepción: un subsistema que actúa solo

Hay un caso en el que algo "del sistema" sí puede ir como actor, y conviene conocerlo para no confundirlo con lo de arriba.

Pensá en el vencimiento de un plan. El socio contrató 8 clases el día 15; el 15 del mes siguiente el plan vence. **Nadie aprieta nada** para que eso pase: un proceso mira el calendario y actúa. Cuando un proceso corre por tiempo, sin disparo humano, se lo modela como un **subsistema** (por ejemplo, un *subsistema notificador*) y ese subsistema **sí es un actor**, porque un actor no es necesariamente una persona: es quien dispara.

La diferencia con §3.3 es esta: ahí "el sistema" era **la solución entera** usada como protagonista de algo que en realidad quiere una persona. Acá es **un componente acotado, con una responsabilidad específica, que dispara por sí mismo**. Cuando el que dispara es una persona (el socio se da de baja y el profesor recibe el aviso), no hay subsistema: el actor es el socio, y el aviso es el final de su escenario.

> 🕳️ **Madriguera — procesos batch**
> Las empresas de servicios emiten doscientas mil facturas por día con un proceso que corre solo de madrugada; a eso se lo llama *batch* (por lotes). Es el ejemplo clásico de proceso sin disparo humano.
> *Volvé al camino: acá solo importa que un proceso que corre por tiempo se modela como subsistema-actor.*

## 4. 🔴 Las tres cosas que salen de un enunciado

Ahora sí, el corazón del módulo. De un enunciado como el del gimnasio, o de una entrevista, salen **tres tipos de frase** que hay que separar. Confundirlas es el error que más se corrige después de "el sistema debe".

### 4.1 Vé los tres juntos primero

Leé este párrafo del enunciado:

> *Para comprometer a los socios en su asistencia, éstos deben avisar al menos el día anterior de su ausencia, así los profes tienen tiempo de ofrecer su lugar a un socio en lista de espera, o bien cancelar la clase si quedan menos de 3 inscritos. Sólo aquellos socios que avisaron de una ausencia, pueden recuperar su clase.*

De ese único párrafo salen cosas de tres naturalezas distintas:

```
  "los socios avisan su ausencia"           → algo que un actor HACE     → RF
  "el socio en lista de espera recibe        → algo que un actor HACE     → RF
   el ofrecimiento del lugar"
  "avisar al menos el día anterior"          → CONDICIÓN del negocio,     → REGLA DE NEGOCIO
                                                existe con o sin sistema
  "solo quien avisó puede recuperar"         → ídem                        → REGLA DE NEGOCIO
  "si quedan menos de 3, se cancela"         → ídem                        → REGLA DE NEGOCIO
  (nada del párrafo dice CÓMO de bien       → no hay RNF acá; habría que
   tiene que funcionar el aviso)               relevarlo o suponerlo
```

Todavía no sabés escribirlos con la forma correcta. Pero fijate que ya pudiste **separarlos**, y eso es lo primero.

### 4.2 Las definiciones, ahora que las viste funcionar

**Requerimiento funcional (RF).** Describe **qué** quiere lograr un actor a través del sistema: una acción, un servicio, una funcionalidad. Es un objetivo del actor. *El socio avisa su ausencia a una clase.* Es independiente de la tecnología: no dice si el aviso es por app, por WhatsApp o por teléfono.

**Requerimiento no funcional (RNF).** Describe **cómo** tiene que darse esa funcionalidad, **bajo qué condiciones o restricciones**: qué tan rápido, qué tan disponible, por qué medio, con qué componente. Restringe al RF. Su característica más importante es que **se puede medir o verificar**: *el tiempo máximo de confirmación de un aviso de ausencia es de 2 segundos.* Puede depender de tecnología, y muchas veces la nombra.

**Regla de negocio.** Una política, restricción o norma **propia del negocio**, que existe **con o sin sistema**: *solo el socio que avisó su ausencia puede recuperar la clase.* Existiría igual si el gimnasio siguiera con carpetas y resaltadores. No es algo que el sistema hace (RF) ni una cualidad que el sistema tiene (RNF): es una condición que el sistema debe **respetar**.

Y hay una cuarta categoría, que es "no es nada": **la justificación**. *"Para comprometer a los socios en su asistencia…"* explica por qué existe la regla; no es requisito ni regla, es contexto. Se anota aparte si sirve para entender, pero no se convierte en nada.

### 4.3 El test de tres preguntas

Frente a cualquier frase de un enunciado, tres preguntas, en este orden:

```
   1. ¿Existiría esta frase aunque no hubiera ningún sistema,
      con carpetas y resaltadores?
        → SÍ  ⇒ REGLA DE NEGOCIO. Listo, no sigas.
        → NO  ⇒ seguí.

   2. ¿Describe algo que un ACTOR quiere lograr (un verbo del actor)?
        → SÍ  ⇒ RF.
        → NO  ⇒ seguí.

   3. ¿Describe una condición, propiedad o restricción de CÓMO
      tiene que darse una funcionalidad (un valor, un medio, un componente)?
        → SÍ  ⇒ RNF.
        → NO  ⇒ es justificación, contexto o dolor. No se convierte en nada
                (pero sirve para entender qué preguntar en la entrevista).
```

Probalo con cuatro frases del enunciado:

| Frase del enunciado | P1 | P2 | P3 | Resultado |
|---|---|---|---|---|
| "Todas las clases duran una hora" | Sí: dura una hora con o sin sistema | — | — | Regla de negocio |
| "los profesores llaman al primer socio inscrito en la lista de espera" | No: es una acción que hoy hacen a mano y quieren que el sistema resuelva | Sí: hay un actor (profesor, o el socio que recibe) y un verbo | — | RF |
| "usan un criterio de identificación de socios poco fiable: 3 letras del nombre y 2 del apellido" | No | No: nadie "quiere lograr" un código malo | Sí: habla de **cómo** se identifica a un socio; es una restricción a rediseñar | RNF (a corregir: el medio de identificación) |
| "han surgido roces entre ellos y con los dueños" | No | No | No | Dolor / contexto. No es nada, pero es oro para la entrevista |

**Sobre la tercera fila, una aclaración honesta.** Lo que el enunciado describe es el criterio *actual*, que es malo. El RNF que vas a escribir no es "el código son 3 letras y 2 letras": es el que **reemplaza** eso, por ejemplo con un identificador único. Cómo se escribe, en M3.

### 4.4 Tabla lado a lado

| | RF | RNF | Regla de negocio |
|---|---|---|---|
| Responde a | ¿Qué quiere lograr el actor? | ¿Cómo lo hace el sistema? ¿Bajo qué restricciones? | ¿Qué política del negocio hay que respetar? |
| Protagonista | El **actor** | El **objeto** que se mide o restringe (el actor desaparece) | El negocio |
| Verbo típico | De acción, en presente: registra, avisa, consulta, paga | **Ser**: es, son | Puede, debe, no puede |
| Se valida | Ejecutando la función en pasos finitos | Midiendo un valor o verificando una propiedad | Contra la organización, no contra el software |
| Existe sin sistema | No | No | **Sí** |
| Ejemplo (gimnasio) | El socio se anota en una clase | El tiempo máximo de confirmación de la inscripción es de 2 segundos | Si una clase tiene menos de 3 inscriptos, se cancela |

> **Para el parcial, si te preguntan:** *¿Qué diferencia hay entre un requisito funcional, uno no funcional y una regla de negocio?*
> El RF describe qué quiere lograr un actor a través del sistema (una funcionalidad) y se valida ejecutándola. El RNF describe cómo debe darse esa funcionalidad, como restricción o propiedad medible que limita el diseño de la solución. La regla de negocio es una política del dominio que existe independientemente del sistema y que el sistema debe respetar; no es un requisito del sistema.

## 5. 🟡 Tres frases que engañan

Para cerrar, tres frases que parecen una cosa y son otra. No las vas a resolver acá: solo tenés que reconocer que engañan. Cada una se cierra en un módulo posterior.

**"El sistema debe registrar la asistencia de los socios a las clases."** Es la de §1. Parece RF. El problema: el protagonista es el sistema, y el sistema no tiene objetivos. Falta saber **de quién** es esa función. ¿Del socio, que se registra al entrar? ¿Del profesor, que toma presente? Son dos requisitos distintos. *Se cierra en M2 §2.*

**"El socio tendrá una credencial para poder ingresar."** Parece RF (tiene actor y verbo). Pero "tener una credencial" no es algo que el socio *haga*: es una **condición sobre cómo se ingresa**, un medio. ¿Entonces es RNF? Sí. ¿Y cómo se escribe un RNF sobre un componente, si no tiene número? *Se cierra en M3 §4.*

**"El registro de asistencia tiene que tardar poco."** Parece RNF (habla de cómo funciona el registro). Pero ¿cuánto es poco? Sin valor no se puede medir, y lo que no se mide no se puede exigir. *Se cierra en M3 §1.*

Fijate que en las tres frases el problema **no es que estén mal clasificadas**. Es que están mal **escritas** para su categoría. Clasificar es este módulo; escribir bien son los dos que siguen.

---

## ✏️ Tu turno

Clasificá cada frase del enunciado con el test de §4.3. Anotá el resultado (RF / RNF / regla de negocio / nada) y **una línea de por qué**. Sin mirar la tabla de §4.4.

1. "Si un socio inscripto se baja de la clase, los profesores llaman al primer socio inscrito en la lista de espera para ofrecerle el lugar."
2. "Para contratar el plan deben reservar su lugar pagando una seña o la totalidad."
3. "Para los sectores sin profesor el tiempo mínimo de uso es de 30 min y el máximo es de 120 min."
4. "Los profesores han pedido a la Junta desentenderse de todo tipo de registro y acción."
5. "Los socios quisieran poder avisar una ausencia hasta una hora antes de la clase."
6. "Los profesores pueden ganar un bono por el porcentaje de clases con cupo completo que dan en un mes."

Una pista, sin respuesta: la frase 5 y la regla de "avisar el día anterior" se contradicen. Eso no es un problema tuyo de clasificación; es un **conflicto entre stakeholders**, y se resuelve negociando, no redactando.

## ✅ Checkpoint

1. ¿Por qué un sistema no puede ser actor? Respondé desde la definición de sistema.
2. Nombrá los tres actores de Vida Sana y, para cada uno, un objetivo que tenga frente al sistema.
3. Un profesor que también es socio: ¿cuántos actores es? ¿Por qué?
4. ¿Cuándo un componente del sistema sí puede modelarse como actor? Dá el ejemplo del gimnasio.
5. ¿Cuál es la pregunta que distingue una regla de negocio de un requisito?
6. "El sistema debe controlar la capacidad máxima de cada clase." ¿Qué hay ahí adentro: RF, RNF, regla de negocio, o una mezcla? Separalo.
7. ¿Por qué "para comprometer a los socios en su asistencia" no se convierte en ningún requisito?
8. ¿En qué se parecen y en qué se diferencian "el socio tendrá una credencial" y "el registro tiene que tardar poco"?

## Qué viene en el Módulo 2

Ya sabés separar. Ahora hay que **escribir el RF con la forma que se corrige**: quién, hace qué, sobre qué. Vas a ver por qué "el sistema debe" se cae, cómo se elige el verbo, qué es el nivel alto y el nivel detallado, y las nueve trampas de redacción que aparecen en casi todos los primeros intentos. Y un método de cinco pasos para ir de una frase del enunciado a un RF que aguante tres preguntas.

**FIN DEL MÓDULO 1**
