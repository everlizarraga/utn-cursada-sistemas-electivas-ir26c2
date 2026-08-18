# Lectura en español — Cap. 5 · Parte 1: Trazabilidad y tipos de interdependencia

> **Origen.** Capítulo 5, secciones 5.1 a 5.3, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Åsa G. Dahlstedt** (Universidad de Skövde) y **Anne Persson**, Suecia.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.

---

## Por qué este capítulo sí te importa

Las interdependencias entre requisitos no figuran en tu cronograma. **La trazabilidad sí** — es una de las palabras del léxico con el que te van a corregir, junto con *verificable*, *no ambiguo* y *específico*.

Y este capítulo es el único de todo el libro que **la define con precisión y la desarma en sus tipos**. La sección 2 de este archivo es probablemente el mejor material que vas a encontrar sobre qué significa exactamente que un requisito sea trazable, y por qué.

El resto —el modelo de tipos de interdependencia— es interesante y te da vocabulario preciso para hablar de relaciones entre requisitos, que es algo que vas a necesitar cuando modeles casos de uso relacionados entre sí.

---

## 1. Introducción 🔴

### El hecho de partida

> **La mayoría de los requisitos individuales no pueden tratarse de manera aislada durante el desarrollo. Están relacionados entre sí y se afectan mutuamente de maneras complejas.**

Y viene con un dato que vale la pena retener:

> **Un estudio reciente mostró que solo aproximadamente una quinta parte de los requisitos de cualquier conjunto son verdaderamente singulares** — es decir, no están relacionados con ningún otro requisito ni lo influyen.

Cuatro de cada cinco requisitos están enganchados con algún otro. Ejemplos de cómo un requisito puede afectar a otros:

- **Restringe** cómo pueden diseñarse o implementarse otros requisitos.
- **Afecta el costo** de implementación de otros requisitos.
- **Aumenta o disminuye la satisfacción** del cliente respecto de otros requisitos.

### Por qué importa

Los autores son claros en un punto:

> **Las interdependencias no son problemáticas en sí mismas.** Lo que pasa es que **influyen sobre un montón de actividades y decisiones** del proceso: planificación de versiones, gestión de cambios, diseño e implementación de requisitos, pruebas, y reutilización de requisitos.

Esas actividades pueden basarse en uno o varios requisitos y **afectar a otros de maneras no intencionadas, o ni siquiera anticipadas**.

**Dos ejemplos concretos:**

**1. Gestión de cambios.** Un cambio hecho a un requisito **puede afectar a varios otros y obligarlos a cambiar también**. Descuidar esas dependencias al evaluar el impacto de un cambio **resulta en descuidar parte del impacto real**. En consecuencia, **el costo de implementar un requisito puede terminar siendo varias veces más alto de lo esperado**, y eso causa problemas de presupuesto o de cronograma.

**2. Planificación de versiones.** Cuando se selecciona el conjunto óptimo de requisitos para la próxima versión, **no siempre es posible elegir los de prioridad más alta, justamente por las interdependencias**. Implementar un requisito de alta prioridad puede requerir **que primero se implemente uno de baja prioridad y alto costo**.

> Ese segundo ejemplo cierra el círculo con el capítulo anterior. Ahí se decía que la lista de prioridades no se puede seguir sin criterio. Acá está la razón principal, con nombre propio.

### Qué es gestionar interdependencias 🔴

> **Gestionar las interdependencias es identificar, almacenar y mantener información sobre cómo los requisitos se relacionan y se afectan entre sí.** Involucra además **decidir qué información de interdependencia hace falta en cada situación** del proceso de desarrollo, **y cómo debería presentarse esa información**.

El propósito de hacerlo sistemáticamente es doble: **mejorar las decisiones** que se toman durante el desarrollo, y **detectar tempranamente problemas potenciales** derivados de esas interdependencias.

Y una constatación honesta de los autores sobre el estado del área: **pese a la necesidad y a los beneficios potenciales, hay poca investigación invertida en este tema**. La literatura existente tiende a abordarlo desde un problema o una actividad específica, y como consecuencia **el conocimiento actual está desparramado en segmentos que tratan aspectos puntuales**. La literatura sobre **las características comunes** de las interdependencias es escasa.

---

## 2. La trazabilidad de requisitos 🔴

Los autores ubican a las interdependencias **como un aspecto específico de un tema más grande: la trazabilidad**. Por eso dedican esta sección a explicarla.

### 2.1 La definición 🔴

Existen varias definiciones del término. La que este capítulo adopta —una de las más usadas en el campo— es:

> **Trazabilidad de requisitos: la capacidad de describir y seguir la vida de un requisito, en dirección hacia adelante y hacia atrás, idealmente a lo largo de todo el ciclo de vida del sistema.**

Desarmémosla, porque cada parte hace trabajo:

- **Describir y seguir** — no alcanza con que la relación exista; tiene que poder recorrerse.
- **La vida de un requisito** — el requisito tiene historia, no es un punto.
- **Hacia adelante y hacia atrás** — en las dos direcciones, y son usos distintos.
- **Todo el ciclo de vida** — no solo la fase de requisitos.

**Cómo se logra, en general:** asociando objetos de información relacionados, como:

| Se asocia… | …con |
|---|---|
| Requisitos | Los componentes del sistema que los satisfacen |
| Objetivos del sistema | Los requisitos derivados de esos objetivos |
| Propuestas de cambio | Los requisitos que pretenden cambiar |
| Una decisión | **Las justificaciones y supuestos sobre los que se basa** |
| Casos de prueba | Los requisitos cuyo cumplimiento pretenden asegurar |
| Componentes del sistema | Los recursos necesarios para implementarlos |

> ⚠️ **Cruce con la cátedra.** Fijate en la cuarta fila: **la decisión se traza hacia su justificación**. La trazabilidad no es solo "de dónde salió este requisito" — incluye **por qué se decidió lo que se decidió**. Eso conecta con el tercer metadato que el capítulo 2 pedía guardar de cada requisito (fuente, prioridad y justificación).

### 2.2 Por qué hace falta 🔴

La trazabilidad se considera hoy **un soporte importante para desarrollar sistemas de software de alta calidad**. Los beneficios que enumera el capítulo:

**1. Análisis de impacto.** En la integración de cambios, la información de trazabilidad **permite identificar el impacto de un cambio propuesto**. Identificar cómo los requisitos y otros artefactos se ven afectados **facilita un análisis de costo y cronograma más preciso**.

**2. Entender la historia.** Sostiene el entendimiento de **por qué un objeto fue creado, modificado y evolucionó**. Eso **motiva y explica las decisiones y los compromisos** tomados durante el desarrollo, y es además una entrada valiosa para la mejora de procesos.

**3. Verificar la completitud en las dos direcciones.** Da la posibilidad de asegurar que **todos los requisitos son cumplidos por los componentes del sistema** y que **no se agregaron funcionalidades de más** — porque todos los componentes o funcionalidades del sistema deberían estar relacionados con uno o varios requisitos.

**4. Menor costo de ciclo de vida.** Una trazabilidad abarcativa sostiene un producto de mejor calidad, mejora tanto el desarrollo como el mantenimiento, y **potencialmente reduce los costos del ciclo de vida del sistema**.

### Qué pasa cuando la trazabilidad es pobre 🔴

Este párrafo del capítulo es el mejor argumento a favor de la trazabilidad que hay en el libro:

> Una práctica pobre de trazabilidad —donde la trazabilidad se descuida, o donde las trazas capturadas son insuficientes y desestructuradas— **produce una disminución de la calidad del sistema, causa revisiones y por lo tanto aumenta el costo y el tiempo del proyecto. Resulta en pérdida de conocimiento si los individuos dejan el proyecto, lleva a decisiones equivocadas, malentendidos y fallas de comunicación.**

> ⚠️ **Cruce con la cátedra.** Guardá especialmente la frase sobre la **pérdida de conocimiento cuando la gente se va**. Es la razón menos obvia y probablemente la más fuerte: sin trazabilidad, **el saber sobre por qué el sistema es como es vive solo en la cabeza de quien estuvo ahí**, y se va con esa persona. Es exactamente el argumento por el cual la cátedra les pide minutas de reunión y documentación del proceso, no solo el producto final.

### 2.3 Los tipos de trazabilidad 🔴

#### Pre-trazabilidad y post-trazabilidad

La trazabilidad se divide en dos tipos mayores según **el momento**:

| | **Pre-trazabilidad** | **Post-trazabilidad** |
|---|---|---|
| **Qué cubre** | Los aspectos de la vida de un requisito **ANTES de que sea incluido en la especificación** | Los aspectos de su vida **DESDE que fue incluido en la especificación en adelante** |
| **A qué apunta** | Un **mejor entendimiento de los requisitos** | Un **mejor entendimiento y aceptación del sistema actual** |
| **Qué incluye** | Rastrear **la elicitación y la definición** de los requisitos, y su **evolución**. Relacionarlos con **su origen** (interesado, regla de negocio, documentación previa) y con otros requisitos asociados | Asegurar que **todos los requisitos son cumplidos por el sistema**, relacionándolos con **el componente** que los satisface. Relacionarlos con **casos de prueba** |
| **De qué se ocupa** | La **producción** de requisitos; el **dominio** con el que se interactúa | El **despliegue** de requisitos; el **software** que se desarrolla |

```
   PRE-TRAZABILIDAD              │           POST-TRAZABILIDAD
                                 │
   interesado ┐                  │        ┌── componente C1
   regla de   ├──► R1 ──► R1.1   │   R1 ──┤
   negocio    │        └► R1.2   │        └── componente C2
   documento ─┘                  │
                                 │        casos de prueba
   ¿DE DÓNDE VINO?               │        ¿DÓNDE TERMINÓ?
              │
              └──── ESPECIFICACIÓN DE REQUISITOS ────┘
```

**Por qué importa cada una:**

- La **pre-trazabilidad es el fundamento para gestionar la evolución** del sistema, porque permite elicitar **qué partes de la especificación se ven afectadas** por un pedido de cambio determinado — sea que venga de políticas organizacionales, de procesos de negocio o del uso del sistema.
- La **post-trazabilidad** asegura que **ningún requisito se pierda y ninguno se agregue**, y es importante para la integración de cambios porque **permite identificar el impacto que los cambios tienen sobre el diseño y la implementación**.

#### Trazabilidad horizontal y vertical 🔴

La otra división es según **el tipo de los objetos relacionados**:

| | **Horizontal** | **Vertical** |
|---|---|---|
| **Qué relaciona** | Versiones o variantes **del mismo tipo** de información — entre requisitos, o entre componentes del sistema | Información **entre fases previas y posteriores** del desarrollo, es decir, **entre objetos de tipos distintos** |
| **Ejemplo** | Requisito ↔ requisito | Requisito → diseño hecho a partir de ese requisito → componente que lo cumple |

> **Dónde encaja este capítulo:** las interdependencias entre requisitos son **principalmente una cuestión de pre-trazabilidad**, de categoría **horizontal** — porque relacionan objetos del mismo tipo.

### 2.4 El meta-modelo de la trazabilidad 🟡

Los autores presentan un modelo con **tres perspectivas mayores** de la trazabilidad:

| Perspectiva | Qué es | Qué destaca |
|---|---|---|
| **Fuente** (*source*) | **El artefacto físico donde se mantiene la información**: documento de especificación, documento de diseño, memorándum, llamada telefónica | La parte de **gestión documental**. Importante porque **los objetos de traza disponibles en fuentes persistentes constituyen la trazabilidad de largo plazo** |
| **Interesado** (*stakeholder*) | **El agente involucrado en la gestión** de la trazabilidad: cliente, analista de sistemas, jefe de proyecto | La importancia de **los distintos roles de uso** al diseñar un sistema de trazabilidad. Además da la capacidad de **definir quién es responsable** de cada producto y decisión |
| **Objeto** (*object*) | **El tipo de objetos de información que deben relacionarse**: requisito, justificación, decisión, componente del sistema | Qué se relaciona con qué |

**Cómo se conectan las tres:** las **fuentes** se usan para documentar los **objetos**. Los **interesados** están involucrados en gestionar las fuentes —las crean, las usan, las mantienen— y además tienen distintos roles en el establecimiento y uso de los objetos y de las trazas entre ellos.

El modelo permite representar varias dimensiones de la trazabilidad:

```
   QUÉ información se representa
   DÓNDE se representa y CÓMO
   QUIÉNES son los interesados y qué rol tienen
        en la creación y uso de esa información
   POR QUÉ cierto objeto se crea o se modifica
```

> Reparen en que **una llamada telefónica figura como "fuente"**. No es un chiste: si una decisión se tomó en una llamada y no quedó en ningún lado, la traza está rota. De ahí que las minutas existan.

### 2.5 Dos advertencias sobre la trazabilidad 🔴

Los autores cierran la sección con dos avisos importantes:

**1. No hay una receta universal.** La información que hace falta capturar **varía entre proyectos, organizaciones y dominios, y debe ajustarse a la situación**. Las organizaciones necesitan soporte para **definir estrategias de trazabilidad adecuadas a sus necesidades específicas**.

**2. Y el aviso más práctico:**

> **La información de trazabilidad tiende a tomar proporciones enormes, lo que resulta en grandes costos adicionales de recolección, almacenamiento y mantenimiento.**

Eso refuerza la necesidad de **considerar cuidadosamente qué información hace falta realmente** según la situación.

> ⚠️ **Cruce con la cátedra.** Este segundo punto es un matiz que conviene tener: la trazabilidad **no es gratis y no es infinita**. La respuesta correcta a "¿hay que trazar todo?" no es sí — es "hay que decidir qué trazar según para qué se va a usar". Es un criterio, no una regla.

---

## 3. Los tipos de interdependencia 🟡

### El problema previo: los tipos se pisan entre sí

Antes de presentar su modelo, los autores describen honestamente el estado del área:

- La literatura que aborda explícitamente los tipos de interdependencia **lo hace desde perspectivas distintas**, lo que produjo **varias visiones más o menos diferentes** sobre qué tipos existen. **Ninguna incluye todos los tipos** presentados en la literatura.
- **Muchos de los tipos encontrados se superponen o son similares**, y por lo tanto **son difíciles de distinguir entre sí**.
- El problema está documentado empíricamente: en una encuesta se les pidió a profesionales que encontraran interdependencias entre un conjunto dado de requisitos **e identificaran qué tipo describía cada relación** — y les costó.

**Un ejemplo de la ambigüedad**, que ilustra bien el problema: la relación entre dos requisitos donde uno debe implementarse antes que el otro puede describirse:

- como una **dependencia temporal** — uno va antes que el otro;
- o como que **el segundo requiere al primero** — uno no puede funcionar sin el otro.

Son la misma relación mirada desde dos ángulos, y ambas etiquetas son defendibles.

### La estrategia del modelo

Los autores optaron por **identificar los tipos fundamentales**, compilando los tipos superpuestos o similares en tipos más genéricos, **manteniendo el número lo más bajo posible sin perder ninguna de las intenciones centrales** de la literatura.

Aclaran además que **el modelo necesita más investigación**: pueden encontrarse más categorías fundamentales y más tipos.

```
                    TIPOS DE INTERDEPENDENCIA
        ┌───────────────────┬──────────────────────┐
        ▼                   ▼                      ▼
   ESTRUCTURALES      DE RESTRICCIÓN         DE COSTO/VALOR
   · refinado_a       · requiere             · aumenta/disminuye
   · cambia_a         · entra_en_conflicto_    _el_costo_de
   · similar_a          con                  · aumenta/disminuye
                                               _el_valor_de
```

---

### 3.1 Interdependencias estructurales 🟡

Se ocupan de que, dado un conjunto de requisitos, **estos pueden organizarse en una estructura** donde las relaciones son **tanto jerárquicas como transversales**.

Los requisitos de negocio de alto nivel se descomponen gradualmente en requisitos de software más detallados, **formando una jerarquía**. Y además puede haber relaciones estructurales **entre requisitos de partes distintas** de esa jerarquía.

#### `refinado_a` (*refined_to*)

> **Un requisito de nivel superior es refinado por varios requisitos más específicos.**

Se usa para describir **estructuras jerárquicas**, donde los requisitos más detallados se relacionan con su requisito fuente. Esos requisitos detallados **dan explicación adicional, detalle o clarificación** sobre el fuente, que puede verse como **una abstracción de los detallados**.

**La condición que lo distingue:** si un requisito detallado se deriva de uno de nivel superior **pero no es un prerrequisito** para ese requisito, entonces la relación es `refinado_a` (y no `requiere`).

Este tipo **compila muchas variantes** de la literatura, que resultaban difíciles de distinguir entre sí. Cubre situaciones donde:

- un requisito es **elaborado** por otro;
- un requisito más detallado **se deriva** de uno de alto nivel;
- uno o varios requisitos **se basan en** un requisito fuente;
- un requisito **se dividió en varias partes** — varios requisitos simples se consideran parte de uno complejo;
- un requisito **formaliza** a otro;
- un requisito de alto nivel es **una generalización** de uno o varios más detallados.

> **EJEMPLO.** Un requisito que dice *"el sistema debe soportar un seguimiento de los pedidos de clientes después de su entrega"* podría refinarse en requisitos que digan que durante el seguimiento debe ser posible comparar el costo de producir los productos de un pedido dado contra los presupuestos de fabricación de esos productos, y que el sistema debe facilitar cambiar esos presupuestos al hacer el seguimiento.

#### `cambia_a` (*changes_to*)

> **Un requisito cambia a otro si se desarrolla una versión nueva que reemplaza a la vieja.**

Se usa para describir **la historia de un requisito** — cómo evolucionó en el tiempo, relacionando sus distintas versiones.

Las razones para una versión nueva pueden ser varias: hacer el requisito **más comprensivo**, **cambiar detalles** internos, o **expresarlo más formalmente**.

> **EJEMPLO.** *"No debe tomar más de 10 segundos realizar una búsqueda de información de contacto"* podría cambiar a una versión nueva que diga *"no debe tomar más de 15 segundos"*.

#### `similar_a` (*similar_to*)

> **Un requisito enunciado es similar a, o se superpone con, uno o más requisitos.**

Describe situaciones donde un requisito es similar o se superpone con otro **en cómo está expresado**, o **en la idea subyacente similar** sobre qué debería poder hacer el sistema.

También sirve para describir **soluciones similares**, de las cuales hay que seleccionar una para que forme parte del sistema. Es decir: sirve para similitudes **tanto dentro de los requisitos como de sus soluciones potenciales**.

> **EJEMPLO.** *"El sistema debe soportar la gestión de ítems de biblioteca"* y *"el sistema debe proveer medios para manejar libros y revistas dentro de la biblioteca"* son similares, ya que tanto libros como revistas podrían considerarse ítems de biblioteca.

---

### 3.2 Interdependencias de restricción 🟡

Parte de la literatura introduce tipos bastante amplios y generales — que hay requisitos que dependen de otros o que restringen a otros. Los autores plantean como **hipótesis** que acá pueden identificarse interdependencias más detalladas, especialmente si se elabora la clasificación respecto de distintas actividades o decisiones. Por ahora identificaron dos tipos.

#### `requiere` (*requires*)

> **El cumplimiento de un requisito depende del cumplimiento de otro requisito.**

Describe que **si un requisito va a incluirse en el sistema, requiere que otro también se incluya**.

También sirve para describir relaciones jerárquicas **de naturaleza más fuerte que `refinado_a`**: acá significa que uno o más requisitos detallados **son requeridos, no opcionales**, para cumplir un requisito de nivel superior. Por eso `requiere` **puede verse como perteneciente parcialmente a la categoría estructural también**.

**Qué abarca:**

- Situaciones donde un requisito **debe estar entre los seleccionados** para poder implementar otro.
- Situaciones donde un requisito **no puede funcionar sin otro** — o sea, uno es **prerrequisito o precondición** del otro.
- Por eso mismo, **puede describir una interdependencia temporal**: un requisito necesita implementarse antes que otro.
- Y también relaciones **de naturaleza más débil**, donde los requisitos **se apoyan o refuerzan mutuamente** su cumplimiento — es decir, uno tiene un **efecto positivo** sobre el cumplimiento del otro sin ser estrictamente obligatorio.

> **EJEMPLO.** Si el sistema debe poder incluir correo electrónico y acceso web, **se requiere una conexión de red**.

#### `entra_en_conflicto_con` (*conflicts_with*)

> **Un requisito está en conflicto con otro si no pueden existir al mismo tiempo, o si aumentar la satisfacción de uno disminuye la satisfacción del otro.**

Notá que la definición tiene **dos casos distintos**:

1. Situaciones donde **es imposible implementar ambos**.
2. Situaciones donde los requisitos **tienen influencia negativa sobre el logro del otro** y hay que **hacer un compromiso** entre ellos.

**El conflicto es uno de los tipos de interdependencia más mencionados** en toda la literatura. Se identificaron algunas relaciones que pueden interpretarse como **razones del conflicto**:

- **necesitar los mismos recursos**;
- un requisito **describe una tarea que depende** de otro requisito;
- un requisito **describe una consecuencia** de otro.

> **EJEMPLO.** Si un requisito dice *"todo el personal debe poder buscar información tanto de productos como de clientes"* y otro dice *"solo el personal con estatus de seguridad A debe poder buscar clientes clasificados como militares"*, **los dos se contradicen y no pueden satisfacerse simultáneamente**.

> ⚠️ **Cruce con la cátedra.** Ese ejemplo es exactamente el tipo de contradicción que un conjunto de requisitos mal revisado deja pasar — porque **cada requisito, leído solo, es impecable**. El conflicto solo aparece al leerlos juntos. Es un buen argumento de por qué la calidad de un conjunto de requisitos no es la suma de la calidad de cada requisito.

---

### 3.3 Interdependencias de costo/valor 🟡

Se ocupan de **los costos de implementar un requisito en relación con el valor** que su cumplimiento le va a dar al cliente o usuario percibido.

#### `aumenta/disminuye_el_costo_de`

> **Si un requisito se elige para implementación, el costo de implementar otro requisito aumenta o disminuye.**

Relaciona requisitos que influyen de algún modo en el costo de implementación mutuo, haciendo más caro o más barato implementar al otro.

> **EJEMPLO.** Si un requisito dice que ningún tiempo de respuesta debe ser mayor a 5 segundos, **muy probablemente aumente el costo de implementar muchos otros requisitos**.

> Ese ejemplo es doblemente instructivo: es un **requisito no funcional** encareciendo funcionales. Conecta con lo que viste en el capítulo 4 —los RNF afectan varias funciones a la vez, no una— y en el capítulo 3 —los RNF limitan el espacio de diseño.

#### `aumenta/disminuye_el_valor_de`

> **Si un requisito se elige para implementación, el valor de otro requisito para el cliente aumenta o disminuye.**

Se enfoca en el efecto que las relaciones entre requisitos pueden tener sobre **el valor percibido por el cliente**. Algunos requisitos tienen **influencia positiva** sobre el valor de otros; otros tienen **influencia negativa**, por ejemplo **volviendo la funcionalidad más compleja**.

> **EJEMPLO.** La satisfacción del cliente por incluir un calendario de planificación en un teléfono móvil **probablemente aumente si es posible sincronizarlo** con los calendarios usados en PC.

---

## Mapa de la Parte 1

```
   SOLO 1 DE CADA 5 REQUISITOS ES VERDADERAMENTE SINGULAR

   ─────────────────────────────────────────────────────

   TRAZABILIDAD = describir y seguir la vida de un
   requisito, hacia adelante y hacia atrás, en todo
   el ciclo de vida

   POR MOMENTO          POR TIPO DE OBJETO
   pre-trazabilidad     horizontal (mismo tipo:
   (¿de dónde vino?)      requisito ↔ requisito)
   post-trazabilidad    vertical (tipos distintos:
   (¿dónde terminó?)      requisito → diseño → componente)

   LAS INTERDEPENDENCIAS SON:
   pre-trazabilidad + horizontal

   SIN TRAZABILIDAD: baja calidad, revisiones, más costo
   y tiempo, PÉRDIDA DE CONOCIMIENTO cuando la gente se va,
   decisiones equivocadas, malentendidos

   PERO: trazar cuesta. Decidir QUÉ trazar es parte del oficio.

   ─────────────────────────────────────────────────────

   LOS 7 TIPOS FUNDAMENTALES

   ESTRUCTURALES
   refinado_a ──► el detallado explica al general
                  (derivado pero NO prerrequisito)
   cambia_a ────► versión nueva reemplaza a la vieja
   similar_a ───► se superponen (requisitos o soluciones)

   DE RESTRICCIÓN
   requiere ────► uno no funciona sin el otro
                  (prerrequisito → también temporal)
   conflicto ───► no pueden coexistir, o uno degrada al otro

   DE COSTO/VALOR
   ± costo ─────► elegir uno encarece/abarata otro
   ± valor ─────► elegir uno hace a otro más/menos valioso
```

---

## Preguntas para chequear que quedó

1. ¿Qué proporción de requisitos son verdaderamente singulares? ¿Qué implica ese dato?
2. Nombrá las tres maneras en que un requisito puede afectar a otro.
3. ¿Por qué los autores dicen que las interdependencias "no son problemáticas en sí mismas"?
4. Explicá por qué descuidar las interdependencias distorsiona el análisis de impacto de un cambio.
5. ¿Por qué no siempre se pueden elegir los requisitos de mayor prioridad para una versión?
6. Definí trazabilidad de requisitos y desarmá la definición en sus cuatro partes.
7. Nombrá cuatro pares de objetos que se asocian para lograr trazabilidad.
8. ¿Qué cuatro beneficios trae la trazabilidad?
9. ¿Qué consecuencias tiene una práctica pobre de trazabilidad? Nombrá al menos cuatro.
10. ¿Por qué la pérdida de conocimiento cuando alguien deja el proyecto es un problema de trazabilidad?
11. Diferenciá pre-trazabilidad de post-trazabilidad: qué cubre cada una y a qué apunta.
12. Diferenciá trazabilidad horizontal de vertical, con un ejemplo de cada una.
13. ¿Dónde se ubican las interdependencias entre requisitos en esas dos clasificaciones?
14. Nombrá las tres perspectivas del meta-modelo de trazabilidad y qué destaca cada una.
15. ¿Por qué una llamada telefónica cuenta como "fuente"?
16. ¿Cuáles son las dos advertencias que hacen los autores sobre la trazabilidad?
17. ¿Por qué los tipos de interdependencia son difíciles de distinguir entre sí? Dé el ejemplo del capítulo.
18. Diferenciá `refinado_a` de `requiere`. ¿Cuál es la condición exacta que los separa?
19. ¿Para qué sirve `cambia_a` y qué razones puede haber para una versión nueva?
20. ¿Qué dos cosas puede describir `similar_a`?
21. ¿Cuáles son los dos casos que abarca `conflicto_con`? ¿Y las tres razones posibles de conflicto?
22. En el ejemplo del personal y los clientes militares, ¿por qué el conflicto no se detecta leyendo cada requisito por separado?
23. ¿Por qué un requisito no funcional de tiempo de respuesta aumenta el costo de muchos otros requisitos?

---

**FIN DEL CAPÍTULO 5 — PARTE 1**

*Sigue en la Parte 2: cómo el conocimiento de las interdependencias facilita siete actividades concretas de la ingeniería de software —gestión de requisitos, gestión de cambios, planificación de versiones, reutilización de componentes y de requisitos, diseño e implementación, y pruebas—, más la agenda de investigación del área.*
