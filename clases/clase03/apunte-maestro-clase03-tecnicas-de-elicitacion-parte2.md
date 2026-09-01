# 📘 APUNTE MAESTRO — Clase 03 · Técnicas de Elicitación — Parte 2

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Unidad:** `clase03` · Jueves 27/08/2026 · Virtual
**Parte 2:** Técnica 3 — Observación.

---

## Sobre esta parte

**Qué cubre:** qué es la observación y cuándo conviene · su clasificación en intrusiva y no intrusiva · una historia clásica sobre elegir mal la técnica · ventajas y desventajas · cómo se prepara y cómo se conduce · muestreo de trabajo · vivir el sistema.

**Qué viene después:** Parte 3 — cuestionarios. Parte 4 — entrevistas. Parte 5 — prototipos de descubrimiento, JRP y el plan de relevamiento.

**Marcas:** 🔴 central, evaluable · 🟡 secundario · 🟢 mencionado al pasar · 🕳️ madriguera.

## De dónde venís

De la Parte 1: el caso de estacionamientos, el mapa de las siete técnicas (la observación es la 3: la información sale de **mirar** cómo se trabaja, no de documentos ni de preguntas), el criterio "lo que se puede medir, se mide", y la fórmula de tamaño de muestra de §6.5 — que acá se vuelve a usar.

---

## 1. 🔴 Qué es observar, y cuándo hace falta

Volvé al caso. Ya leíste las planillas de abonos y los cuadernos de ingresos y egresos. Ya te contaron cómo se cobra. Pero hay dos cosas que ni el documento ni la explicación te van a dar: cómo se mueve **de verdad** una playa un lunes a las 8 cuando entran veinte autos en diez minutos, y cuánto tarda el encargado en cobrar y anotar cada uno. Para eso tenés que ir y mirar.

**Observación** es la técnica en la que el analista **participa en** o **mira a** una persona realizar actividades, para aprender sobre el sistema.

Es especialmente útil en dos situaciones:

- **Cuando la validez de lo que obtuviste por otros métodos está en duda.** Te dijeron que el cobro tarda un minuto; querés confirmarlo con reloj.
- **Cuando la complejidad de una parte del sistema impide que los usuarios la expliquen con claridad.** Hay tareas que la gente hace todos los días y no sabe describir en palabras; hay que verlas.

Un caso típico: el procedimiento escrito dice cinco pasos, y en la práctica diaria se ejecutan dos. Ni el documento ni la persona te lo cuentan — el documento porque describe lo que debería pasar, la persona porque ya ni registra que se saltea tres. Observando lo ves en cinco minutos.

---

## 2. 🔴 Intrusiva y no intrusiva

La observación se clasifica en dos tipos, según **si el observado sabe o no que lo están mirando**:

| Tipo | El observado… | Lo que ganás | Lo que pagás |
|---|---|---|---|
| **Intrusiva** | **sabe** que está siendo observado | Podés pedir permiso, avisar el propósito, tomar notas a la vista, preguntar después | La persona puede actuar distinto porque se sabe mirada (ver §4) |
| **No intrusiva** | **no sabe** que está siendo observado | Ves el comportamiento natural | No podés interactuar ni pedir que te expliquen lo que hacen |

Las dos columnas de la derecha se desarrollan en §4 y §5: casi todas las desventajas de la observación son el precio de que la gente sepa que la mirás, y casi todas las guías para hacerla bien asumen que le avisaste.

> **Para el parcial, si te preguntan:** *¿Cómo se clasifica la observación según si el observado sabe o no que lo están mirando?*
> En intrusiva (el observado sabe que está siendo observado) y no intrusiva (no lo sabe).

---

## 3. 🔴 La Paradoja del Ferrocarril: cuando observar es la técnica equivocada

Una historia clásica del análisis de sistemas, de Gerald Weinberg.

A unos 50 kilómetros de Ciudad Gótica está Suburbia, un suburbio rico. Cada mañana, miles de personas toman el tren de la Central Railroad a la ciudad; cada tarde, el mismo tren las devuelve a sus casas. A muchos cónyuges les gustaba ir a la ciudad a encontrarse con su pareja al final del día: cena, teatro, y antes, un rato de compras. Para llegar con tiempo había que salir a las 2:30 o 3:00 de la tarde — y a esa hora ningún tren paraba en Suburbia.

Algunos vecinos notaron que un tren de la Central **pasaba** por la estación a las 2:30, sin detenerse. Juntaron firmas puerta por puerta pidiendo que ese tren parara en Suburbia: 253. Mandaron la petición.

Tres semanas después llegó la respuesta de la empresa. Agradecían el interés. Explicaban que, en respuesta a la petición, su representante de atención al cliente había visitado la estación de Suburbia **tres días distintos, cada uno a las 2:30 de la tarde**, y que, aunque observó con mucho cuidado, **en ninguna de las tres ocasiones había pasajeros esperando un tren hacia el sur**. La única conclusión posible era que no existía demanda real de una parada a las 2:30. Lamentaban tener que rechazar el pedido.

¿Por qué iba a estar alguien esperando en el andén un tren que todo el mundo sabía que no paraba?

Dos lecciones:

1. **Usá la técnica apropiada para el problema.** Observar fue una elección incorrecta: la observación mide lo que pasa hoy, y lo que se quería saber era qué pasaría si algo cambiara. Para eso servía la petición misma, o un cuestionario a los 253 firmantes, o una entrevista a algunos de ellos. Cada técnica tiene un tipo de pregunta que puede responder y otro que no. Elegir la técnica **es** parte del análisis, no un trámite previo.
2. **Verificá los resultados de tu relevamiento con el usuario.** Si el representante hubiera vuelto con "no había nadie" y se lo hubiera mostrado a un firmante, la respuesta habría sido obvia en diez segundos. Del feedback del usuario podés descubrir que necesitás otra técnica para juntar más información. **Nunca saltes a conclusiones.**

Esta historia es el fundamento de lo que se corrige en el plan de relevamiento: no alcanza con listar técnicas, hay que poder decir por qué **esa** técnica sirve para **ese** hueco de información en **ese** dominio.

> **Para el parcial, si te preguntan:** *¿Qué enseña la Paradoja del Ferrocarril?*
> Que hay que elegir la técnica de relevamiento apropiada al problema —la observación mide lo que pasa hoy, no lo que pasaría si algo cambiara— y que los resultados del relevamiento se verifican con el usuario antes de sacar conclusiones.

---

## 4. 🔴 Ventajas y desventajas

La observación puede ser muy útil **siempre que tengas la capacidad de observar con rigor y precisión**. Sus pros y sus contras:

### Ventajas

- **Los datos son altamente confiables.** A veces se observa justamente para **chequear la validez** de datos obtenidos de las personas por otras técnicas.
- **Ves exactamente lo que se hace.** Las tareas complejas son difíciles de explicar en palabras. Observando podés identificar tareas que las otras técnicas **omitieron o describieron mal**. También obtenés datos del **entorno físico** de la tarea: distribución del espacio, tráfico, iluminación, nivel de ruido — cosas que nadie pone en un formulario.
- **Es relativamente barata.** Las otras técnicas suelen requerir bastante más tiempo liberado de los empleados y gastos de copiado; observar solo te cuesta tu propio tiempo.
- **Permite hacer mediciones de trabajo.** Cuánto tarda cada cosa, cuántas veces ocurre, cuándo. Es la técnica natural para convertir "demora mucho" en un número — el criterio de la Parte 1.

### Desventajas

- **La gente se siente incómoda cuando la miran y, sin darse cuenta, actúa distinto.** El experimento Hawthorne (glosa: estudio clásico en una fábrica donde el rendimiento cambiaba por el solo hecho de que los trabajadores sabían que los estaban estudiando) probó que el acto de observar altera el comportamiento.
- **Lo que observás puede no tener el nivel de dificultad ni el volumen normal.** Fuiste un martes tranquilo; el problema es el lunes a la mañana.
- **Algunas actividades ocurren a horarios incómodos**, y coordinar la agenda del analista con ellas es un problema en sí mismo.
- **Las tareas observadas sufren interrupciones.** No ves el flujo limpio.
- **Las tareas no siempre se hacen como las viste.** Observaste cómo se procesan varios pedidos y creés haber visto el procedimiento; pero eran pedidos regulares. Si alguno hubiera sido especial (un artículo que no se tiene en stock), habrías visto otro procedimiento distinto.
- **Si la gente venía violando los procedimientos, mientras la mirás puede hacerlos bien.** En otras palabras: **la gente te deja ver lo que quiere que veas.**

Fijate que las dos primeras y la última son, exactamente, el costo de la observación **intrusiva** (§2): existen porque el observado sabe.

> **Para el parcial, si te preguntan:** *Mencioná ventajas y desventajas de la observación.*
> Ventajas: datos altamente confiables (sirve para validar lo obtenido por otras técnicas), el analista ve exactamente lo que se hace y detecta tareas omitidas o mal descriptas, obtiene datos del entorno físico, es relativamente barata y permite mediciones de trabajo. Desventajas: la gente actúa distinto al saberse observada (efecto Hawthorne), lo observado puede no ser representativo en dificultad o volumen, hay problemas de horarios e interrupciones, las tareas no siempre se hacen como se vieron, y quien violaba procedimientos puede cumplirlos mientras lo mirás.

---

## 5. 🟡 Cómo se prepara y cómo se conduce

¿Cómo se observa? ¿Llegás al lugar y anotás todo lo que ves? No. **Antes hay mucha preparación.**

### 5.1 Antes de ir

Tenés que decidir **cómo vas a capturar los datos**. Preguntas que te hacés en el escritorio, no en el lugar:

- ¿Hacen falta formularios especiales para registrar rápido lo que veo?
- ¿A las personas les va a molestar que alguien las mire y anote?
- ¿Cuáles son los períodos **bajos, normales y pico** de la tarea que quiero observar?
- ¿Cuál es el momento ideal para observar este aspecto en particular?

La regla de orden: **observá primero con carga de trabajo normal.** Después, observá en los picos, para medir los efectos del volumen. En el caso de estacionamientos: primero un martes a media mañana para entender el procedimiento del encargado; después un lunes a las 8 para ver cuánto se degrada cuando entran veinte autos seguidos, y qué fechas del año saturan.

También conviene obtener **muestras de los documentos o formularios** que usan las personas observadas — son los mismos que pediste en la Técnica 1, ahora vistos en uso.

### 5.2 Las guías para observar

La observación efectiva es difícil de ejecutar; la experiencia es la mejor maestra. Pero estas guías ayudan:

1. Determiná **quién, qué, dónde, cuándo, por qué y cómo** de la observación.
2. **Obtené permiso** de los supervisores o gerentes correspondientes.
3. **Informá a las personas que vas a observar** cuál es el propósito.
4. Mantené **bajo perfil**.
5. Tomá notas **durante** o **inmediatamente después**.
6. **Revisá las notas** con las personas apropiadas.
7. **No interrumpas** a la gente mientras trabaja.
8. No te enfoques en actividades triviales.
9. **No hagas suposiciones.**

Los puntos 2 y 3 definen una observación **intrusiva**: pediste permiso y avisaste. Es la forma en que se hace en un relevamiento profesional; el precio (§4) se paga con el punto 4 y con la regla de observar primero en carga normal.

### 5.3 🟡 Muestreo de trabajo

La fórmula de tamaño de muestra que viste para documentos (Parte 1, §6.5) también sirve para la observación. Acá se llama **muestreo de trabajo** (*work sampling*).

**Muestreo de trabajo** es la técnica que consiste en un **gran número de observaciones tomadas a intervalos aleatorios**.

Es menos amenazante para la gente que una observación continua, porque no estás ahí todo el tiempo. Cómo se hace:

```text
 1. Predefinir las operaciones a observar     ("cobrar", "anotar en cuaderno",
                                                "buscar lugar", "atender consulta"…)
 2. Calcular el tamaño de muestra              (misma fórmula que para documentos)
 3. Hacer esa cantidad de observaciones        a distintas horas del día, al azar
 4. Contar cuántas veces aparece cada          → cómo distribuye su tiempo
    operación en el total                        cada empleado
```

Si de 68 observaciones aleatorias, en 30 el encargado estaba anotando a mano en el cuaderno, ya tenés un dato cuantitativo de dónde se va el tiempo — y un argumento para el sistema que viene.

### 5.4 🟡 Vivir el sistema

Hay una forma particular de observación en la que el analista **hace el rol del usuario** por un tiempo corto: **vivir el sistema** (*living the system*).

Es una de las maneras más efectivas de aprender sobre los problemas y requisitos. Al ponerte en los zapatos del usuario, entendés rápido qué experimenta y qué tiene que hacer para cumplir su tarea. Es educación de primera mano sobre los procesos y funciones del negocio, y sobre sus problemas y desafíos.

En el caso: pasar una tarde en la garita cobrando y anotando. Nada te va a explicar mejor por qué el sistema manual "no da abasto" que anotar el patente número cuarenta con una fila de autos esperando.

> **Para el parcial, si te preguntan:** *¿Qué es el muestreo de trabajo?*
> Es una técnica de observación que consiste en un gran número de observaciones tomadas a intervalos aleatorios. Se predefinen las operaciones a observar, se calcula el tamaño de muestra, se observa al azar a distintas horas y se cuentan las ocurrencias de cada operación. Es menos amenazante que la observación continua.

> **Para el parcial, si te preguntan:** *¿En qué orden conviene observar?*
> Primero con carga de trabajo normal, para entender el procedimiento; después en períodos pico, para medir los efectos del volumen.

---

## 6. ✅ Checkpoint — Parte 2

Sin respuestas. Las respuestas van al complemento.

1. ¿En qué dos situaciones la observación es especialmente útil?
2. Definí observación intrusiva y no intrusiva. ¿Qué desventajas de la técnica aparecen solo en la intrusiva?
3. Contá la Paradoja del Ferrocarril en cinco líneas y decí cuáles son sus dos lecciones.
4. En la paradoja, ¿qué técnica hubiera respondido la pregunta real? Justificá.
5. ¿Por qué se dice que la observación sirve para *validar* lo que obtuviste con otras técnicas?
6. ¿Qué es el efecto Hawthorne y qué desventaja de la observación explica?
7. "La gente te deja ver lo que quiere que veas." ¿A qué desventaja corresponde y cómo la mitigarías con las guías de §5.2?
8. ¿Por qué se observa primero en carga normal y recién después en pico?
9. Describí el procedimiento del muestreo de trabajo y decí qué obtenés al final.
10. En el caso de estacionamientos, ¿qué observarías, a quién, cuándo, y qué dato cuantitativo esperás sacar? Justificá por qué observación y no entrevista para ese dato.

## Qué viene en la Parte 3

Cuestionarios: la técnica para cuando son muchos. Qué son, cuándo conviene y cuándo no, los dos formatos de pregunta y los tres tipos de pregunta cerrada, cómo se diseña uno paso a paso — y por qué el cuestionario va **después** de la entrevista y no antes.

---

**FIN DE LA PARTE 2 — Apunte Maestro clase03 · Técnicas de Elicitación**
