# 📘 APUNTE MAESTRO — Clase 03 · Técnicas de Elicitación — Parte 5

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Unidad:** `clase03` · Jueves 27/08/2026 · Virtual
**Parte 5:** Técnicas 6 y 7 — prototipos de descubrimiento y JRP — y el plan de relevamiento.

---

## Sobre esta parte

**Qué cubre:** Técnica 6, prototipos de descubrimiento · Técnica 7, JRP · síntesis de las siete técnicas: cuándo usar cada una · el plan de relevamiento: qué tiene que tener, cómo se razona, con qué criterios se corrige · el caso de estacionamientos resuelto de punta a punta.

**Cierra la unidad.** Después de esta parte, el complemento (con las respuestas de los cinco checkpoints).

**Marcas:** 🔴 central, evaluable · 🟡 secundario · 🟢 mencionado al pasar · 🕳️ madriguera.

## De dónde venís

De las Partes 1 a 4: el caso, el mapa de siete técnicas, y las cinco primeras desarrolladas. En particular: la documentación va antes que la entrevista (P1 §6.1), la observación valida y mide (P2 §4), el cuestionario va después de la entrevista y dentro del alcance (P3 §5), y la entrevista se prepara con guía y se cierra con minuta (P4 §4). De la Parte 2 §3: la técnica se elige por el problema, y se verifica con el usuario.

---

## 1. 🟡 Técnica 6 — Prototipos de descubrimiento

Volvé al caso una vez más. Entrevistaste al administrador y te dijo que quiere "ver en tiempo real qué pasa en cada playa". Le preguntaste qué significa eso y no supo explicarlo bien: quiere *ver*, pero no sabe decir qué. Hay requisitos que la gente no puede describir hasta que los tiene enfrente.

**Prototipar** es construir un modelo chico y funcional de los requisitos de los usuarios, o de un diseño propuesto. Normalmente es una técnica de **diseño** (se usa en desarrollo rápido de aplicaciones — RAD, glosa: enfoque que prioriza construir rápido versiones parciales en vez de especificar todo primero). Pero el mismo enfoque se puede aplicar **antes**, en el relevamiento y análisis de requisitos, construyendo **prototipos de descubrimiento**.

**Prototipo de descubrimiento** es el acto de construir un modelo a pequeña escala, representativo o funcional, de los requisitos de los usuarios, **para descubrir o verificar esos requisitos**.

Se aplica sobre todo cuando el equipo de desarrollo **tiene problemas para definir los requisitos**. La filosofía: **los usuarios van a reconocer sus requisitos cuando los vean.** Le mostrás al administrador una pantalla con un mapa de las veinte playas y un número de ocupación en cada una, y él te dice "sí, eso — pero además quiero saber cuántos abonos vencen esta semana". Ese segundo requisito no salía de ninguna entrevista.

Cómo se construye un prototipo de descubrimiento:

- **Rápido**, para poder usarlo durante el desarrollo.
- **Solo las áreas donde los requisitos no están claros.** No se prototipa todo.
- **Se deja afuera mucha funcionalidad** y se ignora el control de calidad.
- **Los requisitos no funcionales** —rendimiento, confiabilidad— se relajan respecto del producto final.
- **Se usan tecnologías distintas** de las que va a llevar el software final, muchas veces.
- Por todo lo anterior, **lo más probable es que se descarte** cuando el sistema esté terminado. Es un prototipo **descartable** (*throwaway*): sirve para juntar información y desarrollar ideas sobre el concepto del sistema, no para evolucionar hacia el producto.

Muchas áreas de un sistema propuesto no se entienden con claridad, o son un desafío técnico para los desarrolladores. Prototipar les permite, a ellos y a los usuarios, entender y refinar los problemas de construir el sistema. Minimiza el riesgo de entregar un sistema que no cubre las necesidades del usuario, o que no puede cumplir los requisitos técnicos.

### Ventajas

- Permite a usuarios y desarrolladores **experimentar** con el software y entender cómo podría funcionar el sistema.
- Ayuda a determinar **factibilidad y utilidad antes de incurrir en costos altos** de desarrollo.
- Sirve como **mecanismo de capacitación** para los usuarios.
- Ayuda a construir **planes y escenarios de prueba** que se van a usar al final, en las pruebas del sistema.
- Puede **reducir el tiempo de relevamiento** y ayudar a definir requisitos más estables y confiables.

### Desventajas

- Los desarrolladores pueden necesitar **capacitación** en el enfoque de prototipado.
- **Los usuarios pueden generar expectativas irreales** basadas en el rendimiento, la confiabilidad y las funciones del prototipo. Un prototipo solo *simula* la funcionalidad y es incompleto por naturaleza; hay que **educar a los usuarios** en eso y no engañarlos. Es la misma trampa del cuestionario (Parte 3 §5.1): mostrar algo que después no va a existir.
- Prototipar puede **extender el cronograma** y **aumentar los costos** de desarrollo.

> **Para el parcial, si te preguntan:** *¿Qué es un prototipo de descubrimiento?*
> Es un modelo a pequeña escala, representativo o funcional, de los requisitos de los usuarios, construido rápido y solo sobre las áreas que no están claras, para descubrir o verificar esos requisitos. Se basa en que los usuarios reconocen sus requisitos cuando los ven, y normalmente se descarta al terminar el sistema.

---

## 2. 🟡 Técnica 7 — JRP (Joint Requirements Planning)

La técnica clásica del relevamiento son las **entrevistas separadas** a usuarios finales y gerentes. Pero muchos analistas y organizaciones descubrieron su gran falla: **las entrevistas separadas suelen llevar a hechos, opiniones y prioridades en conflicto** — el administrador dice una cosa, el encargado otra, y vos tenés que reconciliarlas después, sin ellos en la sala — además del tiempo y esfuerzo que consumen. Por eso muchas organizaciones usan la **sesión de trabajo grupal** como sustituto de las entrevistas. Un ejemplo es el JRP.

**JRP** (*Joint Requirements Planning*, planificación conjunta de requisitos) es un proceso en el que se conducen **reuniones grupales altamente estructuradas** para **analizar problemas y definir requisitos**. Es un subconjunto de una técnica más amplia, **JAD** (*Joint Application Development*, desarrollo conjunto de aplicaciones), que abarca todo el proceso de desarrollo de sistemas.

Las técnicas JRP y JAD son cada vez más comunes en planificación y análisis de sistemas para obtener **consenso grupal** sobre problemas, objetivos y requisitos. Requieren **capacitación extensa** para funcionar como está previsto; a cambio, pueden **reducir significativamente el tiempo de relevamiento** en una o más fases del ciclo de vida.

El valor está en el cruce: cuando los procesos son fáciles de pensar pero difíciles de implementar porque las áreas no se adaptan, poner a las áreas en la misma sala **favorece el consenso y hace aflorar los conflictos** antes, no después de haber escrito los requisitos.

### Participantes

Una sesión de JRP incluye varios participantes y roles. **Cada uno debe asistir y participar activamente durante toda la sesión.** Son: el **sponsor**, el **facilitador**, los **usuarios y gerentes**, el **escriba** y el **personal de IT**.

Esta clase desarrolla el rol del sponsor; los otros cuatro quedan nombrados (glosa: el facilitador conduce la sesión; el escriba registra; usuarios y gerentes aportan el conocimiento del negocio; IT aporta la mirada técnica).

**El sponsor.** Toda sesión de JRP exitosa requiere **una sola persona** que actúe como su *campeón*: el **sponsor**. Normalmente es alguien de la **alta gerencia del negocio — no de IT ni de sistemas —** con autoridad que abarca los distintos departamentos y usuarios involucrados. Da apoyo total al proyecto alentando a los usuarios designados a participar activa y voluntariamente. En el enfoque de compromiso incremental (glosa: el proyecto se aprueba por etapas, con puntos de decisión de seguir o no), es el sponsor quien suele tomar las **decisiones finales de seguir o no seguir** (*go / no-go*). Tiene un rol visible: **abre la sesión** con las presentaciones, muchas veces hace los comentarios de cierre, y trabaja con el líder de JRP para planificar la sesión ayudando a identificar a las personas que deben participar.

En el caso: el sponsor sería el dueño o el administrador general — el que puede sentar en la misma mesa a los encargados de veinte playas y hacer que vengan.

> **Para el parcial, si te preguntan:** *¿Qué es JRP y qué problema de las entrevistas resuelve?*
> JRP (Joint Requirements Planning) es un proceso de reuniones grupales altamente estructuradas para analizar problemas y definir requisitos, subconjunto de JAD. Resuelve la gran falla de las entrevistas separadas: que producen hechos, opiniones y prioridades en conflicto y consumen mucho tiempo. Busca consenso grupal.

> **Para el parcial, si te preguntan:** *¿Quién es el sponsor de una sesión de JRP?*
> Una sola persona de la alta gerencia del negocio (no de IT), con autoridad sobre los departamentos involucrados, que apoya el proyecto, alienta a los usuarios a participar, toma las decisiones de seguir o no, abre la sesión y ayuda a planificarla.

---

## 3. 🔴 Síntesis: las siete técnicas, cuándo cada una

Con las siete en la mano, esta es la tabla que tenés que poder reconstruir de memoria:

| Técnica | Usala cuando… | Te da | Te cuesta | Punto ciego |
|---|---|---|---|---|
| **1. Revisión de documentos** | Arrancás. Siempre primero. | Hechos sin sesgo, el mapa (organigrama), el historial | Casi nada | Muestra lo que *debería* pasar, no lo que pasa |
| **2. Investigación** | No conocés el dominio; querés saber cómo lo resolvieron otros | Vocabulario, funcionalidades estándar, software existente | Poco | No te dice nada de *este* cliente |
| **3. Observación** | Dudás de lo que te dijeron; la tarea es difícil de explicar; necesitás medir | Datos confiables, mediciones, el entorno físico, lo que se omite | Tu tiempo; agenda | La gente actúa distinto cuando la mirás; mide el hoy, no el "qué pasaría si" |
| **4. Cuestionario** | Son muchos; necesitás tabular; querés anonimato | Volumen, uniformidad, hechos reales sin el jefe al lado | Diseñarlo bien | Pocas respuestas; no podés repreguntar ni aclarar |
| **5. Entrevista** | Necesitás profundidad, repreguntar, adaptar; el que decide | Alcance, contexto, requisitos, compromiso | Tiempo y dinero; depende de tu habilidad | Sesgo del entrevistado; hechos en conflicto entre entrevistas |
| **6. Prototipo de descubrimiento** | Los usuarios no pueden describir lo que quieren hasta verlo | Requisitos que no salen hablando; factibilidad temprana | Puede extender cronograma y costos | Expectativas irreales sobre lo que se mostró |
| **7. JRP** | Hay varias áreas con intereses cruzados; necesitás consenso | Conflictos resueltos en la sala; menos tiempo total | Capacitación; un sponsor que convoque | Sin sponsor, no viene nadie |

Y el orden natural en que se combinan:

```text
 2. Investigación ─┐
                   ├──►  1. Documentos  ──►  5. Entrevista al que   ──►  4. Cuestionario a
 (si no conocés    │        (siempre          decide (define el          los muchos (dentro
  el dominio)      │         antes)            alcance)                   del alcance)
                   │                              │
                   │                              ├──►  5. Entrevistas a los que operan
                   │                              │
                   │                              └──►  3. Observación (valida, mide)
                   │
                   └──►  6. Prototipo / 7. JRP: cuando la entrevista sola no alcanza
```

---

## 4. 🔴 El plan de relevamiento: qué es y qué tiene que tener

Un **plan de relevamiento** es el documento que le presentás al gerente de proyecto **antes** de relevar, y que responde: **con quién voy a hablar, qué le voy a preguntar, qué información me falta, y con qué técnica saco cada pedazo.** El gerente lo evalúa y lo aprueba —o te lo devuelve— antes de que gastes una hora de nadie.

Lo que tiene que contener:

1. **Roles de la consultora.** Quién hace qué del lado tuyo. Como mínimo: quien releva (el **analista de requisitos**: entrevista, observa, revisa documentos, escribe los requisitos), quien coordina (el **gerente de proyecto**: agenda las reuniones, pide la documentación, recibe y aprueba el plan) y alguien **técnico** que orbite el proceso para bajar a tierra: si aparece un requisito imposible o sin sentido desde lo técnico, se involucra ahí. Los roles son **funciones**, no necesariamente personas distintas: en un proyecto chico, dos personas cubren varios.
2. **Roles del cliente.** Los stakeholders y usuarios de la clase 01, aplicados: quién decide, quién opera, quién usa. **Granulares, no genéricos**: no "empleados", sino "administrador general", "encargado de playa", "conductor con abono mensual", "conductor por hora".
3. **Tareas: cómo vas a relevar.** Ordenadas como un **plan de acción**, por etapas.
4. **Técnicas, la mayor diversidad posible, cada una con una prioridad** (alta / media / baja). Poner prioridad es reconocer que **no se puede hacer todo junto**.
5. **Ventajas de la técnica que considerás más provechosa** para este proyecto.
6. **Por qué.** Cada decisión de arriba, fundamentada.

---

## 5. 🔴 Cómo se razona un plan

No se arma listando técnicas. Se arma **desde los huecos de información**:

```text
 ¿QUÉ NO SÉ?              ¿QUIÉN LO SABE           ¿CON QUÉ TÉCNICA           ¿POR QUÉ ESA
 (hueco de                 O DÓNDE ESTÁ?            LO SACO?                   Y NO OTRA?
  información)             (rol del cliente,        (una de las siete)         (fundamentación)
                            documento, lugar)
        │                        │                        │                        │
        └────────────────────────┴────────────────────────┴────────────────────────┘
                                          │
                              ¿EN QUÉ ORDEN? ¿CON QUÉ PRIORIDAD?
```

Para cada hueco:

- **¿Qué no sé?** Leé el enunciado o el dominio con lápiz: lo que **no dice**, es un hueco. "Suman 2.000 plazas" — ¿cuántas tienen hoy? "Duplica los locales" — ¿entonces son 20 hoy? **No asumas: lo que no está, se pregunta y se confirma.** (Cinco puestos de recepción no son cinco recepcionistas.)
- **¿Quién lo sabe?** El administrador sabe lo macro: locales, presupuesto, alcance. El encargado sabe lo micro: la hora pico, qué falla, qué agregaría. El conductor sabe cómo paga y qué le molesta. El cuaderno sabe qué se anotó. Cada hueco tiene un dueño.
- **¿Con qué técnica?** La que responde *ese* tipo de pregunta a *esa* persona (Parte 2 §3). Datos exactos del que decide → entrevista. Cómo se hace de verdad → observación. Qué piensan miles → cuestionario. Qué existe ya → documentos.
- **¿Por qué esa?** Acá está la nota. "Quiero entrevistar al administrador **porque hay un hueco de información sobre X**, y uso entrevista y no cuestionario **porque necesito repreguntar y es una sola persona**." Eso es un plan. "Entrevista al administrador" solo, es una lista.
- **¿En qué orden?** Etapa previa de diagnóstico: documentación e investigación. Después, entrevistas — de macro a micro o de micro a macro, pero **decidido**. Después, lo que depende de las entrevistas: el cuestionario (dentro del alcance) y la observación (para validar y medir). Cerrar verificando con el usuario.

---

## 6. 🔴 Con qué criterios se corrige un plan

Los criterios con los que se evalúa un plan de relevamiento, con evidencia de cómo se aplican:

1. **Fundamentación por técnica y por dominio.** Las técnicas elegidas pueden estar perfectas — "entrevista individual, observación directa" — y aun así faltar lo principal: **por qué esas herramientas en ese dominio específico, y qué datos querés sacar con cada una.** Se corrige el criterio, no la lista.
2. **Cada entrevista con su objetivo y sus ítems.** "Una entrevista bastante larga al gerente de operaciones" no alcanza: ¿por qué? ¿qué información? ¿cuál es el núcleo de esa entrevista? ¿cuáles son los ítems que la completan? (Parte 4 §4.2.)
3. **Cada documento con qué esperás encontrar.** "Análisis de documentación existente: historial de compras" — ¿qué buscás ahí? Si necesitás saber si en la Cyber Week explotan las compras y no tenés el dato real de otro modo, entonces el historial de compras está justificado. Sin eso, es un ítem decorativo.
4. **Alcance: no preguntar nada fuera de lo que se puede ofrecer.** Todo lo que preguntes tiene que ser acorde a lo que el cliente ya te dijo que va a comprometer. Preguntar por lo que no va a existir genera **falsas expectativas**. (Parte 3 §5.)
5. **Medible, no subjetivo.** "Demora larga" → ¿qué es demora larga? El tiempo se mide; no puede ser lo que la persona cree que esperó. (Parte 1 §5.1; Parte 2 §4.)
6. **Orden como plan de acción.** Etapa previa de diagnóstico (pedir documentación: facturas al de compras, remitos al de distribución, la planilla a quien la lleva), y que esa documentación **llegue antes** de la entrevista. Así el analista se sienta con el cliente sabiendo algo de la organización, y se ahorra otra reunión con otra minuta. Y el orden entre entrevistas —macro a micro o al revés— **explícito y justificado**.
7. **Prioridad por técnica.** Alta y media, al menos: define qué se hace primero cuando no se puede hacer todo.
8. **Sobre el uso de IA.** No está prohibido; se puede usar como guía. Pero el criterio tiene que ser del grupo, y hay que poder **fundamentarlo oralmente**: si en la defensa se nota que dominás las herramientas de relevamiento y el dominio del negocio, está bien; si solo sabés lo que la IA escribió, no. Y **lo que se dice en la defensa tiene que quedar escrito** en el documento.
9. **Al equipo de IT del cliente se le pregunta por el sistema existente.** De dónde salió, si lo implementaron porque alguien lo pidió o por iniciativa interna, quién lo pidió, qué necesidad quería cubrir cuando se originó, y cuál es el problema que **no** está resolviendo y por el que te contratan. (Parte 1 §6.2c.)
10. **No asumir.** Ni del enunciado ni del entrevistado. Lo que no está dicho, se pregunta.

> **Para el parcial, si te preguntan:** *¿Qué debe contener un plan de relevamiento?*
> Los roles involucrados de la consultora y del cliente, las tareas a realizar ordenadas como plan de acción, la mayor diversidad de técnicas de relevamiento con una prioridad para cada una, las ventajas de la técnica más provechosa, y la fundamentación de cada decisión: por qué esa técnica, para ese rol, en ese dominio, y qué información se busca obtener.

> **Para el parcial, si te preguntan:** *¿Por qué no alcanza con listar las técnicas en un plan de relevamiento?*
> Porque la elección de la técnica es parte del análisis: cada técnica responde un tipo de pregunta y no otro. Sin fundamentar por qué esa técnica sirve para ese hueco de información en ese dominio, y qué dato se busca, el plan no demuestra criterio y puede elegir la técnica equivocada (como observar para saber si habría demanda de una parada de tren que no existe).

---

## 7. 🔴 El caso resuelto: plan de relevamiento para la gestión de estacionamientos

Todo lo anterior aplicado al caso de la Parte 1. Es *un* plan defendible; otro con distinto orden o prioridades es igualmente válido **si está justificado**.

### 7.1 Roles

**Consultora:**

| Rol | Qué hace en este plan |
|---|---|
| Analista de requisitos | Pide y revisa la documentación, prepara y conduce las entrevistas, observa, diseña el cuestionario, escribe minutas y requisitos |
| Gerente de proyecto | Agenda las reuniones con el cliente, recibe y aprueba este plan, controla tiempos y costos del relevamiento |
| Desarrollador (perfil técnico) | Orbita el proceso: evalúa factibilidad de lo que surge; se involucra si aparece un requisito técnicamente imposible o sin sentido |

**Cliente:**

| Rol | Qué sabe | Nivel |
|---|---|---|
| Administrador general | Cuántos locales y plazas, cómo se cobra, presupuesto, alcance, qué quiere ver | Macro — decide |
| Encargado de playa (uno por local) | La operación diaria: horas pico, fechas de saturación, cómo cobra y anota, qué le falta | Micro — opera |
| Conductor por hora / por día / con abono mensual | Cómo paga, qué le molesta de la espera, si usaría otro medio | Usuario final |

El organigrama, si existe, puede revelar roles que el enunciado no nombra (quien lleva la contabilidad de abonos, por ejemplo). Se pide primero.

### 7.2 Huecos de información y técnica para cada uno

| Hueco de información | Quién lo tiene | Técnica | Por qué esa | Prioridad |
|---|---|---|---|---|
| Cuántas playas y plazas hay **hoy** (el enunciado da solo lo que se suma) | Administrador | Entrevista | Dato exacto de una sola persona; hay que repreguntar (¿se suman o reemplazan?) | Alta |
| Cómo se cobra en cada modalidad; medios de pago actuales y a agregar | Administrador | Entrevista | Define el alcance; sin esto no se puede armar el cuestionario | Alta |
| Presupuesto, roles que quieren en el sistema, la métrica que más les importa | Administrador | Entrevista | Decisiones de negocio; solo el que decide las tiene | Alta |
| Qué registros existen: cuadernos de ingreso/egreso, planillas de abonos, comprobantes | Los documentos mismos | Revisión de documentos | Están; no cuestan tiempo de nadie; preparan la entrevista y evitan una segunda reunión | Alta — **antes** de entrevistar |
| Cómo funcionan sistemas de estacionamiento existentes | Fuera de la empresa | Investigación | La consultora no conoce el dominio; da vocabulario y funcionalidades estándar | Alta — al inicio, corta |
| Cómo es el día a día en la playa: horas pico, fechas de saturación, qué falla, qué agregaría | Encargado | Entrevista individual | Es el que interactúa con los clientes; viene con opiniones y solicitudes concretas. Individual: no en presencia de pares | Alta |
| Cuánto tarda realmente cobrar y anotar; cuánto se degrada en pico | La playa a las 8 | Observación (directa) del encargado | Lo que se puede medir se mide; valida lo que el encargado contó; primero en horario normal, después en pico | Media |
| Cómo pagan los conductores, qué les molesta, si usarían débito automático o app | Conductores (miles) | Cuestionario | Son demasiados para entrevistar; formato fijo para tabular; anónimo. **Después** de la entrevista al administrador, solo dentro del alcance | Media |

**Técnica más provechosa: la entrevista al administrador.** Ventajas para este proyecto: es la única fuente de los datos que definen el alcance (locales, medios de pago, presupuesto); permite repreguntar sobre lo que el enunciado deja ambiguo; genera el compromiso del que decide; y abre la puerta a las demás técnicas (permiso para hablar con los encargados y observar). Sin ella, el cuestionario no se puede diseñar y la observación no sabe qué buscar.

### 7.3 Plan de acción

```text
 ETAPA 0 — Investigación del dominio              (antes de tocar al cliente)
   Cómo cobran las playas con máquina de tickets, las apps de estacionamiento,
   los sistemas de abonos. Objetivo: llegar sabiendo qué es estándar.

 ETAPA 1 — Pedir documentación                    (por el gerente de proyecto)
   Organigrama → quién es quién.
   Cuadernos/registros de ingreso-egreso de 2-3 playas → qué se anota y qué no.
   Planilla de abonos mensuales → cuántos abonados, cómo se controla el vencimiento.
   Comprobantes de cobro → qué medios de pago hay de verdad.
   Objetivo: entrar a la entrevista con el mapa puesto.

 ETAPA 2 — Entrevista al administrador general    (30 min, guía de la Parte 4 §4.2)
   Objetivo: cerrar los datos macro y el ALCANCE. Pedir permiso para las etapas 3 y 4.
   → Minuta a las 24 hs.

 ETAPA 3 — Encargados de playa                    (macro → micro)
   Entrevistas individuales a 3-4 encargados (playas grandes, chicas, céntricas).
   Objetivo: la operación real, la hora pico, qué falla, qué agregarían.
   Observación directa de una playa: martes a media mañana (carga normal),
   después lunes 8:00 (pico). Con reloj: tiempo de cobro y anotación por auto.
   → Minutas.

 ETAPA 4 — Cuestionario a conductores             (solo dentro del alcance de la Etapa 2)
   Formato fijo con aclaración opcional. Distribución: QR en cada playa.
   Ventana: 10 días. Métrica: tasa de respuesta.

 ETAPA 5 — Consolidación y verificación
   Cruzar lo que dijo el administrador, lo que dijeron los encargados, lo que se
   midió y lo que respondieron los conductores. Volver al administrador con las
   diferencias: verificar con el usuario antes de escribir un requisito.
```

Por qué macro a micro y no al revés: el administrador define el alcance y da el permiso; sin eso, ni la observación ni el cuestionario están autorizados ni acotados. La ruta inversa —arrancar por los encargados para tener el crudo— es defendible en un dominio donde el que decide está lejos de la operación; acá el administrador está cerca y es la puerta.

---

## 8. ✅ Checkpoint — Parte 5

Sin respuestas. Las respuestas van al complemento.

1. ¿Qué es un prototipo de descubrimiento y en qué se diferencia de prototipar en diseño?
2. ¿Por qué el prototipo de descubrimiento es "descartable"? Dá tres características que lo hacen así.
3. ¿Qué desventaja comparten el prototipo de descubrimiento y el cuestionario mal secuenciado?
4. ¿Cuál es la gran falla de las entrevistas separadas, y qué la resuelve?
5. Definí JRP y JAD, y decí cuál contiene a cuál.
6. Nombrá los cinco participantes de una sesión de JRP y describí el rol del sponsor. ¿Por qué no debería ser de IT?
7. Reconstruí de memoria la tabla de las siete técnicas: cuándo, qué te da, punto ciego.
8. ¿Qué seis cosas tiene que contener un plan de relevamiento?
9. Explicá el razonamiento "desde los huecos de información" con un ejemplo distinto al del caso.
10. De los diez criterios de corrección, ¿cuáles tres son los que más se pasaron por alto en los planes que viste? ¿Por qué creés que pasa?
11. En el caso, ¿por qué la revisión de documentos tiene prioridad alta si no aporta ningún requisito nuevo por sí sola?
12. Rehacé el plan de acción del caso con la ruta micro → macro (encargados primero). ¿Qué cambia, qué se gana, qué se pierde?
13. "Vamos a usar IA para armar el plan." ¿Qué está permitido y qué se corrige?

## Cierre de la unidad

Con esto termina la clase 03. Lo que sigue en la materia: pros, contras, costos y consideraciones de las técnicas, con simulacro de entrevista — presencial.

---

**FIN DE LA PARTE 5 — Apunte Maestro clase03 · Técnicas de Elicitación**
**FIN DEL APUNTE MAESTRO — clase03**
