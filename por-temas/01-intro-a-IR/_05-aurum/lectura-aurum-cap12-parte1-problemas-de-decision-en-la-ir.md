# Lectura en español — Cap. 12 · Parte 1: Los problemas de decisión en la IR

> **Origen.** Capítulo 12, secciones 12.1 y 12.2, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **An Ngo-The y Günther Ruhe**, Universidad de Calgary, Canadá.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.

---

## Aviso sobre este capítulo

Es un capítulo de análisis del campo: revisa qué se investigó sobre toma de decisiones en IR y propone una agenda. **No toca ninguna clase de tu cronograma.**

Lo que sí vale, y está marcado en 🔴, es **el vocabulario para clasificar decisiones** —estructuradas contra no estructuradas, y los tres niveles— y, en la Parte 2, **la distinción entre "tomar decisiones" y "dar soporte a la decisión"**, que contiene una de las mejores frases del libro sobre para qué sirven los modelos.

---

## 1. La tesis 🔴

> **La toma de decisiones juega un papel vital en el proceso de generación de valor, siendo una especie de motor impulsor dentro de todo el proceso de desarrollo.**

Y una premisa que el capítulo recoge de una investigación industrial:

> **"La gestión de requisitos no es posible sin gestión de decisiones."**

El capítulo recopila las posiciones que fueron construyendo esta idea:

- **Es importante reconocer los requisitos como DECISIONES DE DISEÑO** para lograr un sistema plenamente integrado.
- Otros desarrollan la idea con la afirmación **"¡Los requisitos SIGNIFICAN decisiones!"**.
- Se señala **la similitud entre las actividades de la toma de decisiones organizacional y las del proceso de IR**.
- Y se describe **la naturaleza fundamental de las actividades de IR como un proceso de toma de decisiones**, observando que **el proceso está lleno de problemas de decisión complejos, desde el nivel de la organización hasta el nivel del proyecto.**

### El argumento central del capítulo 🔴

> **Las decisiones de requisitos son difíciles POR LA INCERTIDUMBRE Y LA INCOMPLETITUD de la información disponible.** Vamos a dar argumentos de que **cualquier noción de optimalidad estricta NO es apropiada en este contexto.**
>
> En cambio, se desarrolla toda la filosofía de **proveer soporte sustancial al que decide**, como enfoque para calificar la toma de decisiones humana real.

Y reconocen el estado del campo con honestidad: **el soporte a la decisión en IR está todavía en su infancia.**

---

## 2. Qué es un problema de decisión 🟡

### El ejemplo de arranque

Después de la fase de elicitación, el jefe de proyecto tiene una lista de unos cien requisitos. **Una estimación gruesa muestra que los recursos disponibles no alcanzan para implementarlos todos.** Tiene que actuar. Las alternativas posibles:

```
   (a) RENEGOCIAR los requisitos
   (b) AUMENTAR los recursos disponibles
   (c) IGNORAR el hecho
   (d) ABANDONAR el proyecto
```

Tiene que **evaluar las consecuencias de cada acción desde perspectivas distintas** y finalmente seleccionar una considerando todas las consecuencias.

### Los dos factores esenciales 🔴

De ese ejemplo salen los dos ingredientes que hacen que algo sea una decisión:

```
   1. UN CONJUNTO DE ALTERNATIVAS
      (si solo una acción es posible, no hay nada
       que decidir)

   2. UN CONJUNTO DE CRITERIOS para evaluar las
      consecuencias de cada acción
      (si no, es una elección al azar, no una decisión)
```

> ⚠️ **Cruce con la cátedra.** Esa segunda condición es la que más se olvida y la más aprovechable: **sin criterios declarados no hay decisión, hay elección arbitraria.** Es la misma idea que viste en el capítulo 7 sobre los **criterios de juicio** que hay que acordar antes de comparar opciones, y en el capítulo 4 sobre por qué "importancia" a secas no sirve como aspecto de priorización.
>
> Y da un test simple para cualquier justificación que escribas en un TP: **si no podés nombrar las alternativas que descartaste y el criterio con el que las descartaste, no tomaste una decisión.**

### Los tres tipos de problema de decisión 🟡

| Tipo | En qué consiste |
|---|---|
| **Selección** | **Seleccionar una alternativa** del conjunto, o un subconjunto de él |
| **Triaje** | **Asignar cada alternativa a una de varias clases** |
| **Ordenamiento** | **Ordenar todas las alternativas** según un orden de preferencia |

*(En el ejemplo del jefe de proyecto, el tipo es selección.)*

**Y dos observaciones importantes:**

- **Durante el proceso de decisión, el conjunto de alternativas puede EVOLUCIONAR.** El jefe podría elegir una acción que no estaba listada inicialmente, como *"renegociar primero, después aumentar recursos, y solo cuando todo falla, considerar entre ignorar o abandonar"*.
- **La descripción de un problema de decisión nunca está completa sin su CONTEXTO**, ya que ese factor afecta fuertemente todas las actividades del proceso.

---

## 3. Estructurado, semi-estructurado, no estructurado 🔴

La clasificación de Simon:

| | Definición |
|---|---|
| **Decisiones estructuradas** | **Repetitivas, con un proceso claramente identificado** para llegar a una buena decisión |
| **Decisiones no estructuradas** | **Novedosas, y el proceso asociado sigue siendo ambiguo** |

**Los dos ejemplos que dan son muy claros:**

```
   ESTRUCTURADA — aprobar o rechazar una solicitud
   de crédito hipotecario
   · el banco recibe millones al año
   · tiene un proceso bien establecido para manejarlas
   · la decisión se basa en información precisa

   NO ESTRUCTURADA — que una empresa decida si continúa
   con su proceso de desarrollo actual o adopta uno nuevo
   · muchas empresas no viven lo suficiente
     como para enfrentar esa decisión
   · pocas la enfrentan más de una vez en su vida
   · y NADIE tiene una idea clara de cómo manejarla
```

**Entre los dos extremos hay muchos grados.** Y de qué depende el grado:

> **En general, ese grado depende esencialmente de NUESTRO CONOCIMIENTO sobre el proceso para manejar el problema.**

### Dónde caen las decisiones de IR 🔴

Y acá está la caracterización que importa:

> **La situación es típica en IR: la mayoría de los problemas de decisión importantes NO SON NOVEDOSOS, pero los procesos asociados son usualmente AMBIGUOS por nuestro entendimiento limitado.**
>
> **Para muchas decisiones pueden identificarse ciertos criterios, pero su evaluación y su agregación no son directas.** Por lo tanto, en general, **los investigadores coinciden en que el proceso de IR es un proceso de toma de decisiones complejo, semi-estructurado o no estructurado.**

> ⚠️ **Cruce con la cátedra.** Esta caracterización explica algo de tu materia: **por qué la cátedra valora el criterio fundamentado por encima de la respuesta canónica.** En un problema estructurado hay una respuesta correcta y se la evalúa contra ella. **En un problema semi-estructurado, los criterios existen pero cómo evaluarlos y combinarlos no está resuelto** — y entonces lo único que se puede evaluar es si el razonamiento se sostiene.
>
> Es la misma conclusión a la que llegaba el capítulo 4 desde la priorización ("el propósito no es dar la respuesta, es sostener la decisión") y el capítulo 7 desde la negociación (generar opciones y elegir con criterios objetivos).

---

## 4. Los tres niveles de decisión 🔴

La clasificación de Anthony — **la misma que ya viste en el capítulo 1**, aplicada ahora a decisiones en vez de a requisitos:

| Nivel | De qué se ocupa | Alcance y horizonte | Ejemplo |
|---|---|---|---|
| **Estratégico** | **Los objetivos y las metas** de una organización o un producto | **Alcance grande** (todas las actividades) y **horizonte de largo plazo** (ciclo de vida del producto, duración del proyecto) | Definir la estrategia de producto de una empresa para los próximos cinco años |
| **Táctico** | **La planificación** —recursos, tiempo, tareas— para lograr las metas decididas en el nivel estratégico. Se toman en el **nivel medio de gestión** | **Alcance menor y horizonte más corto** | Planificación del proyecto: *¿cuánto esfuerzo asignar a cada tarea? ¿cómo programar las tareas?* |
| **Operativo** | Se toman **en el nivel operativo**, por ingenieros de requisitos, desarrolladores o probadores, **mientras realizan tareas específicas** | El más acotado | *¿Cuándo parar de probar? ¿Cómo diseñar los módulos? ¿Qué arquitectura logra mejor la calidad buscada?* |

---

## 5. Dos perspectivas para mirar el problema 🟡

Como un proceso de IR consiste en **artefactos** (los requisitos) y **actividades** (elicitar, analizar), los problemas de decisión también pueden verse desde dos perspectivas:

| | **Centrada en requisitos** | **Centrada en actividades** |
|---|---|---|
| **Quién la toma** | **Un investigador de ingeniería de software mirando el paradigma de la teoría de la decisión** | **Un investigador de teoría de la decisión mirando el paradigma de la ingeniería de software** |
| **Por dónde empieza a identificar decisiones** | **Por los requisitos** | **Por las actividades** del proceso |

La primera **es dominante en la comunidad de ingeniería de software**. Los autores eligen la segunda, creyendo que **arroja luz sobre aspectos distintos** — y aclaran:

> **Las dos perspectivas no están en conflicto sino que son complementarias. Juntas forman un marco comprensivo** para entender los problemas, los contextos y las cuestiones de investigación.

---

## 6. El contexto importa 🟡

Cada perspectiva identifica contextos distintos que afectan cómo se puede dar soporte a la decisión.

**Desde la perspectiva centrada en requisitos**, cinco contextos posibles:

```
   (a) sistemas específicos para un cliente
   (b) sistemas listos para usar (off-the-shelf)
   (c) sistemas embebidos
   (d) sistemas críticos de seguridad
   (e) sistemas centrados en base de datos
```

Y el ejemplo de por qué eso cambia todo:

> **En los sistemas específicos para un cliente, el cliente es una persona real (o un grupo de personas). En cambio, en los sistemas listos para usar, el cliente es apenas una ENTIDAD ABSTRACTA.**
>
> Ese factor afecta fuertemente **cómo podemos dar soporte a ciertos problemas, como la negociación de requisitos.** Mientras una herramienta como EasyWinWin sirve para negociar con el cliente de un sistema específico, **para considerar al cliente de un sistema listo para usar hace falta un enfoque más complicado.**

**Desde la perspectiva centrada en actividades**, cuatro contextos más específicos del proceso de decisión:

```
   (f) MADUREZ de la organización
   (g) EXPERIENCIA del jefe de proyecto
   (h) DISPONIBILIDAD de información
   (i) DISTRIBUCIÓN GEOGRÁFICA de los interesados
```

Y el ejemplo: **en una organización muy madura, es muy probable que el problema de seleccionar requisitos se considere más estructurado**, con un procedimiento de guía claro para resolverlo.

---

## 7. Un catálogo de decisiones de IR 🟡

El capítulo enumera decisiones típicas en cada nivel.

### Decisiones estratégicas

**No se encuentran con frecuencia y son usualmente NO estructuradas.**

**Identificación de las metas de negocio.** Define el alcance de un producto o una organización.

> **Está entre las decisiones más importantes de la IR.** La IR dirigida por metas (capítulo 9) provee un enfoque sistemático, mostrando que **las metas son el fundamento de casi todas las demás actividades**. Los resultados —las metas de negocio— **se usan para guiar el proceso de elicitación y para determinar si un requisito es relevante.** También sirven **como criterios en otros problemas**: priorización, selección, planificación de proyecto y de versiones.

**Selección del proceso de IR.** Otra decisión importante a nivel organizacional, **que algunas organizaciones eligen no enfrentar**. Se guía por las metas de negocio, y tiene muchas sub-decisiones:

```
   ¿debería la organización tener un proceso de IR
    establecido?
   ¿debería usar uno existente o crear el propio?
   ¿cuál, entre los existentes?
   ¿cómo adaptarlo a la organización?
   ¿debería cambiar el proceso actual para enfrentar
    desafíos nuevos?
```

### Decisiones tácticas

**Son principalmente sobre planificación y usualmente semi-estructuradas.** Cualquier jefe de proyecto las enfrenta en todo proyecto — **lo que significa que tenemos cierto conocimiento sobre ellas, pero no suficiente para considerarlas estructuradas.**

Y la caracterización precisa de por qué son semi-estructuradas:

> **Para muchos de estos problemas no es muy difícil identificar el conjunto de alternativas. Hay acuerdo general sobre el conjunto de criterios. Sin embargo, NO HAY UN PROCEDIMIENTO AMPLIAMENTE ACEPTADO para evaluar cada alternativa contra cada criterio y para agregarlos hasta llegar a la decisión final.**

**Identificación de interesados.** *"La participación de los interesados puede ser un factor clave del éxito."* El problema puede formularse como una o varias de estas decisiones:

```
   ¿debería invitarse a esta persona como interesada?
    (cada candidato por separado)
   ¿quiénes son los interesados? (todos los candidatos)
   ¿qué nivel de participación esperar de ellos?
   ¿deberíamos priorizar a los interesados?
```

**Selección de requisitos.** *"¿Qué requisitos deberían implementarse?"* Puede formularse como problema de **priorización** (para poder seleccionar los más deseados), de **negociación** (alcanzar consenso entre interesados sobre qué implementar), o simplemente de **selección** (elegir un subconjunto mediante un procedimiento especial o de optimización).

**Planificación de versiones.** Una generalización del problema de selección **con un horizonte temporal extendido** (dos o más versiones). **De alta importancia, porque materializa la visión de largo plazo de la organización. Su complejidad es muy alta.**

### Decisiones operativas

**Se encuentran con frecuencia y conciernen tareas específicas.** Se esperaría que sean **más estructuradas, menos importantes y por lo tanto más fáciles de manejar.**

**Pero no siempre es así**, y el contraejemplo es bueno:

> **Las pruebas de aceptación son una decisión operativa que es a la vez DIFÍCIL E IMPORTANTE.** Para las pruebas de aceptación, **rara vez pasa que un producto sea perfecto: tenemos que aceptar el producto con cierta tolerancia.** Consideramos el problema semi-estructurado.

---

## Mapa de la Parte 1

```
   "los requisitos SIGNIFICAN decisiones"
   "la gestión de requisitos no es posible sin
    gestión de decisiones"

   ─────────────────────────────────────────────

   QUÉ HACE QUE ALGO SEA UNA DECISIÓN
   1. hay ALTERNATIVAS (si hay una sola, no hay
      nada que decidir)
   2. hay CRITERIOS declarados (si no, es azar,
      no decisión)

   tipos: selección · triaje · ordenamiento

   ─────────────────────────────────────────────

   ESTRUCTURADA ────► repetitiva, proceso claro,
                      información precisa
   NO ESTRUCTURADA ─► novedosa, proceso ambiguo

   ══► LA IR ES SEMI-ESTRUCTURADA ◄══
   los problemas NO son novedosos, pero los procesos
   son ambiguos: se pueden identificar criterios,
   pero cómo EVALUARLOS y AGREGARLOS no está resuelto

   ─────────────────────────────────────────────

   LOS 3 NIVELES (Anthony, igual que en el cap. 1)
   ESTRATÉGICO ─► objetivos, largo plazo, NO estructuradas
                  · metas de negocio · proceso de IR a usar
   TÁCTICO ─────► planificación, semi-estructuradas
                  · identificar interesados · seleccionar
                    requisitos · planificar versiones
   OPERATIVO ───► tareas específicas
                  · pruebas de aceptación (difícil e
                    importante, contra lo esperado)
```

---

## Preguntas para chequear que quedó

1. ¿Qué significa la afirmación "los requisitos significan decisiones"?
2. ¿Por qué las decisiones de requisitos son difíciles, según el argumento central del capítulo?
3. ¿Cuáles son los dos factores esenciales sin los cuales no hay decisión?
4. ¿Qué pasa si hay alternativas pero no hay criterios declarados?
5. Nombrá los tres tipos de problema de decisión.
6. ¿Por qué el conjunto de alternativas puede evolucionar durante el proceso?
7. Diferenciá decisión estructurada de no estructurada. Dé el ejemplo de cada una.
8. ¿De qué depende el grado de estructura de un problema?
9. ¿Por qué el proceso de IR se considera semi-estructurado o no estructurado?
10. ¿Qué relación tiene eso con que se valore el criterio fundamentado por encima de la respuesta canónica?
11. Nombrá los tres niveles de decisión con su alcance y horizonte.
12. Diferenciá la perspectiva centrada en requisitos de la centrada en actividades.
13. ¿Por qué el contexto "sistema específico para un cliente" contra "sistema listo para usar" cambia el soporte a la negociación?
14. Nombrá los cuatro contextos que identifica la perspectiva centrada en actividades.
15. ¿Por qué la identificación de metas de negocio es una de las decisiones más importantes de la IR?
16. ¿Qué caracteriza exactamente a una decisión táctica como semi-estructurada?
17. ¿Por qué las pruebas de aceptación son un contraejemplo de que las decisiones operativas sean fáciles?

---

**FIN DEL CAPÍTULO 12 — PARTE 1**

*Sigue en la Parte 2: las dos escuelas de pensamiento —tomar decisiones contra dar soporte a la decisión—, el análisis de la investigación existente, y la agenda de investigación futura.*
