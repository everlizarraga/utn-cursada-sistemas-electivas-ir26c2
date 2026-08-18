# Lectura en español — Cap. 15 · Parte 1: Qué hace distintos a los sistemas web

> **Origen.** Capítulo 15, secciones 15.1 y 15.2, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Jacob L. Cybulski y Pradip K. Sarkar**, Universidad Deakin, Australia.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.

---

## Aviso sobre este capítulo

El tema —metodologías de desarrollo web de principios de los 2000— está fechado y no toca tu cronograma.

**Pero la Parte 2 tiene una de las mejores ideas de todo el libro**, que es la distinción entre **problema** e **incumbencia** (*concern*), y un hallazgo empírico que vale la pena: **los interesados no se resisten a los requisitos, se resisten a las CONSECUENCIAS de los requisitos.** Eso reencuadra la resistencia de una manera muy usable.

Esta primera parte prepara el terreno: por qué los sistemas web plantean un problema distinto, y por qué las metodologías existentes no lo resolvían.

---

## 1. Qué hace distintos a estos sistemas 🟡

> **Se afirma a menudo que los sistemas de información basados en web tienen un proceso de desarrollo bastante distinto del de los sistemas de software tradicionales. La IDENTIFICACIÓN DE REQUISITOS es una de las etapas donde esa diferencia es especialmente pronunciada.**

### La variedad de propósitos 🟢

Se identifican **cuatro tipos mayores** de sistema web:

```
   · entregar PUBLICIDAD y promoción
   · asistir FLUJOS DE TRABAJO del negocio
   · facilitar la interacción ENTRE ORGANIZACIONES
   · soportar COMERCIO MULTI-PARTICIPANTE
```

Y cada tipo **enfatiza aspectos distintos del diseño según su propósito**: algunos se enfocan en transacciones entre empresas o en asistir al cliente; otros en **promover la marca, construir confianza y credibilidad de mercado**; otros simplemente acentúan **contenidos, disposición, navegación y búsqueda** de información organizacional.

### Lo que arrastra al ingeniero de requisitos 🔴

Y acá viene lo que vuelve el problema distinto:

> **Las preferencias y deseos del cliente van MUCHO MÁS ALLÁ de la función y el rendimiento del sistema: tocan la organización del negocio y sus alianzas, las interacciones entre organizaciones, el flujo de suministros y productos, la presencia del negocio y el acceso a los clientes.**
>
> **En todo ese pantano de negocio y sistema, LAS CUESTIONES DE COMERCIALIZACIÓN se vuelven factores dominantes que impactan el diseño del sitio — frecuentemente POR DELANTE DE SU FUNCIÓN.** Eso incluye estilo y esquema de colores, tipografía, impresión gráfica y multimedia, accesibilidad, internacionalización y personalización.

### El equipo se agranda 🔴

Y con eso se agranda la lista de participantes:

> **Aparte de los interesados obvios del proyecto —patrocinadores, clientes y usuarios— las partes involucradas incluyen también:** desarrolladores de contenido y consultores de derechos de autor, especialistas en comercialización y relaciones públicas, planificadores de medios y estrategas, directores creativos y de arte, diseñadores gráficos, desarrolladores de multimedia e interacción, **y muchísimos otros, que los ingenieros de requisitos NO SUELEN CONSIDERAR como aportantes a la especificación de un sistema de software tradicional.**

### Dónde están los conflictos 🔴

> **Que los interesados sostengan opiniones en conflicto es bien conocido por la comunidad de IR. En estos sistemas, sin embargo, esos conflictos están firmemente incrustados NO SOLO en las necesidades del software a desarrollar, sino más bien EN LOS PROCESOS Y OBJETIVOS DE NEGOCIO de compradores y vendedores en línea, Y EN LAS RESTRICCIONES impuestas por las agencias que regulan las transacciones financieras o determinan el cumplimiento de las leyes del país y de los tratados internacionales.**

> ⚠️ **Cruce con la cátedra.** Esa observación es más profunda de lo que parece. En un sistema tradicional, el conflicto entre interesados está **dentro del sistema** — dos personas quieren funcionalidades incompatibles. Acá **el conflicto ya existía en el negocio antes de que apareciera el software**, y el sistema simplemente lo hace visible.
>
> Conecta con el capítulo 7: allí se decía que el conflicto es **estructural, no accidental**, porque los interesados tienen intereses distintos. Este capítulo lo lleva un paso más lejos: **algunos conflictos ni siquiera son de los interesados presentes — son del sector, o de la regulación.**

---

## 2. La paradoja del tiempo 🔴

Y acá está el problema central que enmarca todo el capítulo.

**Por un lado, el alcance de lo que hay que considerar se agrandó muchísimo.** Por el otro:

> **El ciclo de entrega para aplicaciones web es comúnmente MUY CORTO —menos de tres meses— lo que deja MUY POCO TIEMPO para cualquier recolección formal de requisitos y su consolidación.**

**Y ese tiempo que falta es justamente el que haría falta:**

> **El marco de tiempo adecuado, tan ausente en estos sistemas, es sin embargo CRÍTICO para lidiar con la enorme diversidad de usuarios**, en términos de sus ubicaciones geográficas, trasfondo cultural y lingüístico, competencia informática, **y conocimiento variable de las reglas de negocio.**

```
   ALCANCE de lo que hay que considerar ──► GRANDÍSIMO
   TIEMPO disponible para considerarlo ───► < 3 meses

              → la elicitación formal no entra
```

**La crítica que recoge el capítulo:**

> El proceso de recolección de requisitos tal como se practica es **largamente inadecuado para el desarrollo web**, y les falla a los analistas **en la identificación y caracterización de los usuarios potenciales, sus necesidades y preferencias, y las funcionalidades requeridas.**

---

## 3. El prototipado y su costo 🔴

Dado ese contexto, el desarrollo **se apoya comúnmente en un enfoque de prototipado por pasos**, con un proceso iterativo de diseño, prototipado y evaluación, que involucra actividades desde exploración y refinamiento hasta producción, implementación, lanzamiento, mantenimiento y descubrimiento.

**Y el balance, dicho sin adornos:**

> **Si bien el desarrollo basado en prototipos resulta en un tiempo más corto al mercado, POR EL USO DE MÉTODOS IMPROVISADOS Y NO ESTRUCTURADOS TAMBIÉN LLEVA A UNA CALIDAD POBRE de los sistemas y servicios web, y en última instancia resulta en UNA GRAN CANTIDAD DE USUARIOS INSATISFECHOS.**

> ⚠️ **Cruce con la cátedra.** Ese es un contrapunto directo al capítulo 14. Allí el prototipado y la iteración corta aparecían como virtud; **acá aparecen como la causa de la mala calidad.**
>
> Y la diferencia está en una palabra: **"improvisados y no estructurados".** Lo ágil pide iteraciones cortas **con prácticas disciplinadas**; lo que este capítulo describe son iteraciones cortas **sin ninguna práctica**. No es lo mismo iterar que no haber planificado.

**Y el vacío que el capítulo viene a llenar:**

> **Pocos de los enfoques metodológicos establecidos arrojan luz sobre CÓMO los requisitos podrían afinarse y evolucionar a lo largo de las distintas etapas del prototipado para mejorar la calidad.**

---

## 4. Las cinco metodologías 🟢

El capítulo repasa cinco propuestas metodológicas de la época. Vale leerlas rápido: **lo importante no es cada una, sino qué le falta a todas.**

### 4.1 Ingeniería web

> Argumenta que **el desarrollo web debería reconocerse como un PROCESO con toda su estructura y complejidad, y no apenas como un evento atómico**, que es como lo consideran muchos profesionales.

Sus fundadores enfatizan **seguir un proceso donde funcionalidad y recursos de información se agregan iterativamente con el tiempo**, y sostienen que **la mayoría de las dificultades actuales con sitios web grandes se atribuyen a la falta de modelos de proceso adecuados** para que los equipos sigan.

**Dos aportes que el capítulo destaca:**

- **Los usuarios podrían tratarse como parte integral del sistema.** Al desarrollarlos, es esencial **tener medidas incorporadas al proceso que permitan atender las cuestiones relacionadas con el usuario.**
- **El reconocimiento de la importancia de que los equipos MEJOREN APRENDIENDO DE LA EXPERIENCIA.**

### 4.2 Metodología de gestión de relaciones 🟢

Siete pasos, de los cuales **los primeros tres se enfocan en cuestiones de diseño** usando diagramas de entidad-relación.

**Sus dos problemas:**

> **Si bien reconoce la importancia del análisis de requisitos, ARROJA POCA LUZ SOBRE SUS MECANISMOS.** Además, **los pasos que prescribe requieren un nivel alto de habilidades técnicas especializadas**, lo que puede no ser un factor motivador para su adopción.

### 4.3 La metodología de Howcroft 🟡

La más completa en cobertura. Su fase de análisis:

```
   1. análisis exhaustivo de la estrategia web y
      competitiva de la organización
   2. definición de los OBJETIVOS o necesidades de
      negocio a cumplir
   3. ANÁLISIS DE INTERESADOS
   4. análisis de información: qué información estática
      y dinámica requieren los usuarios objetivo
   5. análisis de las habilidades de los miembros del
      proyecto (comúnmente multidisciplinarias)
   6. ANÁLISIS DE USUARIOS ← el elemento más crítico
      + análisis de riesgos del proyecto
```

Sobre el paso 6:

> **El elemento más crítico es el análisis de usuarios, que en su mayor parte es un proceso complejo en sí mismo, ya que los usuarios pretendidos tienen que identificarse y hay que analizar sus necesidades y características POR ADELANTADO.**

**Su límite:**

> **Pese a su cobertura exhaustiva de objetivos organizacionales, necesidades de negocio y necesidades de usuario, la metodología NO PROPONE NINGÚN MEDIO CONCRETO de cómo los desarrolladores podrían incorporar las cuestiones de los interesados a su trabajo.**

### 4.4 Metodología de desarrollo de comercio en internet 🟡

Esta es la más interesante de las cinco, porque **combina análisis de negocio con desarrollo de sistemas.**

> Se sostiene que **las metodologías tradicionales cubren solo los aspectos MÁS TÉCNICOS del desarrollo y NO MIRAN LOS ASPECTOS DE NEGOCIO.** El comercio por internet **es uno de esos campos que necesitan actividad de negocio intensa como parte del desarrollo**, y por lo tanto requiere un análisis exhaustivo de su lugar en la estrategia general.

**Cómo involucra a los clientes** —esto es lo aprovechable:

```
   · aporte del cliente ESENCIAL en las etapas de
     desarrollo de estrategia y análisis de negocio
   · puede involucrar EQUIPOS DE INVESTIGACIÓN DE
     MERCADO para saber qué requieren los clientes
     y cuáles son las BARRERAS POTENCIALES al uso de
     la web
   · requisitos más detallados: SESIONES GRUPALES DE
     REQUISITOS, entrevistas telefónicas o cuestionarios
   · los clientes evalúan cuestiones de diseño mediante
     PROTOTIPOS
   · se los incluye en las pruebas y la evaluación
   · se obtiene retroalimentación una vez que el sitio
     está EN VIVO
```

**Las dos técnicas de recolección que usa:**

| Técnica | Para qué |
|---|---|
| **Tormenta de ideas** | **Definir maneras alternativas de encarar el comercio por internet** |
| **Sesiones grupales de requisitos** | **Obtener los requisitos detallados en un marco de tiempo relativamente rápido**, con participación de clientes, proveedores y personal interno |

**Y una recomendación organizacional que vale:**

> Las organizaciones que emprenden negocios electrónicos **deberían fomentar entornos de aprendizaje que permitan a los ejecutivos "aprender" de los éxitos y fracasos de OTRAS organizaciones que ya adoptaron esos negocios.** Eso exige invertir en programas de capacitación.
>
> **De hecho, un emprendimiento web NO VA A TENER ÉXITO si a los usuarios no se les da capacitación en el uso del sistema.**

**Su límite:** aunque reconoce la importancia de los interesados y del aprendizaje por experiencia, **no es prescriptiva sobre ningún modelo o proceso específico donde esas cuestiones puedan abordarse.**

### 4.5 Metodología de desarrollo de sistemas de información web 🟢

Es **la aplicación de una metodología PRE-WEB al desarrollo de aplicaciones web**, con el objetivo de evaluar si eso funciona.

Empieza con un análisis exhaustivo de la organización que aloja el sistema. **En palabras del autor: "el objetivo general del análisis organizacional es la consideración de CÓMO SE VA A CREAR VALOR".**

**Su límite:**

> **En su forma actual de definición, NO ESTABLECE NINGUNA RECOMENDACIÓN EXPLÍCITA sobre la identificación y el análisis de los interesados y sus puntos de vista.**

---

## 5. Qué le falta a todas 🔴

La comparación es la parte útil de la sección.

**Lo que comparten:**

- **Todas menos una consideran el contexto organizacional un aspecto primordial.**
- **En general el desarrollo es ITERATIVO E INCREMENTAL.**
- **La importancia de las cuestiones de los interesados SE RECONOCE en la mayoría.**

**Y el hueco, que es unánime:**

> **Sin embargo, NINGUNO DE LOS ENFOQUES INCORPORA EXPLÍCITAMENTE LAS CUESTIONES DE LOS INTERESADOS al proceso de implementación.**

**Y una observación honesta sobre por qué:**

> Los enfoques discutidos, **al ser metodologías, son naturalmente PRESCRIPTIVOS, incluso al punto de poder ERIGIR OBSTÁCULOS para equipos que trabajan en condiciones muy estresantes y complejas.**
>
> **Evitar esos obstáculos podría ser la razón por la que las metodologías revisadas no tratan la cuestión de los interesados de una manera muy estructurada — y por lo tanto restrictiva.**

> ⚠️ **Cruce con la cátedra.** Esa explicación es interesante y aplica más allá del contexto web: **una metodología demasiado prescriptiva no se usa.** Los autores no acusan a las metodologías de descuido; sugieren que **dejaron el tema abierto a propósito**, porque estructurarlo lo habría vuelto rígido.
>
> Es el mismo problema que atraviesa toda la serie desde otros ángulos: en el capítulo 13, las empresas que pedían "herramientas simples para necesidades básicas"; en el capítulo 10, la simplicidad como elección deliberada porque **lo simple se adopta**. La tensión entre rigor y adopción es real y no tiene solución fácil.

---

## 6. Los ocho hechos 🔴

El capítulo cierra la sección con una lista de hallazgos. Los primeros seis describen el contexto; los últimos dos son los que más valen.

```
   · estos sistemas se ADQUIEREN de proveedores, para
     habilitar por web flujos de trabajo intra e
     inter-organizacionales
   · se desarrollan o configuran INCREMENTALMENTE, con
     prototipado evolutivo
   · se agregan funcionalidades nuevas en cada iteración
   · el marco de tiempo es MUY CORTO: unos 3 meses
   · una base DIVERSA Y AMPLIA de interesados son los
     usuarios potenciales, pero NO SIEMPRE ES POSIBLE
     ANTICIPAR los grupos que la componen
   · los interesados son EXTERNOS y por lo tanto están
     MÁS ALLÁ DEL CONTROL del iniciador del proyecto
```

**Y el séptimo, que es el más fuerte de todos:**

> **Debido a esos grupos de interesados grandes, heterogéneos y no anticipados, los requisitos para aplicaciones web A MENUDO SE "CREAN DESDE CERO", EN VEZ DE ELICITARSE.**

**El octavo:**

> **La existencia de un mecanismo que permita a los equipos APRENDER DE LA EXPERIENCIA PASADA puede ayudar al establecimiento de los requisitos.**

> ⚠️ **Cruce con la cátedra — el séptimo punto es el importante.** *"Se crean desde cero en vez de elicitarse"* es una afirmación fuerte, y hay que leerla con lo que sabés del capítulo 2.
>
> Recordá que allí se decía que **elicitar no es recolectar**: hay elementos de **descubrimiento, emergencia e INVENCIÓN**. Y que un giro más reciente hablaba de **"inventar" y "crear" requisitos** para destacar el papel de la creatividad. El capítulo 13 decía lo mismo desde el mercado: los requisitos **"se inventan"** por tirón del mercado o empuje de la tecnología.
>
> Este capítulo lo dice sin eufemismos: **cuando no sabés quiénes son tus usuarios, no hay a quién elicitarle.** Y si tu sistema asignado es una plataforma masiva, estás exactamente ahí — **lo que hagas va a ser, en parte, invención informada, y conviene declararlo como tal en vez de disfrazarlo de elicitación.**

### Los cuatro huecos declarados 🔴

Lo que las metodologías existentes **no cubren adecuadamente**:

```
   1. IDENTIFICACIÓN Y DESCRIPCIÓN de los interesados
      y sus necesidades

   2. LIDIAR con las necesidades e incumbencias expresadas
      por una base de interesados diversa y relativamente
      grande

   3. EL IMPACTO de esas necesidades e incumbencias sobre
      las funcionalidades del sistema

   4. EXPLICACIÓN de cómo las necesidades de los distintos
      usuarios potenciales se incorporan a la evolución
      posterior de los servicios
```

Esos cuatro huecos **son lo que motiva la investigación empírica** que se presenta en la Parte 2.

---

## Mapa de la Parte 1

```
   POR QUÉ SON DISTINTOS
   · las preferencias del cliente van MÁS ALLÁ de función
     y rendimiento: tocan negocio, alianzas, regulación
   · la COMERCIALIZACIÓN domina el diseño, a menudo POR
     DELANTE de la función
   · el equipo incluye gente que la IR tradicional no
     considera: contenidos, derechos de autor, marketing,
     diseño gráfico, multimedia
   · los conflictos están incrustados EN EL NEGOCIO Y LA
     REGULACIÓN, no solo en el sistema

   ─────────────────────────────────────────────

   ══► LA PARADOJA DEL TIEMPO ◄══
   alcance a considerar: ENORME
   tiempo disponible: MENOS DE 3 MESES
   → no entra la elicitación formal
   → se prototipa de manera improvisada
   → tiempo al mercado corto PERO calidad pobre y
     usuarios insatisfechos

   ─────────────────────────────────────────────

   5 METODOLOGÍAS, 1 HUECO COMÚN
   todas RECONOCEN la importancia de los interesados
   NINGUNA la incorpora EXPLÍCITAMENTE al proceso
   posible razón: estructurarla las volvería rígidas,
   y una metodología rígida NO SE USA

   ─────────────────────────────────────────────

   ══► EL HALLAZGO CLAVE ◄══
   los interesados son EXTERNOS, y sus grupos NO SE
   PUEDEN ANTICIPAR
   → los requisitos "SE CREAN DESDE CERO,
     EN VEZ DE ELICITARSE"
```

---

## Preguntas para chequear que quedó

1. Nombrá los cuatro tipos mayores de sistema de información basado en web.
2. ¿Por qué las preferencias del cliente en estos sistemas van más allá de función y rendimiento?
3. ¿Qué factor domina a menudo el diseño, incluso por delante de la función?
4. Nombrá cinco participantes del equipo que la IR tradicional no suele considerar.
5. ¿Dónde están incrustados los conflictos en estos sistemas, a diferencia de un sistema tradicional?
6. Explicá la paradoja del tiempo. ¿Cuánto dura el ciclo de entrega típico?
7. ¿Por qué el marco de tiempo adecuado es especialmente crítico en estos sistemas?
8. ¿Cuál es el balance del desarrollo basado en prototipos: qué gana y qué pierde?
9. ¿Qué palabra del capítulo marca la diferencia entre este prototipado y el del capítulo 14?
10. ¿Qué aporta la ingeniería web como enfoque?
11. ¿Cuáles son los dos problemas de la metodología de gestión de relaciones?
12. En la metodología de Howcroft, ¿cuál es el elemento más crítico y por qué es complejo?
13. ¿Qué crítica hace la metodología de comercio por internet a las metodologías tradicionales?
14. Nombrá las dos técnicas de recolección que usa esa metodología y para qué sirve cada una.
15. ¿Por qué un emprendimiento web no va a tener éxito sin capacitación de usuarios?
16. ¿Qué comparten todas las metodologías revisadas y qué le falta a todas?
17. ¿Cuál es la explicación que dan los autores de por qué ninguna estructura el tema de los interesados?
18. ¿Por qué no siempre es posible anticipar los grupos de interesados?
19. ¿Qué significa que los requisitos "se crean desde cero en vez de elicitarse"? ¿Con qué ideas de los capítulos 2 y 13 se conecta?
20. Nombrá los cuatro huecos que las metodologías no cubren adecuadamente.

---

**FIN DEL CAPÍTULO 15 — PARTE 1**

*Sigue en la Parte 2: el análisis de interesados, la distinción entre problema e incumbencia, y el modelo de evolución de requisitos dirigida por incumbencias — con el hallazgo de que los interesados no se resisten a los requisitos sino a sus consecuencias.*
