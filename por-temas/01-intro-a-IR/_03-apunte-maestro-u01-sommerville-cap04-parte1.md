# 📚 APUNTE MAESTRO — U1: Ingeniería de Requisitos (fundamentos) — Parte 1

**Materia:** Ingeniería de Requisitos (electiva)
**Unidad:** 1
**Parte:** 1 de 2 — *Qué son los requerimientos y cómo se escriben*
**Alcance de esta parte:** requerimientos de usuario y de sistema · funcionales y no funcionales · el documento de requerimientos (SRS) · técnicas de especificación.
**La Parte 2 cubre:** el proceso completo de la ingeniería de requisitos — elicitación y análisis, validación y gestión de cambios.

---

## 0. El mapa completo antes de arrancar

Esta unidad es la base de TODA la materia. Acá se define el vocabulario que vas a usar en cada unidad que sigue, en cada parcial y en cada TP. El territorio completo se ve así:

```
                    INGENIERÍA DE REQUISITOS (RE)
                              │
        ┌─────────────────────┴─────────────────────┐
        │                                           │
   EL PRODUCTO                                 EL PROCESO
   (qué son y cómo se escriben)                (cómo se obtienen y mantienen)
        │                                           │
   ├─ Requerimientos de usuario                ├─ Estudio de factibilidad
   ├─ Requerimientos de sistema                ├─ Elicitación y análisis
   ├─ Funcionales                              │    (entrevistas, escenarios,
   ├─ No funcionales                           │     casos de uso, etnografía)
   ├─ El documento SRS                         ├─ Especificación
   └─ Técnicas de especificación               ├─ Validación
        (lenguaje natural, estructurada,       └─ Gestión de requerimientos
         tablas, notaciones gráficas)               (los requerimientos CAMBIAN)
        │                                           │
   ◄── PARTE 1 (estás acá) ──►                ◄── PARTE 2 ──►
```

**La idea central de toda la unidad, en una frase:** los requerimientos son la descripción de **qué** debe hacer un sistema (los servicios que presta) y **bajo qué restricciones** debe operar — y la ingeniería de requisitos es el proceso de **descubrirlos, analizarlos, documentarlos y verificarlos**.

Todo lo demás es desarrollar esa frase con precisión. Vamos.

---

## 1. El caso que nos acompaña toda la unidad: MHC-PMS 🔴

Antes de una sola definición, el problema concreto.

Una autoridad de salud necesita un sistema de información para gestionar pacientes que reciben tratamiento por problemas de salud mental. Lo vamos a llamar **MHC-PMS** (*Mental Health Care – Patient Management System*, sistema de gestión de pacientes de salud mental). El contexto real del que nace:

- Hay **múltiples clínicas** distribuidas; un mismo paciente puede atenderse en cualquiera de ellas.
- Trabajan con él **recepcionistas médicos** (dan de alta pacientes y gestionan turnos), **enfermeros** (cargan historia clínica, coordinan consultas), **médicos** (diagnostican, prescriben medicación) y **gerentes** (necesitan reportes de gestión y estadísticas).
- Particularidad clave del dominio: los pacientes con problemas de salud mental a veces están **confundidos** — tienen turno en una clínica y se presentan en otra. El sistema tiene que bancarse esa realidad.
- La información es **extremadamente sensible**: historia clínica psiquiátrica. La privacidad no es un "nice to have", es obligación legal.

Guardá este caso en la cabeza. Cada concepto de la unidad se va a apoyar en él: cuando definamos "requerimiento funcional", el ejemplo va a ser una búsqueda de turnos del MHC-PMS; cuando definamos "requerimiento externo", va a ser la ley de privacidad que este sistema debe cumplir.

Más adelante aparece un **segundo caso** más chico (una bomba de insulina embebida) para las técnicas de especificación — lo presento cuando llegue su turno.

---

## 2. ¿Qué es un requerimiento? ¿Qué es la ingeniería de requisitos? 🔴

Pensá en la autoridad de salud del caso. Quiere el MHC-PMS. ¿Qué tiene que pasar entre "lo quiero" y "un equipo lo construye bien"? Alguien tiene que responder con precisión: ¿qué debe hacer exactamente el sistema? ¿qué restricciones tiene? Eso son los requerimientos.

> **Definición** — Los **requerimientos** de un sistema son las descripciones de **lo que el sistema debe hacer**: los **servicios que provee** y las **restricciones sobre su operación**. Reflejan las necesidades del cliente para un sistema que cumple cierto propósito (controlar un dispositivo, hacer un pedido, encontrar información).

> **Definición** — La **ingeniería de requisitos** (**RE**, *Requirements Engineering*) es el proceso de **descubrir, analizar, documentar y verificar** esos servicios y restricciones.

Fijate que "requerimiento" abarca dos cosas distintas que conviven: **servicios** (el sistema *hace* algo: busca turnos, genera reportes) y **restricciones** (el sistema debe *cumplir* algo: responder en menos de X segundos, respetar la ley de privacidad). Esta dualidad reaparece en la sección 4 como funcionales vs. no funcionales.

### 2.1 El problema con la palabra "requerimiento"

En la industria, el término se usa de manera **inconsistente**, y no es descuido: hay una razón estructural. Seguí este escenario:

1. Una organización quiere **licitar** el desarrollo de un sistema grande. Para que varios contratistas puedan **ofertar soluciones distintas**, tiene que describir su necesidad de forma **abstracta**, sin predefinir la solución. Ese documento se llama "los requerimientos".
2. Se adjudica el contrato. Ahora el contratista debe escribir una **definición detallada** del sistema, para que el cliente entienda y pueda **validar** qué va a hacer el software. Ese documento también se llama "los requerimientos".

Dos documentos con niveles de detalle totalmente distintos, mismo nombre. Muchos problemas de la ingeniería de requisitos nacen de **no separar con claridad estos niveles de descripción**. La solución es darles nombre propio — y ese es el próximo concepto, uno de los más evaluables de la unidad.

---

## 3. Los dos niveles: requerimientos de usuario y de sistema 🔴

> **Definición** — Los **requerimientos de usuario** son declaraciones, en **lenguaje natural más diagramas**, de qué servicios se espera que el sistema provea a sus usuarios y bajo qué restricciones debe operar. Son abstractos, de alto nivel.

> **Definición** — Los **requerimientos de sistema** son descripciones **más detalladas** de las funciones, servicios y restricciones operacionales del software. El documento de requerimientos de sistema (a veces llamado **especificación funcional**) debe definir **exactamente qué se va a implementar**, y puede formar parte del **contrato** entre comprador y desarrolladores.

### 3.1 El ejemplo que fija el concepto (MHC-PMS)

Un requerimiento de usuario del MHC-PMS, en una sola oración:

> **RU-1.** El MHC-PMS debe generar reportes mensuales de gestión que muestren el costo de las drogas prescriptas por cada clínica durante ese mes.

General, entendible por un gerente que no sabe (ni le importa) cómo se implementa. Ahora mirá en qué se **expande** cuando bajamos al nivel de sistema:

> **RS-1.1.** El último día hábil de cada mes se genera un resumen de las drogas prescriptas, su costo y las clínicas prescriptoras.
> **RS-1.2.** El sistema genera automáticamente el reporte para impresión después de las 17:30 del último día hábil del mes.
> **RS-1.3.** Se crea un reporte por cada clínica, listando los nombres de cada droga, el total de prescripciones, la cantidad de dosis prescriptas y el costo total de las drogas prescriptas.
> **RS-1.4.** Si una droga está disponible en distintas unidades de dosis (p. ej. 10 mg, 20 mg), se crean reportes separados por cada unidad de dosis.
> **RS-1.5.** El acceso a los reportes de costos queda restringido a los usuarios autorizados listados en una lista de control de acceso de gestión.

**Un** requerimiento de usuario se expandió en **cinco** de sistema, cada uno con información específica y verificable: horarios concretos, contenido exacto del reporte, reglas de acceso. Esa expansión 1→N es el patrón general.

### 3.2 ¿Por qué dos niveles? Porque hay dos públicos

Los niveles no son burocracia: **comunican a lectores distintos que usan la información de manera distinta**.

| Nivel | Quiénes lo leen | Qué les importa |
|---|---|---|
| **Requerimientos de usuario** | Gerentes del cliente, usuarios finales, ingenieros del cliente, gerentes del contratista, arquitectos del sistema | Entender QUÉ necesita el negocio, sin detalle de implementación |
| **Requerimientos de sistema** | Usuarios finales, ingenieros del cliente, arquitectos del sistema, **desarrolladores de software** | Saber con precisión QUÉ va a hacer el sistema, porque lo van a implementar o porque afecta sus procesos de negocio |

Fijate el solapamiento: los usuarios finales y los arquitectos leen ambos. Los que cambian son los extremos — el gerente del cliente no lee el detalle; el desarrollador no puede trabajar sin él.

### 📝 Para el parcial, si te preguntan

**"Diferencie requerimientos de usuario y de sistema."**
Los requerimientos de usuario son declaraciones abstractas de alto nivel, en lenguaje natural y diagramas, de los servicios y restricciones del sistema, orientadas a lectores no técnicos (gerentes, clientes). Los requerimientos de sistema son descripciones detalladas de las funciones, servicios y restricciones, definen exactamente qué se implementa, pueden integrar el contrato, y están orientados a quienes diseñan e implementan. Un requerimiento de usuario típicamente se expande en varios requerimientos de sistema.

**"¿Qué es la ingeniería de requisitos?"**
Es el proceso de descubrir, analizar, documentar y verificar los servicios que un sistema debe proveer y las restricciones bajo las cuales debe operar.

### 3.3 Una aclaración de época: la visión "tradicional" vs. la ágil ⚠️

Esta unidad presenta la visión **tradicional**: una fase identificable de ingeniería de requisitos ANTES de implementar, cuyo resultado es un documento de requerimientos. Los métodos **ágiles** proponen otra cosa: elicitar requerimientos **al mismo tiempo** que se desarrolla el sistema. Para sistemas grandes, el enfoque concurrente ágil sigue siendo raro — la fase previa con documento sigue vigente en licitaciones, sistemas críticos y contratos.

⚠️ **En la práctica** de la industria actual conviven ambos mundos, y en muchos equipos el documento formal completo es la excepción. **Para el examen:** respondé con el enfoque de la materia — proceso de RE con documento de requerimientos como salida — salvo que la pregunta pida explícitamente la comparación con ágil.

🕳️ **Madriguera — Metodologías ágiles / XP**
XP (*Extreme Programming*) es un método ágil donde los requerimientos se capturan incrementalmente como *user stories* (historias de usuario) escritas en tarjetas, y el usuario las prioriza para cada incremento. Aparece de nuevo en la sección del documento SRS y en la Parte 2 (gestión de cambios).
*Volvé al camino — las metodologías ágiles se profundizan aparte, otro día.*

---

## 4. Requerimientos funcionales y no funcionales 🔴

La clasificación más importante de la unidad. Arrancamos por el lado fácil y concreto.

### 4.1 Requerimientos funcionales

Tres requerimientos reales del MHC-PMS:

> **RF-1.** Un usuario debe poder buscar en las listas de turnos de **todas** las clínicas.
> **RF-2.** El sistema debe generar cada día, para cada clínica, la lista de pacientes que se espera que asistan a turnos ese día.
> **RF-3.** Cada miembro del personal que usa el sistema debe identificarse unívocamente por su número de empleado de ocho dígitos.

¿Qué tienen en común? Los tres describen **algo que el sistema hace**: un servicio, una reacción a una entrada, un comportamiento.

> **Definición** — Los **requerimientos funcionales** son declaraciones de los **servicios** que el sistema debe proveer, de **cómo debe reaccionar a entradas particulares** y de **cómo debe comportarse en situaciones particulares**. En algunos casos, también declaran explícitamente lo que el sistema **NO** debe hacer.

Dos observaciones sobre los ejemplos, que son contenido en sí mismas:

- **El nivel de detalle varía.** Compará RF-1 (general: "buscar turnos") con RF-3 (ultra específico: "ocho dígitos"). Ambos son legítimos; los requerimientos funcionales van desde lo general hasta reflejar formas de trabajo locales o sistemas existentes de la organización.
- **Dependen del contexto:** del tipo de software, de los usuarios esperados y del enfoque de la organización al escribir requerimientos.

#### El peligro nº 1: la imprecisión

La **imprecisión en la especificación es causa de muchísimos problemas** de la ingeniería de software. El mecanismo es este, y vale la pena entenderlo como sistema:

```
Requerimiento ambiguo
        │
        ▼
El desarrollador lo interpreta del modo
que SIMPLIFICA su implementación        ◄── natural, no malicia
        │
        ▼
No era lo que el cliente quería
        │
        ▼
Nuevos requerimientos + cambios al sistema
        │
        ▼
Entrega demorada + costos más altos
```

**El caso concreto, con RF-1.** ¿Por qué existe "buscar en todas las clínicas"? Racionalidad del dominio: los pacientes confundidos a veces van a una clínica distinta de la del turno. Si tienen turno en cualquier lado, se los registra como presentes, sin importar la clínica. El personal médico que pidió esto espera que "buscar" signifique: *dado el nombre del paciente, el sistema lo busca en todos los turnos de todas las clínicas*. Pero eso **no está explícito** en el requerimiento. Un desarrollador puede implementar razonablemente: *el usuario elige una clínica y busca ahí* — más simple para él, más pasos de entrada y más tiempo para el usuario que atiende a un paciente confundido. Mismo texto, dos sistemas distintos. Eso es imprecisión.

#### Completitud y consistencia

En principio, la especificación funcional de un sistema debería ser:

- **Completa:** todos los servicios que el usuario requiere están definidos.
- **Consistente:** los requerimientos no tienen definiciones contradictorias.

En la práctica, para sistemas grandes y complejos, es **prácticamente imposible** lograr ambas. Dos razones:

1. Es fácil cometer errores y omisiones escribiendo especificaciones de sistemas complejos.
2. Los sistemas grandes tienen muchos **stakeholders** *(término nuevo: cualquier persona o rol afectado de alguna manera por el sistema — usuarios, gerentes, reguladores, etc.; se desarrolla a fondo en la Parte 2)*, con necesidades distintas y muchas veces **inconsistentes entre sí**. Las inconsistencias no son obvias al especificar; se incluyen en el documento y los problemas emergen recién en el análisis profundo — o después de entregar.

Esto no es una licencia para no intentarlo: es la razón por la que existen la validación y la gestión de requerimientos (Parte 2).

🕳️ **Madriguera — Requerimientos de dominio**
Existe una tercera categoría transversal: requerimientos que derivan del **dominio de aplicación** en sí (no de necesidades puntuales de usuarios) — pueden ser funcionales nuevos, restringir los existentes o definir cómo deben hacerse ciertos cálculos. Su problema típico: los ingenieros de software no siempre entienden el dominio y no detectan cuándo falta o entra en conflicto un requerimiento de dominio.
*Volvé al camino — con saber que existen y su riesgo alcanza para esta unidad.*

### 4.2 Requerimientos no funcionales

> **Definición** — Los **requerimientos no funcionales** son **restricciones** sobre los servicios o funciones que ofrece el sistema. Incluyen restricciones de tiempo, restricciones sobre el proceso de desarrollo y restricciones impuestas por estándares. A menudo aplican al sistema **como un todo**, no a features o servicios individuales.

La palabra clave es **restricción**. No dicen qué hace el sistema; acotan CÓMO lo hace, o cómo se lo desarrolla. Pueden referirse a:

- **Propiedades emergentes** del sistema: confiabilidad, tiempo de respuesta, ocupación de memoria. *(Emergente = propiedad que surge del sistema completo funcionando, no de una pieza aislada — no podés señalar el módulo "confiabilidad".)*
- **Restricciones de implementación:** capacidades de los dispositivos de E/S, representaciones de datos en las interfaces con otros sistemas.

#### Por qué los no funcionales suelen ser MÁS críticos que los funcionales 🔴

Argumento evaluable y contraintuitivo, prestale atención:

- Si una **función** no satisface del todo, los usuarios suelen encontrar **workarounds** *(término nuevo: rodeo o solución alternativa improvisada para sortear una limitación)* y el sistema sigue siendo usable.
- Si falla un **no funcional**, el sistema entero puede volverse **inusable**: un sistema de aeronave que no cumple sus requerimientos de confiabilidad **no se certifica** como seguro para operar; un sistema de control embebido que no cumple sus requerimientos de performance hace que las funciones de control **no operen correctamente**. No hay workaround para "el avión no vuela legalmente".

#### Los no funcionales no viven en un componente

Los funcionales suelen poder rastrearse a componentes concretos ("el módulo de formateo implementa los reportes"). Los no funcionales suelen estar **difundidos por todo el sistema**, por dos razones:

1. Pueden afectar la **arquitectura completa**, no componentes individuales — para cumplir performance quizás tenés que organizar el sistema minimizando comunicaciones entre componentes.
2. Un solo no funcional (p. ej., de seguridad) puede **generar varios funcionales nuevos** (servicios de autenticación) y además **restringir requerimientos existentes**.

Y esto revela algo más general: **los requerimientos no son independientes** — uno genera o restringe a otros. Un requerimiento de usuario sobre seguridad ("solo usuarios autorizados acceden") parece no funcional, pero al desarrollarlo en detalle genera requerimientos claramente funcionales (incluir facilidades de autenticación de usuarios). La frontera funcional/no funcional es **menos nítida** de lo que sugieren las definiciones — las definiciones son el mapa, no el territorio.

#### La clasificación de los no funcionales 🔴

De dónde vienen los no funcionales: de necesidades de usuarios, restricciones de presupuesto, políticas organizacionales, necesidad de interoperar con otro software o hardware, y factores externos como regulaciones de seguridad o legislación de privacidad. Se clasifican por **origen** en tres familias:

```
                        Requerimientos No Funcionales
                                    │
        ┌───────────────────────────┼───────────────────────────┐
        │                          │                           │
   de PRODUCTO               ORGANIZACIONALES               EXTERNOS
   (comportamiento           (políticas y procedimientos   (factores externos
    del software)             de cliente y desarrollador)   al sistema y su
        │                          │                        desarrollo)
   ├─ Usabilidad              ├─ Ambientales                ├─ Regulatorios
   ├─ Eficiencia              ├─ Operacionales              ├─ Éticos
   │   ├─ Performance         └─ De desarrollo              └─ Legislativos
   │   └─ Espacio                                               ├─ Contables
   ├─ Confiabilidad                                             └─ Seguridad/
   └─ Seguridad                                                    protección
```

*(Descripción del diagrama: árbol de tres ramas. La rama "de producto" contiene usabilidad, eficiencia —que a su vez se subdivide en performance y espacio—, confiabilidad y seguridad. La rama "organizacionales" contiene ambientales, operacionales y de desarrollo. La rama "externos" contiene regulatorios, éticos y legislativos; de legislativos cuelgan contables y de seguridad/protección.)*

1. **De producto:** especifican o restringen el **comportamiento del software**. Ejemplos: performance (qué tan rápido ejecuta, cuánta memoria requiere), confiabilidad (tasa de fallas aceptable), seguridad, usabilidad.
2. **Organizacionales:** requerimientos amplios derivados de **políticas y procedimientos** de la organización cliente y de la desarrolladora. Ejemplos: operacionales (cómo se va a usar el sistema), de proceso de desarrollo (lenguaje de programación, entorno o estándares de proceso a usar), ambientales (entorno operativo del sistema).
3. **Externos:** todo lo derivado de **factores externos** al sistema y a su proceso de desarrollo. Ejemplos: regulatorios (qué debe cumplirse para que un regulador — p. ej. un banco central — apruebe el uso), legislativos (operar dentro de la ley), éticos (que el sistema sea aceptable para sus usuarios y el público).

**Los tres, aterrizados en el MHC-PMS:**

| Familia | Requerimiento del MHC-PMS (adaptado) |
|---|---|
| **Producto** (disponibilidad) | El sistema debe estar disponible en todas las clínicas en horario laboral normal (lun–vie, 08:30–17:30). El tiempo caído dentro de ese horario no debe superar los cinco segundos por día. |
| **Organizacional** (autenticación) | Los usuarios se autentican con su tarjeta de identidad de la autoridad de salud. *(La organización migró a autenticación estándar por tarjeta para TODO su software — política organizacional pura.)* |
| **Externo** (legislativo) | El sistema debe implementar las disposiciones de privacidad de pacientes establecidas en la norma nacional correspondiente. *(Privacidad en salud mental: obligación legal, origen 100 % externo.)* |

Fijate que el de disponibilidad **no dice nada de la funcionalidad** — es una restricción que los diseñadores deben considerar. Esa es la marca de fábrica de un no funcional.

#### De metas a requerimientos verificables 🔴

Problema común: usuarios y clientes proponen los no funcionales como **metas** (*goals*) generales — "fácil de usar", "que se recupere de fallas", "respuesta rápida". Las metas expresan buenas intenciones, pero dejan **margen de interpretación y de disputa posterior** a la entrega. Compará:

> ❌ **Meta (no verificable):** "El sistema debe ser fácil de usar por el personal médico y estar organizado de forma que los errores de usuario se minimicen."

Imposible de verificar objetivamente. ¿Quién decide qué es "fácil"? Ahora la versión **testeable**:

> ✅ **Requerimiento verificable:** "El personal médico debe poder usar todas las funciones del sistema tras cuatro horas de capacitación. Después de esa capacitación, el promedio de errores cometidos por usuarios experimentados no debe superar dos por hora de uso."

Con esto podés instrumentar el software para **contar errores** durante las pruebas y verificar objetivamente. La regla práctica: **siempre que sea posible, escribí los no funcionales cuantitativamente**. Métricas típicas por propiedad:

| Propiedad | Métricas posibles |
|---|---|
| Velocidad | Transacciones procesadas/segundo · tiempo de respuesta a usuario/evento · tiempo de refresco de pantalla |
| Tamaño | Mbytes · cantidad de chips ROM |
| Facilidad de uso | Tiempo de capacitación · cantidad de pantallas de ayuda |
| Confiabilidad | Tiempo medio entre fallas · probabilidad de indisponibilidad · tasa de ocurrencia de fallas · disponibilidad |
| Robustez | Tiempo de rearranque tras falla · porcentaje de eventos que causan falla · probabilidad de corrupción de datos ante falla |
| Portabilidad | Porcentaje de sentencias dependientes del destino · cantidad de sistemas destino |

**Los límites honestos de esta regla** (también evaluables): a los clientes les cuesta traducir metas a números; para algunas metas (mantenibilidad) directamente **no hay métricas** usables; aun cuando el número existe, el cliente puede no entender qué significa "confiabilidad 0,999" en su experiencia cotidiana; y **verificar objetivamente cuesta caro** — el cliente puede considerar que no se justifica.

#### Los no funcionales conflictúan entre sí

Los no funcionales a menudo **entran en conflicto e interactúan** con otros requerimientos (funcionales o no). El caso del MHC-PMS: el requerimiento de autenticación por tarjeta exige un **lector de tarjetas** en cada computadora. Pero otro requerimiento pide **acceso móvil** desde las laptops de médicos y enfermeros — que normalmente no tienen lector. Conclusión: hay que admitir algún método de autenticación alternativo. Dos requerimientos legítimos, tensión real, decisión de compromiso. Esto es el pan de cada día de la RE.

#### ¿Separarlos o no en el documento?

En la práctica es **difícil separar** funcionales y no funcionales en el documento de requerimientos: si los no funcionales van aparte, se pierden de vista las **relaciones** entre ellos y los funcionales que generan. Pero conviene **resaltar explícitamente** los que se relacionan con propiedades emergentes (performance, confiabilidad): en una sección propia o distinguidos de algún modo. Para sistemas críticos, los no funcionales de confiabilidad, seguridad y confidencialidad son especialmente importantes y tienen técnicas de especificación propias.

🕳️ **Madriguera — Dependability y sistemas críticos**
Hay toda un área de la ingeniería de software dedicada a especificar requerimientos de *dependability* (confiabilidad en sentido amplio: disponibilidad + confiabilidad + seguridad + protección) para sistemas donde una falla cuesta vidas o fortunas.
*Volvé al camino — excede esta materia; acá alcanza con saber que los NF críticos tienen tratamiento especial.*

### 📝 Para el parcial, si te preguntan

**"Defina y diferencie requerimientos funcionales y no funcionales. Dé un ejemplo de cada uno."**
Los requerimientos funcionales declaran los servicios que el sistema debe proveer, cómo reacciona a entradas particulares y cómo se comporta en situaciones particulares (ej.: "el sistema genera cada día, por clínica, la lista de pacientes con turno"). Los no funcionales son restricciones sobre esos servicios o funciones — de tiempo, del proceso de desarrollo o impuestas por estándares — y suelen aplicar al sistema como un todo (ej.: "el tiempo caído en horario laboral no debe superar cinco segundos por día").

**"Clasifique los requerimientos no funcionales según su origen."**
De producto (especifican o restringen el comportamiento del software: performance, confiabilidad, seguridad, usabilidad), organizacionales (derivan de políticas y procedimientos de las organizaciones cliente y desarrolladora: operacionales, de desarrollo, ambientales) y externos (derivan de factores externos al sistema y su desarrollo: regulatorios, legislativos, éticos).

**"¿Por qué un requerimiento no funcional puede ser más crítico que uno funcional?"**
Porque los usuarios suelen poder rodear una función deficiente con soluciones alternativas, pero el incumplimiento de un no funcional puede volver inusable el sistema completo — por ejemplo, un sistema de aeronave que no cumple la confiabilidad requerida no se certifica para operar.

**"¿Por qué conviene escribir los no funcionales cuantitativamente?"**
Porque expresados como metas generales ("fácil de usar") no pueden verificarse objetivamente y dejan margen de interpretación y disputa tras la entrega; expresados con métricas (tiempo de capacitación, errores por hora, transacciones por segundo) pueden testearse objetivamente contra el sistema.

---

## 5. El documento de requerimientos de software (SRS) 🟡

> **Definición** — El **documento de requerimientos de software** (también llamado **especificación de requerimientos de software** o **SRS**, *Software Requirements Specification*) es la **declaración oficial de lo que los desarrolladores del sistema deben implementar**. Incluye tanto los requerimientos de usuario como una especificación detallada de los requerimientos de sistema.

Variantes de organización: usuario y sistema integrados en una sola descripción; los de usuario como introducción a los de sistema; o, si hay muchísimos requerimientos, el detalle de sistema en documento aparte.

**¿Cuándo es esencial?** Cuando el desarrollo lo hace un **contratista externo**: el documento es la base del acuerdo. La crítica ágil dice: los requerimientos cambian tan rápido que el documento queda viejo apenas se escribe, así que el esfuerzo se desperdicia — mejor recolectarlos incrementalmente como historias de usuario priorizadas. Posición equilibrada para sistemas de negocio con requerimientos inestables: el enfoque incremental es bueno, **pero** conviene igual un documento corto de soporte con los requerimientos de negocio y de *dependability* del sistema — porque al enfocarte en las funciones del próximo release es fácil olvidar los requerimientos que aplican al sistema **como un todo**.

### 5.1 Quiénes usan el documento (y para qué)

El SRS tiene un conjunto de usuarios **diverso**, desde la alta gerencia que paga hasta los ingenieros que desarrollan:

| Usuario | Qué hace con el documento |
|---|---|
| **Clientes del sistema** | Especifican los requerimientos y los releen para verificar que satisfacen sus necesidades; especifican cambios |
| **Gerentes** | Lo usan para planificar una oferta por el sistema y para planificar el proceso de desarrollo |
| **Ingenieros del sistema** | Lo usan para entender qué sistema hay que desarrollar |
| **Ingenieros de prueba** | Lo usan para desarrollar los tests de validación del sistema |
| **Ingenieros de mantenimiento** | Lo usan para entender el sistema y las relaciones entre sus partes |

Consecuencia directa de esa diversidad: el documento es un **compromiso** entre comunicar los requerimientos a los clientes, definirlos con precisión para desarrolladores y testers, e incluir información sobre la **evolución posible** del sistema. La información sobre cambios anticipados ayuda a los diseñadores a evitar decisiones restrictivas y a los mantenedores a adaptar el sistema a requerimientos nuevos.

### 5.2 Cuánto detalle incluir

Depende del **tipo de sistema** y del **proceso de desarrollo**:

- **Sistemas críticos** → requerimientos detallados, porque seguridad y protección se analizan en detalle.
- **Desarrollo por empresa externa** (outsourcing) → especificaciones detalladas y precisas.
- **Desarrollo iterativo interno** → el documento puede ser mucho menos detallado; las ambigüedades se resuelven durante el desarrollo.

### 5.3 La estructura estándar de un SRS 🟡

Existe una estructura de referencia basada en el estándar **IEEE** *(término nuevo: Institute of Electrical and Electronics Engineers, organización que publica estándares muy usados en ingeniería; su estándar de SRS es de los más conocidos)*, genérica y adaptable, extendida acá con información de evolución del sistema:

| Capítulo | Qué contiene |
|---|---|
| **Prefacio** | Público esperado del documento, historial de versiones con racionalidad de cada una |
| **Introducción** | Necesidad del sistema, funciones en breve, cómo se integra con otros sistemas y con los objetivos de negocio |
| **Glosario** | Términos técnicos definidos, sin asumir experiencia del lector |
| **Definición de requerimientos de usuario** | Servicios provistos al usuario + no funcionales, en notación entendible por clientes; estándares de producto y proceso |
| **Arquitectura del sistema** | Panorama de alto nivel de la arquitectura anticipada, distribución de funciones en módulos, componentes reutilizados resaltados |
| **Especificación de requerimientos de sistema** | Funcionales y no funcionales en detalle; interfaces con otros sistemas |
| **Modelos del sistema** | Modelos gráficos de relaciones entre componentes, sistema y entorno (objetos, flujo de datos, datos semánticos) |
| **Evolución del sistema** | Supuestos fundamentales + cambios anticipados por evolución de hardware, necesidades cambiantes, etc. |
| **Apéndices** | Información específica: requerimientos de hardware (configuración mínima y óptima), de base de datos (organización lógica de los datos y relaciones) |
| **Índice** | Alfabético + posibles índices de diagramas, de funciones, etc. |

Dos matices de aplicación: un producto de software con desarrollo evolutivo **omite** muchos capítulos detallados (foco en requerimientos de usuario y no funcionales de alto nivel, los desarrolladores deciden cómo cumplirlos); un sistema grande con hardware y software interactuando necesita el detalle fino, documentos largos, y entonces tabla de contenidos e índice completos se vuelven críticos para navegarlos.

### 📝 Para el parcial, si te preguntan

**"¿Qué es el documento de requerimientos de software y quiénes lo usan?"**
Es la declaración oficial de lo que los desarrolladores deben implementar, e incluye los requerimientos de usuario y la especificación detallada de los de sistema. Lo usan los clientes (especificar y verificar requerimientos), los gerentes (planificar oferta y desarrollo), los ingenieros del sistema (entender qué construir), los de prueba (derivar tests de validación) y los de mantenimiento (entender el sistema y sus relaciones).

---

## 6. Especificación de requerimientos 🔴

> **Definición** — La **especificación de requerimientos** es el proceso de **escribir** los requerimientos de usuario y de sistema en un documento de requerimientos. Idealmente deben ser claros, no ambiguos, fáciles de entender, completos y consistentes — en la práctica es difícil: los stakeholders interpretan distinto y hay conflictos e inconsistencias inherentes.

### 6.1 Cómo se escribe cada nivel

**Requerimientos de usuario:** describen funcionales y no funcionales de forma entendible **por usuarios sin conocimiento técnico detallado**. Deben especificar solo el **comportamiento externo** del sistema — nada de arquitectura ni diseño. Por lo tanto: **sin jerga de software, sin notaciones estructuradas ni formales**. Lenguaje natural, tablas simples, formularios y diagramas intuitivos.

**Requerimientos de sistema:** versiones **expandidas** de los de usuario, punto de partida del **diseño** del sistema. Agregan detalle y explican **cómo** el sistema debe proveer los requerimientos de usuario. Pueden ser parte del contrato → deben ser especificación completa y detallada del sistema entero.

**El ideal y su excepción inevitable:** los requerimientos de sistema deberían describir solo comportamiento externo y restricciones operacionales, sin meterse en diseño ni implementación. Pero al nivel de detalle necesario para especificar completamente un sistema complejo, es **prácticamente imposible excluir toda la información de diseño**, por tres razones concretas:

1. Puede hacer falta diseñar una **arquitectura inicial** solo para **estructurar la especificación** — los requerimientos de sistema se organizan según los subsistemas que componen el sistema (y esa definición arquitectónica es esencial si querés reutilizar componentes).
2. Casi siempre el sistema debe **interoperar con sistemas existentes**, que restringen el diseño e imponen requerimientos al sistema nuevo.
3. Puede ser necesaria una **arquitectura específica para satisfacer no funcionales** (redundancia para confiabilidad, por ejemplo) — incluso un regulador externo puede exigir que se use un diseño arquitectónico ya certificado.

### 6.2 El menú de notaciones 🟡

Para escribir los requerimientos de sistema hay un espectro de opciones:

| Notación | Descripción | Cuándo conviene |
|---|---|---|
| **Oraciones en lenguaje natural** | Oraciones numeradas; cada una expresa UN requerimiento | Default universal; requerimientos de usuario siempre |
| **Lenguaje natural estructurado** | Lenguaje natural sobre un formulario o plantilla estándar; cada campo informa un aspecto del requerimiento | Cuando hace falta uniformidad sin perder legibilidad |
| **Lenguajes de descripción de diseño** | Lenguaje tipo programación con rasgos más abstractos, define un modelo operacional del sistema | Hoy raro; útil en especificación de interfaces |
| **Notaciones gráficas** | Modelos gráficos + anotaciones de texto para funcionales; casos de uso y diagramas de secuencia UML son lo común | Mostrar cambios de estado o secuencias de acciones |
| **Especificaciones matemáticas** | Basadas en máquinas de estados finitos o conjuntos; sin ambigüedad | Sistemas críticos de seguridad; los clientes no las entienden y resisten aceptarlas como contrato |

*(UML — término nuevo: Unified Modeling Language, lenguaje gráfico estándar de facto para modelar sistemas orientados a objetos; sus diagramas de casos de uso aparecen en la Parte 2.)*

Sobre las gráficas: son más útiles cuando necesitás mostrar **cómo cambia un estado** o **describir una secuencia de acciones**. Sobre las matemáticas: reducen la ambigüedad, pero la mayoría de los clientes **no entiende** una especificación formal, no puede verificar que representa lo que quiere, y es reacia a aceptarla como contrato — por eso quedan casi exclusivamente en sistemas críticos de seguridad o protección.

### 6.3 Especificación en lenguaje natural 🔴

El lenguaje natural se usa para requerimientos desde el inicio de la ingeniería de software: es **expresivo, intuitivo y universal** — y también potencialmente **vago, ambiguo**, y su significado depende del trasfondo de quien lee. Hubo muchas propuestas de alternativas; ninguna se adoptó masivamente. El lenguaje natural **va a seguir siendo** la forma dominante de especificar. Conclusión operativa: no lo reemplazás, lo **disciplinás**. Cinco pautas para minimizar malentendidos:

1. **Inventá un formato estándar** y usalo para TODAS las definiciones. Estandarizar reduce omisiones y facilita el chequeo. Formato recomendado: el requerimiento en **una sola oración** + una **racionalidad** asociada.
2. **Usá el lenguaje consistentemente para separar lo obligatorio de lo deseable:** obligatorio = "**shall**" ("debe"), deseable = "**should**" ("debería").
3. **Resaltá** (negrita, cursiva o color) las partes clave del requerimiento.
4. **No asumas que el lector entiende jerga** de ingeniería de software: "arquitectura", "módulo" se malinterpretan fácil. Evitá jerga, abreviaturas y siglas.
5. **Asociá una racionalidad a cada requerimiento de usuario:** por qué se incluyó, y opcionalmente quién lo propuso (la **fuente**, para saber a quién consultar ante un cambio). La racionalidad es oro cuando hay que decidir si un cambio propuesto es una mala idea.

#### El segundo caso: la bomba de insulina

Para ver estas pautas y las técnicas que siguen, entra el segundo caso de la unidad. Es un **sistema embebido** *(término nuevo: software que corre dentro de un dispositivo dedicado, no en una computadora de propósito general)* para una **bomba de insulina automatizada**: un aparato que porta una persona con diabetes, que **mide el nivel de azúcar en sangre** con un sensor y **administra insulina** automáticamente cuando hace falta, sin intervención del usuario. Acá una falla no es una pantalla fea: es una dosis incorrecta en un cuerpo humano. Por eso este caso es el vehículo perfecto para técnicas de especificación precisas.

Dos requerimientos del sistema de la bomba, escritos con el formato de las pautas (una oración + racionalidad entre paréntesis):

> **3.2.** El sistema debe medir el azúcar en sangre y administrar insulina, si se requiere, cada 10 minutos. *(Racionalidad: los cambios de azúcar en sangre son relativamente lentos, medir más seguido es innecesario; medir menos seguido podría llevar a niveles de azúcar innecesariamente altos.)*
> **3.6.** El sistema debe ejecutar una rutina de autodiagnóstico cada minuto, con las condiciones a testear y las acciones asociadas definidas en una tabla. *(Racionalidad: la rutina de autodiagnóstico puede descubrir problemas de hardware o software y alertar al usuario de que la operación normal puede ser imposible.)*

Mirá cómo cada racionalidad te deja **evaluar cambios futuros**: si alguien propone medir cada 30 minutos, la racionalidad de 3.2 ya te dice qué riesgo estás tocando.

### 6.4 Especificación estructurada 🔴

> **Definición** — El **lenguaje natural estructurado** es una forma de escribir requerimientos donde la libertad del redactor se **limita** y todos los requerimientos se escriben de un **modo estándar** (plantillas/formularios). Mantiene casi toda la expresividad y comprensibilidad del lenguaje natural, imponiendo uniformidad.

Las plantillas pueden estructurarse alrededor de los **objetos** que el sistema manipula, las **funciones** que realiza o los **eventos** que procesa. Puede usarse construcción tipo lenguaje de programación para alternativas e iteración, y resaltado para elementos clave.

🕳️ **Madriguera — Método VOLERE**
Un método conocido de RE propone escribir cada requerimiento de usuario en una **tarjeta** con campos: racionalidad, dependencias con otros requerimientos, fuente, material de soporte, etc. Es el mismo espíritu del formulario estructurado.
*Volvé al camino — si un día trabajás con tarjetas de requerimientos, ya sabés de dónde viene la idea.*

**El caso concreto: computar la dosis de insulina.** Especifiquemos con formulario la función que calcula cuánta insulina administrar cuando la medición está en la **zona segura** (entre 3 y 7 unidades). La entrada clave: la lectura actual y las **dos anteriores**, porque la decisión depende de la **tendencia** del azúcar, no del valor puntual.

| Campo | Contenido |
|---|---|
| **Función** | Computar dosis de insulina: nivel de azúcar en zona segura |
| **Descripción** | Computa la dosis a administrar cuando el nivel medido actual está en la zona segura, entre 3 y 7 unidades |
| **Entradas** | Lectura actual de azúcar (r2), las dos lecturas previas (r0 y r1) |
| **Fuente** | Lectura actual: del sensor. Las otras: de memoria |
| **Salidas** | CompDose — la dosis de insulina a administrar |
| **Destino** | Lazo principal de control |
| **Acción** | CompDose es 0 si el azúcar está estable o cayendo, o si crece pero a ritmo decreciente. Si crece a ritmo estable o creciente, CompDose = diferencia entre nivel actual y previo, dividida 4 y redondeada. Si el redondeo da 0, CompDose = dosis mínima administrable |
| **Requiere** | Las dos lecturas previas (para computar el ritmo de cambio) |
| **Precondición** | El reservorio contiene al menos la dosis única máxima permitida de insulina |
| **Poscondición** | r0 se reemplaza por r1, y r1 por r2 (las lecturas "corren" una posición) |
| **Efectos colaterales** | Ninguno |

Y la lista general de qué debe incluir un formulario estándar de requerimiento funcional (esto ES la plantilla, memorizable):

1. Descripción de la **función o entidad** especificada.
2. Descripción de sus **entradas** y de dónde vienen.
3. Descripción de sus **salidas** y adónde van.
4. Información sobre lo que se **necesita** para el cómputo u otras entidades usadas (la parte "requiere").
5. Descripción de la **acción** a tomar.
6. Con enfoque funcional: **precondición** (qué debe ser verdad antes de llamar la función) y **poscondición** (qué es verdad después).
7. Descripción de los **efectos colaterales**, si los hay.

**Balance:** la especificación estructurada reduce la variabilidad y organiza mejor — pero sigue siendo difícil escribir sin ambigüedad los **cómputos complejos** (como el cálculo de la dosis: leíste el campo "Acción" y probablemente lo tuviste que releer). Para eso, el siguiente refuerzo.

### 6.5 Especificación tabular 🔴

Cuando hay **varias situaciones alternativas** y hay que describir la acción para cada una, las **tablas** son el complemento ideal del lenguaje natural. El cálculo de la dosis, tabulado — la bomba decide según el **ritmo de cambio** del azúcar, computado con las lecturas actual y previas:

| Condición | Acción |
|---|---|
| Azúcar cayendo (r2 < r1) | CompDose = 0 |
| Azúcar estable (r2 = r1) | CompDose = 0 |
| Azúcar creciendo y ritmo de crecimiento decreciente ((r2 − r1) < (r1 − r0)) | CompDose = 0 |
| Azúcar creciendo y ritmo de crecimiento estable o creciente ((r2 − r1) ≥ (r1 − r0)) | CompDose = round((r2 − r1)/4). Si el resultado redondeado = 0, entonces CompDose = DosisMínima |

Comparala con el campo "Acción" del formulario: **misma lógica, cero ambigüedad**. Cada fila es un caso exhaustivo y verificable. Para que la termines de internalizar, la misma tabla como pseudocódigo comentado:

```
// Cálculo de dosis de insulina en zona segura (3 a 7 unidades)
// r0 = lectura anteanterior · r1 = lectura anterior · r2 = lectura actual

delta_actual = r2 - r1      // cuánto cambió el azúcar en el último intervalo
delta_previo = r1 - r0      // cuánto había cambiado en el intervalo anterior

SI r2 < r1:                          // el azúcar está CAYENDO
    CompDose = 0                     //   → no dar insulina (la insulina BAJA el azúcar;
                                     //     si ya baja sola, dosificar sería peligroso)
SINO SI r2 = r1:                     // el azúcar está ESTABLE
    CompDose = 0                     //   → no hace falta intervenir

SINO SI delta_actual < delta_previo: // sube, pero cada vez MÁS DESPACIO
    CompDose = 0                     //   → la tendencia ya se está frenando sola

SINO:                                // sube a ritmo estable o CRECIENTE (delta_actual ≥ delta_previo)
    CompDose = round(delta_actual/4) //   → dosis proporcional a la velocidad de suba
    SI CompDose = 0:                 //   → si el redondeo la anuló…
        CompDose = DosisMinima       //     …igual se administra la dosis mínima

// ¿CÓMO FUNCIONA? Ejemplo con lecturas r0=4.0, r1=4.5, r2=5.2:
//   delta_previo = 0.5, delta_actual = 0.7 → 0.7 ≥ 0.5 → rama final
//   CompDose = round(0.7/4) = round(0.175) = 0 → se anuló → CompDose = DosisMinima
// Resultado esperado: el sistema administra la dosis mínima, porque el azúcar
// sube y acelera, aunque el cálculo proporcional haya redondeado a cero.
```

*(El pseudocódigo es una re-expresión pedagógica de la tabla — la especificación oficial es la tabla; en un parcial reproducí la tabla.)*

### 📝 Para el parcial, si te preguntan

**"¿Qué pautas conviene seguir al especificar requerimientos en lenguaje natural?"**
Definir un formato estándar y aplicarlo a todos los requerimientos; usar el lenguaje consistentemente para distinguir obligatorio ("shall"/debe) de deseable ("should"/debería); resaltar las partes clave del texto; evitar jerga, abreviaturas y siglas; y asociar a cada requerimiento de usuario una racionalidad que explique por qué se incluyó.

**"¿Qué ventajas y límites tiene la especificación estructurada frente al lenguaje natural libre?"**
Reduce la variabilidad de la especificación y organiza mejor los requerimientos manteniendo la expresividad del lenguaje natural, porque impone plantillas con campos estándar (función, entradas, salidas, acción, pre/poscondiciones, efectos colaterales). Su límite: los cómputos complejos siguen siendo difíciles de expresar sin ambigüedad, por lo que se complementa con tablas o modelos gráficos.

**"¿Cuándo conviene una especificación tabular?"**
Cuando existen varias situaciones alternativas y hay que describir la acción a tomar en cada una: cada fila condición→acción elimina la ambigüedad que el texto corrido introduce en cómputos con casos múltiples.

---

## 7. Cierre de la Parte 1 — y qué viene

Lo que ya tenés instalado: qué es un requerimiento y la RE (§2), los dos niveles usuario/sistema y sus públicos (§3), la gran clasificación funcional/no funcional con las tres familias de NF y la regla de cuantificar (§4), el documento SRS con sus usuarios y estructura (§5), y el arsenal de especificación — lenguaje natural disciplinado, formularios, tablas (§6).

**En la Parte 2** pasamos del producto al **proceso**: cómo se descubren los requerimientos en el mundo real (elicitación: entrevistas, escenarios, casos de uso, etnografía — con el MHC-PMS como caso), cómo se chequea que definen el sistema que el cliente realmente quiere (validación), y cómo se controla el hecho inevitable de que **van a cambiar** (gestión de requerimientos). El checkpoint de la unidad va al cierre de esa parte.

*(No hubo información operativa de cursada en el material de esta unidad — fechas, TPs o reglas de cátedra se incorporan cuando las traigas.)*

---

**FIN — Apunte Maestro U1 · Parte 1 de 2**
