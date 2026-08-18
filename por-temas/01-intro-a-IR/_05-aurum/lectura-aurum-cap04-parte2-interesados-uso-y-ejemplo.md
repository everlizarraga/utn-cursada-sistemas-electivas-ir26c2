# Lectura en español — Cap. 4 · Parte 2: Interesados, uso práctico y ejemplo trabajado

> **Origen.** Capítulo 4, secciones 4.5 a 4.9, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Patrik Berander y Anneliese Andrews**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1.** Se asumen conocidos los aspectos (importancia, penalidad, costo, tiempo, riesgo, volatilidad) y las cinco técnicas.

---

## 1. Los interesados en el proceso de priorización 🟡

### Desarrollo a medida vs. dirigido por el mercado

En un proyecto **a medida** hay que tener en cuenta **uno o unos pocos interesados**. En desarrollo **dirigido por el mercado**, **todo el mundo puede ser cliente potencial**. Esta tabla resume las diferencias:

| Faceta | **A medida** | **Dirigido por el mercado** |
|---|---|---|
| **Interesado principal** | La organización **cliente** | La organización **que desarrolla** |
| **Usuarios** | Conocidos o identificables | **Desconocidos**; pueden no existir hasta que el producto esté en el mercado |
| **Distancia a los usuarios** | Usualmente **pequeña** | Usualmente **grande** |
| **Cómo se conciben los requisitos** | **Elicitados, analizados, validados** | **Inventados**, por tirón del mercado o empuje de la tecnología |
| **Ciclo de vida** | Una versión, después mantenimiento | **Varias versiones**, mientras haya demanda de mercado |
| **Problemas específicos de IR** | Elicitación, modelado, validación, resolución de conflictos | **Flujo constante de requisitos**, priorización, estimación de costos, planificación de versiones |
| **Objetivo primario** | **Cumplir la especificación** | **Tiempo de salida al mercado** |
| **Medida del éxito** | Satisfacción, aceptación | **Ventas, cuota de mercado** |

Los autores aclaran que son **los dos extremos**: un caso real probablemente cae en algún punto intermedio. Por ejemplo, una empresa puede entregar para un mercado, pero un mercado limitado a un número reducido de clientes — los sistemas de telecomunicaciones solo los compran las operadoras telefónicas.

La discusión que sigue se organiza en **tres escenarios generales**.

### 1.1 Un solo cliente 🟡

Solo hay que considerar las prioridades de un cliente. Muchos de los procesos de desarrollo actuales están basados en un cliente y **asumen que ese cliente está disponible durante todo el proyecto** — Programación Extrema tiene el "cliente en el sitio" como una de sus prácticas centrales.

**Pero hay un problema que hay que tener presente:**

> **El cliente y los usuarios finales no siempre son la misma persona.** En ese caso, **quien prioriza y quienes van a usar el sistema pueden no tener las mismas prioridades.**

Esas situaciones son indeseables, porque pueden resultar en **un uso reducido del producto**. En ese caso, sería mejor **involucrar a los usuarios finales en la priorización**, porque son ellos los que saben lo que necesitan.

El ejemplo que dan es filoso: **si el cliente es el empleador y el usuario es un empleado de la empresa que compra el producto, puede haber conflicto.** Es fácil imaginar funcionalidades que son deseables para un empleador **pero no para un empleado**.

> ⚠️ **Cruce con la cátedra.** Este es el mismo eje cliente / usuario que trabajaste en el entregable de la clase 01, visto ahora en su consecuencia más incómoda: **no solo son roles distintos, pueden tener intereses opuestos.** Un sistema de control de productividad es deseable para quien lo paga y no para quien lo usa. Confundir los dos roles en un TP no es solo impreciso — te hace perder de vista un conflicto real del caso.

### 1.2 Varios clientes conocidos 🟡

Con varios clientes la priorización se vuelve más difícil, porque **pueden tener puntos de vista y preferencias en conflicto**. Aparece el desafío de **unificar esas visiones distintas**.

> **El objetivo último en estas situaciones es crear condiciones de ganar-ganar y hacer de cada interesado un "ganador".** Si se descuida una perspectiva, **el sistema puede ser visto como un fracaso por uno o varios de los interesados.**

De ahí que sea de **enorme importancia que todos los interesados estén involucrados**, porque el éxito del producto se decide en última instancia en este paso.

### 1.3 Mercado masivo 🟢

Cuando se desarrolla para un mercado masivo, **no es posible conseguir que todos los clientes prioricen**. Las fuentes de información disponibles:

| Fuente | Ejemplos |
|---|---|
| **Registros internos** | Envíos, registros de ventas |
| **Inteligencia de marketing** | Información de la fuerza de ventas, de los científicos |
| **Inteligencia de la competencia** | Información sobre estrategias de competidores, comparación de sus productos |
| **Investigación de mercado** | Encuestas, grupos focales |

**Condición al hacer investigación de mercado:** la muestra debe ser **representativa del segmento de mercado buscado** — un grupo de consumidores con necesidades similares. Si se desarrollan productos para empresas grandes, **no tiene sentido involucrar empresas chicas** en los grupos focales o encuestas. Por eso es muy importante **decidir a qué segmentos apunta el producto antes de priorizar**.

**Un uso valioso del resultado:** priorizar para un producto masivo permite analizar **qué requisitos son de alta prioridad para todos los segmentos**. Con esa información se puede identificar **qué partes del sistema deberían ser comunes a todos los segmentos y cuáles desarrollarse específicamente para alguno** — algo valioso al desarrollar líneas de producto de software.

#### Las "personas" 🟡

Una manera de lidiar con que los usuarios posibles no sean conocidos ni accesibles es usar el concepto de **personas** (*personas*), que se originó en marketing y se usa en diseño de sistemas.

> Las personas son **personajes ficticios que representan segmentos de mercado**. Tienen **nombre, ocupación, posesiones, edad, género, situación socioeconómica**. Están basadas e inspiradas en gente real que supuestamente va a usar el producto. Esa información se reúne a partir de **etnografías, investigación de mercado, estudios de usabilidad, entrevistas y observaciones**.

**Para qué sirven:** ayudan a la organización a enfocar la atención en **para quién está diseñado el sistema y para quién no**, y a entender a esas personas objetivo. Además **aumentan el compromiso y la sensación de realidad**, al proveer usuarios ficticios del sistema.

**Cómo se usan al decidir:** haciendo preguntas del tipo *¿por qué estamos construyendo esta funcionalidad?* y *¿por qué la estamos construyendo así?*. Al tener usuarios explícitos aunque ficticios, la organización **puede entender qué elecciones harían esas personas en distintas situaciones**.

### 1.4 Qué roles deben estar representados 🔴

Como los requisitos pueden priorizarse desde aspectos distintos, **también hay que involucrar roles distintos** para obtener las visiones correctas — los jefes de producto priorizan la importancia estratégica, los jefes de proyecto priorizan los riesgos.

> **Al menos tres perspectivas deberían estar siempre representadas: clientes, desarrolladores y representantes financieros.**

| Perspectiva | Qué información aporta que las otras no pueden |
|---|---|
| **Clientes** | Les importa **el valor para el usuario y el cliente** |
| **Desarrolladores** | Conocen **las dificultades técnicas** |
| **Representantes financieros** | Conocen y les importan **las restricciones presupuestarias y los riesgos** |

Cada uno provee información vital **que los otros dos pueden descuidar o directamente ser incapaces de producir**. Y desde luego, conviene involucrar además a todas las demás perspectivas con interés en el proyecto.

### 1.5 Compromisos entre interesados 🔴

En proyectos tanto a medida como dirigidos por el mercado puede haber varios interesados con prioridades y expectativas distintas. **Cómo hacer los compromisos entre ellos es un problema que los jefes de producto mencionan comúnmente**, por dos razones:

1. **Uno o pocos interesados muy fuertes** — sus deseos suelen ser difíciles de descuidar. Los autores lo dicen sin vueltas: **cuando el cliente grande dice salten, la empresa salta.**
2. **Los clientes "que chillan" suelen conseguir lo que quieren.** El que hace más ruido gana, y eso no tiene relación con lo que más conviene.

**La solución propuesta: pesar a los interesados de manera estructurada.** Se ajusta la influencia de cada interesado priorizando por distintos aspectos, por ejemplo pesando los segmentos de mercado según:

- ingresos del año pasado,
- ganancia de la última versión,
- tamaño total del segmento de mercado,
- cantidad de clientes potenciales.

**El aspecto de ponderación depende de la estrategia más adecuada a la fase de mercado actual.** Esas prioridades se usan después para pesar a cada interesado en el proceso.

**Un detalle técnico:** la ponderación de los interesados puede hacerse igual que una priorización ordinaria, usando las técnicas de la Parte 1 — **preferentemente las de escala de razón**, porque proveen las distancias de importancia entre interesados, no solo el orden.

> ⚠️ **Cruce con la cátedra.** Esto le da respuesta técnica al problema de "el que grita más gana": **pesar explícitamente a los interesados con un criterio declarado** convierte una decisión política en una decisión trazable. Es el tipo de fundamentación que sostiene un criterio ante una corrección.

---

## 2. Cuestiones prácticas al priorizar 🔴

### 2.1 El nivel de abstracción 🔴

Los requisitos se representan comúnmente a **distintos niveles de abstracción**, lo que causa problemas al priorizar. La razón principal:

> **Los requisitos que están en niveles de abstracción más altos tienden a obtener prioridad más alta** en las comparaciones por pares.

El ejemplo del capítulo es excelente. Al priorizar requisitos de un auto:

```
   ¿Una lucecita en el tablero  vs.  un BAÚL?
   → casi todos eligen el baúl
      (niveles de abstracción distintos:
       la comparación no significa nada)

   ¿Una lucecita en el baúl  vs.  una lucecita en el tablero?
   → ahí sí la del tablero puede tener más prioridad
      (mismo nivel: la comparación informa)
```

**Conclusión:** es realmente importante que **los requisitos no se mezclen en distintos niveles de abstracción** al priorizar.

**Cómo decidir el nivel.** Depende mucho de la cantidad de requisitos y de su complejidad:

- Con **pocos requisitos**, puede ser posible priorizarlos todos **a un nivel de abstracción bajo**.
- Con **muchos requisitos**, conviene **empezar por los de nivel alto** y priorizar después los niveles inferiores **dentro de cada uno**. *(AHP soporta este enfoque de descomposición jerárquica, justamente para reducir el número de comparaciones.)*
- En otros casos puede ser buena idea **priorizar solo los requisitos de alto nivel y dejar que los subordinados hereden la prioridad**. Si se elige esta vía, **es importante que todos los interesados estén al tanto de esa herencia**.

**Agrupar como solución.** Un estudio que enfrentó el problema de tener muchísimos requisitos los **agrupó** para facilitar la tarea, dividiéndolos en un nivel bajo (los requisitos originales) y uno alto (agrupados según relaciones).

Ese enfoque **no solo reduce la cantidad de requisitos a priorizar, sino que además maneja las dependencias**: agrupar según dependencias —qué requisitos deben implementarse juntos— facilita el análisis posterior, porque **los requisitos agrupados dejan de competir entre sí por la prioridad**. Según los resultados del estudio, **formar grupos coherentes fue fácil** y los interesados priorizaron con éxito en ambos niveles.

> ⚠️ **Cruce con la cátedra.** La regla del café con leche vuelve a aparecer, ahora con evidencia empírica de por qué importa. **Comparar cosas de distinto nivel de granularidad no produce información, produce ruido** — el baúl siempre le va a ganar a la lucecita, y eso no te dice nada sobre la lucecita. Arrancar granular y agrupar después es lo que mantiene comparables las comparaciones.

### 2.2 Repriorización 🟡

Al desarrollar productos es probable que **lleguen requisitos nuevos, se borren requisitos, cambien las prioridades de los existentes, o cambien los requisitos mismos**. Por eso el proceso de priorización tiene que poder lidiar con el cambio.

**Y no todas las escalas se re-priorizan igual de fácil:**

| Escala | Dificultad de repriorizar |
|---|---|
| **Ordinal** (ordenamiento, asignación numérica) **y absoluta** (estimar costo) | **Sin mayores problemas**: al requisito nuevo o modificado solo hay que asignarle un valor o una prioridad correcta |
| **De razón** (AHP, 100 dólares) | **Más complejo**: en principio, **todos los requisitos deberían compararse con todos los demás** para establecer las prioridades relativas correctas |

**El atajo posible para las de razón:** comparar los requisitos nuevos o modificados **solo contra ciertos requisitos de referencia**, y estimar así el valor relativo. Con los 100 dólares, por ejemplo, se pueden identificar **los dos requisitos con puntaje inmediatamente superior e inferior**, establecer el valor relativo respecto de esos dos, y normalizar los pesos del conjunto completo.

**El costo del atajo:** el proceso original no se sigue, y **el resultado puede diferir de una repriorización completa** — aunque la relación costo-beneficio de esa solución puede ser suficientemente buena.

**Un olvido frecuente:** las prioridades de **los requisitos ya implementados también pueden cambiar** — especialmente los no funcionales. Para eso se puede usar el **análisis de brechas** (ver más abajo).

### 2.3 Requisitos funcionales vs. no funcionales 🔴

Esta es la sección más aprovechable de todo el capítulo para tu cursada.

Los métodos presentados **sirven para ambos tipos**, y a veces es preferible priorizarlos juntos. Pero **no siempre es aconsejable** — **por la misma razón por la que no deben priorizarse juntos requisitos de distintos niveles de abstracción.**

Las diferencias entre requisitos funcionales y no funcionales incluyen, sin agotarse en ellas:

| | **Requisitos funcionales** | **Requisitos no funcionales** |
|---|---|---|
| **Alcance** | Se relacionan usualmente con **funciones específicas** | **Afectan varias funciones** — desde un conjunto de funciones hasta el sistema entero |
| **Dependencia** | Se sostienen solos | Son **propiedades que las funciones o el sistema deben tener** — lo que implica que **son inútiles sin requisitos funcionales** |
| **Al implementarse** | **Funcionan o no funcionan** | Tienen a menudo **una escala deslizante de valor** entre bueno y malo |
| **Entre sí** | — | **Están a menudo en conflicto unos con otros**, lo que implica que **hay que hacer compromisos entre ellos** |

> ⚠️ **Cruce con la cátedra — el punto más aprovechable del capítulo.** Las clases 06 y 07 son *"RF y RNF en profundidad"* y *"Repaso e integración de RF y RNF"*, y el primer parcial evalúa RF y RNF. Esta tabla te da **cuatro dimensiones de contraste, no una definición memorizada**, y las cuatro son defendibles en un desarrollo.
>
> La segunda fila es la más potente conceptualmente: **un RNF es inútil sin un RF al cual calificar**. "El sistema debe responder rápido" no significa nada solo — responde rápido *a qué*. Eso explica de raíz por qué un RNF suelto, sin la función a la que aplica, está mal formulado.
>
> Y la tercera fila explica por qué los RNF necesitan métrica y los RF no tanto: un RF se verifica preguntando "¿anda?"; un RNF se verifica preguntando "¿cuánto?", y sin número no hay respuesta. Es el mismo argumento de los objetivos de diseño del capítulo 3.

**Cuándo priorizarlos por separado.** Si hay un requisito funcional sobre una función específica y un requisito no funcional sobre rendimiento, **puede ser difícil priorizar entre ellos**. En esos casos se los puede priorizar por separado, con la misma técnica o incluso con técnicas distintas.

**Una técnica especialmente apta para los no funcionales:** el **análisis conjunto** (*conjoint analysis*), que viene del marketing y prioriza alternativas de producto **basándose en la definición de distintos niveles de atributo**.

Dos observaciones que hacen sobre esa técnica:

- **No parece necesario incluir todos los niveles de todos los atributos** — un tiempo de respuesta más rápido siempre es preferible, no hace falta preguntarlo.
- Como **los compromisos suelen estar presentes** entre esos atributos —mantenibilidad contra rendimiento, por ejemplo— una idea es **incluir solo las comparaciones donde el compromiso esté en juego**.

### 2.4 Introducir la priorización en una organización 🟢

Como en toda transferencia de tecnología, se recomienda **empezar chico** con una o pocas prácticas —por ejemplo, asignación numérica para priorizar importancia y costo— **y agregar sofisticación (y por lo tanto complejidad) a medida que crecen la necesidad y el conocimiento**.

Como introducir y mejorar la priorización es una forma de **mejora de procesos**, deberían aplicarse las reglas de esa disciplina: **cambios en pasos chicos, probados y ajustados en consecuencia**.

Una buena idea es **monitorear las extensiones futuras midiendo la adherencia al proceso y la satisfacción de los interesados** —internos y externos. Así es posible medir el proceso continuamente y **determinar cuándo se vuelve demasiado pesado**, calculando el costo contra el beneficio de cada extensión.

### 2.5 Evaluar la priorización 🟡

Para mejorar el proceso y el producto, hace falta **evaluar el resultado de las priorizaciones en retrospectiva**.

**Condición para poder hacerlo:** que **se conserve la información sobre las prioridades**, porque es la mejor base para analizar tanto el producto como el proceso. Y eso incluye **información sobre los requisitos seleccionados y también sobre los descartados** de una versión.

Con acceso a esa información se puede hacer un **análisis post mórtem** para evaluar si se seleccionaron los requisitos correctos y si cumplieron las expectativas de los interesados. Si no fue así, se puede cambiar el proceso y el producto para las versiones siguientes.

#### El análisis de brechas 🟡

Una manera de evaluar si se asignaron las prioridades correctas es el **análisis de brechas**, donde se calcula la **"brecha" entre el nivel percibido de cumplimiento de un requisito y la importancia de ese requisito**.

```
   IMPORTANCIA del requisito ─────┐
                                  ├──► BRECHA
   CUMPLIMIENTO percibido ────────┘

   brecha grande = alta prioridad de mejora
```

El resultado muestra **cuán bien se cumple cada requisito, o cada tipo de requisito, en relación con cuán importante lo consideran los interesados**. Los requisitos con **las brechas más grandes** obtienen las **prioridades de mejora más altas**. Eso permite mejorar las partes del producto con bajo nivel de cumplimiento, y también **ajustar el proceso para evitar que la situación se repita**.

### 2.6 Cómo usar los resultados 🔴

> **Los resultados de una priorización deben usarse con criterio.**

Los autores dan tres razones por las que **no se puede simplemente seguir la lista**:

**1. Las dependencias.** Hay que considerar las dependencias entre requisitos al elegir cuáles incluir. Pueden estar relacionadas con **costo, valor, cambios, personas, competencia, precedencia técnica**. Esas dependencias **pueden forzar a implementar un requisito antes que otro**, lo que implica que no se puede seguir la lista de priorización sin más.

**2. Las prioridades pueden haber emergido mal.** Cuando la lista de prioridades se les presenta a los interesados, **la prioridad inicial puede haber surgido incorrectamente**: al verse confrontados con la lista, **quieren cambiar las prioridades**. Y una observación fina: **este problema es mayor en las técnicas donde el resultado no es visible durante el proceso**, como AHP.

**3. Las restricciones propias del producto.** Los proyectos tienen restricciones de esfuerzo, calidad, duración. Eso hace que la selección sea más compleja que si dependiera solo de la importancia de cada requisito.

**El enfoque recomendado ante todo esto:**

> **Proponer un número de soluciones alternativas** entre las cuales los interesados puedan elegir la más adecuada, según todos los factores de contexto implícitos.

Computarizando el proceso de generar esas soluciones candidatas, es posible **enfocar la atención de los interesados en un número relativamente chico de candidatas**, en vez de desperdiciar su tiempo discutiendo todas las alternativas posibles. Para automatizarlo hace falta **poner restricciones al producto final**: que no cueste más de cierto monto, que el desarrollo no exceda un plazo, que el nivel de riesgo no supere un umbral.

---

## 3. Un ejemplo completo 🟡

El capítulo cierra con un ejemplo trabajado. Vale seguirlo porque muestra el mecanismo entero funcionando.

**El escenario:** 15 requisitos (R1 a R15), tres clientes conocidos. Cada requisito se prioriza según distintos aspectos, con distintas técnicas y desde distintas perspectivas:

| Aspecto | Técnica usada | Quién lo prioriza |
|---|---|---|
| Importancia estratégica | AHP | Jefe de producto |
| Importancia para el cliente | 100 dólares / Diez principales | Clientes |
| Penalidad | AHP | Jefe de producto |
| Costo | 100 dólares | Desarrolladores |
| Tiempo | Asignación numérica (7 grupos) | Jefe de proyecto |
| Riesgo | Asignación numérica (3 grupos) | Especialista en requisitos |
| Volatilidad | Ordenamiento | Especialista en requisitos |

*(La asignación numérica usa 7 grupos para tiempo y 3 para riesgo, deliberadamente, para mostrar distintos niveles de granularidad.)*

### Los tres movimientos preparatorios 🔴

Antes de priorizar, el ejemplo hace tres cosas que valen más que el cálculo posterior:

**1. Triaje.** **R1 y R2 son absolutamente necesarios** para que el sistema funcione. Por lo tanto **no los priorizan los clientes** — pero sí se les estima costo, riesgo, etc., porque influyen en esas variables de todas maneras.

**2. Agrupamiento por dependencias.** Se identificaron **dos grupos de requisitos con dependencias altas** (deben implementarse juntos) y se los prioriza como una unidad: **R3, R4 y R5 se agrupan como R345**, y **R6 y R7 como R67**.

**3. Ponderación de interesados.** Los tres clientes y el jefe de producto reciben **pesos distintos** según cuán importantes los considera la empresa, usando la prueba de los 100 dólares para obtener los pesos relativos:

```
   Cliente 1 ........ 0,15
   Cliente 2 ........ 0,30
   Cliente 3 ........ 0,20
   Jefe de producto . 0,35   ← el peso más alto
```

**Por qué el jefe de producto pesa más** en este caso concreto: la misión de esta versión del producto es **invertir en requisitos de largo plazo y atraer clientes nuevos, a la vez que se conserva a los existentes**. Es una decisión de estrategia, no una regla general.

*(El Cliente 1 usó la técnica de los diez principales, y por eso sus prioridades quedaron repartidas en partes iguales entre los requisitos que consideró más importantes.)*

### La combinación

La prioridad final de cada requisito se calcula como **la suma de las prioridades que le dio cada interesado, multiplicada cada una por el peso de ese interesado**. Y los autores hacen notar algo importante:

> **Este cálculo es posible porque se usó una escala de razón y no una ordinal.** Con una escala ordinal, sumar y ponderar no significaría nada.

Después se combinan **importancia (peso 0,7) y penalidad (peso 0,3)** en un valor único, y sobre esa lista ordenada se aplican las restricciones del proyecto.

### Las dos restricciones y las dos soluciones candidatas 🟡

**Las restricciones del ejemplo:**

1. El proyecto **no puede costar más del 65 %** del costo total de los requisitos elicitados.
2. El **nivel de riesgo mediano** de los requisitos incluidos **no puede ser mayor a 2,5**.

**Primer intento — tomar de arriba de la lista.** Se incluyen los requisitos con mayor valor combinado hasta llegar al límite de costo.

**Resultado:** cumple el costo, **pero no cumple la restricción de riesgo**. El proyecto queda demasiado riesgoso.

**Segundo intento — usar la razón valor/costo.** En vez de tomar por valor absoluto, se calcula **cuánto valor aporta cada requisito por unidad de costo**, y se incluyen solo los que superan cierto umbral.

**Resultado:**

| | Solución 1 | Solución 2 |
|---|---|---|
| **Restricción de costo** | Cumple | Cumple, **con 9 % menos de costo** |
| **Restricción de riesgo** | **No cumple** | **Cumple** |
| **Valor logrado** | 83 % | **91 %** |

La segunda candidata **cuesta menos, es menos riesgosa y da más valor**. Los autores igual aclaran que **no es óptima**: el costo se restringió arbitrariamente al 65 % y otras combinaciones podrían ser mejores.

### La lección del ejemplo 🔴

Acá viene el remate conceptual, y es lo más valioso de toda la sección.

Este tipo de planificación de versiones se conoce en investigación operativa como el **problema de la mochila binaria**: maximizar valor cuando la selección está acotada por un límite superior.

**Pero hay una diferencia**, y es la que importa:

> **La planificación de versiones es un "problema perverso"** (*wicked problem*). Eso significa que **puede no existir una solución óptima**, que **cada planificación de versión es única**, y que **no existe una medida objetiva de éxito**.

Además, los valores de los aspectos del ejemplo **son estimaciones y medidas subjetivas**, en comparación con medidas objetivas como longitud, peso o volumen.

De ahí la conclusión:

> **En vez de buscar el conjunto óptimo, hay que descubrir distintas soluciones alternativas y elegir la que parezca más adecuada.** Esto implica que **el propósito de la priorización no es producir una lista final de requisitos, sino proveer soporte para tomar buenas decisiones.**

> ⚠️ **Cruce con la cátedra.** "El propósito no es producir la respuesta, es sostener la decisión." Esa frase describe el criterio con el que te corrigen: Laura acepta soluciones distintas a la propuesta **si están justificadas**. Este capítulo te da el fundamento teórico de por qué eso no es indulgencia sino la única postura correcta: en un problema perverso **no hay una respuesta óptima que descubrir**, hay decisiones que sostener con argumentos.

---

## 4. Investigación futura 🟢

Los autores enumeran las preguntas abiertas del área:

**1. Falta validación empírica.** El trabajo existente sobre priorización es limitado, y **existen pocas validaciones empíricas** de las distintas técnicas. Es común que se introduzcan técnicas nuevas que parecen funcionar bien, **pero cuya escalabilidad no se probó**. Y las evaluaciones que existen **se enfocan casi siempre en sistemas de juguete con pocos requisitos, rara vez más de 20**. Uno de los pocos estudios industriales encontró que **AHP no era usable con más de 20 requisitos**, porque el número de comparaciones se volvía excesivo para los profesionales.

**2. ¿Cuánta sofisticación hace falta realmente?** Se desarrollan técnicas cada vez más complejas con el objetivo de ayudar más a los profesionales, **pero los resultados rara vez se usan en la industria**. Los profesionales usan métodos simples como la asignación numérica. Y una observación aguda: **los profesionales viven en un ambiente distinto del de los sujetos experimentales —que suelen ser estudiantes— y están más limitados por restricciones de tiempo y costo.**

**3. ¿Cuándo es adecuada cada técnica?** Los estudios existentes rara vez discuten factores como **tamaño de la empresa, limitaciones de tiempo al mercado, cantidad de interesados, dominio**. El foco está en si una técnica es mejor que otra. **Un enfoque más sensato sería probar distintos enfoques en distintos ambientes** para entender cuándo cada uno es adecuado.

**4. Las dependencias.** Su impacto puede ser enorme. Y el problema de fondo: **técnicas como AHP asumen que los requisitos son independientes, aunque sabemos que rara vez lo son.** Hacen falta mejores maneras de manejar dependencias eficientemente.

**5. Funcionales y no funcionales.** Son muy distintos aunque tienen impacto serio uno sobre otro. **Priorizarlos completamente juntos o completamente separados puede no ser la mejor solución.** Hacen falta enfoques que combinen ambas priorizaciones eficientemente.

---

## 5. Resumen del capítulo 🟡

El capítulo presentó técnicas, aspectos y otras cuestiones a considerar al priorizar. Juntas forman **una base para priorizar requisitos sistemáticamente** durante el desarrollo.

El resultado de una priorización sugiere **qué requisitos deberían implementarse y en qué versión**. Las técnicas pueden ser una ayuda valiosa para que una empresa entienda qué es importante y qué no.

Y el cierre, en la misma línea que la lección del ejemplo:

> **Como con todos los métodos de evaluación, los resultados deberían ser interpretados y posiblemente ajustados por tomadores de decisión con conocimiento, en vez de aceptarse simplemente como una decisión final.**

---

## Mapa de la Parte 2

```
   SEGÚN CUÁNTOS CLIENTES
   uno ────────► ojo: cliente ≠ usuario, pueden tener
                 intereses OPUESTOS
   varios ─────► objetivo ganar-ganar; si se descuida una
                 perspectiva, el sistema es un fracaso para esa
   masivo ─────► segmentos de mercado + "personas" ficticias

   SIEMPRE: clientes + desarrolladores + finanzas
   PESAR a los interesados con criterio declarado
   (contra el "el que grita más, gana")

   ─────────────────────────────────────────────

   CUESTIONES PRÁCTICAS
   ABSTRACCIÓN ──► nunca mezclar niveles
                   (el baúl siempre le gana a la lucecita)
   REPRIORIZAR ──► fácil en ordinal, complejo en razón
   RF vs RNF ────► 4 diferencias; el RNF es INÚTIL sin un RF
   EVALUAR ──────► análisis de brechas
                   (importancia − cumplimiento)
   USAR ─────────► NO seguir la lista sin criterio:
                   dependencias, prioridades mal emergidas,
                   restricciones del proyecto

   ─────────────────────────────────────────────

   LA LECCIÓN DE FONDO
   la planificación de versiones es un PROBLEMA PERVERSO:
   no hay solución óptima, cada caso es único,
   no hay medida objetiva de éxito
   → el propósito de priorizar NO es dar la respuesta,
     es SOSTENER la decisión
```

---

## Preguntas para chequear que quedó

1. Compará desarrollo a medida y dirigido por el mercado en las ocho facetas de la tabla.
2. ¿Por qué en un escenario de un solo cliente puede haber conflicto? Dé el ejemplo del capítulo.
3. ¿Qué pasa si en un escenario de varios clientes se descuida una perspectiva?
4. ¿Qué son las "personas" y para qué sirven al priorizar?
5. ¿Qué tres perspectivas deberían estar siempre representadas, y qué aporta cada una?
6. ¿Cómo se combate el problema de que "el que chilla más consigue lo que quiere"?
7. Explicá el ejemplo del baúl y la lucecita. ¿Qué regla se desprende?
8. ¿Qué dos ventajas tiene agrupar requisitos antes de priorizar?
9. ¿Por qué repriorizar es más difícil en escala de razón que en escala ordinal? ¿Cuál es el atajo y qué se pierde con él?
10. Enumerá las cuatro diferencias entre requisitos funcionales y no funcionales.
11. ¿Por qué se dice que un requisito no funcional es inútil sin un requisito funcional?
12. ¿Por qué un RF "funciona o no funciona" mientras un RNF tiene una escala deslizante? ¿Qué consecuencia tiene eso para verificarlos?
13. ¿Qué se recomienda al introducir la priorización en una organización que nunca priorizó?
14. Explicá el análisis de brechas. ¿Qué requisitos obtienen mayor prioridad de mejora?
15. ¿Por qué hay que conservar la información de los requisitos **descartados** de una versión?
16. Nombrá las tres razones por las que no se puede seguir la lista de prioridades sin criterio.
17. ¿Por qué el problema de "las prioridades emergieron mal" es peor en AHP que en otras técnicas?
18. En el ejemplo, ¿por qué R1 y R2 no los priorizan los clientes pero sí se les estima costo y riesgo?
19. ¿Por qué el jefe de producto recibió el peso más alto en el ejemplo? ¿Es una regla general?
20. ¿Por qué la segunda solución candidata es mejor que la primera en las tres dimensiones?
21. ¿Qué es un "problema perverso" y por qué la planificación de versiones lo es?
22. ¿Cuál es entonces el verdadero propósito de priorizar?

---

**FIN DEL CAPÍTULO 4 — PARTE 2**

**FIN DEL CAPÍTULO 4**

*Sigue el capítulo 5: interdependencias entre requisitos, en 2 partes.*
