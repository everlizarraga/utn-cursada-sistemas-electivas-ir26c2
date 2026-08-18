# Lectura en español — Cap. 13 · Parte 1: Contexto, desafíos y calidad del proceso

> **Origen.** Capítulo 13, secciones 13.1 a 13.3, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Björn Regnell** (Universidad de Lund, Suecia) y **Sjaak Brinkkemper** (Universidad de Utrecht, Países Bajos).
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.

---

## Por qué este capítulo importa más de lo que parece

Toda la serie viene mencionando la distinción entre **desarrollo a medida** y **dirigido por el mercado** — apareció en el capítulo 2 (los interesados son desconocidos), en el 4 (una tabla comparativa entera) y en el 12 (el cliente como entidad abstracta). **Este capítulo es donde esa distinción se desarrolla completa.**

Y hay una razón concreta por la que te conviene: **los sistemas que la cátedra asigna para analizar en equipo suelen ser productos masivos** —del tipo de una aplicación de mensajería con millones de usuarios anónimos. Eso los ubica del lado dirigido por el mercado, donde **no hay un cliente al que entrevistar**. Entender esa tensión te sirve para fundamentar decisiones en el TP.

---

## 1. La distinción de base 🔴

> **Una parte creciente del software producido apunta a ofrecerse en un mercado abierto** en vez de a un cliente específico.

| | **Dirigido por el mercado** | **A medida** (*bespoke*) |
|---|---|---|
| **Quién paga el desarrollo** | **Los costos de un producto genérico se dividen entre muchos compradores** de un mercado abierto | **Un solo cliente paga todos los costos** |
| **A quién responde el producto** | Al mercado | **A las necesidades y deseos de ese único cliente** |
| **De quién es la ganancia potencial** | **Del productor** | — |

El capítulo toma **el punto de vista de la organización que desarrolla**, y se enfoca en su proceso de IR, **orientado a alinear el contenido del producto con las necesidades de los segmentos de mercado apuntados, para crear un producto rentable.**

### Las tres preguntas básicas 🟡

Una organización que desarrolla para un mercado abierto necesita responder tres cosas:

**1. ¿Cómo diseñar y gestionar el proceso?** *"Para maximizar la ganancia es vital superar a los productores competidores EN INGENIERÍA DE REQUISITOS."* Hay que establecer un proceso eficiente que defina cómo trabajar con las actividades clásicas —elicitación, especificación, validación— **pero en un contexto de mercado.**

**2. ¿Cómo diseñar y gestionar el repositorio?** Y acá hay un cambio de fondo:

> Los requisitos de la IR clásica se almacenan a menudo **en un documento llamado "la especificación"**. En este contexto, **es más útil almacenar la información en un REPOSITORIO que evoluciona dinámicamente** con datos pasados y recientes de tipo y nivel de abstracción variados: perfiles de clientes potenciales y actuales, contenidos de versiones actuales y previas, estado actualizado tanto de los requisitos candidatos como de los que están en desarrollo.

**3. ¿Cómo hacer una planificación de versiones rentable?**

> **Un resultado clave del proceso es la decisión estratégica de QUÉ ENTREGAR CUÁNDO.** Esa decisión toma en cuenta los activos estratégicos de la organización —la competencia de sus ingenieros, sus inversiones en arquitectura hasta la fecha, su base actual de clientes— **y los combina con la estrategia general de negocio.**

> ⚠️ **Cruce con la cátedra.** El cambio de "documento de especificación" a "repositorio que evoluciona" es el mismo que atraviesa el capítulo 10. **Cuando los requisitos llegan continuamente y el producto tiene muchas versiones, el documento cerrado deja de ser el artefacto correcto** — porque nunca hay un momento en que esté terminado.

---

## 2. Los tipos de producto 🟡

El capítulo clasifica los productos según dos dimensiones.

**Por grado de personalización:**

| | Definición |
|---|---|
| **Genérico** | **Se usa tal cual, recién sacado de la caja**, quizás con configuraciones menores que el usuario final puede hacer |
| **Personalizado** | **Es útil después de haber sido adaptado** a las necesidades de un cliente específico — por ejemplo agregando módulos por una interfaz abierta |
| **Específico de cliente** | **Todo el producto se desarrolla pensando en los deseos de un cliente particular** |

**Por contenido de hardware y software:**

| | Definición |
|---|---|
| **Hardware puro** | **Fijo por su arquitectura de hardware**, sin software que vuelva flexibles sus funcionalidades |
| **Sistemas embebidos** | Plataforma de hardware **más software embebido** |
| **Software puro** | **Completamente software**, vendido independientemente de sus plataformas |

Cruzando las dos:

| | **Hardware puro** | **Embebido** | **Software puro** |
|---|---|---|---|
| **Genérico** | Notas adhesivas | Teléfono móvil | Cortafuegos |
| **Personalizado** | Muebles de oficina | Auto personalizado | Sistemas de planificación de recursos empresariales |
| **Específico de cliente** | Retrato pintado | Vehículo militar | Sitio web |

**Los productos dirigidos por el mercado** son los genéricos y personalizados, en las columnas de embebido y software puro.

### La distinción no es estricta 🔴

Y acá viene una observación realista que conviene tener:

> **No es raro que la organización venda a la vez un producto genérico a un mercado abierto Y horas de consultoría para personalizarlo.** Algunas partes nuevas y costosas de la evolución del producto **se desarrollan a menudo como funcionalidad específica de un cliente, pagada por ese cliente, y después se GENERALIZAN e incluyen en el producto genérico** para obtener más ingresos de la inversión.
>
> **En esos casos, el productor tiene que lidiar con las dos formas de IR, más la generalización de las partes personalizadas.**

**Otros factores que afectan el contexto:**

- **El tipo de comprador:** empresa contra consumidor. Difieren en cuestiones de usabilidad, imagen de producto, canales de comercialización y cantidad de relaciones con clientes a mantener.
- **La complejidad de la interfaz.** Y el ejemplo es bueno: **un sistema de frenado antibloqueo embebido en un auto tiene una interfaz simplísima —un pedal y una lámpara— pero el software es muy complejo.**

> **Los usuarios de sistemas con interfaces complejas probablemente den retroalimentación extensa sobre cuestiones de interfaz, mientras que los sistemas embebidos transparentes quizás solo llamen la atención CUANDO NO FUNCIONAN COMO SE ESPERABA.**

> ⚠️ **Cruce con la cátedra.** Ese contraste es un buen recordatorio al elegir técnicas de elicitación: **de un sistema invisible no vas a recibir quejas útiles**, porque nadie piensa en él hasta que falla. La elicitación tiene que salir a buscarlo de otra manera.

---

## 3. Las diferencias, una por una 🔴🔴

Esta es la sección más aprovechable de la parte. La evidencia empírica de varios estudios muestra que la IR dirigida por el mercado difiere de la de proyectos a medida **en muchos aspectos**:

| Aspecto | **Dirigido por el mercado** | **A medida** |
|---|---|---|
| **Objetivo primario** | **Entregar el producto correcto en el momento correcto** | **Cumplir un contrato** y adherir a una especificación de requisitos |
| **Cómo se mide el éxito** | **Ventas, cuota de mercado, reseñas del producto** | **Satisfacción del cliente y aceptación del usuario** determinan directamente si el proyecto fracasó o no |
| **Ciclo de vida** | **Una larga serie de versiones**; el producto sufre **evolución continua** | Dividido en **desarrollo primero y mantenimiento después**. A menudo **una versión mayor** |
| **Elicitación** | **Innovación de requisitos nuevos combinada con análisis de mercado.** Algunas funcionalidades pueden ser **confidenciales** y los usuarios eventuales **desconocidos**, así que **no siempre se puede confiar en entrevistas** como fuente principal | **Recolectar información sobre los deseos de una organización**, por ejemplo mediante entrevistas con los usuarios conocidos |
| **Especificación** | **Menos formal**; el **texto en lenguaje natural es la manera dominante** de documentar | Más formal |
| **Dónde va el esfuerzo** | **Priorización, estimación de costos y planificación de versiones** — todas conducidas por la organización que desarrolla | **Negociación y resolución de conflictos** |
| **Validación** | **A menudo se DEMORA hasta una etapa tardía** — exposiciones en ferias, o pruebas beta con clientes clave seleccionados | Puede hacerse **continuamente**, mediante los contactos entre el cliente y los desarrolladores |

### Las seis características resumidas 🔴

El capítulo condensa el contexto típico en seis puntos:

```
   · LA ORGANIZACIÓN QUE DESARROLLA TOMA TODAS LAS
     DECISIONES, PERO TAMBIÉN ASUME TODOS LOS RIESGOS
   · hay un FLUJO CONTINUO de requisitos durante toda
     la vida del producto
   · el volumen de requisitos es potencialmente muy
     grande y CRECE CONTINUAMENTE
   · la MAYORÍA de los requisitos se describe
     INFORMALMENTE
   · el producto EVOLUCIONA continuamente y se entrega
     en MÚLTIPLES VERSIONES
   · la planificación de versiones se enfoca en el
     TIEMPO AL MERCADO y el RETORNO DE INVERSIÓN
```

> ⚠️ **Cruce con la cátedra — leelo pensando en tu TP integrador.** Si el sistema que te asignaron es un producto masivo, **tres de estas diferencias te afectan directamente:**
>
> **1. No hay a quién entrevistar.** La fila de elicitación lo dice: los usuarios eventuales pueden ser desconocidos. La consecuencia práctica es que la técnica que la materia va a evaluar —la entrevista— **se aplica sobre un caso donde en la realidad no habría entrevistado.** Vale saberlo y, si el enunciado lo permite, **declarar el supuesto**: a quién estás entrevistando y en representación de quién.
>
> **2. La validación se demora.** En un producto de mercado no hay un cliente que valide sobre la marcha. Eso hace que **los errores de interpretación duren más** — que es exactamente el problema del capítulo 11: sin cliente disponible, las ambigüedades mal resueltas se duplican.
>
> **3. La organización asume todos los riesgos.** No hay contrato que proteja. Si se eligieron mal los requisitos, la pérdida es entera del que desarrolla.

---

## 4. Los siete desafíos 🔴

De un relevamiento con empleados de cinco empresas de tamaño y madurez variados:

### 4.1 Balancear el tirón del mercado y el empuje de la tecnología

> **Hace falta encontrar un buen compromiso entre los requisitos que corresponden a necesidades percibidas de los usuarios y los nuevos e inventivos, que pueden dar ventaja competitiva mediante tecnología rompedora.** Encontrar ese balance **puede ser un desafío delicado.**

### 4.2 El abismo entre comercialización y desarrollo 🔴

> En algunas empresas **se observa una brecha entre marketing y desarrolladores respecto de las visiones sobre la ingeniería de requisitos.**
>
> **Hacen falta mejor comunicación y colaboración entre esos grupos, para aumentar la calidad de los requisitos y con ella la del producto final.**

> Es la brecha cultural del capítulo 2, pero **dentro de la misma empresa**. No hace falta que el otro sea el cliente para no entenderse.

### 4.3 Inestabilidad organizacional y turbulencia del mercado 🔴

> **Las empresas sin un proceso definido corren un riesgo significativo si personas clave dejan la organización, ya que carecen de la documentación y la estructura necesarias.**
>
> **En tiempos de reducción de personal o de expansión rápida es muy difícil instalar un proceso repetible.**

> ⚠️ **Cruce con la cátedra.** Es el mismo argumento sobre **pérdida de conocimiento** que aparecía en el capítulo 5 sobre trazabilidad: sin documentación, **el saber se va con la persona.** Acá se lo nombra como riesgo organizacional explícito.

### 4.4 Herramientas simples para necesidades básicas 🟡

> **Algunas empresas pidieron técnicas simples y fáciles de usar para actividades básicas. Para ellas era un desafío encontrar soluciones que no fueran demasiado complejas.**

> Otra vez el principio que atraviesa la serie: **lo sofisticado que nadie usa vale menos que lo tosco que se usa.**

### 4.5 Dependencias entre requisitos 🟡

> **Las dependencias vuelven difícil la planificación de versiones. Algunas empresas las tratan de manera básica agrupando requisitos relacionados**, pero hacen falta maneras eficientes de gestionar al menos las más importantes.

### 4.6 Estimación de costo y valor 🔴

Este desafío tiene una simetría que vale la pena:

```
   SUBESTIMAR el COSTO ──► se excede la fecha límite
   SOBRESTIMAR el COSTO ─► se excluyen requisitos VALIOSOS

   SOBRE o SUBESTIMAR el VALOR ──► un producto MAL
   ALINEADO con las necesidades reales del mercado,
   y por lo tanto una inversión que pierde plata
```

**Los cuatro errores duelen, y duelen distinto.** No hay un lado seguro hacia el cual equivocarse.

### 4.7 Gestión de requisitos sobrecargada 🔴

> **Las sugerencias de requisitos de desarrolladores y clientes son esenciales.** El desafío es **evitar que el repositorio se inunde de requisitos, y cómo mantener el rendimiento cuando el número de requisitos que llegan alcanza picos.**

**Y el cierre de la sección, que es honesto:**

> **Los desafíos revelan problemas intrínsecamente difíciles, y es improbable que puedan enfrentarse con una solución única y simple. La cuestión clave para una empresa dirigida por el mercado es MEJORAR CONTINUAMENTE en manejar estos desafíos, de manera de mantenerse por delante de los competidores.**

---

## 5. La calidad del proceso 🔴

### Qué se mide

Cuando se diseña un proceso adaptado a una organización, conviene **definir criterios de éxito**. La calidad del proceso está ligada a la de los artefactos que produce, pero:

> **Una cuestión mayor de calidad del proceso es LA CALIDAD DE LAS DECISIONES que se toman sobre los artefactos producidos.**

### El modelo alfa/beta 🔴

Una manera de capturar la calidad de las decisiones es **la proporción de decisiones correctas de selección de requisitos** durante la planificación de versiones. Se definen dos clases de requisito:

| | Definición |
|---|---|
| **Requisito alfa** | Uno que tiene **tal calidad inherente que idealmente DEBERÍA seleccionarse**. Son **"los granos de oro"** entre todos los candidatos que el proceso debería hacer emerger |
| **Requisito beta** | Uno que **idealmente debería RECHAZARSE**, por ser de calidad inherentemente baja |

*("Alta calidad" puede interpretarse, por ejemplo, como la ganancia adicional real que el requisito aporta si se incluye en el producto.)*

Cruzando la calidad real con la decisión tomada salen **cuatro casos**:

| | **Seleccionado** | **Rechazado** |
|---|---|---|
| **Requisito alfa** | **A — selección correcta** | **B — rechazo incorrecto** |
| **Requisito beta** | **C — selección incorrecta** | **D — rechazo correcto** |

**Y dos métricas que salen de ahí:**

```
   CALIDAD DEL PRODUCTO = A / (A + C)
   la proporción de requisitos alfa entre todos los
   requisitos que efectivamente se seleccionaron
   e implementaron

   CALIDAD DE LA DECISIÓN = (A + D) / (A + B + C + D)
   la proporción de decisiones correctas sobre el total
   de decisiones
```

> **El desafío principal del proceso es ENCONTRAR Y SELECCIONAR los requisitos alfa mientras se RECHAZAN los beta** — maximizando A y D, minimizando B y C.

### El problema, que es grande 🔴

> **Sin embargo, el problema es que NO ES FÁCIL SABER si un requisito es realmente alfa o beta**, porque el compromiso costo-beneficio es muy difícil.
>
> **Las estimaciones tanto de costo como de valor son inherentemente propensas a error, y dependen de pronosticar avances de mercado y de tecnología, y de adivinar acciones de los competidores.**
>
> **Solo A POSTERIORI, cuando el producto lleva un período largo en el mercado, es posible decir con algún grado de certeza si fue correcto o no seleccionar o rechazar un requisito específico.**

Y el remate:

> **No obstante, es la calidad de esa toma de decisiones incierta la que determina ganadores y perdedores en el mercado de productos de software.**

### Cómo se ve gráficamente 🟡

En un diagrama de costo contra valor:

```
   los requisitos ALFA son los que tienen VALOR MAYOR
   QUE SU COSTO → están por encima de la línea de margen

   si se pide un margen mayor (digamos 20 %), la
   pendiente de la línea sube y aumenta la exigencia
   para que un requisito sea alfa
```

**Pero el costo y el valor reales son generalmente DESCONOCIDOS.** La decisión se toma **solo sobre estimaciones inciertas**, con lo cual **requisitos beta pueden terminar por encima de la línea**: el valor se sobrestimó y el costo se subestimó, y **un requisito beta se juzga incorrectamente como alfa.**

### Dos complicaciones adicionales 🔴

**1. El valor y el costo no dependen solo del requisito.**

> **Dependen también de su relación con otros requisitos.** El valor y el costo de un requisito **pueden cambiar según si otros requisitos se seleccionan o no.**
>
> Además, **pueden cambiar CON EL TIEMPO**: una demora imprevista en implementar un requisito **puede dar una relación costo-valor distinta de la esperada** cuando se tomó la decisión.

**2. "Valor" es una palabra compuesta.**

> **El concepto de "valor" puede ser una combinación compleja de muchos tipos de valor contribuyente**: valor para cierto segmento de mercado, **valor para la arquitectura interna que habilita el desarrollo de funcionalidades futuras**, valor para fortalecer la imagen de la empresa, valor para entrar en mercados nuevos.

> ⚠️ **Cruce con la cátedra.** El segundo punto es el más aprovechable: **"valor" no calificado es ambiguo, igual que "importancia" en el capítulo 4.** Y el ejemplo que dan es el que más se olvida — **el valor arquitectónico**: un requisito puede no darle nada al usuario y ser valiosísimo porque habilita todo lo que viene después.

### El hallazgo del relevamiento 🔴

Y acá viene un dato fuerte:

> El modelo alfa/beta se usó como base de un relevamiento entre jefes de producto, **donde se encontró que la mayoría de los encuestados que pudieron estimar consistentemente los parámetros del modelo revelaron que LA MAYORÍA DE LOS REQUISITOS DE PRODUCTO QUE HABÍAN IMPLEMENTADO ESTABAN INCORRECTAMENTE SELECCIONADOS.**
>
> **Este resultado indica que el potencial de mejora del proceso en las empresas relevadas es enorme.**

Y una técnica derivada: **el análisis retrospectivo de la calidad de selección**, que incluye un análisis de causa raíz de las decisiones sospechadas de estar mal, basado en una **re-estimación de costo y valor** hecha después. Reveló **muchas propuestas interesantes de mejora del proceso.**

---

## 6. La capacidad del proceso 🔴

### El problema de la congestión

> Los estudios empíricos encontraron que **hay riesgo de que el proceso entre en estado de CONGESTIÓN**, como consecuencia de **permitir que entren más requisitos de los que pueden manejarse con los recursos disponibles.**
>
> Eso resulta en **problemas de rendimiento y eventualmente un impacto negativo tanto sobre el tiempo al mercado como sobre la calidad del producto.**

Los estudios con teoría de colas y simulación muestran que **si el proceso se sobrecarga, el rendimiento se ve severamente entorpecido y el tiempo medio al mercado aumenta rápidamente.**

### La solución: el filtrado 🔴

> **Un medio importante de reducir el riesgo de sobrecarga es introducir una actividad de FILTRADO** (*screening*).
>
> **Durante el filtrado se hace una evaluación rápida del valor y el costo de cada requisito ANTES de gastar más esfuerzo en analizarlo.** Eso resulta en un juicio grueso sobre **si el requisito debería rechazarse de entrada, o si debería permitírsele entrar a las etapas siguientes de refinamiento.**

**Y el compromiso, dicho con honestidad:**

> **Por supuesto, hay mayor riesgo de tomar una decisión de rechazo equivocada basándose en un análisis rápido y grueso.**
>
> **Pero el beneficio de no empujar demasiados requisitos a las etapas siguientes —y así evitar la sobrecarga— puede ser MAYOR QUE LA PÉRDIDA DE UNOS POCOS GRANOS DE ORO**, ya que **tomar más trabajo del que la capacidad disponible permite puede dañar todo el desarrollo** y resultar en un tiempo medio al mercado irrazonablemente largo.

> ⚠️ **Cruce con la cátedra.** Esta es una lección de gestión que vale más allá del contexto del capítulo: **a veces conviene aceptar perder algo bueno para no ahogar el proceso entero.**
>
> Es la contracara del principio del capítulo 10, donde convenía aumentar la exhaustividad a costa de la precisión —marcar de más y descartar después. Acá el compromiso va al revés, **y la diferencia está en dónde está el cuello de botella.** En el capítulo 10 el costo de un falso positivo era treinta segundos de lectura; acá el costo de dejar entrar de más es congestionar el proceso completo.
>
> El criterio general que se desprende: **antes de decidir si conviene equivocarse de más o de menos, mirá qué recurso es el escaso.**

---

## Mapa de la Parte 1

```
   DIRIGIDO POR EL MERCADO      A MEDIDA
   muchos compradores           un cliente paga todo
   objetivo: producto correcto  objetivo: cumplir el
   en el momento correcto       contrato
   éxito = ventas               éxito = satisfacción
   muchas versiones             una versión + mantenimiento
   elicitar = INNOVAR +         elicitar = entrevistar a
   analizar el mercado          usuarios conocidos
   esfuerzo en PRIORIZAR        esfuerzo en NEGOCIAR
   validación DEMORADA          validación continua

   ══► la organización TOMA TODAS LAS DECISIONES
        y ASUME TODOS LOS RIESGOS ◄══

   ─────────────────────────────────────────────

   LOS 7 DESAFÍOS
   tirón del mercado vs empuje de la tecnología ·
   abismo comercialización/desarrollo · inestabilidad
   organizacional · herramientas simples · dependencias
   · estimación de costo y valor · sobrecarga

   ─────────────────────────────────────────────

   ══► EL MODELO ALFA/BETA ◄══
                  SELECCIONADO   RECHAZADO
   requisito ALFA    A ✓            B ✗
   requisito BETA    C ✗            D ✓

   calidad del producto = A/(A+C)
   calidad de la decisión = (A+D)/total

   PROBLEMA: no se sabe si un requisito es alfa o beta
   hasta MUCHO DESPUÉS
   y el "valor" es compuesto: de mercado, ARQUITECTÓNICO,
   de imagen, de entrada a mercados nuevos

   ─────────────────────────────────────────────

   CAPACIDAD: si entra más de lo que se puede procesar,
   el proceso SE CONGESTIONA
   → FILTRADO: evaluación rápida antes de gastar esfuerzo
   → se aceptan rechazos equivocados a cambio de no
     ahogar el proceso
```

---

## Preguntas para chequear que quedó

1. Diferenciá desarrollo dirigido por el mercado de desarrollo a medida en cuanto a quién paga y a quién responde el producto.
2. ¿Por qué en este contexto conviene un repositorio en vez de un documento de especificación?
3. Nombrá los tres grados de personalización de un producto.
4. ¿Por qué la distinción entre los dos modos de desarrollo no es estricta? Dé el ejemplo del capítulo.
5. ¿Por qué un sistema embebido transparente recibe poca retroalimentación de sus usuarios? ¿Qué implica eso para la elicitación?
6. Compará los dos modos en las siete filas de la tabla de diferencias.
7. ¿Por qué la elicitación no puede confiar en entrevistas en un producto de mercado?
8. ¿Por qué la validación se demora, y qué problema del capítulo 11 se agrava por eso?
9. Nombrá las seis características del contexto dirigido por el mercado.
10. Explicá el desafío de balancear tirón del mercado y empuje de la tecnología.
11. ¿Qué riesgo corren las empresas sin proceso definido cuando se va gente clave?
12. Explicá los cuatro errores posibles de estimación de costo y valor, y por qué ninguno es seguro.
13. ¿Qué son los requisitos alfa y beta?
14. Definí calidad del producto y calidad de la decisión en el modelo alfa/beta.
15. ¿Por qué es difícil saber si un requisito es alfa o beta? ¿Cuándo se puede saber con certeza?
16. ¿Cómo puede un requisito beta terminar por encima de la línea de margen?
17. ¿Por qué el valor y el costo de un requisito no dependen solo del requisito?
18. Nombrá cuatro tipos distintos de valor. ¿Cuál es el que más se olvida?
19. ¿Qué reveló el relevamiento entre jefes de producto?
20. ¿Qué es el filtrado y qué compromiso implica?
21. ¿Por qué conviene aceptar perder algunos "granos de oro" en el filtrado?

---

**FIN DEL CAPÍTULO 13 — PARTE 1**

*Sigue en la Parte 2: la gestión de datos —el modelo de estados de un requisito y el repositorio—, el análisis de mercado y la elicitación en este contexto, y la hoja de ruta y planificación de versiones con un ejemplo industrial.*
