# Lectura en español — Cap. 9 · Parte 1: Qué son las metas y qué papel juegan

> **Origen.** Capítulo 9, secciones 9.1 a 9.2.2, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Colette Rolland y Camille Salinesi**, Universidad de París 1 Panthéon-Sorbonne.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.

---

## Qué esperar de este capítulo

Es el más largo del libro y el más teórico. Va en tres partes:

1. **Esta**: qué es una meta, en qué se diferencia de un requisito, y los seis papeles que juega en el proceso.
2. **La segunda**: cómo se modelan (taxonomías, grafos Y/O, enlaces con escenarios y agentes), cómo se formulan y cómo se razona con ellas — más las cinco debilidades reconocidas del enfoque.
3. **La tercera**: los mapas meta/estrategia, una propuesta propia de los autores.

**Lo que más te sirve está en esta parte y en la segunda.** En particular: la distinción precisa entre **meta, requisito y suposición**, y —en la Parte 2— **la comparación entre metas y escenarios**, que se cruza con el tema "CU vs. Escenario" que tu cronograma tiene para la clase 11.

---

## 1. La cita fundacional 🔴

El capítulo arranca con una definición de 1977, de Ross y Schoman, que ordena todo el campo:

> **La definición de requisitos debe decir POR QUÉ hace falta un sistema, basándose en las condiciones actuales y previstas** —que pueden ser operaciones internas o el mercado externo. **Debe decir QUÉ funcionalidades del sistema van a servir y satisfacer ese contexto. Y debe decir CÓMO ha de construirse el sistema.**

```
   ¿POR QUÉ hace falta?  ────► las METAS
   ¿QUÉ va a servir?     ────► los REQUISITOS
   ¿CÓMO se construye?   ────► el DISEÑO
```

El flujo típico que describen: **se analiza el sistema actual · se señalan problemas y se identifican oportunidades · se elicitan metas estratégicas de alto nivel y se las refina · se elaboran requisitos para cumplirlas.**

> **Las metas son, así, la fuerza motriz del proceso de ingeniería de requisitos.**

### Los números, otra vez 🟡

El capítulo repite la evidencia que ya viste en el capítulo 1, y agrega un dato más reciente:

- Una encuesta de **800 proyectos en 350 empresas estadounidenses**: un tercio nunca se completó y la mitad tuvo éxito solo parcial. **Los requisitos deficientes se identificaron como la fuente principal de problemas.**
- **3.800 organizaciones en 17 países europeos**: la mayoría de los problemas percibidos se relacionan con **especificación** (>50 %) y **gestión** de requisitos (50 %).
- **Y el más pesimista, de 2003:** atribuye **entre el 60 y el 70 % de los fracasos de sistemas a una captura, validación y gestión de requisitos deficientes.**

**La conclusión que sacan:**

> Si queremos que se produzcan sistemas de mejor calidad —sistemas que cumplan los requisitos de sus usuarios— **la IR necesita explorar los objetivos de los distintos interesados y las actividades que llevan a cabo para cumplirlos**, con el fin de derivar requisitos con propósito.

---

## 2. Los tres mundos 🟡

El marco conceptual del capítulo distingue **tres mundos** y las relaciones entre ellos.

| Mundo | Qué contiene |
|---|---|
| **Mundo del uso** | **Las tareas, procedimientos e interacciones realizadas por los agentes**, y cómo se usan los sistemas para hacer el trabajo. Contiene **los objetivos que hay que cumplir en la organización** y que se logran mediante las actividades de los agentes |
| **Mundo del asunto** (*subject world*) | **El conocimiento del dominio del mundo real sobre el cual el sistema propuesto tiene que proveer información** |
| **Mundo del sistema** | **El mundo de las especificaciones del sistema**, donde hay que atender los requisitos que surgen de los otros dos |

**Los requisitos surgen de los dos primeros, pero de manera distinta:**

```
   MUNDO DEL ASUNTO ──── relación de ────► MUNDO DEL SISTEMA
                        REPRESENTACIÓN
   impone REQUISITOS DE DOMINIO:
   hechos de la naturaleza que
   reflejan leyes del dominio

   MUNDO DEL USO ─────── relación ───────► MUNDO DEL SISTEMA
                        INTENCIONAL
   genera REQUISITOS DEFINIDOS POR EL USUARIO:
   surgen de la gente de la organización y
   reflejan sus metas, intenciones y deseos
```

**Por qué importa la relación intencional:**

> **Entender la relación intencional es esencial para comprender la razón por la cual debería construirse un sistema. El mundo del uso provee la justificación para construir un sistema.**
>
> **El propósito de desarrollar un sistema se encuentra fuera del sistema mismo** — en la empresa, o dicho de otro modo, **en el contexto en el que el sistema va a funcionar.**

> ⚠️ **Cruce con la cátedra.** Esa idea —que la razón de ser del sistema está fuera del sistema— es la misma que aparecía en el capítulo 2 como argumento a favor de la elicitación basada en metas, y en el capítulo 5 como criterio para detectar requisitos huérfanos. **Si un requisito no se puede colgar de algo del mundo del uso, no tiene justificación.**

---

## 3. Qué es una meta 🔴

### La definición

> **Una meta corresponde a un objetivo que el sistema debería lograr mediante la cooperación de agentes, tanto del software a construir como del entorno.**

Las metas refieren a **propiedades pretendidas u optativas** del sistema previsto o de su entorno.

### Prescriptivo contra descriptivo 🔴

Y acá viene una distinción precisa que vale la pena:

> **Las metas son expresiones de intención, y por lo tanto declarativas y de naturaleza PRESCRIPTIVA** — por oposición a los **enunciados DESCRIPTIVOS**, que describen hechos reales.

```
   "Transportar pasajeros rápido"
        → es una META (prescriptiva: dice cómo debe ser)

   "Si las puertas están cerradas, no están abiertas"
        → es un ENUNCIADO DESCRIPTIVO (dice cómo es)
```

### Los niveles de abstracción

Las metas pueden formularse **a distintos niveles**:

```
   ALTO NIVEL ──► resultados estratégicos que la empresa
                  quiere lograr
                  ej.: "Transportar pasajeros con seguridad"
        │
        ▼
   BAJO NIVEL ──► preocupaciones técnicas sobre situaciones
                  precisas que un componente debería ayudar
                  a alcanzar
                  ej.: "Mantener las puertas cerradas
                        mientras se está en movimiento"
```

### Metas funcionales y de calidad 🔴

Las metas cubren **tipos distintos de preocupación**:

| | Definición | Ejemplo |
|---|---|---|
| **Metas funcionales** | Refieren a **los servicios que va a proveer el sistema o su entorno** | *Proveer efectivo* |
| **Metas de calidad** (también llamadas no funcionales) | Refieren a **las cualidades del comportamiento del sistema en su entorno** | *Atender al cliente rápidamente* |

---

## 4. Meta, requisito y suposición 🔴🔴

Esta es la sección más aprovechable de la parte, y es corta. El capítulo distingue **tres cosas** que se confunden todo el tiempo.

### Meta vs. requisito

> **A diferencia de los requisitos, las metas se logran usualmente mediante la cooperación de múltiples agentes.**

El ejemplo: la meta *Transportar pasajeros con seguridad* **requiere la cooperación de múltiples agentes** — el sistema de transporte ferroviario, el sistema de software, el sistema de seguimiento **y los propios pasajeros**.

Y de ahí sale la definición precisa:

> **Una meta bajo la responsabilidad de un único agente del software se convierte en un requisito.**

```
   META ─────────► la cumplen VARIOS agentes cooperando
                   (incluyendo personas y el entorno)

   REQUISITO ────► la cumple UN SOLO agente DEL SOFTWARE
```

**Y de ahí se desprende una decisión central del proceso:**

> **Una decisión importante del proceso de IR es, por lo tanto, decidir QUÉ METAS SE VAN A AUTOMATIZAR Y CUÁLES NO.**

### Requisito vs. suposición 🔴

Y acá está el punto más filoso:

> Mientras que **las situaciones reales del entorno del sistema** —leyes físicas, regulaciones, normas y comportamientos— **no están usualmente controladas por el sistema**, sí **es posible controlar la satisfacción de los requisitos implementándolos en el sistema.**

El ejemplo, que es perfecto:

```
   "Mantener las puertas cerradas mientras se está
    en movimiento"
        → es una meta que LLEVA A UN REQUISITO,
          porque el sistema puede asegurar su satisfacción

   "Subir cuando las puertas se abren"
        → es una SUPOSICIÓN sobre agentes que están
          FUERA del control del sistema
        → un enunciado así NO PUEDE USARSE COMO REQUISITO
```

> ⚠️ **Cruce con la cátedra — usá esto como criterio de revisión.** Este par de conceptos te da **un test para depurar una lista de requisitos**:
>
> **Preguntá quién es responsable de que se cumpla cada enunciado.** Si la respuesta es "el software", es un requisito. Si la respuesta es "varios actores cooperando", es una meta que todavía hay que descomponer. **Si la respuesta es "el usuario, y el sistema no puede hacer nada al respecto", no es un requisito** — es una suposición, y hay que registrarla como tal.
>
> Es un error muy común en los TP escribir cosas como "el usuario debe ingresar los datos correctamente" y llamarlas requisito. **El sistema no puede garantizar eso.** Lo que sí puede es *validar* los datos — y ese sí es un requisito.
>
> Conecta también con el capítulo 8: un enunciado que el sistema no controla **no es verificable contra el sistema**, y la verificabilidad es uno de los diez atributos de calidad.

---

## 5. Los seis papeles de las metas 🔴

Como fuerza motriz del proceso de IR, las metas cumplen varios papeles. Esta lista es un buen resumen de por qué el enfoque existe.

### 5.1 Elicitación de requisitos 🔴

> **El modelado de metas demostró ser una manera efectiva de elicitar requisitos.** El argumento a favor: **la justificación para desarrollar un sistema debe encontrarse fuera del sistema mismo, en la empresa en la que el sistema va a funcionar.**

### 5.2 Exploración de alternativas de diseño 🟡

La IR asume que **el sistema previsto podría funcionar e interactuar con su entorno de muchas maneras alternativas**. El **refinamiento alternativo de metas** demostró ser útil **en la exploración sistemática de las opciones del sistema**.

### 5.3 Completitud de los requisitos 🔴

Y acá aparece un criterio que vale oro:

> **La completitud de los requisitos es un tema mayor de la IR.** Yue fue probablemente el primero en argumentar que **las metas proveen un criterio de completitud**:
>
> **La especificación de requisitos es completa si los requisitos son suficientes para lograr la meta que refinan.**

> ⚠️ **Cruce con la cátedra.** Este es el criterio de completitud más usable que hay en todo el libro, porque **es local y verificable**. La completitud "absoluta" —¿están todos los requisitos?— es imposible de chequear, porque no sabés lo que no sabés. Pero **la completitud relativa a una meta sí se puede chequear**: tomás una meta, mirás los requisitos que la refinan, y preguntás *si se cumplen todos estos, ¿la meta queda cumplida?*
>
> Es un ejercicio que podés correr sobre cualquier parte de un TP.

### 5.4 Trazabilidad 🔴

> **Las metas proveen un medio para asegurar la pre-trazabilidad de los requisitos.** Establecen un **vínculo conceptual entre el sistema y su entorno**, facilitando así **la propagación de los cambios organizacionales hacia la funcionalidad del sistema**.
>
> Ese vínculo **provee la justificación de los requisitos** y **facilita la explicación y justificación de los requisitos ante los interesados.**

> Recordá del capítulo 5: la pre-trazabilidad es la que responde *¿de dónde vino este requisito?*. Las metas son la respuesta.

### 5.5 Negociación de requisitos 🟡

Los interesados proveen puntos de vista útiles y realistas sobre el sistema a construir. **Las técnicas de negociación se desarrollaron para ayudar a elegir el predominante**, y las de priorización **para comparar los distintos puntos de vista sobre la base de costos y valor**.

### 5.6 Detección y resolución de conflictos 🔴

> **Los puntos de vista múltiples están inherentemente asociados a conflictos, y se reconoce que las metas ayudan en la detección de conflictos y en su resolución.**

---

## Mapa de la Parte 1

```
   ROSS Y SCHOMAN (1977)
   por qué (metas) · qué (requisitos) · cómo (diseño)

   ─────────────────────────────────────────────

   LOS TRES MUNDOS
   del ASUNTO ──► requisitos de DOMINIO
                  (hechos, leyes)
   del USO ─────► requisitos DEFINIDOS POR EL USUARIO
                  (metas, intenciones, deseos)
   del SISTEMA ─► donde ambos deben atenderse

   la razón de ser del sistema está FUERA del sistema

   ─────────────────────────────────────────────

   QUÉ ES UNA META
   objetivo a lograr mediante la COOPERACIÓN DE AGENTES
   prescriptiva (dice cómo DEBE ser)
   ≠ enunciado descriptivo (dice cómo ES)
   funcionales (servicios) y de calidad (cualidades)

   ─────────────────────────────────────────────

   ══► LA DISTINCIÓN CLAVE ◄══

   META         varios agentes cooperando
                  │  ¿quién es responsable?
                  ▼
   REQUISITO    UN agente DEL SOFTWARE
                → el sistema puede garantizarlo

   SUPOSICIÓN   agentes FUERA del control del sistema
                → NO puede usarse como requisito

   ─────────────────────────────────────────────

   LOS 6 PAPELES
   elicitar · explorar alternativas ·
   COMPLETITUD (¿los requisitos alcanzan para
   cumplir la meta que refinan?) ·
   trazabilidad · negociación · conflictos
```

---

## Preguntas para chequear que quedó

1. ¿Qué tres cosas debe decir una definición de requisitos, según Ross y Schoman? ¿A qué corresponde cada una?
2. Nombrá los tres mundos y qué contiene cada uno.
3. Diferenciá los requisitos de dominio de los definidos por el usuario. ¿De qué mundo viene cada uno?
4. ¿Por qué se dice que el propósito de desarrollar un sistema se encuentra fuera del sistema mismo?
5. Definí "meta". ¿Por qué es prescriptiva y no descriptiva? Dé un ejemplo de cada tipo de enunciado.
6. Diferenciá metas funcionales de metas de calidad, con un ejemplo de cada una.
7. ¿Cuál es la diferencia exacta entre una meta y un requisito?
8. ¿Qué decisión importante del proceso se desprende de esa diferencia?
9. ¿Qué es una suposición y por qué no puede usarse como requisito? Dé el ejemplo de las puertas.
10. "El usuario debe ingresar los datos correctamente": ¿es meta, requisito o suposición? Justificá y proponé una reformulación.
11. ¿Cuál es el criterio de completitud que aportan las metas? ¿Por qué es más usable que una noción absoluta de completitud?
12. ¿Cómo contribuyen las metas a la pre-trazabilidad?
13. Nombrá los seis papeles que juegan las metas en el proceso de IR.

---

**FIN DEL CAPÍTULO 9 — PARTE 1**

*Sigue en la Parte 2: cómo se modelan las metas (taxonomías, metas duras y blandas, grafos Y/O, enlaces con escenarios y con agentes), cómo se formulan, cómo se razona con ellas —y las cinco debilidades reconocidas del enfoque.*
