# 📘 APUNTE MAESTRO — Clase 04 · Entrevistas y redacción de requisitos — Parte 2

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Unidad:** `clase04` · Jueves 03/09/2026 · Presencial (Campus)
**Parte 2:** El simulacro — la entrevista como caso, la puesta en común y la corrección del diseño de entrevista.

---

## Sobre esta parte

**Qué cubre:** cómo fue la entrevista de la consultora a los profesores · lo que se relevó, ordenado por tema (el insumo de la minuta) · la puesta en común: los errores señalados, el hallazgo que resume la técnica, y lo que se aprende de estar del otro lado de la mesa · el cliente que pide la tecnología de moda · los seis criterios con los que se corrigió el diseño de entrevista entregado.

**Qué viene después:** Parte 3 — RF y RNF: el marco de calidad y las estructuras de redacción. Parte 4 — ISO/IEC 25010. Parte 5 — la defensa de requerimientos.

**Marcas:** 🔴 central, evaluable · 🟡 secundario · 🟢 mencionado al pasar · 🕳️ madriguera.

## De dónde venís

De la Parte 1: el encuadre (sos la consultora; el cliente es la Junta; las entrevistas son a la Junta y a los profesores; el destino es elegir entre tres soluciones enlatadas) y la consigna del simulacro. De la clase 01: stakeholders, usuarios y clientes, y el enunciado del centro de entrenamiento con su circuito de fichas, carpetas, lista de espera y planes. De la clase 03, Parte 4: cómo se conduce una entrevista.

---

## 1. 🔴 La mesa

Tu equipo hizo de consultora. Enfrente, otro equipo hizo de **profesores** del centro: los que están en el día a día dando clases, anotando quién llegó, llamando a los de la lista de espera. No de Junta Directiva. Eso importa, porque los profesores tienen sus propios objetivos, y no son los de los dueños.

La guía de preguntas preparada como tarea era corta y estaba armada a la ligera. Eso se notó en la mesa: buena parte de las preguntas salieron sobre la marcha, siguiendo lo que los entrevistados iban diciendo. Y acá viene lo interesante: **eso no fue una anomalía de tu mesa, fue el patrón de todas.** Cuando después se preguntó cuánto habían modificado la entrevista preparada, la respuesta fue "un montón" — porque había preguntas que no estaban bien pensadas, o que quedaron cortas, y porque de una pregunta salían dos o tres de seguimiento que llevaban a lo que de verdad importaba.

Los entrevistados jugaron el personaje a fondo, a veces exagerando: profesores resentidos con la Junta, con sesgos en la lista de espera, con facciones internas. Exagerado o no, es el tipo de entrevistado que existe: el que tiene bronca y la deja salir, el que te da información que no pediste y que sirve, y el que te da información que no pediste y no sirve. Separar una de otra es tu trabajo.

## 2. 🔴 Lo que se relevó, ordenado por tema

En la mesa la información llega desordenada: un tema lleva a otro, una queja abre una pregunta. Lo primero que hace el ingeniero de requisitos después es **ordenarla por tema**. Así queda lo que salió de la entrevista a los profesores. Es el insumo directo de la minuta.

**Registros y tiempo administrativo**
- Todo es papel: fichas, carpetas, lista de espera. Nada centralizado. "Confiamos en el papel."
- Los registros en papel son **el mayor tiempo perdido** de los profesores, que no estudiaron para eso: hicieron el profesorado de educación física, no administración.
- Hay una computadora, con Windows XP. No se usa para esto.
- El único canal es el WhatsApp personal de cada profesor.

**Asistencia**
- La toman los profesores, y en hora pico es imposible hacerlo bien. Hay reclamos de socios a los que no les registraron la asistencia.
- Cuando un socio reclama recuperar una clase que "avisó que faltaba", no hay forma de verificarlo: el aviso quedó en un papelito que se perdió, o nunca se pasó a la lista. No pueden saber si el socio miente.

**Horas pico y horarios**
- Los picos: **de 6 a 8 de la tarde**, y **a las 7-8 de la mañana**. A las 4 de la tarde llegan chicos del colegio.
- Las clases arrancan con 5 a 7 minutos de calentamiento; el que llega tarde no lo hace.
- Hay solapamiento entre la clase que termina y la que empieza: mientras un profesor toma lista, los de la clase siguiente ya están esperando.

**Lista de espera y cupos**
- Cuando se libera un lugar, avisan por WhatsApp personal al primero de la lista, que es física.
- Pero el orden no siempre se respeta: **hay sesgos** — se prioriza a quien cae mejor, o a quien trae algo.
- Cuando una clase no llega a tres inscriptos, avisan por WhatsApp a los dos anotados. A veces se enteran en el momento, y ahí se genera el roce: *"no vuelvo más, me hacés perder el tiempo".*

**Ausencias**
- ¿Por qué pedir aviso con un día de anticipación? Para poder ofrecer el lugar a la lista de espera. Aunque, admiten, con un par de horas alcanzaría.
- Los profesores pedían **penalizar** a los socios que faltan sin avisar. Guardá este punto: es el hallazgo de la sección 3.

**Socios con discapacidad**
- Aparecen sin aviso previo. El profesor se entera al empezar la clase que llegó alguien con bastón o muletas, y tiene que rediseñar la clase en el momento: quince minutos perdidos, y a veces el equipo adaptado ya lo tiene otra clase. **Necesitan saberlo de antemano.**

**Sectores sin profesor (musculación y cardio)**
- La distribución de equipos entre clase y uso libre no es fija: depende de la cantidad de gente en el momento.
- **Cero control** del tiempo de uso ni de la salida. Hay gente que se queda tres horas.

**Pagos**
- También los manejan los profesores, "a veces". No es su trabajo y lo saben.

**Comunicación y clima**
- Falta y mala comunicación, para todos lados: entre profesores (hay grupo entre cuatro, no entre los diez), con la Junta, y con los socios.
- La relación con la Junta es conflictiva: reclamos salariales, aumentos, monotributo, gente que quiere irse. La Junta no quiere contratar personal administrativo.
- ¿Cómo querrían recibir la información si todo estuviera automatizado? Por WhatsApp, pero **separado del personal**: un teléfono de la empresa.

Mirá lo que hay en esa lista: necesidades (saber de antemano quién viene con discapacidad), objetivos (dedicarse solo a dar clase), restricciones (no habrá personal administrativo nuevo), reglas de negocio (menos de tres inscriptos, se cancela), y **conflictos entre stakeholders** (los profesores quieren penalizar a los socios; los socios, según el enunciado, quieren avisar hasta una hora antes; los profesores cobran un bono por clases con cupo completo). Exactamente lo que la consigna pedía identificar.

> **Para el parcial, si te preguntan:** *¿Qué debe hacer el ingeniero de requisitos con la información obtenida en una entrevista?*
> Ordenarla por tema, separando necesidades, objetivos, restricciones, reglas de negocio y conflictos entre stakeholders, y documentarla en una minuta clara y concisa para someterla a la aceptación del entrevistado.

## 3. 🔴 La puesta en común

### 3.1 Lo que faltó al empezar

Primera pregunta después de las entrevistas: *¿hicieron una introducción? ¿Se presentaron? ¿Dijeron qué rol eran?* No. "Pisamos de golpe."

Es importante, y no por cortesía: **para asegurarte de que estás obteniendo la respuesta correcta**. Si el entrevistado no sabe quién sos ni para qué estás ahí, responde a lo que imagina que querés; contás que ya estaba claro el objetivo, y del otro lado preguntaron de onda, sin saber. La presentación fija el marco: quién soy, qué estoy relevando, para qué.

Una corrección que recorrió las mesas mientras entrevistaban: hubo equipos que, en vez de preguntar, **le estaban contando al cliente cómo iba a ser el sistema.** Al revés. *Nosotros relevamos. Preguntamos para obtener información de ellos.* En la entrevista de elicitación, la información fluye del cliente hacia vos. Lo que vos sabés del sistema todavía no existe: se construye con lo que ellos te digan.

### 3.2 El hallazgo: la solución que piden no es la necesidad que tienen

Este es el ejemplo que resume la técnica entera, y salió de una mesa.

Los profesores pedían: **"que se penalice a los socios que faltan."** Es una funcionalidad concreta, un pedido claro. Un entrevistador apurado lo anota como requerimiento y sigue.

Pero alguien preguntó: *¿por qué quieren penalizar las ausencias?*

Respuesta: *porque queremos que avisen con tiempo.*

*¿Y para qué necesitan que avisen con tiempo?*

*Para poder avisarles a los otros socios, a los de la lista de espera, que vengan.*

Entonces la necesidad no es "penalizar". La necesidad es **manejar mejor las asistencias para que los cupos se puedan reasignar**: no perder clases por falta de gente, no tener clases con lugares vacíos que alguien quería. La penalización era la única solución que los profesores imaginaban para esa necesidad — y ni siquiera es buena, porque los socios del enunciado se quejan de la anticipación que se les exige y quieren avisar hasta una hora antes.

Fijate el mecanismo: **pregunta → respuesta → repregunta → necesidad.** La consigna lo decía en abstracto ("cuando un stakeholder proponga una solución, intentá comprender qué necesidad existe detrás"). Esto es lo que se ve en concreto.

> **Para el parcial, si te preguntan:** *Un stakeholder pide una funcionalidad específica durante la entrevista. ¿Qué hace el ingeniero de requisitos?*
> No la registra como requerimiento sin más: repregunta para identificar la necesidad que la motiva. La funcionalidad pedida es una solución que el stakeholder imagina; el requisito surge de la necesidad, que puede admitir otras soluciones mejores.

### 3.3 Preguntas cerradas que abren

Hay preguntas que parecen cerradas y reciben respuesta cerrada — *¿avisan por WhatsApp? Sí.* Pero cada una de esas puede dar pie a más información **si repreguntás**: ¿con el WhatsApp de quién? ¿a quién le avisan primero? ¿y si no contesta? Depende de tu habilidad. Si te quedás callado y te conformás con la primera respuesta, estás en la misma que si no hubieras preguntado.

### 3.4 Cada equipo tuvo un problema distinto

La tarea previa era una entrevista genérica: cuando la diseñaste no sabías cuál era el problema real del cliente. En la mesa, cada equipo recibió una problemática específica dentro del mismo negocio. Resultado: **no todos los ingenieros relevaron el mismo problema**, aunque el contexto fuera idéntico. Eso es realista: dos consultoras que entrevistan a la misma empresa en momentos distintos, o a personas distintas, vuelven con problemas distintos. Por eso la minuta de cada equipo va a ser distinta, y por eso se ponen en común.

### 3.5 Estar del otro lado

Los que hicieron de cliente lo describieron así: *es raro, porque tenés que improvisar, y no sabés cuánta dificultad ponerle al que te entrevista.* Es una buena descripción del entrevistado real, que también improvisa: no tiene un guion, no sabe qué necesitás que te diga, y responde según cómo le preguntes. Haber estado de ese lado te enseña a preguntar del otro.

## 4. 🔴 El cliente que pide la tecnología de moda

Un patrón que va a atravesar tu carrera, contado desde la experiencia de quien lleva décadas relevando: **cuando todos lo tienen, y todos lo quieren, el cliente también lo quiere. ¿Para qué? No sabe. Pero lo quiere.**

Hoy es la inteligencia artificial. Alrededor de 2010 eran las redes sociales: todo tenía que tener un botón de "me gusta", una página de Facebook, si no "no se vendía". Después Instagram. Dentro de unos años será otra cosa. Las modas cambian; el patrón no.

El ingeniero de requisitos tiene que saber decir dos cosas ahí. La primera: *mirá, lo que vos querés hacer, esto no va* — o *esto no es lo que resuelve tu problema.* La segunda, más útil: *veamos cuál es tu punto de dolor.*

**Punto de dolor** (pain point) es el problema concreto que le duele al cliente en su empresa o en su proceso: lo que le cuesta plata, tiempo o clientes hoy.

A veces sirve presentarle soluciones de otros negocios similares: eso le abre la cabeza, le da ideas, lo hace decir *esto me está pasando* o *nada que ver*. Pero siempre desde la necesidad, no desde la moda.

🕳️ **Madriguera — IA en la elicitación**
La cátedra incorpora IA al programa más adelante: la clase del 22/10 compara casos de uso contra escenarios usando herramientas como Elicit y Perplexity. Acá la IA aparece solo como ejemplo de lo que el cliente pide sin saber para qué. *Volvé al camino.*

## 5. 🔴 La corrección del diseño de entrevista: seis criterios

Los diseños de entrevista entregados como tarea volvieron corregidos. De un caso concreto —un equipo que identificó stakeholders, usuarios y clientes, y diseñó cuatro preguntas para los profesores y cuatro para "los clientes"— salieron seis criterios. Cada uno es una regla que vas a necesitar de acá en adelante.

**Criterio 1 — El cliente es quien te paga a vos.**
El equipo puso: *stakeholders: junta directiva, socios y profesores · usuarios: socios y profesores · clientes: socios.* Corrección: **usuarios: junta directiva, socios y profesores · clientes: junta directiva.** *Los socios le pagan al centro de entrenamiento, no a la consultora de software.* Cliente es quien contrata y paga el proyecto. La Junta también es usuaria: va a consultar el sistema.

**Criterio 2 — Un tema, un bloque.**
*Deben mantener un orden en los temas: todas las preguntas del mismo tema en un mismo bloque de la entrevista.* Las cuatro preguntas del equipo saltaban de cupos a medios de pago, a control de efectivo, a presentismo. Cada tema se agota antes de pasar al siguiente; si no, el entrevistado se dispersa y vos perdés el hilo.

**Criterio 3 — Cantidad y profundidad.**
*En general la propuesta es muy pobre en cuanto a la cantidad de preguntas y la información que pueden obtener con ellas.* Cuatro preguntas por entrevista no alcanzan para quince minutos con una persona clave. Y la vara no es cuántas preguntas: es **qué información sale de cada una**. Es el mismo criterio de la Parte 1 §5: antes de cada pregunta, *¿qué voy a sacar de la respuesta?*

**Criterio 4 — No ofrezcas como alternativa lo que ya hacen.**
La pregunta era: *¿Les gustaría contactar ustedes mismos a los socios cuando haya cupo disponible, o prefieren que nuestra solución emita una notificación?* Corrección: *esto es lo que vienen haciendo…* La primera opción es el statu quo, que el enunciado ya describe. La pregunta no releva nada: hay que preguntar qué problemas les trae contactarlos ellos, no si quieren seguir haciéndolo.

**Criterio 5 — Nada de forma impersonal.**
*¿De qué forma **se** controlaban los ingresos y egresos de efectivo?* Corrección: *evitar la forma impersonal del verbo, ya que no queda claro quién será el responsable de ese manejo.* "Se controlaban" no dice quién. Y **quién hace cada cosa es precisamente lo que estás relevando**. La pregunta tiene que forzar la respuesta con sujeto: *¿quién controla los ingresos y egresos de efectivo, y cómo?*

**Criterio 6 — Tiempo presente.**
*¿Se los registra**ban** solo en papel?* Corrección: *¿por qué en tiempo pasado?* El negocio funciona hoy; estás relevando cómo opera ahora. El pasado sugiere algo que ya no existe y confunde al entrevistado.

**Y el criterio que engloba todo — a quién le hacés la segunda entrevista.**
El equipo diseñó preguntas "para los clientes", pensando en los socios. Corrección: *la segunda entrevista era a los dueños, no a los socios o clientes del centro de entrenamiento (¿cómo harían para entrevistar a tantos socios?).* Es el encuadre de la Parte 1 §6 aplicado: dos entrevistas, Junta y profesores; a los socios, cuestionario. Diseñar la entrevista equivocada es perder toda la preparación.

> **Para el parcial, si te preguntan:** *Mencioná criterios para evaluar el diseño de una guía de entrevista.*
> Que identifique correctamente cliente, usuarios y stakeholders; que agrupe las preguntas por tema; que tenga cantidad y profundidad suficientes para obtener información valiosa; que no pregunte por lo que ya se conoce del relevamiento previo; que evite formas impersonales (debe quedar claro quién hace qué); que esté en tiempo presente; y que esté dirigida a la persona correcta.

---

## Info operativa de esta parte

- **La minuta de lo trabajado en la entrevista** es el entregable de la semana siguiente. No se da un formato: se espera criterio propio. Se admite usar IA para armarla, con una condición explícita: **validar lo que escribe** — que los requerimientos estén bien descriptos y que diga todo lo que tiene que decir. La responsabilidad sobre el contenido es de quien firma.
- Los equipos que quedaron diezmados deben repartirse las tareas entre los presentes para poder avanzar.

---

## Qué viene en la Parte 3

Con lo relevado en la mesa, el equipo tuvo cinco minutos para escribir dos o tres requerimientos funcionales y sus no funcionales. Para hacerlo bien hace falta el marco: qué características de calidad tiene que cumplir cualquier requerimiento, cómo se redacta un RF en dos niveles, cómo se redacta un RNF para que sea medible, y qué es una regla de negocio y por qué no es ninguna de las dos cosas.

**FIN DE LA PARTE 2**
