# 📘 APUNTE MAESTRO — Clase 04 · Entrevistas y redacción de requisitos — Parte 1

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Unidad:** `clase04` · Jueves 03/09/2026 · Presencial (Campus)
**Parte 1:** La entrevista antes de sentarte — lo que cuesta, con quién, qué tiene que salir, y el encuadre real del caso.

---

## Sobre esta parte

**Qué cubre:** por qué una entrevista es cara y qué obliga eso · a quién se entrevista y a quién no · la minuta como acuerdo de alcance · las habilidades humanas que la técnica exige (el que no habla, el que habla de más, el problema que no era) · documentar y repreguntar · qué información no va en una entrevista · el encuadre real del integrador (consultora, soluciones enlatadas, dos entrevistas) · la consigna del simulacro.

**Qué viene después:** Parte 2 — la entrevista del simulacro reconstruida como caso, la puesta en común y los criterios de corrección del diseño de entrevista. Parte 3 — RF y RNF: el marco. Parte 4 — ISO/IEC 25010. Parte 5 — la defensa de requerimientos: escribir bien y detectar lo mal escrito.

**Marcas:** 🔴 central, evaluable · 🟡 secundario · 🟢 mencionado al pasar · 🕳️ madriguera.

## De dónde venís

De la clase 03, Parte 4: qué es una entrevista, sus fases, la guía de preguntas, la minuta de seguimiento, escuchar y lenguaje corporal. Todo eso se asume acá; esta clase no lo repite, lo pone en práctica y le agrega la capa que solo aparece cuando hay plata y tiempo en juego. De la clase 03, Parte 3 §5.1: la entrevista al que decide va **antes** del cuestionario a los muchos. De la clase 01: stakeholders, usuarios y clientes.

---

## 1. 🔴 Lo que cuesta una entrevista, y qué obliga eso

Arrancá por el número, porque el número explica el resto.

Para preparar la entrevista del centro de entrenamiento, tu equipo se juntó a partir de un primer relevamiento que les llegó —el enunciado, con una descripción del negocio y del problema— y armó un documento con preguntas. ¿Cuánto llevó? Leer, ponerse de acuerdo, escribir: alrededor de una hora. Una hora por cuatro cabezas. Ahora ponéle precio a la hora de un analista: digamos 50.000 pesos. **200.000 pesos solo para decidir qué le vamos a preguntar al cliente.** Y todavía no entrevistamos a nadie.

Del otro lado de la mesa pasa lo mismo, pero peor: las personas que entrevistás tienen cargos de decisión, y su tiempo vale más que el tuyo. Y con suerte —con suerte— van a responder, van a involucrarse, van a dar la información que necesitás.

De ahí salen tres consecuencias que atraviesan toda la clase:

1. **Cada minuto de entrevista tiene que producir información valiosa, de calidad.** No hay margen para preguntar lo que se podía leer, ni para relevar lo que se podía pedir por escrito.
2. **La entrevista no es una técnica masiva.** No se entrevista a todo el mundo; se entrevista a poca gente, elegida.
3. **Desarrollar la habilidad es parte del trabajo.** Si el analista es de los que se quedan callados ante un entrevistado difícil, esos 200.000 pesos se tiran a la basura: vuelve al líder del proyecto con un "no me quiso decir nada".

Existe una alternativa cuando el problema necesita muchas cabezas a la vez: el **workshop** —el JRP que viste en la clase 03— donde se convoca a gente de distintas áreas, se comparten ideas y experiencias, surge una tormenta de ideas y se trabaja en equipo. Pero no es gratis: tiene su propio costo de elaboración y de implementación, y se esperan resultados de ese costo. Ninguna técnica es barata; lo que cambia es qué comprás con la plata.

> **Para el parcial, si te preguntan:** *¿Por qué la entrevista no se usa de forma masiva?*
> Porque es una técnica cara: requiere tiempo de preparación del analista y tiempo de personas con poder de decisión, cuyo tiempo es costoso. Por eso se reserva para pocas personas clave, y para relevar a muchos se usa el cuestionario.

## 2. 🔴 A quién entrevistás — y a quién no

**Por lo general, no se entrevista al usuario final.** Se entrevista a pocas personas, con roles: cargos de toma de decisión en la empresa o en el negocio. Son los que saben cómo funciona el circuito, cuánto presupuesto hay y hasta dónde quieren llegar.

Bajalo al centro de entrenamiento. ¿A quién le mandarías un cuestionario? A la junta directiva son cuatro o cinco personas: no tiene sentido, a ellos se los entrevista. A los profesores, que son diez: también se los entrevista. **A los socios** —cientos, ficticios en nuestro caso— **se les manda el cuestionario.** Eso es la etapa siguiente del integrador: después de esta entrevista, un cuestionario a los socios.

🕳️ **Madriguera — Google Forms**
Herramienta gratuita de Google para armar formularios que se comparten por link y recopilan las respuestas en una planilla. Se va a usar para el cuestionario del integrador porque todo el mundo la sabe usar y responde fácil. *Volvé al camino — la herramienta no es el tema, el diseño del cuestionario sí.*

Y el orden no es negociable, como viste en la clase 03: **primero la entrevista, después el cuestionario.** Para que lo que le preguntemos a los socios tenga sentido, tiene que ir en línea con lo que nos pide el que paga, que es el centro de entrenamiento. Sin la entrevista, el cuestionario dispara a ciegas.

## 3. 🔴 La minuta como acuerdo de alcance

Ya sabés que la entrevista tiene tres partes: preparación, ejecución y seguimiento con minuta. Lo que esta clase agrega es qué es la minuta *de verdad*, con un caso.

Un especialista de Microsoft venía a un proyecto a capacitar y a hacer definiciones. Después de cada sesión, hacía una minuta. Y la metodología era esta: **la minuta que el cliente no aprobaba, el consultor no volvía.** Sin aprobación, no había sesión siguiente.

¿Por qué tanta rigidez? Porque la minuta **termina siendo el acuerdo**: el acuerdo sobre el alcance que va a tener lo que nosotros planteamos como solución. Todo lo que se dijo en la entrevista, filtrado, escrito, y aceptado por el que decide. Sin ese documento aprobado, cualquier cosa que construyas después se apoya en "me pareció que dijiste".

Por eso, aunque parezca tiempo invertido de más —una reunión, y después un rato escribiendo lo que se dijo en la reunión— no lo es. Es la parte que convierte una conversación en un compromiso.

Tres condiciones de una buena minuta: **clara, concisa, y con los puntos de relevancia.** No es una transcripción; es el destilado de lo que importa, escrito para que el otro lo firme.

> **Para el parcial, si te preguntan:** *¿Cuál es la función de la minuta de una entrevista de elicitación?*
> Documentar lo relevado y obtener la aceptación del entrevistado, de modo que se convierta en el acuerdo sobre el alcance de la solución. Debe ser clara, concisa y contener los puntos relevantes.

## 4. 🔴 Las habilidades humanas: tres escenarios que te van a tocar

La técnica es sencilla de describir y difícil de ejecutar, porque del otro lado hay personas. Estos son los tres escenarios que aparecen una y otra vez, y las habilidades que piden no son técnicas: son humanas, sociales.

**El stakeholder negativo.** Ya lo viste en la clase 01: hay stakeholders a los que el proyecto no les conviene. En la entrevista se manifiesta así: "lo voy a hacer, pero…", da vueltas, se va por las ramas, no entrega la información. Y si vos encima sos callado, tímido, "no digo nada", la combinación es letal: 200.000 pesos de preparación y volvés con las manos vacías. Ahí es donde tiene que surgir la habilidad de sostener la conversación, repreguntar, buscar la información por otro lado.

**El que te cuenta todo.** El escenario opuesto: el entrevistado que te cuenta la vida de su familia, cuánto le costó el auto, y no llega nunca al punto. Acá la habilidad es reencauzar sin cortar el vínculo: *dígame cuál es su problema, qué es lo que podemos resolver.*

**El problema que no era.** Entraste con una hipótesis y en la charla descubrís que la problemática pasaba por otro lado. No es un fracaso de la entrevista; es la entrevista funcionando. Lo que hace falta es la flexibilidad para soltar lo que preparaste y seguir el hilo nuevo.

Estas habilidades se desarrollan **a partir de la práctica**. No hay apunte que las reemplace. Por eso se practica en clase, y por eso los juniors acompañan a personas más senior antes de entrevistar solos: se aprende mirando y haciendo.

**Por qué la práctica es presencial.** Gran parte de lo que pasa en una entrevista es lenguaje corporal —lo viste en la clase 03. Por Zoom se pierde. Y aunque hoy muchas reuniones sean virtuales, no todas lo van a ser; y aun en la virtual hay un aspecto de presentación —"la camisita"— que pesa. La habilidad se entrena en el formato más exigente, que es cara a cara.

## 5. 🔴 Documentar, repreguntar, y qué no va en una entrevista

Hay otra capacidad que este rol exige, y que se subestima: **entender lo que el otro me dice y documentarlo.** No solo escuchar: dejarlo escrito de manera que después sirva. Y tener el reflejo de decir *mirá, esto no quedó claro, te lo repregunto.*

Ahora, hay información que **no amerita tiempo de entrevista**. Cantidad de empleados, cantidad de clientes, cantidad de ventas, volumen de operaciones. Eso son números; salen de un cuestionario, o se piden por escrito, o directamente ya te los dio el enunciado. Gastar minutos de una persona con cargo de decisión en que te dicte cifras es desperdiciar la técnica.

Esto tiene consecuencia directa en la corrección. Varias de las entrevistas que los equipos entregaron como tarea **apuntan más a un cuestionario que a una entrevista**. La pregunta que hay que hacerse antes de cada pregunta es: *¿qué voy a sacar de la respuesta?* Si la respuesta es "5.000 alumnos, 4 profesores, tantas clases por día", eso son números. Una entrevista tiene que sacar otra cosa: el problema, el circuito, quién hace qué, qué pasa cuando algo falla, qué necesita cada uno.

> **Para el parcial, si te preguntan:** *¿Qué tipo de información no conviene relevar mediante entrevista, y por qué?*
> Datos cuantitativos (cantidades, volúmenes, valores), porque no justifican el costo del tiempo de una persona con poder de decisión; se relevan por cuestionario o por documentación. La entrevista se reserva para comprender el problema, los procesos y las necesidades.

## 6. 🔴 El encuadre real del integrador: consultora, soluciones enlatadas, dos entrevistas

Antes de sentarte a la mesa del simulacro necesitás tener claro **quién sos y para qué entrevistás**, porque eso cambia a quién considerás cliente y qué información buscás.

La Junta Directiva del Centro de Entrenamiento Vida Sana tiene una convicción: la excelencia está en sistemas altamente probados, con experiencia en el mercado, **no en desarrollos a medida.** Otros centros de la competencia implementaron soluciones probadas con éxito. Y la Junta mira hacia adelante: quieren expandirse —abrir sucursales, sumar actividades— y quieren que el soporte informático ya los acompañe en esa etapa.

Por eso lo que piden **no es que les construyan un sistema**: piden que, ante el problema detectado, se encuentre la solución técnica más conveniente **de un universo de 3 posibles soluciones enlatadas** que estén en condiciones de soportar la operatoria y su ampliación a otras sucursales.

**Solución enlatada** es un producto de software ya existente, que se compra o se contrata y se configura, en vez de desarrollarse desde cero para un cliente.

Y vos, en este proyecto, **sos la consultora**. Para poder avanzar con el análisis, el relevamiento y la selección, la consultora decidió diseñar **dos entrevistas: una con la Junta Directiva y otra con los profesores**, para identificar requerimientos funcionales y no funcionales, y cualquier otra restricción que impacte en la selección de las soluciones. Ese diseño se pone a consideración del líder del proyecto.

Dos cosas se desprenden de este encuadre y vuelven en la Parte 2 cuando veas la corrección del entregable:

- **El cliente de la consultora es la Junta.** Los socios le pagan al centro de entrenamiento, no a la consultora. Son usuarios y stakeholders del sistema; no son tu cliente.
- **Las dos entrevistas son a la Junta y a los profesores.** No a los socios: a los socios no se los puede entrevistar uno por uno, y para eso está el cuestionario que viene después.

Y una tercera, más de fondo: cuando el destino es elegir entre productos existentes y no construir uno, los requerimientos no funcionales dejan de ser solo "cómo tiene que comportarse lo que construyo" y pasan a ser **criterios de selección**: lo que cada solución enlatada cumple o no cumple. Eso hace que redactarlos bien —medibles, verificables— importe todavía más. Se desarrolla en la Parte 3.

## 7. 🔴 La consigna del simulacro

Cada equipo recibió un rol. A unos les tocó la Junta Directiva; a otros, los profesores; a otros, la consultora —el ingeniero o ingeniera de requisitos. Cinco minutos para ponerse de acuerdo dentro del equipo sobre qué rol juega cada uno, y después los equipos se enfrentan: entrevistadores de un lado de la mesa, entrevistados del otro. Todas las entrevistas en paralelo, unos quince minutos.

**Para los que entrevistan**, la consigna es esta. Sos el ingeniero de requisitos encargado de entrevistar a representantes de un centro de entrenamiento que quiere desarrollar una nueva aplicación. Tu equipo recibió únicamente este contexto: el centro quiere una aplicación para mejorar la gestión de sus actividades; participan de la entrevista personas de la junta directiva y profesores. **No conocés de antemano cuáles son los problemas que tienen ni qué esperan del sistema.** Tu objetivo es realizar una entrevista de elicitación de requisitos. Durante los quince minutos:

- Poné a prueba la entrevista que preparaste como tarea.
- No te limites a seguir la lista de preguntas si la conversación pide profundizar en otro tema.
- **Intentá comprender el problema antes de asumir una solución.**
- Prestá atención a quién realiza cada actividad, qué información utiliza y qué sucede cuando algo cambia o sale mal.
- Identificá necesidades, objetivos, restricciones, reglas de negocio y posibles conflictos entre stakeholders.
- **Cuando un stakeholder proponga una funcionalidad o una solución, intentá comprender qué necesidad existe detrás.**
- No asumas que todos los stakeholders tienen los mismos objetivos.
- No presupongas que una afirmación del cliente es técnicamente correcta.
- Detectá ambigüedades y pedí ejemplos concretos cuando haga falta.
- Buscá llegar a requisitos funcionales suficientemente concretos como para documentarlos después.

Al terminar tenés que poder identificar **al menos dos requisitos funcionales concretos** y tener una comprensión razonable del problema que el cliente intenta resolver. Y una advertencia que resume todo: **tu trabajo no es diseñar la aplicación durante la entrevista. Tu trabajo es entender qué necesita el cliente.**

**Para los que hacen de cliente**, la consigna es la inversa, y es la más difícil de cumplir para un estudiante de ingeniería: **olvidate de que sos ingeniero.** Nunca un cliente te va a pedir "una base de datos que tenga…". El cliente verdadero dice: *quiero esto, que me salga barato, y lo quiero para la semana que viene* — y que el ingeniero se las arregle. Creerse el personaje hace que la dinámica sea rica: en cursadas anteriores hubo un tambero que no soltaba el botón de su problema, y un dueño de negocio que se puso a hablar de la factura de luz mientras los entrevistadores intentaban desesperadamente volver al sistema. Eso es lo que pasa en una entrevista real.

**Lo que tiene que salir de la mesa.** Dos o tres requerimientos funcionales, ya escritos como se vio en las primeras clases, y **al menos un requerimiento no funcional que restrinja a cada uno de esos funcionales** — que diga cómo se puede implementar ese funcional, bajo qué condición. ¿Por qué dos o tres y no uno? Para que no se repitan entre equipos: en la segunda parte de la clase se ponen en común, y con variedad la puesta en común sirve.

Además, cada equipo tuvo una problemática distinta dentro del mismo negocio: la consigna que recibió cada mesa estaba pensada para que no todos los ingenieros relevaran el mismo problema. Vas a ver la consecuencia en la Parte 2.

---

## Info operativa de esta parte

- **Próxima etapa del integrador:** cuestionario a los socios, con Google Forms. Se diseña después de la entrevista, en línea con lo que pide la Junta.
- **Formato de examen, a confirmar:** se mencionó que "el día del examen" las entrevistas se harían una a continuación de la otra, con el resto escuchando, en vez de todas en paralelo. ⚠️ Es una mención al pasar; no está confirmado en qué instancia ni con qué peso. Verificar antes de asumirlo.

---

## Qué viene en la Parte 2

Te sentás a la mesa. La entrevista de tu equipo a los profesores, reconstruida como caso: qué salió, qué se improvisó, qué información apareció y por qué. Después, la puesta en común: los errores que se señalaron, el hallazgo que resume el sentido de toda la técnica —la solución que el stakeholder pide no es la necesidad que tiene— y los seis criterios de corrección que dejó la devolución del diseño de entrevista.

**FIN DE LA PARTE 1**
