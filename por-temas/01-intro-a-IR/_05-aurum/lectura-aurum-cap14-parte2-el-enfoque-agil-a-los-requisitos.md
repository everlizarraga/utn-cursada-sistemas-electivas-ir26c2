# Lectura en español — Cap. 14 · Parte 2: El enfoque ágil a los requisitos

> **Origen.** Capítulo 14, secciones 14.4 a 14.7, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Alberto Sillitti y Giancarlo Succi**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1.** Se asumen conocidos el principio del desperdicio, los cuatro valores y los límites de tamaño.

---

## 1. El cliente único 🔴

### La jugada

> En los métodos ágiles **el cliente asume un papel primordial.** Usualmente el término "cliente" identifica **un conjunto de interesados** de la organización que paga el desarrollo. En ese caso, la interacción con ellos **es compleja por las percepciones distintas del problema que tienen.**

Y acá viene la maniobra característica de lo ágil:

> **En los métodos ágiles, el problema de los múltiples interesados SE RESUELVE REDUCIENDO SU NÚMERO A UNO: una sola persona que representa a todos los interesados involucrados.**
>
> **Ese cliente debería ser un experto del dominio y capaz de tomar decisiones importantes**, como aceptar el producto o priorizar requisitos.

**Y qué pasa cuando no hay quién pague directamente:**

> En el caso de **productos masivos** para los que no hay una organización pagando directamente, **el equipo tiene que identificar un experto en el área —por ejemplo un experto en comercialización— que pueda ACTUAR COMO el cliente** y participar del desarrollo.

**Con una condición que se repite todo el capítulo:**

> **Este enfoque es factible SOLO SI el tamaño del problema es limitado y una sola persona puede actuar como cliente, representando a todos los interesados. Si el tamaño no lo permite, el equipo tiene que usar otras técnicas** para elicitar y gestionar requisitos.

> ⚠️ **Cruce con la cátedra.** Vale la pena ver esto con la lente del capítulo 2: allí se decía que **los interesados críticos para el éxito son los que pueden acordar Y SOSTENER el acuerdo**, y que la identificación de interesados es una actividad completa con su propio método.
>
> **Lo ágil no resuelve ese problema: lo esquiva por decreto.** Declara que hay uno solo y le asigna la responsabilidad de representar a todos. Eso funciona mientras el supuesto se sostenga — y el propio capítulo admite que solo se sostiene en problemas chicos.

### Las tres exigencias al cliente en el sitio 🔴

Cuando el cliente es miembro del equipo y está siempre disponible, se le piden tres cosas:

| Exigencia | Qué implica |
|---|---|
| **Disponibilidad** | **Tiene que estar siempre disponible para responder las preguntas del equipo. Cualquier demora en la respuesta DEMORA EL DESARROLLO** |
| **Conocimiento completo** | Es el representante de todos los interesados; por lo tanto **debe poder responder todas las preguntas**, ya que es el experto del dominio y sabe cómo debería funcionar la aplicación y qué datos de entrada y salida hacen falta |
| **Poder de decisión** | **Puede tomar decisiones y compromisos finales.** Cambios en los requisitos, aceptación de las funcionalidades implementadas, se deciden directamente, **permitiendo un proceso de decisión rápido** |

**Y la dificultad práctica, admitida:**

> **Tener acceso a un cliente capaz de satisfacer todos estos requisitos NO ES FÁCIL, ya que tiene que ser un miembro del personal muy valioso.**
>
> **La disponibilidad de este tipo de cliente es de importancia primordial, ya que la mayoría de los beneficios de los métodos ágiles —reducción de documentación, entrega incremental— ESTÁN ESTRECHAMENTE ACOPLADOS con la participación del cliente.**

> ⚠️ **Cruce con la cátedra — esto conecta directo con el capítulo 11.** Allí el estudio empírico mostraba que **los equipos con el cliente disponible desde el principio resolvían mal el 20 % de las ambigüedades, y los que lo tenían solo al final, el 37 %.**
>
> Lo ágil apuesta todo a esa variable: **si el cliente está siempre disponible, la desambiguación es inmediata y no hace falta documentar para prevenirla.** El razonamiento es correcto. Lo frágil es el supuesto — y el capítulo lo dice: conseguir una persona así **no es fácil**, y una implementación pobre de esta práctica **reduce la efectividad de varios métodos ágiles a la vez.**

---

## 2. El desperdicio en los requisitos 🔴

### Por qué se ataca desde el principio

> **Identificar y reducir el desperdicio DE LOS REQUISITOS asume un papel primordial, para evitar la creación de desperdicio más adelante.** En las prácticas esbeltas, la reducción del desperdicio es extremadamente importante porque **EL DESPERDICIO SIEMPRE GENERA MÁS DESPERDICIO.**

El ejemplo de fábrica que dan lo aclara:

```
   una fábrica produce MÁS de lo que los clientes piden
   (primera pieza de desperdicio)
        ↓ genera
   un depósito
        ↓ genera
   gente y procesos para gestionar el depósito
        ↓ genera
   gente y procesos para gestionar la interacción entre
   la fábrica y el depósito
```

> **La introducción de desperdicio en las fases tempranas causa la creación de más desperdicio después, el incremento de la complejidad, y la DRENAJE DE RECURSOS disponibles para el negocio central de la empresa.**
>
> Por eso, **optimizar una sola actividad produce más ahorro que el ahorro directo de esa actividad**, y contribuye a optimizar todo el proceso.

### Los efectos del desperdicio en requisitos 🔴

La lista completa de lo que causa un requisito de más:

```
   · más código fuente que escribir y MAYOR COSTO
   · mayor complejidad del código
   · entrega DEMORADA de la versión final con todas
     las funcionalidades
   · mantenimiento más complejo y costoso
   · más recursos consumidos por la aplicación:
     memoria, procesamiento, red
   · mayor complejidad DESDE EL PUNTO DE VISTA DEL
     CLIENTE: interfaz más compleja, más esfuerzo
     para aprender a usar la aplicación
   · los AHORROS que la aplicación produciría en el
     proceso productivo del cliente SE DEMORAN
```

**Y el efecto de segunda vuelta:**

> **Al final, todo el desperdicio generado es un costo para el cliente, directa e indirectamente. Esos costos probablemente generen MÁS desperdicio DENTRO DE LA ORGANIZACIÓN DEL CLIENTE**, por la reducción del dinero disponible para su negocio central y la reducción de sus ingresos.

### Las dos clases de desperdicio 🔴

> **El desperdicio en requisitos incluye tanto requisitos EQUIVOCADOS como requisitos INÚTILES.**

Y cada clase tiene su causa y su contramedida.

#### Los requisitos equivocados: causa y remedios

> **Un malentendido entre el cliente y el equipo causa requisitos equivocados.**

Las cuatro técnicas ágiles para reducir esa probabilidad:

| Técnica | Cómo funciona |
|---|---|
| **Todo el equipo recolecta los requisitos** | Así **el uso de documentos para compartir conocimiento se reduce al mínimo y la probabilidad de malentendidos disminuye** |
| **Los requisitos se recolectan en un lenguaje común** | **Se usa el lenguaje DEL CLIENTE, no un lenguaje formal de especificación.** Eso significa que **los desarrolladores tienen que introducirse en el dominio del cliente para entenderlo** |
| **Interacción directa, sin intermediarios** | **No hay intermediarios entre el equipo y el cliente.** Reduce tanto la cantidad de documentos requeridos como **la probabilidad de malentendido por capas de comunicación innecesarias** |
| **División de requisitos** | Si el equipo considera **un requisito demasiado complejo**, esta técnica **ayuda al cliente a dividirlo en otros más simples.** Eso **ayuda a los desarrolladores a entender mejor** las funcionalidades pedidas |

> ⚠️ **Cruce con la cátedra.** Las cuatro son transferibles a tu trabajo en equipo, y la segunda es la más importante: **usar el lenguaje del cliente, no el propio.** Eso es exactamente la brecha cultural del capítulo 2 atacada desde el lado del que construye — **la carga de aprender el vocabulario recae en el desarrollador, no en el cliente.**
>
> Y la cuarta —dividir lo que es demasiado complejo— tiene una justificación que conviene notar: **no se divide para facilitar la estimación, se divide PARA ENTENDER MEJOR.** Si un requisito no se puede partir en piezas comprensibles, probablemente no se lo entendió.

**Y otra vez el límite:**

> **Este enfoque NO ESCALA: es factible solo si el tamaño del equipo es limitado.** Si no, hace falta introducir un representante y documentación adicional. **En caso de proyectos grandes, los métodos ágiles no proveen ninguna solución específica.**

#### Los requisitos inútiles: causa y remedios 🔴

> **Incluso si el cliente es un experto en su propio dominio, identificar las funcionalidades que realmente necesita NO ES FÁCIL. A menudo los clientes SOBRE-ESPECIFICAN la aplicación, incluyendo un rango amplio de funcionalidades que no dan beneficio real a su negocio.** Esos requisitos son inútiles y por lo tanto son desperdicio.

Las dos contramedidas:

- **Priorización de requisitos** — cliente y equipo asignan prioridades para identificar las funcionalidades más importantes.
- **Versiones incrementales** — se entregan en tandas chicas y frecuentes, para recolectar retroalimentación.

### Los cuatro pasos de la priorización ágil 🔴

Y acá hay un procedimiento concreto que vale la pena:

```
   1. EL EQUIPO estima el tiempo requerido para implementar
      cada funcionalidad. SI EL ESFUERZO ES DEMASIADO ALTO,
      el requisito SE DIVIDE en otros más simples que
      puedan implementarse con menos esfuerzo.

   2. EL CLIENTE especifica las PRIORIDADES DE NEGOCIO
      de cada funcionalidad.

   3. EL EQUIPO asigna un FACTOR DE RIESGO a las
      funcionalidades, según esas prioridades de negocio.

   4. CLIENTE Y EQUIPO JUNTOS identifican las
      funcionalidades a implementar en la iteración.
```

**Y se repite entero al comienzo de cada iteración**, junto con la elicitación.

> **De esta manera es posible identificar los requisitos que NO PROVEEN SUFICIENTE VALOR al cliente, para descartarlos y enfocarse en los más importantes.**

> ⚠️ **Cruce con la cátedra.** Fijate en el reparto de responsabilidades, que es lo más instructivo del procedimiento:
>
> - **el esfuerzo lo estima quien va a construir** (el cliente no sabe cuánto cuesta)
> - **la prioridad de negocio la fija quien conoce el negocio** (el equipo no sabe qué vale más)
> - **la decisión final es CONJUNTA**
>
> Es la misma división que pedía el capítulo 4 al exigir que estén representados clientes, desarrolladores y finanzas: **cada perspectiva aporta información que las otras no pueden producir.**

---

## 3. La evolución de los requisitos 🔴

### Las tres hipótesis 🔴

> Los métodos ágiles asumen que **es muy difícil elicitar todos los requisitos del usuario POR ADELANTADO, al comienzo del proyecto.** También asumen que **esos requisitos evolucionan en el tiempo**, ya que el cliente puede cambiar de opinión o el entorno técnico y socioeconómico puede evolucionar.

Las tres hipótesis sobre las que se apoya todo:

```
   1. Los requisitos NO SE CONOCEN BIEN al comienzo
   2. Los requisitos CAMBIAN
   3. HACER CAMBIOS NO ES CARO
```

### La tercera hipótesis, discutida 🔴

Y acá el capítulo hace algo que conviene destacar: **discute su propia tercera hipótesis.**

> Los métodos ágiles asumen que **el costo de introducir cambios en un producto es CASI CONSTANTE a lo largo del tiempo. PERO ESTA HIPÓTESIS NO ES VERDADERA EN TODO CONTEXTO.**
>
> **Usualmente, el costo de implementar cambios CRECE EXPONENCIALMENTE con el tiempo.**
>
> **Por otro lado, si las fases de desarrollo se agrupan en iteraciones muy cortas y las decisiones vinculantes se toman lo más tarde posible, el crecimiento de los costos SE LIMITA.**

```
   COSTO DEL CAMBIO
   ↑
   │        ╱  la curva tradicional:
   │      ╱    crece exponencialmente
   │    ╱
   │  ╱
   │─────────  lo que lo ágil ASPIRA a lograr:
   │           casi constante
   └──────────────────► TIEMPO

   ¿cómo? iteraciones MUY CORTAS + decisiones
   vinculantes DEMORADAS lo más posible
```

> ⚠️ **Cruce con la cátedra.** Esta es una tensión de fondo entre este capítulo y el resto del libro, y vale tenerla identificada.
>
> **El capítulo 8** decía que un problema de requisitos puede costar **hasta 100 veces más** si se detecta en operación. **El capítulo 1** daba la escalera de Boehm: 1 dólar en requisitos, 200 después de entregado. Ambos asumen la curva exponencial.
>
> **Este capítulo no niega esa curva** — dice que es la habitual. Lo que sostiene es que **el achatamiento no es automático: es consecuencia de dos prácticas concretas** (iterar muy corto y demorar las decisiones vinculantes). Sin esas prácticas, la curva exponencial se aplica igual.
>
> Dicho de otro modo: **lo ágil no dice que arreglar tarde sea barato. Dice que si iterás cada dos semanas, nunca es "tarde".**

### Los contratos 🟡

> Para gestionar la evolución, los métodos ágiles usan **contratos de alcance variable y precio variable.** Eso significa que **las funcionalidades realmente implementadas y su costo evolucionan también.**
>
> **Los requisitos no se especifican en detalle a nivel de contrato, sino que se definen paso a paso durante el proyecto, mediante un proceso de negociación** entre cliente y equipo.

### Las dos maneras de gestionar la variabilidad 🔴

**1. Desacoplar los requisitos.**

> **Los requisitos tienen que ser LO MÁS INDEPENDIENTES POSIBLE**, para identificar claramente qué implementar y **volver IRRELEVANTE el orden de su implementación.**

**2. Elicitar y priorizar en cada iteración.** Y acá hay un mecanismo concreto para lo que no entra:

```
   al comienzo de CADA iteración se recolectan y
   priorizan requisitos

   si un requisito es MUY IMPORTANTE
        → se agenda para la iteración próxima
   si NO
        → QUEDA EN ESPERA

   en la iteración siguiente, los que están en espera
   SE REEVALÚAN y, si SIGUEN SIENDO VÁLIDOS, vuelven a
   la lista de candidatos junto con los nuevos

   si un requisito nunca es suficientemente importante,
   QUEDA EN ESPERA INDEFINIDAMENTE
```

**Por qué eso importa:**

> **Este enfoque permite identificar los requisitos más importantes DURANTE TODO EL PROYECTO, no solo al comienzo. Requisitos que no se consideraban muy importantes al principio PUEDEN VOLVERSE RELEVANTES en alguna etapa.**
>
> Además, **el desacoplamiento permite implementar las funcionalidades en casi cualquier orden; por lo tanto se implementan principalmente SEGÚN SU PRIORIDAD, no según sus dependencias funcionales.**

> ⚠️ **Cruce con la cátedra.** Ese último punto es la respuesta ágil al problema del capítulo 5: allí se decía que **no siempre se pueden elegir los requisitos de mayor prioridad, porque las dependencias obligan a implementar antes uno costoso y poco prioritario.**
>
> Lo ágil no resuelve el problema — **lo previene, exigiendo que los requisitos se desacoplen desde el diseño.** Es una jugada elegante: en vez de administrar las dependencias, tratar de que no existan. Y como toda prevención, funciona en la medida en que el dominio lo permita.

---

## 4. Los requisitos no funcionales: el punto débil 🔴

Esta sección es corta y es la autocrítica más fuerte del capítulo.

> **Los métodos ágiles NO PROVEEN NINGUNA TÉCNICA AMPLIAMENTE ACEPTADA para elicitar y gestionar requisitos no funcionales. Esos requisitos se recolectan IMPLÍCITAMENTE durante la actividad de recolección.**

**El argumento de por qué eso sería aceptable:**

> **La necesidad de especificar requisitos no funcionales es menos importante que en otros contextos, por la interacción continua con el cliente.** Después de cada iteración el producto se entrega y el cliente puede probarlo. **Si identifica problemas de cualidades no funcionales, el equipo puede adaptar el sistema en la iteración siguiente sin afectar demasiado el cronograma.**

**Y el problema con ese argumento, que los propios autores señalan:**

> **A menudo el cliente NO PERCIBE COMO DE ALTO IMPACTO muchos requisitos no funcionales** —escalabilidad, seguridad. **Eso puede afectar profundamente la entrega de la versión final, por lo que el equipo tiene que GUIAR AL CLIENTE para identificar esas necesidades ocultas.**
>
> **Este enfoque a los requisitos no funcionales PUEDE REPRESENTAR UN RIESGO MAYOR para los métodos ágiles, ya que carecen de técnicas específicas para su gestión.**

> ⚠️ **Cruce con la cátedra.** Este es el punto donde el enfoque ágil es más vulnerable, y la razón se entiende mirando lo que viste antes.
>
> **Todo el mecanismo ágil descansa en que el cliente detecte los problemas al probar el producto.** Eso funciona bien para lo funcional: si falta algo o hace algo raro, se nota al usarlo. **Pero un problema de escalabilidad no se nota probando con diez registros**, y uno de seguridad no se nota hasta que alguien lo explota.
>
> Y hay una razón estructural: recordá del capítulo 4 que **los requisitos no funcionales afectan varias funciones a la vez, o el sistema entero** — mientras que lo ágil trabaja partiendo el sistema en piezas chicas e independientes. **Lo transversal es justamente lo que ese método no ve.**

---

## 5. Los tres roles 🟡

### El cliente

> **Su presencia es extremadamente importante, ya que la cantidad de documentación se reduce al mínimo y el equipo pide seguido clarificaciones.**
>
> **La presencia constante del cliente REEMPLAZA la mayor parte de la documentación** que se requeriría para describir los requisitos en detalle, y **su contribución es un factor clave del éxito.**

Con la advertencia ya dicha: **una implementación pobre de la práctica del cliente en el sitio puede reducir la efectividad de varios métodos ágiles.**

### Los desarrolladores 🔴

> Todo el equipo participa de la gestión del cliente, recolectando y negociando requisitos. **Por estas razones, las habilidades requeridas de los desarrolladores en equipos ágiles NO SON COMUNES:** tienen que ser muy buenos desarrolladores, poder trabajar en equipo, **e interactuar con el cliente USANDO EL LENGUAJE DE ÉL.**

**Y una responsabilidad que se declara poco:**

> **Como los métodos ágiles se enfocan en esta interacción, EL EQUIPO DE DESARROLLO TIENE LA RESPONSABILIDAD DE EDUCAR AL CLIENTE.**

**El papel de la confianza:**

> **La confianza entre el equipo y el cliente asume un papel primordial. El equipo tiene que proveer software funcionando y de alta calidad EN CADA ITERACIÓN, para recolectar retroalimentación valiosa.**

Y el beneficio es de ida y vuelta:

```
   DESARROLLADORES ──► recolectan información útil para
                       EVITAR implementar funcionalidades
                       inútiles que aumentan el desperdicio

   CLIENTES ─────────► pueden USAR (o al menos probar) el
                       producto unas pocas semanas después
                       del inicio del proyecto
```

### Los gerentes 🟡

> **Los gerentes tienen que crear y sostener un marco para el establecimiento de una interacción productiva entre el equipo y el cliente.** Lo logran **identificando a las mejores personas para incluir en un equipo ágil, promoviendo la colaboración, y negociando los contratos.**

Y su tarea más específica: **los contratos de alcance y precio variables** dependen de **la habilidad del gerente al definirlos**, para satisfacer al cliente y permitir la máxima flexibilidad.

---

## 6. Las herramientas 🟡

Y acá el capítulo tiene una de las frases más memorables:

> **Las herramientas más populares para ingeniería de requisitos en varios métodos ágiles son PAPEL, LÁPIZ Y UN TABLERO DE CORCHO.**

### Las historias de usuario 🔴

> En Programación Extrema los requisitos se recolectan mediante **historias de usuario: descripciones extremadamente cortas de UNA SOLA funcionalidad que el equipo tiene que implementar. Se escriben en papelitos del tamaño de una postal y se cuelgan en un tablero.**

**Y el tablero se divide en tres secciones:**

```
   ┌──────────────┬──────────────┬──────────────┐
   │  historias   │  historias   │  historias   │
   │  POR         │  EN CURSO    │  TERMINADAS  │
   │  IMPLEMENTAR │              │              │
   └──────────────┴──────────────┴──────────────┘

   → provee una REPRESENTACIÓN VISUAL del estado
     del proyecto
```

> ⚠️ **Cruce con la cátedra.** Comparalo con **la escalera de salmones del capítulo 13**: ocho estados, cada uno con sus atributos, en un repositorio con herramienta. Acá son **tres estados en un corcho.**
>
> Y las dos soluciones son correctas para su contexto. La diferencia no es de sofisticación: **es de volumen y de distancia.** Con veinte historias y un equipo en la misma sala, el corcho gana; con ocho mil requisitos y equipos en tres países, el corcho no existe.
>
> Es el mismo principio que atraviesa toda la serie: **la herramienta correcta depende del contexto, no de cuán avanzada sea.**

### Las herramientas que sí se usan 🟢

Aunque muchos equipos ágiles no usan herramientas informáticas, algunas sirven:

**De propósito general:**

| Herramienta | Para qué |
|---|---|
| **Modelado UML** | Dos usos: **(1) escribir una descripción de alto nivel** de la aplicación; **(2) hacer ingeniería inversa del código para crear documentación** |
| **Negociación de requisitos** | Ayudan a **identificar, priorizar y gestionar requisitos** |
| **Mensajería instantánea** | Útiles para **mantener el contacto con el cliente y discutir requisitos CUANDO NO ESTÁ EN EL SITIO** |

**Específicas:** herramientas de gestión de proyecto enfocadas en prácticas ágiles, que **ayudan a almacenar y recuperar los documentos de requisitos —las historias de usuario— en formato electrónico.**

> Notá el segundo uso de UML: **ingeniería inversa del código para generar documentación.** Es coherente con el valor de "software funcionando por encima de documentación" — **la documentación se deriva del código, no al revés.** Y es exactamente lo contrario de lo que decía el capítulo 6 sobre gestionar el cambio jerárquicamente, de los requisitos hacia abajo.

---

## 7. Conclusiones del capítulo 🔴

Los autores cierran con honestidad:

> **Como estos métodos son nuevos, el tema sigue evolucionando y muchas técnicas están bajo investigación. Los métodos ágiles parecen ser un enfoque valioso para UN SUBCONJUNTO RELEVANTE de proyectos, pero SUS LÍMITES NO ESTÁN BIEN DEFINIDOS TODAVÍA.**

**La diferencia de fondo:**

> **La principal diferencia entre métodos ágiles y tradicionales es LA PARTICIPACIÓN DEL CLIENTE en el proceso de desarrollo. AMBOS ENFOQUES PRESENTAN BENEFICIOS Y DESVENTAJAS.**

Y el balance final, que es equilibrado:

| | Dónde funciona | Dónde no |
|---|---|---|
| **Métodos ágiles** | **Gestionan efectivamente los requisitos en proyectos CHICOS** | **No en los grandes** |
| **Métodos tradicionales** | **Gestionan efectivamente proyectos GRANDES** | **Su sobrecarga no es adecuada para los chicos** |

> ⚠️ **Cruce con la cátedra.** Ese cierre es la conclusión más útil del capítulo para un parcial: **la pregunta no es cuál método es mejor, sino para qué tamaño y qué dominio.**
>
> Y notá que **la variable que separa a los dos no es la tecnología ni la moda: es cuánta comunicación directa es posible.** Cuando todos pueden hablar con todos y con el cliente, la documentación es sobrecarga. Cuando no, es lo único que mantiene al proyecto entero.

---

## Mapa de la Parte 2

```
   EL CLIENTE ÚNICO
   el problema de múltiples interesados se resuelve
   REDUCIÉNDOLOS A UNO
   exigencias: disponibilidad · conocimiento completo
   · poder de decisión
   → conseguir esa persona NO ES FÁCIL, y de ella
     dependen casi todos los beneficios

   ─────────────────────────────────────────────

   EL DESPERDICIO EN REQUISITOS
   el desperdicio SIEMPRE GENERA MÁS DESPERDICIO

   EQUIVOCADOS (por malentendido)          INÚTILES
   → todo el equipo elicita                (el cliente
   → LENGUAJE DEL CLIENTE                   sobre-especifica)
   → sin intermediarios                    → priorizar
   → dividir lo complejo                   → entregar
     PARA ENTENDER                           incremental

   PRIORIZACIÓN EN 4 PASOS
   1. el EQUIPO estima esfuerzo (y divide si es mucho)
   2. el CLIENTE fija prioridad de negocio
   3. el EQUIPO asigna riesgo
   4. AMBOS deciden qué entra en la iteración

   ─────────────────────────────────────────────

   LAS 3 HIPÓTESIS
   los requisitos no se conocen · cambian ·
   CAMBIARLOS NO ES CARO ← esta es discutible:
   la curva es exponencial, y se achata SOLO con
   iteraciones muy cortas + decisiones demoradas

   VARIABILIDAD: desacoplar requisitos + re-priorizar
   cada iteración (lo no elegido queda EN ESPERA
   y se reevalúa)

   ─────────────────────────────────────────────

   ══► EL PUNTO DÉBIL: LOS NO FUNCIONALES ◄══
   no hay técnica aceptada; se recolectan implícitamente
   el argumento: el cliente los detecta al probar
   el problema: escalabilidad y seguridad NO SE NOTAN
   probando — y son transversales, justo lo que un
   método que parte en piezas chicas no ve

   ─────────────────────────────────────────────

   HERRAMIENTAS: papel, lápiz y un corcho
   3 columnas: por implementar · en curso · terminadas

   CIERRE: ágil sirve para proyectos CHICOS,
   tradicional para GRANDES. La variable que separa
   es CUÁNTA COMUNICACIÓN DIRECTA ES POSIBLE.
```

---

## Preguntas para chequear que quedó

1. ¿Cómo resuelven los métodos ágiles el problema de los múltiples interesados? ¿Bajo qué condición funciona?
2. ¿Qué se hace cuando no hay una organización que pague directamente por el producto?
3. Nombrá las tres exigencias al cliente en el sitio y por qué cada una importa.
4. ¿Por qué es riesgoso que tantos beneficios dependan de la disponibilidad del cliente?
5. Explicá por qué el desperdicio genera más desperdicio, con el ejemplo de la fábrica.
6. Nombrá cinco efectos del desperdicio en los requisitos.
7. Diferenciá requisitos equivocados de requisitos inútiles. ¿Qué causa cada uno?
8. Nombrá las cuatro técnicas contra los requisitos equivocados.
9. ¿Por qué se recolectan los requisitos en el lenguaje del cliente y no en uno formal? ¿Qué carga impone eso a los desarrolladores?
10. ¿Para qué se divide un requisito demasiado complejo, según este capítulo?
11. Describí los cuatro pasos de la priorización ágil. ¿Quién hace qué y por qué?
12. Nombrá las tres hipótesis sobre las que se apoya la gestión ágil de requisitos.
13. ¿Cuál de las tres discuten los propios autores? ¿Qué dicen que pasa realmente y bajo qué condiciones se achata la curva?
14. ¿Cómo se relaciona eso con la escalera de costos de Boehm del capítulo 1?
15. ¿Qué es un contrato de alcance y precio variables?
16. Nombrá las dos maneras de gestionar la variabilidad.
17. ¿Por qué desacoplar requisitos permite implementarlos por prioridad y no por dependencias? ¿Con qué problema del capítulo 5 se conecta?
18. Explicá el mecanismo de "quedar en espera" y por qué permite identificar requisitos importantes durante todo el proyecto.
19. ¿Cuál es el punto débil de los métodos ágiles respecto de los requisitos no funcionales?
20. ¿Por qué el argumento de "el cliente los detecta al probar" no alcanza para escalabilidad y seguridad?
21. ¿Qué responsabilidad tiene el equipo respecto del cliente, según la sección de roles?
22. ¿Cuáles son las herramientas más populares y cómo se organiza el tablero?
23. ¿Para qué se usa UML en un contexto ágil? ¿En qué se diferencia del uso tradicional?
24. Según el cierre, ¿para qué tipo de proyecto sirve cada enfoque, y cuál es la variable que los separa?

---

**FIN DEL CAPÍTULO 14 — PARTE 2**

**FIN DEL CAPÍTULO 14**

*Sigue el capítulo 15: ingeniería de requisitos para sistemas de información basados en web, en 2 partes.*
