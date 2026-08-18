# Lectura en español — Cap. 12 · Parte 2: Soporte a la decisión contra toma de decisiones

> **Origen.** Capítulo 12, secciones 12.3 a 12.5, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **An Ngo-The y Günther Ruhe**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1.** Se asume conocida la clasificación estructurado / semi-estructurado / no estructurado y los tres niveles de decisión.

---

## 1. Las dos escuelas de pensamiento 🔴

### El obstáculo

Los autores identifican el problema de fondo de la investigación en IR dirigida por decisiones:

> **El obstáculo principal reside en el DESEO DE RESOLVER TODO PROBLEMA FORMAL Y RIGUROSAMENTE.** Eso presupone que **cada problema puede describirse apropiadamente mediante un modelo formal y "resolverse" usando solo ese modelo. Equipara la toma de decisiones con encontrar la solución óptima.**

Y señalan que ese mismo pensamiento **fue dominante alguna vez en las ciencias de la administración y en la investigación operativa**. La realidad fue otra:

> **Pese al enorme progreso en optimización e investigación operativa, muchas preguntas del mundo real no podían responderse de manera satisfactoria. En muchas situaciones reales, insistir en establecer el modelo ideal y buscar la solución numéricamente óptima TERMINA EN UN CALLEJÓN SIN SALIDA.**

A esos problemas se los caracterizó como **"problemas perversos"** — el mismo término que ya viste en el capítulo 4 sobre planificación de versiones.

De ahí nace la escuela que **enfatiza estudiar el SOPORTE a la decisión (o la ayuda) en vez de la TOMA de decisiones.**

### Las seis diferencias 🔴🔴

Esta tabla es lo mejor del capítulo. Vale la pena leerla entera.

| | **Toma de decisiones** | **Soporte a la decisión** |
|---|---|---|
| **Qué se busca** | **"LA" decisión óptima.** Cree en la existencia y la relevancia de una solución óptima. Su misión es **encontrarla, o ayudar al que decide a encontrarla** | **"UNA" decisión satisfactoria.** Reconoce que **en muchas situaciones esa solución óptima NO EXISTE.** Su misión es ayudar al que decide **a encontrar una decisión satisfactoria para el problema real** |
| **Para qué sirve el modelo** | **Modelo DESCRIPTIVO:** se apoya en modelos **para describir una realidad**. Los modelos **solo deberían aceptarse cuando son "suficientemente buenos"** para resolver el problema | **Modelo EXPLORATIVO:** acepta que cuando **ningún esfuerzo puede producir un modelo realista y suficientemente bueno**, entonces **los modelos deberían usarse como MEDIO PARA EXPLORAR LA REALIDAD** |
| **El proceso** | Una vez que hay un modelo, **se lo usa para resolver el problema y obtener la solución óptima** | **El proceso de entendimiento CONTINÚA con la evolución de los modelos** hasta alcanzar una solución satisfactoria. **Pueden usarse modelos distintos iterativamente** |
| **Comparar alternativas** | La creencia en la solución óptima implica que **debe existir una manera de comparar todas las alternativas** mediante una evaluación | **Cuando es demasiado difícil comparar dos alternativas, SE ACEPTA QUE NO PUEDEN COMPARARSE** |
| **Tipos de problema** | Como todo debe poder ordenarse, **no hace falta distinguir entre selección, triaje y ordenamiento** | **Esa distinción tiene sentido solo para esta escuela** |
| **Estructura del problema** | Si se propone un modelo para resolver un problema, **se asume que el problema ya está estructurado** | **Cuando el problema NO está estructurado, igual se puede avanzar**, esperando encontrar una solución satisfactoria en vez de la óptima |

### La frase que hay que retener 🔴

De la segunda fila sale la formulación más elegante del capítulo:

> **En la TOMA DE DECISIONES debemos ENTENDER LA REALIDAD PARA CREAR EL MODELO.**
>
> **En el SOPORTE A LA DECISIÓN usamos LOS MODELOS PARA ENTENDER LA REALIDAD.**

```
   TOMA DE DECISIONES
   realidad ──entender──► MODELO ──resolver──► óptimo

   SOPORTE A LA DECISIÓN
   MODELO ──explorar──► realidad ──► modelo mejor
      ▲                                    │
      └────────── iterar ──────────────────┘
```

> ⚠️ **Cruce con la cátedra — esto reencuadra para qué modelás.** La frase invierte la intuición habitual: **no modelás porque ya entendiste; modelás PARA entender.**
>
> Es exactamente lo que constataba el capítulo 11 en su técnica de detección de ambigüedad: la pregunta *"¿hay requisitos que ahora interpretás distinto después de haber construido el modelo?"* **presupone que construir el modelo cambia lo que entendés del texto.** Si el modelo fuera solo un registro de lo que ya sabías, esa pregunta no tendría sentido.
>
> Y da un argumento contra una tentación común en los TP: **esperar a "entender bien el caso" antes de empezar a diagramar.** El diagrama es una de las herramientas para entenderlo. Un modelo temprano y provisorio que se corrige tres veces enseña más que uno solo, tardío y prolijo.
>
> Conecta también con el capítulo 4: allí la conclusión era que *el propósito de priorizar no es producir la lista final, sino sostener la decisión*. Es la misma escuela, aplicada a otro problema.

---

## 2. El caso de la planificación de versiones 🟡

Los autores usan un problema concreto para mostrar la diferencia.

> **Una versión de software es una colección de funcionalidades nuevas o modificadas que forman un producto nuevo. La planificación de versiones asigna funcionalidades a versiones de modo que se cumplan las restricciones técnicas, de recursos, de riesgo y de presupuesto más importantes.**

### El argumento de la complementariedad 🔴

Y acá viene el razonamiento más útil de la sección:

> **Ni la sutileza del juicio humano ni la fuerza rígida del modelo computacional, POR SÍ SOLOS, son capaces de proveer soporte apropiado al problema perverso de la planificación de versiones.**

Porque cada uno tiene una ventaja donde el otro falla:

| | **La ventaja del juicio humano** | **La ventaja del modelo computacional** |
|---|---|---|
| | **Manejar objetivos y restricciones BLANDOS E IMPLÍCITOS** | **Cubrir una porción grande del espacio de soluciones** |
| **Por qué el otro no puede** | — | **La complejidad computacional del problema vuelve imposible que el que decide tenga una percepción razonable del conjunto de soluciones posibles**, y que las evalúe y priorice |

**La integración de los dos**, entonces, tiene dos aspectos:

```
   1. con la fuerza del MODELO COMPUTACIONAL podemos
      esperar soluciones a problemas formalmente
      definidos de tamaño y complejidad grandes

   2. el soporte a la decisión necesita la inclusión del
      JUICIO HUMANO para incorporar componentes tácitos
      y subjetivos al proceso de seleccionar las
      soluciones más prometedoras
```

**Y un efecto secundario que vale:**

> **Típicamente, de esa participación surgen preguntas nuevas que llevan a un mejor entendimiento del jefe de proyecto sobre distintos aspectos del problema.**

> ⚠️ **Cruce con la cátedra.** Retené la asimetría: **lo blando e implícito lo maneja la persona; la cobertura exhaustiva la maneja el método.** Es un principio general de división del trabajo entre criterio y procedimiento, y aplica más allá de la planificación de versiones.
>
> Por ejemplo, a la revisión de un entregable: **el chequeo mecánico** (buscar frases débiles, correr la lista de verificación de ambigüedad) **cubre terreno que la lectura atenta se saltea**; y **la lectura atenta ve lo que ninguna lista puede codificar.** No compiten — se necesitan.

---

## 3. El análisis de la investigación 🟢

Los autores hacen un relevamiento sistemático de lo publicado sobre decisiones en IR.

### El esquema de clasificación 🟢

Clasifican cada trabajo en **tres dimensiones**:

**Dimensión 1 — el problema:**

- **General:** discute aspectos de la toma de decisiones en IR **sin abordar un problema particular**.
- **Específico:** discute **problemas concretos** como identificación de interesados o negociación.

**Dimensión 2 — la contribución:**

| | Qué aporta |
|---|---|
| **Orientada al proceso** | Propone **un método en términos de un proceso o una guía**. **No presenta representación formal, modelado ni manipulación algorítmica** |
| **Orientada al producto** | **El problema se formula con un modelo formal y se resuelve con algún algoritmo.** Puede haber un proceso, pero **el núcleo de la contribución es un modelo formal o una herramienta** |
| **Entendimiento** | Reporta sobre **el estado de la práctica, de la investigación, o discute un tema** relacionado |

**Dimensión 3 — el carácter de la investigación:**

| | Qué hace |
|---|---|
| **Descriptiva** | Describe **cómo se toman REALMENTE las decisiones de IR en la realidad** |
| **Prescriptiva** | Describe **cómo DEBERÍAN tomarse** |
| **Otra** | Ni una ni otra |

**El alcance:** publicaciones de los últimos cinco años en siete revistas y tres conferencias del área. Y una dificultad metodológica que declaran:

> **Como la toma de decisiones en IR todavía no es un tema de investigación establecido, no pudimos determinar los trabajos usando palabras clave.**

**El resultado:** identificaron **44 trabajos**.

### Las siete observaciones 🟡

**1. El tema no está en el radar.** Buscar por "decisión" e "ingeniería de requisitos" **dio muy pocos resultados**; esas dos palabras clave **ni siquiera aparecen en muchos de los trabajos seleccionados.** Pese a una revisión de alcance amplio, **solo 44 trabajos tenían relación significativa** con problemas de decisión.

**2. Hay una discrepancia.** Entre la afirmación de que **el proceso de IR está lleno de decisiones difíciles** y el hecho de que **muy pocos problemas de decisión se formulan explícitamente en la literatura.** La explicación tentativa: **la percepción de los requisitos como decisiones es reciente**, y muchas decisiones **todavía no se identifican como suficientemente importantes** para tratarse como problema explícito.

**3. La distribución es desigual.** Los trabajos sobre **planificación, priorización y negociación dominan** (21 de 35 sobre problemas específicos). **Hay muy pocos sobre elicitación y sobre decisiones estratégicas.** Sobre la elicitación, la explicación: **la mayoría de los trabajos discute solo el proceso y no lo relaciona con la toma de decisiones.** Y una hipótesis honesta: **puede ser porque ciertas decisiones son demasiado fáciles —la guía del proceso alcanza— y otras demasiado difíciles, incluso de formular.**

**4. Los problemas no técnicos empiezan a reconocerse.** 🔴 Esta observación vale la pena:

```
   · "la gestión de requisitos es, de hecho, un
      PROCESO POLÍTICO"
   · "en muchos casos, las decisiones importantes que se
      toman en la industria del software son SUBJETIVAS"
   · "los requisitos de sistemas de gran escala se
      construyen mediante un proceso de decisión complejo
      en el que LA AMBIGÜEDAD POLÍTICA puede jugar un
      papel tan significativo como la COMPLEJIDAD
      DEL DOMINIO"
   · la IR debería abordarse con un enfoque que vaya
      MÁS ALLÁ DE LO TÉCNICO: un "proceso socialmente
      mediado"
```

> ⚠️ **Cruce con la cátedra.** La tercera de esas afirmaciones es la más filosa: **lo político puede pesar tanto como lo técnico.** Es lo mismo que señalaba el capítulo 7 sobre negociación ("los interesados son individuos con personalidades y agendas personales… ignorar esas cuestiones eleva el riesgo") y el capítulo 2 sobre trabajo grupal ("es menos efectivo en situaciones altamente politizadas"). **Tres capítulos, escritos por equipos distintos, insistiendo en que la parte social no es ruido alrededor del problema técnico: es parte del problema.**

**5. Domina la optimización.** De las técnicas usadas para resolver problemas de decisión, **el enfoque más popular sigue siendo la optimización** —maximizar ganancia, valor. **La aplicación de técnicas nuevas como simulación, inteligencia artificial y sistemas de soporte a la decisión sigue siendo limitada.**

**6. Falta investigación descriptiva.** 🔴 Solo **siete** de los 44 trabajos son descriptivos, y algunos ni siquiera del todo, porque **están diseñados para validar un método propuesto por los autores** — quedando **en algún lugar entre la descripción del mundo real y la prescripción del modelo en consideración.**

Y el argumento de por qué eso importa:

> **Dado que la investigación en decisiones de IR está en su infancia, la investigación descriptiva es particularmente importante. Sin un entendimiento profundo de CÓMO manejan los profesionales los problemas actualmente y POR QUÉ hacen lo que hacen, no tenemos una base sólida para prescribir soluciones adecuadas que los profesionales puedan aceptar.**
>
> **Esto podría ser uno de los factores que ensanchan la brecha entre investigadores y profesionales.**

**7. El mismo problema, tres lecturas distintas.** 🔴 La última observación es la más instructiva. Sobre **la planificación de versiones**, hay tres enfoques que **implican tres suposiciones distintas sobre qué clase de problema es**:

| Enfoque | Qué asume |
|---|---|
| Un estudio comprensivo concluye que **el problema es "perverso"** | **NO estructurado** |
| Un modelo que usa datos financieros para **optimizar el retorno de inversión** — recolectar los datos, aplicar el modelo, obtener la solución óptima | **ESTRUCTURADO.** Puede ser cierto en su contexto: una organización con alta madurez y datos suficientes |
| Enfoques que **combinan técnicas de inteligencia artificial, bases de experiencia y patrones de evolución** para apoyar el proceso | **SEMI-estructurado** |

> El mismo problema, y cada equipo lo trata como una clase distinta. **La clase del problema no es una propiedad del problema: es una propiedad de cuánto sabemos sobre él, y eso varía según el contexto.** Es lo que decía la Parte 1: *el grado de estructura depende esencialmente de nuestro conocimiento sobre el proceso para manejarlo.*

---

## 4. Conclusión y agenda 🔴

### La tesis del cierre

> **Las decisiones sobre tecnologías, procesos, recursos y herramientas de software son los puntos de cristalización para lograr calidad en productos y servicios dependientes de software. El impacto de las mejores decisiones es más fuerte cuanto más temprano en el ciclo de vida hay que tomarlas.**
>
> **Las decisiones en ingeniería de software deberían basarse tanto en objetivos y restricciones formulados explícitamente como en aquellos conocidos implícitamente.**

Y la frase que resume la posición del capítulo:

> **La meta del soporte a la decisión NO ES REEMPLAZAR el juicio y la pericia humanos, sino ASISTIR a los humanos a tomar mejores decisiones.**

### El argumento contra la optimalidad 🔴

> **La IR es un proceso dirigido por decisiones e impactado por un alto grado de INCERTIDUMBRE. La incertidumbre puede surgir de las organizaciones, las personas, las tecnologías, la funcionalidad, el tiempo, el presupuesto y los recursos.**
>
> **Bajo esas circunstancias NO TIENE SENTIDO BUSCAR SOLUCIONES ÓPTIMAS, sino más bien determinar alternativas de solución razonables.**
>
> **Ninguna técnica formalizada AISLADA es probable que determine resultados significativos, porque solo puede tomarse en cuenta un subconjunto de la realidad. La inteligencia humana provista por expertos del dominio o de la solución tiene más probabilidad de abordar los factores ocultos que son parte de la toma de decisiones humana.**

### La agenda de investigación 🟢

Seis líneas propuestas:

```
   1. IDENTIFICAR y estudiar más problemas de decisión
      del proceso de IR — investigadores y profesionales
      deberían trabajar juntos

   2. AVANZAR la metodología de soporte, con énfasis en
      DECISIONES BAJO INCERTIDUMBRE — hay técnicas
      disponibles en otras disciplinas: teoría de la
      probabilidad, estadística, estimación bayesiana,
      conjuntos y lógica difusa, teoría de conjuntos
      aproximados

   3. DESARROLLAR enfoques que exploten la estructura
      específica de los problemas de decisión de
      requisitos. Hay una falta sustancial en abordar
      apropiadamente los problemas ESTRATÉGICOS

   4. VALIDAR el impacto de las mejores decisiones sobre
      procesos y productos — hace falta determinar el
      valor agregado de decidir de manera más sistemática

   5. INVESTIGAR la influencia de las cuestiones NO
      TÉCNICAS: políticas, sociales, organizacionales
      y culturales

   6. ESTUDIOS EMPÍRICOS más comprensivos y más enfocados
```

---

## Mapa de la Parte 2

```
   ══► LAS DOS ESCUELAS ◄══

   TOMA DE DECISIONES        SOPORTE A LA DECISIÓN
   busca LA óptima           busca UNA satisfactoria
   modelo DESCRIPTIVO        modelo EXPLORATIVO
   modelo → resolver         modelos EVOLUCIONAN
   todo es comparable        se acepta lo incomparable
   asume problema            sirve para problemas
   estructurado              NO estructurados

   ══► "en la toma de decisiones ENTENDEMOS LA REALIDAD
        PARA CREAR EL MODELO;
        en el soporte a la decisión USAMOS LOS MODELOS
        PARA ENTENDER LA REALIDAD" ◄══

   ─────────────────────────────────────────────

   JUICIO HUMANO vs MODELO COMPUTACIONAL
   humano ──► objetivos y restricciones BLANDOS
              e IMPLÍCITOS
   modelo ──► cubrir el ESPACIO DE SOLUCIONES
   ninguno alcanza solo → integrarlos

   ─────────────────────────────────────────────

   ANÁLISIS DE 44 TRABAJOS
   · el tema casi no está en el radar
   · domina la optimización
   · casi NO HAY investigación DESCRIPTIVA
     → sin saber cómo se hace realmente, no hay base
       para prescribir
   · lo POLÍTICO puede pesar tanto como lo técnico
   · el mismo problema (planificar versiones) es tratado
     como estructurado, semi y no estructurado según
     el equipo → la clase del problema depende de
     CUÁNTO SABEMOS, no del problema

   ─────────────────────────────────────────────

   "la meta del soporte a la decisión no es REEMPLAZAR
    el juicio humano, sino ASISTIRLO"
```

---

## Preguntas para chequear que quedó

1. ¿Cuál es el obstáculo principal de la investigación en IR dirigida por decisiones?
2. ¿Qué pasó cuando las ciencias de la administración insistieron en buscar la solución óptima?
3. Compará las dos escuelas en las seis dimensiones de la tabla.
4. Explicá la diferencia entre un modelo descriptivo y uno explorativo.
5. ¿Qué significa "en el soporte a la decisión usamos los modelos para entender la realidad"? ¿Qué consecuencia práctica tiene para cuándo empezar a modelar?
6. ¿Por qué en el soporte a la decisión se acepta que dos alternativas no puedan compararse?
7. ¿Por qué la distinción entre selección, triaje y ordenamiento solo tiene sentido para una de las dos escuelas?
8. ¿Cuál es la ventaja del juicio humano y cuál la del modelo computacional? ¿Por qué ninguno alcanza solo?
9. ¿Qué efecto secundario tiene incorporar el juicio humano al proceso?
10. Nombrá las tres dimensiones del esquema de clasificación.
11. Diferenciá una contribución orientada al proceso de una orientada al producto.
12. Diferenciá investigación descriptiva de prescriptiva.
13. ¿Por qué no pudieron seleccionar los trabajos por palabras clave?
14. ¿Qué dice la observación 4 sobre los factores no técnicos? ¿Con qué otros capítulos se conecta?
15. ¿Qué técnica domina entre las usadas para resolver problemas de decisión?
16. ¿Por qué la falta de investigación descriptiva es un problema? ¿Qué consecuencia tiene sobre la brecha entre investigadores y profesionales?
17. En la observación 7, ¿por qué el mismo problema se trata como estructurado, semi-estructurado y no estructurado según el equipo? ¿Qué dice eso sobre la clase de un problema?
18. ¿Por qué no tiene sentido buscar soluciones óptimas en IR?
19. ¿Por qué ninguna técnica formalizada aislada da resultados significativos?
20. ¿Cuál es la meta declarada del soporte a la decisión?

---

**FIN DEL CAPÍTULO 12 — PARTE 2**

**FIN DEL CAPÍTULO 12**

*Sigue el capítulo 13: ingeniería de requisitos dirigida por el mercado, en 2 partes.*
