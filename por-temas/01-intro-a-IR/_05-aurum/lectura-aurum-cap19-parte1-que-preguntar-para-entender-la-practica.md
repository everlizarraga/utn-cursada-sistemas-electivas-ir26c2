# Lectura en español — Cap. 19 · Parte 1: Qué preguntar para entender la práctica

> **Origen.** Capítulo 19, secciones 19.1 a 19.3, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Barbara Paech, Tom Koenig, Lars Borner** (Universidad de Heidelberg) y **Aybüke Aurum** (Universidad de Nueva Gales del Sur).
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.

---

## Qué es este capítulo

Después del capítulo 18 —que estudió seis empresas— este hace algo más ambicioso: **recopila más de veinte relevamientos hechos por otros a lo largo de veinte años** y los cruza.

Responde dos preguntas:

```
   1. ¿QUÉ PODEMOS PREGUNTAR para entender la práctica?
      → un marco de preguntas (esta Parte 1)

   2. ¿QUÉ EVIDENCIA TENEMOS hasta ahora sobre las
      prácticas? (la Parte 2)
```

**Para vos lo más útil es la Parte 2**, que trae los resultados acumulados. Pero esta primera tiene una sección que vale: **el catálogo de factores de contexto** que hay que registrar para que un dato tenga sentido. Sirve como recordatorio de que **un número sin contexto no dice nada.**

---

## 1. Por qué hace falta evidencia empírica 🔴

El capítulo arranca con una crítica al estado de la investigación en ingeniería de software:

> **A diferencia de, por ejemplo, las ciencias sociales, hasta ahora la mayor parte de la investigación en ingeniería de software NO INVOLUCRA MÉTODOS EMPÍRICOS, SINO EJEMPLOS DE JUGUETE. Claramente, eso NO DEMUESTRA NADA sobre la aplicabilidad en la práctica.**

**El argumento a favor:**

> **Necesitamos OBSERVACIONES DE LA PRÁCTICA, que ayuden a hacer aflorar leyes explicadas por teorías. Solo la investigación empírica puede producir observaciones, leyes y teorías válidas.**

**Y la excusa que se usa para no hacerlo:**

> **Desafortunadamente, LA COMPLEJIDAD de la ingeniería de software SE USA A MENUDO COMO EXCUSA para omitir la investigación empírica**, ya que es muy difícil identificar observaciones generales.

> ⚠️ **Cruce con la cátedra.** *"Ejemplos de juguete"* es una crítica que vale tener presente: **mostrar que una técnica funciona en un caso armado no prueba que funcione en uno real.**
>
> Es la misma advertencia que atraviesa varios capítulos de la serie: en el capítulo 4, las técnicas de priorización que fallan cuando pasás de 20 a 100 requisitos; en el capítulo 12, la observación de que casi no hay **investigación descriptiva** —sobre cómo se hace realmente— frente a mucha investigación prescriptiva sobre cómo debería hacerse.

---

## 2. Las siete estrategias de investigación 🟡

Vale conocerlas porque **nombran cosas que ya viste hacer en la serie**, y porque distinguirlas ayuda a leer cualquier estudio.

| Estrategia | Qué hace |
|---|---|
| **Relevamiento** (*survey*) | **Junta datos —típicamente en retrospectiva— de una muestra representativa**, mediante entrevistas o cuestionarios, **y trata de generalizarlos a toda la población** |
| **Experimento** | Se hace **en un entorno de laboratorio**, donde sujetos específicos se asignan a tratamientos distintos y se mide su desempeño. **El objetivo es manipular variables específicas y controlar todas las demás** |
| **Estudio de casos** | Junta datos **a lo largo de un período sostenido** —típicamente monitoreando proyectos— y trata de **entender en más detalle un factor específico y su relación con otros** |
| **Teoría fundamentada** | Emplea **múltiples etapas de recolección de datos de grupos distintos**, para **maximizar similitudes y diferencias** y comparar los datos con categorías emergentes |
| **Etnografía** | Se enfoca en **datos de observación recolectados en un entorno natural**, sobre un grupo cultural intacto |
| **Investigación narrativa** | **Estudia las vidas de individuos** y reorganiza la información en una cronología narrativa |
| **Investigación fenomenológica** | **Estudia las experiencias vividas de un número CHICO de sujetos** para identificar la esencia de esas experiencias respecto de un fenómeno |

> ⚠️ **Cruce con la cátedra.** Dos de estas ya las viste en acción: **la etnografía** en el capítulo 2 (observar el trabajo real en su entorno) y **la fenomenológica** en el capítulo 15 (entrevistar a unos pocos jefes de proyecto para extraer la esencia de su experiencia).
>
> Y el capítulo 18 usó **estudio de casos** más **teoría fundamentada** en su método inductivo.

### Los tres tipos de estudio combinado 🟢

| | Se basa en | Usa | Emplea |
|---|---|---|---|
| **Cuantitativos** | Afirmaciones pospositivistas | Relevamientos y experimentos | **Preguntas predeterminadas y cerradas, análisis numérico** |
| **Cualitativos** | Perspectivas constructivistas | Las otras cinco estrategias | **Preguntas emergentes y abiertas, análisis no numérico** |
| **Métodos mixtos** | Afirmaciones pragmáticas | Múltiples estrategias | Múltiples métodos de recolección y análisis |

---

## 3. Los tres propósitos posibles 🔴

Esta distinción es corta y muy usable:

| Tipo de estudio | Qué intenta |
|---|---|
| **Descriptivo** | **ENTENDER QUÉ SE HACE**, en general o sobre una práctica específica. Por ejemplo: si se usa una herramienta, cómo se lleva a cabo la captura de requisitos, o qué impacto tiene la volatilidad sobre el éxito del proyecto |
| **Prescriptivo** | **HACER UN JUICIO.** Apunta a identificar prácticas exitosas, o factores de éxito y obstáculos para una práctica específica. También se lo llama **explicativo**, porque **trata de identificar las RAZONES de las acciones** |
| **Prospectivo** | **IDENTIFICAR NECESIDADES FUTURAS** de la industria |

**Y una distinción transversal:**

> Pueden distinguirse dos direcciones generales: por un lado los estudios exploran **el estado de la práctica** —qué está haciendo la práctica— y por otro exploran más específicamente **la relación entre el estado del arte y el estado de la práctica** — es decir, **QUÉ SABE LA PRÁCTICA SOBRE LA INVESTIGACIÓN.**

> ⚠️ **Cruce con la cátedra.** Esa segunda dirección es interesante y poco frecuente: **no medir qué hace la industria, sino cuánto conoce de lo que se investiga.**
>
> Vas a ver en la Parte 2 que ese es uno de los hallazgos más reveladores: **hay técnicas con evidencia positiva que casi nadie usa**, y la razón parece ser simplemente que no se las conoce.

---

## 4. El tamaño de la muestra y qué permite 🔴

Una regla metodológica que vale:

> **Claramente, UNA MUESTRA CHICA NO ES ADECUADA PARA ESTUDIOS PRESCRIPTIVOS en general, ya que pocos puntos de datos no pueden demostrar la generalidad necesaria. Lo mismo vale para la BAJA HETEROGENEIDAD de trasfondos y contextos de los participantes.**

**Pero con un matiz honesto:**

> Por otro lado, **es muy difícil, PARTICULARMENTE EN INGENIERÍA DE REQUISITOS, identificar principios que apliquen a todo tipo de entorno.**

**Y dos salidas prácticas:**

```
   · hacer un estudio CHICO con el objetivo de ser
     prescriptivo SOLO PARA LA POBLACIÓN INVOLUCRADA
     (dar consejo a esas empresas, no al mundo)

   · usar un enfoque MULTI-ETAPA: empezar con un estudio
     chico y DESCRIPTIVO para entender el tema, y después
     involucrar a muchos participantes para establecer
     principios generales en un estudio PRESCRIPTIVO
```

> ⚠️ **Cruce con la cátedra.** La primera salida es exactamente lo que hizo el capítulo 18: **seis empresas, conclusiones prescriptivas para esas seis, y una advertencia explícita de que puede no generalizarse.** Es una manera honesta de sacar valor de una muestra chica.
>
> Y aplica a un TP: **si relevás un solo negocio, tus conclusiones valen para ese negocio.** Presentarlas como si valieran en general es un error que se nota.

---

## 5. Los tres mecanismos de captura 🟡

| Mecanismo | Qué es | Cuándo conviene |
|---|---|---|
| **Cuestionarios** | **Una lista predeterminada de preguntas abiertas o cerradas.** Se distribuyen en línea o por correo, o **pueden llenarse conjuntamente entre entrevistador y entrevistado** | **Para muestras grandes son mucho más fáciles de manejar** |
| **Interacción directa** | **La lista NO está completamente predeterminada; los participantes pueden influir sobre qué información se recoge.** Ejemplos: entrevista semi-estructurada, observación del trabajo. Para involucrar a más gente, un taller | **Da MÁS DETALLE Y MÁS INFORMACIÓN CONFIABLE**, porque pueden evitarse los malentendidos. Más adecuada para estudios descriptivos y prospectivos |
| **Datos de medición** | **Datos que NO se capturan específicamente para el estudio**, sino que están disponibles por un programa de medición o una evaluación | **Requiere el mayor esfuerzo**, y por eso a menudo no está disponible |

**Y sobre el análisis:**

> **Claramente, una muestra chica NO PERMITE análisis numérico válido, y una muestra grande NO PUEDE MANEJARSE con análisis no numérico.**

> ⚠️ **Cruce con la cátedra.** Notá la ventaja que se le atribuye a la interacción directa: **"pueden evitarse los malentendidos".**
>
> Es exactamente el argumento del capítulo 2 a favor de las entrevistas sobre los cuestionarios: en un cuestionario, si la pregunta se entiende mal, **nadie se entera**. En una entrevista, la confusión se ve y se corrige en el momento.

---

## 6. El catálogo de factores de contexto 🔴🔴

Esta es la sección más aprovechable de la Parte 1.

### Por qué importa

> **Para poder analizar datos de ingeniería de requisitos, ES IMPORTANTE ENTENDER EL CONTEXTO Y EL TRASFONDO de los participantes. Típicamente, LAS PRÁCTICAS DEPENDEN MUCHÍSIMO DE ESE CONTEXTO.**
>
> **Desafortunadamente NO HAY ESTÁNDARES sobre cómo capturar cada factor de contexto. ESO VUELVE MUY DIFÍCIL LA COMPARACIÓN entre estudios distintos.**

### 6.1 Contexto personal 🔴

Determina **el punto de vista del participante.**

| Faceta | Qué determina |
|---|---|
| **Región** | **El contexto cultural.** Varios estudios son de un solo país. Los autores señalan que **NINGÚN estudio de ingeniería de requisitos analizó explícitamente las diferencias culturales** hasta ese momento |
| **Rol actual** | **El punto de vista y la involucración en el proceso.** Roles típicos: **usuario, desarrollador, experto en calidad, jefe de proyecto, alta gerencia, consultor y académico** |
| **Experiencia profesional previa** | **Si el participante puede reportar solo intuiciones preliminares o experiencias sostenidas.** Puede medirse por años de experiencia o cantidad de proyectos. **Rara vez se lo captura** |

> ⚠️ **Cruce con la cátedra.** El factor **rol** es el más importante de los tres, y vas a ver en la Parte 2 un dato que lo confirma dramáticamente: **la estimación del uso de una práctica varió un 30 % según el rol del entrevistado.**
>
> O sea: **preguntarle a un jefe de proyecto y a un desarrollador sobre lo mismo da respuestas distintas.** No porque alguno mienta, sino porque ven partes distintas del proceso. Es la razón por la cual la triangulación del capítulo 18 usaba fuentes de proyecto **y** de línea.

### 6.2 Contexto de la empresa 🔴

| Faceta | Qué distingue |
|---|---|
| **Tamaño** | **La cantidad de empleados involucrados en desarrollo hace una gran diferencia.** La distinción principal es entre **pequeñas y medianas empresas y grandes**, donde el límite se asume típicamente en **500 empleados, a veces 100 o 300** |
| **Rubro** | Se distingue **industria primaria** —el software ES el negocio principal— de **industria secundaria** —el software es PARTE de un producto. Y el sector al que apunta: finanzas, público, telecomunicaciones, manufactura, transporte, logística, salud. Eso implica además **tipos de software**: sistemas de información o sistemas embebidos |

**Y una queja recurrente:**

> **Desafortunadamente NO HAY CATEGORÍAS ESTÁNDAR para el rubro ni para los tipos de software. Por lo tanto, LOS DATOS DE ESTUDIOS DISTINTOS NO PUEDEN COMPARARSE.**

### 6.3 Contexto del proyecto 🔴

A menudo se le pide al entrevistado **elegir un proyecto típico** para reportar.

| Faceta | Qué se registra |
|---|---|
| **Cliente / usuario** | **La relación cliente-proveedor tiene gran influencia.** Importa distinguir si el proyecto produce **software a medida o software comercial listo para usar.** Ortogonal a eso: **si el cliente es INTERNO O EXTERNO.** Además, **la cantidad de usuarios y las fuentes de los requisitos** |
| **Tamaño del proyecto** | **El tamaño de la empresa NO determina el del proyecto.** Este se mide por **cantidad de personal, cantidad de meses-persona y duración.** Otra característica importante: **cuál es la restricción principal — presupuesto, tiempo o calidad** |
| **Software** | **El tamaño del software NO SIEMPRE COINCIDE con el del proyecto.** Importa el **tamaño del código y la CANTIDAD DE REQUISITOS.** El precio del software **rara vez se captura**. También: plataforma, cantidad de variantes, nivel de confiabilidad requerido |

> ⚠️ **Cruce con la cátedra.** Este catálogo de tres niveles —persona, empresa, proyecto— es un buen recordatorio de **cuánta información hace falta para que un dato signifique algo.**
>
> Cuando leas *"el 60 % de las empresas tiene un proceso definido de requisitos"*, esa cifra **no te sirve** hasta saber: ¿empresas de qué tamaño? ¿de qué rubro? ¿desarrollan a medida o para mercado? ¿el cliente es interno o externo?
>
> Y aplica también en la otra dirección: **si en un TP describís un negocio, esos son los datos que hay que dar** para que cualquier decisión posterior se pueda evaluar.

---

## 7. Qué preguntar sobre el proceso 🟡

### Los hechos generales

```
   · ¿EXISTE un proceso de requisitos definido?
     además: adherencia a ciertos paradigmas o ciclos
     de vida, y si existe UN ROL RESPONSABLE de las
     actividades de requisitos
     + el TAMAÑO de la definición del proceso
     + EN QUÉ MEDIDA se lo cumple realmente

   · el ALCANCE DE LA DOCUMENTACIÓN, que es un indicador
     importante del nivel de detalle del proceso

   · el DESEMPEÑO: esfuerzo, herramientas, características
     del equipo, y conocimiento o uso de prácticas
     establecidas
     → el esfuerzo puede medirse PARA TODO EL PROCESO
       o POR ACTIVIDAD
     → y además de preguntar porcentajes, puede preguntarse
       SI LAS ACTIVIDADES SE REALIZAN IMPLÍCITA O
       EXPLÍCITAMENTE
```

**Y una advertencia sobre el vocabulario:**

> **La terminología específica de la ingeniería de requisitos ES UN PROBLEMA acá** —para documentos y actividades— **ya que los desarrolladores a menudo USAN SU PROPIA TERMINOLOGÍA.**

> ⚠️ **Cruce con la cátedra.** Dos cosas para llevarse:
>
> **1. Preguntar si una actividad se hace implícita o explícitamente** es más fácil de responder que preguntar cuánto esfuerzo lleva, y da información parecida. Es una buena idea de diseño de encuesta.
>
> **2. El problema de la terminología es el mismo del glosario**, ahora en el nivel de investigar sobre el proceso: **si preguntás "¿hacen validación?" y el otro llama a eso de otra manera, la respuesta va a estar mal** — y nadie se va a enterar.

### Cómo se mide el éxito 🔴

Y acá viene algo útil. **El éxito de un proyecto** puede medirse por **seis variables:**

```
   · SATISFACCIÓN DEL CLIENTE
   · CUMPLIMIENTO de los requisitos
   · COSTO dentro del presupuesto
   · DURACIÓN dentro del cronograma
   · PRODUCTIVIDAD del personal
   · MORAL del personal
```

**Y la primera se desglosa:** puede medirse a través de **aptitud para el uso, facilidad de uso, y la cantidad de defectos reportados por el cliente.**

**Sobre la calidad de los productos de requisitos** —que es más difícil:

> Por la diversidad de actividades **es aún más difícil medir la calidad de los productos y servicios de la ingeniería de requisitos.** Existe **una lista validada empíricamente de 34 criterios**, que puede usarse **para dos propósitos: como INSTRUMENTO DE MEDICIÓN del éxito, y como LISTA DE VERIFICACIÓN de las características importantes de un buen proceso.**

> ⚠️ **Cruce con la cátedra.** Notá que **la moral del personal** figura entre las seis variables de éxito de un proyecto. Es una medida que casi nunca se toma y que el capítulo 15 mencionaba como **costo social**: resistencia, rotación, ausentismo.
>
> Y el doble uso de la lista de criterios —medir *y* servir de lista de verificación— es el mismo patrón que ya viste en la rúbrica: **lo que sirve para evaluar sirve para guiar.**

---

## Mapa de la Parte 1

```
   LA CRÍTICA DE ARRANQUE
   la mayor parte de la investigación en ingeniería de
   software usa EJEMPLOS DE JUGUETE, que no demuestran
   nada sobre la práctica

   ─────────────────────────────────────────────

   7 ESTRATEGIAS DE INVESTIGACIÓN
   relevamiento · experimento · estudio de casos ·
   teoría fundamentada · ETNOGRAFÍA (cap. 2) ·
   narrativa · FENOMENOLÓGICA (cap. 15)

   3 PROPÓSITOS
   DESCRIPTIVO (qué se hace) · PRESCRIPTIVO (juzgar,
   explicar por qué) · PROSPECTIVO (qué va a hacer falta)

   y 2 direcciones: qué HACE la práctica ·
   qué SABE la práctica sobre la investigación

   ─────────────────────────────────────────────

   MUESTRA CHICA → no sirve para conclusiones generales
   PERO sí para dar consejo A ESA POBLACIÓN
   (es lo que hizo el cap. 18)

   ─────────────────────────────────────────────

   ══► LOS FACTORES DE CONTEXTO ◄══
   sin ellos, un número NO SIGNIFICA NADA

   PERSONAL ─► región (cultura) · ROL (¡el que más pesa!)
               · experiencia previa
   EMPRESA ──► tamaño (el corte suele ser 500 empleados)
               · rubro: ¿el software ES el negocio o es
                 PARTE de un producto?
   PROYECTO ─► cliente: ¿a medida o para mercado?
                        ¿INTERNO o EXTERNO?
               · tamaño · restricción principal:
                 presupuesto, tiempo o calidad
               · cantidad de REQUISITOS

   problema declarado: NO HAY CATEGORÍAS ESTÁNDAR
   → los estudios NO SE PUEDEN COMPARAR entre sí

   ─────────────────────────────────────────────

   MEDIR EL ÉXITO — 6 variables
   satisfacción del cliente · cumplimiento de requisitos
   · costo · duración · productividad · MORAL DEL PERSONAL
```

---

## Preguntas para chequear que quedó

1. ¿Qué crítica hacen los autores al estado de la investigación en ingeniería de software?
2. ¿Qué excusa se usa para omitir la investigación empírica?
3. Nombrá las siete estrategias de investigación y decí qué hace cada una.
4. ¿Cuáles dos de esas estrategias ya viste usar en otros capítulos de la serie y dónde?
5. Diferenciá estudios cuantitativos, cualitativos y de métodos mixtos.
6. Nombrá los tres propósitos posibles de un estudio y qué intenta cada uno.
7. ¿Cuáles son las dos direcciones generales que pueden explorar los estudios?
8. ¿Por qué una muestra chica no sirve para un estudio prescriptivo?
9. ¿Cuáles son las dos salidas prácticas para sacar valor de una muestra chica?
10. Nombrá los tres mecanismos de captura de datos y cuándo conviene cada uno.
11. ¿Qué ventaja tiene la interacción directa sobre el cuestionario? ¿Con qué argumento del capítulo 2 se conecta?
12. ¿Por qué es tan importante registrar los factores de contexto?
13. ¿Qué problema causa que no haya estándares para capturar el contexto?
14. Nombrá las tres facetas del contexto personal. ¿Cuál pesa más y por qué?
15. ¿Cuál es el corte típico entre pequeña/mediana y gran empresa?
16. Diferenciá industria primaria de secundaria en cuanto al software.
17. Nombrá las tres facetas del contexto de proyecto.
18. ¿Por qué el tamaño de la empresa no determina el del proyecto?
19. ¿Qué información hace falta para que la cifra "el 60 % tiene proceso definido" signifique algo?
20. ¿Qué ventaja tiene preguntar si una actividad se hace implícita o explícitamente, en vez de preguntar el esfuerzo?
21. ¿Qué problema plantea la terminología al investigar sobre procesos de requisitos?
22. Nombrá las seis variables con que puede medirse el éxito de un proyecto.
23. ¿Cuáles son los dos usos posibles de una lista de criterios de calidad?

---

**FIN DEL CAPÍTULO 19 — PARTE 1**

*Sigue en la Parte 2: la evidencia acumulada — cuánto se usa cada práctica, los tres problemas que se repiten desde 1986, los factores de éxito, y el estudio propio de los autores.*
