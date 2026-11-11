# Clase desde cero — LEL — Módulo 3: Cómo se construye un LEL

**Serie:** Clase desde cero — LEL (módulo 3 de 4) · **Materia:** Ingeniería de Requisitos · **Unidad:** clase11

---

## Sobre este documento

**Qué cubre:** las cinco etapas para construir un LEL, de dónde sale el vocabulario y en qué orden se consulta, cómo decidir qué palabras entran, las reglas para describirlas, y dónde va lo que no es vocabulario. Todo aplicado a Vida Sana, el centro de entrenamiento del TP integrador: al final del módulo hay un LEL inicial de nueve símbolos armado desde el enunciado.

**Qué NO cubre:** cómo se revisa ese LEL para encontrar lo que está mal. Las dos últimas etapas (verificar y validar) se nombran acá y se desarrollan en el módulo 4.

**Peso:** este módulo es 🟡 en conjunto. La cátedra lo evalúa con preguntas conceptuales (las etapas, las fuentes, qué va a la ficha), no con un ejercicio. El ejemplo de Vida Sana es 🔴 por otro motivo: es tu TP integrador.

## De dónde venís

Del módulo 1: el símbolo y sus tipos. Del módulo 2: los dos principios, sinónimos, homónimos y jerarquías. De la clase03 de la materia: las técnicas de elicitación (entrevistas estructuradas y no estructuradas, observación, lectura de documentos). Acá se dice cuál sirve para qué etapa.

---

## 1. 🔴 Las cinco etapas

Construir un LEL es un proceso con cinco etapas. Cada etapa corresponde a una de las actividades generales de la ingeniería de requisitos que ya conocés: elicitar (descubrir), modelar (representar) y analizar (controlar).

| # | Etapa | Qué se hace | Actividad de IR |
|---|---|---|---|
| 1 | **Planear** | Identificar y priorizar las fuentes de información; elegir las técnicas de elicitación | Elicitar |
| 2 | **Recolectar** | Identificar los símbolos, organizarlos en una lista y clasificarlos por tipo | Elicitar + Modelar |
| 3 | **Describir** | Escribir la noción y el impacto de cada símbolo según su plantilla | Modelar |
| 4 | **Verificar** | Detectar defectos de construcción con heurísticas (reglas prácticas) e inspección (revisión sistemática hecha por los analistas con una lista de control) | Analizar |
| 5 | **Validar** | Confirmar el vocabulario con los usuarios | Analizar |

**No es lineal.** Verificar y validar producen una **lista de DEOs** (discrepancias o defectos, errores y omisiones: la lista de lo que está mal, que se explica en el módulo 4) que vuelve a Recolectar y a Describir para corregir. Y el LEL sigue cambiando durante todo el proyecto, a medida que se entiende más el negocio.

```
 Planear → Recolectar → Describir → Verificar → Validar
               ↑            ↑           │          │
               └────────────┴───────────┴──────────┘
                        lista de DEOs
```

> ⚠️ **Nota de cátedra.** Algunos textos describen el proceso con seis etapas (separan "clasificar" o agregan "control"). En la materia son **cinco**, con la clasificación dentro de Recolectar. Para el parcial, cinco.

> 🎓 **Para el parcial, si te preguntan: ¿cuáles son las etapas de construcción del LEL?**
> Planear (identificar y priorizar fuentes, elegir técnicas), Recolectar (identificar, listar y clasificar símbolos), Describir (escribir noción e impacto según la plantilla), Verificar (detectar defectos con heurísticas e inspección) y Validar (confirmar con los usuarios). Las dos últimas generan listas de DEOs que realimentan las anteriores: el proceso no es lineal.

🕳️ **Madriguera — SADT.** Las lecturas del aula muestran estas etapas como diagramas SADT, con cajas y flechas de entradas, controles y salidas. Es una notación de procesos; la cátedra no la pide. *Volvé al camino.*

## 2. 🟡 Planear: de dónde sale el vocabulario

**Las fuentes**, en orden de prioridad:

1. **Los que piden el software.** En Vida Sana, la Junta Directiva (los dueños).
2. **Las personas impactadas:** los que van a usarlo o a cambiar su forma de trabajar. Los profesores y los socios.
3. **Los documentos del negocio.** Las carpetas de fichas, de clases y de caja; la ficha que lleva cada socio.

Una distinción que la cátedra pregunta: la información puede ser **actual** o **formal**.
- **Actual:** lo que la gente hace y dice hoy. Sale de los usuarios, de los formularios que usan, del software que tienen.
- **Formal:** lo que dicen los manuales, las políticas, el reglamento. A veces coincide con lo actual y a veces no (el reglamento dice una cosa y la gente hace otra).

El LEL registra las dos, pero conviene saber cuál es cuál: un requisito basado en lo formal puede chocar con la realidad.

**Las técnicas**, según la etapa:
- Para **recolectar**: entrevistas no estructuradas (dejar hablar al usuario, que use su vocabulario) y lectura de documentos.
- Para **describir**: entrevistas estructuradas (preguntar por un símbolo puntual: "¿qué es exactamente la ficha del socio?").
- La **observación** sirve para ver cómo se trabaja, pero captura poco vocabulario: la gente no habla mientras hace.

En Vida Sana ya hiciste parte de esto: la entrevista del TP integrador y el cuestionario a los socios son las fuentes de donde sale el LEL.

## 3. 🔴 Recolectar: qué palabras entran

Tenés el enunciado, las entrevistas, los documentos. ¿Qué palabras son símbolos y cuáles no? Cuatro criterios:

1. **Son del negocio.** Palabras o frases propias del dominio, o comunes pero usadas con otro sentido.
2. **Se repiten.** Las que el usuario dice todo el tiempo o aparecen mucho en los documentos. Pensá en una nube de palabras: las más grandes son las que hay que mirar primero.
3. **Son significativas.** Se excluye lo obvio del lenguaje común: "hora", "mes", "día" no son símbolos (salvo que en ese negocio signifiquen algo especial).
4. **No se descarta antes de tiempo.** Ante la duda, entra como candidato. Es más barato sacar después que descubrir tarde que faltaba.

Con esos criterios aparecen tres clases de palabras:

| Clase | Qué son | Qué hacés | Ejemplo en Vida Sana |
|---|---|---|---|
| **Core** | Sin ellas el negocio no se entiende. Si faltan, es grave | Entran sí o sí | socio, clase, plan, cupo, lista de espera |
| **Grises** | Pueden ser del negocio o del lenguaje común, o no se sabe si entran en el alcance; no se nota a simple vista | **No supongas: preguntale al usuario.** Si lo incluís y después no hacía falta, no pasa nada | sector, seña, bono, código de socio |
| **Comunes** | Lenguaje de todos los días, sin sentido especial | No entran | hora, mes, sábado, resaltador |

La regla "no supongas" es de la cátedra y vale para todo el tema: lo que parece obvio para vos puede significar otra cosa para el cliente. La agenda de una veterinaria puede ser "la agenda" de cualquiera, o puede ser *el* objeto central donde se asignan los turnos. Solo el usuario lo sabe.

**El resultado de esta etapa** es una lista de **símbolos candidatos**, cada uno con su tipo asignado (sujeto, objeto, verbo o estado). Todavía sin describir.

### 3.1 Vida Sana: la lista de candidatos

Del enunciado del centro de entrenamiento salen, leyendo con los cuatro criterios:

| Candidato | Tipo | ¿Core, gris o común? | Por qué |
|---|---|---|---|
| Socio | Sujeto | Core | Aparece en todo el texto; es quien contrata, se inscribe, avisa |
| Profesor | Sujeto | Core | Da clases y hoy lleva todos los registros |
| Junta Directiva | Sujeto | Core | Son los dueños; deciden; piden el software |
| Clase | Objeto | Core | Unidad de todo: tiene cupo, horario, inscriptos |
| Plan | Objeto | Core | 4, 6, 8 o 12 clases por mes; lo que el socio contrata |
| Cupo | Objeto | Core | Lo que limita cada clase; de ahí sale la lista de espera |
| Lista de espera | Objeto | Core | Mecanismo propio del negocio, con reglas |
| Ficha del socio | Objeto | Core | El registro de la carpeta del centro, con planes, presentes y pagos; genera los problemas que motivan el software |
| Ficha que lleva el socio | Objeto | Gris → preguntar | Es otro papel: lo lleva el socio y tiene inicio y fin del plan y presentes. ¿Es un segundo símbolo o una copia de la anterior? |
| Carpeta de clases | Objeto | Core | Donde se anotan presentes y ausentes |
| Control de caja | Objeto | Gris → preguntar | Es un documento del negocio; falta saber si tiene reglas propias o es solo "la caja" |
| Sector | Objeto | Gris → preguntar | "Sector de cardio", "sector de musculación": ¿es un concepto con reglas (tiempo mínimo y máximo) o solo un lugar? |
| Turno | Objeto | Gris → preguntar | Se usa para las franjas horarias; ¿es lo mismo que clase? (módulo 2: sinónimo parcial) |
| Reformer | Objeto | Core | Es el aparato de pilates, palabra propia del negocio; define el cupo de esa clase |
| Código de socio | Objeto | Gris → preguntar | Las 3 letras del nombre + 2 del apellido; poco fiable |
| Contratar plan | Verbo | Core | Acción que arranca todo |
| Inscribirse a clase | Verbo | Core | La acción central |
| Avisar ausencia | Verbo | Core | Tiene regla propia (el día anterior) y consecuencia (recuperar) |
| Recuperar clase | Verbo | Core | Solo quien avisó puede |
| Completa | Estado | Core | Estado de una clase con el cupo lleno; habilita la lista de espera |
| Socio fijo | Estado | Gris → preguntar | Se anotan en azul; ¿qué los distingue? |
| Seña | Objeto | Gris → preguntar | Forma de pago; ¿tiene reglas propias? |
| Bono | Objeto | Gris → preguntar | Los profesores lo cobran por clases completas; ¿entra en el alcance? |
| Hora, mes, sábado, resaltador verde | — | Común | No entran |

Veintitrés candidatos, de los cuales quince son core. Para el ejemplo de este módulo se describen nueve: suficientes para ver la técnica. El resto queda para el TP.

🕳️ **Madriguera — clasificación por dominio.** En algunos proyectos se arman subtipos propios del negocio (personas, sectores, formularios, índices) para describir con más uniformidad. La cátedra se queda con los cuatro tipos. *Volvé al camino.*

## 4. 🔴 Describir: cómo se escribe cada símbolo

Ahora cada candidato recibe su noción y su impacto. Las reglas, divididas en forma y contenido. Varias ya las viste en el módulo 1; acá está la lista completa que usa la cátedra.

**Forma**
- Al menos un nombre, una oración en la noción y una en el impacto.
- Oraciones simples: una sola idea y un solo verbo. Una condición pegada a la acción ("cuando se llena el cupo", "si avisó") cuenta como parte de la misma idea; lo que no va es juntar dos acciones con "y".
- Cada oración menciona al menos otro símbolo, marcado.
- El nombre es el que usa el negocio; los sinónimos comparten la entrada.
- Verbos en infinitivo; sustantivos en singular.
- Se respeta la plantilla del tipo.

**Contenido**
- Registrar **todo impacto conocido**: la calidad del LEL se juega en que los impactos estén completos.
- En sujetos y objetos, acentuar el **"qué"** de las acciones: *qué* hace el socio, no *cómo* lo hace paso a paso.
- Evitar el **"cómo"**: un LEL orientado a procedimientos deja de ser un vocabulario y se vuelve un manual.
- Identificar si cada oración es información actual o formal.
- El "cómo" y los problemas actuales van a la **Ficha de Información Anticipada** (sección 5).
- Explorar frases con el mismo núcleo para descubrir símbolos omitidos o sinónimos (módulo 2, jerarquías).

### 4.1 Vida Sana: nueve símbolos descriptos

**Sujetos**

> ### Socio
> *Tipo: Sujeto*
>
> **Noción**
> - Es la persona que contrata un [[Plan]] para asistir a las [[Clase|clases]] del centro de entrenamiento.
>
> **Impacto**
> - Realiza [[Contratar plan]].
> - Realiza [[Inscribirse a clase]] hasta la cantidad de [[Clase|clases]] de su [[Plan]].
> - Realiza [[Avisar ausencia]] al menos el día anterior a la [[Clase]].
> - Realiza [[Recuperar clase]] solo si realizó [[Avisar ausencia]].
> - Es anotado en la [[Lista de espera]] cuando la [[Clase]] está [[Completa]].
> - Es registrado por el [[Profesor]] en la [[Ficha del socio]].

> ### Profesor
> *Tipo: Sujeto*
>
> **Noción**
> - Es el empleado que da las [[Clase|clases]] del centro de entrenamiento.
>
> **Impacto**
> - Registra al [[Socio]] en la [[Ficha del socio]] y en la [[Carpeta de clases]].
> - Llama a los [[Socio|socios]] de la [[Lista de espera]] cuando se libera un [[Cupo]].
> - Llama a los [[Socio|socios]] inscriptos para ofrecerles otra [[Clase]] cuando hay menos de tres anotados.
> - Registra los pagos del [[Plan]] en la [[Ficha del socio]].

**Objetos**

> ### Clase
> *Tipo: Objeto*
>
> **Noción**
> - Es una sesión de una hora de pilates, funcional, stretching o yoga, dada por un [[Profesor]] en un horario fijo.
> - Tiene un [[Cupo]] de ocho [[Socio|socios]].
>
> **Impacto**
> - El [[Socio]] realiza [[Inscribirse a clase]] en ella.
> - Pasa a [[Completa]] cuando se llena su [[Cupo]].
> - Se cancela si tiene menos de tres [[Socio|socios]] anotados.
> - Se registra en la [[Carpeta de clases]].

> ### Plan
> *Tipo: Objeto*
>
> **Noción**
> - Es un paquete de 4, 6, 8 o 12 [[Clase|clases]] que el [[Socio]] contrata por mes calendario.
> - Vence al mes de la primera [[Clase]].
>
> **Impacto**
> - El [[Socio]] lo contrata mediante [[Contratar plan]].
> - Limita cuántas veces el [[Socio]] puede [[Inscribirse a clase]].
> - Se registra en la [[Ficha del socio]].

> ### Lista de espera
> *Tipo: Objeto*
>
> **Noción**
> - Es la lista ordenada de [[Socio|socios]] que quieren un [[Cupo]] en una [[Clase]] que está [[Completa]].
>
> **Impacto**
> - El [[Profesor]] anota al [[Socio]] en ella.
> - El [[Profesor]] llama al primero de la lista cuando un [[Socio]] realiza [[Avisar ausencia]].

> ### Ficha del socio
> *Tipo: Objeto*
>
> **Noción**
> - Es el registro de un [[Socio]], en la carpeta del centro, donde constan su [[Plan]], sus presentes y sus pagos.
> - Se distingue de la [[Ficha que lleva el socio]], que es otro papel.
>
> **Impacto**
> - El [[Profesor]] la completa en cada [[Clase]].
> - El [[Profesor]] registra en ella los pagos del [[Plan]].

**Verbos**

> ### Inscribirse a clase
> *Tipo: Verbo*
>
> **Noción**
> - Lo realiza el [[Socio]] con el [[Profesor]], en el centro, para reservar un [[Cupo]] en una [[Clase]].
>
> **Impacto**
> - El [[Profesor]] lo anota en la [[Carpeta de clases]].
> - No puede realizarse si el [[Socio]] no tiene [[Clase|clases]] disponibles en su [[Plan]].
> - Si la [[Clase]] está [[Completa]], el [[Socio]] puede anotarse en la [[Lista de espera]].

> ### Avisar ausencia
> *Tipo: Verbo*
>
> **Noción**
> - Lo realiza el [[Socio]], al menos el día anterior a la [[Clase]], para informar que no va a asistir.
>
> **Impacto**
> - Libera el [[Cupo]] del [[Socio]] en esa [[Clase]].
> - Habilita al [[Socio]] a realizar [[Recuperar clase]].
> - Desencadena que el [[Profesor]] llame a la [[Lista de espera]].

**Estado**

> ### Completa
> *Tipo: Estado*
>
> **Noción**
> - Es el estado de una [[Clase]] cuyo [[Cupo]] está lleno.
> - Se llega a él cuando el último [[Socio]] realiza [[Inscribirse a clase]].
>
> **Impacto**
> - Los nuevos [[Socio|socios]] van a la [[Lista de espera]].
> - Deja de estar Completa cuando un [[Socio]] realiza [[Avisar ausencia]].

**Cosas para notar en estos nueve:**
- Cada oración menciona al menos otro símbolo con corchetes. Contá: no hay ninguna sin referencia.
- Varias oraciones tienen una condición ("cuando se llena su Cupo", "si realizó Avisar ausencia"). Cuenta como una sola idea: la acción y su condición. Lo que no hay es ninguna oración con dos acciones unidas por "y".
- `Profesor` tiene cuatro impactos porque hoy hace muchas cosas. Está bien registrarlas todas aunque el software las vaya a cambiar: el LEL describe el negocio *actual*. Fijate que no dice que el profesor *cobra*: el enunciado no lo dice, y eso es justo un caso de "no supongas, preguntá".
- `Socio` tiene oraciones en pasiva ("es anotado", "es registrado"): acciones que recibe. Sigue siendo sujeto (módulo 2, sección 6).
- Se mencionan `Cupo`, `Carpeta de clases`, `Ficha que lleva el socio`, `Contratar plan` y `Recuperar clase` sin haberlos descripto. En un LEL terminado eso sería una **omisión**; acá es a propósito, porque el ejemplo quedó en nueve. Cuando lo completes para el TP, se describen.

🧵 **Hilo abierto.** Estos nueve símbolos no se revisaron. ¿Hay algo mal? Seguro. En el módulo 4 se pasa la lista de control y aparece.

## 5. 🔴 La Ficha de Información Anticipada

Mientras recolectás vocabulario, el usuario te cuenta un montón de cosas que **no son vocabulario**: qué le molesta, qué querría cambiar, cómo hace hoy cada tarea paso a paso. Eso es valioso, pero no va al LEL. Va a la **Ficha de Información Anticipada**: un registro aparte, de texto libre, que se usa después, cuando se construyen los escenarios futuros (serie siguiente).

Qué va a la ficha:
- **Necesidades y problemas:** "los profesores quieren desentenderse de todo registro y dedicarse a dar clase".
- **Propuestas:** "los socios quieren poder avisar una ausencia hasta una hora antes".
- **El "cómo" actual, paso a paso:** "el profesor pinta con resaltador verde los presentes y con naranja los ausentes".
- **Restricciones de los dueños:** "la Junta no quiere contratar personal extra para el registro".
- **Defectos del sistema actual:** "el código de socio (3 letras del nombre + 2 del apellido) genera repetidos".

Fijate que ninguna de esas oraciones define una palabra. Todas describen una situación o un deseo. Por eso no son noción ni impacto de nada.

> 🎓 **Para el parcial, si te preguntan: ¿qué es la Ficha de Información Anticipada?**
> Es el registro donde se anota la información elicitada que no es vocabulario: necesidades, problemas, propuestas y el "cómo" actual de las actividades. Se completa durante la construcción del LEL y se analiza después, al construir los escenarios futuros.

## 6. 🟡 Verificar y validar: el anticipo

Las dos últimas etapas son el módulo 4 entero. Acá, solo para que el proceso cierre:

- **Verificar** responde "¿está bien construido?": lo hacen los analistas, contra el modelo del LEL, las plantillas y las reglas de este módulo. Es una inspección.
- **Validar** responde "¿es el vocabulario que el negocio usa de verdad?": se hace con los clientes y usuarios, leyéndoles cada símbolo para que confirmen, corrijan o agreguen. Es fácil, porque el LEL está escrito en su idioma.

Las dos producen una lista de DEOs que vuelve a Recolectar y a Describir.

---

## Checkpoint del módulo 3

Respondé sin mirar el texto. Sin respuestas acá: van al complemento.

1. Nombrá las cinco etapas en orden y decí cuál es de elicitar, cuál de modelar y cuál de analizar. ¿Por qué se dice que el proceso no es lineal?
2. En Vida Sana, ¿quiénes son las fuentes de información y en qué orden las priorizás? Da un ejemplo de información actual y uno de información formal.
3. "Resaltador naranja" aparece en el enunciado. ¿Es un símbolo? ¿Y "reformer"? Justificá con los criterios de selección y decí qué harías con el gris.
4. Escribí el símbolo `Cupo` (objeto) para Vida Sana, con noción e impacto, usando corchetes. Después decí cuál de los nueve del módulo debería mencionarlo y no lo hace.
5. Clasificá cada frase: ¿va al LEL (como noción o impacto de qué símbolo) o a la Ficha de Información Anticipada? (a) "El plan vence al mes de la primera clase." (b) "Los socios se quejan por la anticipación con que deben avisar." (c) "El profesor llama al primero de la lista de espera." (d) "Los profesores quieren un bono por clases completas."

## Qué viene en el módulo 4

Los nueve símbolos de Vida Sana y el borrador de la veterinaria se revisan con la lista de control de la cátedra. Vas a ver verificar y validar en detalle, la lista DEO como la pide la cátedra, los cuatro grupos de defectos con la señal que delata cada uno, y lo justo de Obsidian para el parcial y el TP. Es el módulo que más se parece a lo que te van a tomar.

---

**FIN DEL MÓDULO 3 — Clase desde cero — LEL**
