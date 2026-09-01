# ANEXO — Errores típicos con casos de uso: los diez problemas de proyectos reales

**Ingeniería de Requisitos — clase02 · Anexo de lectura**
Sobre el paper *"Use Case Pitfalls: Top 10 Problems from Real Projects Using Use Cases"* de Susan Lilly (SRA International, IEEE). Explicado en español, en palabras propias, siguiendo la estructura del original: no es una traducción.

---

## De qué trata el paper

Los casos de uso tienen una virtud que es también su trampa: son **fáciles**. El formato es informal y accesible, la notación gráfica es trivial, y por eso no intimidan ni siquiera a equipos sin experiencia en especificación formal de requisitos. Pero escribir *buenos* casos de uso requiere habilidad y práctica — y los equipos que los usan por primera vez tropiezan con los mismos problemas, una y otra vez.

La autora observó varios proyectos reales que usaron casos de uso de distintas maneras: como la especificación completa de requisitos del sistema; como una parte de ella; como técnica de análisis para relevar requisitos que después se escribían en otro formato (los clásicos "el sistema deberá…"); o como requisitos a nivel de subsistema. Los equipos arrancaban sin problemas… y al escalar, chocaban con lo mismo: límite del sistema indefinido, modelos demasiado complejos, especificaciones de largo y granularidad equivocados, casos de uso que nadie entiende o que nunca se terminan.

> 🕳️ **Madriguera — los "shalls"**
> En especificación tradicional, cada requisito se redacta como una oración "el sistema deberá…" (*the system shall…*). El paper los llama "shalls" a secas. Acá alcanza con saber que es el formato clásico, previo a los casos de uso.
> *Volvé al camino.*

De esas observaciones sale la lista de diez. Antes de recorrerla, el sistema que el paper usa para todos los ejemplos.

### El sistema de los ejemplos: venta de entradas de béisbol

Un sistema informático para simplificar la venta de entradas a partidos de béisbol:

- Los clientes pueden **ver el calendario de la temporada** y **reservar entradas** en **kioscos** ubicados en lugares convenientes, como shoppings.
- Alternativamente, un cliente puede **llamar a un número gratuito**, y un **operador telefónico** le reserva las entradas.
- El cliente paga **con tarjeta de crédito**, o **al retirar las entradas** en el estadio el día del partido.

Tres personas van a aparecer todo el tiempo: el **Cliente de kiosco** (opera el sistema por sí mismo), el **Cliente telefónico** (llama, no toca el sistema) y el **Operador telefónico** (empleado que opera el sistema para el cliente que llama). Más un sistema externo: el **Sistema de validación de tarjetas de crédito**.

---

## 1. El límite del sistema está indefinido o es inconsistente

*(Problem #1: The system boundary is undefined or inconsistent)*

Alguien se sienta a modelar la venta de entradas y dibuja esto:

```
      ┌───────────────── ¿Sistema? ─────────────────┐
      │                                              │
 [actor] Cliente telefónico ──┐                      │
 [actor] Cliente de kiosco ───┼──( Pedir entradas )──┼── [actor] Sistema de validación de tarjetas
 [actor] Operador telefónico ─┘                      │
      │                                              │
      └──────────────────────────────────────────────┘
```

¿Qué está mal? Que el **Cliente telefónico** no usa el sistema informático: llama por teléfono y le habla a una persona. Quien opera el sistema es el Operador. El diagrama mezcló **los usuarios del negocio** con **los usuarios del sistema informático** en un mismo modelo — y por eso la caja del límite tiene un signo de pregunta.

**El síntoma:** casos de uso descriptos a alcances inconsistentes — algunos a nivel del negocio, otros a nivel del sistema informático, otros incluso a nivel de subsistema. A veces la mezcla está dentro de una misma especificación.

**El concepto que falta:** el modelo de casos de uso tiene un elemento que es una caja rotulada, **el límite del sistema**: los actores van afuera, los casos de uso adentro. Antes de identificar actores y casos de uso hay que ser explícito sobre qué significa "sistema": ¿un sistema informático? ¿una aplicación? ¿un componente o subsistema? ¿la empresa entera? Los casos de uso pueden describir cualquiera de esos límites — **pero uno a la vez**. Los actores y casos de uso correctos para un límite son, casi seguro, incorrectos para otro.

**La cura:** ser explícito sobre el alcance y rotular el límite en consecuencia. Decir "sí, el modelo del negocio es muy interesante, pero ahora estamos definiendo casos de uso a nivel del sistema informático" — y sostenerlo. Con eso, el mismo problema tiene dos modelos válidos según qué se esté haciendo:

```
A nivel del SISTEMA INFORMÁTICO ("Sistema de venta de entradas"):

 [actor] Cliente de kiosco ────┐
                               ├──( Pedir entradas )──── [actor] Sistema de validación de tarjetas
 [actor] Operador telefónico ──┘

A nivel del NEGOCIO ("Negocio de venta de entradas"):

 [actor] Cliente telefónico ────( Pedir entradas por teléfono )──── [actor] Sistema de validación de tarjetas
```

En el primero, el Cliente telefónico no aparece: no es usuario del sistema informático. En el segundo sí: es usuario del negocio. Los dos son correctos; la elección depende de si estás **definiendo los requisitos de un sistema informático** (el primero) o **modelando o rediseñando procesos de negocio** (el segundo).

**Segundo síntoma:** mirando el modelo, no queda claro qué está adentro y qué afuera. Pasa mucho con herramientas de modelado que no dibujan la caja del límite — incluida, dice la autora, la líder del mercado.

> 🕳️ **Madriguera — herramientas CASE**
> *Computer-Aided Software Engineering*: las herramientas de modelado visual de la época (Rational Rose era la líder). Acá solo importa que algunas no dibujan el límite del sistema.
> *Volvé al camino.*

**La cura:** dibujar el límite, aunque sea mentalmente. Si la herramienta no lo dibuja, ubicar los casos de uso **en el medio** ("adentro") y los actores **alrededor** ("afuera") de una caja imaginaria. El mismo modelo, formateado de las dos maneras:

```
❌  Actores y casos de uso entremezclados, sin que se distinga adentro de afuera.

✅  [actor] Cliente de kiosco ──( Pedir entradas )
                                ( Ver calendario )──── [actor] Sistema de validación
    [actor] Administrador ──────( Crear calendario )
             del calendario
    → casos de uso en el centro, actores en la periferia
```

**En una frase:** decidí primero qué es "el sistema", modelá un solo límite a la vez, y que se vea quién está adentro y quién afuera.

---

## 2. Los casos de uso están escritos desde el punto de vista del sistema

*(Problem #2: The use cases are written from the system's (not the actors') point of view)*

Un equipo nombra sus casos de uso así: **"Procesar pedido de entradas"**, **"Mostrar calendario"**. Suenan a casos de uso. No lo son: describen **lo que hace el sistema**, no **lo que el actor quiere lograr**.

**El síntoma:** los nombres describen acciones del sistema en vez de la meta del actor.

**La cura:** nombrar desde la perspectiva de las **metas del actor**. "Pedir entradas" y "Ver calendario" son metas de los usuarios — buenos nombres. "Procesar pedido" y "Mostrar calendario" son cosas que hace el sistema — malos nombres.

**Segundo síntoma:** los pasos de la especificación describen funcionalidad interna en vez de interacciones a través del límite del sistema.

**La cura:** concentrarse en **qué** necesita hacer el sistema para satisfacer la meta del actor, no en **cómo** lo va a lograr.

**Tercer síntoma:** el modelo de casos de uso parece un diagrama de flujo de datos o de procesos.

**La cura:** prestar atención a los casos de uso que **no están asociados directamente a ningún actor**, sino solo enganchados a otros por relaciones «uses» o «extends». A veces esa es una forma apropiada de modelar. Pero muchos modeladores novatos — sobre todo programadores, o gente que viene del modelado de procesos — abusan de esas relaciones para **descomponer funcionalmente** el problema, en vez de enfocarse en las interacciones entre actores y sistema.

El test para saberlo: mirá la especificación del caso de uso usado o extendido. Sus pasos tienen que describir **interacciones entre el actor (del caso de uso base) y el sistema**. Si los pasos hablan exclusivamente de procesamiento interno, esos casos de uso están funcionando como mecanismo de descomposición funcional — y entonces **no pertenecen al modelo de casos de uso**.

> 🕳️ **Madriguera — descomposición funcional**
> Técnica clásica de diseño: partir una función grande en subfunciones, y esas en sub-subfunciones, hasta llegar a algo programable. Sirve para diseñar, no para expresar lo que el usuario quiere.
> *Volvé al camino.*

**En una frase:** el nombre es la meta del actor, los pasos son interacciones actor–sistema, y todo óvalo que solo describa procesamiento interno sobra.

---

## 3. Los nombres de los actores son inconsistentes

*(Problem #3: The actor names are inconsistent)*

La persona que administra el calendario de partidos aparece como **"Administrador del calendario"** en un modelo, **"Gestor del calendario"** en otro y **"Calendarista"** en un tercero. Es el mismo rol con tres nombres.

**El síntoma:** distintos nombres para el mismo rol. Es sorprendentemente fácil que pase: las distintas fuentes de requisitos usan variantes para la misma cosa — y nombres parecidos para cosas muy distintas. Cuando el problema es grande, hay varios equipos modelando partes distintas, y el mismo actor lógico aparece con variantes de modelo en modelo.

**La cura:** ponerse de acuerdo **temprano** sobre los nombres de actores (y de los términos en general). Armar un **glosario** desde el principio y usarlo para definir los actores: el nombre, su significado y los **alias** con los que ese rol también se conoce. El glosario va como apéndice del documento de casos de uso.

**En una frase:** un rol, un nombre, y un glosario que lo fije antes de que cada equipo invente el suyo.

---

## 4. Demasiados casos de uso

*(Problem #4: Too many use cases)*

Dos versiones del mismo cliente frente al kiosco:

```
El "Cliente de kiosco feliz":

 [actor] Cliente de kiosco ────( Pedir entradas )

El "Cliente de kiosco triste":

 [actor] Cliente de kiosco ────( Seleccionar fecha del partido )
                          ├────( Seleccionar sector del estadio )
                          └────( Pasar la tarjeta de crédito )
```

El primero tiene **un** caso de uso: la meta real del cliente al acercarse al kiosco. El segundo tiene tres — y los tres describen interacciones entre el cliente y el sistema, sí, pero son **pasos incidentales** en el camino a la meta real, que sigue siendo pedir entradas. ¿Cómo se partió la meta en tres sub-metas? El equipo intentó hacer **un caso de uso por cada elemento de la interfaz de usuario**.

**El síntoma:** el modelo tiene una cantidad enorme de casos de uso.

**La cura:** revisar la **granularidad**. Los casos de uso tienen que reflejar **"resultados de valor"** para los usuarios: el logro de una meta real. Dos movimientos:

- **Combinar** los casos de uso que describen comportamiento trivial o incidental y que en realidad son fragmentos de los casos de uso reales. Se parten en fragmentos, típicamente, cuando alguien intenta asociar pantallas a casos de uso uno a uno.
- **Eliminar** los casos de uso que describen procesamiento puramente interno (interno respecto del límite que se esté usando).

**Y si la granularidad está bien pero el sistema es simplemente enorme:** particionar el conjunto en **paquetes de casos de uso**. Cada paquete contiene un subconjunto **cohesivo** de casos de uso, agrupado alrededor de uno o más actores que comparten metas, con un conjunto limitado de actores.

```
Sin particionar: 25 óvalos y 5 actores en un solo diagrama, líneas cruzadas por todos lados.

Particionado:
 ┌ Paquete 1 ┐  ┌ Paquete 2 ┐  ┌ Paquete 3 ┐  ┌ Paquete 4 ┐  ┌ Paquete 5 ┐
 │ Actor A   │  │ Actor B   │  │ Actor A   │  │ Actor D   │  │ Actor C   │
 │ Actor C   │  │           │  │ Actor E   │  │ Actor A   │  │           │
 └───────────┘  └───────────┘  └───────────┘  └───────────┘  └───────────┘
```

**En una frase:** un caso de uso por meta real del usuario; los pasos no son casos de uso; y si igual son muchos, agrupalos en paquetes cohesivos.

---

## 5. Las relaciones actor–caso de uso parecen una telaraña

*(Problem #5: The actor-to-use case relationships resemble a spider's web)*

**Los síntomas:** (a) hay demasiadas relaciones entre actores y casos de uso; (b) un actor interactúa con **todos** los casos de uso; (c) un caso de uso interactúa con **todos** los actores.

**La cura, primera parte:** los actores pueden estar definidos **demasiado ampliamente**. Examinalos para encontrar roles más explícitos, cada uno participando en un conjunto más limitado de casos de uso. "Empleado" es muy general y se asocia con muchísimos casos de uso; "Operador telefónico" y "Administrador del calendario" son más específicos, y cada uno se asocia con un conjunto más chico y más orientado a su rol.

**La cura, segunda parte:** a veces lo que simplifica es reconocer una **clase más general de actores**. Pasa cuando dos o más actores están asociados **al mismo conjunto de casos de uso** por algo que sus roles tienen en común. El resultado sin tratar es una telaraña de líneas cruzadas:

```
❌  [actor] Cliente de kiosco ──┬──( Ver calendario )
                                ├──( Pedir entradas )
    [actor] Operador telefónico ┼──( Ver calendario )        ← líneas cruzadas
                                ├──( Pedir entradas )
                                └──( Ver reporte diario de ventas )
```

La notación de casos de uso tiene un mecanismo para reconocer explícitamente lo común entre roles: la **generalización de actores**. El mismo modelo, redibujado:

```
✅  [actor] Ticketer ────( Ver calendario )
           △    △        ( Pedir entradas )
           │    │
  [actor] Cliente   [actor] Operador ────( Ver reporte diario de ventas )
          de kiosco         telefónico
```

Este modelo dice: un Cliente de kiosco **es un tipo de** Ticketer, y un Operador telefónico **es un tipo de** Ticketer. Cualquier Ticketer puede ver el calendario o pedir entradas. El Operador (y no el Cliente de kiosco) puede además ver el reporte diario de ventas.

> 🕳️ **Madriguera — "Ticketer"**
> Nombre acuñado por la autora para el rol genérico "quien opera entradas". No tiene traducción establecida; se deja tal cual.
> *Volvé al camino.*

**Una advertencia importante:** no habría sido correcto modelar al Operador telefónico como especialización del Cliente de kiosco en lugar de crear Ticketer. Las relaciones actor–caso de uso quedarían bien, pero la relación **actor–actor sería semánticamente insostenible**: un Operador telefónico **no es un tipo de** Cliente de kiosco. La autora cuenta haberlo visto en un libro reciente, que modelaba a un Representante de ventas como subclase de Cliente solo para heredar las asociaciones que se solapaban.

**En una frase:** si un actor se asocia con todo, está demasiado amplio; si dos actores comparten el mismo conjunto, creá el padre común — pero solo si cada hijo *es un tipo de* ese padre.

---

## 6. Las especificaciones son demasiado largas

*(Problem #6: The use case specifications are too long)*

**El síntoma:** una especificación de caso de uso que sigue durante páginas.

**La cura, opción A — la granularidad es demasiado gruesa.** "Usar calendario" — un caso de uso que incluye todo lo que cualquier usuario podría querer hacer con un calendario — es demasiado amplio. Casos de uso más acotados y específicos, como "Ver calendario" y "Crear calendario", tienden a ser más cortos y más fáciles de entender.

**La cura, opción B — la granularidad de los *pasos* es demasiado fina.** Los pasos pueden estar demasiado detallados, o incluir procesamiento puramente interno (implementación). Reescribirlos para enfocarse en la **interacción esencial**.

**En una frase:** si es largo, o el caso de uso abarca demasiado, o los pasos bajan demasiado.

---

## 7. Las especificaciones son confusas

*(Problem #7: The use case specifications are confusing)*

**Primer síntoma:** al caso de uso le falta contexto; **no "cuenta una historia"**.

**La cura:** incluir un campo **Contexto** en la plantilla de especificación, que describa el conjunto de circunstancias en las que el caso de uso es relevante. Ese campo tiene que poner a cada caso de uso en perspectiva respecto del "panorama general" — el alcance inmediatamente exterior. No usarlo para resumir el caso de uso.

**Segundo síntoma:** los pasos del flujo normal parecen un programa de computadora.

**La cura:** reescribir los pasos como un conjunto de **interacciones esenciales** entre el actor y el sistema, que desembocan en el logro de la meta del actor. Tres movimientos concretos:

- Sacar el comportamiento condicional ("Si…") a **flujos alternativos** descriptos por separado, dejando el flujo normal más corto y fácil de entender.
- Los pasos de un caso de uso no sirven para describir algoritmos no triviales, con mucha ramificación y bucles. Para eso, usar técnicas más efectivas: **tabla de decisión, árbol de decisión o pseudocódigo**.
- Asegurarse de que los pasos **no especifiquen implementación**. Enfocarse en las interacciones externas. Considerar expresar parte del comportamiento como **"reglas"** en vez de algoritmos.

> 🕳️ **Madriguera — tabla de decisión**
> Una grilla que cruza condiciones (filas) con acciones: cada columna es una combinación de condiciones y qué hacer en ese caso. Compacta lo que en pasos sería un enredo de "si… entonces… salvo que…".
> *Volvé al camino.*

**En una frase:** contexto para que se entienda dónde encaja, interacciones en el flujo normal, condicionales a flujos alternativos, algoritmos a otra notación.

---

## 8. El caso de uso no describe correctamente la habilitación funcional

*(Problem #8: The use case doesn't correctly describe functional entitlement)*

Un caso de uso llamado **"Procesar calendario de partidos"** describe todo lo que cualquier actor podría querer hacer con el calendario. Su especificación tiene un flujo normal para **ver** el calendario, y flujos alternativos para **actualizarlo**:

```
❌  [actor] Cliente de kiosco ──────────┐
    (solo puede ver el calendario)      ├──( Procesar calendario de partidos )
    [actor] Administrador del calendario┘
    (puede ver o actualizar el calendario)
```

El Cliente de kiosco puede usar el flujo normal, pero **no** los flujos alternativos: solo el Administrador está habilitado para actualizar. El diagrama no lo dice — las dos líneas se ven iguales.

**El síntoma:** las asociaciones entre actores y casos de uso no describen correcta o completamente **quién puede hacer qué** con el sistema. La autora encontró dos causas:

- El equipo intentó ser "orientado a objetos", haciendo casos de uso **gordos** que incluyen todas las acciones posibles sobre un objeto de negocio. La autora los llama **"casos de uso CRUD"**, porque suelen contener flujos para crear, leer, actualizar y borrar el objeto. Sus nombres delatan: incluyen palabras como **"mantener", "gestionar" o "procesar"**.
- El equipo intentó hacer coincidir casos de uso con **pantallas**. Frente a una pantalla de consulta que también permite editar (a un usuario con autoridad), combinaron ver y actualizar en un único caso de uso que se corresponde con esa única pantalla.

> 🕳️ **Madriguera — CRUD**
> *Create, Read, Update, Delete*: las cuatro operaciones básicas sobre cualquier registro. Un "caso de uso CRUD" es uno que las mete a todas juntas sobre un mismo objeto.
> *Volvé al camino.*

**La cura:** asegurarse de que **cada actor asociado a un caso de uso esté completamente habilitado para ejecutarlo**. Si un actor solo está habilitado para una parte del caso de uso, **el caso de uso se parte**:

```
✅  [actor] Cliente de kiosco ──────────( Ver calendario de partidos )──── [actor] Administrador
                                                                                   del calendario
                                        ( Actualizar calendario de partidos )──── [actor] Administrador
                                                                                   del calendario
```

Ahora se ve de un vistazo: el Cliente de kiosco puede ver el calendario, pero no actualizarlo.

**En una frase:** cada línea actor–caso de uso significa "puede hacerlo entero"; si solo puede una parte, hay dos casos de uso.

---

## 9. El cliente no entiende los casos de uso

*(Problem #9: The customer doesn't understand the use cases)*

**Primer síntoma:** el cliente no sabe nada de casos de uso, y le entregan un documento de requisitos basado en casos de uso para revisar o aprobar. (Lo ideal es que clientes y usuarios finales participen en el desarrollo de los casos de uso; pero quien revisa o aprueba puede no haber estado involucrado.)

**La cura:** enseñarle **lo justo** para entender.

- Incluir en el documento una explicación breve (una o dos páginas) de qué son los casos de uso, como prefacio o apéndice, con una clave para leer el modelo y las especificaciones, y un ejemplo simple.
- Dar una capacitación corta cuando se distribuye el documento para revisión.
- **Pensarlo muy bien antes de usar «uses» y «extends»** en el modelo: son una comodidad de modelado, pero no son para nada intuitivas para un revisor sin experiencia.

**Segundo síntoma:** los casos de uso **no cuentan una historia**.

**La cura:** agregar información que la cuente.

- Incluir la sección Contexto en la plantilla (como en el error 7).
- Agregar una sección de **panorama general** que dé contexto a un conjunto de casos de uso relacionados (por ejemplo, un paquete), y usarla para contar la historia.
- Incluir **otros tipos de modelos** cuando hagan falta. Con frecuencia, un caso de uso produce un cambio de estado en un objeto importante del dominio — pero el modelo de casos de uso solo no cuenta cómo ese objeto va cambiando de estado a través de muchos casos de uso a lo largo del tiempo. Un **diagrama de estados** de ese objeto puede ser una forma excelente de mostrar cómo encajan entre sí varios casos de uso relacionados.

> 🕳️ **Madriguera — diagrama de transición de estados**
> Muestra los estados por los que pasa un objeto (una entrada: reservada → pagada → retirada) y qué evento produce cada cambio. Es el diagrama que cuenta "la vida" de un objeto.
> *Volvé al camino.*

**Tercer síntoma:** la organización de los casos de uso no coincide con cómo el cliente piensa el problema.

**La cura:** encontrar la estrategia de organización que tenga sentido **para el cliente**. Escuchar cómo describe su negocio.

- **Cómo particionar en paquetes:** por roles o actores principales, o por los grandes eventos del negocio del cliente. Ejemplo: el cliente habla todo el tiempo de la **"preparación de primavera"** — cuando cargan el nuevo calendario de partidos, las definiciones de sectores del estadio y los precios de las entradas. Aunque no sea así como los desarrolladores piensan el sistema, esa es la organización en paquetes que tiene sentido para el cliente.
- **Cómo ordenar los casos de uso dentro de un paquete:** **cronológicamente**, para describir una historia de uso del sistema a lo largo del tiempo. **No alfabéticamente.**

**Cuarto síntoma:** el caso de uso está escrito en **"computarés"**.

**La cura:** cuidado con la jerga informática que no es parte del vocabulario del cliente. Decir "el sistema muestra la pantalla de resultados", no "se invoca la pantalla de resultados".

**Quinto síntoma:** el cliente directamente **odia** los casos de uso.

**La cura:** entregar lo que el cliente quiere. Eso no significa que los casos de uso no puedan usarse como técnica de relevamiento, si realmente son la técnica correcta para el trabajo — pero pueden no ser el producto entregable principal. Ejemplo: un cliente tiene su propia plantilla de documento de requisitos, que no está basada en casos de uso. Pero el sistema es de naturaleza muy operativa, y el equipo considera que los casos de uso son la mejor forma de relevar y modelar sus requisitos. Entonces hacen el análisis basado en casos de uso, y después **escriben los requisitos en el formato que el cliente quiere**, a partir de lo aprendido en ese análisis. Los casos de uso pueden ir en un apéndice, o directamente no entregarse.

**En una frase:** el documento es para el cliente — enseñale a leerlo, contale la historia en su orden y su idioma, y si no lo quiere, usá los casos de uso para vos y entregale lo que pide.

---

## 10. Los casos de uso nunca se terminan

*(Problem #10: The use cases are never finished)*

**Primer síntoma:** hay que cambiar los casos de uso cada vez que cambia la **interfaz de usuario**.

**La cura:** **desacoplar** los detalles de la interfaz de las interacciones del caso de uso. El diseño de la interfaz va a cambiar, y no querés que los requisitos del sistema dependan del diseño — la dependencia va al revés: **el diseño de la interfaz tiene que satisfacer los requisitos de los casos de uso**. Un poco de acoplamiento está bien: bocetos de "baja fidelidad" de la interfaz ayudan a entender el caso de uso. Pero no atar las interacciones fundamentales a los mecanismos de la interfaz, que son lo más propenso a cambiar.

En los flujos, enfocarse en lo esencial de **lo que hace el actor** — "selecciona un partido", "envía una solicitud" — y no en **cómo** se hace la interacción — "hace doble clic en el botón Enviar".

Y los **eventos disparadores** del caso de uso se especifican como **precondiciones** — "el usuario seleccionó un partido y solicitó pedir entradas" — no como detalles de navegación entre pantallas. La navegación va en un documento de diseño de interfaz **separado**, no en el modelo de casos de uso.

**Segundo síntoma:** hay que cambiar los casos de uso cada vez que cambia el **diseño**.

**La cura:** la respuesta fácil es **"no pongas diseño en tus casos de uso"** — y es un buen consejo cuando los casos de uso están a nivel del sistema informático. Los casos de uso registran **qué** debe hacer el sistema, no los detalles de diseño o implementación. Los pasos no tienen que ser innecesariamente de bajo nivel: tienen que especificar completamente qué debe hacer el sistema, **pero nada más que eso**. La información de diseño que aparezca durante el análisis va a un documento separado de **guía de diseño**.

Hay un caso especial: cuando los casos de uso están definidos a nivel de **subsistema**, los cambios en el diseño de nivel sistema (por ejemplo, cómo se reparte la funcionalidad entre subsistemas) afectan los requisitos del subsistema. Hasta que el diseño del sistema esté estable — y explícitamente documentado —, los requisitos del subsistema, incluidos sus casos de uso, no se van a estabilizar.

**Tercer síntoma:** ¡hay tantos casos alternativos posibles!

**La cura:** cuidado con la **"parálisis por análisis"**. Hay un punto en el que los requisitos están adecuadamente especificados, y más análisis y más especificación **no agregan calidad**. Cubrir el **80%** de los casos; hacer lo mejor posible con el resto dentro del presupuesto asignado de tiempo y dinero.

**Cuarto síntoma:** los requisitos, sencillamente, **se desconocen**.

**La cura:** el formato simple, informal y accesible de los casos de uso puede llevar a la conclusión engañosa de que desarrollarlos es fácil. Pero la simplicidad del formato **no hace que el proceso de análisis de requisitos sea menos crítico ni más fácil**. Los casos de uso son un mecanismo para definir y documentar requisitos operativos — **no son magia**.

**En una frase:** requisitos desacoplados de la interfaz y del diseño, disparadores como precondiciones, el 80% cubierto y el resto según presupuesto — y ningún formato reemplaza el trabajo de averiguar qué se necesita.

---

## Conclusiones del paper

Los problemas descriptos **no son una acusación contra los casos de uso**: son problemas en su aplicación por practicantes sin experiencia. Y eso es lo normal: la mayoría de los equipos que desarrollan casos de uso incluyen miembros inexpertos — la técnica puede ser nueva para la organización, o los analistas tienen experiencia pero el resto del equipo no. El equipo ideal incluye **clientes, usuarios finales y expertos del dominio**, que casi nunca tienen experiencia previa con casos de uso. Justamente la simplicidad de la notación y las especificaciones en lenguaje natural les permiten participar plenamente — y, con la misma probabilidad, caer en estos tropiezos.

La sugerencia final de la autora, para equipos con miembros nuevos en la técnica: hacer **revisiones informales periódicas "en progreso"** de los modelos y las especificaciones, para atrapar los problemas temprano y educar al equipo sobre la marcha. Una revisión o inspección formal del documento terminado también corresponde. Y las revisiones son más efectivas si se apoyan en una **lista de verificación** que ayude a identificar estos problemas comunes.

### Los diez, como lista de verificación

Reconstruida a partir de los diez problemas, para revisar un modelo antes de darlo por terminado:

| # | Pregunta de revisión |
|---|---|
| 1 | ¿Está definido y rotulado el límite del sistema? ¿Todos los casos de uso están al mismo alcance? |
| 2 | ¿Cada nombre expresa la meta del actor, no una acción del sistema? ¿Los pasos son interacciones actor–sistema? ¿Hay óvalos que solo describen procesamiento interno? |
| 3 | ¿Cada rol tiene un único nombre? ¿Hay glosario de actores con alias? |
| 4 | ¿Cada caso de uso es un resultado de valor para el usuario, o hay pasos disfrazados de casos de uso? Si son muchos, ¿están en paquetes cohesivos? |
| 5 | ¿Algún actor se asocia con casi todo? ¿Dos actores comparten el mismo conjunto y falta un padre común? ¿Cada hijo *es un tipo de* su padre? |
| 6 | ¿Alguna especificación ocupa páginas? ¿Es el caso de uso demasiado amplio, o los pasos demasiado finos? |
| 7 | ¿Cada caso de uso tiene contexto? ¿Los condicionales están en flujos alternativos? ¿Los algoritmos complejos están en otra notación? |
| 8 | ¿Cada actor asociado puede ejecutar el caso de uso **entero**? ¿Hay nombres con "mantener", "gestionar", "procesar"? |
| 9 | ¿Puede el cliente leer el documento? ¿Cuenta una historia, en su orden y en su vocabulario? |
| 10 | ¿Los flujos están atados a la interfaz o al diseño? ¿Los disparadores están como precondiciones? ¿Se cubrió el 80%? |

**FIN DEL ANEXO**
