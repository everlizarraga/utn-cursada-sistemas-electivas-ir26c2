# 📘 APUNTE MAESTRO — Clase 01 · Parte 1

## Conceptos fundamentales: el negocio, sus roles y de dónde salen los requisitos

---

### Qué cubre esta parte

El marco completo de la materia y el primer bloque conceptual: qué es la Ingeniería de Requisitos, qué es un negocio y por qué hay que entenderlo antes de escribir una sola línea de especificación, y quiénes son los que tienen la información que necesitamos — usuarios, clientes y stakeholders.

Cierra con el régimen de la cursada: cómo se evalúa, cómo se entrega y qué hay que tener hecho para la semana que viene.

La Parte 2 toma estos roles y los pone a trabajar sobre sistemas reales: dónde termina la solución y empieza el negocio, cómo se elige la granularidad de los roles, y la primera aproximación a requisitos funcionales, no funcionales y reglas de negocio.

---

## 1. 🔴 Los requisitos no aparecen de la nada

Arranquemos con una escena concreta.

Una petrolera termina de construir un oleoducto y está por ponerlo operativo. Hubo un cambio de gestión y las prioridades de la empresa se reacomodaron: lo que antes era secundario ahora es central. Alguien tiene que responder preguntas como qué servicios va a dar ese oleoducto, qué beneficios trae, cómo se mide el retorno de la inversión, qué información hay que registrar y quién la va a consultar.

Ninguna de esas preguntas es técnica todavía. No hay pantallas, no hay base de datos, no hay lenguaje elegido. Y sin embargo, de ahí van a salir los requisitos del sistema que eventualmente se construya.

Esa es la idea que hay que instalar antes que ninguna otra:

```
┌─────────┐    ┌─────────────┐    ┌─────────────┐    ┌──────────┐
│ Negocio │ ─► │ Necesidades │ ─► │  Requisitos │ ─► │ Producto │
└─────────┘    └─────────────┘    └─────────────┘    └──────────┘
```

Se lee de izquierda a derecha y cada eslabón depende del anterior. **Los requisitos nacen del negocio**: no los sacamos de la galera, no los inventa el analista, no los propone el equipo de desarrollo. El negocio tiene objetivos; de esos objetivos surgen necesidades; esas necesidades se transforman en requisitos; y recién ahí, de los requisitos, sale un producto.

Y ojo con el último eslabón, porque "producto" no significa necesariamente software nuevo. Puede ser:

- una **mejora de un proceso**, sin escribir código;
- un **módulo agregado** a un producto que ya está operativo;
- el **reemplazo** de un producto que quedó obsoleto, que no cumple una característica de seguridad o de performance que el crecimiento del negocio ahora exige, o que se volvió tan caro de mantener que conviene cambiar de solución.

El disparador puede ser una baja de costos, una mejora de procesos, una cuestión de imagen institucional o cualquier otro objetivo del negocio. La cadena es siempre la misma; lo que cambia es qué la dispara y en qué termina.

> 🕳️ **Madriguera — BPM y BPMN**
> Son, respectivamente, la disciplina de gestión de procesos de negocio y su notación gráfica estándar para diagramarlos. Esta materia no está enfocada en procesos ni usa esa notación, pero conviene saber que un análisis de procesos es una fuente legítima de requisitos y de demandas de cambio.
> *Volvé al camino — esto se profundiza aparte, otro día.*

---

## 2. 🔴 Qué hacemos cuando hacemos Ingeniería de Requisitos

La cadena de arriba dice qué producimos. Esta sección dice qué actividades hacemos para producirlo. Son seis, y no son fases rígidas con una sola pasada: se vuelve sobre ellas.

| Actividad | En qué consiste |
|---|---|
| **Comprender el contexto** | Saber a qué se dedica la organización, cómo funciona, qué normativa la alcanza, en qué momento está. Es preparación previa al relevamiento. |
| **Identificar necesidades** | Detectar qué es lo que el negocio realmente necesita resolver. |
| **Elicitar información** | *Elicitar* significa sacar a la luz: obtener la información que está en la cabeza de la gente, en los procesos o en los papeles, para poder documentarla y validarla. Se hace con técnicas específicas. |
| **Especificar requisitos** | Documentarlos con herramientas concretas: casos de uso, especificación de requisitos, historias de usuario con sus criterios de aceptación. |
| **Validar lo especificado** | Confirmar con el área usuaria y con el stakeholder que lo que documentamos es efectivamente lo que se necesita, antes de que pase a diseño y desarrollo. |
| **Gestionar cambios** | Todo esto puede cambiar, y cambia. Hay que poder absorberlo sin que se caiga la especificación entera. |

Fijate que **validar y negociar van juntos**: no todo lo que el negocio pretende es factible. Hay restricciones de recursos, de tiempo, de personas y de dinero, y parte del trabajo es acordar qué entra y qué no.

### El arco de la materia

Esas seis actividades se agrupan en cinco movimientos, y ese es el orden en que la materia los va a recorrer:

```
┌──────────┐   ┌───────────┐   ┌──────────┐   ┌────────────┐   ┌──────────┐
│ ENTENDER │ ► │ DESCUBRIR │ ► │ MODELAR  │ ► │ ESPECIFICAR│ ► │ VALIDAR  │
└──────────┘   └───────────┘   └──────────┘   └────────────┘   └──────────┘
```

- **ENTENDER** — el negocio, su contexto y sus actores: usuarios, clientes y stakeholders.
- **DESCUBRIR** — las necesidades y los requisitos, mediante técnicas de elicitación.
- **MODELAR** — el negocio y sus requisitos con distintas herramientas: UML, escenarios.
- **ESPECIFICAR** — requisitos claros, verificables y trazables.
- **VALIDAR** — que lo modelado represente lo que realmente se necesita.

Cada etapa construye sobre la anterior. Esta clase es, entera, la primera: **ENTENDER**.

### Sobre las metodologías

Cuando se habla de "gestionar cambios" aparece inevitablemente la pregunta de con qué metodología se avanza. **Cascada** es la que recorre cada etapa de punta a punta y recién cuando una termina arranca la siguiente. Ese esquema no es inválido y algo de él siempre va a estar presente — hasta que no entiendo el problema difícilmente pueda atacar una solución. Pero hoy los cambios llegan mucho más rápido, a veces empujados por tecnologías o modas que aparecen, y eso obliga a buscar formas más ágiles de recorrer las etapas para poder gestionar esos cambios sin rehacer todo.

*(Espiral, iterativo e incremental son las otras familias de metodologías que suelen nombrarse junto a cascada. Sobre "iterativo e incremental" volvemos en la sección 10, porque es el modo de trabajo de esta cursada.)*

---

## 3. 🟢 Con qué llegamos a esta materia

La Ingeniería de Requisitos no arranca de cero: se apoya en cinco cosas que ya están en la carrera.

```
                         ┌──────────────────┐
                         │    Análisis de   │
                         │     Sistemas     │
                         └────────┬─────────┘
   ┌──────────────┐               ┆               ┌───────────────┐
   │ Paradigmas y │               ┆               │      UML      │
   │ Programación │┄┄┄┄┐          ┆         ┌┄┄┄┄┤               │
   └──────────────┘    ┆    ┌─────┴─────┐   ┆    └───────────────┘
                       └┄┄┄┤ Ingeniería ├┄┄┄┘
                       ┌┄┄┄┤ de Requisitos ├┄┄┄┐
   ┌──────────────┐    ┆    └───────────┘   ┆    ┌───────────────┐
   │   Diseño de  │┄┄┄┄┘                    └┄┄┄┤  Metodologías  │
   │   Sistemas   │                             │     Ágiles     │
   └──────────────┘                             └────────────────┘
```

- **Análisis de Sistemas** — relevamiento, procesos, actores, negocio.
- **Paradigmas de Programación** — cómo los requisitos se relacionan con el software, y el principio de abstracción: mirar el sistema desde arriba e identificar los puntos que se van uniendo, en lugar de quedarse en el detalle de la implementación.
- **Diseño de Sistemas** — los requisitos son el insumo de las etapas posteriores.
- **UML** — la representación de conceptos.
- **Metodologías Ágiles** — historias de usuario y su relación con los requisitos funcionales.

La diferencia de enfoque respecto de esas materias vale la pena marcarla, porque cambia la forma de trabajar. Acá **no se transcribe literalmente lo que dijo el usuario en el relevamiento**. Se parte de eso, sí, pero se le agrega criterio propio y calidad. Si un enunciado pide algo, la respuesta no está limitada a lo que el actor dijo textualmente: se puede — y se espera — agregar lo que uno observa y entiende como mejor resultado, siempre que esté fundamentado.

Dicho al revés, y esto sirve para toda la cursada: **el criterio fundamentado vale más que la respuesta canónica.** Hay una solución propuesta por la cátedra, pero pueden aparecer soluciones mejores o puntos de vista que la enriquezcan. Lo que no se negocia es la fundamentación.

---

## 4. 🔴 El negocio y sus procesos

Ya usamos la palabra "negocio" varias veces. Ahora la definición precisa, porque es un término que en el uso corriente significa otra cosa.

> **Negocio:** el objetivo central de una organización, la razón por la cual existe. Puede ser público o privado, con o sin fines de lucro.

Es decir: **el negocio no es "lo que da plata".** Es lo que la organización quiere resolver y lo que se propone entregar. Un hospital público, una facultad y un organismo de recaudación tienen negocio, aunque ninguno persiga rentabilidad.

> **Proceso de negocio:** el conjunto de actividades coordinadas que realiza la organización para alcanzar su objetivo, de acuerdo a su misión, visión y valores.

Los procesos son *cómo* la organización hace las cosas para lograr ese objetivo. Y no son independientes de la tecnología: los procesos de una organización están apoyados en las herramientas que ya tiene. Cuando traemos una solución, o se apoya sobre esos procesos existentes, o viene a acompañarlos y sustentarlos — pero nunca los ignora.

De ahí sale la versión larga de la cadena, con los procesos en el medio:

> **Negocio → Procesos → Necesidades → Sistema**

**El analista debe comprender el negocio antes de documentar cualquier requerimiento técnico.**

### Por qué el contexto no es un adorno

Dos empresas que hacen exactamente el mismo negocio **no** tienen los mismos requerimientos. Cambian:

- la **cultura organizacional** — cómo se toman las decisiones, qué tan formal es todo, qué se puede y qué no;
- la **normativa** que cada una tiene que cumplir;
- el **momento** que atraviesan — un cambio de gestión, una fusión, una obra que se termina y hay que poner a producir.

Por eso no se puede llegar a un relevamiento sin saber de qué empresa se trata, a qué se dedica y en qué situación está. Entender el contexto **es parte de la preparación del relevamiento**, no una gentileza previa.

---

## 5. 🔴 ¿Quiénes tienen información sobre el problema?

Acá empieza el corazón de la clase.

Volvamos a un caso concreto. Una aplicación de delivery: pedís comida, un repartidor la trae, un restaurante la cocina, la empresa dueña de la app se lleva una comisión, alguien invirtió el dinero para que la app exista y un organismo estatal controla que se facture como corresponde.

Preguntá quiénes son los "usuarios" de ese sistema y vas a tener problemas de inmediato. ¿El que pide la comida? ¿El repartidor, que la usa ocho horas por día pero no paga nada? ¿El dueño del restaurante, que carga su menú y paga una comisión? ¿La empresa que le da crédito mensual a sus empleados para pedir el almuerzo?

La palabra "usuario", sola, no alcanza. Por eso se separan **tres roles distintos**, y distinguirlos bien es lo que evita perder requisitos.

| Rol | Qué lo define |
|---|---|
| **Usuario** | **Opera e interactúa directamente con el sistema** en su día a día. Su feedback valida usabilidad y funcionalidad. |
| **Cliente** | Representa al negocio o al mercado objetivo. **Aporta los fondos** para el desarrollo y el mantenimiento. |
| **Stakeholder** | **Tiene interés**, influencia, o se ve afectado por la solución — aunque no la use directamente. |

Aplicado al delivery: el que pide la comida es usuario; el restaurante que paga comisión para estar en la plataforma es cliente; el organismo que regula la facturación es stakeholder y no toca la app jamás.

> ⚠️ **Cuidado con "cliente".** En el uso corriente y en buena parte de la industria, "cliente" es el que compra o consume el producto. En esta materia, **cliente es el que aporta los fondos** para que la solución se desarrolle y se mantenga. Para el parcial: responder con la definición de la materia.

### Los roles se superponen

Esto es lo que más se pregunta y donde más se pifia:

> **Los roles pueden superponerse: un stakeholder puede ser, a la vez, cliente y usuario con poder de decisión.**

Que una persona sea usuario **no** la excluye de ser stakeholder. Que sea cliente **no** la excluye de ser usuario. En la app de delivery, para poder ser cliente prácticamente tenés que usar el producto — difícilmente lo califiques o consumas sin usarlo. Y a la inversa: hoy no hay forma de pedir sin que te cobren algo, sea por abono fijo o por pedido, así que el usuario termina siendo también cliente.

El caso inverso también existe y es el más ilustrativo. Una directora de recursos humanos que impulsa un proyecto con todo su peso político puede no llegar a usar nunca el sistema resultante. No es usuaria. Es un **stakeholder fuerte**.

La consecuencia práctica es que **un mismo nombre puede aparecer en más de una columna**, y eso no es un error de la respuesta: es la realidad del negocio. Lo que sí es un error es meterlos a todos en una sola bolsa.

### El cliente no siempre existe de entrada

Hay tres situaciones distintas y conviene tenerlas separadas:

1. **Cliente identificado.** Una empresa contrata el desarrollo de una solución para sí misma y la financia. Es el caso más directo.
2. **Producto transversal, sin un cliente único.** La solución resuelve una problemática que se repite en muchas organizaciones — documentar procesos de auditoría, gestionar recursos humanos, un ERP. Acá no hay un cliente puntual que aporte para el desarrollo: es la propia fábrica del producto la que reinvierte. Cuanto mejor sea el producto, más clientes va a tener. *(Un **ERP** es un sistema integrado que cubre las áreas administrativas de una empresa — contabilidad, compras, stock, sueldos — bajo una misma base de datos.)*
3. **Producto que sale a buscar su cliente.** Alguien tiene una idea, pone el aporte inicial y recién después sale a conseguir quién la financie o quién se sume. Por ejemplo, una app que te da puntos por caminar y después los canjeás por beneficios en comercios adheridos: el que la desarrolló no tenía identificado al cliente de antemano, lo fue encontrando a medida que difundía la solución.

> 🕳️ **Madriguera — implicancias legales de reutilizar una solución**
> Cuando una solución desarrollada para un cliente después se ofrece a otros, hay cuestiones contractuales y de propiedad intelectual que definen si eso se puede o no. Existe, es real y condiciona el modelo de negocio, pero no se trabaja en esta materia.
> *Volvé al camino — esto se profundiza aparte, otro día.*

---

### 🎓 Para el parcial, si te preguntan

**¿Cuál es la diferencia entre usuario, cliente y stakeholder?**

El usuario opera e interactúa directamente con el sistema en su día a día, y su feedback valida usabilidad y funcionalidad. El cliente representa al negocio o al mercado objetivo y aporta los fondos para el desarrollo y el mantenimiento. El stakeholder tiene interés, influencia o se ve afectado por la solución, aunque no la use directamente. Los tres roles pueden superponerse en una misma persona u organización.

**¿Por qué no alcanza con identificar a los usuarios?**

Porque identificar solamente a los usuarios hace perder requisitos importantes. Los stakeholders muchas veces forman parte del equipo de toma de decisiones, y sus intereses y restricciones condicionan la solución aunque nunca interactúen con el sistema.

---

## 6. 🔴 Tipos de stakeholder: no todos usan el sistema

Sabiendo que el stakeholder es el que tiene interés sin necesariamente usar nada, el problema pasa a ser **dónde buscarlos**. Hay cuatro lugares clásicos.

| Tipo | Qué hace | Ejemplo |
|---|---|---|
| **Sponsors** | Proveen los recursos financieros y estratégicos del proyecto, o ayudan a que esos fondos se obtengan. Abogan para que el proyecto avance y lo mantienen vivo hasta que la solución se implementa. | Un gerente que impulsa la iniciativa y consigue el presupuesto. |
| **Entes reguladores** | Establecen normativas legales o técnicas **de cumplimiento obligatorio**. Dan un marco y restringen cómo podemos implementar la solución. | El Banco Central sobre los bancos y sus proveedores; el organismo de recaudación sobre todo lo relativo a facturación. |
| **Áreas indirectas** | Departamentos que no desarrollan la solución pero se ven afectados por ella. Un área tiene un objetivo, pero para lograrlo se afectan recursos o procesos de otras áreas: la empresa funciona como un todo. | Finanzas, cuando el proyecto de otra área consume su presupuesto. |
| **Usuarios con poder de decisión** | Tienen injerencia sobre funcionalidades, plazos o alcance. | Decisiones gremiales o sindicales que pesan por el impacto de la solución en el área operativa. |

Sobre el último: cuando se implementaron las máquinas de autogestión en el subte para cargar la tarjeta de transporte, el sindicato objetó dónde iban a estar ubicadas, por el impacto físico sobre los trabajadores. Quienes analizaron y diseñaron la solución no lo habían previsto, y eso terminó condicionando la implementación. Ese es exactamente el tipo de requisito que se pierde si solo mirás a quien opera el sistema.

Y el cierre, que es la razón de ser de todo este bloque:

> **Identificar solamente a los usuarios puede hacernos perder requisitos importantes. Muchas veces los stakeholders forman parte del equipo de toma de decisiones.**

*(Sobre la palabra: en "stakeholder", el **stake** es lo que uno tiene en juego — su interés o participación — y el **holder** es quien lo tiene. Un stakeholder es, literalmente, el que tiene algo en juego en la solución o en el proyecto.)*

---

## 7. 🔴 Stakeholders que no están en esa lista

Los cuatro tipos de arriba son de dónde salen casi siempre. Pero al analizar sistemas reales aparecen tres más que conviene tener a mano, porque son los que más se olvidan.

### El stakeholder negativo

Un stakeholder tiene interés en la solución — pero **el interés puede ser en contra**.

Seguimos con la directora de recursos humanos que impulsa un proyecto. Del otro lado aparece el gerente de finanzas que dice que no hay presupuesto, que no ve el retorno de la inversión y que no habilita la billetera. Por más peso que tenga quien impulsa, ese proyecto no sale.

Ese gerente **es un stakeholder**, y es negativo: va en contra del proyecto, con o sin argumentos. Puede tener una justificación sólida — no hay fondos, no hay retorno — o simplemente un interés contrario. En cualquiera de los dos casos va a boicotear la propuesta, y por eso hay que identificarlo desde el principio en vez de descubrirlo cuando ya es tarde.

### La competencia

Las empresas que vienen a resolver la misma problemática son stakeholders. Tienen interés directo en cómo le va a nuestra solución: la miran, la copian, la superan.

Y el límite de quién es "competencia" es más ancho de lo que parece. Una app de delivery que empieza a vender productos de almacén se vuelve competencia del supermercado del barrio, aunque nadie la haya pensado como tal. Desde el punto de vista del negocio — no de la solución — esos comercios pasan a ser stakeholders.

### Los proveedores

Si la solución consume un servicio de un tercero, ese tercero es stakeholder.

Una app de viajes necesita mapas, cálculo de rutas y tiempos estimados. Los consume a través de una **API** de un proveedor de mapas — *una API es el punto de entrada que un servicio publica para que otros programas le pidan datos o funciones, en lugar de que una persona use su pantalla*. Ese proveedor tiene interés en que la app lo siga eligiendo y no se pase a una alternativa, entre otras cosas porque muy probablemente le esté cobrando por el uso. Es un stakeholder.

---

## 8. 🟡 Entes reguladores: cuidado con quién obliga de verdad

Esta distinción es fina y se presta a error, así que vale detenerse.

La pregunta natural es: si una empresa tiene que cumplir normas ISO, ¿ISO es un ente regulador?

**ISO** significa *International Organization for Standardization*: una organización internacional dedicada a definir estándares y mejores prácticas. Y ahí está la clave. A ISO, como organización, **no le interesa que una empresa puntual aplique o no sus normas**. Le interesa que cada vez más empresas adhieran en general — porque eso sostiene el ecosistema de certificación y le permite actualizar y nutrir sus normas — pero no persigue a nadie por incumplir. Dice: estas son las mejores prácticas; si adherís, contás con el certificado.

Entonces, si ISO no obliga, **¿quién obliga?** Ahí aparecen los que sí son reguladores en el sentido estricto, y los que ejercen presión sin serlo:

- **El regulador real** — el Banco Central sobre los bancos y sus proveedores, el organismo de recaudación en materia de facturación, un ministerio sobre un sector específico. Estos sí establecen normativa de cumplimiento obligatorio.
- **El interés propio de la empresa** — adherir a un estándar y certificar es, la mayoría de las veces, una decisión comercial: da respaldo frente al mercado, permite conseguir cuentas y mantenerlas. El proceso se sostiene con auditorías internas y externas periódicas, que tienen su costo.
- **El cliente, en casos particulares** — no es lo habitual, pero pasa. Si voy a contratar un servicio en la nube y voy a poner información mía ahí, es razonable que exija cumplimiento de la norma de seguridad de la información antes de comprar. Ahí sí el cliente es quien impone la restricción.

El matiz importante: **el cliente masivo casi nunca pide esto.** Nadie elige un hospital pensando en si tiene bien protegida la base de datos de historias clínicas. Quien sí lo exige es una empresa que contrata una cobertura de salud para sus empleados, o una aseguradora de riesgos del trabajo — es decir, un cliente corporativo. El cliente individual ni se lo plantea.

Y una regla que ordena todo esto: **cuanto más crítico es el producto respecto de la vida de las personas, mayor es la adherencia a este tipo de normativas.** No es lo mismo fabricar un termómetro hogareño que un equipo de monitoreo de signos vitales para terapia intensiva. Un comprador de auto quiere que su auto tenga ciertos parámetros de calidad, aunque desconozca por completo el mecanismo de estándares y auditorías con el que el fabricante lo garantiza.

**Para lo que nos importa:** todo esto se traduce en requisitos. Que la solución tenga que cumplir determinada normativa de seguridad, de calidad de la información o de resguardo de datos personales es una restricción perfectamente válida y hay que capturarla.

> 🕳️ **Madriguera — las normas por número y los entes certificadores**
> Cada norma cubre un dominio: calidad de gestión, gestión ambiental, seguridad de la información, y así. Quien audita y emite el certificado no es ISO sino organismos certificadores independientes, que verifican con auditorías periódicas que los estándares se cumplan y no se desvíen.
> *Volvé al camino — esto se profundiza aparte, otro día.*

---

## 9. 🟡 Los usuarios que no podemos nombrar

Una pregunta que parece de trámite: ¿siempre vamos a poder identificar a nuestros usuarios?

La respuesta corta es que no.

Si la solución está acotada —es para esta empresa y para ninguna otra— los usuarios son identificables: son sus empleados, tienen nombre, área y función. Pero si desarrollamos algo genérico, una app que van a instalar millones de personas, podemos saber *cuántas* son pero no *quiénes* son.

Y lo que perdemos no es el nombre. Lo que perdemos es **el perfil**. Sin conocer el universo de usuarios no sabemos si entre ellos hay:

- personas con limitaciones motrices o de otro tipo, que necesitan que la solución contemple esas condiciones para poder ejecutar las mismas funcionalidades que el resto;
- distintos rangos etarios;
- distintos idiomas y regiones.

Todo eso **entra como requisito**, y entra del lado de los no funcionales: son condiciones bajo las cuales la funcionalidad tiene que poder ejecutarse. No es un detalle de diseño que se resuelve después — es parte de la definición.

---

## 10. 🔴 Cómo se trabaja en esta materia

### Encuentros

La cursada alterna semana a semana entre virtual y presencial, según cronograma.

| Modalidad | Horario |
|---|---|
| Virtual (Zoom) | 19:00 a 21:30 — **se arranca 19:05 sí o sí**, sin esperar rezagados |
| Presencial (Campus) | 19:00 a 22:00 |

Los **finales se rinden en Medrano**, no en Campus. La asistencia admite un máximo de **25% de inasistencias**. La cámara no se evalúa formalmente, pero está fuertemente sugerida: el trato es cercano, la cátedra registra participación oral y aprende los nombres y los contextos laborales de cada uno porque eso alimenta la construcción de las clases.

### Equipos y entregas

El trabajo en equipo es condición de la materia. Cada equipo tiene su **carpeta compartida en Google Drive** con el documento de trabajo — ahí se elabora. La entrega formal, en cambio, **siempre pasa por el Campus Virtual**, que es el canal oficial y único para consignas, entregas, notas y avisos.

El ciclo semanal tiene una lógica y conviene entenderla, porque explica por qué la fecha de entrega es la que es:

```
  jueves/viernes AM        miércoles 21:00         lunes            jueves
  ─────────────────        ───────────────      ──────────      ────────────
  se publica el TP    ►    se entrega      ►    lo leen    ►    feedback en clase
```

Es una materia cuatrimestral: si se entregara un jueves y se devolviera al jueves siguiente, pasarían dos semanas y el feedback llegaría cuando ya arrancó el trabajo siguiente. Por eso el miércoles a las 21:00, y por eso el ciclo corto.

El modo de trabajo declarado es **iterativo e incremental**: se espera rehacer y mejorar sobre lo entregado, no entregar una vez y cerrar. Va a haber cosas para corregir, y a veces habrá que rehacer.

### 🔴 La rúbrica colaborativa

Este es el dato de mayor valor operativo de toda la clase.

A medida que llega el feedback de cada entrega, los estudiantes **construyen su propia rúbrica de corrección** en formato colaborativo — el criterio con el que se corrige un caso de uso, por ejemplo, destilado de las devoluciones acumuladas.

**Esa rúbrica se puede llevar impresa al parcial.**

Lo que se sigue de ahí: todo feedback recibido durante la cursada es material de parcial. Hay que ver las correcciones, tomar nota, compilarlas y entenderlas — sistemáticamente, desde la primera devolución.

### Evaluación

- **Dos parciales + dos recuperatorios**, teórico-prácticos.
- **Promoción: 8 o más**, que equivale a aproximadamente el **85%** del parcial correcto — no el 60%, no el 80%.
- **Cada punto del parcial se aprueba con un mínimo del 60%**, y se recupera de forma independiente: en un parcial de cuatro puntos podés tener que recuperar uno solo, aunque no sea el de mayor peso.
- **Instancia oral** para quienes están en condición de promocionar.
- **No existe** ningún trabajo práctico adicional que habilite la promoción si las notas no dan.
- Los recuperatorios generales caen en diciembre —coincidentes con las mesas de finales— o en febrero, porque el cuatrimestre cierra en febrero.

Dos precisiones sobre el **primer parcial**: se toma en **dos fechas**, porque tiene una parte teórica y una parte práctica. Y la instancia práctica es **prácticamente irrecuperable**: solo se arma una alternativa por causa de fuerza mayor documentada, del tipo un viaje impuesto por el trabajo o una urgencia familiar en el interior. No es una fecha negociable — conviene anotarla y blindarla.

### Canales

| Canal | Para qué |
|---|---|
| **Campus Virtual** | Oficial y único: consignas, entregas, notas, avisos, material de lectura |
| **Página web de la materia** | Complemento administrativo: cronograma, links rápidos, hoja de ruta del integrador. Es una novedad de este cuatrimestre y la cátedra pide feedback al cierre |
| **Google Drive** | Carpeta por equipo, donde se elabora |
| **Google Calendar** | Calendario de la materia, suscribible |
| **Foro de avisos** | Unidireccional, sin respuesta |
| **Foro de consultas** | Se responde típicamente en la clase siguiente, salvo que impacte en una entrega |

El cronograma está publicado pero **está sujeto a cambios**: se ajusta según cómo avanza el curso y qué temas piden más espacio.

### Cómo se espera que participes

Cuatro supuestos que la cátedra declara explícitamente y que después se traducen en cómo corrige:

1. **Todos traemos saberes distintos y complementarios** — todos valiosos, ninguno descartable.
2. **Todos podemos aportar respuestas válidas** — sin que eso sea condición excluyente del cuerpo docente.
3. **Todo alumno debe fundamentar sus respuestas** — los criterios importan tanto como las conclusiones.
4. **El aprendizaje nace de la discusión** — distintos criterios y puntos de vista alimentan las mejores soluciones.

El silencio no juega a favor. Se espera que la clase hable, pregunte y discuta.

### 🔴 Notación UML

Todo artefacto que se modele con UML —caso de uso, clases, objetos, estados, secuencia, actividad— **tiene que respetar la notación**. La U es de *unificado* y la M es de *modelo*: el sentido de una notación estándar es que el otro que lee el modelo entienda exactamente lo que quisimos representar, sin interpretar.

En esta materia se usa principalmente en **casos de uso**. Y se corrige: una inclusión mal dibujada o un actor mal representado se marca como error. El repaso de la notación corre por cuenta de cada uno, con el material de repaso disponible en el aula —el clásico de Fowler sobre UML, que funciona como referencia de notación y es contra lo que se corrige.

### Lo inmediato

- **Miércoles 19/08, 21:00 — Caso de uso diagnóstico, individual, en JPG.** Es diagnóstico: sirve para que la cátedra calibre el punto de partida del curso.
- **Jueves 20/08 — clase presencial en Campus, 19:00.** Se trabaja sobre ese caso de uso.
- **Para el jueves, tarea de observación:** la próxima vez que te tomes un colectivo, mirá el lector de tarjeta de transporte cuando le decís al chofer hasta dónde vas y pagás. Fijate **qué secuencia de contenidos muestra la pantalla**, en qué orden. Se pregunta en clase, y es el ejemplo con el que se baja a tierra la diferencia entre el *qué* y el *cómo*.

---

## Qué viene en la Parte 2

Los roles ya están definidos. La Parte 2 los pone a prueba sobre seis sistemas reales y de ahí salen los criterios más finos de la clase: hasta dónde llega la solución y dónde empieza el negocio, con qué granularidad conviene abrir los roles, por qué la palabra "usar" está prohibida, y la primera aproximación al par requisitos funcionales / no funcionales junto con las reglas de negocio.

El checkpoint de la unidad va al cierre de esa parte.

---

**FIN DE LA PARTE 1 — Clase 01 · Conceptos fundamentales**
