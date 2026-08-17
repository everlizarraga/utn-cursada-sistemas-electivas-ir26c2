# 📘 APUNTE MAESTRO — Clase 01 · Parte 2

## Los roles puestos a prueba: límite, granularidad y la primera mirada a los requisitos

---

### Qué cubre esta parte

Los tres roles de la Parte 1 aplicados sobre sistemas reales, y los criterios finos que solo aparecen cuando uno intenta usarlos: hasta dónde llega la solución que estamos analizando, con qué granularidad conviene abrir los roles, y por qué hay palabras que conviene desterrar del vocabulario.

Después, la primera aproximación al par requisitos funcionales / no funcionales y a las reglas de negocio.

Cierra con el checkpoint de la unidad completa.

---

## 1. 🔴 El ejercicio: ingeniería inversa sobre sistemas que ya usás

La forma de poner a prueba los tres roles no fue con un caso inventado, sino al revés: tomar aplicaciones que todos usamos en la vida diaria y **reconstruir hacia atrás** quiénes son sus usuarios, sus clientes y sus stakeholders.

*(A eso se le llama **ingeniería inversa**: partir de un producto terminado y reconstruir las definiciones y decisiones que lo originaron, en lugar de ir de la definición al producto.)*

La consigna se trabaja sobre un documento con dos partes:

| Parte | Qué se completa |
|---|---|
| **Parte 1** | Tres columnas: **Stakeholders · Usuarios · Clientes** |
| **Parte 2** | Tres columnas: **Requisitos funcionales · Requisitos no funcionales** (asociados al RF de la misma fila) **· Reglas de negocio** (asociadas al RF de la misma fila) |

Prestá atención a la letra chica de la Parte 2, porque es una restricción de forma y se corrige: no son tres listas paralelas e independientes. **La asociación es por fila.** Cada requisito no funcional y cada regla de negocio están anclados al requisito funcional que tienen al lado.

Los sistemas analizados fueron seis, y cada uno hizo aflorar un problema distinto:

| Sistema | Qué puso en evidencia |
|---|---|
| App de delivery de comida | Roles que se superponen; el actor que trabaja dentro del sistema sin pagarlo; el cliente corporativo |
| Billetera virtual | Granularidad: cuándo dos cosas que parecen iguales son mundos distintos |
| Sistema de transporte con tarjeta | El límite de la solución — el caso más difícil de todos |
| App de viajes | El proveedor como stakeholder; la frontera borrosa entre app y negocio |
| Plataforma de reservas | Accionista y cliente no son lo mismo |
| App de mensajería | La palabra "usuario" no siempre identifica el rol; regulador vs. recaudador |

Las secciones que siguen son, cada una, uno de esos hallazgos.

---

## 2. 🔴 Dónde termina la solución y empieza el negocio

Este es el criterio más difícil de la clase y el que más se equivoca. Vamos con el caso completo.

**El sistema de tarjeta de transporte.** Todos lo conocemos: hay una tarjeta física, hay una app en el celular, hay kioscos donde cargás saldo, hay colectivos y subtes que cobran el viaje, y hay empresas de transporte que en algún momento cobran por haberte llevado.

Preguntá quiénes son los usuarios y aparecen enseguida: los pasajeros, y también los kiosqueros que acreditan la carga. Preguntá quiénes son los clientes y alguien va a decir las empresas de transporte. Y ahí es donde se rompe todo.

Porque antes de listar un solo rol hay que responder otra pregunta: **¿cuál es la solución que estamos analizando?**

```
        ┌─────────────────────────────────────────────────┐
        │            SISTEMA DE TRANSPORTE                │
        │                  (el negocio)                   │
        │                                                 │
        │   ┌──────────┐  ┌──────────┐  ┌──────────────┐  │
        │   │   App    │  │  Módulo  │  │    Módulo    │  │
        │   │    de    │  │    de    │  │      de      │  │
        │   │ pasajero │  │  carga   │  │   empresas   │  │
        │   │          │  │ (kiosco) │  │de transporte │  │
        │   └──────────┘  └──────────┘  └──────────────┘  │
        │        ▲                                        │
        │        └── si el alcance es ESTO,               │
        │            el kiosquero y la empresa            │
        │            NO son usuarios de la solución       │
        └─────────────────────────────────────────────────┘
```

Si el alcance declarado es **la app del pasajero**, entonces el kiosquero no es usuario: usa otro módulo, que es otra parte de la plataforma. Y la empresa de transporte tampoco: cuando pagás el viaje, la plata **no va a la cuenta de la empresa del colectivo**. Va a un fondo común que administra el Estado, y después se hace un reparto — tantos viajes en esta línea, tanto dinero a esa empresa. Eso es un **clearing**: una compensación de cuentas que se liquida después, no en el momento de cada operación. La empresa opera contra otro módulo, no contra tu app.

El razonamiento vale en las dos direcciones. Si el alcance fuera "la plataforma de transporte completa", entonces sí: kiosqueros y empresas entran como usuarios de sus respectivos módulos.

**La conclusión operativa: definir el límite de la solución es el paso previo a listar roles, no una consecuencia de haberlos listado.** Sin límite declarado, la discusión sobre si tal actor es usuario o no es irresoluble, porque cada uno está pensando en un sistema distinto.

### Cuando la frontera es realmente borrosa

No siempre se separa tan limpio. En una app de viajes aparecen exigencias sobre el estado de los vehículos, la patente habilitada, el certificado de transporte de pasajeros. ¿Eso es un requisito de la aplicación o una condición del negocio del transporte?

Ahí la respuesta honesta es que casi se superponen: la aplicación está hecha con un sentido y ese sentido *es* el negocio. Se hace difícil separarlos. Pero la pregunta —**¿esto tiene que ver con el negocio o con la aplicación?**— hay que hacérsela igual en cada ítem, porque de la respuesta depende dónde va a caer ese requisito.

### 🎓 Para el parcial, si te preguntan

**¿Por qué hay que definir el alcance de la solución antes de identificar los roles?**

Porque el mismo actor puede ser usuario o no serlo según dónde se trace el límite. En un sistema de transporte, quien acredita carga en un kiosco es usuario de la plataforma pero no de la app del pasajero: opera contra otro módulo. Sin un alcance declarado, la clasificación de roles no es verificable.

---

## 3. 🔴 La regla del café con leche

Otro caso, ahora con una billetera virtual.

Al listar stakeholders aparecieron juntos "bancos y billeteras virtuales". Parece razonable: los dos compiten con la solución. Pero no tienen el mismo interés. Los bancos miran el problema de la interoperabilidad entre cuentas bancarias y cuentas de billetera —de hecho, una billetera de origen bancario nace justamente como respuesta a eso—, mientras que las otras billeteras miran qué funcionalidades ofrece la competencia para igualarlas o superarlas. Son dos intereses distintos, y por lo tanto **dos filas distintas**, no una.

Lo mismo pasó con los comercios: no es igual un comercio físico que cobra con posnet que una plataforma digital que integra el medio de pago para vender online, sin local. Puede ser que haya que separarlos, puede ser que no — pero conviene arrancar separados y decidirlo después.

Y en el sistema de transporte, la persona que carga saldo en la tarjeta de su hija no es la pasajera. Ahí la granularidad estaba bien puesta.

De esos tres casos sale una regla que la cátedra usa todo el tiempo:

> ### ☕ La regla del café con leche
>
> Me levanto a la mañana y no sé bien si quiero un café o un café con leche.
>
> Si me hago un **café** y era eso lo que quería, listo. Y si de repente me dan ganas de que sea con leche, le agrego la leche y también listo — tuve el desayuno que quería.
>
> Ahora, si de una me hago un **café con leche** y después me doy cuenta de que quería café solo, ya no hay vuelta atrás. La leche no se saca.
>
> **Arrancá separado. Si después ves que se trata de lo mismo, lo unís. Al revés no se puede.**

Aplica a roles, a funciones, a casos de uso y a prácticamente todo lo que se modele en esta materia. Empezar granular hace más fácil el diseño y el mantenimiento; empezar con todo mezclado es meterse en un problema que después cuesta muchísimo desarmar.

Y es una regla que va a reaparecer. Vale la pena tenerla anotada aparte.

---

## 4. 🟡 Accionista, sponsor y cliente no son lo mismo

Una plataforma de reservas de alojamiento. Al completar la columna de clientes, la respuesta intuitiva es "los accionistas": son los que ponen los fondos iniciales y los que permiten que la plataforma siga existiendo.

Suena bien y es incorrecto. Fijate en un detalle de la experiencia real: reservar una habitación por la plataforma **no sale lo mismo** que pagarla directamente en el hotel. Hay una diferencia, y esa diferencia es una comisión.

Entonces, ¿quién fondea efectivamente el desarrollo y el mantenimiento? **Los huéspedes y los propietarios**, cada vez que pagan esa comisión. Ellos son los clientes. El accionista gana plata *a partir de* ese flujo — que es, justamente, la razón por la que invirtió.

La distinción, ordenada:

| Rol | Qué aporta | Qué busca |
|---|---|---|
| **Accionista / inversor** | Capital, participación | Retorno sobre su inversión. Es **stakeholder** |
| **Sponsor** | Recursos financieros y estratégicos del proyecto; empuja para que avance | Que el proyecto llegue a implementarse. Es **stakeholder** |
| **Cliente** | Los fondos para el desarrollo y el mantenimiento, vía el pago del producto o servicio | Que el producto resuelva su necesidad |

El punto fino: que alguien ponga dinero **no lo convierte en cliente**. Hay que preguntarse por dónde entra efectivamente el dinero que sostiene la solución.

---

## 5. 🔴 "Usuario" es ambiguo y "usar" está prohibido

Última parada en los roles, y esta es una convención de la cátedra que conviene incorporar ya, porque afecta cómo se redacta todo de acá en adelante.

En una app de mensajería, poner "usuarios" en la columna de usuarios no dice absolutamente nada. ¿Quiénes? ¿Las personas físicas? ¿Las empresas que atienden clientes? ¿Los administradores internos? El rótulo no identifica el rol — es circular.

La solución fue nombrarlos por lo que efectivamente son en ese sistema: **cuentas**. Cuentas personales, cuentas de empresa, cuentas de medios de difusión. Cada una con su comportamiento y sus requisitos.

De ahí sale la regla general:

> ⚠️ **El verbo "usar" se evita.** Es ambiguo: no dice qué hace el actor ni qué obtiene. En los casos de uso, especialmente, hay que reemplazarlo por un verbo que describa la acción concreta. La palabra "usuario" sobrevive como nombre del rol genérico, pero cuando hay que nombrar actores concretos se busca un nombre que los identifique de verdad.
>
> En la industria "usar" aparece en todas partes y nadie se escandaliza. **Para el parcial y para los TPs de esta materia: evitarlo.**

Esto se enlaza directo con la regla del café con leche: nombrar granularmente los roles es, al mismo tiempo, encontrar nombres que los identifiquen. "Cuentas de empresa" y "cuentas personales" es mejor que "usuarios" por las dos razones a la vez.

### Regulador no es lo mismo que recaudador

Un último matiz que salió del mismo caso. Al listar entes reguladores de una app de mensajería aparecieron los organismos impositivos. La objeción: **un organismo de recaudación no regula la solución, cobra impuestos**. Para él, la empresa es un contribuyente más — como cualquier otra.

Distinto sería un organismo que regule el contenido, o el tratamiento de datos personales, o las condiciones del servicio. Ese sí establece normativa que restringe cómo se implementa la solución, que es la definición de ente regulador que vimos en la Parte 1.

*(Vale la pena tener presente que el organismo recaudador de cada país es distinto del banco central de ese país: uno recauda, el otro regula el sistema financiero. Confundirlos al nombrar stakeholders es un error frecuente.)*

---

## 6. 🔴 Requisitos funcionales y no funcionales: el qué y el cómo

Hasta acá trabajamos sobre quiénes tienen la información. Ahora empezamos con qué es lo que esa información produce.

Hay **dos grandes universos de requisitos**, y esto es el core de la materia:

> **Requisitos funcionales (RF): QUÉ es lo que se quiere resolver** con la solución, el software o el proceso que estamos implementando. Qué quiere resolver el usuario.
>
> **Requisitos no funcionales (RNF): CÓMO se resuelve. Bajo qué condiciones** tienen que operar esos requisitos funcionales.

Y la relación entre ambos:

```
   ┌────────────────────┐
   │   RF — el QUÉ      │   ← lo que la solución tiene que resolver
   └─────────┬──────────┘
             │
             │  restringido por
             ▼
   ┌────────────────────┐
   │   RNF — el CÓMO    │   ← bajo qué condiciones tiene que poder hacerlo
   └────────────────────┘
```

**Los requisitos no funcionales restringen la forma en que puedo implementar los funcionales.** Ponen condiciones de operatividad, de calidad, de mantenibilidad, de tecnología a utilizar. No son un agregado opcional al final: acotan el espacio de soluciones posibles.

Ya vimos un caso de esto sin nombrarlo. En la Parte 1, cuando no podemos identificar el universo de usuarios y tenemos que contemplar limitaciones motrices, distintos rangos etarios, distintos idiomas o distintas regiones — eso son requisitos no funcionales. La funcionalidad es la misma; lo que cambia son las condiciones bajo las cuales tiene que poder ejecutarse, y para quiénes.

### 🔬 Para observar antes de la próxima clase

La próxima vez que te tomes un colectivo, mirá el lector de tarjeta cuando le decís al chofer hasta dónde vas y pagás.

**Fijate qué muestra la pantalla, y en qué orden.** Cada cosa que aparece ahí está resolviendo algo, y no todas resuelven lo mismo. Ese aparatito es el ejemplo con el que se termina de bajar a tierra la diferencia entre el qué y el cómo — y se pregunta en clase.

*(La teoría completa de RF y RNF se desarrolla en la clase siguiente. Lo de arriba es el marco con el que hay que llegar: qué resuelve, bajo qué condiciones, y cómo lo segundo condiciona a lo primero.)*

### 🎓 Para el parcial, si te preguntan

**¿Qué diferencia hay entre un requisito funcional y uno no funcional?**

El requisito funcional define qué es lo que se quiere resolver con la solución; el no funcional define bajo qué condiciones ese requisito funcional tiene que operar. Los no funcionales restringen la forma en que se pueden implementar los funcionales, imponiendo condiciones de operatividad, calidad, mantenibilidad o tecnología.

---

## 7. 🟡 Reglas de negocio

Junto a los funcionales y los no funcionales aparece una tercera categoría, que en el documento de trabajo tiene columna propia: las **reglas de negocio**.

Ya nos cruzamos con una, en el caso del sistema de transporte:

> Una tarjeta **registrada** a nombre de una persona obtiene descuento en la tarifa. Una tarjeta **sin registrar** funciona igual, pero paga tarifa plena.

Fijate lo que esa regla no es. No es una funcionalidad — el sistema cobra el viaje en los dos casos. No es una condición de operación tecnológica. Es una **definición del negocio** sobre cómo tiene que comportarse el sistema, y podría cambiar mañana por decisión de quien administra el servicio, sin que cambie una sola línea de la funcionalidad de cobrar.

Por eso en el documento van **asociadas a un requisito funcional determinado**, en la misma fila: una regla de negocio no flota sola, condiciona a una funcionalidad concreta.

*(La teoría de reglas de negocio, y el criterio fino para distinguirlas de los requisitos no funcionales, se ve junto con RF y RNF más adelante. Por ahora alcanza con reconocerlas: son definiciones del negocio sobre cómo debe comportarse el sistema en determinada situación.)*

---

## 8. 🟡 El diagnóstico inicial

La clase incluyó un cuestionario breve cuyo objetivo no era calificar sino **calibrar de dónde parte el curso**. Las respuestas se guardan como diagnóstico.

Los conceptos que exploró vienen casi todos de UML y de modelado: qué es un modelo y para qué sirve, qué permite una especificación, qué permite la implementación, la relación entre modelos e instancias, la generalización como relación entre una descripción general y una variedad más específica, herencia, polimorfismo, interfaces y clases abstractas. Y, en el medio, el concepto de caso de uso.

Dos resultados vale la pena retener, porque marcan cómo se corrige de acá en adelante.

**El primero es el más importante.** Ante la afirmación de que no hace falta respetar la nomenclatura del modelo porque igual se entiende, **el 96% del curso respondió que era correcta**. No lo es. La respuesta de la cátedra fue tajante: una inclusión mal dibujada o un actor mal representado no se acepta. El repaso de la notación es responsabilidad de cada uno y hay material disponible para eso. Es, probablemente, la fuente de pérdida de puntos más barata de evitar de toda la cursada.

**El segundo quedó abierto a propósito.** El ítem que definía al caso de uso como una instancia o una ejecución de una función requerida por el actor generó un resultado que la cátedra marcó como interesante, con el anuncio de que más adelante se va a discutir si esa definición es la correcta. Es decir: hay una corrección viniendo sobre ese punto, y todavía no llegó. Conviene no fijar esa definición en la cabeza como si estuviera cerrada.

---

## 9. 🟢 Qué se construye durante la cursada

El objetivo general, en una línea: **pasar de un problema o necesidad del negocio a una especificación documentada** que pueda ser comprendida, validada y utilizada por el equipo de diseño o desarrollo — y validada, sobre todo, por el área usuaria.

El recorrido se divide en dos mitades:

**Primera parte**
- Requisitos funcionales, no funcionales y reglas de negocio
- Casos de uso como herramienta de documentación de requisitos, con mucha ejercitación
- Técnicas de elicitación — de todas las que existen, se trabajan en profundidad **entrevistas y cuestionarios**; el resto se conocen y se estudian en la teoría, porque el cuatrimestre no da para practicarlas todas
- Soluciones a proponer y su relación con nuevas tecnologías

**Segunda parte**
- Documentación de requisitos: **escenarios**, **LEL** (Léxico Extendido del Lenguaje — una herramienta que funciona como un glosario, pero bastante más completo) e historias de usuario
- Requisitos no funcionales, particularmente los de hardware

Y una precisión sobre el vocabulario que ya podemos anticipar: los **casos de uso** sirven para pensar el *qué*, mientras que los **escenarios** sirven para pensar el *cómo*. Cada unidad construye sobre la anterior.

> 🕳️ **Madriguera — metodologías ágiles e historias de usuario**
> Las historias de usuario son una forma de expresar requisitos desde la perspectiva de quien los necesita, con criterios de aceptación que definen cuándo están cumplidas; las épicas agrupan varias. Aparecen en la segunda parte de la materia, así que existe y tiene nombre, pero todavía no es el momento.
> *Volvé al camino — esto se profundiza aparte, otro día.*

---

## ✅ Checkpoint — Clase 01

Diez preguntas sobre la unidad completa. Sin respuestas: la idea es que intentes contestarlas de memoria antes de buscar nada.

1. ¿Qué significa que los requisitos nacen del negocio, y qué implica eso para lo que el analista tiene que hacer *antes* de un relevamiento?

2. Definí negocio y proceso de negocio. ¿Por qué una organización sin fines de lucro tiene negocio?

3. Diferenciá usuario, cliente y stakeholder. Dame un caso en el que una misma persona ocupe dos de esos roles a la vez, y otro en el que un stakeholder no sea usuario ni cliente.

4. Nombrá los cuatro tipos de stakeholder y dá un ejemplo de cada uno.

5. ¿Qué es un stakeholder negativo? ¿Por qué conviene identificarlo temprano en lugar de descubrirlo sobre la marcha?

6. ¿Es ISO un ente regulador? Fundamentá la respuesta e indicá quién sí exige el cumplimiento de una norma en la práctica.

7. Cuando no podemos identificar a nuestro universo de usuarios, ¿qué es exactamente lo que perdemos, y cómo se traduce eso en requisitos?

8. Enunciá la regla del café con leche. ¿Por qué el orden no es reversible, y a qué cosas se aplica además de a los roles?

9. ¿Por qué hay que definir el límite de la solución antes de listar los roles? Ilustralo con un caso donde el mismo actor sea usuario o no según dónde se trace ese límite.

10. ¿Cuál es la diferencia entre un requisito funcional y uno no funcional, y qué relación de dependencia hay entre ellos?

---

**FIN DE LA PARTE 2 — Clase 01 · Conceptos fundamentales**

**FIN DEL APUNTE MAESTRO — Clase 01**
