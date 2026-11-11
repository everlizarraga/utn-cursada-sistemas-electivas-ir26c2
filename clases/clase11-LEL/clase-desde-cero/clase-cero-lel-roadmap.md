# Clase desde cero — LEL — Roadmap

**Materia:** Ingeniería de Requisitos · **Cubre:** clase11 (22/10) y la parte de LEL de la clase13 (5/11) · **Serie:** `clase-cero-lel-moduloN-*.md`
**Para qué sirve este archivo:** es el plan de la serie. Te dice qué vas a aprender, en qué orden, cuánto pesa cada parte para el parcial y qué queda afuera a propósito. No es material de estudio: el estudio está en los módulos.

---

## Sobre este documento

- **Qué es el LEL, en una línea:** un diccionario del negocio del cliente, escrito de una forma especial, que se arma *antes* de entender el problema. "LEL" significa Léxico Extendido del Lenguaje. "Léxico" = vocabulario.
- **Por qué existe esta serie:** la clase real la dieron dos ex alumnos con una herramienta (Obsidian) y vos no la pudiste seguir. Acá el tema se enseña desde cero, como si nunca lo hubieras escuchado.
- **Qué asume que ya sabés (de clases anteriores de la materia):** qué es un requisito funcional y no funcional, qué es un caso de uso y qué es una entrevista. Nada más.
- **Qué viene después:** la serie **Clase desde cero — Escenarios**. Los escenarios se escriben con las palabras del LEL, por eso el LEL va primero.

**Palabras que usa este plan:**
- **Módulo:** un archivo de estudio, pensado para una sesión de 40 a 60 minutos.
- **Peso:** cuánto importa para el parcial. 🔴 central y evaluable · 🟡 secundario · 🟢 mencionado al pasar.
- **Hilo:** una pregunta que un módulo deja abierta a propósito y otro módulo responde más adelante. Sirve para que lo nuevo tenga un motivo.
- **Checkpoint:** las preguntas del final de cada módulo. Van sin respuestas para que las intentes solo; las respuestas se juntan después en el complemento.
- **Madriguera 🕳️:** una nota de 2 líneas sobre algo que existe en las lecturas pero que la profe no da ni evalúa. Se lee y se sigue de largo.

## Paso 0 — Cuánto hay que aprender, en serio

- **Conceptos nuevos de verdad:** 6. Símbolo, noción, impacto, los 4 tipos de símbolo, los 2 principios de escritura, y la lista DEO (la forma de anotar lo que está mal).
- **Lo demás son reglas de escritura:** singular, infinitivo, una idea por oración, enlazar palabras. Son muchas, pero simples. Lo difícil es aplicarlas con constancia, no entenderlas.
- **Lo que no es nuevo:** entrevistar, leer documentos, verificar vs. validar. Ya lo viste con requisitos; acá se aplica a otra cosa.
- **Dificultad real:** 4 sobre 10. La sensación de 10 vino de afuera: faltaste a la introducción, la clase la dieron con una herramienta nueva y vos estabas con otras entregas.
- **Tiempo estimado:** 4 módulos de 40 a 60 minutos de lectura cada uno, más el checkpoint. Unas 4 horas en total.

## Qué evalúa la profe (esto calibra todo)

Señales que salen de sus clases y de su PPT:

1. **Encontrar errores en un LEL ya hecho**, no armar uno de cero. La dinámica de la clase fue exactamente eso: revisar un borrador hecho por IA y anotar una lista DEO.
2. **Clasificar bien** cada símbolo (sujeto, objeto, verbo, estado) y respetar la plantilla de cada tipo. La profe llamó **error** a un objeto puesto como sujeto.
3. **Reglas de forma:** verbos en infinitivo, nombres en singular, sinónimos en una sola entrada, homónimos en entradas separadas y numeradas.
4. **Los dos principios:** circularidad y vocabulario mínimo. Un símbolo que no menciona a otros, o que nadie menciona, es **señal de alerta**: hay que revisarlo. En clase, el símbolo suelto "diagnóstico" se trató como "faltó enlazarlo".
5. **Las 5 etapas de construcción**, qué actividad es cada una (elicitar, modelar, analizar) y la diferencia entre verificar y validar: preguntas conceptuales.
6. **No suponer:** cuando una palabra puede ser del negocio o del lenguaje común (el caso "agenda"), se consulta al usuario.
7. El puente hacia escenarios: los impactos de sujetos y verbos dan origen a los escenarios.

## Los 4 módulos

| # | Módulo | Al terminarlo vas a poder… | Peso | Ejemplo trabajado |
|---|---|---|---|---|
| 1 | Qué es el LEL y cómo se escribe un símbolo | Leer un símbolo y decir si cada parte está en su lugar; escribir uno de cada tipo | 🔴 | Tienda que vende en cuotas (Cliente, Producto, Vender, En Mora) |
| 2 | La red: principios, sinónimos, homónimos y jerarquías | Decidir si dos palabras van juntas o separadas; marcar las referencias entre símbolos | 🔴 | Seguros (Productor, Cartera, Portfolio) y la tienda (Cancelar(1) y Cancelar(2)); museo (Obra de arte) |
| 3 | Cómo se construye un LEL | Explicar las 5 etapas; elegir qué palabras entran y cuáles no; describirlas con las reglas | 🟡 | Centro de entrenamiento Vida Sana (armar 8 símbolos desde el enunciado) |
| 4 | Verificar y validar: encontrar los errores de un LEL | Usar Obsidian; revisar un LEL ajeno y entregar una lista DEO como la pide la profe | 🔴 | Taller resuelto: el borrador de IA de la veterinaria, error por error |

## Detalle de cada módulo

### Módulo 1 — Qué es el LEL y cómo se escribe un símbolo 🔴

**Cubre**
- El problema que resuelve: la misma palabra significa cosas distintas en cada negocio. Primero el vocabulario, después el problema.
- Universo del Discurso: el negocio, su gente y sus documentos. (Es un nombre raro para algo simple: "el mundo del cliente".)
- El símbolo y sus tres partes: nombre, noción (qué es) e impacto (cómo actúa).
- Los 4 tipos: sujeto, objeto, verbo, estado. Qué va en la noción y en el impacto de cada uno (la plantilla).
- Reglas de forma: nombre en singular, verbo en infinitivo, oraciones cortas con un solo verbo.

**No cubre:** cómo se enlazan los símbolos entre sí (módulo 2) ni cómo se descubren (módulo 3).

**Ejemplo trabajado:** la tienda que vende en cuotas. Se escriben cuatro símbolos completos, uno de cada tipo, explicando cada oración.

**Hilos que abre:** (a) en el ejemplo, un símbolo menciona "Producto" como texto común, sin marcar; ¿importa? (b) aparecen dos símbolos llamados "Cancelar": ¿es un error?

**Checkpoint:** 6 preguntas.

### Módulo 2 — La red: principios, sinónimos, homónimos y jerarquías 🔴

**Cubre**
- Principio de circularidad: describir un símbolo usando otros símbolos. Todo símbolo menciona a otros y es mencionado por otros.
- Principio de vocabulario mínimo: usar lo menos posible palabras ajenas al negocio.
- Cómo se marca una referencia: subrayado en papel, `[[doble corchete]]` en Obsidian. Con eso el LEL se vuelve un hipertexto: un texto donde cada palabra marcada lleva a otra entrada.
- Sinónimos: dos nombres, un significado; una sola entrada, con el más usado primero. Sinónimos parciales: uno reemplaza al otro solo en algunos usos; cuidado.
- Homónimos: un nombre, dos significados; una entrada por significado, numeradas, y la noción dice en qué área se usa cada una.
- Jerarquías: varios símbolos que son "tipos de" otro. Hay jerarquía solo si el género también es símbolo del LEL, y la noción de cada tipo empieza con el género ("Es una obra de arte…").
- Un sujeto también puede aparecer como objeto (el alumno se inscribe, pero también es registrado).

**No cubre:** la mecánica de Obsidian (módulo 4), el proceso de construcción (módulo 3) ni la lista de defectos (módulo 4).

**Ejemplo trabajado:** seguros (Cartera / Portfolio como sinónimos; Cartera(1) y Cartera(2) como homónimos) y la tienda (Cancelar(1) anular compra, Cancelar(2) saldar deuda). Museo para la jerarquía.

**Hilos que cierra:** los dos del módulo 1. **Abre:** "¿cómo sé si mi LEL está bien hecho?"

**Checkpoint:** 6 preguntas.

### Módulo 3 — Cómo se construye un LEL 🟡

**Cubre**
- Las 5 etapas: planear, recolectar, describir, verificar, validar. Qué actividad es cada una: las dos primeras elicitan, describir modela, las dos últimas analizan. No es lineal: las últimas dos devuelven correcciones.
- De dónde sale el vocabulario: fuentes y en qué orden se priorizan. Información actual (lo que la gente usa hoy) vs. formal (manuales, políticas). Qué técnica sirve para cada etapa.
- Cómo elegir qué palabras entran: las del negocio, las repetidas, las significativas; no descartar antes de tiempo. Los símbolos **core** (si faltan es grave: paciente, diagnóstico) vs. los **grises** (agenda: puede estar o no). Regla de la profe: ante la duda, no supongas, consultá al usuario. La nube de palabras: lo más mencionado es lo que hay que mirar.
- Cómo describir: al menos una oración en noción y una en impacto; el "qué" y no el "cómo".
- La Ficha de Información Anticipada: dónde va lo que no es vocabulario (necesidades, problemas, el "cómo" actual).

**No cubre:** cómo se corrige lo que salió mal (módulo 4).

**Ejemplo trabajado:** Vida Sana. Desde el enunciado del centro de entrenamiento, se arman 8 símbolos siguiendo las etapas, marcando cuáles son core y cuáles grises. Sirve directo para el TP integrador.

**Hilos que abre:** el LEL de Vida Sana queda sin revisar a propósito. Se revisa en el módulo 4.

**Checkpoint:** 5 preguntas.

### Módulo 4 — Verificar y validar: encontrar los errores de un LEL 🔴

**Cubre**
- Verificar (¿está bien construido?) vs. validar (¿es el vocabulario real del cliente?). Quién hace cada una y cómo.
- La lista DEO. La **D es "discrepancia" o "defecto"**, la profe usa las dos. Su criterio en clase, que es el del parcial: un tipo mal asignado es un **error**; una referencia sin marcar es un **defecto**; dos definiciones que se contradicen dentro del LEL son una **discrepancia**; algo que falta es una **omisión**. Cómo se redacta cada entrada: símbolo, qué está mal, corrección.
- Los 4 grupos de defectos (descripción, clasificación, identificación, referencia) y la **señal** que delata cada uno.
- Una lista de control de 6 puntos para revisar cualquier LEL.
- **Obsidian, lo justo para el parcial y el TP:** crear la bóveda, importar una carpeta, una nota por símbolo, carpetas por tipo, propiedades (tipo, sinónimos), el enlace con alias `[[Producto|productos]]` (que es lo que permite nombres en singular con oraciones legibles), el panel de "menciones sin enlazar", la vista de grafo con colores por tipo y qué significa un nodo suelto.

**Ejemplo trabajado (el corazón del módulo):** el borrador de IA de la veterinaria, el mismo de la clase. Se revisan los 12 símbolos uno por uno: los 7 hallazgos que salieron en clase (propietario / dueño como sinónimo, veterinario sin definir, consulta como sujeto, prescribir tratamiento faltante, diagnóstico faltante y después suelto, "solicitando" en vez de solicitar, agenda como caso gris), con el debate D o E de "consulta" como ejemplo central, y los que nadie mencionó. Cada uno clasificado, con su tipo de defecto y su corrección. Después, revisión corta del LEL de Vida Sana del módulo 3.

**Hilos que cierra:** todos los anteriores.

**Puente a la serie siguiente:** los impactos de los sujetos y verbos del LEL son el punto de partida de los escenarios.

**Checkpoint:** 8 preguntas.

## Mapa de hilos que se cierran

| Hilo | Se abre en | Se cierra en |
|---|---|---|
| "Producto" mencionado sin marcar | M1 | M2 (circularidad) y M4 (menciones sin enlazar) |
| Dos símbolos "Cancelar" | M1 | M2 (homónimos) |
| ¿Cómo sé si mi LEL está bien? | M2 | M4 (verificación) |
| LEL de Vida Sana sin revisar | M3 | M4 (taller) |
| ¿Para qué sirve el LEL después? | M4 | Serie Escenarios, M1 |

## Lo que queda afuera a propósito (madrigueras)

Están en las lecturas del aula, pero la profe no las dio ni las evalúa. Aparecen en los módulos como 🕳️ de 2 líneas:
- Los diagramas de proceso de la tesis (SADT).
- Los 14 formularios de inspección de Kaplan.
- Las subplantillas del texto de la UNLP (personas, sectores, formularios, índices).
- Las versiones del proceso con 6 etapas: la profe usa 5.

## Cómo usar la serie

1. Un módulo por sesión. Leé, hacé el checkpoint sin mirar el material, anotá lo que no te cierre.
2. Las dudas van al chat; después se juntan en el complemento con las respuestas de los checkpoints.
3. **Calendario:** módulos 1 y 2 el 5 y 6/11; módulos 3 y 4 el 7 y 8/11. El módulo 4 se genera después de la clase del jueves 5/11, que es de verificación de LEL y escenarios, para incorporar lo que la profe corrija ahí. **Grabá esa clase.**

## Insumos de la serie (para la generación)

PPT "LEL 2026" de la cátedra (manda sobre el resto) · PPT y capturas de la clase 11 (tienda en cuotas, seguros) · transcripción de la clase 11 (correcciones de la profe) · transcripción de la clase 13 (cuando esté) · Hadad cap. 4 · Kaplan, inspección del LEL · texto UNLP cap. 3 · bóveda de la veterinaria · enunciado de Vida Sana · consigna "LEL del LEL".

---

**FIN DEL ROADMAP — Clase desde cero — LEL**
