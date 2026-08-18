# Lectura en español — Cap. 9 · Parte 3: Los mapas meta/estrategia

> **Origen.** Capítulo 9, secciones 9.3 y 9.4, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Colette Rolland y Camille Salinesi**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 2.** Se asumen conocidos los grafos Y/O, la comparación metas/escenarios y las cinco debilidades del enfoque.

---

## Aviso

Esta parte es **la propuesta propia de los autores** — no es estado del arte compartido, es su modelo. Es la parte menos conectada con tu cursada de todo el capítulo, y probablemente de toda la serie.

Dicho eso, tiene **dos ideas que sí valen** y que marqué en 🟡: la distinción entre **modelar la meta y modelar cómo se la logra**, y la observación de que **el mismo objetivo admite estrategias distintas** — que es el mismo principio que ya viste en la selección de técnicas de elicitación y en la priorización.

---

## 1. Por qué proponen algo nuevo 🟡

### El cambio de contexto

> **Los enfoques de modelado de metas se concibieron con el ciclo de vida tradicional en mente**: se capturan metas estratégicas altas para elicitar requisitos y construir la funcionalidad que los cumple.
>
> **Sin embargo, en años recientes el desarrollo "desde cero" pasó a ser la excepción**, y emergió un contexto nuevo.

El contraste que plantean:

```
   ANTES                          HOY
   un sistema cumplía el          un sistema debe concebirse en
   propósito de UNA               una perspectiva más amplia,
   organización y de UN           para cumplir el propósito de
   conjunto de clientes           VARIAS organizaciones y ser
                                  ADAPTABLE a distintas
                                  situaciones de uso / conjuntos
                                  de clientes
```

Lo primero es típico de un desarrollo tipo **ERP**; lo segundo es la preocupación del **desarrollo de líneas de producto** y del **software adaptable**.

### La variabilidad 🟡

Eso lleva a la noción de **variabilidad del software**:

> **Variabilidad: la capacidad de un sistema de software de ser cambiado, personalizado o configurado para un contexto específico.**

Y la posición que toman los autores:

> Mientras la comunidad de software **estudia la variabilidad como un problema de diseño y se concentra en cuestiones de implementación**, nosotros creemos que **capturar la variabilidad al nivel de las metas es esencial** para atender la naturaleza multi-propósito de los sistemas nuevos.

### De un propósito con una cara a un propósito con muchas 🟡

El argumento central:

> **La variabilidad implica pasar de sistemas con un propósito de una sola faceta a sistemas con un propósito multi-facetado.** Mientras el primero **se concentra en el descubrimiento de metas**, la naturaleza multi-facetada **lo extiende para considerar las muchas maneras distintas de lograr la meta.**

El ejemplo que dan:

```
   ANTES
   meta: "Comprar material"
   → alcanzaba con saber que la organización lo logra
     PRONOSTICANDO la necesidad de material
   → UNA sola estrategia: propósito de una cara

   AHORA
   meta: "Comprar material"
   → hay que introducir además otras estrategias,
     por ejemplo la de PUNTO DE REPOSICIÓN
   → MUCHAS estrategias: propósito multi-facetado
```

**La conclusión:**

> Lo anterior señala la necesidad de **balancear la orientación a metas con la introducción de ESTRATEGIAS para lograrlas. Esa es la esencia de los mapas meta/estrategia.**

> ⚠️ **Cruce con la cátedra.** Esta idea —que **una meta no basta, hay que decir también por qué camino se la logra**— es la misma que ya viste en dos lugares distintos: en la selección de técnicas de elicitación (capítulo 2, el hallazgo de Hickey y Davis: la elección de técnica se justifica contra el caso) y en la priorización (capítulo 4: no hay solución óptima, hay decisiones que sostener).
>
> El patrón se repite: **declarar el objetivo sin declarar el camino deja la mitad de la decisión sin documentar.** Y la parte no documentada es justamente la que después no se puede discutir ni auditar.

---

## 2. El formalismo del mapa 🟢

### La definición

> **Un mapa meta/estrategia —o mapa, para abreviar— es un grafo con INTENCIONES como nodos y ESTRATEGIAS como aristas. Una arista que entra a un nodo identifica una estrategia que puede usarse para lograr la intención de ese nodo.**
>
> El mapa muestra, entonces, **qué intenciones pueden lograrse mediante qué estrategias, una vez que se ha logrado una intención precedente.**

### Los tres conceptos base

| Concepto | Definición |
|---|---|
| **Intención** | **Una meta, un enunciado optativo que expresa lo que se quiere**: un estado que se espera alcanzar o mantener. Cada mapa tiene **dos intenciones especiales, Inicio y Fin**, asociadas a los estados inicial y final |
| **Estrategia** | **Un enfoque, una manera, un medio para lograr una intención** |
| **Sección** | **La agregación de una intención origen, una intención destino y una estrategia** — el triplete `<origen, destino, estrategia>` |

El ejemplo que usan es una reserva de hotel:

```
   INTENCIÓN: "Hacer reserva de habitación"
     su logro deja al sistema en el estado "Reserva hecha"

   ESTRATEGIAS para lograrla:
     · por Internet
     · visitando una agencia de viajes

   SECCIONES resultantes:
     <Inicio, Hacer reserva de habitación, por Internet>
     <Inicio, Hacer reserva de habitación, por agencia>
```

**La sección es la construcción básica del mapa**, que en sí mismo puede verse como un ensamblado de secciones. **Cuando un mapa modela un propósito multi-facetado, cada sección representa una faceta.**

> Una **faceta** destaca una característica consistente y cohesiva del sistema que los interesados quieren que se implemente. Es cercana a la noción de **característica** (*feature*), definible como *"un aspecto, cualidad o característica prominente y distintiva, visible al usuario, de un sistema de software"*.

### Los cuatro tipos de relación 🟢

#### Relación de hilo (*thread*)

> Es posible que **una intención destino se logre desde una intención origen de muchas maneras distintas**. Cada una se expresa como una sección. A esa topología se la llama **multi-hilo**, y las secciones participantes están **en relación de hilo** entre sí.

```
                   por transferencia electrónica
   Hacer reserva ──────────────────────────────► Aceptar pago
   de habitación ──────────────────────────────►
                        por tarjeta de crédito

   las dos secciones están en relación de HILO:
   son dos maneras distintas de lograr lo mismo
```

**La relación de hilo entre dos secciones representa directamente la variabilidad** asociada a un propósito multi-facetado.

#### Relación de camino (*path*)

> Establece una **relación de precedencia/sucesión** entre secciones. **Para que una sección suceda a otra, su intención origen debe ser la intención destino de la precedente.**

Dadas las relaciones de hilo y de camino, **una intención puede lograrse por varias combinaciones de secciones** — a eso se lo llama **multi-camino**.

```
   CAMINO 1
   <Inicio, Hacer reserva, por Internet> →
   <Hacer reserva, Aceptar pago, transferencia> →
   <Aceptar pago, Fin, normalmente>

   CAMINO 2
   <Inicio, Hacer reserva, por Internet> →
   <Hacer reserva, Aceptar pago, tarjeta> →
   <Aceptar pago, Fin, normalmente>
```

**Desde el punto de vista de las facetas:** el camino introduce una **faceta compuesta**, mientras que la faceta basada en una sección es **atómica**.

#### Relación de paquete (*bundle*)

> **Varias secciones que tienen el mismo par origen-destino y que son MUTUAMENTE EXCLUYENTES están en relación de paquete.**
>
> **La diferencia entre hilo y paquete es el O exclusivo de las secciones en el segundo, frente al O inclusivo en el primero.**

```
   HILO ─────► se pueden usar VARIAS (O inclusivo)
   PAQUETE ──► solo UNA (O exclusivo)
```

#### Relación de refinamiento

> **Una sección de un mapa puede refinarse como otro mapa.** El mapa refinado completo representa entonces a esa sección.
>
> **El refinamiento es un mecanismo de abstracción por el cual un ensamblado complejo de secciones del nivel i+1 se ve como una única sección del nivel i.**

### Cómo queda el modelo completo 🟢

Resumido por los propios autores:

```
   · El propósito del sistema se captura en una
     JERARQUÍA DE MAPAS. La intención asociada al mapa
     raíz es el enunciado de propósito de más alto nivel.
     Cada sección puede refinarse como un mapa, y la
     aplicación recursiva produce la jerarquía.

   · En cualquier nivel dado, la dimensión multi-facetada
     se basa en las topologías multi-hilo y multi-camino:
       MULTI-HILO ──► faceteo LOCAL: las distintas maneras
                      de lograr una intención directamente
       MULTI-CAMINO ► faceteo GLOBAL: las distintas
                      combinaciones de intenciones y
                      estrategias para lograr la intención
                      del mapa
```

---

## 3. El ejemplo: el módulo de materiales de SAP 🟢

Los autores ilustran el mapa con el **módulo de Gestión de Materiales (MM) de SAP R/3**, que da soporte automatizado a las operaciones diarias de cualquier negocio que consuma materiales.

**Sus cinco componentes clave:** planificación de necesidades de materiales · compras · gestión de inventario · gestión de almacenes · verificación de facturas. Más dos de apoyo: sistema de información e intercambio electrónico de datos.

### El mapa raíz

> **En su totalidad, el módulo puede verse como cumpliendo el propósito: "Satisfacer la necesidad de material eficientemente".** Esa es la intención del mapa raíz.

Para cumplirlo hay que lograr **dos intenciones**: **Comprar material** y **Monitorear stock** — que reflejan la visión convencional de la gestión de materiales como *"procurar materia prima y asegurar la efectividad de la tubería logística por la que fluyen los materiales"*.

Y hay **un orden entre ellas**: **el stock no puede monitorearse hasta que se lo haya procurado.**

> **El mapa tiene 25 caminos desde Inicio hasta Fin.** Así, es capaz de presentar **una perspectiva global de las diversas maneras de lograr el propósito principal.**

### Las facetas de "Comprar material" 🟢

Tres estrategias para lograrla:

| Estrategia | Qué permite |
|---|---|
| **De planificación** | Contiene, a su vez, **dos facetas mutuamente excluyentes** (un paquete): comprar **cuando el stock cae al punto de reposición**, o comprar **según la necesidad planificada** |
| **Manual** | Permite al comprador **ingresar manualmente una solicitud de compra**, que lleva a generar la orden |
| **De recordatorio** | Sirve para **recordarle al proveedor que entregue el material** cuando la entrega no se hace a tiempo |

Y una observación que los autores destacan y que es la más interesante del ejemplo:

> **Puede verse que la estructura de componentes de SAP NO REFLEJA DIRECTAMENTE la funcionalidad alternativa de lograr la misma meta.**

Las dos estrategias del paquete corresponden a funciones de un componente; la manual es parte de otro. **La organización técnica del producto y la organización por intenciones no coinciden.**

> ⚠️ **Cruce con la cátedra.** Esa observación es el argumento central a favor de modelar por intenciones y no por módulos: **la estructura del producto refleja decisiones de implementación, no las maneras de cumplir un objetivo.** Dos funciones que sirven al mismo fin pueden estar en componentes distintos, y nada en el catálogo del producto te lo dice.
>
> Es la misma tensión que el capítulo 3 planteaba entre requisitos de usuario (dominio del problema) y de sistema (dominio de la solución).

### Las facetas de "Monitorear stock" 🟢

Tiene **tres clases de faceta**:

**a) Procuración/registro.** El material puede procurarse **contra una orden de compra** o **sin orden formal, directamente del mercado**. En el segundo caso el material está listo para registrarse de inmediato; en el primero, el registro se hace después de la entrega contra la orden. Dos facetas:

- Registro de la entrega **contra una orden de compra**.
- Registro de material procurado **por compra directa**.

La primera es en realidad **compuesta**, y su refinamiento revela un mapa de nivel inferior con dos intenciones ordenadas: **Aceptar entrega** y **Ingresar mercadería en stock**.

*Aceptar entrega* tiene **cuatro facetas**: una para cuando la entrega es estrictamente según la orden, y tres que permiten aceptarla **dentro de tolerancias especificadas**:

```
   · la entrega cumple la orden de compra
   · hay que reconciliar contra la orden de compra
   · hay que reconciliar entre las UNIDADES distintas
     que usan proveedor y receptor
   · hay que reconciliar sub-entregas o sobre-entregas
```

Y una precisión técnica del modelo: **las tres facetas de reconciliación pueden usarse simultáneamente**, por eso **no forman un paquete sino que se representan cada una como un hilo**.

**b) Logística de materiales.** Entran en juego **solo después del registro inicial**. La pregunta es sobre el movimiento del stock y cómo se lo sigue: **Monitorear stock tiene que lograrse repetidamente después de cada movimiento** hacia/desde almacenes, a puntos de consumo, o para inspección de calidad. Tres facetas: control del movimiento hacia/desde almacenes · transferencia a tiempo a puntos de consumo · control de calidad del material transferido.

**Estas tres estrategias tienen a Monitorear stock tanto como intención inicial como destino** — lo que representa **el logro repetido** de la misma intención.

**c) Financiera.** Toma la forma del componente de verificación de facturas.

---

## 4. Los mapas para personalizar sistemas multi-propósito 🟢

### El cambio en el proceso

La visión multi-propósito **tiene una contraparte en la dimensión del proceso**, que implica un cambio del proceso tradicional de IR:

```
   PROCESO TRADICIONAL
   modelo TAL-COMO-ES ──── propagación ────► modelo A-SER

   PROCESO DE PERSONALIZACIÓN
   modelo TAL-COMO-SE-DESEA ──┐
                              ├─ proceso de ──► modelo A-SER
   modelo PODRÍA-SER ─────────┘  EMPAREJAMIENTO
   (capacidad funcional del
    sistema multi-propósito,
    p. ej. un ERP)
```

> **Las metas organizacionales se expresan en el modelo Tal-como-se-desea. El modelo Podría-ser refleja la capacidad funcional del sistema multi-propósito. Y el modelo A-ser debe definirse como el MEJOR EMPAREJAMIENTO entre ambos.**

Ese proceso lleva a **personalizar el modelo Podría-ser para adaptarlo a los requisitos organizacionales** del Tal-como-se-desea.

### Qué esperan las personas de un modelo de proceso 🟡

Los autores relatan lo que observaron en proyectos reales, y esta parte sí es transferible:

> **Primero:** las personas **están enfrentando un problema y tienen una meta en mente**, y les gustaría que los modelos de proceso **les permitieran ubicar ambos fácilmente y les sugirieran distintos caminos alternativos** para lograr la meta y resolver el problema.
>
> **Segundo:** quieren **libertad y flexibilidad en sus maneras de trabajar. Una única manera de trabajar impuesta no es aceptable.** Esperan **aprender sobre las distintas maneras** en que cada meta puede lograrse.
>
> **Tercero:** quieren **consejo sobre cómo elegir entre las distintas soluciones alternativas** que se les propongan.

### Las tres estrategias de emparejamiento 🟢

El modelo de proceso que desarrollaron para un proyecto de personalización de ERP ofrece **tres maneras distintas** de construir el mapa emparejado, y **la elección depende del contexto**:

| Estrategia | Cuándo usarla |
|---|---|
| **Dirigida por lo deseado** | Si el contexto es de **requisitos de negocio bien definidos a los que el sistema debe ajustarse**, y **el desarrollo interno no es un problema** |
| **Dirigida por el sistema** | Si **el sistema es menos probable de cambiar que el negocio** —porque personalizarlo se volvió demasiado caro— **o si la personalización es una oportunidad para cambiar el negocio**, por ejemplo porque permite generalizar su buena práctica asociada |
| **Dirigida por lo existente** | Si es **particularmente importante preservar la funcionalidad del sistema existente** en el sistema futuro. Son los **requisitos de no regresión funcional** |

> **Las tres estrategias tienen las mismas intenciones inicial y destino**, lo que muestra que **la intención destino puede lograrse de manera no determinista**. Eso refleja que **distintas organizaciones pueden intercalar estas estrategias en combinaciones distintas**, siguiendo así procesos diferentes.

---

## 5. Conclusión del capítulo 🔴

Los autores cierran con **seis ventajas** del enfoque dirigido por metas. Vale leerlas porque resumen todo el capítulo:

```
   1. Las metas TIENDEN UN PUENTE entre las estrategias
      organizacionales y los requisitos del sistema,
      proveyendo un vínculo conceptual entre el sistema
      y su contexto organizacional.

   2. Los grafos de descomposición de metas proveen
      PRE-TRAZABILIDAD entre las preocupaciones estratégicas
      de alto nivel y las restricciones técnicas de bajo
      nivel, facilitando la propagación de los cambios del
      negocio hacia las características del sistema.

   3. Las metas unidas por O introducen EXPLÍCITAMENTE las
      opciones de diseño, que así pueden discutirse,
      negociarse y decidirse.

   4. Los enlaces Y sostienen el REFINAMIENTO de metas de
      alto nivel hacia metas de nivel más bajo, hasta
      encontrar metas operacionalizables que se asocian
      a requisitos del sistema.

   5. Las técnicas potentes de elicitación de metas
      FACILITAN EL DESCUBRIMIENTO de metas y requisitos.

   6. Las relaciones entre metas y conceptos como objetos,
      eventos y operaciones facilitan el MAPEO de los
      grafos de metas hacia la especificación de diseño.
```

Y el reconocimiento final:

> **Los enfoques dirigidos por metas sufren varias debilidades, en parte por la naturaleza del concepto de meta y en parte por la falta de modelado y soporte del proceso.**

> ⚠️ **Cruce con la cátedra.** Fijate en el punto 3, que es el que más se puede aprovechar en un TP: **las metas alternativas hacen explícitas las opciones de diseño.** Cuando modelás con O en vez de decidir de antemano, **estás documentando que hubo una elección** — y eso es lo que después permite discutirla y justificarla.
>
> Es el mismo principio que atraviesa toda la serie: en el capítulo 2 (justificar la técnica de elicitación elegida), en el 4 (la priorización sostiene la decisión, no la reemplaza) y en el 7 (generar variedad de opciones antes de decidir). **Lo que no se hace explícito no se puede fundamentar.**

---

## Mapa de la Parte 3

```
   EL PROBLEMA NUEVO
   los sistemas ya no son de UNA organización y UN
   conjunto de clientes → VARIABILIDAD
   → hay que capturarla al nivel de las METAS,
     no solo del diseño

   propósito de UNA cara ──► propósito MULTI-FACETADO
   (descubrir la meta)       (+ las muchas maneras de
                              lograrla = ESTRATEGIAS)

   ─────────────────────────────────────────────

   EL MAPA
   nodos = INTENCIONES · aristas = ESTRATEGIAS
   sección = <origen, destino, estrategia>

   RELACIONES
   hilo ────────► varias maneras de lograr lo mismo
                  (O inclusivo) → faceteo LOCAL
   camino ──────► precedencia entre secciones
                  → faceteo GLOBAL
   paquete ─────► como el hilo pero MUTUAMENTE
                  EXCLUYENTE (O exclusivo)
   refinamiento ► una sección se abre como otro mapa
                  → jerarquía de mapas

   ─────────────────────────────────────────────

   EJEMPLO SAP: la estructura de COMPONENTES del
   producto NO refleja las maneras alternativas de
   lograr la misma meta

   ─────────────────────────────────────────────

   LAS 6 VENTAJAS DEL ENFOQUE POR METAS
   puente organización/sistema · pre-trazabilidad ·
   O = opciones de diseño EXPLÍCITAS · Y = refinamiento ·
   elicitación · mapeo al diseño
```

---

## Preguntas para chequear que quedó

1. ¿Qué cambió en el contexto de desarrollo que motiva la propuesta de los mapas?
2. Definí variabilidad del software. ¿Por qué los autores sostienen que hay que capturarla al nivel de las metas?
3. ¿Qué diferencia hay entre un propósito de una faceta y uno multi-facetado?
4. Definí mapa, intención, estrategia y sección.
5. ¿Qué es una faceta y con qué noción más conocida se emparenta?
6. Explicá la relación de hilo. ¿Qué tipo de faceteo introduce?
7. Explicá la relación de camino. ¿Qué es una faceta compuesta?
8. ¿Cuál es la diferencia exacta entre una relación de hilo y una de paquete?
9. ¿Qué hace el refinamiento y qué estructura produce al aplicarse recursivamente?
10. En el ejemplo de SAP, ¿cuáles son las dos intenciones del mapa raíz y por qué hay un orden entre ellas?
11. ¿Cuáles son las tres estrategias para "Comprar material"?
12. ¿Por qué las tres facetas de reconciliación se representan como hilos y no como paquete?
13. ¿Qué observación hacen los autores sobre la estructura de componentes de SAP? ¿Por qué es importante?
14. Compará el proceso tradicional de IR con el proceso de personalización de un sistema multi-propósito.
15. ¿Qué tres cosas esperan las personas de un modelo de proceso, según la experiencia de los autores?
16. Describí las tres estrategias de emparejamiento y en qué contexto conviene cada una.
17. ¿Qué son los requisitos de no regresión funcional?
18. Nombrá las seis ventajas del enfoque dirigido por metas.
19. ¿Por qué las metas unidas por O son valiosas para la discusión y la justificación?

---

**FIN DEL CAPÍTULO 9 — PARTE 3**

**FIN DEL CAPÍTULO 9**

*Sigue el capítulo 10: gestión de grandes repositorios de requisitos en lenguaje natural, en 2 partes.*
