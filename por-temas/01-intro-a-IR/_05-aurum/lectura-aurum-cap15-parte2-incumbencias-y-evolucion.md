# Lectura en español — Cap. 15 · Parte 2: Las incumbencias y la evolución de los requisitos

> **Origen.** Capítulo 15, secciones 15.3 a 15.5, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Jacob L. Cybulski y Pradip K. Sarkar**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1.** Se asume conocido el contexto: interesados externos e imprevisibles, tiempo de entrega muy corto, requisitos creados desde cero.

---

## Lo que hay acá

Dos cosas que valen mucho:

1. **La distinción entre "problema" e "incumbencia"** — un cambio de palabra que cambia quién puede resolver qué.
2. **El hallazgo empírico central del capítulo:** los interesados **no se resisten a los requisitos, se resisten a las CONSECUENCIAS de los requisitos.** Es una observación simple que reencuadra por completo cómo tratar la resistencia.

Y de yapa, una definición operativa de **cuándo un desacuerdo se está convirtiendo en conflicto**, que se conecta directo con el capítulo 7.

---

## 1. Por qué el análisis de interesados 🔴

### La causa de fracaso que nadie mira

> Una revisión de la literatura de desarrollo de sistemas y de gestión de proyectos revela que **una de las causas mayores de fracaso puede atribuirse a LA INSATISFACCIÓN DE LOS INTERESADOS, sea con la manera en que se emprende el proyecto o con el producto final.**
>
> **La resistencia de los interesados a la adopción de tecnología nueva, sus incumbencias sobre su relación con ella, y las estructuras de poder prevalecientes tienen gran impacto sobre la implementación real de los artefactos tecnológicos dentro de la organización.**

Y una afirmación de los profesionales que vale la pena:

> **Los proyectos de desarrollo a menudo fracasan porque los desarrolladores NO SABEN QUIÉNES SON LOS INTERESADOS "REALES".**

### De dónde viene la técnica 🟡

> **El análisis de interesados se origina en la GESTIÓN ESTRATÉGICA.** Uno de los trabajos más prominentes argumenta que **un prerrequisito para la planificación estratégica efectiva es la identificación y el análisis de aquellas partes que pueden AFECTAR la implementación de los programas estratégicos de la organización, o SER AFECTADAS por ellos.**

*(Es la misma definición de interesado que viste en el capítulo 1.)*

Los interesados del negocio **sostienen perspectivas distintas** sobre cuestiones como: las metas y valores del grupo y la organización, la asignación de recursos, la distribución de recompensas, políticas, procedimientos y asignación de tareas.

### El argumento ético 🟡

Y acá aparece una justificación poco frecuente en la literatura técnica:

> El análisis de interesados **debería hacerse no solo para asegurar la supervivencia y la rentabilidad de la organización, SINO TAMBIÉN PORQUE ES ÉTICO mirar los puntos de vista de los interesados que están o van a estar afectados por las decisiones estratégicas de la organización.**

### Lo que muestra la evidencia 🔴

> Los investigadores descubrieron que **el éxito de los proyectos de desarrollo depende en gran medida DE LA PARTICIPACIÓN DE TODOS LOS INTERESADOS.**
>
> Como **distintos interesados tienen expectativas distintas** respecto de un sistema, **el éxito o el fracaso del proyecto depende de CUÁN EFECTIVAMENTE LOS GERENTES ABORDEN ESAS EXPECTATIVAS.**

Y la advertencia más contundente, de un enfoque socio-técnico de diseño:

> **"Los sistemas diseñados sin la participación activa de los usuarios PUEDEN PARECER INICIALMENTE COSTO-EFECTIVOS según criterios técnicos, pero de hecho a menudo INCURREN EN ALTOS COSTOS SOCIALES: resistencia al cambio, utilización pobre del equipamiento, alta rotación de personal y ausentismo."**

**La premisa detrás:** para que un proyecto tenga éxito **debe haber un ajuste estrecho de la tecnología con los factores sociales y organizacionales.**

Y en la misma línea: **la participación de los interesados puede llevar a niveles más altos de satisfacción del usuario, calidad del sistema y uso del sistema.**

> ⚠️ **Cruce con la cátedra.** Esa cita sobre los costos sociales es aprovechable y va más allá del contexto web: **un sistema puede ser impecable en lo técnico y fracasar completamente en lo organizacional.** Y notá que los costos que enumera —resistencia, subutilización, rotación, ausentismo— **no aparecen en ninguna métrica de software.** Se pagan igual, pero en otra contabilidad.
>
> Conecta con el capítulo 12, donde se decía que **la ambigüedad política puede jugar un papel tan significativo como la complejidad del dominio.**

---

## 2. Problema o incumbencia 🔴🔴

Esta es la contribución conceptual del capítulo, y es corta.

### El cambio de palabra

> Según la posición que adopta el capítulo, **los problemas SON PERCEPCIONES EN LA MENTE DE LAS PERSONAS. Por lo tanto es más apropiado referirse a esas cuestiones como "INCUMBENCIAS" en vez de "problemas", ya que lo primero ASOCIA ESTRECHAMENTE LA CUESTIÓN CON UN DUEÑO.**

**Y por qué eso importa** —los autores lo enuncian en sus puntos clave:

```
   · llamar "PROBLEMAS" a las cuestiones en disputa
     LAS OBJETIVIZA, ignorando así las perspectivas de
     quienes las expresaron, y en consecuencia
     RESTRINGIENDO LA RESOLUCIÓN A MANOS DE LA ÉLITE

   · esas cuestiones se consideran problemas
     PORQUE LA GENTE LAS PERCIBE COMO TALES

   · por eso el término "INCUMBENCIA" es más apropiado:
     relaciona la cuestión con la perspectiva original
     de la persona
```

> ⚠️ **Cruce con la cátedra — vale la pena entender bien esta jugada.** No es un cambio cosmético de vocabulario.
>
> **Decir "hay un problema con el módulo de facturación"** convierte la cuestión en un hecho objetivo del mundo. Y si es un hecho objetivo, **quien lo resuelve es el que tiene autoridad técnica** — el que sabe. La persona que lo planteó desaparece de la escena.
>
> **Decir "el área de finanzas tiene una incumbencia sobre el módulo de facturación"** mantiene visible de quién es. Y eso tiene una consecuencia práctica: **no se puede cerrar sin volver a esa persona.** Un problema se resuelve; una incumbencia se atiende con su dueño.
>
> Conecta directo con el capítulo 8, que usaba **"problema" en vez de "defecto"** por una razón parecida: un desacuerdo entre interesados hay que resolverlo, pero **no es la equivocación de nadie.** Las dos jugadas van en la misma dirección — nombrar las cosas de manera que se puedan tratar sin acusar.

### Cómo se reconcilian 🔴

Si las incumbencias se expresan mediante los puntos de vista de múltiples interesados, **¿cómo sabemos que están enfocadas en la misma cuestión?** La respuesta que recogen:

```
   1. SEPARAR la cuestión problemática DE LA PERSONA
      que la percibió como tal

   2. PEDIRLE A OTRAS PERSONAS que expresen sus
      incumbencias SOBRE ESA MISMA CUESTIÓN

   3. ANALIZAR Y RECONCILIAR las incumbencias, con el
      objetivo de generar UN PUNTO DE VISTA COLECTIVO
      sobre el problema
```

**Y por qué ese punto de vista colectivo importa:**

> **Es un prerrequisito para producir una SOLUCIÓN COLECTIVA.**

*(Los autores lo alinean con una teoría de la acción comunicativa, según la cual los miembros de una sociedad persiguen conjuntamente acciones para alcanzar consenso racional y entendimiento mutuo.)*

### Cuándo la incumbencia se vuelve conflicto 🔴🔴

Y acá viene lo más útil de la sección:

> **Si ese consenso y entendimiento mutuo NO PUEDEN ALCANZARSE, las incumbencias pueden potencialmente INTENSIFICARSE y resultar en un CONFLICTO ABIERTO.**
>
> **Por lo tanto, EN LAS INCUMBENCIAS PUEDEN DETECTARSE LAS SEMILLAS O ANTECEDENTES DEL CONFLICTO.**

```
   INCUMBENCIA no atendida
        ↓ se intensifica
   INCUMBENCIA INTENSA ← señal de alarma
        ↓ si sigue sin atenderse
   CONFLICTO ABIERTO
```

> ⚠️ **Cruce con la cátedra.** Esto le da al capítulo 7 algo que ahí faltaba: **un indicador temprano.** Allí el conflicto aparecía ya declarado, y el ingeniero de requisitos entraba como mediador a resolverlo.
>
> Acá se dice que **antes del conflicto hay incumbencias intensas**, y que esas incumbencias son observables si uno las busca. La consecuencia práctica es directa: **atender una incumbencia es más barato que mediar un conflicto**, y lo primero se puede hacer antes de que lo segundo exista.
>
> Para una minuta de mediación, es un criterio útil: registrar no solo los desacuerdos declarados sino **las incumbencias que quedaron sin respuesta**, porque esas son las que van a volver.

### Para qué sirven las incumbencias 🔴

Dos observaciones más:

> **Las percepciones de los interesados respecto del sistema propuesto SE FORMAN SOBRE LA BASE DE SUS INCUMBENCIAS.** Por lo tanto, **el entendimiento que tengan los jefes de proyecto de esas incumbencias es CENTRAL PARA EL "BUEN DISEÑO" del sistema.**

Y una imagen que vale:

> **Las incumbencias proveen el "LENTE" primario por el cual la gente procesa multitudes de información. Dicho de otro modo: ASIGNAN PRIORIDADES A LOS MENSAJES SOBRE LA BASE DE SUS INCUMBENCIAS.**

### La definición 🔴

> **Una INCUMBENCIA es una cuestión expresada por un interesado particular respecto de algún aspecto del sistema de información propuesto, que IMPACTA LA PARTICIPACIÓN DE ESE INTERESADO en el sistema, y que AL SER ATENDIDA DETERMINARÁ LA NECESIDAD DE UNA EVOLUCIÓN POSTERIOR del sistema.**

Desarmémosla:

```
   · es una cuestión EXPRESADA POR ALGUIEN (tiene dueño)
   · es SOBRE ALGÚN ASPECTO del sistema propuesto
   · IMPACTA LA PARTICIPACIÓN de esa persona
     (o sea: si no se atiende, esa persona se corre)
   · atenderla GENERA EVOLUCIÓN del sistema
```

**Y su relación con las metas** (capítulo 9):

> **Las incumbencias están relacionadas, aunque no directamente, con las EXPECTATIVAS Y METAS de los interesados**: tanto unas como otras están vinculadas a sus creencias sobre **qué aspectos del sistema propuesto motivarán (o no) su participación.**

**Una recomendación concreta para los jefes de proyecto:**

> Hay que **incitar a clientes y usuarios a expresar sus principales incumbencias respecto de las cuestiones QUE LES IMPIDEN alcanzar sus metas laborales y personales.** También se les pide **enunciar oportunidades que actualmente no pueden aprovechar**, o **revelar cuestiones que consolidan su posición social en la organización.**

> ⚠️ **Cruce con la cátedra.** Esas tres preguntas son una técnica de elicitación en sí mismas, y son distintas de las habituales:
>
> - *¿qué te impide alcanzar tus objetivos?* (no "¿qué querés?")
> - *¿qué oportunidad no podés aprovechar hoy?*
> - *¿qué consolida tu posición en la organización?*
>
> La tercera es la más audaz y la que ninguna metodología pregunta: **reconoce abiertamente que la gente tiene intereses posicionales dentro de su organización, y que esos intereses influyen sobre qué sistema quiere.** Es lo mismo que el capítulo 7 llamaba *"individuos con personalidades y agendas personales"*, convertido en pregunta.

---

## 3. El estudio y su hallazgo central 🔴

### El estudio 🟢

Se estudiaron **seis organizaciones** que implementaban sistemas web de servicios al empleado: **cuatro universidades y las dos únicas empresas de liquidación de sueldos tercerizada** de la ciudad que adoptaban tecnología web.

**Los interesados típicos de esos proyectos:** los iniciadores del proyecto (las divisiones de recursos humanos y los proveedores de liquidación), personal de sistemas, clientes de las empresas tercerizadoras, empleados y supervisores.

**El método:** entrevistas semi-estructuradas con quienes encabezaban los proyectos, apuntando a su experiencia con:

```
   · la implementación y evolución continua del sistema
   · las características de los interesados de base
   · su experiencia CON LAS INCUMBENCIAS de los
     interesados
   · sus puntos de vista sobre las cuestiones de
     disonancia expresadas por los usuarios y por los
     distintos actores de las ESTRUCTURAS DE PODER
   · las consecuencias percibidas de las medidas tomadas
     para ALIVIAR LA DISCORDIA o disminuir la RESISTENCIA
```

**Y lo que reveló el análisis:**

> El relato multidimensional de las experiencias de los jefes de proyecto **reveló LOS OBSTÁCULOS SOCIALES Y LA FRAGILIDAD DE LAS RELACIONES INTRA-ORGANIZACIONALES, que demandaban un enfoque cauteloso y con tacto de parte de la gestión del proyecto.**

### El paralelo con la educación 🟡

Un hallazgo lateral interesante: la noción de evolución de requisitos dirigida por incumbencias **encaja con un modelo que se originó en la investigación educativa** de los años 70 y 80, hecho para estudiar **el proceso de cambio tal como lo experimentan los docentes** al implementar currículos y modos de enseñanza nuevos.

**El paralelo, que los autores llaman "sorprendente":**

```
   el CURRÍCULO ────────────► una especificación de la
                              práctica docente
   los DOCENTES ────────────► los interesados
   la gestión EDUCATIVA ────► los jefes de proyecto
   la ADOPCIÓN del currículo ► el refinamiento de
                               requisitos
```

Ese modelo aporta **las "etapas de incumbencia"**, un marco para elaborar **los sentimientos y motivaciones** de los docentes ante el cambio en distintos momentos de la implementación. Las etapas que se usaron para analizar la evolución de requisitos:

```
   1. despertar la CONCIENCIA del cambio
   2. las búsquedas INFORMATIVAS de los interesados
   3. el compromiso PERSONAL y de GESTIÓN
   4. lidiar con las CONSECUENCIAS del cambio
   5. la mejora COLABORATIVA sobre el cambio
   6. el posible REENFOQUE
```

### El hallazgo central 🔴🔴

Y acá viene lo mejor del capítulo entero.

**Cómo funciona el ciclo, según el modelo:**

```
   1. LOS JEFES DE PROYECTO especifican un conjunto
      INICIAL de requisitos, guiados por sus propias
      incumbencias personales y de gestión

   2. esos requisitos SE VALIDAN con los interesados
      mediante retroalimentación

   3. los interesados expresan sus PUNTOS DE VISTA
      respecto de los requisitos
```

**Pero el estudio descubrió algo que cambia la lectura:**

> **Las incumbencias subyacentes detrás de los puntos de vista ESTABAN VINCULADAS A LAS CONSECUENCIAS REALES O PROYECTADAS DE LOS REQUISITOS, MÁS QUE A LOS REQUISITOS EN SÍ MISMOS.**
>
> **En otras palabras: los interesados estaban primariamente preocupados por LAS SITUACIONES QUE RESULTARÍAN de los efectos de los requisitos del iniciador. Así, RESISTEN LOS REQUISITOS EN ANTICIPACIÓN DE ESAS SITUACIONES.**

```
   requisito propuesto
        ↓ produciría
   una CONSECUENCIA en el trabajo de alguien
        ↓ genera
   una INCUMBENCIA
        ↓ se manifiesta como
   RESISTENCIA AL REQUISITO

   ══► la resistencia se dirige al requisito
       PERO SU CAUSA ESTÁ EN LA CONSECUENCIA ◄══
```

> ⚠️ **Cruce con la cátedra — este es el punto más aprovechable del capítulo.** Reencuadra por completo qué hacer ante la resistencia.
>
> Si alguien se opone a un requisito y uno interpreta que **se opone al requisito**, la respuesta natural es argumentar a favor del requisito: explicar por qué es necesario, mostrar sus beneficios, convencer. **Y eso no funciona, porque no es a lo que se opone.**
>
> Si uno entiende que **se opone a una consecuencia** —que ese requisito le va a agregar trabajo, o le va a quitar control sobre algo, o va a hacer visible algo que prefería que no se viera— entonces **la conversación es otra**: cuál es esa consecuencia, es real o proyectada, y qué se puede hacer al respecto.
>
> Es exactamente el principio de Fisher y Ury del capítulo 7: **enfocarse en los INTERESES, no en las POSICIONES.** La oposición al requisito es la posición; la consecuencia temida es el interés. Y este capítulo agrega el dato empírico de que **casi siempre es así.**

### Qué hacer con la resistencia 🔴

El modelo describe el ciclo completo:

> **Para minimizar la resistencia, los jefes de proyecto INTERACTÚAN Y NEGOCIAN con los interesados.** Eso puede dar lugar a **incumbencias de colaboración** de parte de los propios jefes de proyecto.
>
> **Es durante esas interacciones que los jefes de proyecto DEBERÍAN PODER DETECTAR LA EXISTENCIA DE ANTECEDENTES DE CONFLICTO.**

**Y las dos salidas posibles:**

```
   SI las incumbencias NO se atienden adecuadamente
        → la resistencia SE INTENSIFICA
        → aumenta la probabilidad de que los antecedentes
          se manifiesten en CONFLICTO ABIERTO

   SI se atienden
        → introduciendo requisitos NUEVOS, o mejorando
          o modificando los existentes
        → REENFOQUE del proyecto y de los requisitos
```

**Y el bucle se cierra:**

> **Evidentemente, las consecuencias de algunos de los requisitos nuevos o modificados son percibidas negativamente POR LOS PROPIOS JEFES DE PROYECTO, y dan lugar a SUS PROPIAS INCUMBENCIAS.** Así se demuestra **la naturaleza iterativa de estos proyectos.**

```
   incumbencias del iniciador
        ↓
   REQUISITOS
        ↓
   CONSECUENCIAS
        ↓
   incumbencias de los interesados → RESISTENCIA
        ↓                                  ↓
        │                          negociación / acción
        │                                  ↓
        └──── requisitos nuevos o modificados ──┐
                       ↓                        │
              consecuencias nuevas ─────────────┘
              (que pueden generar incumbencias
               del propio iniciador)
```

### La base de experiencia 🟡

Un elemento más del modelo:

> **La base de experiencia —por implícita o semi-institucional que sea— provee asistencia tanto a los desarrolladores como a los jefes de proyecto.** La flecha es **de doble sentido**, para sugerir el flujo dual de información: **también alimentan y aumentan la base de experiencia con lo que aprendieron del proyecto actual**, mientras aprovechan la asistencia que esa infraestructura de conocimiento provee.

### La conclusión del modelo 🔴

> **Está claro por los datos empíricos que LAS INCUMBENCIAS DE LOS INTERESADOS SON LOS PRECURSORES ELEMENTALES DE LOS REQUISITOS DEL SISTEMA.**
>
> **Es por lo tanto inconcebible que en el desarrollo de estos sistemas —y de otros similares— las incumbencias de los interesados se dejen SIN RECOLECTAR, SIN PROCESAR Y SIN ATENDER.**
>
> **Los métodos de IR deben por lo tanto mejorarse significativamente, y los analistas RE-ENTRENARSE, para poner un foco especial en su trabajo con los requisitos del sistema Y CON LAS INCUMBENCIAS DE LOS INTERESADOS.**

---

## 4. Conclusiones del capítulo 🔴

### Lo que confirmó el estudio

> **A lo largo de un proyecto, mientras interesados distintos e interdependientes desarrollan múltiples puntos de vista, la divergencia resultante de visiones y objetivos CREA EL POTENCIAL DE CONFLICTO.**
>
> **La evidencia empírica confirma que la participación de interesados con múltiples puntos de vista PUEDE EFECTIVAMENTE LLEVAR A CONFLICTOS** en la ingeniería de requisitos.

Y el vínculo explícito que identifican:

```
   INCUMBENCIAS de los interesados
        ↓
   RESISTENCIA al cambio
        ↓
   POTENCIAL DE CONFLICTO entre interesados preocupados
   e iniciadores que NO RESPONDEN
```

> Notá la última parte: el conflicto no se desarrolla entre los interesados y el proyecto. Se desarrolla **entre los interesados preocupados y los iniciadores que no responden.** La falta de respuesta es un ingrediente.

### La generalización 🔴

Y acá el capítulo se sale del tema web y dice algo más ambicioso:

> **El advenimiento de los sistemas basados en web, bastante únicos en sus características y requerimientos de desarrollo, es solo INDICATIVO DE LA NUEVA GENERACIÓN de sistemas de software** — representada también por los sistemas de alcance empresarial, los sistemas comerciales listos para usar y los basados en componentes reutilizables.

**Lo que esos sistemas tienen en común:**

```
   · infraestructura habilitante SOFISTICADA
   · ALTO IMPACTO en el negocio
   · TIEMPO CORTO al mercado
   · ALTO NIVEL de incumbencias de los interesados
```

**Y el desplazamiento que producen:**

> **La nueva generación de sistemas de software REDEFINE EL PAPEL DEL INGENIERO DE REQUISITOS y corre su atención DE LA GESTIÓN DE REQUISITOS A LA GESTIÓN DE INTERESADOS E INCUMBENCIAS.**

### La paradoja final 🔴

El capítulo cierra con una idea que vale la pena, parafraseando a otro autor:

> **No podemos separar fácilmente los requisitos reales de otras características deseables del sistema.** De hecho, **habiendo recolectado los requisitos del sistema, el ingeniero de requisitos de los sistemas de nueva generación TODAVÍA TIENE UNA TAREA CONSIDERABLE POR DELANTE.**
>
> **Si bien el resto de las necesidades de los interesados puede no ser más que expresión de preferencia, ESAS PREFERENCIAS REPRESENTAN UNA GRAN PARTE —QUIZÁS LA MAYORÍA— DE LO QUE LOS INTERESADOS QUIEREN.**
>
> **Esas preferencias van a tener conflictos, van a tener comunidades distintas que las desean, y —lo más importante— VAN A SER SATISFECHAS EN GRADOS VARIABLES por el sistema entregado.**

Y de ahí la paradoja:

> **El ingeniero de requisitos nuevo debe ahora gastar una cantidad considerable de esfuerzo LIDIANDO CON NO-REQUISITOS.**
>
> **Su territorio tradicional —la expresión de los interesados sobre qué querían, qué necesitaban, qué mejoraría su trabajo— trata de esas mismas necesidades, y sin embargo LA MAYORÍA DE ESAS COSAS SON AHORA INCUMBENCIAS.**

> ⚠️ **Cruce con la cátedra.** Esta paradoja es un buen cierre para pensar, y conviene entenderla bien.
>
> Lo que dice es que **la mayor parte de lo que la gente quiere de un sistema no llega a tener forma de requisito.** Son preferencias, expectativas, temores sobre consecuencias — cosas reales que influyen decisivamente en si el sistema se adopta o se rechaza, **pero que no entran en una especificación.**
>
> Y el ingeniero de requisitos que solo trabaja con lo que sí entra en la especificación **está atendiendo la parte chica del problema.** No porque los requisitos no importen, sino porque alrededor de ellos hay un campo de incumbencias que determina si van a servir de algo.
>
> Es la misma constatación que atraviesa toda la serie desde ángulos distintos: en el capítulo 2 (la IR es un proceso social y las técnicas lingüísticas solo pueden apoyarlo), en el 7 (los interesados tienen agendas personales), en el 12 (lo político pesa tanto como lo técnico). **Este capítulo es el que lo dice más fuerte.**

---

## Mapa de la Parte 2

```
   POR QUÉ EL ANÁLISIS DE INTERESADOS
   · una causa mayor de fracaso es su INSATISFACCIÓN
   · "los proyectos fracasan porque los desarrolladores
      NO SABEN QUIÉNES SON LOS INTERESADOS REALES"
   · un sistema sin participación de usuarios puede
     parecer costo-efectivo Y TENER ALTOS COSTOS
     SOCIALES: resistencia, subutilización, rotación,
     ausentismo

   ─────────────────────────────────────────────

   ══► PROBLEMA vs INCUMBENCIA ◄══

   "PROBLEMA" ────► objetiviza la cuestión
                    → la resolución queda en manos
                      de quien tiene autoridad
                    → el que la planteó DESAPARECE

   "INCUMBENCIA" ─► mantiene visible DE QUIÉN ES
                    → no se puede cerrar sin volver
                      a esa persona

   INCUMBENCIA no atendida → se INTENSIFICA → CONFLICTO
   → las incumbencias son LOS ANTECEDENTES del conflicto
     (indicador TEMPRANO, antes de que el conflicto exista)

   ─────────────────────────────────────────────

   ══► EL HALLAZGO CENTRAL ◄══

   los interesados NO se resisten a LOS REQUISITOS:
   se resisten a LAS CONSECUENCIAS de los requisitos

   → argumentar a favor del requisito NO FUNCIONA
   → hay que preguntar QUÉ CONSECUENCIA se teme
   → es "intereses, no posiciones" (cap. 7) con
     evidencia empírica

   ─────────────────────────────────────────────

   EL BUCLE
   incumbencias del iniciador → requisitos →
   consecuencias → incumbencias de los interesados →
   resistencia → negociación → requisitos nuevos →
   consecuencias nuevas → (y vuelve)

   ─────────────────────────────────────────────

   LA PARADOJA FINAL
   la mayoría de lo que los interesados quieren
   NO LLEGA A SER REQUISITO — son incumbencias
   → el papel se corre de GESTIONAR REQUISITOS
     a GESTIONAR INTERESADOS E INCUMBENCIAS
```

---

## Preguntas para chequear que quedó

1. ¿Cuál es una de las causas mayores de fracaso de proyectos según la literatura revisada?
2. ¿Por qué fracasan los proyectos según los profesionales citados?
3. ¿De qué disciplina proviene el análisis de interesados?
4. ¿Cuál es el argumento ético para hacer análisis de interesados?
5. ¿Qué costos sociales incurre un sistema diseñado sin participación de usuarios? ¿Por qué no aparecen en las métricas de software?
6. ¿Por qué "problema" objetiviza una cuestión y qué consecuencia tiene eso sobre quién la resuelve?
7. ¿Qué gana el término "incumbencia" respecto de "problema"?
8. Describí los tres pasos para reconciliar incumbencias de varios interesados.
9. ¿Qué pasa si no se alcanza el consenso? ¿Por qué las incumbencias son un indicador temprano?
10. ¿Por qué atender una incumbencia es más barato que mediar un conflicto?
11. Definí "incumbencia" y desarmá la definición en sus cuatro partes.
12. ¿Qué imagen usa el capítulo para describir cómo las incumbencias filtran la información?
13. Nombrá las tres preguntas que se recomienda hacerle a clientes y usuarios. ¿Cuál es la más audaz y por qué?
14. ¿Qué reveló el estudio sobre las relaciones intra-organizacionales?
15. Explicá el paralelo entre la evolución de requisitos y la adopción de un currículo educativo.
16. ¿Cuál es el hallazgo central del capítulo sobre a qué se resisten los interesados?
17. ¿Por qué argumentar a favor de un requisito no reduce la resistencia? ¿Qué habría que hacer en cambio?
18. ¿Con qué principio del capítulo 7 se conecta ese hallazgo?
19. Describí el bucle completo del modelo, desde las incumbencias del iniciador hasta el reenfoque.
20. ¿Por qué los requisitos nuevos pueden generar incumbencias en los propios jefes de proyecto?
21. ¿Entre quiénes se desarrolla el conflicto, según la conclusión? ¿Qué ingrediente aporta el iniciador?
22. ¿Qué tienen en común los sistemas de la "nueva generación"?
23. Explicá la paradoja final: ¿por qué el ingeniero de requisitos debe lidiar con "no-requisitos"?

---

**FIN DEL CAPÍTULO 15 — PARTE 2**

**FIN DEL CAPÍTULO 15**

*Sigue el capítulo 16: un caso de desarrollo y gestión de sistemas de software de calidad en el sector público, en 2 partes.*
