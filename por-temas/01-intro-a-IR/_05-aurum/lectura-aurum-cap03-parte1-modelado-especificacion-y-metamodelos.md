# Lectura en español — Cap. 3 · Parte 1: Modelado, especificación y metamodelos

> **Origen.** Capítulo 3, secciones 3.1 a 3.3, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Ricardo J. Machado, Isabel Ramos y João M. Fernandes**, de la Universidad do Minho, Portugal.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.

---

## Aviso sobre este capítulo

Es el más técnico de los que llevamos y el que más se aleja de tu cursada. Habla de **metamodelos**: la teoría de qué tipos de modelo existen y qué puede representar cada uno. Buena parte del contenido pertenece al mundo de los sistemas embebidos y el diseño de hardware, no al de los sistemas de información.

Dicho eso, tiene tres cosas que sí te sirven, y las marqué en 🔴:

1. La distinción entre **requisitos de usuario** y **requisitos de sistema**, que es la columna vertebral del capítulo.
2. La diferencia precisa entre **modelar** y **especificar** — dos palabras que se usan como sinónimas y no lo son.
3. **Qué metamodelo hay detrás de cada diagrama de UML**, incluyendo una aclaración que corrige un error muy extendido sobre los DFD.

El resto —máquinas de estado, redes de Petri, PSM, SpecCharts— leelo como cultura general si te interesa. No aparece en ninguna clase de tu cronograma.

---

## 1. Introducción 🟡

### Qué es un sistema basado en computadora

Los sistemas basados en computadora integran, como subsistemas de procesamiento de información, **uno o más sistemas de computación** capaces de capturar, almacenar, procesar, transferir, presentar y gestionar información.

Diseñarlos justifica incorporar varias entidades tecnológicas:

1. **Software, firmware y hardware** (analógico y digital), para procesar y almacenar información.
2. **Servicios de red de comunicación**, para transportar información.
3. **Sensores y actuadores**, para interactuar con el ambiente físico.
4. **Interfaces persona-máquina**, para intercambiar información con operadores humanos.

Y aunque pueden basarse estrictamente en tecnologías de computación, **normalmente incluyen además otras entidades**: operadores humanos, subsistemas organizacionales, documentación y manuales.

De ahí la premisa del capítulo: como estos sistemas son **heterogéneos por naturaleza**, modelar y especificar sus requisitos **demanda un enfoque holístico** — que mire el todo, no las piezas por separado.

### Qué es un requisito, otra vez 🟡

Los autores dan dos definiciones cortas antes de la formal, y el contraste vale:

- Un requisito es **"algo que un cliente necesita"**.
- Desde el punto de vista del diseñador o del ingeniero de requisitos, también es **"algo que debe ser diseñado"**.

Y después reproducen la definición del estándar **IEEE 610**, que ya viste en la Parte 1 de esta serie: condición o capacidad que un usuario necesita; condición o capacidad que el sistema debe cumplir para satisfacer un contrato o estándar; y la representación documentada de cualquiera de las dos.

### La distinción central del capítulo 🔴

Clientes y desarrolladores tienen, naturalmente, **puntos de vista distintos** hacia los requisitos. De ahí que los requisitos se dividan en **dos categorías**:

| | **Requisitos de USUARIO** | **Requisitos de SISTEMA** |
|---|---|---|
| **De dónde salen** | Directamente de la tarea de elicitación, como esfuerzo por entender las necesidades del cliente | Del esfuerzo de los desarrolladores por **organizar** los requisitos de usuario en el dominio de la solución |
| **Cómo se describen** | **Lenguaje natural y diagramas informales** | **Modelos abstractos** del sistema |
| **Nivel de detalle** | Relativamente **bajo** | Relativamente **alto** |
| **En qué dominio viven** | El **dominio del problema** | El **dominio de la solución** |
| **Para qué sirven** | Son el **principal medio de comunicación entre clientes y desarrolladores**, en la fase de análisis | Son la **primera representación del sistema**, al comienzo de la fase de diseño |

```
   NECESIDADES          REQUISITOS            REQUISITOS
   DEL CLIENTE   ────►  DE USUARIO    ────►   DE SISTEMA    ────►  DISEÑO
                        (problema)            (solución)
                        lenguaje natural      modelos abstractos
                        detalle bajo          detalle alto
                              │                     │
                        elicitación          organización por
                                             los desarrolladores
```

**Por qué importa que esa derivación se haga bien.** Los autores dan dos razones:

1. **Asegura que la fase de diseño se base en las necesidades efectivas del cliente.**
2. **Garantiza que los desarrolladores no introduzcan arbitrariamente ningún juicio errado** durante el proceso de especificación de los requisitos de sistema.

> ⚠️ **Cruce con la cátedra.** Esta distinción explica una tensión que vas a vivir en los TP. Cuando la cátedra insiste en que los requisitos se redacten en el vocabulario del negocio y no en términos de implementación, está pidiendo **requisitos de usuario**. Cuando después modelás con casos de uso y UML, estás produciendo el puente hacia los **requisitos de sistema**. Son dos artefactos con dominios distintos, no dos niveles de prolijidad del mismo.
>
> Y el segundo punto —que el desarrollador no meta juicios propios en la traducción— es exactamente el riesgo de la **introspección** que viste en la Parte 3 del capítulo anterior, visto ahora desde la etapa siguiente.

Los autores aclaran que el capítulo **no pretende ser un relevamiento exhaustivo** de los enfoques de modelado existentes. Da guías para que diseñadores e ingenieros de requisitos **seleccionen el enfoque que mejor se ajuste a su problema**.

---

## 2. Modelar no es lo mismo que especificar 🔴

Esta sección es la más valiosa del capítulo, y es corta.

### El punto de partida: la vista

La primera decisión de los desarrolladores, cuando quieren especificar un sistema, es **seleccionar qué parte del sistema van a tener en cuenta**. Esa selección define la **vista del sistema** — la perspectiva que necesita representarse.

Y acá está el detalle importante: **esa vista tiene una existencia meramente conceptual, en la mente humana**, con una representación no estructurada e informal, al menos al nivel consciente de los desarrolladores. Todavía no es nada que se pueda mostrar.

### El primer paso: el modelo

**La formalización de la vista ocurre cuando esta origina un modelo.** El modelo consiste en una representación —todavía conceptual— de la vista del sistema, **según un metamodelo particular**.

> **Metamodelo** = un conjunto de **elementos de composición** (funcionales o estructurales) y de **reglas de composición** que permiten construir un modelo que representa la vista del sistema.

En criollo: el metamodelo es el juego de piezas y las reglas de cómo se pueden encastrar. "Estados y transiciones" es un juego de piezas. "Entidades y relaciones" es otro.

**Para qué sirve el modelo:** para **explicar y compartir** la vista conceptual que hasta ahora vivía solo en una cabeza. Así los desarrolladores ponen su vista **a disposición del juicio de otros** y de una reformulación posterior.

**De qué depende que un modelado sea exacto:** de su capacidad de **seleccionar el metamodelo que soporte semánticamente las características del sistema** a modelar. Porque el metamodelo elegido **define los límites semánticos de la representación**. Lo que el juego de piezas no puede expresar, el modelo no lo va a expresar nunca.

### El segundo paso: la especificación

Aunque el modelo ya es resultado de un esfuerzo de formalización, **su existencia sigue siendo conceptual**. Para volverse tangible debe transformarse en una representación concreta llamada **especificación**: una representación real del modelo **en un lenguaje dado**.

El modelo conceptual adoptado al definir ese lenguaje es el **metamodelo del lenguaje**, y es el que permite describir el modelo mediante una representación gráfica, textual o de otro tipo.

### La definición precisa 🔴

```
   SISTEMA ──► VISTA ──► MODELO ──────────► ESPECIFICACIÓN
               (en la    (conceptual,       (tangible, en
                mente)    según un           un lenguaje)
                          metamodelo)
                              ▲                   ▲
                              │                   │
                        METAMODELO           METAMODELO
                        del sistema          DEL LENGUAJE
                              │                   │
                              └─── deben ser ─────┘
                                  COMPATIBLES
```

| Actividad | Qué es |
|---|---|
| **Modelar** | Seleccionar **un metamodelo** para formalizar, a nivel conceptual, una vista dada del sistema |
| **Especificar** | Adoptar **un lenguaje** para hacer tangible un modelo del sistema |

Obtener una especificación que represente adecuadamente al sistema depende **de las dos cosas a la vez**: de las características del metamodelo elegido para modelar, y del metamodelo del lenguaje de representación elegido.

De ahí la regla que cierra la sección:

> **Para evitar desajustes semánticos, los dos metamodelos adoptados deben ser compatibles.** Siempre que sea posible, el metamodelo del lenguaje debería ser el mismo que el usado en la actividad de modelado.

> Un ejemplo para aterrizarlo. Si modelaste el sistema pensando en estados y transiciones, y después lo especificás con un diagrama de entidad-relación, el lenguaje no tiene piezas para expresar lo que modelaste. La especificación va a quedar muda respecto de lo más importante.

---

## 3. Las cinco categorías de metamodelos 🟡

Para simplificar, se puede asumir que el lenguaje de representación fue seleccionado conscientemente teniendo en cuenta las características de su metamodelo — **lo cual, aclaran los autores, no siempre es cierto**.

Idealmente, los lenguajes de representación deberían permitir especificar las características deseadas del sistema **de manera no ambigua**. Eso es posible si el metamodelo del lenguaje cumple dos condiciones:

1. **Formal** (exacto, riguroso), para evitar ambigüedades en la interpretación de la representación del sistema.
2. **Completo**, para permitir construir una representación que **describa totalmente** la vista del sistema.

Y una aclaración honesta: **no son propiedades absolutas**. Dependen del sistema particular que se quiera especificar.

La clasificación que sigue es la de **Gajski y otros**, que organizan los metamodelos más comunes en cinco grupos.

---

### 3.1 Orientados a estados 🟢

Permiten modelar el sistema como **un conjunto de estados y un conjunto de transiciones**. Las transiciones entre estados evolucionan según algún **estímulo externo**.

**Cuándo son adecuados:** para sistemas en los que **el comportamiento temporal es el aspecto más importante** a capturar.

#### Máquinas de estados finitos (FSM)

También llamadas **autómatas finitos**. Son **el metamodelo más usado en la descripción de sistemas de control**, porque el comportamiento temporal de esos sistemas se representa naturalmente como estados y transiciones.

Hay dos alternativas básicas para construirlas, y **difieren solo en la función de salida**:

| | De qué depende la salida |
|---|---|
| **Máquina de Mealy** | Del **estado y de las entradas** |
| **Máquina de Moore** | **Solo de los estados** |

Los diagramas gráficos que las representan se llaman **diagramas de transición de estados (STD)**.

#### FSM con caminos de datos (FSMD)

Son una evolución de las FSM para resolver, de manera simple, el problema de la **explosión de estados**. Extienden las FSM usando **variables enteras o de punto flotante** para reemplazar miles de estados de la FSM equivalente.

**Qué ganan:** mientras las FSM solo pueden representar sistemas de control, **las FSMD también pueden representar sistemas de computación**.

**Qué les falta:** no capturan comportamientos complejos, porque **carecen de la capacidad de manejar concurrencia y jerarquía**.

#### HCFSM

Otra extensión de las FSM: **soportan la representación de concurrencia** y permiten construir **modelos jerárquicos**. Su límite: son relativamente limitadas para manejar estructuras de datos complejas.

El metamodelo detrás de las HCFSM es el mismo que el del lenguaje gráfico **StateCharts de Harel**. Y de ahí un dato concreto:

> **Los diagramas de estados de UML tienen su origen en los StateCharts de Harel.**

#### Redes de Petri

Otro metamodelo orientado a estados, y el que más elogios recibe en el capítulo.

**Son apropiadas para modelar acciones concurrentes**, porque manejan cuatro cosas a la vez: **paralelismo, sincronización, compartición de recursos y memorización**.

**Su fortaleza distintiva:** encierran una **base matemática sólida**, lo que permite **analizar los modelos formalmente** — demostrar propiedades, no solo dibujarlas.

Además, son uno de los metamodelos que **más extensiones ofrecen**, habilitando una enorme variedad de usos: desde especificación de sistemas y análisis de rendimiento hasta síntesis e implementación. Varias de esas extensiones incluyen mecanismos semánticos potentes, como enfoques jerárquicos y orientación a objetos, que permiten abordar el modelado de sistemas complejos.

---

### 3.2 Orientados a actividades 🟡

Permiten modelar el sistema como **un conjunto de actividades relacionadas por datos o por dependencias de ejecución**.

**Cuándo son adecuados:** para sistemas donde **los datos son afectados por una secuencia de transformaciones a tasa constante**.

#### Diagramas de flujo de datos (DFD)

También llamados **grafos de flujo de datos (DFG)**. Consisten en un conjunto de **actividades o procesos interconectados**, con arcos que representan el **flujo de datos** entre ellos.

**Soportan jerarquía:** cada actividad puede detallarse con otro DFD.

**Su límite:** **no pueden expresar comportamiento temporal ni control de acciones.**

Y ahora la aclaración más útil de toda la sección:

> ⚠️ **UML no tiene ningún tipo de diagrama basado en el metamodelo de los DFD.** Ni los diagramas de casos de uso ni los diagramas de actividad de UML son DFD — aunque, reconocen los autores, **algunos desarrolladores argumentan que hay parecidos gráficos**.

Es un error extendido y vale tenerlo claro: un diagrama de actividad **parece** un DFD porque tiene cajas y flechas, pero las flechas significan otra cosa. En un DFD la flecha es **un dato que viaja**; en un diagrama de actividad es **el control que pasa al paso siguiente**.

#### Diagramas de flujo (flowcharts)

También llamados **grafos de flujo de control (CFG)**. Modelan **el flujo de control entre actividades**.

**La diferencia clave con las FSM:** mientras en las FSM las transiciones se activan por **eventos externos**, en los diagramas de flujo las transiciones se activan **apenas una actividad se completa**. No esperan a nadie de afuera.

**Cuándo son adecuados:** para sistemas con actividades bien definidas **que no dependen de estímulo externo**, permitiendo representar secuencias de actividades relacionadas por flujo de control.

> **Los diagramas de actividad de UML están esencialmente basados en este metamodelo.** Sin embargo, sus primitivas de bifurcación y unión (*fork* y *join*) **están inspiradas en las transiciones de las redes de Petri.**

---

### 3.3 Orientados a estructura 🟡

Permiten describir **los módulos físicos del sistema y sus interconexiones**. Están dedicados a caracterizar la **composición física** del sistema, **en vez de su funcionalidad**.

Los **diagramas de bloques** —también llamados **diagramas de componente-conectividad (CCD)**— son el metamodelo orientado a estructura más frecuentemente usado.

> **Los diagramas de despliegue y de componentes de UML están basados en este metamodelo.**

---

### 3.4 Orientados a datos 🟡

Permiten modelar el sistema como **una colección de datos relacionados por algún tipo de atributo**. Le dan **más importancia a la organización de los datos que a la funcionalidad** del sistema.

Sobre UML, una aclaración con matiz:

> **UML no tiene ningún diagrama exclusivamente basado en estos metamodelos**, porque favorece los sistemas orientados a objetos y no promueve el uso de diagramas dedicados principalmente al modelado de datos. **Sin embargo, es posible argumentar que los diagramas de clases de UML son parcialmente orientados a datos.**

Estos metamodelos se usan típicamente dentro de metodologías basadas en las **técnicas tradicionales de análisis y diseño estructurado**.

#### Diagramas de entidad-relación (DER)

Describen el sistema como una **colección de entidades y las relaciones existentes entre ellas**. Cada entidad corresponde a un **tipo único de dato** con uno o más atributos específicos.

**Cuándo son útiles:** cuando los desarrolladores quieren organizar **relaciones complejas entre distintos tipos de datos**.

**Su límite:** **no pueden modelar características funcionales ni temporales.**

#### Diagramas estructurados de Jackson (JSD)

Modelan **la estructura de cada tipo de dato**, mediante descomposición en subtipos. La descomposición se realiza en una **estructura de árbol** donde:

- las **hojas** corresponden a los tipos de datos básicos,
- los **demás nodos** a los datos compuestos, obtenidos mediante operaciones como **composición (Y)**, **selección (O)** e **iteración (\*)**.

**La diferencia de uso con los DER:**

| DER | JSD |
|---|---|
| Adecuados para modelar **distintas entidades de datos con interrelaciones complejas** | Adecuados para modelar **estructuras de datos complejas** |

Las limitaciones de los JSD son similares a las de los DER.

---

### 3.5 Heterogéneos 🟢

Permiten usar, **en una misma representación del sistema**, varias características de metamodelos distintos — de las cuatro categorías anteriores.

**Cuándo conviene:** son una buena solución cuando hay que modelar **sistemas relativamente complejos**.

#### Grafos de flujo de control/datos (CDFG)

Incorporan **DFD** —para modelar el flujo de datos entre las actividades del sistema— **y diagramas de flujo** —para imponer la secuencia de ejecución de esos DFD.

Logran modelar, **en una sola representación**, las dependencias de datos y la secuencia de control del sistema simultáneamente, aprovechando las ventajas de ambos.

#### Diagramas objeto-proceso (OPD)

Dentro de la **Metodología Objeto-Proceso (OPM)** se recomienda el uso combinado de objetos y procesos.

Un OPD puede incluir **procesos y objetos**, vistos como **entidades complementarias** que juntas describen la estructura y el comportamiento del sistema:

- **Los objetos son entidades persistentes.**
- **Los procesos transforman los objetos**, generándolos, consumiéndolos o afectándolos.

Además, **los estados también se integran** en los OPD, para describir a los objetos.

#### Máquinas de estado de programa (PSM)

Permiten **integrar HCFSM con un lenguaje de programación textual**.

Consisten básicamente en una **jerarquía de estados de programa**, en la que cada estado representa un **modo de computación distinto**. En cualquier instante, **solo un subconjunto de los estados está ejecutando sus computaciones** simultáneamente.

**Por qué son más potentes que las HCFSM:** pueden modelar sistemas que poseen estructuras de datos complejas, porque **incorporan en un modelo único datos, actividades y estados**.

Los autores plantean una relación elegante entre los tres conceptos:

```
   HCFSM ◄───────────── PSM ─────────────► LENGUAJE DE PROGRAMACIÓN

   un PSM en el que                        un PSM con un
   NINGÚN estado tiene                     ÚNICO estado
   descripción en el                       especificado
   lenguaje de programación
```

**SpecCharts** es un lenguaje de representación para el metamodelo PSM.

#### Los lenguajes de programación como metamodelo 🟡

Si los PSM se consideran un metamodelo heterogéneo, **también es aceptable considerar a los lenguajes de programación como metamodelos en sí mismos**.

Hay un número considerable de desarrolladores que **usan lenguajes de programación para especificar sistemas** — usualmente su comportamiento y sus estructuras de datos. Y acá los autores meten una advertencia importante:

> **Este enfoque impone una cantidad considerable de decisiones de diseño e implementación en la fase de análisis**, lo cual puede tener un efecto indeseado sobre las especificaciones.

Los lenguajes de programación permiten modelar estructuras de datos, actividades y control. Al "estilo" de modelado que impone un lenguaje particular se lo llama **paradigma**. Y de ahí sale una distinción fina:

> **El metamodelo detrás de un lenguaje de programación es su paradigma, no el lenguaje mismo.** Los lenguajes de programación deberían considerarse lenguajes de representación **a nivel de implementación**.

Los paradigmas, históricamente:

| Paradigma | Cómo funciona | Ejemplos |
|---|---|---|
| **Imperativo** | Sigue el modelo computacional de **von Neumann**: adopta la **ejecución secuencial** de las primitivas | C, Pascal |
| **Declarativo** | **No define un orden explícito** de ejecución. Se enfoca en definir **el objetivo de la computación**, mediante declaración de funciones y reglas lógicas | Lisp, Prolog |
| **Orientado a objetos** | Más reciente. Basado en el metamodelo heterogéneo orientado a objetos | — |

Sobre el tercero, el capítulo agrega detalle:

- **Los metamodelos orientados a objetos evolucionaron de los orientados a datos.** Se caracterizan por su tendencia a describir el sistema como **una colección de objetos cooperantes**.
- Cada objeto consiste en **una colección de datos y en operaciones para transformar esos datos**.
- Soportan **abstracción de datos** (ocultamiento de información) mediante el **encapsulamiento** de los datos en cada objeto, haciéndolos invisibles a los demás.
- **Representan la concurrencia con facilidad**, porque cada objeto coexiste con los otros y puede potencialmente ejecutar sus tareas en paralelo con las de los demás.

---

## 4. El enfoque de vistas múltiples 🔴

Con la creciente complejidad de los sistemas, usar **distintos metamodelos para representar distintos tipos de características** se está volviendo práctica común.

El sistema se modela mediante **un conjunto de modelos diferentes**, cada uno correspondiente a **una vista distinta**, dedicada a representar un conjunto bien delimitado de características del sistema.

### La distinción que hay que no confundir 🔴

> **El enfoque de vistas múltiples NO es lo mismo que usar un metamodelo heterogéneo.**

| Vistas múltiples | Metamodelo heterogéneo |
|---|---|
| La información de las distintas vistas **puede no estar explícitamente relacionada** mediante estructuras de información comunes | Las distintas vistas **deben** sostener estructuras de información comunes, **dentro de una representación integrada única** |
| Varios modelos separados | Un modelo solo, con piezas de varios tipos |

**La notación UML permite adoptar enfoques de vistas múltiples.**

### Las tres vistas ortogonales 🔴

El modelado por vistas múltiples puede adoptar vistas ortogonales — es decir, que no se solapan:

| Vista | De qué es responsable | Diagrama UML que la soporta |
|---|---|---|
| **De función** | Representar **los procesos** del sistema | Diagramas de **actividad** |
| **De datos** | Definir **la información** del sistema | Diagramas de **clases** |
| **De control** | Caracterizar **el comportamiento dinámico** del sistema | Diagramas de **estados** |

Varios autores definieron enfoques de vistas múltiples distintos, donde **las vistas son vehículos para la separación de incumbencias**.

> ⚠️ **Cruce con la cátedra.** Esta tabla es lo más aprovechable del capítulo para tu materia. Explica **por qué UML tiene tantos diagramas distintos y no uno solo**: cada uno se apoya en un metamodelo diferente y por eso puede expresar cosas que los otros no. Un diagrama de clases no puede expresar comportamiento temporal porque su metamodelo no tiene piezas para eso. No es una limitación del dibujo: es una limitación del juego de piezas.

---

## Mapa de la Parte 1

```
   REQUISITOS DE USUARIO ────► REQUISITOS DE SISTEMA
   (problema, lenguaje         (solución, modelos
    natural, detalle bajo)      abstractos, detalle alto)

   ─────────────────────────────────────────────────────

   VISTA ──► MODELO ──► ESPECIFICACIÓN
             (modelar: elegir metamodelo)
                        (especificar: elegir lenguaje)
             ambos metamodelos deben ser COMPATIBLES

   ─────────────────────────────────────────────────────

   LAS 5 CATEGORÍAS          QUÉ DIAGRAMA UML USA
   ESTADOS ──────────────►   diagramas de estados
     FSM, FSMD, HCFSM,       (vienen de StateCharts)
     redes de Petri
   ACTIVIDADES ──────────►   diagramas de actividad
     DFD (¡UML NO tiene!)    (vienen de flowcharts)
     flowcharts
   ESTRUCTURA ───────────►   despliegue y componentes
     diagramas de bloques
   DATOS ────────────────►   clases (parcialmente)
     DER, JSD
   HETEROGÉNEOS ─────────►   —
     CDFG, OPD, PSM,
     paradigmas de
     programación

   ─────────────────────────────────────────────────────

   VISTAS MÚLTIPLES (UML lo permite)
   función → actividad · datos → clases · control → estados
```

---

## Preguntas para chequear que quedó

1. ¿Cuáles son las cuatro entidades tecnológicas que integra un sistema basado en computadora? ¿Qué otras entidades no tecnológicas suele incluir?
2. Compará requisitos de usuario y de sistema en las cinco dimensiones de la tabla.
3. ¿Cuáles son las dos razones por las que importa que la derivación de requisitos de usuario a requisitos de sistema se haga bien?
4. ¿Qué es una "vista" del sistema y dónde existe antes de formalizarse?
5. Definí "metamodelo" con tus palabras.
6. ¿Cuál es la diferencia exacta entre modelar y especificar?
7. ¿Por qué los dos metamodelos —el del modelado y el del lenguaje— deben ser compatibles? ¿Qué pasa si no lo son?
8. ¿Qué dos propiedades debería tener el metamodelo de un lenguaje para permitir especificaciones no ambiguas?
9. ¿En qué se diferencian una máquina de Mealy y una de Moore?
10. ¿Qué problema resuelven las FSMD y qué siguen sin poder hacer?
11. ¿Cuál es la fortaleza distintiva de las redes de Petri frente a los otros metamodelos orientados a estados?
12. ¿Tiene UML algún diagrama basado en el metamodelo de los DFD? Justificá.
13. ¿En qué se diferencia la activación de una transición en una FSM respecto de un diagrama de flujo?
14. ¿Qué metamodelo hay detrás de los diagramas de actividad de UML? ¿Y de dónde vienen sus primitivas de bifurcación y unión?
15. ¿Por qué UML no tiene diagramas puramente orientados a datos?
16. ¿En qué se diferencia el uso de un DER del uso de un JSD?
17. ¿Cuál es el riesgo de usar un lenguaje de programación como lenguaje de especificación?
18. ¿Por qué el metamodelo de un lenguaje de programación es su paradigma y no el lenguaje?
19. Explicá la diferencia entre el enfoque de vistas múltiples y un metamodelo heterogéneo.
20. ¿Qué diagrama UML soporta cada una de las tres vistas ortogonales?

---

**FIN DEL CAPÍTULO 3 — PARTE 1**

*Sigue en la Parte 2: metodología de especificación (lenguaje, control de complejidad, continuidad de modelos), tratamiento de los requisitos no funcionales, y la técnica 4SRS para transformar casos de uso en objetos.*
