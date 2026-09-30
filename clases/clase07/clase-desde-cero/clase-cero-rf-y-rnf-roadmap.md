# 🧭 CLASE DESDE CERO — Requerimientos Funcionales y No Funcionales — Roadmap

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Tema:** cómo se leen, se escriben y se corrigen los RF y los RNF, y cómo se conectan con los casos de uso
**Eje de todos los ejemplos:** el Centro de Entrenamiento **Vida Sana** (el gimnasio)
**Material pedagógico extra.** No reemplaza a los apuntes maestros; los prepara.

---

## Para qué existe esta clase

Hay una brecha típica en esta materia: se conocen las definiciones (qué es un RF, qué es un RNF, qué es una regla de negocio) y sin embargo, frente a un enunciado de dos páginas, no sale ni un requisito bien escrito. La definición no alcanza. Lo que falta es el **procedimiento**: leer un párrafo y saber qué sacar de ahí, con qué forma, y qué no sacar.

Esta clase enseña ese procedimiento desde cero. Si nunca escuchaste hablar de esto, perfecto: está escrita para eso. Cada término se explica antes de usarse. Y todo, absolutamente todo, se ejercita sobre el mismo negocio, para que al volver al enunciado del gimnasio cada frase te resulte reconocible.

Al terminarla tenés que poder hacer tres cosas: **(1)** clasificar cualquier frase de un enunciado o de una entrevista como RF, RNF, regla de negocio o "no es nada"; **(2)** escribir cada una con la forma que la cátedra corrige; **(3)** pasar de los RF a un diagrama de casos de uso sin inventar actores ni casos.

## Los seis módulos

| Módulo | Archivo | Qué resuelve | Densidad |
|---|---|---|---|
| **M1 — Antes de escribir** | `clase-cero-rf-y-rnf-modulo1-antes-de-escribir.md` | Qué es un sistema y dónde termina · quién es actor y quién no · las tres cosas que salen de un enunciado (RF, RNF, regla de negocio) y el test para distinguirlas | 🔴 |
| **M2 — El RF** | `clase-cero-rf-y-rnf-modulo2-el-rf.md` | Rol + verbo + objeto · presente indicativo · nivel alto y nivel detallado · las trampas de redacción · el método de 5 pasos para pasar de una frase a un RF | 🔴 |
| **M3 — El RNF** | `clase-cero-rf-y-rnf-modulo3-el-rnf.md` | Objeto + atributo + valor + unidad · el verbo "ser" y el actor que desaparece · RNF sin unidad · transversales vs. de una función · el catálogo de atributos (ISO 25010) · las palabras que suenan técnicas y no miden nada | 🔴 |
| **M4 — Cómo corrige** | `clase-cero-rf-y-rnf-modulo4-como-corrige.md` | Las seis características de calidad con su pregunta guía · cohesión · verificable ≠ completo · la lista DEO · el checklist para pasar antes de entregar | 🔴 |
| **M5 — Vida Sana párrafo por párrafo** | `clase-cero-rf-y-rnf-modulo5-vida-sana-parte1.md` y `-parte2.md` | El método aplicado al enunciado completo: de cada párrafo, qué RF, qué RNF, qué regla de negocio, y qué **no** se puede sacar | 🔴 |
| **M6 — De los RF a los casos de uso** | `clase-cero-rf-y-rnf-modulo6-de-rf-a-casos-de-uso.md` | El RF de nivel alto es el nombre del caso de uso · el RNF no genera casos de uso, restringe el escenario · la regla de negocio es precondición · el diagrama del gimnasio | 🔴 |

**Densidad:** los seis son 🔴 porque los seis son evaluables. La diferencia está en el tipo de esfuerzo: M1 a M4 son conceptos (lectura atenta, 30-45 minutos cada uno); M5 y M6 son procedimiento (leer con el enunciado al lado, más lento, y es el tramo que más rinde).

## Por qué este orden y no otro

El orden sigue **dependencias**, no el orden en que los temas aparecieron en la cursada:

```
   M1 ─── sin saber quién es actor y dónde termina el sistema,
    │      no podés decidir de quién es un requisito
    ▼
   M2 ─── el RF nombra al actor: necesita M1
    │
    ▼
   M3 ─── el RNF restringe a un RF: necesita M2
    │
    ▼
   M4 ─── corregir exige saber qué forma debía tener cada cosa: necesita M2 y M3
    │
    ▼
   M5 ─── el procedimiento completo usa todo lo anterior
    │
    ▼
   M6 ─── el diagrama sale de los RF ya escritos: necesita M5
```

No se puede saltar M1. Es corto, pero es el que evita el error número uno: escribir "el sistema debe…".

## Hilos que se abren y se cierran

Cada módulo deja a propósito una o dos preguntas sin resolver, para que sientas el problema antes de recibir la herramienta. Esta tabla te dice dónde se cierra cada una, para que no te quedes dando vueltas.

| Hilo | Se abre en | Se cierra en |
|---|---|---|
| "El sistema debe registrar…" suena perfecto. ¿Por qué está mal? | M1 §1 | M2 §2 |
| "El socio tendrá una credencial": ¿es un requisito? ¿de qué tipo? | M1 §5 | M3 §4 |
| "El registro de asistencia tiene que tardar poco." ¿Cuánto es poco? | M2 §1 | M3 §1 |
| Escribí un RF que suena bien. ¿Cómo sé si está bien? | M2 §5 | M4 §1 |
| "Registrar socio" a nivel alto: ¿eso es un caso de uso? | M2 §3 | M6 §1 |
| ¿De qué párrafo del enunciado sale cada requisito? | M1 §4 | M5 |
| La lista tiene 15 RF. ¿Cómo me doy cuenta de que falta uno? | M4 §5 | M5 parte 2 |

## Leyenda de bloques

| Marca | Qué es |
|---|---|
| 🔴 🟡 🟢 | Importancia de la sección: central y evaluable · secundaria · mencionada al pasar |
| **Para el parcial, si te preguntan** | Pregunta probable con su respuesta modelo, en formato de examen (la primera oración ya responde) |
| ⚠️ | Punto donde el material escrito de la materia y lo que se corrige no coinciden del todo. Dice qué responder en el parcial |
| 🕳️ Madriguera | Tangente que existe pero no entra en la materia. Se lee y se sigue de largo |
| ✏️ Tu turno | Ejercicio corto para hacer antes de seguir. Sin respuestas acá: las respuestas van al complemento |
| ✅ Checkpoint | Preguntas de cierre de cada módulo, sin respuestas (ídem) |
| ❌ / ✅ | Versión mal escrita / versión corregida, siempre con el porqué |

## Cómo usarlo

1. **Un módulo por sesión.** Leélo con el enunciado del gimnasio a mano; cada ejemplo sale de ahí.
2. **Hacé los "Tu turno" en el momento**, por escrito, antes de leer lo que sigue. Sin eso, el módulo se lee lindo y no queda nada.
3. **No busques las respuestas de los checkpoints en el módulo.** Si no podés responder una, anotala: es una duda para el chat, y después decanta al complemento.
4. **M5 se lee dos veces.** La primera siguiendo el razonamiento; la segunda tapando la solución de cada párrafo e intentando sacarla vos antes de destapar.
5. **Al terminar M6**, el apunte maestro y la profundización de la clase 07 (sobre otro negocio, ParkingDog) son tu prueba de fuego: mismo método, enunciado nuevo.

---

**FIN DEL ROADMAP**
