# Lectura en español — Cap. 7 · Parte 2: Las dimensiones de la negociación

> **Origen.** Capítulo 7, secciones 7.3 a 7.5, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Paul Grünbacher y Norbert Seyff**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1.** Se asume conocido el proceso de tres etapas: pre-negociación, negociación y post-negociación.

---

## El marco de tres dimensiones

El proceso de la Parte 1 define **el alcance y el propósito** de las actividades, pero no aborda aspectos más específicos. Los autores presentan entonces un marco de tres dimensiones:

```
   1. ESTRATEGIA DE RESOLUCIÓN DE CONFLICTOS
      ¿cómo se resuelven los conflictos?

   2. SITUACIÓN DE COLABORACIÓN
      ¿cómo colaboran los interesados?

   3. SOPORTE DE HERRAMIENTAS
      ¿qué herramientas se usan?
```

**Su doble propósito:** clasificar y entender los enfoques y herramientas existentes, y **abordar cuestiones importantes para las organizaciones que quieren diseñar e implementar procesos de negociación efectivos**.

Los autores aclaran honestamente que **no pretenden que el marco sea completo**, y que **las dependencias entre las dimensiones no se abordan explícitamente** — aunque existen: una situación de colaboración dada puede implicar ciertas estrategias de resolución y cierto tipo de soporte.

---

## 1. Dimensión 1 — Estrategia de resolución de conflictos 🔴

### De dónde vienen los conflictos 🔴

Los proyectos enfrentan conflictos de intereses y necesidades en decisiones importantes. Teóricamente, esas situaciones se enmarcan como **de motivo mixto**:

> **Las partes experimentan en parte un terreno común** —las metas y objetivos conjuntos del proyecto— **pero también enfrentan diferencias considerables en sus preferencias sobre temas específicos.**

Y una constatación: **se demostró que el conflicto no es la excepción sino algo muy común en las interacciones grupales.**

**Las tres fuentes mayores de conflicto** en ingeniería de software, según el estudio de Curtis y otros:

```
   1. LA DISTRIBUCIÓN DELGADA del conocimiento del
      dominio de aplicación
      (poca gente sabe realmente cómo funciona el negocio)

   2. REQUISITOS FLUCTUANTES Y EN CONFLICTO

   3. RUPTURAS en la comunicación y la coordinación
```

Los requisitos en conflicto tienen muchas causas, incluyendo **cambios en el entorno organizacional y de negocio**. Y una razón de fondo: **el software va a ser usado por personas distintas con metas y necesidades distintas.**

**Otras fuentes de conflicto** que lista Easterbrook:

- conflictos entre **componentes de solución** sugeridos;
- conflictos entre **restricciones enunciadas**;
- conflictos entre **necesidades percibidas**;
- conflictos en el **uso de recursos**;
- **discrepancias entre evaluaciones de prioridad**.

> ⚠️ **Cruce con la cátedra.** Esa lista es un checklist útil para preparar una mediación: son **cinco lugares distintos donde buscar el conflicto**. Notá que el primero y el tercero son distintos — dos personas pueden estar de acuerdo en la necesidad y en desacuerdo en la solución, o al revés. Confundirlos es tratar de resolver el conflicto equivocado.

### Los cinco modos de manejo del conflicto 🔴

El modelo más conocido, propuesto por **Thomas** en psicología organizacional. La orientación de un interesado tiene **dos dimensiones**:

```
                        ASERTIVO
                     (satisfacer las
                    preocupaciones
                       PROPIAS)
                           ▲
              COMPETIR     │     COLABORAR
                           │
   NO COOPERATIVO ─── COMPROMETER ─── COOPERATIVO ──►
   (ignorar las              │        (satisfacer las
    preocupaciones           │         preocupaciones
    ajenas)      EVITAR      │    ACOMODAR    AJENAS)
                             │
                             ▼
                       NO ASERTIVO
```

| Modo | En qué consiste |
|---|---|
| **Competir** (forzar) | Énfasis en **ganar las preocupaciones propias a expensas del otro**. Lleva a menudo a situaciones de **ganar-perder** |
| **Acomodar** (suavizar) | Intentar **satisfacer las preocupaciones del otro sin atender las propias**. Puede significar que un interesado **se auto-sacrifica y cede** ante el otro |
| **Colaborar** (resolver el problema) | Foco en **satisfacer las preocupaciones de todas las partes**, buscando alternativas que las satisfagan. El énfasis está en encontrar situaciones de **ganar-ganar** |
| **Evitar** (retirarse) | Puede resultar de **indiferencia, negación o apatía** |
| **Comprometer** (repartir) | Involucra **concesiones para encontrar un punto medio satisfactorio** |

### Cómo se elige el modo 🔴

Y acá está la parte útil: **la mejor estrategia depende de cuatro factores.**

```
   · las APUESTAS del resultado (qué hay en juego)
   · la INTERDEPENDENCIA de intereses
   · el PODER RELATIVO de las partes
   · la CALIDAD DE LA RELACIÓN entre ellas
```

**El ejemplo que dan:** si **las apuestas del resultado son altas** para un interesado —lo cual pasa en muchos proyectos de software— **y la gente quiere mantener una relación de buena calidad**, entonces **se prefiere el modo colaborativo por sobre el acomodativo**.

> ⚠️ **Cruce con la cátedra.** Los cinco modos son vocabulario preciso para nombrar lo que pasa en una reunión, y eso sirve directamente en una minuta de mediación. Anotar *"el equipo acomodó ante la posición del área de finanzas"* dice mucho más que *"se acordó lo que propuso finanzas"* — nombra que hubo un sacrificio unilateral, que es un riesgo a futuro.
>
> Y notá que **comprometer no es lo mismo que colaborar**: comprometer reparte la diferencia (los dos ceden algo); colaborar busca una opción nueva que satisfaga a los dos. La segunda es más difícil y da mejores resultados; la primera es más rápida.

### Blanda, dura y de principios 🔴

Otro modelo, de **Fisher y Ury**, distingue tres estrategias:

| | **Blanda** | **Dura** |
|---|---|---|
| **Supuesto** | Las partes **están dispuestas a colaborar** para buscar acuerdos mutuamente satisfactorios. Cooperan en un proceso de equipo orientado al consenso | Las partes **se ven como competidores** que no necesariamente quieren llegar a un ganar-ganar. Interacción de interesados en competencia, donde el conflicto ocurrirá inevitablemente |

En vez de quedarse en esos dos extremos, Fisher y Ury proponen un enfoque combinado: **la estrategia de principios**. Esta es la tabla comparativa completa:

| **Blanda** | **Dura** | **De principios** |
|---|---|---|
| Los participantes son **amigos** | Los participantes son **adversarios** | Los participantes son **resolvedores de problemas** |
| La meta es **el acuerdo** | La meta es **la victoria** | La meta es **un resultado sabio, alcanzado eficiente y amigablemente** |
| **Hacer concesiones** para cultivar la relación | **Exigir concesiones** como condición de la relación | **Separar a las personas del problema** |
| Ser **blando con las personas y con el problema** | Ser **duro con el problema y con las personas** | **Ser blando con las personas, duro con el problema** |
| **Confiar** en los otros | **Desconfiar** de los otros | **Proceder independientemente de la confianza** |
| **Cambiar de posición fácilmente** | **Atrincherarse** en la posición | **Enfocarse en los intereses, no en las posiciones** |
| Hacer **ofertas** | Hacer **amenazas** | **Explorar los intereses** |
| **Revelar** el límite propio | **Engañar** sobre el límite propio | **Evitar tener un límite** |
| **Aceptar pérdidas unilaterales** para llegar al acuerdo | **Exigir ganancias unilaterales** como precio del acuerdo | **Inventar opciones de ganancia mutua** |
| Buscar **la única respuesta: la que ellos aceptarán** | Buscar **la única respuesta: la que vos aceptarás** | **Desarrollar múltiples opciones para elegir; decidir después** |
| Insistir en **el acuerdo** | Insistir en **tu posición** | **Insistir en usar criterios objetivos** |
| Intentar **evitar** un choque de voluntades | Intentar **ganar** un choque de voluntades | **Buscar un resultado basado en estándares independientes de la voluntad** |
| **Ceder a la presión** | **Aplicar presión** | **Razonar y estar abierto a la razón; ceder ante el principio, no ante la presión** |

### Los cuatro principios 🔴

La estrategia combinada se apoya en **cuatro principios** (los que van en negrita en la columna derecha):

```
   1. SEPARAR a las personas del problema
   2. ENFOCARSE en los intereses, NO en las posiciones
   3. GENERAR una variedad de posibilidades antes de
      decidir qué hacer
   4. INSISTIR en que el resultado se base en algún
      estándar OBJETIVO
```

> ⚠️ **Cruce con la cátedra.** Estos cuatro principios son lo más directamente aplicable de todo el capítulo a la reunión de mediación de la clase 05.
>
> **El principio 2 es el central y el más fácil de errar.** Una *posición* es lo que alguien dice que quiere ("necesito el reporte en PDF"); un *interés* es por qué lo quiere ("necesito poder mandárselo al directorio sin que lo modifiquen"). Las posiciones chocan; **los intereses casi siempre admiten más de una solución.** Es el mismo problema que viste en el capítulo 2 sobre interesados que **proponen soluciones en vez de requisitos** — acá aparece del lado de la negociación.
>
> **Y el principio 4 conecta con los criterios de juicio de la Parte 1:** un estándar objetivo es lo que impide que el acuerdo lo gane el que tiene más poder o más aguante.

---

## 2. Dimensión 2 — La situación de colaboración 🔴

El proceso tiene que considerar **distintas situaciones de colaboración según el tiempo y el lugar** de la interacción. Un equipo puede, por ejemplo, decidir una reunión cara a cara para definir los acuerdos, mientras la elicitación de preferencias se hace de manera dislocada.

> **El tiempo de la negociación y la ubicación de los interesados tienen un impacto fuerte sobre las interacciones reales y plantean desafíos adicionales.**

El esquema viene del campo del **Trabajo Cooperativo Asistido por Computadora (CSCW)**, y da cuatro escenarios:

| | **Co-ubicados** | **Dislocados** |
|---|---|---|
| **Comunicación síncrona** | **Mismo tiempo / mismo lugar** | **Mismo tiempo / distinto lugar** |
| **Comunicación asíncrona** | **Distinto tiempo / mismo lugar** | **Distinto tiempo / distinto lugar** |

### 2.1 Mismo tiempo / mismo lugar 🔴

Las reuniones cara a cara siguen siendo **una manera común de elicitar y negociar requisitos**. En IR, muchos enfoques **funcionan mejor, o incluso necesitan, trabajo de equipo continuo y síncrono**. Los métodos ágiles las promueven fuertemente — el ejemplo popular es **el "cliente en el sitio"** de Programación Extrema.

**Y la razón por la que importa para el conflicto específicamente:**

> **Especialmente al intentar resolver conflictos, la riqueza de las interacciones cara a cara vuelve más fácil construir confianza y buscar soluciones conjuntamente.**

Las guías de facilitación de uno de los enfoques sugieren organizar la actividad de **"negociación de acuerdos" como reunión cara a cara**, para aprovechar **la riqueza de las señales no verbales**, que vuelven más fácil entender a la gente **y por lo tanto reducen el tiempo de negociación**.

### 2.2 Distinto tiempo / mismo lugar 🟡

**Organizar una negociación entera con reuniones cara a cara típicamente no es posible**, incluso si los interesados están en el mismo sitio. Las razones:

- **La duración de las negociaciones suele exceder el tiempo de los talleres típicos.**
- **Las reuniones son generalmente difíciles de coordinar** por restricciones de agenda.
- **La información necesaria para tomar una decisión final a menudo no está disponible durante la reunión.**

Por eso es necesario **llevar a cabo ciertos pasos de manera asíncrona**, apoyados por **espacios de trabajo compartidos** que permitan a todos contribuir a las negociaciones en curso y **seguir el progreso**.

### 2.3 Mismo tiempo / distinto lugar 🟡

Aun si es imposible juntar a los interesados cara a cara, **frecuentemente es posible reunirlos al mismo tiempo, con algunos participando remotamente**.

El uso de **audio y videoconferencia da un ancho de banda de interacción razonable**, y el equipo se beneficia de la interacción en tiempo real. Los sistemas de soporte a decisiones grupales **se usaron con éxito para sesiones síncronas y dislocadas de tormenta de ideas o de votación**.

### 2.4 Distinto tiempo / distinto lugar 🟡

> **La ingeniería de requisitos se realiza cada vez más en escenarios asíncronos y dislocados**, a medida que más proyectos abarcan el mundo entero o afectan a múltiples organizaciones.

En esa situación, **la tecnología avanzada de colaboración es una necesidad**. Pero los autores señalan una brecha:

> **Existe poca investigación que examine el impacto de las interacciones de distinto tiempo / distinto lugar sobre el éxito de la negociación de requisitos.**

### Lo que la matriz no cubre 🟡

Los autores aclaran que las cuatro situaciones **no abordan todas las cuestiones importantes** que impactan las negociaciones:

- **la cantidad de interesados involucrados**;
- **la diferencia entre múltiples sitios individuales y múltiples sitios grupales** — no es lo mismo diez personas en diez lugares que dos grupos de cinco en dos lugares;
- **las diferencias culturales** entre las partes que negocian.

> ⚠️ **Cruce con la cátedra.** Esta dimensión describe literalmente tu cursada: **la modalidad alterna semana a semana entre virtual por Zoom y presencial en Campus**, y trabajás en equipo con carpetas compartidas en Drive. O sea que atravesás **al menos tres de los cuatro cuadrantes**.
>
> El dato aprovechable: el capítulo dice que **para resolver conflictos conviene el cara a cara**, por la riqueza de las señales no verbales, mientras que **la elicitación de preferencias y el trabajo de recopilación** se pueden hacer asincrónicamente. Si tu equipo tiene que resolver un desacuerdo de fondo, **guardalo para la semana presencial**; lo que se puede adelantar por Drive, adelantalo.

---

## 3. Dimensión 3 — El soporte de herramientas 🟡

Las negociaciones se apoyan a menudo en **medios tradicionales**: guías y manuales de facilitación, y herramientas generales de reunión como **pizarras y rotafolios**. Pero la escala y complejidad de los proyectos reales sugieren formas más sofisticadas.

La clasificación que adopta el capítulo tiene **tres niveles**:

| Nivel | Qué hace | Ejemplos |
|---|---|---|
| **Soporte pasivo** | Provee **la infraestructura** para negociar. Permite a las partes **expresar preferencias, comunicar ideas, ofertas y argumentos, y compartir resultados intermedios y finales**. **No apoya la producción de contenido** con pistas ni orientación | Correo electrónico, chat, salas multimedia |
| **Soporte activo facilitativo** | Capaz de **guiar a los interesados hacia un acuerdo**, por ejemplo **identificando situaciones de ganancia mutua**. Ayuda en la formulación, evaluación y solución de problemas difíciles. Apoya la **construcción de concesiones y ofertas** y la **evaluación del proceso**. Típicamente **sigue un proceso de negociación** | Sistemas de soporte a decisiones grupales, especialmente si están integrados con guías de facilitación |
| **Soporte pro-activo intervencionista** | Además **coordina las actividades** de los interesados: **critica sus acciones o sugiere qué acuerdo aceptar**. Para eso accede a bases de conocimiento y emplea **agentes de software inteligentes** que monitorean el proceso y las actividades individuales | Sistemas con agentes que dan advertencias durante la negociación |

```
   PASIVO ──────────► ACTIVO ──────────► PRO-ACTIVO
   te da el canal     te guía hacia      te critica y
                      el acuerdo          te sugiere
```

---

## 4. Cuatro sistemas reales, comparados 🟢

El capítulo usa el proceso y el marco para caracterizar cuatro sistemas de soporte a la negociación.

### 4.1 Aspire

Extensión de un sistema anterior, provee **soporte de nivel pro-activo** mediante un agente de software que **aconseja a los negociadores analizando la negociación en curso, con reglas derivadas de la literatura** — por ejemplo, **advirtiendo al usuario sobre las implicancias de acciones que piensa emprender**.

Es **basado en web**, soporta negociaciones **asíncronas y dislocadas**, y está dirigido a **negociaciones bilaterales** (dos partes).

Implementa el modelo de tres fases:

- **Pre-negociación:** analizar la situación respecto de temas y opciones, identificar interesados clave. Asiste dando **una descripción detallada de la situación inicial**, e invita a expresar preferencias sobre temas y alternativas.
- **Negociación:** los oponentes **intercambian mensajes y ofertas**. Termina cuando se logra un acuerdo o **uno de los oponentes detiene la negociación**. El sistema **registra un historial** del proceso, consultable por ambos.
- **Post-acuerdo:** **basándose en la información de preferencias ingresada al principio**, determina si el acuerdo actual satisface a las contrapartes y **verifica si hay una solución mejor posible para una parte sin pérdida para la otra**.

### 4.2 Negoisst 🟡

Enfocado en **comercio electrónico entre empresas**. Combina **comunicación y gestión documental**: los equipos pueden usar **lenguaje natural para intercambiar mensajes semi-estructurados** y **componer conjuntamente los términos de un contrato complejo**.

Su objetivo declarado: dar soporte **intuitivo, no ambiguo, eficiente y orientado al proceso** entre negociadores humanos.

**Cómo logra la no ambigüedad:** mediante **intercambio de mensajes semi-estructurados**, donde los negociadores **eligen entre varios tipos de mensaje para volver explícitas sus intenciones**. Los tipos disponibles —que además delinean el proceso— son:

```
   solicitud · oferta · contraoferta · aceptación
   · rechazo · pregunta · aclaración
```

> ⚠️ **Cruce con la cátedra.** Ese mecanismo es elegante y transferible a una minuta: **etiquetar cada intervención por su tipo** vuelve explícito qué se estaba haciendo. No es lo mismo registrar "se habló del plazo" que registrar "oferta: 30 días · contraoferta: 45 días · aclaración: el plazo incluye pruebas · aceptación". La segunda versión se puede auditar; la primera no.

### 4.3 EasyWinWin 🔴

Es **el único de los cuatro específicamente dirigido a negociación de requisitos de software**. Combina el modelo espiral de ganar-ganar con técnicas colaborativas de conocimiento y la automatización de un sistema de soporte grupal.

**Su vocabulario de trabajo** —vale la pena, porque es simple y ordenado:

| Concepto | Qué es |
|---|---|
| **Condiciones de victoria** (*win conditions*) | Los **objetivos individuales** de cada interesado |
| **Temas** (*issues*) | Los **conflictos entre condiciones de victoria**, más los riesgos e incertidumbres |
| **Opciones** | Lo que **se propone para reconciliar los temas** |
| **Acuerdos** | Se desarrollan **a partir de las condiciones de victoria y de las opciones**, teniendo en cuenta **el proceso de decisión previo y su justificación** |

```
   condiciones de victoria ─┐
                            ├─► TEMAS ─► OPCIONES ─► ACUERDOS
   riesgos e incertidumbres ┘
```

**Qué logra:** ayuda al equipo a **ganar un entendimiento mejor y más completo del problema** y **apoya el aprendizaje cooperativo sobre los puntos de vista ajenos**.

**Incluye pasos de elicitación y análisis.** En un paso de tormenta de ideas, todos los interesados son invitados a publicar sus ideas; **un facilitador analiza las ideas y forma las condiciones de victoria junto con el equipo**.

#### El mecanismo de las páginas que rotan 🟡

Este detalle es ingenioso y vale la pena:

> Hay **una página electrónica para cada interesado**. **Cada vez que alguien aporta un comentario a una página, el sistema se la quita y la reemplaza al azar por otra página con comentarios de otros interesados.** A medida que la actividad avanza, **las páginas van rotando entre los participantes, recogiendo un comentario nuevo en cada parada.**
>
> **Este proceso tiende a ampliar el alcance de la discusión, produciendo amplitud en vez de profundidad. Es una manera útil de identificar muchos conceptos en poco tiempo.**

> ⚠️ **Cruce con la cátedra.** Es una técnica concreta y robable para trabajo grupal. Resuelve dos problemas de una vez: **evita que las personalidades dominantes monopolicen** —el problema que el capítulo 2 señalaba en el trabajo grupal— y **fuerza a que cada uno lea lo que escribieron los otros**, que es lo que nadie hace cuando todos escriben en su propio documento.

**Su caracterización en el marco:**

- **Estrategia de conflicto:** principalmente **colaborativa**.
- **Situación de colaboración:** sin limitaciones formales, aunque **la mayoría de los grupos lo usó en escenarios de mismo tiempo**.
- **Soporte de herramientas:** **activo**.
- **Fortalezas y debilidades:** el aspecto de **elicitación de metas está fuertemente soportado**; el de **generación de soluciones es más débil y depende de la ayuda de un facilitador**.

### 4.4 SmartSettle 🟢

Sistema comercial que usa Internet para permitir la interacción entre interesados con objetivos en conflicto. **Requiere un facilitador** que modele el problema y represente las preferencias de manera utilizable por los algoritmos de optimización adoptados.

Usa **un área de sesión conjunta** para componer un **marco de acuerdo** con mensajes en lenguaje natural, y **grafos de satisfacción** para representar preferencias.

**Lo distintivo:** usa **algoritmos de optimización** para transformar objetivos en conflicto en soluciones justas y eficientes, y para **generar sugerencias antes de que se alcance un acuerdo**. Y después de un acuerdo tentativo, **busca mejorar la situación distribuyendo las ganancias equitativamente entre ambas partes**.

**Sus etapas:** preparar la negociación · calificar intereses · calificar satisfacción · establecer equidad · maximizar beneficios · asegurar el compromiso.

### La comparación 🟡

| | **Aspire** | **Negoisst** | **EasyWinWin** | **SmartSettle** |
|---|---|---|---|---|
| **Estrategia de conflicto** | Competir | Competir | **Colaborar / comprometer** | Competir / comprometer |
| **Situación de colaboración** | Distinto tiempo / distinto lugar | Distinto tiempo / distinto lugar | **Mismo tiempo** (mismo o distinto lugar) | Distinto tiempo / distinto lugar |
| **Soporte** | **Pro-activo intervencionista** | Activo facilitativo | Activo facilitativo | Activo facilitativo |

**Lo que muestra la comparación:**

- **Las implementaciones concretas enfatizan etapas distintas.** Negoisst tiene un modelo de mensajes fuerte para la negociación propiamente dicha; **EasyWinWin soporta tanto la pre-negociación como la negociación, pero su modelo se impone con menos rigor.**
- **En el manejo del conflicto:** Aspire soporta un enfoque orientado al conflicto donde **dos interesados intercambian ofertas y contraofertas**, mientras **EasyWinWin enfatiza la resolución colaborativa basada en la resolución de problemas por un equipo**.
- **Aspire es el único clasificable como pro-activo intervencionista**, porque su agente monitorea continuamente y da orientación.

---

## 5. Conclusiones del capítulo 🟡

Los autores recapitulan lo que hicieron: explicar los pasos importantes de la negociación, presentar un marco tridimensional, y discutir los enfoques existentes en el contexto de ese marco.

**Lo que queda abierto:** aunque se hizo algún progreso, **quedan muchas cuestiones sin resolver**. En particular, **investigar las interdependencias complejas entre las tres dimensiones** lleva a preguntas interesantes — por ejemplo, **encontrar el proceso de negociación más efectivo para un problema, un comportamiento de conflicto esperado, una situación de colaboración y un conjunto de herramientas dados**.

Y cuatro desarrollos esperados:

**1. Escalabilidad.** Se desarrollaron numerosos métodos y herramientas, pero **a menudo son aplicables solo a problemas chicos y no escalan a situaciones del mundo real**, caracterizadas por **muchos interesados y muchos temas** — que es el caso de la mayoría de los proyectos reales.

**2. Integración de campos.** Los investigadores de ingeniería de software **desarrollaron enfoques sin estar al tanto de la investigación en la comunidad de sistemas de soporte a la negociación**. Los enfoques pragmáticos funcionan bien en escenarios reales, pero **complementarlos con técnicas de esa otra comunidad sería beneficioso**.

**3. Herramientas nuevas.** Los desarrollos tecnológicos van a dar soporte más sofisticado. **La computación móvil permite a los interesados participar en negociaciones en situaciones de colaboración nuevas** más fácilmente.

**4. Sistemas distribuidos multi-interesado.** Un desafío que viene del hecho de que cada vez más aplicaciones —especialmente las desplegadas sobre la web— son sistemas **"en los que subconjuntos de los nodos son diseñados, poseídos u operados por interesados distintos"**. Esos nodos **se diseñan u operan a menudo ignorándose mutuamente, o con metas distintas y posiblemente en conflicto.** Los enfoques de negociación **van a volverse aún más importantes** en ese contexto.

---

## Mapa de la Parte 2

```
   DIMENSIÓN 1 — ESTRATEGIA DE CONFLICTO

   3 fuentes mayores: conocimiento del dominio mal
   distribuido · requisitos fluctuantes · rupturas
   de comunicación

   LOS 5 MODOS (Thomas)
   competir · acomodar · colaborar · evitar · comprometer
   se elige según: apuestas · interdependencia ·
   poder relativo · calidad de la relación

   BLANDA / DURA / DE PRINCIPIOS (Fisher y Ury)
   los 4 principios:
     1. separar las PERSONAS del PROBLEMA
     2. intereses, NO posiciones
     3. generar variedad ANTES de decidir
     4. insistir en criterios OBJETIVOS

   ─────────────────────────────────────────────

   DIMENSIÓN 2 — SITUACIÓN DE COLABORACIÓN

                  MISMO LUGAR    DISTINTO LUGAR
   SÍNCRONO       cara a cara    audio/video
                  ← mejor para
                    RESOLVER
                    CONFLICTOS
   ASÍNCRONO      espacios       colaboración
                  compartidos    global (poco
                                 investigado)

   ─────────────────────────────────────────────

   DIMENSIÓN 3 — SOPORTE
   pasivo (canal) → activo (guía) → pro-activo (critica)

   ─────────────────────────────────────────────

   EASYWINWIN — el único de requisitos
   condiciones de victoria → temas → opciones → acuerdos
   + páginas que rotan (amplitud, no profundidad;
     evita que dominen los de siempre)
```

---

## Preguntas para chequear que quedó

1. ¿Qué significa que las situaciones de conflicto sean "de motivo mixto"?
2. Nombrá las tres fuentes mayores de conflicto en ingeniería de software.
3. Nombrá las cinco fuentes adicionales que lista Easterbrook. ¿Por qué "conflicto entre soluciones" y "conflicto entre necesidades" son distintos?
4. Describí las dos dimensiones del modelo de Thomas y ubicá los cinco modos.
5. Diferenciá "comprometer" de "colaborar". ¿Cuál es más difícil y por qué da mejor resultado?
6. ¿De qué cuatro factores depende elegir el modo de manejo del conflicto?
7. En un proyecto con apuestas altas y buena relación entre las partes, ¿qué modo se prefiere y sobre cuál?
8. Compará las estrategias blanda y dura en al menos cuatro filas de la tabla.
9. Nombrá los cuatro principios de la estrategia de principios.
10. Explicá la diferencia entre una posición y un interés, con un ejemplo propio.
11. ¿Por qué "ser blando con las personas y duro con el problema" es distinto de las otras dos estrategias?
12. Describí las cuatro situaciones de colaboración de la matriz CSCW.
13. ¿Por qué el cara a cara conviene especialmente para resolver conflictos?
14. ¿Por qué no se puede hacer toda la negociación cara a cara aunque los interesados estén en el mismo sitio?
15. ¿Qué tres cuestiones importantes NO cubre la matriz CSCW?
16. Diferenciá los tres niveles de soporte de herramientas.
17. En EasyWinWin, ¿qué son las condiciones de victoria, los temas, las opciones y los acuerdos? ¿Cómo se encadenan?
18. Explicá el mecanismo de las páginas que rotan y los dos problemas que resuelve.
19. ¿Cuál es la fortaleza y cuál la debilidad de EasyWinWin?
20. ¿Cómo logra Negoisst que los mensajes no sean ambiguos?
21. ¿Cuál de los cuatro sistemas es el único pro-activo intervencionista y por qué?
22. ¿Cuáles son los cuatro desarrollos esperados que enumeran los autores?

---

**FIN DEL CAPÍTULO 7 — PARTE 2**

**FIN DEL CAPÍTULO 7**

*Sigue el capítulo 8: aseguramiento de calidad en ingeniería de requisitos, en 2 partes.*
