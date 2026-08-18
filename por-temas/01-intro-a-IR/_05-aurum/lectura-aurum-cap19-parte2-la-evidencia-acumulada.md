# Lectura en español — Cap. 19 · Parte 2: Qué sabemos después de veinte años

> **Origen.** Capítulo 19, secciones 19.4 a 19.7, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Barbara Paech, Tom Koenig, Lars Borner y Aybüke Aurum**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1.** Se asume conocido el marco de factores de contexto.

---

## Lo que hay acá

**La evidencia acumulada de más de veinte relevamientos.** Y trae dos cosas que valen mucho:

1. **Los tres problemas que se repiten desde 1986** — identificados en el primer estudio del campo y confirmados una y otra vez durante veinte años.
2. **Los datos de adopción de cada práctica** — cuánta gente usa casos de uso, prototipos, inspecciones, y cuánta no. Con algunos números que sorprenden.

---

## 1. Los hechos generales 🔴

### ¿Hay proceso definido? 🟡

La evolución a lo largo del tiempo:

```
   1992 ──► solo unos pocos
   2000 ──► 50 %
        ──► ~30 % para pequeñas y medianas empresas
   2002 ──► 60 % en general
```

**Y un dato curioso que los autores destacan:**

> **Interesantemente, EL 70 % DE LAS EMPRESAS SIN PROCESO ESTÁN CONFORMES con la calidad de sus productos de requisitos.**

> ⚠️ **Cruce con la cátedra.** Ese dato es incómodo y vale pensarlo: **estar conforme y estar bien no es lo mismo.** La gente que no tiene proceso no percibe lo que se está perdiendo, porque **nunca vio la comparación.**
>
> Es el mismo mecanismo del capítulo 11: las ambigüedades no detectadas **no generan quejas** — generan acuerdo aparente. Y del capítulo 17: un proceso que **no aborda** una calidad no produce reclamos, produce silencio.

### El esfuerzo que lleva 🔴

Los pocos datos disponibles:

| Medida | Valor |
|---|---|
| **Esfuerzo dedicado a requisitos** | **14 %** del esfuerzo total en un estudio, **15,7 %** en otro |
| **Duración del proyecto** dedicada a requisitos | **38,6 %** |
| **Esfuerzo IDEAL estimado** | **15 a 30 %** en un contexto; **25 %** en otro |

**Y la distribución del esfuerzo en los equipos exitosos:**

```
   11 % del esfuerzo del proyecto en ELICITACIÓN
   10 % en MODELADO
    7 % en VALIDACIÓN Y VERIFICACIÓN
```

> ⚠️ **Cruce con la cátedra.** Fijate en el contraste entre las dos primeras filas: **los requisitos consumen el 14-16 % del ESFUERZO pero el 38,6 % de la DURACIÓN.**
>
> Eso significa que **la fase de requisitos es larga pero poco intensiva** — mucho tiempo de calendario con poca gente trabajando. Y tiene sentido: gran parte del tiempo se va esperando reuniones, esperando respuestas, esperando que la gente esté disponible.
>
> Es exactamente el problema que ya viste dos veces: el **ciclo de retroalimentación** de tu materia (el foro responde en la clase siguiente) y el hallazgo del capítulo 11 de que **las dudas hay que levantarlas apenas aparecen**, porque el tiempo de espera es el cuello de botella.

### Los sobrecostos 🔴

| Estudio | Sobrecosto | Sobre-tiempo |
|---|---|---|
| Uno | Poco costo | **Significativo tiempo** |
| Otro | **35 %** | **44 %** |
| El informe más conocido, 2003 | **43 % de los proyectos** con sobrecosto | **82 % con sobre-tiempo** |

> El patrón es consistente: **el tiempo se desborda mucho más que el presupuesto.**

### Tamaño del equipo y herramientas 🟡

**Tamaño promedio del equipo de requisitos:** **6,2** en un estudio, **7** en otro.

**Sobre las herramientas:**

> **El uso de herramientas de requisitos NO ESTÁ DIFUNDIDO: típicamente prevalecen las herramientas de propósito general.** Incluso para pequeñas y medianas empresas, **solo el 30 % usa un procesador de texto estándar, y las herramientas comerciales de requisitos NO SE USAN EN ABSOLUTO.**
>
> Otro estudio encontró **30 % usando solo procesadores de texto, pero para proyectos grandes, mayormente herramientas de requisitos.** Y más recientemente, **un 29 % de uso de herramientas de trazado.**

### La importancia reconocida 🔴

> **La ingeniería de requisitos se identifica MUY A MENUDO como contribuyente mayor a los problemas:** la especificación de requisitos y la gestión de requisitos del cliente **exhiben la mayor cantidad de problemas** en un estudio. Similarmente, **los problemas de requisitos tuvieron la participación MÁS ALTA —48 %— entre los problemas de desarrollo mencionados** en otro.

**Y los datos de percepción:**

```
   · el 80 % de las pequeñas y medianas empresas
     encuentra a la IR DE IMPORTANCIA ESTRATÉGICA
   · el 70 % indica QUE NO SE DEDICA SUFICIENTE TIEMPO
     a los requisitos  ← reconfirmado en dos estudios
```

**Y una evolución positiva** en las tasas de éxito de proyectos informáticos en general:

```
   1994 ──► 16 % de proyectos exitosos
   1998 ──► más del 26 %
   2003 ──► 34 %
```

> ⚠️ **Cruce con la cátedra.** El 70 % que dice que no se dedica suficiente tiempo a los requisitos es un dato notable: **la gente que hace el trabajo sabe que se está apurando.** No es que no entiendan el valor — es que el proceso no les da el espacio.
>
> Y notá que **la tasa de éxito subió de 16 % a 34 % en nueve años.** Sigue siendo baja, pero se duplicó.

---

## 2. Los tres problemas que no cambian 🔴🔴

Esta es la parte más importante del capítulo. **El primer estudio del campo, de 1986, identificó tres problemas — y se confirmaron una y otra vez durante veinte años.**

### Problema 1 — El conocimiento del dominio está mal repartido

> **Distribución delgada del conocimiento del dominio de aplicación.**

Confirmado en varios estudios, **particularmente para proyectos dirigidos por el mercado.** También aparece como **"habilidades inapropiadas"** en otro relevamiento.

### Problema 2 — Requisitos que fluctúan y se contradicen

> **Requisitos fluctuantes y en conflicto.**

Aparece con nombres distintos según el estudio:

```
   · "gestionar la incertidumbre"
   · "requisitos iniciales vagos, crecimiento de los
      requisitos, complejidad de la aplicación"
   · "completitud, gestión del cambio y trazabilidad"
     ← los problemas principales en un estudio
```

### Problema 3 — Se rompen la comunicación y la coordinación 🔴

> **Rupturas de comunicación y coordinación.**

Y este es el que más manifestaciones tiene:

```
   · participación del usuario y capacidades de gestión
     del proyecto
   · LOS PROBLEMAS DE PROCESO ORGANIZACIONAL SON DOS
     TERCIOS de los problemas relacionados con requisitos
   · comunicación entre desarrolladores · recursos
     inadecuados · RETENCIÓN DEL PERSONAL · comunicación
     con el usuario
   · la INDEFINICIÓN del propio proceso de requisitos
   · identificación de las FUENTES de requisitos
   · y en un estudio, "comunicación" fue EL problema
     principal
```

> ⚠️ **Cruce con la cátedra — esto es lo más citable del capítulo.** Tres problemas, identificados en 1986, **confirmados durante veinte años por estudios independientes en países distintos.**
>
> Y notá qué son: **ninguno es técnico.** Son *no saber lo suficiente del negocio*, *que las cosas cambien*, y *que la gente no se entienda*. Ninguna herramienta los resuelve.
>
> Fijate además en el dato de que **dos tercios de los problemas de requisitos son de proceso organizacional**, no de contenido. Es la misma conclusión a la que llegaba el capítulo 12 (*lo político pesa tanto como lo técnico*), el capítulo 15 (*el papel se corre de gestionar requisitos a gestionar interesados*) y el capítulo 2 (*la IR es un proceso social*).
>
> **Cinco capítulos, cinco equipos, la misma conclusión.** Si hay una tesis en todo el libro, es esta.

### Los otros dos problemas típicos 🟡

**Herramientas.** Son un problema porque **los beneficios no están claros**, y por cuestiones de **integración, selección y adaptación** de herramientas.

**Documentación.** **A menudo NO EXISTE.** Y si existe, el problema es **gestionarla**, o el nivel de detalle del modelo funcional, o la priorización, o **la falta de plantilla.**

---

## 3. Los factores de éxito 🔴

La lista más refinada que encontraron se estructura en **cinco áreas.**

### 3.1 Adecuación de la solución recomendada

```
   cultura de cambio · adecuación estratégica ·
   apoyo de la gerencia al cambio · adecuación al
   negocio y a la tecnología
```

### 3.2 Satisfacción y compromiso del usuario 🔴

```
   ADHESIÓN del usuario · CONSENSO del usuario ·
   adecuación al TRABAJO del usuario ·
   adecuación de la PRIMERA VERSIÓN
```

**Confirmado además por:** participación del usuario y relaciones del equipo.

### 3.3 Calidad de la arquitectura de requisitos 🔴

```
   procesos de negocio CLAROS · requisitos CORRECTOS ·
   VÍNCULOS desde los objetivos hacia los modelos ·
   casos de negocio VÁLIDOS
```

**Y los factores relacionados que identificó otro estudio** — esta lista es muy aprovechable:

```
   · COBERTURA de las fuentes de requisitos
   · uso de PLANTILLAS
   · PRIORIZACIÓN
   · COMBINACIÓN de prototipos y modelos
   · MATRIZ DE TRAZABILIDAD
   · REVISIONES POR PARES con usuarios
   · ESCENARIOS
   · RECORRIDOS (walkthroughs)
```

**Y otro estudio agrega**, para proyectos con poco tiempo al mercado: **especificación no ambigua** y **priorización**; y para los que no tienen esa presión: **gestión del cambio.**

### 3.4 Calidad del análisis costo-beneficio 🟡

```
   apoyo de la gerencia · alta prioridad de negocio ·
   estimaciones precisas de beneficios y costos
   INCLUSO PARA LOS BENEFICIOS INTANGIBLES
```

### 3.5 Costo-efectividad del proceso 🟡

```
   comparado con proyectos similares y con el esfuerzo
   total del proyecto · POCO CAMBIO ·
   UTILIDAD DE LOS ENTREGABLES
```

**Y la observación de los autores sobre toda la lista:**

> **Esta lista muestra que, AL IGUAL QUE CON LOS PROBLEMAS, MUCHOS FACTORES SON ORGANIZACIONALES.**

### El hallazgo sobre participación del usuario 🔴🔴

Y acá viene un resultado muy fino:

> Se investigó la relación entre **participación del usuario, incertidumbre y éxito.**
>
> **Encontraron que EN PRESENCIA DE INCERTIDUMBRE la participación del usuario MEJORA** las dos primeras categorías, **y a la inversa: LA PARTICIPACIÓN DEL USUARIO TIENE MENOS IMPACTO SI LA INCERTIDUMBRE ES BAJA.**

> ⚠️ **Cruce con la cátedra — este hallazgo es sutil y muy útil.** No dice *"involucrá siempre al usuario"*. Dice algo más preciso: **la participación del usuario rinde EN PROPORCIÓN A LA INCERTIDUMBRE que haya.**
>
> Cuando ya sabés bien qué hay que hacer, sumar al usuario aporta poco. **Cuando no sabés, es lo que más aporta.** Y eso da un criterio para asignar esfuerzo: **poné al usuario donde más dudas tenés**, no repartido parejo.
>
> Conecta con el capítulo 18: allí la empresa Alfa —donde el cliente sabía exactamente lo que quería— podía omitir prácticas de clarificación **legítimamente**, y el método de evaluación lo contemplaba como *"satisfecha-explicada"*. Es el mismo principio.

### ¿La ingeniería de requisitos hace diferencia? 🔴

Los resultados acumulados:

```
   · adoptar prácticas de requisitos tiene IMPACTO
     POSITIVO SOBRE LA PRODUCTIVIDAD del proyecto
     en empresas grandes
   · los problemas de requisitos SE REDUCEN en niveles
     de madurez más altos
   · el impacto principal son METAS Y ALCANCE COMUNES
   · una ESPECIFICACIÓN FUNCIONAL MÁS COMPLETA AUMENTA
     LA PRODUCTIVIDAD (medida en código producido por día)
```

**Y un matiz importante sobre ese último punto:**

> Sin embargo, el mismo estudio encontró que **LA INCOMPLETITUD DE LA ESPECIFICACIÓN PUEDE COMPENSARSE mediante técnicas que generan RETROALIMENTACIÓN TEMPRANA sobre el desempeño del producto, como PROTOTIPOS O PRUEBAS.**

> ⚠️ **Cruce con la cátedra.** Ese matiz es la conciliación entre el enfoque documental y el ágil: **no hay una sola manera de resolver la incompletitud.** O especificás más, o generás retroalimentación más rápido. **Las dos funcionan; lo que no funciona es ninguna de las dos.**

---

## 4. Qué prácticas se usan realmente 🔴🔴

Esta sección tiene los datos más concretos del capítulo.

### En pequeñas y medianas empresas 🔴

```
   solo el 33 % tiene ESTRUCTURA DE DOCUMENTO ESTÁNDAR
   aún MENOS usa un lenguaje de modelado como estándar
   los MÉTODOS FORMALES NO SE USAN NUNCA
   los ESCENARIOS SE USAN RARA VEZ
   los requisitos SE NUMERAN solo en el 15 % de
     las empresas
   solo un cuarto usa más que marginalmente las diez
     prácticas principales recomendadas
```

> ⚠️ **Cruce con la cátedra.** *"Los requisitos se numeran solo en el 15 % de las empresas"* es un dato que da perspectiva. **Numerar requisitos es la cosa más simple que se puede hacer** — es el prerrequisito de toda trazabilidad — **y el 85 % no lo hace.**

### El uso de técnicas 🔴

Los porcentajes de adopción:

| Técnica | Adopción |
|---|---|
| **Prototipado** | **60 %** |
| **Inspecciones** | **59 %** |
| **Escenarios o casos de uso** | **50 %** |
| Análisis orientado a objetos | 30 % |
| Grupos focales | 30 % |
| Modelado informal | 30 % |
| **Modelos formales** | **7 %** — y solo en empresas grandes |

**Y dos observaciones más:**

> **Los escenarios y casos de uso son LA PRÁCTICA MÁS CONOCIDA** en uno de los estudios.
>
> **La adherencia a procesos muy tradicionales también se confirma por el hecho de que EL 35 % DE LAS EMPRESAS TODAVÍA USA CASCADA.**

**Y una hipótesis sobre por qué no se adoptan más técnicas:**

> Eso puede seguir estando relacionado con **CONOCIMIENTO FALTANTE, ya que LAS TÉCNICAS CONOCIDAS TIENEN MÁS PROBABILIDAD DE PERCIBIRSE COMO ÚTILES.**

> ⚠️ **Cruce con la cátedra.** Esa hipótesis es la respuesta a la pregunta que abría el capítulo 18 (*¿la industria usa lo que la teoría propone?*): **no, y la razón principal parece ser que no lo conoce.**
>
> Y hay un círculo vicioso: **una técnica que no conocés no te parece útil, y una que no te parece útil no la aprendés.** Por eso los autores señalan como pregunta pendiente **por qué los escenarios se adoptaron ampliamente y otras técnicas con evidencia positiva no.**

### La variación entre contextos 🔴

Y acá viene el hallazgo metodológico más importante:

> **Los estudios grandes encontraron que LA ADOPCIÓN DE BUENAS PRÁCTICAS VARÍA ENORMEMENTE:**

```
   · el uso estimado de prácticas VARIÓ UN 30 % SEGÚN
     EL ROL del entrevistado
   · variación de prácticas de gestión DEL 65 % AL 32 %
     ENTRE PAÍSES, y del 60 % al 36 % ENTRE SECTORES
     de negocio — observado en tres estudios consecutivos
   · variación DE HASTA EL 70 % ENTRE PAÍSES para una
     práctica específica de desarrollo
```

**Pero con un matiz:**

> En ese último estudio **LA IMPORTANCIA RELATIVA de las distintas prácticas NO VARIÓ MUCHO.** Por ejemplo, **crear una especificación funcional era una de las prácticas más adoptadas EN TODOS LOS PAÍSES.**

> ⚠️ **Cruce con la cátedra — el primer dato es el que más te sirve.** *"El uso estimado de prácticas varió un 30 % según el rol del entrevistado"* significa que **preguntarle a un jefe de proyecto y a un desarrollador sobre lo mismo da respuestas distintas en un 30 %.**
>
> No porque alguno mienta. **Porque ven partes distintas del proceso.** El jefe sabe qué está definido; el desarrollador sabe qué se hace realmente.
>
> Es la justificación empírica de la **triangulación** del capítulo 18 y de la **lectura por perspectivas** del capítulo 8: **una sola fuente te da una versión, y la versión depende de dónde está parado el que habla.**

### Qué querría la gente de una técnica nueva 🔴

Preguntados por las características principales que debería tener una técnica nueva:

```
   · FÁCIL DE USAR
   · que FACILITE LA BUENA COMUNICACIÓN
   · requisitos COMPLETOS
   · TRAZABILIDAD
```

> Notá que **"fácil de usar" está primero.** Es la misma constatación del capítulo 10 (la simplicidad como elección deliberada porque **lo simple se adopta**) y del capítulo 13 (las empresas pedían *"herramientas simples para necesidades básicas"*).

---

## 5. Hallazgos sobre temas específicos 🟡

Estudios en profundidad sobre fenómenos puntuales. Los más relevantes:

### Sobre el contenido de los documentos 🔴

> **Los documentos de requisitos deberían enfocarse en el QUÉ Y EL CÓMO, ya que eso es lo que LOS DISEÑADORES QUIEREN SABER. Típicamente quieren saber CÓMO UN USUARIO VA A REALIZAR SU TAREA con la funcionalidad del sistema.**
>
> **Esa importancia se mantuvo estable en entornos de empresa muy distintos.**

> ⚠️ **Cruce con la cátedra — este hallazgo es incómodo y hay que leerlo con cuidado.** Aparentemente contradice la regla de "qué, no cómo".
>
> **Pero no la contradice: la precisa.** El "cómo" que los diseñadores quieren **no es cómo lo implementa el sistema** —eso sí es decisión de diseño— sino **cómo el usuario lleva a cabo su tarea usando el sistema.** Eso es el flujo del caso de uso, y es exactamente lo que un caso de uso describe.
>
> La distinción, entonces, es: **el cómo DEL USUARIO va en los requisitos; el cómo DEL SISTEMA es diseño.**

### Sobre la trazabilidad 🔴

> **Es un problema por FALTA DE DEFINICIÓN COMÚN y por PRE-TRAZABILIDAD INADECUADA.** Lo último se debe a problemas **para los proveedores** de información de trazabilidad —el trabajo extra— **y para los usuarios** de esa información — **la dependencia de la comunicación personal.**

**Y un dato de escala:** **el 60 % son usuarios intensivos de trazabilidad, con más de 10.000 requisitos** y esquemas elaborados.

### Sobre la volatilidad de los requisitos 🔴

Este es el hallazgo más denso y vale la pena entero:

```
   la volatilidad consiste en: INESTABILIDAD +
   FALTA DE ANALIZABILIDAD + DIVERSIDAD

   se relaciona con:
     · el TAMAÑO de los requisitos
     · el COSTO del proyecto
     · y MUY SIGNIFICATIVAMENTE, LA DEMORA del proyecto

   la CAPACIDAD DEL DESARROLLADOR tiene impacto NEGATIVO
   sobre la volatilidad
   la volatilidad NO TIENE RELACIÓN con la calidad del
   código ni con la calidad de la gestión

   ══► ALTA VOLATILIDAD SE RELACIONA CON FALTA DE
       SATISFACCIÓN DEL CLIENTE ◄══

   INDUCEN volatilidad:  una metodología definida ·
                         comunicación frecuente con
                         el usuario · inspecciones
   REDUCEN volatilidad:  los REPRESENTANTES de usuarios
```

> ⚠️ **Cruce con la cátedra — leé de nuevo las dos últimas líneas, que son contraintuitivas.**
>
> **La comunicación frecuente con el usuario y las inspecciones INDUCEN volatilidad.** Eso suena a que serían malas prácticas — pero no: **inducen volatilidad porque ENCUENTRAN COSAS.** Cada conversación y cada inspección descubre un requisito que estaba mal o faltaba, y eso se registra como un cambio.
>
> Es exactamente **la paradoja de la volatilidad** del capítulo 4: elicitar bien hace pensar a la gente, y eso les cambia lo que quieren. **La volatilidad que ves es la que detectaste; la que no ves te espera más adelante.**

### Sobre casos de uso y escenarios 🔴

> **Pueden usarse de muchas maneras distintas. Son PARTICULARMENTE ÚTILES EN COMBINACIÓN CON PROTOTIPADO Y GLOSARIOS.**
>
> **Ayudan a complementar los modelos dinámicos y estáticos abstractos, a REDUCIR LA COMPLEJIDAD, y a ALCANZAR ACUERDO Y CONSISTENCIA PARCIALES.**
>
> **Las cuestiones problemáticas son:** vistas parciales, gestionar el desarrollo distribuido de escenarios, revisiones, derivación de casos de prueba, trazabilidad y evolución.

> ⚠️ **Cruce con la cátedra.** *"Particularmente útiles en combinación con prototipado y glosarios"* es un hallazgo empírico que le da respaldo a algo que la serie viene diciendo desde ángulos distintos: **los casos de uso no se bastan solos.**
>
> Necesitan el glosario para que los términos signifiquen lo mismo (capítulos 8, 10, 11, 17) y el prototipo para que el usuario pueda evaluar algo concreto (capítulo 8).

### Sobre la documentación 🟡

Para qué se la necesita, en orden:

```
   · APRENDER sobre el software ............... 61 %
   · PROBAR el software ....................... 58 %
   · trabajar con software nuevo .............. 54 %
   · responder preguntas ante problemas ....... 50 %
   · mantenimiento ............................ solo 35 %
```

**Y dos observaciones:**

> **La documentación de alto nivel ES ÚTIL INCLUSO CUANDO ESTÁ DESACTUALIZADA.**
>
> **Los requisitos se actualizan MENOS FRECUENTEMENTE que toda otra documentación, mientras que la documentación de pruebas es la que MÁS se actualiza.**

### Sobre las revisiones 🔴

```
   · las revisiones de requisitos son ligeramente más
     comunes (42 %) que las de diseño (49 %) entre las
     empresas que tienen documentación
   · A MENUDO (60 %) LOS REVISORES NO TIENEN TIEMPO
     DE PREPARARSE
   · cuando hay tiempo, las LISTAS DE VERIFICACIÓN (50 %)
     son más comunes que lo improvisado (35 %)
   · SOLO EL 25 % RECOLECTA DATOS durante la revisión
     y los usa para mejorar
```

> ⚠️ **Cruce con la cátedra.** *"El 60 % de los revisores no tiene tiempo de prepararse"* explica por qué las revisiones rinden menos de lo que podrían.
>
> Recordá del capítulo 8: **si se saltea la preparación individual, la inspección se degrada a un recorrido** — una reunión donde se discute, no una detección sistemática. Y del capítulo 11: un equipo de tres preparados encuentra el doble que uno solo.
>
> **La revisión sin preparación no es una revisión más barata: es otra cosa.**

---

## 6. El resumen de la evidencia 🔴

Los autores destilan lo aprendido, y el punto principal es metodológico:

> Los estudios **confirman que EL DESEMPEÑO DEL PROCESO Y LA ADOPCIÓN DE PRÁCTICAS VARÍAN MUCHÍSIMO entre empresas distintas.**
>
> Por lo tanto, **NO PARECE VÁLIDO GENERALIZAR LOS RESULTADOS CUANTITATIVOS —los porcentajes— encontrados en UN estudio A TODAS LAS EMPRESAS. Eso solo puede hacerse sobre la base de un análisis cuidadoso DE TODOS LOS FACTORES DE CONTEXTO.**

**Pero los resultados cualitativos sí muestran tendencias:**

```
   · un proceso de requisitos definido SE ENCUENTRA MÁS
     A MENUDO HOY que en estudios anteriores
   · muchos estudios establecen LA IMPORTANCIA de la IR:
     puntúa alto entre los problemas Y se estableció su
     impacto positivo sobre la productividad
   · LOS PROBLEMAS IDENTIFICADOS PARECEN BASTANTE
     ESTABLES: conocimiento del dominio mal repartido,
     requisitos fluctuantes y en conflicto, y rupturas
     de comunicación y coordinación
```

**Y una conexión con el capítulo anterior:**

> Como se discutió en el capítulo 18, **el primer problema ES MENOS PROBLEMÁTICO cuando las empresas se especializan en ciertos dominios. Los otros dos SÍ SE CONFIRMARON** en esos estudios.

---

## 7. El estudio propio 🟡

Los autores presentan datos nuevos de Alemania y Australia, para ilustrar los problemas de interpretar este tipo de estudios.

### Los tres estudios combinados 🟢

```
   · un PRE-ESTUDIO en Alemania (1999): nueve entrevistas
     de dos horas
   · un CUESTIONARIO en línea con devolución personalizada:
     33 empresas alemanas
   · CUATRO ESTUDIOS EN PROFUNDIDAD en Australia:
     11 empresas multinacionales, 23 proyectos
     (banca, farmacéutica, salud, telecomunicaciones,
      alimentación)
```

**Y un detalle que los autores destacan:** **por casualidad, los tres estudios tuvieron contextos de empresa muy distintos** —uno con dos tercios de empresas de más de 10.000 empleados, otro con dos tercios de menos de 100— **y juntos dan una variedad muy buena: 20 % en cada franja de tamaño.**

### Lo que encontraron 🔴

**Sobre el proceso:**

```
   · el 72 % tenía un ESTÁNDAR de proceso
   · esos estándares tienen largo considerable:
     en el estudio australiano TODOS pasaban las 6 páginas
     y dos tercios pasaban las 25
   · casi todas las empresas confirman que EL PROCESO REAL
     SE ADHIERE al estándar
   · MÁS DE LA MITAD tiene un ROL EXPLÍCITO responsable
     de requisitos
```

**Sobre las actividades** —y acá usaron la idea de preguntar por explícito/implícito en vez de por esfuerzo:

> **Elicitación, documentación, y verificación y validación son casi igualmente importantes.** Pero **mirando las actividades explícitas de cada estudio por separado, SE VE UNA ALTA VARIACIÓN.** Las pequeñas y medianas empresas **no realizan tantas actividades explícitamente.**
>
> **En todos los estudios, TODA empresa tiene AL MENOS UNA actividad explícita.**

**Sobre los documentos:** los de **requisitos del cliente y requisitos del desarrollador son los más populares, y SI SE CREA UNO, SE CREA EL OTRO.**

### El resultado negativo más interesante 🔴

Y acá viene un hallazgo que los autores reportan honestamente aunque no les guste:

> Investigamos la relación entre los factores de contexto y las características del proceso.
>
> **LA ÚNICA RELACIÓN SIGNIFICATIVA QUE ENCONTRAMOS fue entre EL TAMAÑO DEL PROYECTO y la cantidad de actividades realizadas explícitamente y la cantidad de roles involucrados. Esa relación es bastante obvia.**
>
> **Así que LOS FACTORES DE CONTEXTO LISTADOS NO SON SUFICIENTES para explicar la variedad de procesos.**

> ⚠️ **Cruce con la cátedra.** Ese resultado es valioso justamente porque es negativo: **construyeron un catálogo cuidadoso de factores de contexto y no alcanzó para explicar por qué las empresas hacen cosas tan distintas.**
>
> Lo que sugiere es que **la variación no viene del tamaño, el rubro ni el tipo de cliente — viene de algo que no midieron**: la historia de la empresa, quién la dirige, qué les salió mal antes. Es decir, **lo que el capítulo 12 llamaba factores no técnicos.**

### Los problemas encontrados 🔴

Preguntando **por rol** —una idea que los autores destacan como propia:

```
   · la ESTIMACIÓN DE COSTOS es un problema ...... 48 %
   · los requisitos NO SON ESTABLES .............. 45 %
   · LA NECESIDAD DE CAMBIO SE DETECTA
     DEMASIADO TARDE ............................ 42 %
   · la comunicación entre requisitos y diseño ... solo 33 %
```

**Y las pocas relaciones que sí pudieron establecer:**

```
   · crear MODELOS DE PROCESOS DE NEGOCIO reduce los
     problemas con el sistema terminado, y MEJORA LA
     COMUNICACIÓN entre el probador y el diseñador
   · la existencia de REQUISITOS DEL CLIENTE reduce
     los problemas DEL PROBADOR
   · la existencia de REQUISITOS DEL DESARROLLADOR
     reduce los problemas DE LOS DISEÑADORES y de los
     ingenieros de requisitos
```

> ⚠️ **Cruce con la cátedra.** *"La necesidad de cambio se detecta demasiado tarde"* (42 %) es un problema distinto de *"los requisitos no son estables"* (45 %), y la diferencia importa: **el problema no es solo que cambien — es no darse cuenta a tiempo.**
>
> Es exactamente lo que atacaba el análisis de impacto del capítulo 6 y la identificación de **requisitos volátiles** del capítulo 18, que resultó ser una de las seis carencias.

---

## 8. Recomendaciones y conclusión 🔴

### Tres observaciones metodológicas

```
   1. Los hechos sobre la práctica DEPENDEN MUCHÍSIMO
      DEL CONTEXTO → hay que capturarlo cuidadosamente
      e investigar su relación con lo observado

   2. Es DIFÍCIL EVALUAR EL PROGRESO EN EL TIEMPO porque
      los estudios usaron preguntas muy distintas
      → ayudaría que todos usaran un marco común

   3. HAY ALTO RIESGO DE MALENTENDIDOS en los cuestionarios
      estandarizados → AL MENOS DEBERÍA PROVEERSE
      UN GLOSARIO DE TÉRMINOS
```

> ⚠️ **Cruce con la cátedra.** La tercera recomendación cierra el círculo del capítulo: **hasta para preguntar sobre requisitos hace falta un glosario.**
>
> Es la séptima vez que la serie llega al glosario desde un lugar distinto — y esta es la más recursiva de todas: **el instrumento para estudiar la ambigüedad es él mismo ambiguo si no define sus términos.**

### La conclusión 🔴

> **NI EL ESTADO DE LA PRÁCTICA NI EL ESTADO DEL CONOCIMIENTO SOBRE LA PRÁCTICA SON SATISFACTORIOS.**
>
> **Hasta ahora NO ES POSIBLE llegar a números que caractericen uniformemente la adopción de prácticas. PERO HAY HALLAZGOS REPETIDOS SOBRE PROBLEMAS Y FACTORES DE ÉXITO.**

**Y las preguntas que dejan abiertas:**

```
   · dado el amplio consenso sobre los problemas,
     PARECE HORA DE ESTUDIAR ESOS PROBLEMAS EN DETALLE
   · como hay menos evidencia sobre factores de éxito,
     habría que hacer estudios para confirmarlos
   · ══► parece importante AVERIGUAR POR QUÉ UNA TÉCNICA
     COMO LOS ESCENARIOS SE ADOPTÓ AMPLIAMENTE, MIENTRAS
     OTRA NO SE ADOPTA A PESAR DE LA EVIDENCIA POSITIVA
     A SU FAVOR ◄══
   · integrar los estudios de la comunidad de sistemas
     de información, que se enfocan en REQUISITOS
     ESTRATÉGICOS y en el éxito medido como CAMBIO
     ESTRATÉGICO, frente a los de ingeniería de software,
     que se enfocan en requisitos MÁS OPERATIVOS
```

> ⚠️ **Cruce con la cátedra.** La tercera pregunta es la más interesante del capítulo y una buena manera de cerrarlo: **¿por qué algunas técnicas se adoptan y otras, con la misma o mejor evidencia, no?**
>
> Las pistas están repartidas por toda la serie: **lo simple se adopta** (capítulo 10), **lo que exige infraestructura no** (capítulo 18, las inspecciones), **lo que no se conoce no se percibe como útil** (este capítulo), **y lo demasiado prescriptivo erige obstáculos** (capítulo 15).
>
> Los casos de uso ganaron porque **tienen tres conceptos, se leen sin entrenamiento, y no requieren herramienta.** No porque sean los más potentes.

---

## Mapa de la Parte 2

```
   ══► LOS 3 PROBLEMAS QUE NO CAMBIAN DESDE 1986 ◄══
   1. conocimiento del dominio MAL REPARTIDO
   2. requisitos FLUCTUANTES Y EN CONFLICTO
   3. RUPTURAS de comunicación y coordinación
      → DOS TERCIOS de los problemas de requisitos son
        de PROCESO ORGANIZACIONAL, no de contenido

   ninguno de los tres es técnico

   ─────────────────────────────────────────────

   LOS NÚMEROS
   esfuerzo en requisitos: 14-16 % del ESFUERZO
                           38,6 % de la DURACIÓN
   sobrecosto 43 % de los proyectos · sobre-tiempo 82 %
   el 70 % dice que NO SE DEDICA SUFICIENTE TIEMPO
   el 70 % de los que NO tienen proceso ESTÁN CONFORMES

   ADOPCIÓN DE TÉCNICAS
   prototipado 60 % · inspecciones 59 % ·
   casos de uso 50 % · modelos formales 7 %
   los requisitos se NUMERAN en solo el 15 % de las PyME
   el 35 % todavía usa CASCADA

   ─────────────────────────────────────────────

   ══► EL DATO METODOLÓGICO ◄══
   el uso estimado de prácticas VARIÓ UN 30 % SEGÚN
   EL ROL del entrevistado
   → una sola fuente te da UNA VERSIÓN

   ─────────────────────────────────────────────

   HALLAZGOS FINOS
   · la participación del usuario rinde EN PROPORCIÓN
     A LA INCERTIDUMBRE
   · la incompletitud SE PUEDE COMPENSAR con prototipos
     o pruebas (no hay una sola salida)
   · comunicación frecuente e inspecciones INDUCEN
     volatilidad — porque ENCUENTRAN COSAS
   · los casos de uso son útiles EN COMBINACIÓN con
     prototipos y GLOSARIOS
   · el 60 % de los revisores NO TIENE TIEMPO DE
     PREPARARSE

   ─────────────────────────────────────────────

   LA PREGUNTA QUE DEJAN ABIERTA
   ¿por qué unas técnicas se adoptan y otras no,
   con la misma evidencia a favor?
```

---

## Preguntas para chequear que quedó

1. ¿Cómo evolucionó el porcentaje de empresas con proceso definido de requisitos?
2. ¿Qué porcentaje de las empresas sin proceso está conforme con su calidad? ¿Por qué ese dato es incómodo?
3. Compará el esfuerzo dedicado a requisitos con la duración. ¿Qué explica la diferencia?
4. ¿Cómo distribuyen el esfuerzo los equipos exitosos entre elicitación, modelado y validación?
5. ¿Qué se desborda más, el presupuesto o el cronograma?
6. Nombrá los tres problemas identificados en 1986 y confirmados durante veinte años.
7. ¿Qué tienen en común esos tres problemas?
8. ¿Qué proporción de los problemas de requisitos son de proceso organizacional?
9. Nombrá las cinco áreas de factores de éxito.
10. ¿Qué ocho factores identificó un estudio dentro de la calidad de la arquitectura de requisitos?
11. Explicá el hallazgo sobre participación del usuario e incertidumbre. ¿Qué criterio práctico da?
12. ¿Cómo puede compensarse la incompletitud de una especificación?
13. ¿Qué porcentaje de pequeñas y medianas empresas numera sus requisitos? ¿Por qué es un dato revelador?
14. Ordená por adopción: prototipado, inspecciones, casos de uso, modelos formales.
15. ¿Qué hipótesis dan sobre por qué no se adoptan más técnicas?
16. ¿Cuánto varió el uso estimado de prácticas según el rol del entrevistado? ¿Por qué pasa eso?
17. ¿Qué cuatro características debería tener una técnica nueva, según los profesionales?
18. Explicá el hallazgo sobre "el qué y el cómo" en los documentos. ¿Contradice la regla de "qué, no cómo"?
19. ¿Qué prácticas inducen volatilidad y cuál la reduce? ¿Por qué las que la inducen no son malas prácticas?
20. ¿Con qué se combinan mejor los casos de uso, según la evidencia?
21. ¿Para qué se usa más la documentación? ¿Y cuál se actualiza menos?
22. ¿Qué porcentaje de revisores no tiene tiempo de prepararse? ¿Qué consecuencia tiene?
23. ¿Por qué no se pueden generalizar los porcentajes de un estudio a todas las empresas?
24. ¿Cuál fue la única relación significativa que encontraron entre contexto y proceso? ¿Qué sugiere ese resultado negativo?
25. Nombrá los tres problemas más reportados en el estudio propio. ¿Por qué "el cambio se detecta tarde" es distinto de "los requisitos no son estables"?
26. ¿Cuál es la tercera recomendación metodológica y por qué es irónica?
27. ¿Cuál es la pregunta más interesante que dejan abierta? ¿Qué pistas hay en la serie para responderla?

---

**FIN DEL CAPÍTULO 19 — PARTE 2**

**FIN DEL CAPÍTULO 19**

*Sigue el capítulo 20: soluciones y tendencias — el cierre del libro, en 2 partes.*
