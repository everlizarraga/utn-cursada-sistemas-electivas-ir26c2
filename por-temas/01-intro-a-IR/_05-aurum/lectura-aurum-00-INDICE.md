# 📑 ÍNDICE — Serie de lecturas en español (Aurum & Wohlin, 2005)

**Actualizado:** 17 de agosto de 2026 · **Estado: ✅ COMPLETO — 42 partes, los 20 capítulos**

---

## Qué es esta serie

El contenido completo de ***Engineering and Managing Software Requirements*** (Aurum, A. y Wohlin, C., eds., Springer, 2005) en español. Es el libro que la cátedra subió al aula virtual del proyecto de Ingeniería de Requisitos: 487 páginas, 20 capítulos, cada uno escrito por un equipo distinto de investigadores.

**Aclaración importante sobre qué son estos archivos.** No son traducciones literales. Son **el contenido reescrito en español**, capítulo por capítulo, sección por sección. La distinción es esta:

| | |
|---|---|
| **Cobertura** | **Fiel y completa.** No se saltea ninguna sección, ningún concepto, ningún dato, ninguna tabla. El orden es el del original |
| **Redacción** | **Propia.** Las oraciones largas se parten, las referencias bibliográficas incrustadas salen del medio del texto, la voz pasiva se vuelve activa, y lo que pide desarmarse se desarma |

El objetivo era resolver el problema real: material denso de investigación en inglés académico, que en calco literal seguiría siendo ilegible.

**Lo que agregué y no está en el libro**, siempre marcado como tal:

- **Notas ⚠️** de cruce con la cursada — dónde el contenido toca una clase del cronograma, el léxico de corrección de la cátedra, o un entregable.
- **Madrigueras 🕳️** para términos que el libro usa sin explicar.
- **Diagramas ASCII** y **mapas de cierre** de cada archivo.
- **Preguntas de checkpoint** al final de cada parte, sin respuestas.

**Las marcas 🔴🟡🟢** indican relevancia para *tu* materia, no señales de la cátedra:

- 🔴 se cruza directo con el cronograma o con cómo te corrigen
- 🟡 contexto útil
- 🟢 propio del ámbito de investigación

---

## Cómo se cortan las partes

Regla de balance, para que ningún archivo quede desproporcionado:

| Extensión del capítulo | Partes |
|---|---|
| Hasta 15 páginas | 1 |
| 16 a 30 páginas | 2 |
| Más de 30 páginas | 3 |

Cada archivo cubre entre 10 y 15 páginas de origen. **Total de la serie: 41 partes.**

**Nomenclatura:** `lectura-aurum-capNN-parteM-[tema].md`

*(Nota: los tres archivos del capítulo 2 conservan nombres largos de antes de fijar esta convención. Funcionan igual; el orden lo da el número de parte.)*

---

## ✅ GENERADO — 42 partes · SERIE COMPLETA

### Capítulo 1 — Requirements Engineering: Setting the Context
*Aurum y Wohlin · 15 pp · 1 parte*

| | Archivo | Contenido |
|---|---|---|
| 1/1 | `lectura-aurum-cap01-contexto-de-la-ir` | Qué es un requisito (IEEE 610), las nueve clasificaciones, el proceso y sus modelos, stakeholders, los tres niveles (organizacional/producto/proyecto), las cinco prácticas de gestión, evidencia empírica |

> **Lo más útil:** la escalera de costos de Boehm (US$1 en requisitos → US$200 después de entregado) y el ejemplo de la seguridad que muestra por qué la frontera RF/RNF se vuelve difusa.

### Capítulo 2 — Requirements Elicitation
*Zowghi y Coulin · 28 pp · 3 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/3 | `lectura-aurum-cap02-parte1-elicitacion-proceso-y-roles` | Qué es elicitar (≠ recolectar), la brecha cultural, las cinco actividades del proceso, los cuatro roles del ingeniero de requisitos |
| 2/3 | `lectura-aurum-cap02-parte2-catalogo-de-tecnicas` | Las 20 técnicas en seis familias + las dos tablas de comparación |
| 3/3 | `lectura-aurum-cap02-parte3-metodologias-problemas-y-tendencias` | SAD, UML y casos de uso, ágil, herramientas, las siete categorías de problemas, tendencias y cierre |

> **Lo más útil:** los roles **mediador** y **documentador** (contenido literal de la clase 05), el hallazgo de Hickey y Davis sobre por qué se eligen las técnicas, y la definición de caso de uso como *abstracción de escenarios*.
>
> ⚠️ **Ojo:** los "escenarios" del capítulo 2 **no son** los escenarios de Leite y Doorn que se ven en las clases 10-14.

### Capítulo 3 — Specification of Requirements Models
*Machado, Ramos y Fernandes · 22 pp · 2 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/2 | `lectura-aurum-cap03-parte1-modelado-especificacion-y-metamodelos` | Requisitos de usuario vs. de sistema, modelar ≠ especificar, las cinco categorías de metamodelos, qué metamodelo hay detrás de cada diagrama UML, vistas múltiples |
| 2/2 | `lectura-aurum-cap03-parte2-metodologia-y-transformacion` | Metodología de especificación, control de complejidad, continuidad de modelos, los tres grupos de RNF, la técnica 4SRS |

> **Lo más útil:** los **objetivos de diseño** ("debe ser rápido") que no son requisitos hasta tener métrica, y la tabla de qué diagrama UML soporta cada vista.

### Capítulo 4 — Requirements Prioritization
*Berander y Andrews · 26 pp · 2 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/2 | `lectura-aurum-cap04-parte1-aspectos-y-tecnicas-de-priorizacion` | Los seis aspectos, las cinco técnicas (AHP, 100 dólares, asignación numérica, ordenamiento, top-ten), tabla comparativa, combinaciones |
| 2/2 | `lectura-aurum-cap04-parte2-interesados-uso-y-ejemplo` | Un cliente / varios / mercado masivo, niveles de abstracción, repriorización, **RF vs. RNF en cuatro dimensiones**, ejemplo completo, cierre |

> **Lo más útil:** la tabla RF vs. RNF de la parte 2 (para las clases 06 y 07), y por qué "crítico/estándar/opcional" funciona y "alto/medio/bajo" no.

### Capítulo 5 — Requirements Interdependencies
*Dahlstedt y Persson · 22 pp · 2 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/2 | `lectura-aurum-cap05-parte1-trazabilidad-y-tipos-de-interdependencia` | **Trazabilidad definida y desarmada** (pre/post, horizontal/vertical, meta-modelo), los siete tipos fundamentales de interdependencia |
| 2/2 | `lectura-aurum-cap05-parte2-aplicaciones-y-agenda` | Las siete actividades y qué tipo necesita cada una, agenda de investigación, cierre |

> **Lo más útil:** la sección de trazabilidad de la parte 1. Es el único lugar del libro donde una de las palabras del léxico de corrección de la cátedra queda definida con precisión.


### Capítulo 6 — Impact Analysis
*Jönsson y Lindvall · 26 pp · 2 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/2 | `lectura-aurum-cap06-parte1-conceptos-gestion-del-cambio-y-estrategias` | SLO, los cuatro conjuntos de impacto, cambio primario y secundario, las cinco piezas de la gestión del cambio, estrategias automatizables y manuales |
| 2/2 | `lectura-aurum-cap06-parte2-rnf-metricas-y-herramientas` | Descomponer RNF en funcionales, el factor de impacto, métricas, el estudio de campo en Ericsson, herramientas y futuro |

> **Lo más útil:** el **factor de impacto** (cambiar el vocabulario del dominio o el modelo de casos de uso genera cambios grandes en todo lo demás) y el estudio de Ericsson: profesionales reales subpredijeron el impacto **por un factor de 3**.

### Capítulo 7 — Requirements Negotiation
*Grünbacher y Seyff · 20 pp · 2 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/2 | `lectura-aurum-cap07-parte1-por-que-negociar-y-el-proceso` | Los siete beneficios de negociar, el proceso en tres etapas, interesados críticos para el éxito, los criterios de juicio |
| 2/2 | `lectura-aurum-cap07-parte2-dimensiones-de-la-negociacion` | Los cinco modos de conflicto, estrategias blanda/dura/de principios, la matriz de tiempo y lugar, niveles de soporte, cuatro sistemas comparados |

> **Lo más útil:** es **la teoría detrás de la minuta de mediación de la clase 05**. Los cuatro principios de Fisher y Ury —sobre todo *intereses, no posiciones*— y los criterios de juicio que hay que acordar **antes** de discutir opciones.

### Capítulo 8 — Quality Assurance in RE
*Denger y Olsson · 24 pp · 2 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/2 | `lectura-aurum-cap08-parte1-atributos-de-calidad-y-estrategia` | **Los diez atributos de calidad de los requisitos**, las cinco vistas sobre la calidad, la estrategia de calidad, constructivos vs. analíticos |
| 2/2 | `lectura-aurum-cap08-parte2-enfoques-constructivos-y-analiticos` | Elicitación, especificación y prototipado como calidad · inspecciones, técnicas de lectura, lectura por perspectivas · pruebas tempranas · detección de frases débiles |

> **El capítulo más importante de la serie para tu cursada.** Contiene la tabla con *no ambiguo, verificable, trazable, completo, consistente, comprensible* definidos uno por uno — el léxico exacto con el que te corrigen. Y en la parte 2, el **test operativo de la verificabilidad**: si no podés escribir el caso de prueba, el requisito está mal.


### Capítulo 9 — Modeling Goals and Reasoning with Them
*Rolland y Salinesi · 30 pp · 3 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/3 | `lectura-aurum-cap09-parte1-que-son-las-metas-y-sus-roles` | Los tres mundos, qué es una meta, **meta vs. requisito vs. suposición**, los seis papeles de las metas |
| 2/3 | `lectura-aurum-cap09-parte2-modelar-formular-y-razonar` | Metas duras y blandas, grafos Y/O, **metas vs. escenarios**, formulación por verbo y parámetros, cinco técnicas de razonamiento, las cinco debilidades |
| 3/3 | `lectura-aurum-cap09-parte3-mapas-meta-estrategia` | Variabilidad, el formalismo de los mapas, el ejemplo de SAP, personalización de sistemas multi-propósito |

> **Lo más útil:** la distinción **meta / requisito / suposición** de la parte 1 (¿quién es responsable de que se cumpla?) y la comparación **metas vs. escenarios** de la parte 2 — declarativo/procedural, abstracto/concreto — que se cruza con el "CU vs. Escenario" de la clase 11.

### Capítulo 10 — Managing Large Repositories of NL Requirements
*Natt och Dag y Gervasi · 26 pp · 2 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/2 | `lectura-aurum-cap10-parte1-lenguaje-natural-y-similitud` | **Las cinco razones por las que se escribe en lenguaje natural**, verificación vs. validación, **las abstracciones del dominio como conjuntos de términos**, medidas de similitud |
| 2/2 | `lectura-aurum-cap10-parte2-los-tres-casos-de-estudio` | Telelogic (duplicados), Baan (vincular deseos con requisitos), Sony Ericsson (pedidos redundantes), conclusiones |

> **Lo más útil:** la distinción **verificación** (¿es consistente consigo mismo?) vs. **validación** (¿corresponde con lo que el usuario quiere?), y el fundamento de por qué las abstracciones de un dominio se capturan mediante **conjuntos de términos** — la base conceptual de un léxico del dominio.


### Capítulo 11 — Understanding Ambiguity in RE
*Kamsties · 22 pp · 2 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/2 | `lectura-aurum-cap11-parte1-que-es-la-ambiguedad` | **Ambigüedad lingüística vs. de ingeniería**, polisemias sistemáticas, los cuatro dominios de contexto, las tres fuentes, los cuatro destinos de un defecto |
| 2/2 | `lectura-aurum-cap11-parte2-estudios-y-como-convivir` | Los dos estudios empíricos, la lista de verificación de ambigüedad, la técnica de lectura, **las cuatro estrategias para convivir con la ambigüedad** |

> **El capítulo que más directamente explica el criterio con el que te corrigen.** Tres cosas: el grueso de la ambigüedad **no está en la redacción sino en lo que diste por supuesto del dominio**; las ambigüedades no detectadas **se malinterpretan** (a diferencia de la incompletitud, que solo se reenvía); y con el cliente disponible desde el principio, **los errores de interpretación se reducen a la mitad**.

### Capítulo 12 — Decision Support in RE
*Ngo-The y Ruhe · 20 pp · 2 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/2 | `lectura-aurum-cap12-parte1-problemas-de-decision-en-la-ir` | Qué hace que algo sea una decisión, estructurado / semi / no estructurado, los tres niveles, catálogo de decisiones de IR |
| 2/2 | `lectura-aurum-cap12-parte2-soporte-vs-toma-de-decisiones` | **Las dos escuelas**, juicio humano vs. modelo computacional, análisis de 44 trabajos, agenda |

> **Lo más útil:** *"en la toma de decisiones entendemos la realidad para crear el modelo; en el soporte a la decisión usamos los modelos para entender la realidad"*. Reencuadra para qué modelás — y da un argumento contra esperar a "entender bien el caso" antes de empezar a diagramar.

### Capítulo 13 — Market-Driven RE for Software Products
*Regnell y Brinkkemper · 22 pp · 2 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/2 | `lectura-aurum-cap13-parte1-contexto-desafios-y-calidad` | **Dirigido por el mercado vs. a medida** (tabla completa), los siete desafíos, el modelo alfa/beta, capacidad y filtrado |
| 2/2 | `lectura-aurum-cap13-parte2-gestion-de-datos-y-hoja-de-ruta` | La escalera de salmones, el repositorio y sus atributos por estado, elicitación de mercado, hoja de ruta con ejemplo industrial |

> **Lo más útil si tu sistema asignado es un producto masivo:** ahí **no hay a quién entrevistar**, la validación se demora y la organización asume todos los riesgos. Explica la tensión de practicar entrevistas sobre un caso donde en la realidad no habría entrevistado.


### Capítulo 14 — RE for Agile Methods
*Sillitti y Succi · 18 pp · 2 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/2 | `lectura-aurum-cap14-parte1-que-son-los-metodos-agiles` | La producción esbelta y el desperdicio, los cuatro valores, las cinco prácticas, **los tres límites reconocidos** (tamaño, gente, dominio), los factores de fracaso |
| 2/2 | `lectura-aurum-cap14-parte2-el-enfoque-agil-a-los-requisitos` | El cliente único, el desperdicio en requisitos, la priorización en cuatro pasos, la evolución, **el punto débil: los no funcionales**, roles y herramientas |

> **Lo más útil:** el marco que explica **por qué** lo ágil hace lo que hace — todo se deriva de eliminar el desperdicio. Y una discusión honesta de sus límites: los propios autores admiten que **no escala** y que carece de técnicas para requisitos no funcionales.

### Capítulo 15 — RE for Web-Based Information Systems
*Cybulski y Sarkar · 24 pp · 2 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/2 | `lectura-aurum-cap15-parte1-que-hace-distintos-a-los-sistemas-web` | La paradoja del tiempo, cinco metodologías y su hueco común, **los requisitos "creados desde cero en vez de elicitados"** |
| 2/2 | `lectura-aurum-cap15-parte2-incumbencias-y-evolucion` | **Problema vs. incumbencia**, las incumbencias como antecedentes del conflicto, **el hallazgo: se resisten a las consecuencias, no a los requisitos**, la paradoja final |

> **Lo más útil:** la parte 2. La distinción **problema / incumbencia** (un cambio de palabra que cambia quién puede cerrar la cuestión) y el hallazgo empírico de que **la resistencia apunta al requisito pero su causa está en la consecuencia temida** — que es "intereses, no posiciones" del capítulo 7 con evidencia detrás.


### Capítulo 16 — RE en el Sector Público (caso)
*Martin y Gregor · 20 pp · 2 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/2 | `lectura-aurum-cap16-parte1-el-caso-la-gobernanza-y-el-proceso` | **De dónde nacen realmente los requisitos**, la cadena de trazabilidad vertical, la arquitectura empresarial y sus dos reglas, las cinco fases |
| 2/2 | `lectura-aurum-cap16-parte2-fase-de-requisitos-y-lecciones` | Identificar/registrar/revisar/priorizar, la comparación con teoría y estándares, **tres ejemplos reales de requisitos**, las lecciones |

> **Lo más útil:** el ejemplo del software de entrevista, donde el personal de campo pidió que *"no debe causar preocupación a los entrevistados"* porque las portátiles podían intimidar a la gente. Un requisito que solo sale de quien tocó timbres. Y la lección clave: **una especificación puede no estar nunca completa en todos los aspectos** — razón por la cual importa tanto priorizar bien.

### Capítulo 17 — Requisitos de Buena Calidad en el Proceso Unificado
*Yilmaztürk · 32 pp · 3 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/3 | `lectura-aurum-cap17-parte1-el-contexto-y-el-proceso` | **El proceso de doce pasos**, del taller de casos de uso a los casos de prueba, con quién participa en cada paso |
| 2/3 | `lectura-aurum-cap17-parte2-los-26-atributos-y-sus-relaciones` | Los 26 atributos, los tres problemas al comparar fuentes, **los tres tipos de relación entre atributos** |
| 3/3 | `lectura-aurum-cap17-parte3-atributo-por-atributo-con-metricas` | Atributo por atributo con **métricas concretas**, el ejemplo de reescritura del requisito ambiguo, el diagnóstico sobre UML |

> **Lo más útil:** el ejemplo de la parte 3 — *"el sistema debe tener un tiempo de cómputo rápido"* convertido en *"...no debe ser mayor a 6,0 ms"* con límites de medición y configuración. Y la métrica de no ambigüedad: **contar frases débiles + opciones, valor deseado cero.** Más el diagnóstico sobre UML: solo da actores y casos de uso; **todo lo demás es lenguaje natural.**


### Capítulo 18 — Requirements Experience in Practice: Six Companies
*Gorschek y Svahnberg · 22 pp · 2 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/2 | `lectura-aurum-cap18-parte1-las-seis-empresas-y-los-metodos` | Las seis empresas, evaluación por modelo vs. inductiva, **la categoría "satisfecha-explicada"**, la triangulación de fuentes |
| 2/2 | `lectura-aurum-cap18-parte2-los-hallazgos` | **Las seis carencias** y las tres fortalezas, los hallazgos de la evaluación profunda, la comparación con otros relevamientos |

> **Lo más útil:** cinco de seis empresas competentes **no expresaban los requisitos no funcionales en forma verificable**, y cinco de seis **no revisaban los requisitos** — no por no creer que sirva, sino por falta de infraestructura (gente entrenada, listas de verificación). Y la recomendación más fuerte: si podés revisar una sola cosa, **revisá los requisitos, no el código.**

### Capítulo 19 — An Analysis of Empirical RE Survey
*Paech, Koenig, Borner y Aurum · 26 pp · 2 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/2 | `lectura-aurum-cap19-parte1-que-preguntar-para-entender-la-practica` | Las siete estrategias de investigación, los tres propósitos, **el catálogo de factores de contexto**, cómo medir el éxito |
| 2/2 | `lectura-aurum-cap19-parte2-la-evidencia-acumulada` | **Los tres problemas que no cambian desde 1986**, los factores de éxito, los datos de adopción de cada técnica, el estudio propio |

> **Lo más útil:** los tres problemas identificados en 1986 y confirmados durante veinte años — conocimiento del dominio mal repartido, requisitos fluctuantes, rupturas de comunicación. **Ninguno es técnico.** Y el dato metodológico: **el uso estimado de prácticas varió un 30 % según el rol del entrevistado.**

### Capítulo 20 — RE: Solutions and Trends
*Ebert y Wieringa · 24 pp · 2 partes*

| | Archivo | Contenido |
|---|---|---|
| 1/2 | `lectura-aurum-cap20-parte1-el-marco-y-las-soluciones` | Qué es la IR, la clasificación en dos dimensiones, la incertidumbre, **los seis riesgos característicos**, el diagnóstico sobre transferencia tecnológica |
| 2/2 | `lectura-aurum-cap20-parte2-tendencias-y-cierre` | Las cuatro tendencias, la parálisis por análisis y sus cinco causas, **las habilidades del ingeniero de requisitos**, hacia dónde va la disciplina |

> **Lo más útil:** los **seis riesgos** de la parte 1 como checklist final, y las **habilidades personales** de la parte 2 — comunicación (el 100 % del tiempo), cognitivas (constructor de puentes, y *saber cuándo omitir detalles*) y sociales. Con la advertencia de que **los programas académicos por sí solos no las forman.**

---

## ✅ NADA PENDIENTE

**La serie está completa: los 20 capítulos del libro, en 42 partes.**

<!-- PENDIENTE_VIEJO — 5 partes

| Cap. | Título | Págs. | Partes |
|---|---|---:|---:|
| **16** | Case: Quality Software Systems in the Public Sector | 20 | 2 |
| **17** | Good Quality Requirements in Unified Process | 32 | 3 |
| **18** | Requirements Experience in Practice: Six Companies | 22 | 2 |
| **19** | An Analysis of Empirical RE Survey | 26 | 2 |
| **20** | RE: Solutions and Trends — *soluciones y tendencias* | 24 | 2 |

-->

---

## Mapa rápido: qué capítulo toca qué clase

Para cuando avance la cursada y quieras ir directo a lo que corresponde.

| Clase del cronograma | Tema | Dónde mirar |
|---|---|---|
| **01** (13/08) | RF, RNF, stakeholders, usuarios y clientes | **Cap. 1** |
| **02** (20/08) | Casos de uso: actores y relaciones | **Cap. 2 parte 3** (qué es un CU) · **Cap. 3 parte 2** (CU → objetos) |
| **03** (27/08) | Elicitación: conceptos y técnicas | **Cap. 2 partes 1 y 2** |
| **04** (03/09) | Entrevistas y cuestionarios: pros y contras | **Cap. 2 parte 2** (los tres tipos de entrevista) |
| **05** (10/09) | Elicitación · rol del IR (mediador, documentador) | **Cap. 2 parte 1** (los cuatro roles) |
| **06-07** (17 y 24/09) | RF y RNF en profundidad · repaso | **Cap. 4 parte 2** (RF vs. RNF) · **Cap. 3 parte 2** (los tres grupos de RNF) · **Cap. 1** |
| **10-14** (oct-nov) | LEL y escenarios | ⚠️ **El artefacto no está en el libro** (es tradición de Leite y Doorn). Pero el **fundamento conceptual** sí: **Cap. 10 parte 1** (abstracciones del dominio como conjuntos de términos) y **Cap. 9 parte 2** (metas vs. escenarios) |
| **Transversal** | Léxico de corrección: verificable, trazable, no ambiguo | **Cap. 8 parte 1** (los diez atributos, definidos) · **Cap. 17 partes 2 y 3** (26 atributos, sus relaciones y métricas) · **Cap. 11 completo** (ambigüedad en profundidad) · **Cap. 5 parte 1** (trazabilidad) |
| **Transversal** | Minuta de reunión de mediación (clase 05) | **Cap. 7** completo |
| **Transversal** | Inspecciones y revisión de entregables | **Cap. 8 parte 2** |

---

## Lo que el libro NO cubre

Para que no lo busques:

- **LEL** (Léxico Extendido del Lenguaje) — no aparece en ningún capítulo.
- **Escenarios en la tradición de Leite y Doorn** — el libro usa "escenario" en otro sentido.
- **Tipos de actores y relaciones UML** (inclusión, extensión, generalización) — va del Fowler.
- **Notación UML en detalle** — el libro dice qué diagrama sirve para qué, no cómo se dibuja.

---

**FIN DEL ÍNDICE**
