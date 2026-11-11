# Clase desde cero — LEL — Módulo 1: Qué es el LEL y cómo se escribe un símbolo

**Serie:** Clase desde cero — LEL (módulo 1 de 4) · **Materia:** Ingeniería de Requisitos · **Unidad:** clase11

---

## Sobre este documento

**Qué cubre:** el problema que resuelve el LEL, qué es, cómo se escribe cada entrada (el "símbolo"), los cuatro tipos de símbolo con su plantilla, y las reglas de forma que la cátedra corrige.

**Qué NO cubre:** cómo se enlazan los símbolos entre sí (módulo 2), cómo se descubren en el negocio (módulo 3) y cómo se encuentran los errores de un LEL ya hecho (módulo 4).

**Cómo leerlo:** primero viene siempre un caso concreto y después la definición. Si una palabra nueva aparece, tiene su línea de explicación ahí mismo. Al final hay un checkpoint de 6 preguntas, sin respuestas: hacelo sin mirar el texto.

**Notación de esta serie:** cuando una palabra dentro de una descripción es *otro símbolo del mismo LEL*, va entre dobles corchetes: `[[Producto]]`. Es la notación de Obsidian, la herramienta que usa la cátedra. En papel, lo mismo se hace subrayando la palabra.

## De dónde venís

De las clases anteriores de la materia asumo que ya sabés:
- Qué es un **requisito funcional** (lo que el sistema tiene que hacer) y uno **no funcional** (con qué calidad lo hace).
- Qué es un **caso de uso**: una función del sistema vista desde un actor, con su flujo de pasos.
- Que los requisitos se **elicitan** (se descubren) entrevistando gente y leyendo documentos.

Nada más. Todo lo que sigue se explica desde cero.

---

## 1. 🔴 El problema: la misma palabra, otro significado

Imaginate que te contratan para relevar los requisitos de una compañía de seguros. En la primera entrevista, el gerente dice:

> "Cuando un **productor** tiene mucha **cartera**, el **cúmulo** en una zona nos preocupa. Y si una **cobertura está suspendida**, hay que ver si la **rehabilitamos**."

Vos entendiste las palabras. ¿Entendiste la oración?

| Palabra | Lo que significa en la vida diaria | Lo que significa en ese negocio |
|---|---|---|
| Productor | El que fabrica algo | Intermediario que vende pólizas y atiende asegurados |
| Cartera | Billetera, bolso | Conjunto de pólizas asignadas a un productor |
| Rehabilitar | Recuperar, reparar | Reactivar una póliza suspendida por falta de pago, después de pagar la deuda |
| Suspendida | Dada de baja | La póliza sigue vigente, pero si pasa algo no cubre |
| Cúmulo | Un montón | Suma de los montos asegurados en una misma zona, que la aseguradora limita |

Con el significado de la vida diaria, la oración del gerente no quiere decir nada. Con el del negocio, es un problema concreto de riesgo. Y si escribís un requisito sin saber esto, lo escribís mal: "el sistema debe permitir rehabilitar la póliza" significa otra cosa para vos que para el cliente.

**La idea central de todo este tema:** primero entendé el vocabulario, después el problema. Nadie puede analizar un negocio cuyas palabras no conoce.

Dos nombres que vas a ver todo el tiempo:
- **Universo del Discurso (UdeD):** nombre pomposo para "el mundo del cliente": su negocio, su gente, sus documentos, su forma de hablar. Todo lo que tenés que entender.
- **Lenguaje de la aplicación:** la forma particular de hablar de ese negocio. Es lenguaje natural (castellano), pero con palabras propias y con palabras comunes usadas con otro sentido.

## 2. 🔴 Qué es el LEL

El **LEL** (Léxico Extendido del Lenguaje; "léxico" = vocabulario) es un **glosario del negocio**: una lista de las palabras importantes del cliente, cada una con su definición. Lo que lo hace distinto de un glosario común es que **cada palabra se describe con dos partes**, no una:

- **qué es** la palabra (como en cualquier diccionario), y
- **cómo actúa** esa palabra en el negocio: qué hace, qué le hacen, con qué se relaciona.

Eso segundo no está en un diccionario, y es lo que te hace entender el negocio.

**Para qué sirve:**

| Beneficio | Qué quiere decir |
|---|---|
| Buena comunicación | Vos y el cliente hablan de lo mismo cuando dicen "cartera" |
| Validación más simple | El cliente entiende los documentos que escribís porque usan sus palabras |
| Ancla de los modelos | Los escenarios (serie siguiente) y los requisitos se escriben con las palabras del LEL, así que se puede rastrear de dónde salió cada cosa |
| Repositorio de conocimiento | Sirve para que alguien nuevo en el equipo aprenda el negocio |

> 🎓 **Para el parcial, si te preguntan: ¿qué es el LEL?**
> Es un glosario del dominio de la aplicación que describe cada símbolo por lo que es (noción) y por cómo actúa en el negocio (impacto). Se construye antes de entender el problema, para que los involucrados compartan el mismo vocabulario, y es el punto de partida de los escenarios y los requisitos.

## 3. 🔴 El símbolo: nombre, noción e impacto

Cada entrada del LEL se llama **símbolo**. Vamos a ver uno antes de definirlo.

**El caso de esta serie:** una tienda de electrodomésticos que vende en cuotas. Su vocabulario tiene cosas como cliente, vendedor, cajero, analista de crédito, producto, orden de compra, plan de cuotas, cuota, deuda, factura, legajo del cliente, vender, emitir factura, cobrar cuota, aprobar crédito, cancelar, aprobado, en mora.

Así se ve el símbolo **Cliente** en ese LEL:

> ### Cliente
> *Tipo: Sujeto · Sinónimo: Comprador*
>
> **Noción**
> - Es una persona que compra un Producto.
>
> **Impacto**
> - Elige un [[Producto]] con el [[Vendedor]].
> - Puede pagar con un [[Plan de Cuotas]].
> - Firma la [[Orden de Compra]].
> - Paga cada [[Cuota]] al [[Cajero]].
> - Puede pedir [[Cancelar(1)]] antes de la entrega.
> - Debe [[Cancelar(2)]] la [[Deuda]].

Leélo de arriba a abajo:

- **Nombre:** `Cliente`. Es la palabra tal como la usa la tienda. Si en la tienda también le dicen "comprador", eso es un **sinónimo** y va en la misma entrada (lo vemos en el módulo 2).
- **Noción:** *qué es* un cliente. Acá alcanza con una oración; pueden ser varias, pero siempre al menos una. Si tuvieras que explicarle a alguien de afuera qué es un cliente en esta tienda, es esto.
- **Impacto:** *cómo actúa* el cliente en el negocio. Cada oración es una cosa que hace o que le pasa. Fijate que casi todas las oraciones mencionan **otro símbolo** entre corchetes: Producto, Vendedor, Plan de Cuotas… Eso no es casualidad, es la regla más importante del LEL y es el tema del módulo 2.

> 🧵 **Hilo abierto (a).** En la noción dice "compra un Producto", y *Producto* no tiene corchetes, aunque es un símbolo del LEL. ¿Importa? Dejalo anotado. Se responde en el módulo 2.

> 🧵 **Hilo abierto (b).** En el impacto aparecen `Cancelar(1)` y `Cancelar(2)`: dos símbolos con el mismo nombre y un número. ¿No es un error tener dos veces la misma palabra? También se responde en el módulo 2.

**Ahora sí, la definición.** Un símbolo es una palabra o frase con significado especial en el negocio, y tiene tres partes:

| Parte | Qué es | Pregunta que responde |
|---|---|---|
| **Nombre** | La palabra tal como la usa el cliente (uno o varios, si hay sinónimos) | ¿Cómo le dicen? |
| **Noción** | Lo que el símbolo *es* | ¿Qué es? |
| **Impacto** | Cómo el símbolo *actúa* en el negocio | ¿Qué hace? ¿Qué le hacen? |

Reglas mínimas: **todo símbolo tiene al menos un nombre, una oración en la noción y una oración en el impacto.** Una entrada con noción vacía o impacto vacío está incompleta.

> ⚠️ **Nota de cátedra.** Algunos textos admiten símbolos sin impacto. En la materia, no: siempre al menos una oración en cada parte. Para el parcial, respondé eso.

> 🎓 **Para el parcial, si te preguntan: ¿qué diferencia hay entre noción e impacto?**
> La noción es la denotación del símbolo: dice qué es. El impacto es la connotación: dice cómo actúa en el dominio, qué acciones realiza o recibe y con qué otros símbolos se relaciona. Todo símbolo necesita al menos una oración de cada una.

🕳️ **Madriguera — denotación y connotación.** Son los nombres técnicos de la lingüística para "qué es" y "qué evoca o cómo actúa". La cátedra los usa como sinónimos de noción e impacto. No hace falta saber más. *Volvé al camino.*

## 4. 🔴 Los cuatro tipos de símbolo

Volvamos a la lista de palabras de la tienda y agrupémoslas por lo que *son*:

| Palabras | Qué tienen en común | Tipo |
|---|---|---|
| Cliente, Vendedor, Cajero, Analista de Crédito | Son quienes **hacen cosas** | **Sujeto** |
| Producto, Orden de Compra, Plan de Cuotas, Cuota, Deuda, Factura, Legajo del Cliente | Son cosas a las que **les hacen cosas** | **Objeto** |
| Vender, Emitir Factura, Cobrar Cuota, Aprobar Crédito, Cancelar | Son **acciones** | **Verbo** |
| Aprobado, En Mora | Son **condiciones** en las que alguien o algo puede estar | **Estado** |

Esos son los cuatro tipos. ¿Para qué sirve clasificar? Porque **cada tipo se describe de una forma distinta**: lo que va en la noción y en el impacto cambia según el tipo. A eso se le llama la **plantilla** del tipo.

| Tipo | Qué es | Qué va en la **Noción** | Qué va en el **Impacto** |
|---|---|---|---|
| **Sujeto** | Entidad activa: persona, área, máquina o sistema que realiza actividades | Quién es | Actividades o responsabilidades que ejecuta o recibe |
| **Objeto** | Entidad pasiva, a la que se le aplican acciones | Qué representa, sus características y los objetos con que se relaciona | Acciones que se le aplican o se realizan con él |
| **Verbo** | Actividad o acción que ocurre en el negocio | Propósito; quién, cuándo y dónde la ejecuta; sobre qué objeto | Procedimientos, situaciones que la impiden y acciones que desencadena |
| **Estado** | Condición en la que están sujetos, objetos o verbos | Qué significa y qué acciones llevaron a él | Otros estados y acciones que pueden ocurrir desde él |

Una frase para recordarlo con el ejemplo que usa la cátedra: *el empleado de logística (sujeto) ubica (verbo) una obra de arte (objeto) y queda expuesta (estado).*

### 4.1 Un ejemplo de cada tipo, explicado

Ya viste un **Sujeto** (Cliente). Fijate que su noción dice quién es, y su impacto es una lista de cosas que hace: elige, firma, paga… Exactamente lo que pide la plantilla.

**Objeto:**

> ### Producto
> *Tipo: Objeto*
>
> **Noción**
> - Es un electrodoméstico que la tienda [[Vender|vende]].
> - Se incluye en una [[Orden de Compra]].
>
> **Impacto**
> - El [[Vendedor]] lo ofrece al [[Cliente]].
> - Se entrega al [[Cliente]] después de [[Emitir Factura]].
> - Vuelve a la tienda cuando ocurre [[Cancelar(1)]].

Por qué está escrito así: la noción dice *qué representa* (un electrodoméstico) y *con qué objeto se relaciona* (la orden de compra). El impacto son *acciones que se le aplican*: lo ofrecen, lo entregan, vuelve. El producto no hace nada por sí mismo; le hacen cosas. Esa es la marca de un objeto.

**Verbo:**

> ### Vender
> *Tipo: Verbo*
>
> **Noción**
> - Lo realiza el [[Vendedor]] con el [[Cliente]] en el salón de ventas.
> - Su propósito es acordar la compra de un [[Producto]].
>
> **Impacto**
> - Genera una [[Orden de Compra]].
> - Si el [[Cliente]] elige un [[Plan de Cuotas]], desencadena [[Aprobar Crédito]].
> - No puede realizarse si el [[Cliente]] está [[En Mora]].

Por qué está escrito así: la noción responde *quién* (vendedor), *con quién* (cliente), *dónde* (salón), *para qué* (acordar la compra) y *sobre qué* (producto). El impacto tiene las tres cosas de la plantilla: qué procedimiento sigue (genera una orden), qué desencadena (aprobar crédito) y qué lo impide (cliente en mora). Y el nombre está en **infinitivo**: Vender, no "venta" ni "vendiendo".

**Estado:**

> ### En Mora
> *Tipo: Estado*
>
> **Noción**
> - Es el estado de un [[Cliente]] que no pagó una [[Cuota]] en su fecha de vencimiento.
> - Se llega a él cuando el [[Cajero]] registra la [[Cuota]] vencida sin [[Cobrar Cuota|cobrarla]].
>
> **Impacto**
> - Mientras está En Mora, el [[Vendedor]] no puede [[Vender|venderle]].
> - Sale del estado cuando el [[Cliente]] realiza [[Cancelar(2)]] de la [[Deuda]].

Por qué está escrito así: la noción dice *qué significa* y *qué acción llevó a él* (no pagar la cuota). El impacto dice *qué pasa desde ahí* (no le venden) y *cómo se sale* (cancelando la deuda). Un estado siempre se describe en relación a cómo se entra y cómo se sale.

Detalle de notación que ya apareció: `[[Cobrar Cuota|cobrarla]]`. La barra vertical permite que en el texto se lea "cobrarla" pero el enlace apunte al símbolo `Cobrar Cuota`. Así el nombre queda en infinitivo y la oración se lee natural. Lo vas a usar en Obsidian.

### 4.2 La trampa más común al clasificar

Un sustantivo que termina en *-ción*, *-miento* o parecidos suele ser un **objeto** o el resultado de un verbo, no un sujeto: "inscripción", "consulta", "reserva" no hacen nada, les hacen cosas. Preguntate siempre: **¿esto actúa o le actúan?** Si actúa, es sujeto. Si le actúan, es objeto. Si es la acción misma, es verbo (y va en infinitivo: "inscribirse", "consultar", "reservar").

> 🎓 **Para el parcial, si te preguntan: ¿cuáles son los tipos de símbolo del LEL?**
> Sujeto (entidad activa que realiza actividades), objeto (entidad pasiva a la que se le aplican acciones), verbo (actividad del dominio) y estado (condición de un sujeto, objeto o verbo). Cada tipo tiene una plantilla que indica qué va en la noción y qué en el impacto.

🕳️ **Madriguera — subtipos por negocio.** En algunos trabajos se subdividen los tipos según el negocio: sujetos en "personas" y "sectores", objetos en "formularios", "índices", etc. La cátedra usa solo los cuatro tipos. *Volvé al camino.*

## 5. 🔴 Las reglas de forma

Son pocas, pero la cátedra las corrige todas. Cada fila es un error que la cátedra corrige o que es típico.

| Regla | ❌ Mal | ✅ Bien | Por qué |
|---|---|---|---|
| El nombre va en **singular** | `Clientes` | `Cliente` | El LEL define el concepto, no la cantidad |
| El verbo va en **infinitivo** | `Solicitando Turno`, `Venta` | `Solicitar Turno`, `Vender` | Si no, se confunde con un objeto ("la venta") y se clasifica mal |
| **Una idea y un solo verbo por oración** | "El cliente elige el producto, firma la orden y paga la cuota" | Tres oraciones, una por acción | Cada acción puede mencionar otro símbolo distinto y se puede controlar por separado |
| **Oraciones cortas y directas** | "A los efectos de concretar la operación comercial, el cliente procede a…" | "El cliente firma la orden de compra." | El cliente tiene que poder leerlo y decir "sí, es así" |
| El nombre es **el que usa el negocio**, aunque sea largo | `AC` (inventado) | `Analista de Crédito` | Si vos le cambiás el nombre, el cliente no lo reconoce |
| **Al menos una oración** en noción y una en impacto | Impacto vacío | Siempre algo | Un símbolo sin impacto no dice cómo actúa |
| La descripción **respeta la plantilla** del tipo | Un sujeto cuyo impacto describe sus características | Un sujeto cuyo impacto lista lo que hace | Si no, está mal clasificado o mal descripto |

> ⚠️ **Nota de cátedra.** Algunos textos aceptan el verbo "en su forma sustantiva" (Venta). En la materia se corrige: **infinitivo siempre**.

## 6. 🟡 Lo que todavía no sabés hacer (y es a propósito)

Con este módulo podés leer un símbolo y decir si cada parte está en su lugar, y escribir uno de cada tipo. Todavía no sabés:
- por qué casi todas las oraciones mencionan otros símbolos y qué pasa cuando no lo hacen (módulo 2);
- qué hacer cuando dos palabras significan lo mismo o una palabra significa dos cosas (módulo 2);
- de dónde sacás las palabras y cómo decidís cuáles entran (módulo 3);
- cómo revisar un LEL ajeno y entregar la lista de errores que pide la cátedra (módulo 4).

---

## Checkpoint del módulo 1

Respondé sin mirar el texto. Sin respuestas acá: van al complemento.

1. ¿Por qué se construye el LEL *antes* de entender el problema del cliente? Explicalo con el ejemplo de la aseguradora.
2. ¿Qué diferencia a un LEL de un glosario común?
3. Un compañero escribió el símbolo `Cuota` así: *Noción: "El cliente la paga al cajero cada mes." Impacto: "Es una parte del plan de cuotas."* ¿Qué está al revés y por qué?
4. Clasificá estas palabras de un gimnasio en los cuatro tipos y justificá una de cada tipo: socio, clase, inscribirse, completa, profesor, lista de espera, avisar ausencia, plan.
5. Escribí el símbolo `Cajero` de la tienda, con noción e impacto, siguiendo la plantilla de sujeto. Usá corchetes para los otros símbolos.
6. Estos nombres tienen un error de forma cada uno: `Cuotas`, `Cobrando Cuota`, `Emisión de Factura`. Corregilos y decí qué regla rompían.

## Qué viene en el módulo 2

Los dos hilos que dejamos abiertos: "Producto" sin corchetes en la noción de Cliente, y los dos símbolos llamados Cancelar. La respuesta al primero es el **principio de circularidad**, la regla que convierte una lista de definiciones en una red. La del segundo son los **homónimos**. Junto con eso, el **vocabulario mínimo** y los otros casos especiales de cualquier LEL real: sinónimos y jerarquías.

---

**FIN DEL MÓDULO 1 — Clase desde cero — LEL**
