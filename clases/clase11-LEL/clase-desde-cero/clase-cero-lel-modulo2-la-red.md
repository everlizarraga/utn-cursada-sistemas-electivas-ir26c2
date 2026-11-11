# Clase desde cero — LEL — Módulo 2: La red: principios, sinónimos, homónimos y jerarquías

**Serie:** Clase desde cero — LEL (módulo 2 de 4) · **Materia:** Ingeniería de Requisitos · **Unidad:** clase11

---

## Sobre este documento

**Qué cubre:** los dos principios que rigen cómo se escribe un LEL (circularidad y vocabulario mínimo), qué es el hipertexto que resulta de aplicarlos, y los tres casos especiales que aparecen en todo LEL real: sinónimos, homónimos y jerarquías. Cierra con un caso particular: el sujeto que también aparece como objeto.

**Qué NO cubre:** cómo se construye el LEL etapa por etapa (módulo 3), la mecánica de Obsidian y la lista de errores (módulo 4).

## De dónde venís

Del módulo 1: un símbolo tiene nombre, noción e impacto; hay cuatro tipos con su plantilla; el nombre va en singular y los verbos en infinitivo. Y quedó un hilo abierto: en la noción de `Cliente`, la palabra *Producto* no tenía corchetes.

---

## 1. 🔴 Principio de circularidad

Volvé al símbolo `Cliente` del módulo 1:

> **Noción**
> - Es una persona que compra un Producto.

Y ahora pensá que sos alguien nuevo en el equipo, leyendo este LEL por primera vez. Leés "compra un Producto" y querés saber qué es un producto en esta tienda. ¿Cómo lo encontrás? Tenés que ir a buscarlo a mano por toda la lista. En una carpeta de 50 hojas, eso es lento. Y peor: **no sabés si "Producto" es una palabra del negocio o una palabra común**, porque nada lo indica.

La versión correcta es:

> **Noción**
> - Es una persona que compra un [[Producto]].

Con los corchetes (o el subrayado, en papel) pasan dos cosas: queda claro que *Producto* tiene su propia entrada, y podés saltar a ella. Eso es el **principio de circularidad**:

> **Al describir un símbolo, usá al máximo los otros símbolos del LEL, y marcá cada uno.**

Tiene dos consecuencias que se controlan por separado:

1. **Toda noción y todo impacto mencionan al menos otro símbolo.** Si una oración no menciona ninguno, sospechá: o falta marcar una palabra, o falta un símbolo en el LEL.
2. **Todo símbolo es mencionado por al menos otro símbolo.** Si nadie lo nombra, está suelto: o se te olvidó enlazarlo, o no es realmente del negocio.

Mirá cómo se encadenan tres símbolos de la aseguradora del módulo 1:

> **Productor** (sujeto) · Noción: Intermediario entre el negocio y un potencial [[Asegurado]]. · Impacto: Vende una [[Póliza]]. Atiende al [[Asegurado]].
>
> **Póliza** (objeto) · Noción: Documento que establece la cobertura del [[Asegurado]]. · Impacto: El [[Productor]] la vende.
>
> **Asegurado** (sujeto) · Noción: Persona a la que se refiere la cobertura de una [[Póliza]]. · Impacto: Recibe atención del [[Productor]].

```
   [[Productor]] ──── [[Póliza]] ──── [[Asegurado]]
         └──────────────────────────────────┘
```

Cada uno define a los otros. Por eso "circularidad": las definiciones se cierran sobre sí mismas, sin salir del vocabulario del negocio.

**Cómo se marca:** en papel, subrayando la palabra con su nombre completo. En Obsidian, con `[[dobles corchetes]]`, y con la barra para plurales y conjugaciones (`[[Producto|productos]]`), como ya viste en el módulo 1.

**El resultado:** un **hipertexto**. Un texto donde cada palabra marcada te lleva a otra entrada, y desde esa a otra, sin fin. Es la misma idea de Wikipedia: podés arrancar en un artículo y terminar en cualquier otro siguiendo enlaces. Un LEL bien hecho se navega así.

> 🎓 **Para el parcial, si te preguntan: ¿qué es el principio de circularidad?**
> Es el principio que exige maximizar el uso de símbolos del LEL en la descripción de otros símbolos. Toda noción e impacto refiere al menos a otro símbolo, todo símbolo es referido por otro, y las referencias se marcan con el nombre completo. El resultado es un hipertexto autocontenido y conectado, con menos ambigüedad.

## 2. 🔴 Principio de vocabulario mínimo

Ahora el problema inverso. Alguien quiso "enriquecer" el símbolo `Productor` y escribió:

> **Impacto**
> - Gestiona su cartera mediante un workflow omnicanal de captación y fidelización de asegurados.

¿Qué pasó? "Workflow", "omnicanal", "captación", "fidelización" no son palabras del negocio (no están en el LEL) y tampoco son palabras simples del castellano que cualquiera entiende. Son jerga de otro lado. El cliente lee eso y no se reconoce; el analista nuevo lee eso y no entiende más que antes.

La versión correcta:

> **Impacto**
> - Vende una [[Póliza]].
> - Atiende al [[Asegurado]].

(Dos oraciones, no una con "y": un verbo por oración, como en el módulo 1.) Eso es el **principio de vocabulario mínimo**:

> **Usá lo menos posible palabras ajenas al LEL. Las que uses, que sean del lenguaje común más básico.**

La idea de fondo: una oración del LEL se compone de dos clases de palabras, **símbolos** (marcados) y **palabras comunes** ("es", "una", "persona", "que", "compra"). Las palabras comunes tienen que salir de un conjunto chico de palabras que todo el mundo entiende. Si necesitás una palabra "rara" para describir un símbolo, hay dos opciones: o es del negocio y entonces **falta un símbolo**, o no es del negocio y entonces **sobra**.

🕳️ **Madriguera — las 700 palabras.** La idea original propone tomar ese conjunto chico de un diccionario básico del idioma, de unas 700 palabras. Nadie lo controla palabra por palabra; es un criterio, no una lista. *Volvé al camino.*

**Los dos principios juntos** producen una red cerrada y conectada: cada símbolo apunta a otros (circularidad) y nada apunta hacia afuera (vocabulario mínimo). De ahí sale la **señal de alerta** que más usa la cátedra: *un símbolo que no menciona a otros, o que ningún otro menciona, hay que revisarlo.* En la vista de grafo de Obsidian (el dibujo donde cada símbolo es un punto y cada enlace una línea; se ve en el módulo 4) ese símbolo aparece como un punto suelto, sin líneas.

> 🎓 **Para el parcial, si te preguntan: ¿cuáles son los dos principios del LEL?**
> Circularidad: maximizar el uso de símbolos del LEL al describir otros símbolos. Vocabulario mínimo: minimizar los términos externos al léxico, tomándolos de un subconjunto pequeño del lenguaje común. Juntos hacen del LEL un hipertexto cerrado y reducen la ambigüedad.

## 3. 🔴 Sinónimos: dos nombres, un significado

En la tienda, algunos empleados dicen "cliente" y otros dicen "comprador". Se refieren exactamente a lo mismo: misma noción, mismo impacto. ¿Dos símbolos? **No. Uno solo, con dos nombres:**

> ### Cliente / Comprador
> *Tipo: Sujeto*
> *(noción e impacto, los del módulo 1)*

Regla: **los sinónimos comparten una única entrada**, con el nombre más usado primero. En Obsidian, el segundo nombre se carga como "alias" (nombre alternativo) en la cabecera de la nota, y cualquiera de los dos nombres lleva a la misma nota. La mecánica se ve en el módulo 4.

Otro ejemplo, de la aseguradora: **Cartera / Portfolio**. Dos palabras, una en castellano y otra en inglés, mismo significado: conjunto de pólizas vigentes asignadas a un productor.

**Cómo se descubren:** casi siempre al validar con el cliente. Un caso real de un banco de sangre: los analistas tenían como símbolos dos laboratorios distintos, y recién al leerle el LEL al usuario descubrieron que cuando el personal dice "inmuno" se refiere a uno solo de ellos. "Inmuno" pasó a ser sinónimo de ese laboratorio. Por eso la validación es la etapa donde más sinónimos aparecen (módulo 3).

**Cuidado con los sinónimos parciales.** Dos palabras son sinónimos parciales cuando una reemplaza a la otra *solo en algunos usos*. Imaginate un gimnasio donde la gente dice "me anoto en el turno de las 9" y también "me anoto en la clase de las 9". Parecen sinónimos. Pero si en ese mismo gimnasio "turno" también se usa para la franja horaria de la sala de aparatos, donde no hay clase, entonces **no son sinónimos**: son dos símbolos distintos, `Turno` y `Clase`, que a veces coinciden. Si los unís en una entrada, perdés un concepto. Si dudás, es señal de que hay que preguntarle al usuario (y a veces, de que falta un tercer símbolo).

## 4. 🔴 Homónimos: un nombre, dos significados

El caso opuesto. En la tienda, "cancelar" se usa para dos cosas que no tienen nada que ver:

> ### Cancelar(1)
> *Tipo: Verbo · Sinónimo: Anular Compra*
>
> **Noción**
> - Lo pide el [[Cliente]] y lo realiza el [[Vendedor]].
> - Se usa en el salón de ventas, antes de la entrega del [[Producto]].
>
> **Impacto**
> - Se anula la [[Factura]].
> - El [[Producto]] vuelve a la tienda.
> - No se genera [[Deuda]].

> ### Cancelar(2)
> *Tipo: Verbo · Sinónimo: Saldar Deuda*
>
> **Noción**
> - Lo realiza el [[Cliente]] con el [[Cajero]] en la caja de la tienda.
> - Ocurre al pagar la última [[Cuota]], en tiempo o por adelantado.
>
> **Impacto**
> - La [[Deuda]] queda en cero.
> - El [[Cliente]] deja de estar [[En Mora]].

Fijate las tres reglas aplicadas:

1. **Una entrada por significado**, no una entrada con dos nociones.
2. **Un índice numérico** en el nombre: Cancelar(1), Cancelar(2). Así, cuando otro símbolo lo menciona, no hay duda de cuál es.
3. **La noción dice en qué contexto se usa** ese significado: "en el salón de ventas, antes de la entrega" vs. "en la caja, al pagar la última cuota".

Y un detalle: cada homónimo puede tener a su vez sinónimos. Cancelar(1) es también "anular compra"; Cancelar(2) es también "saldar deuda".

Otro ejemplo, de la aseguradora: **Cartera(1)**, en el área comercial, es el conjunto de pólizas de un productor. **Cartera(2)**, en el área de finanzas, es el conjunto de inversiones de la aseguradora. Misma palabra, dos áreas, dos entradas.

> 🎓 **Para el parcial, si te preguntan: ¿cómo se tratan los sinónimos y los homónimos en el LEL?**
> Los sinónimos (varios nombres, un significado) comparten una única entrada, con el nombre más usado primero. Los homónimos (un nombre, varios significados) se separan en una entrada por significado, con un índice numérico en el nombre y el contexto de uso indicado en la noción.

## 5. 🔴 Jerarquías: símbolos que son "tipos de" otro símbolo

En un museo, el vocabulario tiene `Obra de arte`, `Cuadro` y `Escultura`. Un cuadro *es una* obra de arte; una escultura *es una* obra de arte. Eso es una **jerarquía**: un símbolo género (obra de arte) con sus subtipos (cuadro, escultura).

```
        ┌──────────────┐
        │ OBRA DE ARTE │   ← género
        └──────────────┘
           ↑        ↑
     ┌─────────┐ ┌───────────┐
     │ CUADRO  │ │ ESCULTURA │   ← subtipos
     └─────────┘ └───────────┘
```

Dos reglas:

1. **Hay jerarquía si y solo si el género es un símbolo del LEL.** Si en el museo nadie dice "obra de arte" con un sentido propio, no hay jerarquía, aunque vos sepas que cuadro y escultura son obras de arte.
2. **La noción de cada subtipo empieza con el género:** "Es una [[Obra de arte]] que…". Así la relación queda escrita, no solo dibujada.

¿Para qué detectarlas? Para reducir la ambigüedad (lo que vale para toda obra de arte vale para el cuadro) y para **descubrir símbolos que faltan**: si tenés `Cuadro` y `Escultura` y el personal habla de "las obras", te falta el género. O al revés: si tenés el género y aparecen dos subtipos, preguntate si hay un tercero.

**Un truco para encontrarlas:** mirá los nombres compuestos por un **núcleo** y un **modificador**. En un gimnasio: `Carpeta de clases`, `Carpeta de fichas de socios`, `Carpeta de caja`. El núcleo es "carpeta". ¿Existe `Carpeta` sola como símbolo? Si el personal dice "fijate en la carpeta" y se entiende cuál, tal vez sí, y hay jerarquía. Si no, son tres símbolos independientes que comparten una palabra común. La decisión siempre la da el uso real, no la lógica.

Contraejemplo en la tienda: `Vendedor`, `Cajero` y `Analista de Crédito` son todos empleados. ¿Jerarquía con género `Empleado`? Solo si "empleado" es una palabra con significado propio en esa tienda. Si nadie la usa, no se inventa.

🕳️ **Madriguera — hiperonimia.** En lingüística, la relación "es un" se llama hiperonimia, y la inversa, hiponimia. La cátedra dice "jerarquía" y "género / subtipo". *Volvé al camino.*

## 6. 🟡 Un sujeto que también es objeto

Un caso que confunde: el `Alumno` de una facultad. Se inscribe a una materia: hace algo, es sujeto. Pero también *es registrado* por Secretaría, *es incluido* en un curso, *tiene* un legajo: le hacen cosas, como a un objeto. ¿Qué es?

**Es un sujeto.** Y las cosas que le hacen van en su impacto, en voz pasiva: "Es registrado por [[Secretaría]]". Un sujeto no deja de serlo porque reciba acciones; la plantilla de sujeto dice "actividades que ejecuta **o recibe**". Lo que no se hace es duplicarlo como objeto.

El caso de verdad distinto es cuando el negocio tiene *un registro* del sujeto con nombre propio: `Legajo del Cliente`, `Ficha del Socio`. Eso sí es un objeto aparte, porque es una cosa (un papel, un archivo) con su propia vida: se crea, se consulta, se archiva.

Resumiendo: `Socio` es sujeto aunque lo registren; `Ficha del Socio` es objeto; y no hace falta un tercer símbolo.

> ⚠️ **Nota de cátedra.** En la materia se habla de un "doble rol": un sujeto que en algún rol aparece como objeto (el alumno que se inscribe y que a la vez es registrado). Si te lo preguntan en el parcial, respondé que **sí puede pasar**, y explicalo así: las acciones que el sujeto recibe van en su impacto, y el registro con nombre propio (legajo, ficha) es un objeto aparte.

## 7. Qué quedó cerrado y qué sigue abierto

**Cerrado:** el hilo de "Producto" sin corchetes (era una falta de circularidad; se corrige marcando). El hilo de "dos símbolos Cancelar" (son homónimos, correctamente separados con índice).

**Abierto:** ya sabés cómo tiene que verse un LEL bien hecho. Pero si te dan uno hecho por otro, ¿cómo lo revisás de forma sistemática? ¿Cómo anotás lo que está mal para que la cátedra lo acepte? Eso es el módulo 4. Antes, en el módulo 3, cómo se construye uno desde el negocio.

---

## Checkpoint del módulo 2

Respondé sin mirar el texto. Sin respuestas acá: van al complemento.

1. ¿Qué dos consecuencias controlables tiene el principio de circularidad? Da un ejemplo de cada una con la tienda.
2. Reescribí esta oración para que cumpla el vocabulario mínimo: "El Cajero efectúa la percepción del importe correspondiente a la cuota mediante los canales de cobranza habilitados."
3. En un gimnasio, "socio" y "alumno" se usan indistintamente para la misma persona, con las mismas acciones. ¿Cómo lo escribís en el LEL? ¿Y si "alumno" solo se usara para los que están en una clase con profesor, y "socio" para todos?
4. En una clínica, "consulta" significa a veces la visita del paciente al médico y a veces la pregunta que hace un paciente por teléfono. ¿Cómo lo escribís? Da los nombres y una noción de cada uno.
5. Tenés los símbolos `Clase de pilates`, `Clase de yoga` y `Clase de funcional`. ¿Qué tenés que averiguar antes de decidir si hay una jerarquía? ¿Y cómo empezaría la noción de `Clase de pilates` si la hubiera?
6. El `Profesor` del gimnasio "es contratado por la Junta Directiva" y "es evaluado por los socios". ¿Eso lo convierte en objeto? ¿Dónde van esas oraciones?

## Qué viene en el módulo 3

Hasta acá, cómo se ve un LEL terminado. El módulo 3 es cómo se llega ahí: las cinco etapas de construcción, de dónde salen las palabras, cómo decidir cuáles entran y cómo escribir las descripciones con las reglas. El ejemplo es Vida Sana, el centro de entrenamiento del TP integrador.

---

**FIN DEL MÓDULO 2 — Clase desde cero — LEL**
