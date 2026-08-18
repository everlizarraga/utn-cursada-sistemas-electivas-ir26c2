# Lectura en español — Cap. 16 · Parte 1: El caso, la gobernanza y el proceso

> **Origen.** Capítulo 16, secciones 16.1 a 16.4, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Nigel Martin y Shirley Gregor**, Universidad Nacional Australiana.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.

---

## Qué es este capítulo

Arranca la **Parte 3 del libro**: estudios y experiencia industrial. Es el primero de cuatro capítulos que en vez de proponer teoría **describen lo que pasa realmente en organizaciones concretas**.

Este describe **la Oficina Australiana de Estadísticas**, un organismo público que genera internamente el 60 % de su software de negocio. El interés no está en las estadísticas: **está en ver un proceso de requisitos que funciona bien, descrito con nombres y números.**

Y hay dos cosas que te sirven directamente:

1. **De dónde nacen realmente los requisitos** — no en la fase de requisitos, sino mucho antes y mucho más arriba.
2. La **cadena de trazabilidad vertical** desde las metas de negocio hasta los objetos de diseño, que es el ejemplo más concreto de trazabilidad de todo el libro.

---

## 1. Por qué eligieron este caso 🟡

> El organismo **fue seleccionado por su desempeño ejemplar como agencia del gobierno australiano y por su récord continuo de logros en el desarrollo y la gestión de sistemas de alta calidad**, particularmente el software requerido para entregar productos estadísticos.

**Y el dato que lo vuelve interesante:**

> **Es una organización gubernamental única en que GENERA INTERNAMENTE EL SESENTA POR CIENTO de su software de negocio.** Ese esfuerzo incluye desarrollar sistemas nuevos donde hace falta, **y adaptar e integrar paquetes comerciales y especializados a la infraestructura existente.**

**Cómo se hizo el estudio:** método cualitativo, con **entrevistas semi-estructuradas y no estructuradas con la alta gerencia y los ejecutivos**, recolección y análisis de documentos de archivo e informes parlamentarios, estudio de anuncios públicos y presentaciones, y **participación en demostraciones de los sistemas** — incluyendo una prueba práctica de una de las aplicaciones.

### La escala 🟢

Para dimensionar:

```
   · 3.002 personas (matemáticas, economía, estadística,
     informática, finanzas, administración)
   · ~17 % del personal son profesionales de informática
   · ~20 % del gasto anual va a actividades de informática
   · más de 690 publicaciones separadas por año
   · más de 3.400 computadoras personales y 1.100 portátiles
   · 20 bases de datos que soportan más de 150 aplicaciones
```

---

## 2. El principio rector 🔴

Y acá está lo más aprovechable de la sección introductoria. La organización tiene una creencia central que funciona como axioma:

> **"Nunca perder el foco de negocio. Toda tecnología de la información debe tener un valor de negocio DIRECTO O INDIRECTO."**

Los autores comentan: **"es potencialmente un buen axioma para todas las organizaciones, sean del sector privado o público."**

**Y una consecuencia de proceso que se deriva de ese principio:**

> **La organización busca asegurar que, POR MÁS DIVERSAS QUE SEAN SUS NECESIDADES DE SOFTWARE, la fase de ingeniería y gestión de requisitos —incluyendo todas las actividades y tareas asociadas— PERMANEZCA CONSTANTE** en todas sus actividades informáticas.

> ⚠️ **Cruce con la cátedra.** Notá el contraste con lo que viste en el capítulo 15: allí las metodologías web dejaban las cosas abiertas para no ser rígidas, y el resultado era que **nadie estructuraba el tema de los interesados**. Acá la jugada es la opuesta: **el proceso es el mismo siempre, sin importar qué se esté construyendo.**
>
> Y funciona porque el proceso está definido a un nivel que no depende de la tecnología: **identificar, registrar, revisar, priorizar.** Esas cuatro cosas se hacen igual para un almacén de datos que para un software de encuestas.

---

## 3. De dónde nacen realmente los requisitos 🔴🔴

Esta sección es la más valiosa del capítulo y merece atención.

### El punto de partida

> Para entender la fase táctica de requisitos, **consideramos importante reconocer que SON LAS CUESTIONES DE GESTIÓN ESTRATÉGICA LAS QUE IMPULSAN EL NEGOCIO.**
>
> **La creación de requisitos de software NO EMPIEZA SIMPLEMENTE CUANDO UNA ORGANIZACIÓN DECIDE COMPRAR UNA HERRAMIENTA NUEVA. Las semillas de los sistemas nuevos se siembran MUY TEMPRANO, EN LOS NIVELES MÁS ALTOS DE LA GESTIÓN.**

En este caso concreto, **los consejeros no ejecutivos y el grupo ejecutivo superior juegan un papel central en la definición temprana de las necesidades y los impulsores centrales del negocio.**

> **Los dos grupos de gestión más altos fijan las direcciones corporativas que dan forma a los procesos de negocio y al alcance de los sistemas a desarrollar** durante el programa de trabajo continuo de tres años.
>
> **Eso significa que LOS REQUISITOS DE SOFTWARE TIENEN SU GÉNESIS Y SU RESPALDO EN LAS FILAS EJECUTIVAS.**

> ⚠️ **Cruce con la cátedra.** Esto es lo que el capítulo 1 llamaba **requisitos a nivel organizacional** y el capítulo 9 llamaba **metas estratégicas** — pero acá se ve en funcionamiento, con quién hace qué.
>
> Y tiene una consecuencia práctica para un TP: **si el enunciado te da un negocio asignado, los requisitos no empiezan en la primera entrevista.** Empiezan en la pregunta de qué está tratando de lograr esa organización, que es información que hay que ir a buscar antes de hablar con ningún usuario.

### La consulta obligatoria 🔴

Los grupos de gestión **dieron la directiva de que ocurran consultas sustanciales con grupos de usuarios**, para asegurar que los requisitos de negocio **se eliciten, identifiquen y prioricen** para acción y desarrollo.

**Y el objetivo declarado de esas consultas:**

> Están **dirigidas a asistir en la compilación de requisitos que sean CONSISTENTES, FACTIBLES Y VERIFICABLES.**

**La escala de la consulta, que es notable:**

```
   más de 57 grupos de trabajo asesores externos y
   comités consultivos SE ACTIVAN CADA AÑO
   para probar direcciones, procesos y prácticas
   de negocio

   los grupos de usuarios corporativos están
   representados en:
     · las juntas de gestión de proyecto
     · los paneles de arquitectura (gerentes de negocio
       + arquitectos de sistemas)
     · los grupos de clientes críticos de cada unidad
```

**Y participan además más tarde**, en la fase de pruebas, con **protocolos de prueba de usuario** para revisar prototipos y sistemas de producción.

> ⚠️ **Cruce con la cátedra.** Retené la tríada del objetivo: **consistentes, factibles y verificables.** Son tres de los diez atributos de calidad del capítulo 8, y acá aparecen como **el propósito declarado de consultar a los usuarios** — no como una lista de chequeo posterior.
>
> Es decir: **no se consulta para "juntar requisitos" y después se los revisa contra criterios de calidad. Se consulta PARA QUE SALGAN con esas propiedades.** La calidad se construye en la elicitación, que es exactamente lo que el capítulo 8 llamaba **enfoque constructivo**.

### La responsabilidad conjunta 🔴

> **La definición y el desarrollo de requisitos en los niveles ESTRATÉGICO Y TÁCTICO de la organización es evidente. Este enfoque sugiere que las juntas no ejecutivas, los ejecutivos de gobierno y los gerentes operativos DEBERÍAN ASUMIR RESPONSABILIDADES CONJUNTAS** para el desarrollo de los sistemas del negocio.

### La cadena de trazabilidad 🔴🔴

Y acá viene el aporte más concreto del capítulo:

> **El flujo VERTICAL de requisitos desde el "negocio" de alto nivel hacia el "software" de bajo nivel también provee UNA VÍA DE TRAZABILIDAD** que está definida en los estándares de software relevantes.
>
> **Los requisitos de software deben ser trazables hacia las NECESIDADES DEL NEGOCIO, los REQUISITOS DE SISTEMA y los OBJETOS DE DISEÑO.**

```
   NECESIDADES DEL NEGOCIO
        ↕ trazable
   REQUISITOS DE SISTEMA
        ↕ trazable
   REQUISITOS DE SOFTWARE
        ↕ trazable
   OBJETOS DE DISEÑO
```

> ⚠️ **Cruce con la cátedra.** Esta es la **trazabilidad vertical** del capítulo 5 —la que relaciona objetos de tipos distintos— vista en una organización real y con los cuatro niveles nombrados.
>
> Y notá de dónde sale: **no se construye al final como un trámite.** Sale como consecuencia de que los requisitos bajaron por esa cadena. **Si las decisiones se toman arriba y se refinan hacia abajo, la traza queda hecha; si aparecen sueltas en el medio, no hay traza que construir después.**
>
> Es exactamente lo que el capítulo 6 llamaba **gestionar jerárquicamente** — los cambios entran por arriba, nunca por el código.

---

## 4. La arquitectura empresarial 🟡

### Qué es

> **La arquitectura empresarial realiza la visión de la organización para la informática, proveyendo un MARCO INTEGRADOR entre las metas de negocio y las actividades de software e infraestructura.**
>
> **Es una descripción de TODOS LOS ELEMENTOS de la organización, incluyendo las relaciones conectivas entre ellos:** las taxonomías de procesos de negocio, las tecnologías y herramientas, la arquitectura de aplicaciones, la arquitectura de gestión de datos, y la infraestructura.

**Qué la impulsa:** **las metas de negocio, las estrategias y el financiamiento corporativo.**

### Las dos reglas duras 🔴

La arquitectura **impone reglas estratégicas y tácticas estrictas** sobre el desarrollo. Y las dos que menciona el capítulo son muy concretas:

**Regla 1 — el orden de preferencia:**

> **La agencia "DEBE ENSAMBLAR ANTES DE COMPRAR, Y COMPRAR ANTES DE CONSTRUIR" sistemas nuevos.**
>
> **A los programadores se los ALIENTA A ENCASTRAR componentes ya desarrollados o comerciales usando interfaces de servicio, EN VEZ DE CREAR SISTEMAS NUEVOS.**

```
   1º  ENSAMBLAR lo que ya existe
   2º  COMPRAR lo que no existe internamente
   3º  CONSTRUIR solo si no queda otra
```

**Regla 2 — el control tecnológico:**

> **A los jefes de proyecto se los instruye a MIRAR LAS TECNOLOGÍAS YA DESPLEGADAS, para mantener el control y la disciplina tecnológica.**

**Y la consecuencia estratégica:**

> Los activos de software **son intrínsecos a la agencia y a su arquitectura y, a nivel estratégico, PROVEEN UNA FUENTE DE VENTAJA COMPETITIVA** en la entrega de bienes y servicios.
>
> **Importantemente, como vemos en este caso, LOS REQUISITOS DE SOFTWARE TIENEN UNA DIMENSIÓN ESTRATÉGICA que a menudo se olvida cuando se los enmarca en un proyecto individual.**

> ⚠️ **Cruce con la cátedra.** El principio de ensamblar-comprar-construir es interesante porque **invierte el instinto del desarrollador**, que suele ser construir. Y conecta con el capítulo 14: allí, **construir de más era desperdicio**; acá, la regla organizacional lo previene por política, no por criterio individual.
>
> Y la frase final es la que más vale: **un requisito visto desde un proyecto parece una decisión técnica; visto desde la organización es una decisión estratégica.** Es el mismo desdoblamiento que el capítulo 1 planteaba con los tres niveles.

---

## 5. El proceso de desarrollo 🟡

### Cómo se formalizó 🔴

Un detalle histórico que vale la pena:

> Para traer mayor consistencia, uniformidad y calidad al desarrollo, **se inició un proyecto de calidad de negocio bajo la conducción de un director senior a mediados de 2001. El proceso se lanzó y adoptó oficialmente en septiembre de 2002, FORMALIZANDO EFECTIVAMENTE VEINTE AÑOS DE PRÁCTICA DE DESARROLLO.**

> ⚠️ **Cruce con la cátedra.** *"Formalizando veinte años de práctica"* es la manera correcta de leer esto: **el proceso no se inventó en un escritorio y se impuso; se destiló de lo que ya se venía haciendo.**
>
> Es lo mismo que el capítulo 14 decía del manifiesto ágil —*no son invenciones, son el resultado de racionalizar la experiencia*— y lo que el capítulo 8 llamaba **estrategias básicas**: lo que ya está en uso da una entrada valiosa sobre por dónde empezar y qué rindió.

### La jerarquía de tres niveles 🟡

> La organización **adoptó deliberadamente una jerarquía específica** de fases, actividades y tareas.

```
   el PROCESO consiste en 5 FASES centrales
        cada fase se divide en ACTIVIDADES integradas
             cada actividad se subdivide en TAREAS
             interrelacionadas
```

### Las cinco fases 🟡

| | Fase | Qué pasa |
|---|---|---|
| **1** | **Requisitos** | **Los requisitos del cliente se IDENTIFICAN, REGISTRAN, REVISAN y PRIORIZAN** |
| **2** | **Diseño** | Se inicia **un panel de arquitectura con representantes de negocio y técnicos**, se conduce el análisis y diseño, y se prepara una especificación de la implementación |
| **3** | **Construcción** | **Todas las unidades o componentes se SELECCIONAN o se CREAN (si hace falta)**, y se prepara la documentación incluyendo los planes de prueba. Todos los módulos se prueban individualmente |
| **4** | **Integración y prueba** | Los sistemas se colocan **en un entorno particionado de prueba y desarrollo** para integración, construcción de prototipos y prueba de sistema. **Se inicia la prueba de aceptación de usuario y la retroalimentación sobre los prototipos.** Los cambios se avanzan según esa retroalimentación |
| **5** | **Liberación** | El software se libera al entorno de producción. **Se capacita a los usuarios y se conduce una REVISIÓN POSTERIOR A LA IMPLEMENTACIÓN** |

> Notá el detalle de la fase 3: *"se seleccionan o se crean (si hace falta)"*. La regla de ensamblar-antes-de-construir está incorporada al vocabulario del proceso, no solo a la política.

### Por qué armaron un proceso propio 🟡

> **Operar como organización nacional de estadísticas es un negocio especializado que requiere habilidades, personas y sistemas específicos.** En consecuencia, **la organización NO PUDO SIMPLEMENTE COMPRAR E INSTALAR software comercial** para cumplir su rol.
>
> Desarrolló un proceso propio **para implementar un enfoque consistente y uniforme a través de toda la organización.** Pero **de mayor significación potencial es la mejora de los procesos de calidad A NIVEL CORPORATIVO.**

Y el beneficio que destacan:

> El proceso **permite desarrollos coherentes e integrados, a la vez que provee OPORTUNIDADES PARA TRABAJO COLABORATIVO Y COMUNICATIVO a través de toda la empresa.**

---

## Mapa de la Parte 1

```
   EL PRINCIPIO RECTOR
   "nunca perder el foco de negocio: toda tecnología
    debe tener valor de negocio directo o indirecto"
   → el proceso de requisitos permanece CONSTANTE por
     más diversas que sean las necesidades

   ─────────────────────────────────────────────

   ══► DE DÓNDE NACEN LOS REQUISITOS ◄══
   NO empiezan cuando se decide comprar una herramienta
   "las semillas se siembran MUY TEMPRANO, en los
    NIVELES MÁS ALTOS de la gestión"
   → tienen su GÉNESIS Y RESPALDO en las filas ejecutivas

   consulta obligatoria: 57+ grupos asesores por año
   objetivo declarado: requisitos CONSISTENTES,
   FACTIBLES y VERIFICABLES
   → la calidad se construye EN la elicitación

   ─────────────────────────────────────────────

   ══► LA CADENA DE TRAZABILIDAD VERTICAL ◄══
   necesidades del NEGOCIO
        ↕
   requisitos de SISTEMA
        ↕
   requisitos de SOFTWARE
        ↕
   objetos de DISEÑO

   no se construye al final: SALE de que los requisitos
   bajaron por esa cadena

   ─────────────────────────────────────────────

   ARQUITECTURA EMPRESARIAL — 2 reglas duras
   1. ENSAMBLAR antes de COMPRAR, comprar antes
      de CONSTRUIR
   2. mirar las tecnologías YA DESPLEGADAS

   ─────────────────────────────────────────────

   EL PROCESO: 5 fases → actividades → tareas
   requisitos · diseño · construcción · integración
   y prueba · liberación
   se formalizó en 2002, DESTILANDO 20 AÑOS de práctica
```

---

## Preguntas para chequear que quedó

1. ¿Por qué se eligió esta organización como caso de estudio? ¿Qué la vuelve inusual?
2. ¿Cuál es el axioma central de la organización sobre la tecnología de la información?
3. ¿Qué significa que la fase de requisitos "permanezca constante" pese a la diversidad de necesidades? ¿Por qué es posible?
4. ¿Dónde empiezan realmente los requisitos, según el capítulo? ¿Quiénes los originan?
5. ¿Qué consecuencia tiene eso para encarar un caso de negocio asignado?
6. ¿Cuál es el objetivo declarado de las consultas con grupos de usuarios? Nombrá las tres propiedades buscadas.
7. ¿Por qué se dice que la calidad se construye en la elicitación y no después?
8. Nombrá los tres ámbitos donde están representados los grupos de usuarios corporativos.
9. Describí la cadena de trazabilidad vertical con sus cuatro niveles.
10. ¿Por qué esa trazabilidad no se construye al final?
11. ¿Qué es la arquitectura empresarial y qué elementos describe?
12. Explicá la regla de ensamblar-comprar-construir y en qué orden va.
13. ¿Qué instrucción reciben los jefes de proyecto sobre las tecnologías desplegadas y para qué?
14. ¿Por qué se dice que los requisitos tienen una dimensión estratégica que se olvida al mirarlos desde un proyecto?
15. ¿Cómo se originó el proceso formal de desarrollo? ¿Qué significa que "formalizó veinte años de práctica"?
16. Nombrá la jerarquía de tres niveles del proceso.
17. Nombrá las cinco fases y qué pasa en cada una.
18. ¿Por qué la organización no pudo simplemente comprar software comercial?
19. Además de la consistencia técnica, ¿qué beneficio organizacional trae tener un proceso definido?

---

**FIN DEL CAPÍTULO 16 — PARTE 1**

*Sigue en la Parte 2: la fase de requisitos en detalle —identificar, registrar, revisar y priorizar—, la comparación con la teoría y los estándares internacionales, tres ejemplos reales de requisitos elicitados, y las lecciones del caso.*
