# Lectura en español — Cap. 9 · Parte 2: Modelar, formular y razonar con metas

> **Origen.** Capítulo 9, secciones 9.2.3 y 9.2.4, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Colette Rolland y Camille Salinesi**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1.** Se asume conocida la distinción entre meta, requisito y suposición, y los seis papeles de las metas.

---

## Lo que hay acá

Esta parte tiene **la sección más aprovechable de todo el capítulo para tu cursada**: la comparación entre **metas y escenarios**, que está en el apartado 3. Si tenés poco tiempo, andá directo ahí.

El resto cubre las taxonomías de metas, los grafos Y/O, cómo se formulan las metas, cinco técnicas de razonamiento, y —al final— **las cinco debilidades que los propios autores le reconocen al enfoque**, que es una sección honesta y poco común.

---

## 1. Las taxonomías de metas 🟡

Las metas se modelan por **características intrínsecas** —como su tipo— y por **enlaces** con otras metas o con otros elementos del modelo de requisitos.

Se propusieron varios esquemas de clasificación:

### 1.1 Funcionales contra no funcionales

La primera y más conocida:

| | Qué subyace |
|---|---|
| **Metas funcionales** | **Los servicios que se espera que el sistema entregue** |
| **Metas no funcionales** | **Las cualidades esperadas del sistema**: seguridad, protección, rendimiento, usabilidad, flexibilidad, personalización, interoperabilidad, y demás |

### 1.2 Metas duras y metas blandas 🔴

Esta distinción es más fina y más útil:

| | Definición |
|---|---|
| **Metas duras** (*hard goals*) | Aquellas cuya satisfacción **puede establecerse mediante técnicas de verificación** |
| **Metas blandas** (*soft goals*) | Aquellas cuya satisfacción **no puede establecerse de manera tajante** |

**Para qué sirven las blandas, entonces:**

> **Las metas blandas son especialmente útiles para comparar refinamientos alternativos de metas y elegir el que contribuye "mejor" a ellas.**

#### Satisfacción y "satisfacción aproximada" 🟡

De ahí surge una distinción terminológica que el capítulo desarrolla:

Algunos autores extienden las relaciones entre metas para capturar **influencias positivas y negativas**: se dice que una submeta **contribuye parcialmente** a su meta padre. Eso lleva a la noción de ***satisfycing*** en vez de satisfacción.

```
   SATISFACCIÓN (marco CUANTITATIVO)
   se expresa en grafos Y/O de METAS DURAS
   puede VERIFICARSE cuantitativamente con algún criterio

   SATISFACCIÓN APROXIMADA (marco CUALITATIVO)
   se expresa con METAS BLANDAS
   NO puede establecerse de manera tajante
```

El ejemplo: *Asegurar la confidencialidad de las cuentas* y *Asegurar la seguridad de las cuentas* están unidas por **Y** a *Proteger las cuentas*. **Ambas contribuyen positivamente** a la satisfacción aproximada de la meta padre, pero ninguna la garantiza por sí sola ni de manera medible.

> ⚠️ **Cruce con la cátedra.** Esta distinción le da nombre a un problema que ya viste dos veces: en el capítulo 3, los **objetivos de diseño** que "no son realmente requisitos" hasta tener métrica; y en el capítulo 8, la **verificabilidad** como atributo de calidad.
>
> Una meta blanda es, exactamente, **una meta que no es verificable**. Y el capítulo no dice que haya que descartarlas: dice que **sirven para comparar alternativas**. Es decir: "el sistema debe ser fácil de usar" no sirve como requisito, **pero sí sirve para decidir entre dos diseños que hacen lo mismo**. Es el mismo movimiento que proponía el capítulo 3.

### 1.3 Por comportamiento temporal 🟢

Otra clasificación, según el tipo de comportamiento que la meta prescribe:

| Tipo | Qué hace |
|---|---|
| **De logro** (y su opuesto, **de cese**) | **Generan** comportamientos del sistema |
| **De mantenimiento** (y su opuesto, **de evitación**) | **Restringen** comportamientos |
| **De optimización** | **Comparan** comportamientos, para favorecer los que mejor aseguran alguna propiedad blanda |

Otras clasificaciones que menciona: según **estados deseados del sistema** (positivo, negativo, alternativo, de retroalimentación, de reparación de excepción) y según **nivel de meta** (de política, funcional, de dominio). Y una distinción entre **metas objetivas**, que refieren a objetos del sistema, y **metas adverbiales**, que refieren a **maneras de lograr** las objetivas.

**Para qué se usan las taxonomías:** para **formular** una meta y para **definir heurísticas** de adquisición de metas, refinamiento, derivación de requisitos y **chequeo semi-formal de consistencia y completitud**.

---

## 2. Los enlaces entre metas 🔴

### 2.1 Los grafos Y/O 🔴

> **La forma más común de un modelo de metas es un grafo Y/O.** Las relaciones Y/O —inspiradas en los grafos Y/O de la inteligencia artificial— se usan para capturar, respectivamente, **la descomposición de una meta en metas más operativas** y **las metas alternativas**.

```
   RELACIÓN Y (AND)
   TODAS las submetas deben satisfacerse
   para que la meta padre se logre

   RELACIÓN O (OR)
   si UNA de las metas alternativas se logra,
   la meta padre queda satisfecha
```

El ejemplo, de un sistema de préstamo de libros:

```
   Satisfacer el pedido del prestatario
        │ (Y)
        ├── Satisfacer el pedido bibliográfico
        ├── Satisfacer el pedido de libro
        └── Proveer un período de préstamo largo

   Satisfacer el pedido del cliente
        │ (O)
        ├── Mantener tantas copias como haga falta
        └── Mantener disponibilidad regular
```

### 2.2 Relaciones de conflicto 🔴

Otro tipo de relación entre metas:

> Se introdujeron **relaciones de conflicto** para capturar el hecho de que **una meta podría impedir que otra se satisfaga.**

Y el ejemplo del capítulo es excelente porque muestra el conflicto **dentro del mismo grafo**:

```
   "Proveer un período de préstamo largo"
        (submeta Y de "Satisfacer el pedido del prestatario")
                        ⚡ EN CONFLICTO CON ⚡
   "Mantener disponibilidad regular"
        (meta alternativa O de "Satisfacer el pedido del cliente")
```

> ⚠️ **Cruce con la cátedra.** Fijate en la mecánica: **las dos metas son razonables por separado y ambas están correctamente derivadas.** El conflicto no lo produce un error de nadie — lo produce el hecho de que **el mismo recurso (los libros) sirve a dos objetivos incompatibles**. Es exactamente el caso del capítulo 5 (`entra_en_conflicto_con`, con la razón "necesitar los mismos recursos") y del capítulo 7 (el conflicto es estructural, no accidental).
>
> Y notá algo útil: **el conflicto se hace visible porque el grafo pone las dos metas en la misma hoja.** Es un argumento a favor de modelar: no es decoración, es lo que hace que ciertos problemas salten a la vista.

---

## 3. Metas y escenarios 🔴🔴

**Esta es la sección más aprovechable del capítulo para tu materia.** Tu cronograma tiene, para la clase 11, el tema **"CU vs. Escenario"**. Acá está la comparación conceptual completa entre metas y escenarios, hecha por especialistas del área.

### El triángulo mágico

Lamsweerde introdujo lo que llamó **el triángulo mágico de la IR**, compuesto por **meta, escenario y agente**. Las metas tienen relaciones privilegiadas con los otros dos conceptos.

### Por qué se combinan 🔴

Muchos autores sugieren combinar metas y escenarios. Y la razón está en esta tabla, que conviene retener entera:

| **Metas** | **Escenarios** |
|---|---|
| **Declarativas** | **Procedurales** |
| Las intenciones **están explícitas** | Las intenciones **están implícitas** |
| **Abstractas** | **Concretas** |

> **Combinar metas y escenarios puede verse, por lo tanto, como una manera de mitigar las limitaciones que cada concepto tiene cuando se lo usa aisladamente.**

Y una cita que los autores recogen y que vale por sí sola:

> **Es imprudente aplicar métodos de requisitos basados en metas de manera aislada** — hay que complementarlos con escenarios.

### Para qué se usa la combinación

**El uso principal: hacer concretas las metas.**

> **Los escenarios pueden interpretarse como contenedores de información sobre CÓMO pueden lograrse las metas.**

Las posiciones que recoge el capítulo van escalando:

**Posición 1 — la meta como documentación.** Algunos consideran a la meta como **una propiedad contextual de un caso de uso** — una propiedad que relaciona el escenario con su contexto organizacional. En esta visión, **las metas juegan solo un papel documental**.

**Posición 2 — la meta como estructura.** Otros van más allá y sugieren **usar las metas para estructurar los casos de uso, conectando cada acción de un escenario con una meta asignada a un actor.** En ese sentido, **se descubre un escenario cada vez que se descubre una meta**.

**Y el capítulo hace notar:** todas esas visiones **sugieren una relación unidireccional** entre metas y escenarios.

### La relación bidireccional 🔴

La propuesta que los autores destacan va más lejos: **una relación bidireccional**.

```
   DE LA META AL ESCENARIO  (dirección hacia adelante)
   el escenario representa un comportamiento posible del
   sistema para lograr la meta
   → los escenarios ayudan a HACER CONCRETA la meta
   → y a DETECTAR METAS IRREALISTAS

   DEL ESCENARIO A LA META  (dirección hacia atrás)
   se usa para DESCUBRIR METAS NUEVAS mediante técnicas
   de minería
   → como el escenario representa un comportamiento
     concreto y realista, las metas inferidas de él
     deberían ser realistas también
```

> ⚠️ **Cruce con la cátedra — leelo con atención.** Tres cosas de esta sección te sirven directamente:
>
> **1. La tabla de tres filas es la respuesta corta a "meta vs. escenario".** Declarativo/procedural, intención explícita/implícita, abstracto/concreto. Y notá que **la misma estructura sirve para "caso de uso vs. escenario"** con otros contenidos: en el capítulo 2 viste que **el caso de uso es una abstracción de escenarios**. La constante es que **lo abstracto y lo concreto se necesitan mutuamente.**
>
> **2. "Es imprudente aplicar métodos basados en metas de manera aislada."** El argumento de fondo es que **lo abstracto solo no alcanza**, porque no se puede verificar contra nada. El escenario es lo que aterriza la meta.
>
> **3. La dirección hacia adelante detecta metas irrealistas.** Ese es un uso práctico y concreto: **si no podés escribir un escenario que muestre cómo se logra la meta, la meta probablemente sea irrealista o esté mal formulada.** Es el mismo test que viste en el capítulo 8 para la verificabilidad (si no podés escribir el caso de prueba, el requisito está mal), aplicado un nivel más arriba.
>
> ⚠️ **Ojo con el alcance, igual.** "Escenario" en este capítulo sigue siendo el sentido genérico de la literatura anglosajona, no el artefacto formal de Leite y Doorn que vas a construir en las clases 10 a 14. Lo que sí es transferible es la **relación conceptual** entre lo abstracto y lo concreto.

### 3.1 Metas y agentes 🟡

El tercer vértice del triángulo. Como la satisfacción de una meta requiere cooperación entre agentes, se enfatizaron las relaciones con ellos: en algunos modelos **una meta es el objeto de la dependencia entre dos agentes**; en otros, el enlace sirve para **capturar quién es responsable de una meta**.

### 3.2 Otros enlaces 🟢

Las metas también se enlazan con:

- **Operaciones** que las operacionalizan — como terminación lógica de la descomposición Y/O.
- **Objetos del sistema.**
- **Problemas, oportunidades y amenazas**, con el fin de entender mejor el contexto de una meta.
- **Obstáculos**, mediante relaciones de obstrucción y resolución.

---

## 4. Cómo se formulan las metas 🟡

La formulación es necesaria **para documentar el modelo y para sostener alguna forma de razonamiento**. Puede ser **informal, semi-formal o formal**.

### 4.1 Informal

Los enunciados de meta son a menudo **textos en lenguaje natural**, y pueden complementarse con **una especificación informal que precise qué designa el nombre de la meta**.

### 4.2 Semi-formal 🔴

**La motivación** para las formulaciones semi-formales o formales es **sostener alguna forma de análisis automático**.

**Las formulaciones semi-formales típicas usan una taxonomía y asocian el nombre de la meta a un tipo predefinido.** Eso **ayuda a clarificar el significado de la meta**. Ejemplos:

- Una meta no funcional puede especificarse como `Exactitud[cuenta.saldo]`.
- En un proyecto concreto, **las metas de cambio se prefijan con uno de siete tipos de cambio**: *Mantener, Cesar, Mejorar, Agregar, Introducir, Extender, Adoptar y Reemplazar*.

#### La formulación por verbo y parámetros 🔴

La propuesta más interesante de esta sección: **formular cada meta como una cláusula con un verbo principal y varios parámetros**, donde cada parámetro **juega un papel distinto respecto del verbo**.

```
   Retirar (efectivo) (del cajero automático)
      │        │              │
      │        │              └── parámetro MEDIO
      │        └───────────────── parámetro OBJETIVO
      └────────────────────────── VERBO PRINCIPAL
```

Los tipos de parámetro que enumera, cada uno con un papel distinto:

| Parámetro | Qué designa |
|---|---|
| **Objetivo** | Las **entidades afectadas** por la meta |
| **Medio** y **manera** | **Cómo** se logra la meta |
| **Beneficiario** | El **agente que se beneficia** del logro |
| **Destino** | En metas de comunicación, **a dónde va** |
| **Fuente** | Las **entidades necesarias** para lograr la meta |

Y una nota de origen: esta manera de formular **se basa en la gramática de casos de Fillmore**, un enfoque lingüístico donde **cada tipo de parámetro corresponde a un caso gramatical**.

> ⚠️ **Cruce con la cátedra — muy transferible.** Esta técnica de formulación es directamente aplicable a la redacción de requisitos y de nombres de casos de uso. **Verbo principal + parámetros con papeles declarados** produce enunciados que son difíciles de escribir mal:
>
> - Si no podés nombrar el **verbo**, no sabés qué hace.
> - Si no podés nombrar el **objetivo**, no sabés sobre qué actúa.
> - Si el **beneficiario** no aparece por ningún lado, quizás la meta no le sirva a nadie.
>
> Y conecta con algo que la cátedra sí pide explícitamente: **evitar el verbo "usar"** por ambiguo. En este esquema se ve por qué — *usar* no dice nada del objetivo ni del medio; es un verbo que no tiene casos que llenar.

### 4.3 Formal 🟢

Las especificaciones formales **requieren un esfuerzo mayor pero producen un razonamiento más potente.** Se expresan en lógica, con cuantificadores y predicados sobre las entidades del dominio.

---

## 5. Razonar con metas: cinco técnicas 🟡

> **El propósito último del modelado de metas es sostener alguna forma de razonamiento** para los subprocesos de la IR: elicitación, chequeo de consistencia y completitud, descubrimiento de obstáculos, resolución de conflictos.

Y una constatación de arranque que importa:

> **Aunque a veces los interesados expresan metas espontáneamente, LA MAYORÍA DE LAS METAS SON IMPLÍCITAS.** Por lo tanto, elicitar metas no siempre es una tarea fácil, y las técnicas de razonamiento pueden emplearse con provecho.

### 5.1 Elicitar metas por reutilización 🟢

Recuperar **metas que tengan especificaciones semántica y estructuralmente similares** de un repositorio de componentes reutilizables, y después **transponer las especificaciones encontradas** según la correspondencia que surgió de la recuperación.

### 5.2 Elicitar metas a partir de escenarios 🔴

Una técnica **inductiva** basada en el análisis de escenarios conceptualizados. La lógica:

> Se toman **escenarios como ejemplos y contraejemplos del comportamiento pretendido del sistema**, y **se generan metas que cubran los escenarios positivos y excluyan los negativos.**

> Es la dirección "hacia atrás" de la relación bidireccional que viste en la sección 3, hecha operativa.

### 5.3 Elicitar metas por refinamiento 🔴

Los enfoques centrados en metas apuntan a ayudar en el movimiento **desde las preocupaciones estratégicas y las metas de alto nivel hacia las preocupaciones técnicas y las metas de bajo nivel de abstracción**.

**Las jerarquías medio-fin.** Inspirados en la ingeniería cognitiva, algunos enfoques trabajan con **jerarquías medio-fin**, donde **cada nivel jerárquico representa un modelo distinto del mismo sistema**:

> **La información de cualquier nivel actúa como una meta (el fin) respecto del modelo del nivel inmediatamente inferior (el medio).**

**Y la técnica más simple de todas:**

> **Otra técnica obvia para refinar es descomponer preguntando "¿CÓMO?".**

```
   ¿CÓMO? ────► baja hacia el detalle (descompone)
   ¿POR QUÉ? ─► sube hacia la justificación
```

> ⚠️ **Cruce con la cátedra.** Este par de preguntas es la herramienta más barata del capítulo, y es la misma que aparecía en los enfoques basados en metas del capítulo 2. Sirve para **ubicar cualquier enunciado en su nivel**: si preguntás "¿por qué?" y no hay respuesta, estás en la cima (o el enunciado no tiene justificación, que es peor). Si preguntás "¿cómo?" y no hay respuesta, ya estás en el nivel operativo.

### 5.4 Elaboración dirigida por obstáculos 🔴

> **Los modelos de metas parecen ser instrumentos potentes para razonar sobre peligros.**

Las dos definiciones:

| | Definición |
|---|---|
| **Obstáculo** | **Un fenómeno que ocurre en el sistema y/o en su entorno y que obstruye el logro de la meta** |
| **Conflicto** | **Cuando el logro de dos metas distintas se obstruye mutuamente** |

**Y una aplicación derivada que vale la pena conocer:**

> Un principio similar se usa para construir **descripciones de casos de mal uso** (*misuse cases*). **Un caso de mal uso es un caso de uso descrito desde el punto de vista de un actor hostil. La meta de ese actor es usar las funciones del sistema para un propósito distinto del pretendido inicialmente.**

> ⚠️ **Cruce con la cátedra.** El caso de mal uso es un concepto directamente robable y fácil de aplicar: **tomá tus casos de uso y reescribilos desde la perspectiva de alguien que quiere abusar del sistema.** Es una técnica de descubrimiento de requisitos —sobre todo no funcionales de seguridad— que sale casi gratis si ya tenés los casos de uso hechos.
>
> Y conecta con la lectura basada en perspectivas del capítulo 8: es la misma idea —leer el mismo artefacto desde un rol distinto— con un rol especialmente productivo.

### 5.5 Resolución de conflictos 🟡

Razonar con metas también ayuda a **resolver conflictos entre interesados**. Algunos autores **generalizan las nociones de obstáculo, conflicto y otras amenazas del sistema en la noción de amenaza**, porque todas corresponden **al impedimento parcial o total de una o varias metas del sistema**.

---

## 6. Las cinco debilidades 🔴

Esta sección es poco común: **los autores le reconocen al enfoque cinco problemas reales**, y varios de ellos aplican a cualquier trabajo con metas o con requisitos abstractos.

### 6.1 Mitigar la abstracción de las metas

> **Nuestra propia experiencia en varios dominios** —control de tráfico aéreo, suministro eléctrico, gestión de recursos humanos, desarrollo de herramientas— **es que a los expertos del dominio les resulta difícil lidiar con el concepto abstracto de una meta.**
>
> **La autoría de escenarios es una de las pocas maneras usadas para hacer más concreta una meta. Hacen falta más mecanismos.**

> Es la confirmación empírica de lo que decía la sección 3: **lo abstracto solo no funciona con la gente real.**

### 6.2 Encontrar la meta correcta 🔴

Este es el más filoso de los cinco:

> **Se asume a menudo que los sistemas se construyen con algunas metas en mente. Sin embargo, la experiencia práctica muestra que las metas no están dadas**, y por lo tanto **la pregunta de dónde se originan adquiere importancia.**
>
> Además, **las metas empresariales que inician el proceso de descubrimiento NO REFLEJAN LA SITUACIÓN REAL, SINO UNA IDEALIZADA.** Por lo tanto, **partir de metas espurias puede llevar a requisitos inefectivos.**

> ⚠️ **Cruce con la cátedra.** Retené esto: **las metas declaradas de una organización son la versión de folleto.** Lo que la empresa dice que persigue y lo que realmente hace todos los días pueden no coincidir. Es el mismo hallazgo que la etnografía del capítulo 2 —el proceso oficial y el proceso real difieren— visto desde el nivel estratégico.
>
> En un TP con un negocio asignado, esto significa: **no tomes la descripción del negocio como verdad literal.** Es un punto de partida, no un dato.

### 6.3 Quitar la difusidad de las metas 🔴

> **El enunciado inicial de una meta es usualmente bastante impreciso y esquemático, y puede interpretarse de muchas maneras. El significado exacto se va aclarando a medida que el proceso de elicitación avanza.**
>
> Sin embargo, la experiencia muestra que **es mejor hacer un enunciado preciso y formal de la meta lo más temprano posible** en el proceso, y que **el enunciado informal debe llevarse a una forma que permita realizar el análisis.**
>
> **Los enfoques basados en metas deben sostener mejor la formulación, evitando no obstante la carga de los lenguajes formales.**

> Ese "evitando no obstante la carga de los lenguajes formales" es la tensión central: **precisión sin volverse ilegible para el cliente.** Es el mismo compromiso que planteaba el capítulo 8 con los métodos formales.

### 6.4 Sostener la operacionalización 🟡

> **Se demostró que aplicar métodos de reducción de metas para descubrir las metas componentes de una meta no es tan directo como la literatura sugiere.** Es evidente que **hace falta ayuda para lograr un modelado significativo.**

### 6.5 Guiar el descubrimiento de alternativas 🟡

> **Encontrar metas alternativas a una meta padre es crucial para imaginar el sistema futuro.** Sin embargo, **la experiencia muestra que el proceso es manual, improvisado e insatisfactorio.** Es similar a lo observado en el descubrimiento de variantes de casos de uso.
>
> **Hace falta soporte automatizado**, ya que **una generación exhaustiva de alternativas es muy difícil de practicar manualmente.**

---

## Mapa de la Parte 2

```
   TAXONOMÍAS
   funcionales / no funcionales
   DURAS (verificables) / BLANDAS (no verificables,
     sirven para COMPARAR alternativas)
   logro · cese · mantenimiento · evitación · optimización

   ─────────────────────────────────────────────

   ENLACES
   grafo Y/O:  Y = todas las submetas
               O = alternativas
   CONFLICTO: dos metas correctas que se obstruyen
              (el grafo las hace VISIBLES)

   ─────────────────────────────────────────────

   ══► METAS vs ESCENARIOS ◄══

   METAS              ESCENARIOS
   declarativas       procedurales
   intención          intención
   EXPLÍCITA          IMPLÍCITA
   abstractas         concretas

   "es imprudente aplicar métodos basados en metas
    de manera aislada"

   bidireccional:
   meta → escenario: hace CONCRETA la meta y
                     detecta metas IRREALISTAS
   escenario → meta: descubre metas nuevas, y como
                     el escenario es realista, las
                     metas inferidas también

   ─────────────────────────────────────────────

   FORMULACIÓN
   verbo principal + parámetros con papel declarado
   objetivo · medio · manera · beneficiario ·
   destino · fuente

   ─────────────────────────────────────────────

   RAZONAMIENTO
   reutilización · desde escenarios · refinamiento
   (¿CÓMO? baja, ¿POR QUÉ? sube) ·
   OBSTÁCULOS (+ casos de MAL USO) · conflictos

   ─────────────────────────────────────────────

   LAS 5 DEBILIDADES
   1. la meta es demasiado ABSTRACTA para la gente real
   2. las metas declaradas son IDEALIZADAS, no reales
   3. el enunciado inicial es DIFUSO
   4. descomponer no es tan directo como se dice
   5. encontrar alternativas es manual e improvisado
```

---

## Preguntas para chequear que quedó

1. Diferenciá metas duras de metas blandas. ¿Para qué sirven las blandas si no se pueden verificar?
2. ¿Qué diferencia hay entre satisfacción y "satisfacción aproximada"? ¿Con qué tipo de meta va cada una?
3. Nombrá los tres tipos de meta según el comportamiento temporal que prescriben.
4. Explicá las relaciones Y y O de un grafo de metas.
5. En el ejemplo del sistema de préstamo, ¿qué dos metas entran en conflicto y por qué? ¿Alguna de las dos está mal formulada?
6. Nombrá los tres vértices del "triángulo mágico".
7. Compará metas y escenarios en las tres dimensiones de la tabla.
8. ¿Por qué es "imprudente" aplicar métodos basados en metas de manera aislada?
9. Explicá la relación bidireccional entre metas y escenarios. ¿Qué aporta cada dirección?
10. ¿Cómo se usan los escenarios para detectar metas irrealistas?
11. ¿Cuál es la motivación de las formulaciones semi-formales o formales?
12. Descomponé la meta "Retirar efectivo del cajero automático" en verbo y parámetros. Nombrá el papel de cada parámetro.
13. ¿Por qué el verbo "usar" es problemático desde el punto de vista de esta manera de formular?
14. ¿Por qué elicitar metas no es fácil, aunque los interesados a veces las expresen espontáneamente?
15. Explicá cómo se eliciten metas a partir de escenarios positivos y negativos.
16. ¿Qué hace la pregunta "¿cómo?" y qué hace "¿por qué?" en el refinamiento?
17. Definí obstáculo y conflicto. ¿En qué se diferencian?
18. ¿Qué es un caso de mal uso y cómo se construye? ¿Con qué técnica del capítulo 8 se conecta?
19. ¿Por qué a los expertos del dominio les cuesta trabajar con metas? ¿Cuál es la única solución que menciona el capítulo?
20. ¿Por qué las metas empresariales declaradas pueden llevar a requisitos inefectivos?
21. ¿Cuál es la tensión que plantea la debilidad de la "difusidad"?
22. ¿Por qué encontrar metas alternativas es un problema práctico?

---

**FIN DEL CAPÍTULO 9 — PARTE 2**

*Sigue en la Parte 3: los mapas meta/estrategia — la propuesta propia de los autores para modelar sistemas multi-propósito, con su formalismo, el ejemplo del módulo de gestión de materiales de SAP, y el proceso de personalización.*
