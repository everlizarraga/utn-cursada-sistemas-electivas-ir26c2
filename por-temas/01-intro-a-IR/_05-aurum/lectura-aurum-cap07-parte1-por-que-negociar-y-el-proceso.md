# Lectura en español — Cap. 7 · Parte 1: Por qué negociar y el proceso de negociación

> **Origen.** Capítulo 7, secciones 7.1 y 7.2, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Paul Grünbacher y Norbert Seyff**, Universidad Johannes Kepler de Linz, Austria.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.

---

## Por qué este capítulo te toca de cerca

La clase 05 de tu cronograma se titula, en parte, **"Rol del IR (mediador, documentador)"**, y su entregable es una **minuta de reunión de mediación**. El capítulo 2 te dijo *que* el ingeniero de requisitos hace de mediador y *por qué* el conflicto es inevitable.

**Este capítulo es el que explica cómo se media.** Es la teoría detrás de ese entregable, y es el único lugar del libro donde el tema se desarrolla en serio.

---

## 1. Por qué hace falta negociar 🔴

### El conflicto es estructural, no accidental

> **Los conflictos surgen casi inevitablemente, porque los interesados del proyecto —usuarios futuros, adquirentes, desarrolladores, mantenedores— persiguen frecuentemente metas que no coinciden.**

El capítulo da el mapa concreto de esas metas encontradas:

| Interesado | Qué le interesa típicamente |
|---|---|
| **Usuarios futuros** | Muchas funcionalidades · alto nivel de servicio · **disponibilidad temprana** |
| **Adquirentes** (quienes compran) | **Costo-efectividad** · cumplimiento de estándares · restricciones de presupuesto y cronograma |
| **Desarrolladores** | **Contratos flexibles** y **requisitos estables** |

```
   USUARIOS          ADQUIRENTES        DESARROLLADORES
   "más cosas"       "más barato"       "que no cambie"
   "y ya"            "y que cumpla       "y que el contrato
                      las normas"         me deje margen"
        └──────────────────┬──────────────────┘
                    NO PUEDEN CUMPLIRSE
                    LAS TRES A LA VEZ
```

Y una crítica al estado de la disciplina:

> **Aunque los estudios muestran que el conflicto es extenso en la ingeniería de software, muchos métodos existentes lo descuidan o no abordan explícitamente su manejo y resolución.**

### Qué es lo que la negociación produce realmente 🔴

Este párrafo vale por sí solo, porque corrige una expectativa ingenua:

> La ingeniería de software es un proceso altamente colaborativo, e identificar los intereses compartidos u opuestos es una necesidad para el éxito del proyecto. Los objetivos de clientes, usuarios y desarrolladores **tienen que entenderse y reconciliarse** para desarrollar acuerdos mutuamente aceptables.
>
> **Esto obviamente no significa que los interesados vayan a estar siempre de acuerdo. El resultado de la negociación es también entender POR QUÉ los interesados están en desacuerdo. Los desacuerdos identificados representan riesgos mayores y necesitan ser atendidos por la gestión del proyecto.**

> ⚠️ **Cruce con la cátedra.** Retené eso para la minuta de mediación: **una negociación que termina con un desacuerdo documentado y explicado no fracasó.** Produjo información — nombró un riesgo que antes estaba escondido. Lo que fracasa es la reunión que termina con un acuerdo aparente que en realidad tapa el desacuerdo.

### No es un episodio único 🔴

> **La negociación de requisitos no es un episodio de una sola vez en un proyecto: debería usarse desde temprano y repetirse en etapas posteriores.**

En cada ciclo hay que considerar **interesados nuevos y objetivos nuevos**, que a menudo llevan a negociaciones nuevas. En ciclos de vida iterativos, **los acuerdos alcanzados evolucionan hacia requisitos más detallados, planes de desarrollo, arquitecturas**.

**El propósito primario:** identificar y resolver conflictos entre interesados. Contribuye a la meta de **definir requisitos factibles y mutuamente satisfactorios** que acomoden todas las metas y expectativas.

---

## 2. Los siete beneficios de negociar 🔴

Más allá del propósito primario, la investigación y la evidencia de los profesionales muestran siete beneficios adicionales.

### 2.1 Entender las restricciones del proyecto

Los estudios muestran que los proyectos **fallan a menudo en cumplir restricciones críticas como presupuesto y cronograma**. **La negociación vuelve a los interesados conscientes de esas restricciones** y ayuda a encontrar soluciones para cumplirlas.

### 2.2 Adaptarse a los cambios

Por los cambios rápidos en la competencia del mercado, la tecnología y el personal, **los requisitos —y a veces incluso las restricciones— son altamente volátiles**. Los interesados quedan forzados a adaptarse frecuentemente.

**La negociación ayuda a lidiar con esos cambios más fácilmente**, porque los interesados **están al tanto de los problemas y alternativas existentes**. Y si un acuerdo queda obsoleto, **puede re-negociarse y revisarse**.

### 2.3 Fomentar el aprendizaje del equipo 🔴

Los distintos interesados llegan al proyecto con sus experiencias, trasfondos y expectativas, y traen sus metas a la mesa.

> **Desarrollar requisitos es un proceso cognitivo, en el que los interesados descubren colaborativamente qué hay que hacer** — entendiendo problemas y dominios, aprendiendo de los otros interesados, y negociando y discutiendo puntos de vista distintos.

Y el intercambio concreto que produce:

```
   DESARROLLADORES ────► aprenden más sobre el mundo del
                          cliente y del usuario

   CLIENTES Y USUARIOS ► aprenden más sobre qué es técnica
                          y económicamente FACTIBLE
```

> ⚠️ **Cruce con la cátedra.** Fijate que esto responde directamente a dos de los problemas del capítulo 2: la **brecha cultural** entre quien tiene el problema y quien lo resuelve, y el hecho de que los interesados **no conocen las consecuencias de sus requisitos ni saben qué es realista**. La negociación no es solo repartir; **es donde las dos partes se educan mutuamente**.

### 2.4 Sacar a la luz el conocimiento tácito 🔴

> **La gente sabe más de lo que puede llegar a decir.** Las metas tácitas de los interesados, los supuestos ocultos y las expectativas no dichas llevan a menudo a problemas en los proyectos. **La negociación ayuda a la gente a traer a la mesa esos temas y supuestos escondidos.**

> Este beneficio es el hermano del problema que viste en el capítulo 2 —lo trivial y repetido se da por sentado y no se menciona. La negociación lo desentierra por un mecanismo distinto de la entrevista: **cuando alguien tiene que defender su posición contra otra, se ve obligado a explicitar el supuesto sobre el que se para.**

### 2.5 Manejar la complejidad 🟡

Establecer requisitos está cargado de complejidad. **En un proyecto no trivial típico, con 10 o más interesados, hay que lidiar con cientos de metas individuales y decenas de problemas y alternativas** que hay que entender.

Otras fuentes de complejidad que menciona:

- **Interdependencias complejas** entre requisitos y entre requisitos y otros artefactos (el capítulo 5).
- **Desbordes cognitivos.**
- **Estrategias conflictivas de los negociadores.**
- **Intervenciones imprevistas de terceros.**

### 2.6 Lidiar con la incertidumbre 🔴

> **Especificar requisitos sin negociación es difícil, porque los usuarios no saben exactamente qué necesitan ni qué es tecnológicamente factible.**

**La negociación ayuda a reducir la incertidumbre** destacando las cosas que necesitan atención, **y fomenta una visión compartida** entre los interesados.

### 2.7 Encontrar mejores soluciones 🔴

Este es el más agudo de los siete:

> **Sin técnicas de negociación, los interesados a menudo intentan persuadir a los otros de aceptar una solución sugerida, en vez de buscar conjuntamente soluciones nuevas que sean beneficiosas para todas las partes.**

Y da el mecanismo concreto por el que se pierde calidad:

> **La principal desventaja de negociar los temas de manera secuencial es que los compromisos entre temas no pueden considerarse adecuadamente.** Las técnicas de negociación ayudan a **ver el cuadro completo en vez de tratar los temas uno por uno**, lo que ayuda a evitar soluciones subóptimas.

> ⚠️ **Cruce con la cátedra.** "Persuadir de aceptar una solución" contra "buscar conjuntamente una solución nueva" es la distinción que separa una reunión que funciona de una que no. Y el argumento sobre lo secuencial es útil: **si negociás punto por punto, nunca podés canjear** — "te doy este si me das aquel" requiere tener los dos sobre la mesa al mismo tiempo. Es un criterio concreto para diseñar una reunión de mediación.

### Las preguntas que quedan abiertas 🟡

Los beneficios son obvios, pero **establecer un proceso de negociación no es trivial**. Las cuestiones que hay que resolver:

```
   ¿Cómo se IDENTIFICAN los conflictos?
   ¿Cómo se RESUELVEN los conflictos identificados?
   ¿Cómo encuentran los interesados ALTERNATIVAS factibles?
   ¿QUIÉN está a cargo: los interesados o un facilitador?
   ¿Cómo se APOYA la negociación con herramientas u otros medios?
```

Y una nota sobre de dónde viene el conocimiento: la negociación de requisitos **puede aprovechar métodos y herramientas de una amplia gama de disciplinas**. Es una fase del proceso de toma de decisiones, y la negociación en decisiones grupales se investigó desde **teoría de la decisión, teoría de la administración y ciencias sociales, psicología organizacional y teoría de juegos**.

---

## 3. Qué es negociar: las definiciones 🔴

El capítulo revisa varias definiciones, y cada una enfatiza algo distinto. Vale verlas juntas.

**La visión tradicional:**

> **Negociación: las interacciones reales entre los participantes que llevan a un compromiso mutuo**, empezando **cuando los participantes comienzan a comunicar sus metas**, y terminando (exitosamente) **cuando todos acuerdan un contrato especificado**.

**La definición de Easterbrook**, que pone el foco en el conflicto:

> **Un enfoque colaborativo para resolver conflictos mediante la exploración del rango de posibilidades. Se caracteriza porque los participantes intentan encontrar un arreglo que satisfaga a todas las partes tanto como sea posible.**

Los autores hacen notar dos cosas de esta definición: **enfatiza el conflicto como la razón fundamental de la negociación**, y al decir "tanto como sea posible" **señala que la negociación involucra a menudo alguna clase de compromiso**.

**La definición desde la ingeniería de requisitos**, de Curtis y otros:

> **En términos generales, la negociación de requisitos puede verse como un proceso iterativo a través del cual los interesados hacen compromisos entre las funciones solicitadas del sistema, las capacidades de la tecnología existente o prevista, el cronograma de entrega y el costo.**

**Y la ampliación del alcance:** Robinson y Volkov argumentan que, más allá de la negociación propiamente dicha, **hay que considerar también las fases de pre-negociación y post-negociación** como parte del proceso — cubriendo actividades como el reconocimiento inicial del problema, la solicitación y comunicación de participantes, y el mantenimiento de la solución.

Esa visión más amplia es la que adopta el capítulo:

```
   PRE-NEGOCIACIÓN ──► NEGOCIACIÓN ──► POST-NEGOCIACIÓN
```

---

## 4. Etapa 1 — Pre-negociación 🔴

**Sus actividades:** definir el problema de negociación, identificar y convocar a los interesados, elicitar sus metas, y analizar esas metas para encontrar conflictos.

**Su resultado:** los **temas y conflictos** involucrados.

> **Un tema** (*issue*) es **un tópico de discusión de interés particular en una negociación. Cada tema tiene un rango de alternativas u opciones, una de las cuales debe finalmente ser acordada por los negociadores para lograr un compromiso.**

### 4.1 Definición del problema

Antes de que la negociación pueda empezar, hay que **identificar el problema analizando la situación y definiendo el propósito de la negociación**.

En un proyecto de software, el problema **depende tanto de los objetivos generales del proyecto como de la etapa actual**:

| Etapa | Qué se negocia |
|---|---|
| **Temprana** | **Temas de alto nivel** |
| **Posterior** | **Aspectos específicos o subproyectos** |

Y una observación que ya viste antes: **los requisitos reunidos en etapas tempranas expresan un rango más amplio de posibilidades en términos generales, y se vuelven más precisos después.**

**Por qué importa definir bien el problema:** es **esencial para identificar a los interesados y para ajustar el método y las técnicas** de negociación.

### 4.2 Identificación de los interesados 🔴

Hay que identificar a los **interesados críticos para el éxito**. Encontrar a las personas —o a los representantes apropiados— **cuyos intereses deben acomodarse** es a menudo una tarea desafiante en sí misma, pero es esencial.

Y acá viene la definición operativa más útil del capítulo:

> **Los interesados críticos para el éxito son las personas que pueden hacer acuerdos sobre los requisitos Y PUEDEN HACER QUE ESOS ACUERDOS SE SOSTENGAN.**

**Identificar a la gente correcta puede acelerar el proceso de negociación.**

> ⚠️ **Cruce con la cátedra.** Esa definición es un criterio de selección durísimo y muy útil. No alcanza con que alguien **tenga interés** en el sistema — para la mesa de negociación hace falta que **pueda comprometerse y sostener el compromiso**. Alguien que dice que sí y después no puede cumplirlo no es un interesado crítico: es una pérdida de tiempo y una fuente de conflicto futuro.
>
> Es una distinción fina respecto de la definición general de interesado del capítulo 1 (cualquiera que influya o sea influido). Todos esos son interesados; **solo algunos pueden sentarse a acordar**.

### 4.3 Elicitación de metas 🔴

Antes de poder identificar conflictos, los interesados **tienen que traer sus metas individuales a la mesa**.

> **Una meta es un objetivo que el sistema bajo consideración debería alcanzar.**

**Todos los interesados críticos** necesitan expresar **sus metas propias o las de la gente que representan**.

Y una observación sobre la forma que toman esas metas: según el problema identificado y las características del interesado —rol, conocimiento del dominio, experiencia— **las metas se formulan a distintos niveles de granularidad**:

```
   ALTO NIVEL ──► capacidades generales del sistema,
                  presupuestos, cronogramas
        │
        ▼
   BAJO NIVEL ──► preocupaciones técnicas como entornos
                  de desarrollo o plataformas objetivo
```

*(Las técnicas de elicitación y priorización de los capítulos 2 y 4 sostienen esta actividad.)*

### 4.4 Análisis de metas 🔴

Las metas elicitadas **se examinan para identificar conflictos**, analizando las metas y preferencias de los interesados. El ejemplo del capítulo: **puede haber conflicto entre el nivel de servicio que requieren los usuarios y las restricciones de presupuesto que imponen los adquirentes.**

**Cómo se hace, hoy:**

> **Identificar conflictos es típicamente un proceso manual, y depende del conocimiento y la pericia de los interesados involucrados y de las capacidades del facilitador.**

Y un beneficio lateral importante:

> **El análisis de metas no solo revela conflictos entre las metas de los interesados: típicamente revela también inconsistencias, riesgos, incertidumbres y supuestos ocultos.**

**Intentos de automatizarlo:** hay enfoques para identificar conflictos y cooperación entre requisitos **basados en atributos de software y trazabilidad automatizada**, y **técnicas de visualización sofisticadas** para identificar metas y requisitos en conflicto.

---

## 5. Etapa 2 — La negociación 🔴

Esta fase involucra **la conducción real de la negociación y la definición de los acuerdos**.

Sobre la base de las metas elicitadas y los conflictos identificados, **los interesados buscan soluciones mutuamente beneficiosas que sean aceptables para todas las partes**. La actividad consiste en:

- **estructurar los temas** y
- **desarrollar alternativas** para resolver los problemas — por ejemplo, **intercambiando ofertas y contraofertas**, o **proponiendo alternativas de ganancia mutua**.

Después de desarrollar las soluciones posibles, los interesados **eventualmente acuerdan la "mejor"**.

### El prerrequisito que casi siempre se olvida 🔴

Y acá viene el punto operativo más aprovechable de toda la sección:

> **La explicación de las soluciones posibles es un prerrequisito antes de que los interesados puedan acordar una decisión, y requiere el establecimiento de CRITERIOS DE JUICIO: un conjunto común de reglas acordado por todos los interesados.**
>
> **Si esas reglas faltan, los méritos de las distintas opciones van a ser inconsistentes.** Puede ser necesario, por lo tanto, **llevar a cabo una sesión de negociación preparatoria para acordar esos criterios de juicio.**

> ⚠️ **Cruce con la cátedra — usalo en la minuta.** Esto es de lo más aplicable que hay en el capítulo. **Antes de decidir entre opciones, hay que acordar con qué vara se van a medir.** Si no, cada uno evalúa las opciones con su propio criterio, todos creen estar comparando lo mismo, y el acuerdo que salga va a ser frágil.
>
> Es la misma lógica del capítulo 4 sobre por qué "importancia" a secas no sirve como aspecto de priorización, y por qué "alto/medio/bajo" confunde: **sin referente compartido, no hay comparación posible.**
>
> Y notá la consecuencia práctica: **puede hacer falta una reunión previa solo para acordar los criterios.** Eso es diseño de proceso, y es exactamente el tipo de decisión fundamentada que una corrección valora.

### Las estrategias disponibles 🔴

Según el tipo de conflicto y el problema en cuestión, pueden adoptarse **distintas estrategias**:

| Estrategia | En qué consiste |
|---|---|
| **Compromisos** (*trade-offs*) | Los interesados **ceden parcialmente en algunos temas para ganar en otros** — por ejemplo, haciendo concesiones para facilitar el acuerdo |
| **Resolución de problemas** | **Identificar y adoptar soluciones que satisfagan las metas de las partes** |
| **Persuasión** | **Convencer a otros negociadores de conceder** |
| **Abandono** | Aparentemente, los negociadores **también pueden decidir salirse de una negociación** |

---

## 6. Etapa 3 — Post-negociación 🔴

En esta fase los interesados —o herramientas automatizadas— **analizan y evalúan los resultados de la negociación y sugieren re-negociar si hace falta**.

**Qué se puede determinar:**

- **Si el acuerdo actual satisface las preferencias de las contrapartes**, y **si sería posible una solución mejor para una de las partes sin causar pérdida a la otra**.
- Puede involucrar además **revisiones de aseguramiento de calidad** de los resultados de la negociación.

### El aspecto que más se descuida 🔴

> **Otro aspecto importante de la post-negociación es asegurar el compromiso de los interesados a lo largo del tiempo** — por ejemplo, **monitoreando los acuerdos existentes e iniciando la re-negociación en caso de que queden obsoletos** por desarrollos nuevos.

Y en modelos de ciclo de vida iterativos:

> **Los resultados de la negociación necesitan evolucionar constantemente, ya que siempre pueden surgir metas nuevas que causen conflictos nuevos.** Entender los impactos de las metas cambiantes es típicamente no trivial (ver el capítulo 6).

> ⚠️ **Cruce con la cátedra.** "Asegurar el compromiso a lo largo del tiempo" le da función a la minuta más allá del registro. **Una minuta no documenta lo que se dijo: documenta a qué se comprometió cada uno**, y es el instrumento contra el cual se verifica después si el acuerdo sigue vigente. Eso conecta con el rol de documentador del capítulo 2 y con la trazabilidad del capítulo 5 — la minuta es la fuente que preserva la decisión y su justificación.

---

## Mapa de la Parte 1

```
   EL CONFLICTO ES ESTRUCTURAL
   usuarios (más y ya) vs adquirentes (barato y normado)
   vs desarrolladores (estable y flexible)

   negociar NO significa que todos acuerden:
   también sirve para entender POR QUÉ no acuerdan
   → un desacuerdo documentado es un RIESGO IDENTIFICADO

   ─────────────────────────────────────────────

   LOS 7 BENEFICIOS
   1. entender las restricciones del proyecto
   2. adaptarse a los cambios
   3. aprendizaje del equipo (cada lado educa al otro)
   4. sacar a la luz el CONOCIMIENTO TÁCITO
   5. manejar la complejidad
   6. lidiar con la incertidumbre
   7. encontrar MEJORES soluciones
      (persuadir ≠ buscar juntos)
      (secuencial impide canjear)

   ─────────────────────────────────────────────

   EL PROCESO EN 3 ETAPAS

   PRE-NEGOCIACIÓN
   · definir el problema
   · identificar interesados CRÍTICOS PARA EL ÉXITO
     = los que pueden acordar Y SOSTENER el acuerdo
   · elicitar metas
   · analizar metas → conflictos (+ inconsistencias,
     riesgos, supuestos ocultos)

   NEGOCIACIÓN
   · estructurar temas, desarrollar alternativas
   · ⚠ PRIMERO acordar CRITERIOS DE JUICIO
     (puede requerir una reunión previa solo para eso)
   · estrategias: compromiso · resolución de problemas
     · persuasión · abandono

   POST-NEGOCIACIÓN
   · evaluar resultados, sugerir re-negociación
   · revisiones de calidad
   · ASEGURAR EL COMPROMISO EN EL TIEMPO
```

---

## Preguntas para chequear que quedó

1. ¿Qué le interesa típicamente a cada uno de los tres grupos de interesados que enumera el capítulo?
2. ¿Por qué se dice que el resultado de la negociación también es entender por qué hay desacuerdo? ¿Qué se hace con un desacuerdo identificado?
3. ¿Por qué la negociación no es un episodio único?
4. Nombrá los siete beneficios de negociar.
5. En el beneficio de aprendizaje del equipo, ¿qué aprende cada lado? ¿Con qué problema del capítulo 2 se conecta?
6. ¿Qué es el conocimiento tácito y por qué la negociación lo saca a la luz mejor que otras técnicas?
7. Explicá por qué negociar los temas secuencialmente produce soluciones subóptimas.
8. Compará las tres definiciones de negociación: ¿qué enfatiza cada una?
9. ¿Qué es un "tema" (*issue*) en una negociación?
10. ¿Por qué el problema a negociar depende de la etapa del proyecto?
11. ¿Cómo se define un interesado crítico para el éxito? ¿En qué se diferencia de la definición general de interesado del capítulo 1?
12. ¿Qué es una meta y a qué niveles de granularidad puede formularse?
13. Además de conflictos, ¿qué otras tres cosas revela el análisis de metas?
14. ¿Qué son los criterios de juicio y qué pasa si faltan?
15. ¿Por qué puede hacer falta una sesión preparatoria antes de la negociación real?
16. Nombrá las cuatro estrategias que pueden adoptarse durante la negociación.
17. ¿Qué se evalúa en la post-negociación?
18. ¿Por qué "asegurar el compromiso a lo largo del tiempo" es parte del proceso, y qué instrumento lo permite?

---

**FIN DEL CAPÍTULO 7 — PARTE 1**

*Sigue en la Parte 2: las tres dimensiones de la negociación — los cinco modos de manejo del conflicto, las estrategias blanda, dura y de principios, las cuatro situaciones de colaboración según tiempo y lugar, y los tres niveles de soporte de herramientas—, más cuatro sistemas reales comparados.*
