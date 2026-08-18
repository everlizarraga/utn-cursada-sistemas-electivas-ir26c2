# Lectura en español — Cap. 4 · Parte 1: Aspectos y técnicas de priorización

> **Origen.** Capítulo 4, secciones 4.1 a 4.4, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Patrik Berander** (Instituto Tecnológico de Blekinge, Suecia) y **Anneliese Andrews** (Universidad Estatal de Washington).
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.

---

## Aviso sobre este capítulo

La priorización no figura en ninguna clase de tu cronograma. Pero es **una de las cinco prácticas esenciales de la gestión de requisitos** que enumeró el capítulo 1, y hay tres cosas acá que sí te van a servir:

- La técnica de **asignación numérica** está recomendada por el **IEEE 830** —que es contenido de la unidad 7 de tu programa— y viene con una advertencia sobre cómo nombrar las categorías que se cruza directo con el vocabulario de calidad de la cátedra.
- El problema de **mezclar niveles de abstracción** al priorizar, que rima con la regla del café con leche.
- Y en la Parte 2, una **comparación entre requisitos funcionales y no funcionales** en cuatro dimensiones, que es de lo mejor que hay para las clases 06 y 07.

El resto es planificación de producto y decisión gerencial. Interesante, no evaluable.

---

## 1. Introducción 🟡

Los autores arrancan con una analogía cotidiana. Todos los días tomamos decisiones —comprar un reproductor de DVD, comida, un teléfono— y muchas veces ni siquiera somos conscientes de estar tomándolas. Normalmente no tenemos más que un par de opciones a considerar: qué marca de mostaza, o si tomar este colectivo o el que viene. **Y aun con un par de opciones, las decisiones pueden ser difíciles. Con decenas, cientos o miles de alternativas, decidir se vuelve muchísimo más difícil.**

Una de las claves para decidir bien es **priorizar entre las alternativas**. Y no suele ser obvio cuál opción es mejor, **porque hay que tener en cuenta varios aspectos a la vez**.

El ejemplo que dan es bueno: al comprar un auto, es relativamente fácil elegir **basándose solo en la velocidad** — alcanza con ver cuál es el más rápido. Cuando entran en juego múltiples aspectos —precio, seguridad, confort, capacidad de carga— **la elección se vuelve mucho más difícil**.

En el desarrollo de software hay que hacer compromisos parecidos:

> **La funcionalidad que es más importante para los clientes puede no ser tan importante cuando se factorizan otros aspectos, como el precio.** Hay que desarrollar la funcionalidad que es más deseada por los clientes, y a la vez la menos riesgosa, la menos costosa, y así siguiendo.

---

## 2. Qué es la priorización de requisitos 🔴

### El problema de fondo

La calidad de un producto de software se determina, muchas veces, por **su capacidad de satisfacer las necesidades de los clientes y usuarios**. Por eso, elicitar y especificar los requisitos correctos, y planificar versiones adecuadas con la funcionalidad correcta, es un paso mayor hacia el éxito.

Y una frase que conviene retener:

> **Si se implementan los requisitos equivocados y los usuarios se resisten a usar el producto, no importa cuán sólido sea ese producto ni con cuánta minuciosidad haya sido probado.**

El hecho estructural del que parte todo:

> **La mayoría de los proyectos de software tiene más requisitos candidatos de los que pueden realizarse dentro de las restricciones de tiempo y costo.**

La priorización ayuda a identificar los requisitos más valiosos de ese conjunto, **distinguiendo los pocos críticos de los muchos triviales**.

### Para qué sirve priorizar 🟡

El proceso de priorizar da soporte a estas actividades:

- que los interesados **decidan cuáles son los requisitos centrales** del sistema;
- **planificar y seleccionar un conjunto ordenado y óptimo** de requisitos para implementar en versiones sucesivas;
- **compensar el alcance deseado del proyecto** contra restricciones a veces contradictorias: cronograma, presupuesto, recursos, tiempo de salida al mercado y calidad;
- **balancear el beneficio de negocio** de cada requisito **contra su costo**;
- balancear las implicancias de los requisitos **sobre la arquitectura del software** y sobre la evolución futura del producto, y su costo asociado;
- **seleccionar solo un subconjunto** de los requisitos y aun así producir un sistema que satisfaga al cliente;
- **estimar la satisfacción esperada** del cliente;
- **obtener ventaja técnica** y optimizar la oportunidad de mercado;
- **minimizar el retrabajo y los desvíos de cronograma** (estabilidad del plan);
- **manejar requisitos contradictorios**, enfocar el proceso de negociación y resolver desacuerdos entre interesados;
- **establecer la importancia relativa** de cada requisito, para dar el mayor valor al menor costo.

Es un **proceso estratégico**, porque estas decisiones manejan los gastos de desarrollo y los ingresos del producto, además de marcar la diferencia entre ganar o perder mercado. El resultado puede formar la base de los planes de producto y de marketing, y ser fuerza motriz durante la planificación del proyecto.

El desafío, resumido por Ruhe y otros: seleccionar **los requisitos "correctos"** de un superconjunto de candidatos, de modo que se cumplan todos los intereses clave, las restricciones técnicas y las preferencias de los interesados críticos, **y se maximice el valor de negocio global** del producto.

### Por qué conviene acertar temprano 🔴

Es posible rectificar decisiones incorrectas más adelante, vía gestión de cambios. **Pero puede salir muy caro**, porque corregir problemas tarde en el proceso de desarrollo es significativamente más costoso.

Y acá aparece una de las citas más famosas de la ingeniería de software, de **Frederick P. Brooks**:

> **La parte más difícil de construir un sistema de software es decidir precisamente qué construir. Ninguna otra parte del trabajo lisia tanto al sistema resultante si se hace mal. Ninguna otra parte es más difícil de rectificar después.**

De ahí la conclusión: **la manera más costo-efectiva de desarrollar software es encontrar el conjunto óptimo de requisitos temprano** y después desarrollar según ese conjunto. Y para lograrlo hay que priorizar.

### Un beneficio lateral que vale la pena 🔴

Además de lo obvio, priorizar tiene otro beneficio:

> **Es posible encontrar defectos en los requisitos** —requisitos mal juzgados, incorrectos y **ambiguos**— porque al priorizar se los analiza **desde una perspectiva distinta** de la que se toma durante las revisiones de requisitos.

> ⚠️ **Cruce con la cátedra.** Este es un argumento útil: priorizar funciona como **un mecanismo de detección de ambigüedad**. Cuando tenés que decidir si un requisito vale más que otro, te obliga a entender qué dice exactamente — y ahí saltan los que no dicen nada preciso. Es un control de calidad que llega por la puerta de atrás.

### Qué tan difícil es priorizar 🟢

Los autores señalan que no hay acuerdo:

- **Algunos autores la consideran fácil.**
- **Otros de dificultad media.**
- **Otros la consideran una de las actividades más complejas del proceso de requisitos**, afirmando que pocas empresas de software tienen métodos efectivos y sistemáticos para priorizar.

Lo que sí comparten todas las fuentes: **es una actividad fundamental para el éxito del proyecto**. Y sin embargo, agregan, **algunos libros de texto sobre ingeniería de requisitos no la discuten en ninguna medida real**.

### Cuándo se prioriza 🟡

No hay un proceso de requisitos "correcto", y la manera de manejar requisitos difiere mucho entre dominios y empresas. Además, **los requisitos son típicamente más vagos al principio y se vuelven más explícitos a medida que crece el entendimiento del producto**.

Esas dos circunstancias implican algo importante:

> **No hay una fase específica donde se prioriza. Se prioriza a lo largo de todo el proceso de desarrollo.** Es un proceso iterativo, que puede realizarse a distintos niveles de abstracción y con distinta información según la fase del ciclo de vida.

### Las dos grandes familias 🟡

Las técnicas de priorización se dividen a grandes rasgos en dos categorías:

| | **Métodos** | **Enfoques de negociación** |
|---|---|---|
| **Cómo funcionan** | Asignan **valores cuantitativos** a distintos aspectos de los requisitos | Dan prioridades **alcanzando acuerdo entre los interesados** |
| **En qué se basan** | Medidas cuantitativas | **Medidas subjetivas** |
| **Cuándo se usan** | Facilitan **agregar distintas variables de decisión** en una evaluación global, y llevan a decisiones más rápidas | Cuando los análisis son **contextuales** y las variables de decisión **están fuertemente interrelacionadas** |

### La advertencia social 🔴

Y antes de entrar en las técnicas, los autores meten un párrafo que conviene no saltear:

> **Hay que ser consciente de la naturaleza social de la priorización. Priorizar requisitos es mucho más que simplemente preguntarles a los interesados por sus prioridades.**
>
> Los interesados **cumplen roles** y deberían actuar según los objetivos de ese rol, **pero también son individuos con personalidades y agendas personales**. Además hay que tener en cuenta muchas cuestiones organizacionales, como el poder. **Ignorar estas cuestiones puede elevar el nivel de riesgo de un proyecto.**

*(El capítulo se enfoca principalmente en los métodos cuantitativos.)*

---

## 3. Los aspectos de la priorización 🟡

> **Un aspecto** es una **propiedad o atributo de un proyecto y de sus requisitos** que puede usarse para priorizar.

Los aspectos comunes son: **importancia, penalidad, costo, tiempo y riesgo**.

Cuando se prioriza por **un solo aspecto**, es fácil decidir cuál es más deseable —como con la velocidad del auto. Cuando entran otros, la cosa cambia:

> **Los clientes pueden cambiar de opinión, y requisitos de alta prioridad pueden resultar menos importantes si son muy caros de satisfacer.**

Además, **los aspectos interactúan entre sí**: cambios en uno pueden impactar en otro. Por eso es esencial conocer los efectos que esos conflictos pueden tener, y **es vital no considerar solamente la importancia** al priorizar.

Los aspectos son evaluados usualmente por los interesados del proyecto: gerentes, usuarios, desarrolladores.

### 3.1 Importancia

Los interesados priorizan **cuáles requisitos son más importantes** para el sistema.

Pero acá hay una trampa: **la importancia puede ser un concepto extremadamente multifacético**, porque depende mucho de la perspectiva del interesado. Puede significar:

- urgencia de implementación,
- importancia del requisito **para la arquitectura del producto**,
- importancia **estratégica para la empresa**,
- entre otras.

**Conclusión operativa:** es esencial **especificar qué tipo de importancia** deben priorizar los interesados en cada caso.

> ⚠️ **Cruce con la cátedra.** "Importante" sin calificar es una palabra ambigua — el mismo vicio que el léxico de calidad ataca. Dos personas priorizando "importancia" sin haber acordado qué significa están priorizando dos cosas distintas y no lo saben.

### 3.2 Penalidad 🔴

Es posible evaluar **la penalidad que se introduce si un requisito NO se cumple**.

Y la observación clave:

> **La penalidad no es simplemente lo opuesto de la importancia.**

Los dos ejemplos que dan lo dejan claro:

- **No cumplir con un estándar** puede acarrear una **penalidad alta** aunque sea de **baja importancia** para el cliente — o sea, el cliente no se entusiasma si el requisito se cumple, pero se arma un problema si no.
- Lo mismo pasa con los **requisitos implícitos que los usuarios dan por sentados**, y cuya ausencia podría **volver al producto inadecuado para el mercado**.

> Es una distinción fina y muy útil. Hay cosas que no suman puntos si están, pero restan muchísimos si faltan. Priorizar solo por importancia las deja afuera todas.

### 3.3 Costo

El costo de implementación lo estima usualmente **la organización que desarrolla**. Las medidas que lo influyen incluyen:

- la **complejidad** del requisito,
- la capacidad de **reutilizar código existente**,
- la cantidad de **pruebas y documentación** necesarias.

**Se expresa a menudo en horas de personal (esfuerzo)**, porque el costo principal del desarrollo de software suele estar primariamente relacionado con la cantidad de horas dedicadas.

### 3.4 Tiempo

Aunque el costo se relaciona con las horas de personal, **el tiempo** —el plazo real hasta la entrega— está influido por muchos otros factores:

- el **grado de paralelismo** en el desarrollo,
- las **necesidades de capacitación**,
- la necesidad de **desarrollar infraestructura de soporte**,
- **completar estándares de la industria**.

> Costo y tiempo no son la misma cosa medida en unidades distintas. Nueve mujeres no hacen un bebé en un mes: el esfuerzo puede repartirse, el plazo no siempre.

### 3.5 Riesgo

Todo proyecto conlleva algún grado de riesgo. En gestión de proyectos, la gestión de riesgos se usa para lidiar con riesgos **internos** (técnicos y de mercado) y **externos** (regulaciones, proveedores).

**Hay que considerar dos variables** al determinar el nivel de riesgo de un ítem o actividad: **la probabilidad y el impacto**.

La gestión de riesgos también sirve al planificar requisitos en productos y versiones, **identificando riesgos que probablemente causen dificultades durante el desarrollo**: riesgos de rendimiento, de proceso, de cronograma. Con la probabilidad y el impacto estimados de cada requisito, se puede calcular el nivel de riesgo del proyecto.

### 3.6 Volatilidad 🟡

La volatilidad de los requisitos **se considera un factor de riesgo** y a veces se maneja como parte del aspecto riesgo. Otros piensan que **debería analizarse por separado** y tenerse en cuenta como aspecto propio en la priorización.

**Las razones de la volatilidad varían:**

- cambia el mercado,
- cambian los requisitos del negocio,
- ocurren cambios legislativos,
- cambian los usuarios,
- **o los requisitos se vuelven más claros durante el ciclo de vida.**

Independientemente de la razón, los requisitos volátiles **afectan la estabilidad y la planificación** del proyecto, y **presumiblemente aumentan los costos**, porque los cambios durante el desarrollo encarecen el proyecto.

Y un costo indirecto que se pasa por alto: **el proyecto puede encarecerse porque los desarrolladores tienen que elegir una arquitectura apta para el cambio**, si se sabe de antemano que la volatilidad va a ser un problema.

### 3.7 Otros aspectos

La lista anterior no es exhaustiva. Otros ejemplos: **beneficio financiero, beneficio estratégico, competidores, competencia y recursos disponibles, tema de la versión, capacidad de venta**.

La recomendación de los autores para una empresa: que **los interesados desarrollen su propia lista de aspectos importantes** para usar en la toma de decisiones. Y una condición:

> **Es importante que los interesados tengan la misma interpretación de los aspectos, así como de los requisitos.** Hay estudios que muestran que **es difícil interpretar los resultados si no hay directrices sobre el significado verdadero de cada aspecto.**

### 3.8 Combinar aspectos 🟡

En la práctica es importante considerar **múltiples aspectos** antes de decidir si un requisito se implementa ya, después, o nunca. Ejemplos de combinaciones:

| Enfoque | Qué combina |
|---|---|
| **Costo-Valor** | Prioriza **valor (importancia) y costo**, para implementar los requisitos que dan más valor por el dinero |
| **Planning Game** (de Programación Extrema) | Prioriza **importancia, esfuerzo (costo) y riesgos** |
| **Enfoque de Wiegers** | Divide **el valor relativo (importancia) por el costo relativo y el riesgo relativo**, para determinar los requisitos con el balance más favorable entre valor, costo y riesgo. Permite además **pesos distintos para aspectos distintos**, para favorecer al más importante en cada situación |

También se sugiere usar **importancia y estabilidad (volatilidad)** como aspectos, y otros agregan que **las dependencias también deben considerarse**.

---

## 4. Las técnicas de priorización 🔴

### El propósito y las escalas

> **El propósito de toda priorización es asignar valores a objetos distintos, de modo que se pueda establecer un orden relativo entre los objetos del conjunto.** En nuestro caso, los objetos son los requisitos.

La priorización puede hacerse con distintas escalas de medición, y la potencia de la escala determina qué se puede calcular después:

| Escala | Qué permite | Potencia |
|---|---|---|
| **Ordinal** | Ver **cuáles requisitos son más importantes que otros**, pero **no cuánto más** | La menos potente |
| **De razón** | **Cuantificar cuánto más importante** es un requisito que otro. Suele expresarse de 0 a 100 % | Más potente |
| **Absoluta** | Situaciones donde se puede asignar **un número absoluto** (ej.: cantidad de horas) | La más potente |

> **A mayor nivel de medición, más sofisticadas son las evaluaciones y los cálculos posibles.**

*(En los ejemplos que siguen se usa la **importancia** como aspecto a priorizar, aunque cualquier otro aspecto podría evaluarse con cada técnica.)*

---

### 4.1 Proceso Analítico Jerárquico (AHP) 🟡

Es un **método sistemático de toma de decisiones** adaptado a la priorización de requisitos de software.

**Cómo funciona:** se comparan **todos los pares posibles** de requisitos clasificados jerárquicamente, para determinar cuál tiene mayor prioridad **y en qué medida** — usualmente en una escala de **uno a nueve**, donde uno representa igual importancia y nueve representa absolutamente más importante.

**El problema de escala:** el número total de comparaciones es **n × (n−1)/2** en cada nivel jerárquico, lo que produce un **aumento dramático** a medida que crece la cantidad de requisitos.

```
   10 requisitos  →   45 comparaciones
   20 requisitos  →  190 comparaciones
   50 requisitos  → 1225 comparaciones
```

**Los estudios muestran que AHP no es adecuado para grandes cantidades de requisitos.** Se intentó reducir el número de comparaciones, y algunas variantes lo redujeron **hasta en un 75 %**.

**Su ventaja distintiva:** en su forma original, **la redundancia de las comparaciones por pares permite un control de consistencia**, donde se pueden identificar errores de juicio y calcular un **índice de consistencia**.

**Pero hay un compromiso:** al reducir el número de comparaciones **también se reduce la cantidad de comparaciones redundantes**, y por lo tanto **la capacidad de identificar juicios inconsistentes**.

*(Con las otras técnicas no hace falta índice de consistencia, porque todos los requisitos se comparan directamente entre sí y la consistencia está siempre asegurada.)*

**Un problema humano:** algunos estudios indican que **las personas que priorizan con AHP tienden a desconfiar de los resultados**, porque se pierde el control al comparar solo de a pares.

**Resultado:** una lista ponderada en **escala de razón**.

---

### 4.2 Votación acumulativa: la prueba de los 100 dólares 🟡

Una técnica **muy directa**: a los interesados se les dan **100 unidades imaginarias** —dinero, horas, lo que sea— **para distribuir entre los requisitos**.

**Resultado:** escala de razón.

**Problema 1 — demasiados requisitos.** Con 25 requisitos hay, en promedio, **cuatro puntos por requisito**. Un estudio que enfrentó este problema con 17 grupos de requisitos usó **una suma ficticia de $100.000** para tener más libertad. Los participantes reaccionaron bien, lo que indica que **se pueden usar montos distintos de 100**: 1.000, 10.000 o 1.000.000.

**Problema 2 — errores de cálculo.** Especialmente con muchos requisitos, quien prioriza puede equivocarse y **los puntos no suman 100**. Se previene con una herramienta que lleve la cuenta.

**Problema 3 — el juego estratégico.** Este es el más interesante:

> **La priorización debería hacerse una sola vez sobre el mismo conjunto de requisitos**, porque los interesados **pueden sesgar su evaluación la segunda vez** si no consiguieron que alguno de sus favoritos quedara arriba. En esa situación podrían **poner todo su dinero en un solo requisito**, lo que influiría el resultado pesadamente.
>
> Del mismo modo, **algunos interesados astutos pueden poner todo su dinero en un requisito favorito que los demás no priorizan alto** —el ejemplo del capítulo es la compatibilidad con Mac— **mientras no le dan dinero a requisitos que van a recibir mucho de todas formas**, como el tiempo de respuesta.

**La solución posible:** limitar el monto que se puede gastar en un requisito individual. **El riesgo de esa solución:** que los interesados queden forzados a **no priorizar según sus prioridades reales**.

---

### 4.3 Asignación numérica (agrupamiento) 🔴

> **Es la técnica de priorización más común**, y está sugerida tanto en el **RFC 2119** como en el **IEEE Std. 830-1998**.

**Cómo funciona:** se agrupan los requisitos en **grupos de prioridad** distintos. La cantidad de grupos puede variar, pero **en la práctica tres grupos es muy común**.

**La regla de oro de esta técnica** —y es la parte que más te sirve:

> **Es importante que cada grupo represente algo con lo que los interesados puedan relacionarse** — por ejemplo: **crítico, estándar, opcional** — para lograr una clasificación confiable.
>
> **Usar términos relativos como alto, medio y bajo va a confundir a los interesados.** Esto parece ser especialmente importante cuando hay interesados con visiones distintas de qué significan alto, medio y bajo. **Una definición clara de qué significa realmente cada grupo minimiza esos problemas.**

> ⚠️ **Cruce con la cátedra.** Esto es el léxico de calidad aplicado a la priorización. "Alto / medio / bajo" es ambiguo: no hay nada en las palabras que le diga a nadie dónde va la frontera, y cada interesado la pone donde quiere. "Crítico / estándar / opcional" **nombra el efecto real**, y por eso dos personas distintas clasifican parecido. Es exactamente la misma lógica por la que un requisito debe ser verificable: **si no hay un referente compartido, no hay medición posible**.

**El otro problema, y es muy citado:**

> **Los interesados tienden a pensar que todo es crítico.** Si los clientes priorizan por sí mismos usando tres grupos —crítico, estándar, opcional— lo más probable es que consideren **el 85 % de los requisitos como críticos, el 10 % como estándar y el 5 % como opcionales.**

**Una idea para evitarlo:** poner **restricciones a la cantidad de requisitos permitidos en cada grupo** — por ejemplo, no menos del 25 % en cada uno.

**El problema de esa idea:** **la utilidad de las prioridades disminuye**, porque los interesados quedan forzados a dividir requisitos en ciertos grupos. *(Los autores aclaran que no existe evidencia empírica sobre si esas restricciones dan buenos o malos resultados.)*

**Resultado:** escala **ordinal**. Y una limitación estructural: **los requisitos de un mismo grupo tienen la misma prioridad**, lo que significa que **ningún requisito obtiene una prioridad única**.

---

### 4.4 Ordenamiento (ranking) 🟡

Como la asignación numérica, se basa en una **escala ordinal** — pero los requisitos **se ordenan sin empates**. El más importante recibe el puesto 1 y el menos importante el puesto *n*.

**Qué gana respecto de la asignación numérica:** cada requisito tiene **un puesto único**.

**Qué sigue sin poder:** **no es posible ver la diferencia relativa** entre los ítems ordenados, como sí permiten AHP o los 100 dólares.

La lista puede obtenerse de varias maneras, por ejemplo usando algoritmos de **ordenamiento burbuja** o **árbol binario de búsqueda**.

**Su límite práctico:** independientemente del algoritmo, **el ordenamiento parece más adecuado para un solo interesado**, porque puede ser difícil alinear las visiones de varios. Se pueden combinar tomando **la prioridad media** de cada requisito, pero **eso puede producir empates** — justo lo que el método quería evitar.

---

### 4.5 Los diez requisitos principales 🟡

Los interesados eligen **sus diez requisitos principales** de un conjunto más grande, **sin asignar un orden interno** entre ellos.

**Por qué eso lo hace adecuado para múltiples interesados de igual importancia:** la razón de no priorizar más allá es que **podría crear conflicto innecesario** cuando algunos interesados consiguen apoyo para su primera prioridad y otros solo para su tercera.

**El problema que igual aparece:** el conflicto puede surgir de todos modos si, por ejemplo, un cliente mete tres de sus diez requisitos en el producto y otro mete seis.

**La regla crítica de esta técnica:**

> **Es importante NO tomar simplemente un promedio entre todos los interesados**, porque eso puede llevar a que **algunos interesados no obtengan ninguno de sus requisitos principales**. En cambio, **es crucial que se satisfagan algunos requisitos esenciales de cada interesado**.

Eso puede derivar, admiten los autores, en **una situación que deja a todos los clientes insatisfechos en vez de satisfacer completamente a unos pocos**. Balancear eso es el desafío principal de la técnica.

---

### 4.6 Cuál técnica elegir 🔴

| Técnica | Escala | Granularidad | Sofisticación |
|---|---|---|---|
| **AHP** | De razón | Fina | **Muy compleja** |
| **Prueba de los 100 dólares** | De razón | Fina | Compleja |
| **Ordenamiento** | Ordinal | Media | Fácil |
| **Asignación numérica** | Ordinal | Gruesa | Muy fácil |
| **Diez principales** | — | Extremadamente gruesa | Extremadamente fácil |

**El consejo general de los autores:**

> **Usar la técnica de priorización más simple que sea apropiada**, y recurrir a las más sofisticadas **solo cuando haga falta un análisis más sensible** para resolver desacuerdos o para sostener las decisiones más críticas.

Como las técnicas sofisticadas generalmente consumen más tiempo, **la técnica más simple posible asegura decisiones costo-efectivas**. El compromiso es decidir exactamente **cuán "rápido y sucio" puede ser el enfoque sin que la calidad de las decisiones sufra**.

*(Existen herramientas comerciales que facilitan las técnicas sofisticadas como AHP, y también es posible construir herramientas caseras simples —en planillas de cálculo, por ejemplo.)*

---

### 4.7 Combinar técnicas 🟡

Se pueden combinar técnicas para hacer la priorización más fácil o más eficiente. Dos ejemplos conocidos:

**Planning Game (de Programación Extrema).** Combina **asignación numérica y ordenamiento**: primero divide los requisitos en grupos de prioridad, **y después ordena los requisitos dentro de cada grupo**.

**Triaje de requisitos.** Traza un paralelo con la atención médica en hospitales. El personal médico divide a las víctimas en tres categorías:

```
   1. los que van a morir sean tratados o no
   2. los que van a recuperarse sean tratados o no
   3. aquellos para quienes el tratamiento médico
      SÍ puede hacer una diferencia significativa
```

Llevado a requisitos:

```
   1. requisitos que DEBEN estar en el producto
      (ej.: requisitos de plataforma)
   2. requisitos que el producto claramente NO necesita
      satisfacer (ej.: muy opcionales)
   3. requisitos que NECESITAN MÁS ATENCIÓN
```

Los requisitos se asignan a uno de los tres grupos —asignación numérica— y **solo los del tercer grupo se priorizan con alguna de las otras técnicas** (AHP, ordenamiento, 100 puntos).

> **La ventaja: no hace falta priorizar todos los requisitos con una técnica sofisticada, lo que reduce el esfuerzo.** Es la aplicación práctica del consejo de usar la técnica más simple posible — pero por partes, gastando el método caro solo donde rinde.

---

## Mapa de la Parte 1

```
   POR QUÉ PRIORIZAR
   siempre hay más requisitos candidatos que
   tiempo y dinero → separar los pocos críticos
   de los muchos triviales
   (Brooks: decidir qué construir es lo más difícil)

   ─────────────────────────────────────────────

   LOS ASPECTOS (por qué criterio se prioriza)
   IMPORTANCIA  ─► ¡especificar de qué tipo!
   PENALIDAD    ─► NO es lo opuesto de importancia
   COSTO        ─► horas de esfuerzo
   TIEMPO       ─► plazo, ≠ costo
   RIESGO       ─► probabilidad × impacto
   VOLATILIDAD  ─► encarece incluso la arquitectura

   ─────────────────────────────────────────────

   LAS TÉCNICAS (cómo se prioriza)
                    escala      granularidad   esfuerzo
   AHP              razón       fina           muy alto
   100 dólares      razón       fina           alto
   Ordenamiento     ordinal     media          bajo
   Asignación num.  ordinal     gruesa         muy bajo
   Diez principales —           muy gruesa     mínimo

   REGLA: la más simple que sirva.
   COMBINACIONES: Planning Game · Triaje
```

---

## Preguntas para chequear que quedó

1. ¿Por qué hace falta priorizar? ¿Cuál es el hecho estructural del que parte todo el capítulo?
2. ¿Qué dice Brooks sobre decidir qué construir, y por qué esa cita justifica priorizar temprano?
3. ¿Por qué priorizar ayuda a detectar defectos y ambigüedades en los requisitos?
4. ¿En qué fase del desarrollo se prioriza? Justificá.
5. Diferenciá métodos de enfoques de negociación.
6. ¿Por qué los autores advierten sobre la "naturaleza social" de la priorización?
7. ¿Por qué "importancia" a secas es un aspecto problemático? ¿Qué hay que hacer al respecto?
8. Explicá por qué la penalidad no es lo opuesto de la importancia. Dé un ejemplo propio.
9. ¿Por qué costo y tiempo son aspectos distintos y no el mismo medido diferente?
10. ¿Qué dos variables determinan el nivel de riesgo?
11. Nombrá tres causas de volatilidad de requisitos y un costo indirecto que genera.
12. ¿Qué tres escalas de medición existen y qué permite cada una?
13. ¿Cuál es la ventaja distintiva de AHP, y qué se pierde al reducir el número de comparaciones?
14. Con 20 requisitos, ¿cuántas comparaciones exige AHP?
15. Describí el juego estratégico posible en la prueba de los 100 dólares. ¿Cuál es la solución y cuál su riesgo?
16. ¿Por qué "crítico / estándar / opcional" funciona mejor que "alto / medio / bajo"?
17. ¿Qué porcentaje de requisitos clasifican los clientes como críticos cuando priorizan solos? ¿Qué se puede hacer y qué se pierde al hacerlo?
18. ¿Qué gana y qué sigue sin poder el ordenamiento respecto de la asignación numérica?
19. En la técnica de los diez principales, ¿por qué no hay que promediar entre interesados?
20. Explicá el triaje de requisitos y por qué reduce el esfuerzo total.

---

**FIN DEL CAPÍTULO 4 — PARTE 1**

*Sigue en la Parte 2: qué cambia según haya un cliente, varios clientes conocidos o un mercado masivo; el problema de los niveles de abstracción; la repriorización; las diferencias entre requisitos funcionales y no funcionales; un ejemplo completo trabajado con 15 requisitos; y las preguntas abiertas del área.*
