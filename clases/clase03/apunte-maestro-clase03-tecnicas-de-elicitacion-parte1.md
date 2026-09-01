# 📘 APUNTE MAESTRO — Clase 03 · Técnicas de Elicitación — Parte 1

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Unidad:** `clase03` · Jueves 27/08/2026 · Virtual
**Parte 1:** el problema del relevamiento, el mapa de las siete técnicas, los dos ejes transversales, y las dos técnicas que no le preguntan nada a nadie.

---

## Sobre esta parte

**Qué cubre:** por qué existe el relevamiento (el caso de la consultora que no conoce el negocio) · qué es elicitación · el mapa de las siete técnicas y cómo las nombra la cátedra · los dos ejes que atraviesan todas las técnicas (dato cuantitativo/cualitativo, pregunta abierta/cerrada) · **Técnica 1: revisión de documentos**, incluido el muestreo · **Técnica 2: investigación y visitas**.

**Qué viene después:** Parte 2 — observación. Parte 3 — cuestionarios. Parte 4 — entrevistas. Parte 5 — prototipos de descubrimiento, JRP, y el plan de relevamiento: la resolución del caso con los criterios con que se corrige.

**Marcas:** 🔴 central, evaluable · 🟡 secundario · 🟢 mencionado al pasar · 🕳️ madriguera (existe, no se profundiza acá).

## De dónde venís

Clase 01: requisitos funcionales y no funcionales; stakeholders, usuarios y clientes — y que no son lo mismo. Clase 02: casos de uso, actores y relaciones. Todo eso se asume: esta clase se para encima. En particular, cuando acá se habla de "roles del cliente", son los stakeholders y usuarios que ya sabés distinguir.

---

## 1. 🔴 El problema: relevar un negocio que no conocés

**Situación.** Formás parte del equipo de Ingeniería de Requisitos de una consultora exitosa. Su especialidad son los sistemas de torres de control aeroportuaria. Los contrata una empresa de estacionamientos que está expandiéndose: suma playas en 20 locaciones de la ciudad, unas 2.000 plazas más, y ofrece estacionamiento por hora, por día (jornada o media jornada) y mensual. Esto duplica su cantidad de locales y prevén un crecimiento exponencial de clientes. El control de ingresos y egresos, y el de abonos, hoy es manual, garage por garage y cliente por cliente — y no aguanta el crecimiento.

Tu consultora **no sabe nada de estacionamientos.**

**Lo que te piden:** un **plan de relevamiento** para presentarle al gerente de proyecto, que detalle los roles involucrados (de la consultora y del cliente), las tareas a realizar, la mayor diversidad posible de técnicas de relevamiento con una prioridad para cada una, y las ventajas de la técnica que consideres más provechosa. Y cuatro preguntas: ¿cómo harían el relevamiento? ¿qué roles de la consultora? ¿qué roles del cliente? **¿por qué?**

Antes de contestar, notá tres cosas:

1. **No podés inventar los requisitos.** No conocés el negocio, así que cualquier requisito que escribas sin relevar es una suposición — y las suposiciones son lo que después se paga caro.
2. **La información está repartida.** Parte en la cabeza del administrador, parte en la del encargado que cobra en la garita, parte en planillas y comprobantes, parte en cómo se mueve un cliente un lunes a las 8 de la mañana.
3. **Hay que elegir cómo sacar cada pedazo de información — y justificar la elección.** Ese "¿por qué?" del final no es decorativo: es la pregunta que se corrige. "Voy a hacer entrevistas y cuestionarios" no es un plan. "Entrevisto al administrador porque tengo un hueco de información sobre X, y uso entrevista y no cuestionario porque necesito repreguntar" sí lo es.

Todo lo que sigue en esta clase es el conjunto de herramientas para responder eso.

---

## 2. 🔴 Qué es elicitación

**Elicitación** (del inglés *elicit*: sacar a la luz, hacer aflorar) es la actividad de la Ingeniería de Requisitos que **descubre** los requisitos: hablando con las personas, leyendo lo que la organización ya produjo y mirando cómo se trabaja de verdad. En la cátedra vas a escuchar tres nombres para lo mismo: **elicitación**, **relevamiento** y recolección de información. Son intercambiables; "plan de relevamiento" y "técnicas de elicitación" hablan de la misma actividad.

En el arco de la materia —entender, **descubrir**, modelar, especificar, validar— la elicitación es el *descubrir*. Sin ella, todo lo que modelás y especificás después se apoya en aire.

Un analista necesita un **método organizado** para recolectar hechos, y una mentalidad de detective: discernir qué es relevante y qué no. Eso es lo que las técnicas te dan. No son recetas: son instrumentos, cada uno con su costo, su fortaleza y su punto ciego. Por eso en un plan de relevamiento se **combinan** — ninguna sola alcanza.

---

## 3. 🟢 Dos actividades que cierran el ciclo (contexto)

No son el tema de hoy, pero aparecen definidas y vuelven más adelante en la materia, así que van en pocas líneas cada una.

**Validación de requisitos:** chequear el documento de definición de requisitos por exactitud, completitud, consistencia y conformidad a estándares. Se hace sobre el borrador final, cuando ya se recibió todo el aporte de dueños y usuarios; su propósito es asegurar que los requisitos estén *bien escritos*. Los errores típicos que encuentra: modelos con errores, errores de tipeo o gramática, requisitos que se contradicen entre sí, **requisitos ambiguos o mal redactados**, y falta de conformidad al estándar del documento. Fijate que "ambiguo" ya está acá como error: es el criterio de calidad que atraviesa toda la materia.

**Gestión de requisitos:** el proceso de administrar el **cambio** de los requisitos. A lo largo de un proyecto es normal que aparezcan requisitos nuevos y que cambien los ya aprobados — hay estudios que dan 50% o más de cambio antes de que el sistema entre en producción. Gestionar eso es definir cómo se presenta un pedido de cambio, cómo se analiza su impacto (alcance, cronograma, costo), cómo se aprueba o rechaza, y cómo se implementa si se aprueba.

*Volvé al camino: hoy lo que importa es descubrir los requisitos, no todavía validarlos ni gestionarlos.*

---

## 4. 🔴 El mapa: siete técnicas

Hay siete técnicas de elicitación, y conviene tenerlas todas en la cabeza antes de entrar a cualquiera. Lo primero que distingue una técnica de otra es **de dónde sale la información**: de documentos que ya existen, de mirar el trabajo, o de preguntarle a alguien.

```text
 ¿DE DÓNDE SALE LA INFORMACIÓN?
 ──────────────────────────────────────────────────────────────────────
 De lo que la organización        1. Revisión de documentos
 YA PRODUJO — nadie te            2. Investigación (y visitas a otras
 contesta nada                       organizaciones)
 ──────────────────────────────────────────────────────────────────────
 De MIRAR cómo se trabaja         3. Observación
 ──────────────────────────────────────────────────────────────────────
 De PREGUNTARLE a alguien         4. Cuestionario  → por escrito, sin vos presente
                                  5. Entrevista    → cara a cara
                                  6. Prototipo de descubrimiento
                                                   → mostrás un modelo y la gente
                                                     reconoce lo que quiere
                                  7. JRP           → sesión grupal estructurada
```

| # | Técnica | En una línea | Detalle |
|---|---|---|---|
| 1 | **Revisión de documentos** | Analizar material que la organización ya generó: formularios, reportes, bases de datos, organigrama. | Esta parte, §6 |
| 2 | **Investigación** | Estudiar el dominio del problema fuera de la organización: cómo lo resolvieron otros, visitas, bibliografía. | Esta parte, §7 |
| 3 | **Observación** | Mirar (o hacer) el trabajo en el lugar donde ocurre. Se clasifica en intrusiva y no intrusiva. | Parte 2 |
| 4 | **Cuestionario** | Documento con preguntas que la gente responde por su cuenta, sin el analista presente. | Parte 3 |
| 5 | **Entrevista** | Conversación cara a cara, dirigida por el analista. La más usada y la más importante. | Parte 4 |
| 6 | **Prototipo de descubrimiento** | Modelo chico y rápido del sistema, para que los usuarios reconozcan sus requisitos al verlo. | Parte 5 |
| 7 | **JRP** (*Joint Requirements Planning*) | Reuniones grupales muy estructuradas para analizar problemas y definir requisitos con todos en la sala. | Parte 5 |

Las cinco primeras son las que la cátedra nombra como base; las dos últimas amplían el repertorio.

> **Para el parcial, si te preguntan:** *¿Cuál de las técnicas no implica preguntarle nada a una persona?*
> La revisión de documentos: se analiza material que la organización ya generó —formularios, reportes, bases de datos, organigrama— sin entrevistar ni encuestar a nadie.

> ⚠️ **Informe de reconocimiento.** En esta clase aparece como ejemplo de **documento** que se le puede pedir a la empresa —junto al organigrama— para conocer su misión, valores y cultura. Es un documento, **no una técnica**. Si te lo ponen al lado de "revisión de documentos" preguntando cuál técnica no interroga a nadie, la respuesta es revisión de documentos.

---

## 5. 🔴 Dos ejes que atraviesan todas las técnicas

### 5.1 Dato cuantitativo vs. cualitativo

Un dato **cuantitativo** es exacto y medible: "procesamos 200 pedidos por día", "hay 30 consultorios", "el abono mensual cuesta tanto". Un dato cualitativo (glosa: opiniones, percepciones, descripciones — "el sistema es lento", "los clientes se quejan") también se releva, pero no reemplaza al número.

El criterio de la cátedra es directo: **lo que se puede medir, se mide.** "Esperé un montón" no es un dato; "esperé 15 minutos" sí. Cuando en un plan de relevamiento escribís "hay demoras largas", la pregunta que te van a hacer es *¿qué es una demora larga?* — y la respuesta tiene que ser un número, obtenido por observación con reloj, por registros, o por una pregunta cerrada que pida el número. Una persona puede decir que esperó "80 horas" y haber esperado 15 minutos.

> **Para el parcial, si te preguntan:** *Si en una entrevista el analista busca datos exactos y medibles, ¿qué tipo de información busca?*
> Cuantitativa: datos exactos y medibles, como "procesamos 200 pedidos por día".

### 5.2 Preguntas abiertas vs. cerradas

Una pregunta **abierta** deja al entrevistado o encuestado hablar y desarrollar ("¿qué problemas tenés hoy con el cobro de abonos?"). Una pregunta **cerrada** le da opciones y tiene que elegir ("¿cobrás en efectivo, con tarjeta o ambos?").

Este eje tiene sentido en **dos técnicas solamente: entrevista y cuestionario** — las dos donde hay preguntas. En la observación no preguntás; en la revisión de documentos tampoco.

Cuál usar depende de qué información querés y de cuánta gente responde. Si vas a encuestar a 500 personas, no te sirve que 500 personas desarrollen y fundamenten: necesitás cerradas para poder tabular. Si estás con el administrador que conoce el negocio entero, una abierta bien puesta te da más que diez cerradas. El detalle de cómo se arman —y los tipos de pregunta cerrada que existen— se desarrolla en la Parte 3 (cuestionarios) y la Parte 4 (entrevistas).

> **Para el parcial, si te preguntan:** *¿En qué dos técnicas tiene sentido hablar de preguntas abiertas o cerradas?*
> En entrevista y cuestionario. Abierta: el entrevistado desarrolla la respuesta. Cerrada: elige entre opciones dadas.

> **Para el parcial, si te preguntan:** *¿Qué diferencia principal hay entre entrevista y cuestionario?*
> La entrevista es interacción directa con la persona, cara a cara; el cuestionario se responde por escrito, sin el analista presente.

---

## 6. 🔴 Técnica 1 — Revisión de documentos

(También: muestreo de documentación, formularios y archivos existentes.)

### 6.1 Por qué se empieza por acá

**Un buen analista obtiene los hechos primero de la documentación existente y recién después de las personas.** Cuatro razones:

- **Ya existe.** No le cuesta una hora a nadie de la organización.
- **No miente por cortesía.** Un formulario completado muestra lo que se hizo; una persona te cuenta lo que cree, o lo que quiere que veas.
- **Te da el mapa antes de la charla.** Con el organigrama y los procedimientos leídos, llegás a la entrevista sabiendo a quién le preguntás qué. Lo contrario —ir a preguntar cosas que estaban en un documento— desperdicia la entrevista y, peor, te obliga a una segunda reunión, con su minuta, su agenda y su costo.
- **Verifica.** Lo que te digan después se puede contrastar contra lo que el documento muestra.

En el caso de estacionamientos: antes de sentarte con el administrador, pedís las planillas de abonos mensuales, los comprobantes de cobro por hora, los registros de ingreso y egreso de cada garage (aunque sean cuadernos), y el organigrama si existe. Cuando llegues a la entrevista, ya vas a saber cuántos locales hay hoy, cómo se cobra y dónde se pierde información.

### 6.2 Qué documentos buscar

**El primero, siempre: el organigrama.** Te dice quién es quién, quién depende de quién y a quién tenés que entrevistar.

Después, tres familias de documentos, que responden a tres preguntas distintas.

**(a) ¿Cuál es el problema y de dónde viene?** Documentos que describen el problema y la historia que llevó al proyecto:
- Memos internos, estudios, minutas de reunión, notas del buzón de sugerencias, reclamos de clientes, informes que documentan el área con problemas.
- Registros contables, evaluaciones de desempeño, mediciones de trabajo y otros reportes operativos periódicos.
- Pedidos de proyectos de sistemas, pasados y presentes — qué se pidió antes y qué pasó con eso.

**(b) ¿Cómo funciona el negocio que voy a informatizar?** Documentos que describen la función de negocio:
- Misión y plan estratégico de la empresa.
- Objetivos formales de las áreas o subunidades que estás estudiando.
- **Manuales de políticas** — ojo: pueden imponer restricciones a cualquier sistema que propongas.
- Procedimientos operativos estándar (SOP, *standard operating procedures*: el "cómo se hace" escrito paso a paso), descripciones de puesto, instructivos de tareas del día a día.
- **Formularios completados** que representen transacciones reales en distintos puntos del proceso.
- Muestras de bases de datos, manuales y computarizadas.
- Muestras de pantallas y reportes, manuales y computarizados.

**(c) ¿Alguien ya intentó resolver esto?** Documentación de estudios y diseños de sistemas anteriores, hechos por analistas o consultoras previas:
- Diagramas y flujogramas de todo tipo.
- Diccionarios o repositorios de proyecto.
- Documentación de diseño: entradas, salidas, bases de datos.
- Documentación de programas.
- Manuales de operación y de capacitación.

Que exista un sistema anterior que "no alcanza" es información valiosísima: de dónde salió, quién lo pidió, qué necesidad quería cubrir y por qué no resuelve el problema por el que ahora te contratan. Eso es lo primero que le vas a preguntar al equipo de IT del cliente — pero antes, revisás lo que dejaron escrito.

### 6.3 Vigencia: lo desactualizado también sirve

Toda la documentación que juntes hay que analizarla para saber **qué tan vigente está**. Pero no descartes lo desactualizado: te muestra cómo era, y te marca exactamente qué hay que verificar o actualizar con otra técnica. Mientras revisás, tomá notas, dibujá, y modelá lo que vas entendiendo con las herramientas de análisis que ya manejás — relevar y modelar no son etapas separadas por una pared.

### 6.4 🟡 Muestreo: no podés leer todo

Sería impracticable estudiar cada ocurrencia de cada formulario o cada registro de una base. Por eso se trabaja con una **muestra**.

**Muestreo** es el proceso de recolectar una muestra **representativa** de documentos, formularios y registros. La palabra clave es *representativa*: querés muestrear lo suficiente como para que aparezcan toda la naturaleza y complejidad de los datos — **todas las condiciones de procesamiento y todas las excepciones**. Si tu muestra solo tiene casos normales, tu sistema no va a contemplar los raros, y los raros son los que rompen.

Dos reglas de analista experimentado:
- **Nunca muestrear formularios en blanco.** Un formulario vacío no te dice nada de cómo se usa, cómo no se usa o cómo se usa mal. El valor está en los completados.
- Muestrear hasta cubrir las excepciones, no hasta "tener varios".

### 6.5 🟡 Cuánto muestrear: la fórmula

El tamaño de la muestra depende de qué tan representativa la querés. Hay una fórmula simple y confiable:

```text
Tamaño de muestra = 0,25 × ( factor de certeza / error aceptable )²
```

- **Error aceptable:** cuánto margen de error tolerás, como proporción (10% → 0,10).
- **Factor de certeza:** cuánta confianza querés de que la muestra no deje afuera variaciones que sí existen en la población. Sale de tabla:

| Certeza deseada | Factor de certeza |
|---|---|
| 95% | 1,960 |
| 90% | 1,645 |
| 80% | 1,281 |

- **0,25:** valor heurístico para cuando no sabés nada de la población. Es el máximo posible de p(1−p), que se da en p = 0,5 — o sea, el caso peor. Si sabés algo más, se reemplaza (ver más abajo).

> 🕳️ **Madriguera — de dónde sale el factor de certeza**
> Es el valor *z* de la distribución normal estándar para ese nivel de confianza — lo mismo que usaste en Probabilidad y Estadística para intervalos de confianza. Las tablas completas están en cualquier texto de estadística o ingeniería industrial.
> *Volvé al camino — acá alcanza con la tabla de tres filas.*

**Ejemplo resuelto.** Querés 90% de certeza de que una muestra de facturas no deje afuera variaciones, con 10% de error aceptable.

```text
Paso 1   factor / error   =  1,645 / 0,10    = 16,45
Paso 2   al cuadrado      =  16,45²          = 270,60
Paso 3   × 0,25           =  0,25 × 270,60   = 67,65
Paso 4   redondeo         →  68 facturas     (siempre hacia arriba: 67 no alcanza)
```

Si quisieras 95% de certeza, el factor sube a 1,960 y la muestra crece. Más certeza, más facturas.

**Refinamiento cuando sabés algo de la población.** Supongamos que por experiencia sabés que 1 de cada 10 facturas se aparta de la norma. Entonces conocés **p = 0,10** (la proporción con variaciones), y en lugar del 0,25 genérico usás **p(1−p)**:

```text
Tamaño de muestra = p × (1−p) × ( factor de certeza / error aceptable )²

Paso 1   p(1−p)             =  0,10 × 0,90    = 0,09
Paso 2   (1,645 / 0,10)²    =  270,60         (igual que antes)
Paso 3   0,09 × 270,60      =  24,35
Paso 4   redondeo           →  25 facturas
```

Saber más de la población te permite muestrear **menos** con la misma certeza: de 68 bajaste a 25. Por eso vale la pena, antes de muestrear, preguntar "¿qué proporción de estos registros suele ser rara?".

### 6.6 🟡 Cómo elegir las muestras: randomización y estratificación

Ya sabés que necesitás 25 facturas. ¿Cuáles 25? Dos técnicas:

**Randomización:** elegir sin ningún patrón ni plan predeterminado. Agarrás 25 facturas al azar.

**Estratificación:** técnica **sistemática** que reduce la varianza de las estimaciones **distribuyendo** el muestreo —por ejemplo, eligiendo documentos o registros por fórmula— y evitando así caer en estimaciones muy altas o muy bajas por mala suerte.

Ejemplo con archivos computarizados: las facturas están en una base de datos con unos 250.000 registros y necesitás 25. Escribís un programa que imprima **cada registro número 10.000** (250.000 / 25). Con archivos manuales, hacés lo mismo a mano: cada n-ésima carpeta.

```text
 POBLACIÓN                ¿CUÁNTAS?                    ¿CUÁLES?
 250.000 facturas   ──►   fórmula → 25        ──►   randomización:   25 al azar
                                                     estratificación: 1 cada 10.000
```

> **Para el parcial, si te preguntan:** *¿Qué es el muestreo y cuál es la palabra clave?*
> Muestreo es recolectar una muestra representativa de documentos, formularios y registros. La palabra clave es *representativa*: la muestra tiene que cubrir todas las condiciones de procesamiento y excepciones, no solo los casos normales.

> **Para el parcial, si te preguntan:** *¿Por qué no se muestrean formularios en blanco?*
> Porque no dicen nada de cómo se usa, no se usa o se usa mal el formulario. La información está en los formularios completados, que representan transacciones reales.

> **Para el parcial, si te preguntan:** *Diferencia entre randomización y estratificación.*
> Randomización: se eligen las muestras sin patrón ni plan predeterminado. Estratificación: se eligen de forma sistemática (por ejemplo, cada n-ésimo registro) para distribuir el muestreo y reducir la varianza, evitando estimaciones muy altas o muy bajas.

---

## 7. 🟡 Técnica 2 — Investigación y visitas

**La mayoría de los problemas no son únicos: otros ya los resolvieron antes.** La investigación es estudiar a fondo el dominio del problema *fuera* de la organización que estás relevando.

Fuentes:
- **Visitas** a empresas que se sabe que tuvieron el mismo problema. Si están dispuestas a compartir, lo que aprendés ahorra tiempo y costo de desarrollo.
- **Asociaciones profesionales** del área de sistemas: una red de contactos con gente que pasó por lo mismo.
- **Revistas del rubro y libros de referencia:** cómo otros resolvieron problemas similares, y si ya existe un **paquete de software** que resuelva el tuyo — a veces la respuesta al relevamiento es "esto no se desarrolla, se compra".
- **Internet**, sin moverte del escritorio.

Para el caso: tu consultora no conoce estacionamientos, pero el problema de cobrar por hora, por día y por abono en múltiples locales está resuelto mil veces. Investigar cómo funcionan las playas de shopping con máquina de tickets, las apps de estacionamiento y los sistemas de abonos te da vocabulario, preguntas mejores para la entrevista, y una idea de qué funcionalidades son estándar antes de que el cliente te las pida.

> **Para el parcial, si te preguntan:** *¿Qué aporta la investigación como técnica de relevamiento?*
> Conocer cómo otras organizaciones resolvieron el mismo problema —mediante visitas, asociaciones profesionales, bibliografía e Internet—, lo que ahorra tiempo y costo, y permite saber si ya existe software que lo resuelva.

---

## 8. 📌 Información operativa de la clase

- **TP integrador — dominio asignado: un centro de entrenamiento.** Se trabaja sobre él durante todo el resto del cuatrimestre con entregas encadenadas. **Parte 1:** definir stakeholders, usuarios y clientes de la aplicación, y armar las preguntas que incluirías en una entrevista a los **profesores** y en una entrevista a los **dueños**. Van diferenciadas: profesores y dueños tienen intereses distintos sobre el mismo sistema, y los dueños probablemente no lo usen todos los días. Se entrega en el mismo documento del Drive del equipo; en el aula va a haber un espacio donde pegás el link. Según el cronograma, es el entregable que se corrige en la clase 04.
- **Caso de uso del Museo de Bellas Artes:** entregable para seguir reforzando la teoría de casos de uso.
- **Lo que se dijo en la defensa oral tiene que quedar escrito en el TP.** Los cambios comentados al aire no cuentan si no se cierran en el documento.
- **Devolución de los TPs anteriores** entre el jueves y el viernes; la de casos de uso va a ser más detallada que la que se dio en clase.
- **Teoría de elicitación** habilitada en el aula virtual, sección "técnicas de elicitación de requerimientos": preparación de la entrevista, minuta posterior, y costos de una reunión en tiempo y dinero.
- **Clase 04 (03/09): presencial en Campus.** Posible cambio de aula — se pide una más grande. Contenido: pros, contras, costos y consideraciones de las técnicas, con simulacro de entrevista. Se pide llegar con las consignas de entrevista preparadas.
- **Drive del equipo:** la carpeta compartida desde la primera clase se usa todo el cuatrimestre — conviene marcarla como favorita. Las consignas de clase se suben ahí, una por equipo.
- **Dominio del equipo 6 en la práctica de esta clase:** gestión de estacionamientos (el caso de §1).

---

## 9. ✅ Checkpoint — Parte 1

Sin respuestas. Las respuestas van al complemento.

1. Explicá con tus palabras qué es elicitación y por qué en la cátedra se la llama también "relevamiento".
2. En el caso de estacionamientos, ¿por qué no podés escribir los requisitos directamente? ¿Qué te falta y dónde está?
3. Nombrá las siete técnicas y agrupalas según de dónde sale la información.
4. ¿Cuál es la única técnica en la que no le preguntás nada a nadie? ¿Por qué "informe de reconocimiento" no es una respuesta válida a esa pregunta?
5. "El sistema tarda mucho en registrar un egreso." ¿Es un dato cuantitativo o cualitativo? ¿Cómo lo convertirías en el otro?
6. ¿Por qué el eje abierta/cerrada solo aplica a entrevista y cuestionario?
7. ¿Por qué un buen analista arranca por los documentos y no por las personas? Dá al menos tres razones.
8. ¿Cuál es el primer documento que buscás y para qué sirve?
9. ¿Por qué no se muestrean formularios en blanco?
10. Calculá el tamaño de muestra para 95% de certeza y 5% de error aceptable, sin conocer la población. Después recalculalo sabiendo que el 20% de los registros se aparta de la norma. ¿Cuánto bajó y por qué?
11. Tenés 80.000 remitos en una base y necesitás una muestra de 40. Describí cómo la elegirías por estratificación.
12. En el caso de estacionamientos, ¿qué investigarías fuera de la empresa antes de la primera entrevista?

## Qué viene en la Parte 2

Observación: mirar el trabajo donde ocurre. Cuándo usarla, la clasificación en intrusiva y no intrusiva, qué puede salir mal cuando la gente sabe que la mirás, cómo se prepara — y una historia sobre un tren que no paraba a las 2:30.

---

**FIN DE LA PARTE 1 — Apunte Maestro clase03 · Técnicas de Elicitación**
