# Lectura en español — Cap. 5 · Parte 2: Aplicaciones prácticas y agenda de investigación

> **Origen.** Capítulo 5, secciones 5.4 a 5.6, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Åsa G. Dahlstedt y Anne Persson**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1.** Se asumen conocidos el concepto de trazabilidad y los siete tipos de interdependencia: `refinado_a`, `cambia_a`, `similar_a`, `requiere`, `entra_en_conflicto_con`, y los dos de costo/valor.

---

## Cómo leer esta parte

La sección 1 recorre **siete actividades** de la ingeniería de software y, para cada una, dice **qué tipos de interdependencia hacen falta ahí**. Es la parte útil: convierte el modelo de tipos en una herramienta de trabajo en vez de una taxonomía.

Al final hay una tabla que resume las siete actividades contra los siete tipos. Si tenés poco tiempo, mirá esa.

---

## 1. Cómo ayuda saber sobre interdependencias 🟡

Los autores ya argumentaron que los requisitos son interdependientes y que eso influye distintas actividades. Esta sección da el detalle actividad por actividad.

---

### 1.1 Gestión de requisitos 🔴

La **gestión de requisitos** se ocupa de manejar la gran cantidad de información relacionada con requisitos que se elicita durante el proceso. Entre otras cosas incluye **llevar registro y mantener la descomposición de los requisitos** — cómo los requisitos y objetivos de alto nivel se descomponen en requisitos más refinados que describen el sistema en mayor detalle.

**Por qué importa conocer esa descomposición.** El capítulo da cuatro razones:

**1. Entender por qué existen los requisitos derivados** y cómo se desarrollaron — especialmente porque **la descomposición se basa a menudo en supuestos hechos por los desarrolladores y otros interesados**. Si los supuestos no quedan visibles, nadie puede revisarlos.

**2. Asegurar que todo requisito de bajo nivel se relaciona con uno de alto nivel o con una meta** — es decir, **que existe por una buena razón**. Y de ahí una regla:

> Como en un proyecto casi siempre hay restricciones apretadas de presupuesto y cronograma, **los requisitos que sostienen las estrategias y objetivos de negocio del sistema deberían tener alta prioridad**. Por lo tanto, **todos los requisitos deberían venir de una fuente aprobada y basarse en las necesidades reales de clientes y usuarios.**

**3. Dar una vista histórica de la evolución** de los requisitos, mostrando cómo los de alto nivel se descompusieron en detalle.

**4. Manejar la cantidad creciente de requisitos**, ya que agruparlos en jerarquías es una forma de controlar el volumen.

**Tipos relevantes:** los estructurales `refinado_a` y `cambia_a`, y también `requiere`.

> ⚠️ **Cruce con la cátedra.** El punto 2 es el más aprovechable: **un requisito que no se puede colgar de ninguna meta de negocio es sospechoso**. Es un criterio de revisión concreto — recorrer la lista de requisitos preguntando "¿de qué objetivo cuelga este?" y ver cuáles quedan huérfanos. Los huérfanos suelen ser introspección disfrazada (capítulo 2, Parte 3) o funcionalidad que alguien quiso meter porque le pareció linda.

---

### 1.2 Gestión de cambios y análisis de impacto 🔴

> **Uno de los desafíos mayores del desarrollo de software es la evolución y el cambio constante de los requisitos.**

La gestión de cambios y el análisis de impacto se ocupan de manejar los cambios sistemáticamente y de **evaluar el efecto de los pedidos de cambio**.

Los autores notan que **la investigación en análisis de impacto se enfocó tradicionalmente en el código de programa**, lo que puede explicar la cantidad limitada de literatura sobre la influencia de las interdependencias de requisitos en este contexto.

**Para qué sirven las interdependencias acá:**

- **Muestran la evolución** de los requisitos — cómo un requisito cambió a lo largo del tiempo.
- **Muestran los supuestos principales detrás de un requisito**, al relacionarlo con el requisito original — lo que puede **indicar su importancia**.
- Y el beneficio principal: **muestran si los requisitos se influyen entre sí**, lo que **facilita la precisión del análisis de impacto**, porque permite identificar qué otros requisitos necesitan cambiar por causa de un pedido de cambio.

**Tipos relevantes:** toda la categoría **de restricción**, más `cambia_a`. También `refinado_a` y `requiere`, porque permiten mostrar los supuestos principales detrás de un requisito.

---

### 1.3 Planificación de versiones 🟡

En desarrollo dirigido por el mercado, los proveedores lanzan versiones nuevas de manera más o menos regular. **La planificación de versiones es la actividad de seleccionar la colección óptima de requisitos** para implementar en la próxima versión.

Los proveedores suelen tener **una gran cantidad de requisitos entre los cuales elegir**. El objetivo es doble: identificar el conjunto que **maximiza el valor agregado para los clientes**, y **seleccionar los que puedan desarrollarse dentro de las restricciones de recursos disponibles y de la fecha fija de la versión**.

La selección se basa usualmente en **la prioridad y el costo estimado**. Pero:

> Debido a que los requisitos se relacionan y se afectan entre sí, **eso no puede ser la única base para la selección**. Seleccionar un requisito puede implicar que **varios otros tengan que seleccionarse también**, o al menos considerarse.

**El ejemplo:** seleccionar un requisito A de alta prioridad puede implicar que **el requisito B, costoso y no tan prioritario, tenga que seleccionarse también**, porque A no puede implementarse sin tener B en su lugar.

Las interdependencias, entonces, **aumentan la complejidad de la selección**. Y conocerlas es base importante para las decisiones, **porque demuestran el impacto de incluir o excluir requisitos**.

**Tipos relevantes y por qué —esta lista es la más completa del capítulo:**

| Tipo | Para qué sirve en planificación de versiones |
|---|---|
| **`requiere`** | Mostrar que **si un requisito se selecciona, otro debe incluirse también** |
| **`similar_a`** | **Evitar incluir dos requisitos similares** en una misma versión. Si eso pasa, **los recursos se calculan dos veces para la misma funcionalidad o propiedad** — y esa doble contabilización podría haber impedido incluir otros requisitos por límites de recursos |
| **`conflicto_con`** | Los conflictos pueden **resolverse antes de la inclusión o evitarse**, por ejemplo incluyendo solo uno de los dos requisitos en conflicto |
| **Costo/valor** | Permite **maximizar la selección respecto de los recursos disponibles** |

> La razón del `similar_a` es más aguda de lo que parece a primera vista. El problema no es solo hacer dos veces el mismo trabajo — es que **el presupuesto se consume dos veces por una sola cosa**, y eso deja afuera funcionalidad que sí era distinta.

---

### 1.4 Reutilización de componentes 🟢

La trazabilidad sostiene el proceso de **reutilizar componentes a nivel de requisitos**.

**Cómo funciona:** si las similitudes entre requisitos están documentadas, esa información sirve para **identificar componentes reutilizables**, comparando los requisitos enunciados con los requisitos del sistema existente. Después esos requisitos pueden **rastrearse hacia abajo hasta el diseño y la implementación**, usando la información de trazabilidad, para identificar el componente que los implementa.

Además, la información de trazabilidad sirve para **reconocer el ajuste necesario** para adaptar esos componentes a la aplicación nueva.

**Tipo relevante:** `similar_a`.

---

### 1.5 Reutilización de requisitos 🟢

Cuando se desarrollan **variantes de productos de software**, parte de los requisitos puede ser la misma, ya que los productos suelen construirse sobre la misma funcionalidad básica. Los documentos de requisitos tienen entonces muchas similitudes.

**El problema actual:** cuando los requisitos se reciclan —al construir una variante nueva de un producto— **eso se hace habitualmente de manera improvisada, lo que consume tiempo y es propenso a errores.** Las razones:

1. La dificultad de **identificar qué requisitos pueden reutilizarse**.
2. La dificultad de **asegurar que se incluyan todos los requisitos relacionados** con los reciclados.
3. Y el problema inverso: que **se incluyan demasiados requisitos** en el documento nuevo.

**Una advertencia importante:** **no todos los requisitos relacionados pueden incluirse sin análisis.** Hay pasos de reciclado más complejos donde hay que considerar la adaptación — pueden hacer falta cambios a los requisitos reciclados.

Y una observación de fondo:

> **El refinamiento de un requisito de alto nivel en requisitos más detallados es un proceso de negociación**, donde se deciden los detalles de la funcionalidad. Por lo tanto, **no es evidente que todos esos detalles deban formar parte de la funcionalidad de la versión nueva** del sistema.

**El ejemplo:** una función de búsqueda puede estar explicada por varios requisitos detallados que describen su comportamiento fino. Al reciclar esa funcionalidad, **algunos detalles avanzados pueden excluirse por restricciones de presupuesto**.

**Tipos relevantes:** `refinado_a`, `requiere`, y toda la categoría **de restricción**.

---

### 1.6 Diseño e implementación 🟡

> **El diseño de software está en gran medida orientado a la toma de decisiones.**

Se hacen muchos compromisos: decidir el alcance y la funcionalidad del sistema, y también entre el costo de implementación y otros recursos. **Un compromiso común es entre requisitos en conflicto o inconsistentes.**

El desafío es **analizar hasta qué punto múltiples requisitos pueden satisfacerse simultáneamente**, lo cual es beneficioso para **detectar problemas potenciales antes de la construcción del sistema**.

#### Gestión de la interacción de requisitos 🟡

Para responder a esa necesidad se desarrolló un área específica. Su definición:

> **Gestión de la interacción de requisitos: el conjunto de actividades dirigidas al descubrimiento, la gestión y la disposición de las relaciones críticas entre conjuntos de requisitos.**

**Su objetivo:** encontrar dependencias entre requisitos y **mostrar aquellas que no pueden satisfacerse simultáneamente**. Ese conocimiento es enormemente importante para identificar y resolver problemas cuando el sistema se está diseñando.

**Otro uso:** las interdependencias sirven además para **planificar la implementación** — en qué orden implementar los requisitos por restricciones de prueba y eficiencia, o cómo **asignar requisitos a desarrolladores**.

**Tipos relevantes:** `conflicto_con` es el fundamental acá. También `requiere` y `aumenta/disminuye_el_costo_de`.

---

### 1.7 Pruebas 🟡

Las pruebas se ocupan, entre otras cosas, de **asegurar que todos los requisitos del sistema se hayan cumplido**. Incluyen planificar las pruebas, seleccionar y diseñar casos de prueba, ejecutarlos, e informar los resultados.

#### El orden de ejecución 🟡

> **El orden en que se ejecutan los casos de prueba es esencial**, porque **alguna funcionalidad del sistema no puede probarse antes de que otra funcionalidad esté en su lugar y verificada.**

Y además es esencial **por razones de eficiencia**:

> **La funcionalidad sobre la cual se apoya mucha otra funcionalidad debería probarse primero**, para evitar o reducir la re-ejecución innecesaria de casos de prueba si se descubren errores en esa funcionalidad de base.

La situación ideal es **identificar y probar primero esa información de base**, y después probar la funcionalidad relacionada. **Esas relaciones pueden descubrirse a partir de las dependencias entre requisitos.**

Esto se relaciona además con las **pruebas de regresión**, donde se seleccionan casos de prueba relacionados para re-ejecutar cuando se encuentran y corrigen errores. En ese caso **la funcionalidad ya probada debe probarse de nuevo**, para asegurar que el sistema funciona como debe y como funcionaba antes de la corrección.

#### El diseño de los casos de prueba 🔴

Los casos de prueba se desarrollan **a partir de los requisitos**, para asegurar su cumplimiento. Y como los requisitos están relacionados:

> **El conocimiento sobre las interdependencias afecta ciertamente la capacidad de crear casos de prueba útiles y completos.** Los casos de prueba se relacionan con uno o varios requisitos, lo que significa que **las interdependencias sirven para decidir qué requisitos deberían agruparse en un mismo caso de prueba.**

**Tipos relevantes:** principalmente `requiere` y la categoría **de restricción**. Pero también es importante tener buena estructura y visión general del conjunto, lo que hace relevante la categoría **estructural**, sobre todo `refinado_a`.

> ⚠️ **Cruce con la cátedra.** Este apartado le da contenido concreto a la palabra **verificable**. Un requisito es verificable si se puede derivar de él un caso de prueba — y este capítulo agrega que además hay que saber **en qué orden** ejecutarlos y **cuáles agrupar**. La cadena completa es: requisito bien redactado → caso de prueba derivable → verificación posible. Si el requisito es ambiguo, la cadena se corta en el primer eslabón.

---

## La tabla que resume todo 🔴

Reuniendo lo que el capítulo asigna actividad por actividad:

| Actividad | Tipos de interdependencia relevantes |
|---|---|
| **Gestión de requisitos** | `refinado_a` · `cambia_a` · `requiere` |
| **Gestión de cambios / análisis de impacto** | Toda la categoría de **restricción** · `cambia_a` · `refinado_a` · `requiere` |
| **Planificación de versiones** | `requiere` · `similar_a` · `conflicto_con` · toda la categoría **costo/valor** |
| **Reutilización de componentes** | `similar_a` |
| **Reutilización de requisitos** | `refinado_a` · `requiere` · toda la categoría de **restricción** |
| **Diseño e implementación** | `conflicto_con` (fundamental) · `requiere` · `aumenta/disminuye_el_costo_de` |
| **Pruebas** | `requiere` · categoría de **restricción** · `refinado_a` |

> Notá que **`requiere` aparece en seis de las siete actividades**. Si tuvieras que documentar un solo tipo de interdependencia, sería ese. Y `conflicto_con` es el que más pesa en las dos actividades donde se decide qué se construye y cómo.

---

## 2. Agenda de investigación 🟢

Los autores declaran que el tema **está bastante inexplorado y es diverso**. Hay partes con más investigación —gestión de la interacción de requisitos, gestión de conflictos— pero **en conjunto hace falta una cantidad sustancial de investigación adicional**. Plantean cuatro áreas.

### 2.1 ¿Cuál es la naturaleza de las interdependencias?

Como el fenómeno está poco explorado, **no se sabe mucho sobre él como tal**. Las preguntas abiertas:

- **¿Con qué frecuencia** son interdependientes los requisitos?
- **¿Por qué** son interdependientes y **cómo exactamente** se afectan entre sí?
- **¿Qué tipo de dependencia es el más común**?
- **¿El modelo de tipos fundamentales cubre las relaciones más comunes?**

Resolver estas preguntas se considera **esencial** para mejorar el entendimiento del fenómeno, y en particular para desarrollar enfoques que aborden las tres cuestiones siguientes.

### 2.2 ¿Cómo identificamos las interdependencias?

El problema no es solo **registrar y mantener** los vínculos: **hay que identificarlos de alguna manera**.

Algunas pueden ser fáciles de identificar al analizar el conjunto de requisitos, **pero hay otras más difíciles de descubrir**. Y **puede ser difícil identificar cómo se afectan entre sí, especialmente en el caso de los requisitos no funcionales**.

#### El problema de la dinámica 🟡

Este es el punto más interesante de la agenda:

> **Las interdependencias no son necesariamente estáticas a lo largo del ciclo de vida.**

El ejemplo: si hay que hacer un cambio al requisito R1, **eso puede no afectar a R2** — pero **en la planificación de versiones, R1 puede tener un impacto importante sobre el valor de R2 para el cliente**.

Es decir: **la misma pareja de requisitos puede estar relacionada o no según qué actividad se esté haciendo.** La dinámica de las interdependencias es un área de investigación futura.

#### El riesgo de agregar trabajo

Los autores señalan un riesgo práctico: identificar interdependencias **podría verse como otra tarea más a hacer dentro de un cronograma apretado**.

**La solución que proponen:** combinar ese análisis con **actividades ya existentes** —como la priorización o las inspecciones— para **aprovechar trabajo que ya se está haciendo**. Lo consideran un buen punto de partida.

#### Lo que ya existe

- Trabajo sobre **herramientas de lenguaje** para analizar conjuntos de requisitos, pero **solo para identificar similitudes**.
- Un método para **registrar automáticamente** vínculos de trazabilidad.
- **Análisis por pares** de los requisitos para descubrir interdependencias, con alternativas para reducir el tiempo que lleva.

**Las limitaciones de todo eso:** los dos últimos enfoques **asumen que los desarrolladores ya saben cómo se afectan los requisitos**, y **ninguno maneja dependencias dinámicas**. Falta además:

> Enfoques que se enfoquen en **explorar las consecuencias de un tipo de interdependencia particular en una situación dada** — es decir, **cómo se afectan los requisitos, y no solo que se afectan.**

### 2.3 ¿Cómo describimos las interdependencias?

Una vez identificadas, hay que **almacenarlas y gestionarlas**. Y acá hay un problema con las herramientas actuales:

> **Proveen medios para almacenar una relación entre requisitos, pero dan muy poca guía respecto de la semántica, el significado inherente y las consecuencias de esa relación.**

Las cuestiones abiertas:

**1. Escala.** Grandes cantidades de interdependencias son difíciles y costosas de mantener. **¿Cómo desarrollar un enfoque que escale?** ¿Habría que **limitar** la cantidad? Si sí, ¿enfocarse en **las más críticas**, o en **los requisitos más críticos**, o es mejor **agrupar requisitos y almacenar relaciones entre grupos**? Y además: **¿cómo saber cuáles son las más críticas en cada situación, y qué significa "crítica" en cada contexto?**

**2. Fuerza.** Podría hacer falta **almacenar la fuerza de la dependencia**, ya que el impacto puede ser chico o grande.

**3. Dinámica.** Hay que considerar las interdependencias dinámicas. **¿Cómo mostrar bajo qué condiciones existe una dependencia?**

**4. Elección del tipo.** Habría que abordar **la dificultad de elegir qué tipo de dependencia usar** — por ejemplo, priorizando los tipos según la situación de desarrollo.

Y una crítica explícita a lo que se usa hoy:

> Los autores **enfatizan la necesidad de mejorar mucho más allá de la tendencia actual a usar matrices de dependencia**. Los enfoques actuales de matriz de trazabilidad **carecen de soporte para especificar la naturaleza de las dependencias y tienen capacidades pobres de visualización.**

Queda además sin resolver **a qué nivel de abstracción describir las interdependencias**: en algunas situaciones es relevante relacionar requisitos autónomos, en otras es más apropiado **agrupar requisitos y relacionar grupos**.

Como área de donde tomar ideas nuevas, sugieren mirar el **modelado de metas**, ya que **los requisitos podrían considerarse metas de bajo nivel**.

### 2.4 ¿Cómo las abordamos en el proceso de desarrollo?

La literatura y los estándares de trazabilidad **dan pocas directrices sobre qué tipo de información hay que capturar y en qué contexto**.

Las cuestiones de investigación:

- **Qué significa, en distintos contextos, afirmar que existe una interdependencia.**
- **Qué tipos de interdependencia son críticos de considerar en cada situación.** El primer paso hacia eso es investigar **qué actividades se ven afectadas** por las interdependencias.

Se sugirió que la gestión debería basarse **en la fuerza más que en el tipo**. Los autores creen que seleccionar cuáles almacenar y gestionar **depende de varios factores**:

```
   · el USO POTENCIAL del conocimiento
     (qué necesitamos saber para cada decisión y situación)
   · la FUERZA de las dependencias
   · la CRITICIDAD y SIGNIFICACIÓN de los requisitos
```

### 2.5 Cómo se relacionan estas cuestiones entre sí 🟢

Los autores cierran la agenda con una reflexión metodológica honesta:

- **Poder descubrir e identificar interdependencias es prerrequisito para tener algo que almacenar y gestionar.**
- Para sostener efectivamente la gestión, **hay que entender cómo se usa ese conocimiento** en las actividades y decisiones del desarrollo.
- Para hacer la identificación más eficiente, **hay que saber más sobre qué deberíamos identificar** — o sea, cómo las interdependencias afectan las distintas situaciones.

De ahí la conclusión:

> **No hay un punto de partida obvio para la investigación entre estas tres cuestiones.** Existen maneras de identificar interdependencias, pero podrían mejorarse. Sería beneficioso saber más sobre qué deberíamos identificar antes de empezar. Por otro lado, con mejores técnicas para explorar relaciones potenciales, se sostendría el trabajo de averiguar qué tipos de dependencia hay. **Abordar las tres cuestiones es esencial.**

---

## 3. Resumen del capítulo 🔴

Los autores recapitulan:

**La mayoría de los requisitos individuales no pueden tratarse de manera aislada.** Están relacionados y se afectan de maneras complejas. A esas relaciones las llamamos **interdependencias de requisitos**.

El capítulo hizo tres cosas:

1. **Identificó las interdependencias como parte de un tema mayor: la trazabilidad de requisitos.**
2. **Desarrolló un modelo** que describe los tipos fundamentales de interdependencia.
3. Mostró que **las dependencias no son un problema en sí mismas**, pero afectan muchas decisiones y actividades del proceso: gestión de requisitos, gestión de cambios y análisis de impacto, planificación de versiones, reutilización de componentes y de requisitos, diseño e implementación, y pruebas.

Y la advertencia de cierre:

> **No abordar las interdependencias de requisitos en esas situaciones muy probablemente cause problemas en términos de funcionalidad pobre y de desbordes de presupuesto y cronograma.**

Los desafíos principales para el futuro, según los autores:

```
   1. ENTENDER la naturaleza de las interdependencias
   2. DESARROLLAR enfoques que permitan
      identificarlas, describirlas y
      manejarlas efectivamente en el proceso
```

---

## Mapa de la Parte 2

```
   7 ACTIVIDADES × QUÉ TIPOS NECESITAN

   GESTIÓN DE REQUISITOS ────► refinado_a, cambia_a, requiere
     · todo requisito debe colgar de una meta
     · los huérfanos son sospechosos

   CAMBIOS / IMPACTO ────────► restricción, cambia_a,
                               refinado_a, requiere
     · sin esto, el impacto de un cambio se subestima

   PLANIFICACIÓN DE VERSIONES ► requiere, similar_a,
                                conflicto_con, costo/valor
     · similar_a evita pagar dos veces lo mismo

   REÚSO DE COMPONENTES ─────► similar_a

   REÚSO DE REQUISITOS ──────► refinado_a, requiere, restricción
     · ojo: refinar es NEGOCIAR, no todo detalle
       viaja a la versión nueva

   DISEÑO E IMPLEMENTACIÓN ──► conflicto_con (clave),
                               requiere, ±costo
     · gestión de la interacción de requisitos

   PRUEBAS ──────────────────► requiere, restricción, refinado_a
     · orden de ejecución: primero la base
     · qué requisitos agrupar en un caso de prueba

   ══► `requiere` aparece en 6 de las 7

   ─────────────────────────────────────────────

   AGENDA: ¿cuál es su NATURALEZA? · ¿cómo IDENTIFICARLAS?
   · ¿cómo DESCRIBIRLAS? · ¿cómo ABORDARLAS en el proceso?
   Problema abierto clave: son DINÁMICAS — la misma pareja
   está relacionada o no según qué actividad estés haciendo.
```

---

## Preguntas para chequear que quedó

1. ¿Por qué es importante conocer la descomposición de los requisitos? Nombrá las cuatro razones.
2. ¿Qué significa que un requisito debe "venir de una fuente aprobada"? ¿Cómo usarías eso como criterio de revisión?
3. ¿Por qué la investigación en análisis de impacto se enfocó históricamente en el código y no en los requisitos?
4. ¿De qué tres maneras ayudan las interdependencias al análisis de impacto?
5. En planificación de versiones, ¿por qué la prioridad y el costo no pueden ser la única base de selección?
6. ¿Por qué `similar_a` es importante al planificar una versión? ¿Qué problema concreto evita?
7. ¿Cómo se usa `similar_a` para reutilizar componentes?
8. Nombrá los tres problemas que aparecen al reciclar requisitos de manera improvisada.
9. ¿Por qué no todos los requisitos detallados de una funcionalidad reciclada deberían pasar a la versión nueva?
10. Definí "gestión de la interacción de requisitos" y decí cuál es su objetivo.
11. ¿Qué tipo de interdependencia es fundamental en diseño e implementación, y por qué?
12. ¿Por qué el orden de ejecución de los casos de prueba es esencial? Dé las dos razones.
13. ¿Qué funcionalidad debería probarse primero y por qué?
14. ¿Cómo ayudan las interdependencias a decidir qué requisitos agrupar en un mismo caso de prueba?
15. ¿Qué tipo de interdependencia aparece en la mayor cantidad de actividades? ¿Cuántas?
16. Explicá el problema de la dinámica de las interdependencias con el ejemplo de R1 y R2.
17. ¿Qué solución proponen los autores para que identificar interdependencias no sea "una tarea más"?
18. ¿Qué limitación comparten los enfoques existentes de identificación?
19. ¿Cuál es la crítica de los autores a las matrices de trazabilidad?
20. ¿De qué tres factores depende decidir qué interdependencias almacenar?
21. ¿Por qué los autores dicen que no hay un punto de partida obvio para la investigación en esta área?
22. ¿Qué consecuencias tiene no abordar las interdependencias?

---

**FIN DEL CAPÍTULO 5 — PARTE 2**

**FIN DEL CAPÍTULO 5**

*Sigue el capítulo 6: análisis de impacto, en 2 partes.*
