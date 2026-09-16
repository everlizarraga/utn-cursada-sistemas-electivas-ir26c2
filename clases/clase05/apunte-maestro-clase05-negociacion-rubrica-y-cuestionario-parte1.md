# 📘 APUNTE MAESTRO — Clase 05 · Negociación de cambios, rúbrica y cuestionario — Parte 1

**Materia:** Ingeniería de Requisitos (IR) — UTN FRBA · 2C 2026
**Clase:** 05 · jueves 10/09/2026 · virtual
**Parte 1 de 2:** el rol del ingeniero de requisitos · los cambios en los requerimientos y la reunión de negociación · el caso Vida Sana · lecciones de la mediación

**Leyenda:** 🔴 central, evaluable · 🟡 secundario · 🟢 mencionado al pasar · 🕳️ madriguera (tangente que se saltea sin culpa)

---

## Sobre esta parte

**Qué cubre:** qué hace un ingeniero de requisitos cuando los stakeholders piden cosas contrapuestas. Sus tres roles, por qué los requerimientos cambian, cómo se estructura una reunión de negociación, qué registra el documentador, y el caso completo del centro de entrenamiento Vida Sana con las lecciones que dejó.

**Qué viene en la Parte 2:** la rúbrica de casos de uso, el cuestionario a socios, kernel sentences, la información operativa de la clase y el checkpoint final de la unidad.

## De dónde venís

De la clase 01: stakeholders, usuarios y clientes. De las clases 03 y 04: la entrevista, su guía de preguntas y la minuta. De la clase 04: cómo se escribe un RF (rol + verbo + objeto, f(x) = y) y un RNF con métrica. Esta clase se para sobre eso y no lo repite: lo usa.

---

## 1. 🔴 El rol del ingeniero de requisitos

Arrancá desde donde quedaste. Entrevistaste a la Junta Directiva y a los profesores de Vida Sana. Tenés dos minutas. Y cuando las ponés una al lado de la otra aparece el problema: **piden cosas distintas, y algunas se contradicen**. La Junta quiere cámaras para controlar que las clases se dicten y que los pagos se registren. Los profesores quieren dejar de hacer tareas administrativas y desconfían de las cámaras. No le podés cumplir a todos. Y todavía no escribiste una línea de código, no buscaste un proveedor ni presupuestaste nada.

Ese momento define qué es un ingeniero de requisitos. No es simplemente "el que se junta con el cliente": **lidera la elicitación, documenta con distintas técnicas y valida los requerimientos con los usuarios**. Para hacerlo cumple tres roles a la vez.

### 1.1 Facilitador

Asiste a los stakeholders y a los usuarios en el proceso, y hace que se sientan seguros y participativos.

Por qué importa: necesitás que los stakeholders y los futuros usuarios **participen** para obtener buenos requerimientos. Si no participan, el desarrollo termina basado en nada, o en inferencias y descubrimientos erróneos.

Una línea que aparece en algunas minutas muestra el rol bien hecho: *"esto después lo tenemos que ratificar con la Junta Directiva"*. El analista no se queda con lo que le dicen los stakeholders que **no** toman la decisión; sabe quién decide y lo lleva a validar ahí.

### 1.2 Mediador

Facilita la resolución de **conflictos de intereses** y la **priorización entre requisitos**.

Las diferencias típicas: entre lo que pide un universo de futuros usuarios y lo que pide otro; entre los usuarios principales, que van a operar la aplicación todos los días y registrar la información que después se usa para tomar decisiones, y quienes financian o esponsorean el proyecto. El objetivo del mediador es llegar a un producto que satisfaga los requerimientos **prioritarios**, los que van a dar el mejor resultado para el cliente.

### 1.3 Documentador, y puente hacia el desarrollo

Documenta y define para el trabajo posterior del equipo de desarrollo.

```text
   CLIENTE                    INGENIERO DE                    EQUIPO DE
   (stakeholders,   ◄────►    REQUISITOS      ◄────►    DISEÑO Y DESARROLLO
    usuarios)                                              (o proveedor)

   Le da la cara al cliente          │          Se da vuelta y le da la cara
   para elicitar y documentar        │          al desarrollo con TODA la
   lo que descubre                   │          información para arrancar
```

Cuando terminás de mirar al cliente, te das vuelta y le das la cara al desarrollador, o al equipo que va a diseñar y desarrollar, y le entregás todo lo que hace falta para empezar a trabajar en la solución. Para eso tenés que **conocer las limitaciones de la arquitectura, la infraestructura y el estado del arte** de los sistemas, y saber qué posibilidades tiene tu equipo y qué posibilidades tiene el cliente en gasto, inversión, tiempo y recursos.

Ejemplo: el cliente pide "una aplicación con inteligencia artificial". Vos no vas a implementar el bot, pero tenés que saber cómo se costea, cómo se calcula, qué se puede lograr y qué no. Eso sale de haber trabajado con la gente de desarrollo o de capacitarte por tu cuenta. **No podés quedarte esperando que alguien venga a contarte: el conocimiento se va a buscar.** Y de ese conocimiento salen las relaciones que te sirven en la mesa: "esto que sirve acá puede servir para tal otra cosa".

### 1.4 El requerimiento se cumple completo

Un caso real. Una persona saca un turno médico por WhatsApp, con un bot. La doctora cancela. Las recepcionistas no pueden avisarle, porque **no tienen acceso a la información del bot**: en su agenda hay algún dato del paciente, pero no tienen forma de contactarlo a partir de los turnos que dio el WhatsApp.

Se automatizó la asignación del turno y se dejó afuera el resto del circuito. El requerimiento se tiene que cumplir **completo**: si te doy el turno, te lo tengo que poder avisar cuando se cancela. Los datos podían estar en otro lado, integrados; nadie lo pensó. Cuando documentás un requerimiento, documentás el circuito entero, no la mitad que brilla.

> **Para el parcial, si te preguntan:** *¿Cuáles son los roles del ingeniero de requisitos?*
> Facilitador (asiste a stakeholders y usuarios para que participen del proceso), mediador (resuelve conflictos de intereses y prioriza entre requisitos) y documentador (documenta y define para el trabajo posterior del equipo de desarrollo). No es solo quien se junta con el cliente: lidera la elicitación, documenta con distintas técnicas y valida los requerimientos con los usuarios.

> **Para el parcial, si te preguntan:** *¿Por qué el ingeniero de requisitos necesita conocer las limitaciones técnicas y los costos?*
> Porque documenta y define para el equipo de desarrollo, y tiene que saber qué es posible con la arquitectura, la infraestructura, el estado del arte y los recursos del equipo y del cliente. Sin ese conocimiento no puede evaluar ni negociar lo que el cliente pide.

---

## 2. 🔴 Los cambios en los requerimientos y la reunión de negociación

### 2.1 Por qué aparecen cambios

Los cambios aparecen siempre. Un ejemplo chico: el proyecto se dimensionó por cantidad de usuarios y alguien dice "usuarios no, vamos con concurrentes". ¿Cuántos concurrentes? Hay que salir a preguntar, a averiguar, a hacer métricas. Y con eso cambió un montón: el costeo, quiénes están involucrados, y aparece el riesgo de que los usuarios no alcancen o de que no se pueda ampliar después.

Cada cambio se **negocia**. Y la regla número uno de esa negociación: **no dejar afuera a ninguno de los que tienen peso en las decisiones**. "Uy, no le preguntaste a tal." "Uy, yo sabía que estaba interesado." Eso no puede pasar: un acuerdo cerrado sin uno de los que deciden es un acuerdo que se va a reabrir.

### 2.2 Cuándo se convoca la reunión

En Vida Sana la etapa siguiente no es desarrollar: es la **preselección de soluciones enlatadas** (glosa: software ya hecho, que se compra o se contrata y se configura, en vez de desarrollarse a medida). Antes de investigar soluciones, antes de contactar proveedores, antes de evaluar e invertir, las partes tienen que **ponerse de acuerdo en qué requerimientos hay que cubrir**. Si no, investigás y presupuestás sobre requerimientos que después cambian.

Por eso, cuando profesores y Junta vienen con reclamos que se contradicen, el equipo convoca a una reunión con **las dos partes juntas**. En las entrevistas, un equipo con stakeholders enfrentados podía partir la reunión en dos, media con la Junta y media con los profesores, para que no se peleen. En la negociación no: la confrontación es el punto de la reunión.

La modalidad se decide por tiempo y por costo. Una reunión presencial implica pagarle al consultor también las horas de traslado, y la entrevista se vuelve onerosa; si los tiempos no dan, se hace virtual.

### 2.3 Los tres momentos de la reunión

```text
  ┌───────────────────────┐    ┌───────────────────────┐    ┌───────────────────────┐
  │ 1. EXPOSICIÓN DE      │    │ 2. NEGOCIACIÓN        │    │ 3. ACUERDO FINAL      │
  │    POSICIONES         │ ─► │    PUNTO POR PUNTO    │ ─► │                       │
  │                       │    │                       │    │ Cada acuerdo se       │
  │ Cada parte expone qué │    │ Quién cede, quién no. │    │ reformula como RF o   │
  │ le pasa, qué pide y   │    │ Se cierra un punto    │    │ RNF bien redactado.   │
  │ qué trae como no      │    │ antes de pasar al     │    │ Lo sin acuerdo queda  │
  │ negociable.           │    │ siguiente.            │    │ como pendiente.       │
  └───────────────────────┘    └───────────────────────┘    └───────────────────────┘
```

**1. Exposición de posiciones.** Cada parte expone su postura frente a los conflictos: cómo se siente, qué le pasó, por qué cambiaron sus requerimientos. Lo que hay que registrar: sus principales problemáticas, cada petición y **cómo la presentan**, porque todo eso sirve para el acuerdo final. Cada parte trae a la mesa lo que considera **no negociable**, que muchas veces es, para la otra parte, no implementable.

**2. Negociación punto por punto.** Con toda la información sobre la mesa, se cierra cada punto: **quién cede y quién no, cuáles fueron los no negociables y cómo se llega al acuerdo**. La notación para documentarlo:

| Marca | Significado |
|---|---|
| **NN** | No negociable: la parte no cede en ese punto. |
| **C** | Cedido desde una posición previa: la parte aceptó algo que al principio no aceptaba. |

Si una reunión de cuarenta minutos termina y nadie sabe en qué quedó, falló. Cada punto se cierra antes de avanzar: "ok, ¿estamos todos de acuerdo con esto?".

**3. Acuerdo final.** Se establecen los principales conflictos y el acuerdo al que se llegó con ambas partes. Y **cada acuerdo se reformula como un requerimiento funcional o no funcional correctamente redactado**: rol, verbo, objeto y datos para el RF; métrica para el RNF, como en la clase 04. Lo que no se acordó no desaparece: queda documentado como punto sin resolver.

### 2.4 Quién hace qué en la mesa

| Rol | Qué hace |
|---|---|
| **Las partes** (Junta Directiva, profesores) | Traen sus demandas, sus prioridades y sus no negociables. Ceden o no. |
| **Mediadores** (ingenieros de requisitos) | Lideran la reunión. Al inicio plantean las **reglas** (tiempos, cuántas prioridades trae cada parte, no interrumpirse). Primero **escuchan** las demandas; recién después negocian. Cierran cada punto. |
| **Documentadores** (ingenieros de requisitos) | Apoyan a los mediadores y registran. Al final leen lo acordado. |

Las reglas del documentador, que son las que definen qué vale después:

- Registra **mandatoriamente** lo que ambas partes acuerdan **explícitamente**.
- **Puede** registrar aquello en lo que no hubo acuerdo.
- Si hay duda, lo anota como **punto pendiente**.
- Tiene a mano la minuta de la entrevista previa: la abre, la copia y va marcando si hubo cambios respecto de lo relevado.
- **Puede interrumpir para cerrar un punto** ("entonces esto queda como requerimiento funcional"). No es solo un escriba: como lo que queda documentado es lo que vale, si un acuerdo quedó difuso, lo pregunta. Preguntar no es exclusivo del mediador.
- Durante la reunión anota libre, tipo lluvia de ideas; nadie corrige esas notas. Lo que sí se redacta con cuidado es el **acuerdo final**, como RF y RNF.
- Entrega, con todo el equipo: la lista de **RF acordados**, **RNF acordados** y **puntos sin resolver**.

> **Para el parcial, si te preguntan:** *¿Cuáles son los momentos de una reunión de negociación de requerimientos?*
> Exposición de posiciones (cada parte expone sus problemáticas, peticiones y no negociables), negociación punto por punto (se documenta quién cede y quién no, cerrando cada punto antes de seguir) y acuerdo final (cada acuerdo se reformula como RF o RNF correctamente redactado; lo no acordado queda como pendiente).

> **Para el parcial, si te preguntan:** *¿Qué registra el documentador en una reunión de negociación?*
> Obligatoriamente, lo que ambas partes acuerdan explícitamente. Puede registrar lo no acordado, y ante la duda anota el punto como pendiente. Entrega una lista de RF acordados, RNF acordados y puntos sin resolver.

---

## 3. 🔴 El caso: Vida Sana, Junta Directiva contra profesores

Ahora el caso completo, tal como se desarrolló en la reunión, para que las lecciones de la sección 4 tengan de dónde agarrarse.

### 3.1 El punto de partida

La Junta registra una **pérdida del 5%** respecto del mes anterior, por pagos de planes de socios que no se registran. Hoy ese registro lo hacen los profesores. La Junta no confía en que todas las clases se dicten como corresponde. Los profesores no quieren hacer tareas administrativas. Y hay una fecha: la Junta confirmó su participación en una **feria de fitness en 45 días** y quiere mostrar ahí un sistema de acceso por QR para captar socios.

### 3.2 Las posiciones y cómo se negociaron

Los mediadores abrieron planteando las reglas: cada parte expone **al menos tres prioridades**, después se negocia punto por punto, y nadie interrumpe. Después dieron la palabra a la Junta.

| Tema | Junta Directiva | Profesores | Cómo quedó |
|---|---|---|---|
| **Cámaras** | NN. Para verificar que las clases se dictan y contar asistentes. Después lo reformuló: uso **forense** (glosa: revisar las grabaciones después de un hecho para reconstruir qué pasó), cruzando pagos registrados contra personas en la clase. La inversión se recupera si frena la pérdida. | Preguntaron quién las controla, dónde se guardan las grabaciones, si van en las salas o en administración. Les preocupa la privacidad de los socios, que no fueron avisados y podrían darse de baja. Aceptan (C) si eso no afecta la retención de socios; les sirve para demostrar cuándo una clase se cancela por falta de alumnos. | **Acordado** instalar cámaras. Sin definir: ubicación, quién las mira, almacenamiento, aviso a socios, financiamiento. |
| **Cobros y registros** | Sostuvo que los profesores firmaron sabiendo que harían tareas administrativas. Pero su objetivo es que **la aplicación** las absorba: el cobro por la aplicación, directo a la caja. | NN: no van a cortar una clase para ir a cobrar. Piden personal administrativo o un sistema. | **Acordado**: el cobro se hace por la aplicación. Pendiente: uno o dos administrativos de respaldo mientras el sistema se ajusta. |
| **Acceso por QR en 45 días** | NN. Vital para la feria. Acepta arrancar con un **MVP** (glosa: producto mínimo viable, la primera versión con lo indispensable) y seguir por ciclos. | — | **Acordado** el MVP con QR y cámaras; el molinete queda para una segunda instancia. **Sin acuerdo** sobre la fecha: los analistas no la comprometen sin los requerimientos definidos. |
| **Indicadores para el presidente** | Viaja seguido y necesita ver desde el celular: clases del día, asistentes por clase, deudores y recaudación mensual. Con eso decide si abre más clases o suma profesores. | — | **Acordado**, con los cuatro indicadores. |
| **Rutinas** | Quiere saber el impacto en el presupuesto antes de decidir. | El encargado de rutinas las arma a mano, personalizadas, y las manda en PDF por WhatsApp; cuando se va de vacaciones no hay forma de hacerlo. Pide cargarlas y asignarlas desde un lugar centralizado. | **Pendiente**: canal (aplicación o WhatsApp) y costo. |
| **Profesores sin smartphone** | NN. No es responsabilidad de la Junta proveer celulares. | Piden un dispositivo para recibir las notificaciones. | **Sin acuerdo.** La Junta cambió de tema y quedó postergado. |

Dos intervenciones de los analistas que vale la pena ver. Cuando la discusión sobre cámaras y administración se empezó a mezclar y los mediadores querían pasar al tema siguiente, uno de los analistas frenó: *"antes de pasar a la siguiente problemática necesitamos definir la anterior"*, y dejó planteado el acuerdo (cámaras más sistema automatizado, con respaldo administrativo al inicio). Los mediadores lo registraron como propuesta a armar después, y recién ahí habilitaron el siguiente tema. Y cuando la Junta presionó por la fecha, los mediadores no dieron un plazo: propusieron enviar una minuta con las decisiones, que la Junta confirme los requerimientos, y recién ahí un plazo. Se comprometieron a responder **en 72 horas**.

### 3.3 Lo que faltó en la mesa

En medio de la discusión sobre las cámaras apareció una parte que nadie había convocado: **los socios**. ¿Van a querer venir si saben que los filman? ¿O se van a sentir más seguros? Nadie en la reunión lo sabía, porque nadie les había preguntado. Y el gimnasio como servicio no es solo la calidad de la clase: es toda la interacción del socio con el centro, incluida la parte administrativa que los profesores quieren dejar de hacer. Ese hueco se cubre con la técnica de la Parte 2: el cuestionario.

---

## 4. 🔴 Lecciones de la mediación

### 4.1 La decisión unilateral es el peor escenario

Cuando la situación se pone áspera, la tentación es patear para adelante: "esta definición requiere más discusión, la dejamos para después". A veces corresponde. Pero a veces **hay que tomar la definición por sí o por no**, porque si todo queda para después, no se avanza (en Vida Sana quedaron muchos puntos sin definir, y el equipo técnico va a recibir una lista de tareas incompleta).

Lo que nunca puede pasar es la **decisión unilateral**: que una de las partes te llame después para decidir algo, y la otra parte se entere cuando ya está hecho. "Pongo las cámaras como a mí me parece y que los profesores se enteren después." Eso trae conflicto y problemas más adelante. Toda decisión se toma con los dos lados sabiendo.

### 4.2 La presión por fechas

La Junta hizo lo que hace un cliente que sabe de sistemas: pidió el sistema completo, después "solo el QR", después "un MVP", y siempre con la fecha inamovible. Frente a eso hay tres herramientas.

**Priorizar.** No todo se puede en esa fecha. "De los diez requerimientos, definime tres." Y si tres no se pueden, cinco. Se achica hasta que lo que queda es viable con el equipo técnico. Lo que no entra pasa al **backlog** (glosa: la lista de pendientes ordenada por prioridad), y acá aparece algo que se repite: **lo que queda en el backlog suele perder prioridad, y muchas veces termina concluyéndose que no era tan necesario**. Si sobreviviste todo ese tiempo resolviendo otras funcionalidades y no esa, tan necesaria no era.

**Comprometer una fecha para la respuesta, no para la entrega.** Decir "no sé, lo tengo que ver" frente a un cliente con urgencia pone la situación más picante. Decir "lo vemos con el equipo técnico y mañana te mandamos un mail" es poner una fecha a algo, aunque la información todavía no la tengas.

**Si ponés fecha, tené información.** Para decir sí, no, o una fecha, necesitás datos. Y si la ponés: una fecha laxa que resolvés antes te deja bien parado; una fecha ajustada que sabés que no se puede cumplir te complica.

### 4.3 El costo oculto de un pedido

Las cámaras son el ejemplo perfecto. La primera pregunta: **¿quién las va a ver?** Si nadie está atrás mirando en línea, la cámara sola no tiene mucho sentido. Si el uso es forense, como en las aduanas, donde las cámaras graban y las grabaciones se piden recién cuando hay un oficio judicial, entonces el punto técnico es otro: hay que **comprar o pagar almacenamiento** para guardar video de quien entró a hacer cuatro abdominales, definir **cuánto tiempo** se guardan los archivos, pagar el **procesamiento** y el servicio. Y evaluar el costo-beneficio de todo eso.

Ese conocimiento técnico es lo que te permite reaccionar en la mesa y negociar para que el stakeholder entienda que **no es tan lineal, ni tan barato, ni gratis**. La inteligencia artificial tampoco es gratis. Y cada pedido suma: si quieren reconocimiento facial, hay que comprar un molinete que habilite el paso; sin nada que frene, la cámara no impide que entre cualquiera. La reunión terminó como terminan muchas: "agregamos todo esto, pero sin aumentar el presupuesto".

Más allá de la cuestión ética, está la **factibilidad técnica**: si alguna de las soluciones enlatadas que se investiguen integra las cámaras, o si van a ir por separado con su propio visor. Es una pregunta para la etapa siguiente.

> 🕳️ **Madriguera — Grabar personas y datos personales**
> Filmar socios y empleados es tratar datos personales, y en Argentina eso tiene regulación propia (Ley 25.326). Qué exige avisar, qué se puede guardar y por cuánto tiempo, no entra en esta materia.
> *Volvé al camino — esto se profundiza aparte, otro día.*

### 4.4 Manejar la agenda sin dejar cabos sueltos

Cuando el tema de los celulares se trabó, la Junta lo cortó ("esto lo vemos después") y saltó al QR. La reunión avanzó. Postergar un punto que traba es una habilidad que el analista también tiene que absorber, con una condición: el punto **queda registrado como pendiente y se retoma**. Si se posterga y se olvida, vuelve más adelante como conflicto (4.1).

### 4.5 Qué llevar a la reunión

Lo que se lleva a la mesa de negociación, resumido:

- **Conocimiento**: entender las restricciones técnicas y de costos antes de entrar (sección 1.3).
- **Prioridades bajo la manga**: saber qué es prioritario y qué no, para poder achicar cuando aprieten (4.2).
- **Habilidades de mediación**: escuchar primero, cerrar cada punto, no dejar a nadie afuera, no decidir unilateralmente.
- **Herramientas para documentar**: tomar nota, y eventualmente grabar la conversación para documentar después, porque lo definido en la reunión muchas veces hay que entregarlo en breve. Qué herramienta usar depende del cliente, del equipo y de la forma de trabajo que se vaya incorporando.

> **Para el parcial, si te preguntan:** *¿Qué es una decisión unilateral en la negociación de requerimientos y por qué debe evitarse?*
> Es una decisión que una de las partes toma con el analista sin que la otra parte con peso en la decisión lo sepa. Se evita porque genera conflicto y reabre el acuerdo: toda definición se toma con ambas partes informadas.

> **Para el parcial, si te preguntan:** *¿Cómo responde el ingeniero de requisitos cuando el cliente exige una fecha sin tener los requerimientos definidos?*
> No compromete un plazo sin requerimientos definidos ni información técnica. Prioriza con el cliente qué es indispensable para esa fecha (por ejemplo, un MVP), y compromete una fecha para dar la respuesta, no para la entrega. Si fija una fecha, prefiere una laxa que pueda adelantar antes que una ajustada que sabe que no cumplirá.

> **Para el parcial, si te preguntan:** *¿Qué debe evaluar el ingeniero de requisitos cuando el cliente pide instalar cámaras?*
> Quién va a ver las imágenes y para qué (monitoreo en línea o uso forense), el costo de almacenamiento, procesamiento y servicio, por cuánto tiempo se guardan las grabaciones, y la factibilidad técnica de integrarlas con la solución. Con eso muestra al cliente que el pedido no es lineal ni gratuito.

---

## 5. ✅ Checkpoint — Parte 1

Sin respuestas: van al complemento.

1. ¿Qué diferencia hay entre el rol de facilitador y el de mediador del ingeniero de requisitos?
2. ¿Por qué se dice que el ingeniero de requisitos "le da la espalda al cliente" en algún momento? ¿Qué necesita saber para ese momento?
3. En el caso del turno médico por WhatsApp, ¿qué parte del requerimiento faltó y qué enseña sobre cómo documentar?
4. ¿Qué tiene que pasar antes de investigar soluciones enlatadas para Vida Sana, y por qué?
5. ¿Qué significan las marcas NN y C, y en qué momento de la reunión se usan?
6. ¿Puede un documentador interrumpir la negociación? ¿Con qué objetivo?
7. En Vida Sana, ¿qué puntos quedaron acordados y cuáles sin resolver? Nombrá al menos dos de cada grupo.
8. ¿Qué suele pasar con los requerimientos que quedan en el backlog después de priorizar?
9. ¿Qué preguntas técnicas convierten "queremos cámaras" en un pedido con costo?
10. ¿Qué parte interesada apareció en la reunión sin haber sido convocada, y qué técnica la cubre?

---

## Qué viene en la Parte 2

La rúbrica de casos de uso como instrumento de autoevaluación de calidad: criterios medibles sin adverbios, niveles de logro con puntaje y el ejemplo del nombre del caso de uso. El cuestionario a socios: qué lugar ocupa después de la negociación, cómo se diseñan sus preguntas y cómo se defiende cada una. Kernel sentences, la información operativa de la clase y el checkpoint final de la unidad.

**FIN DE LA PARTE 1**
