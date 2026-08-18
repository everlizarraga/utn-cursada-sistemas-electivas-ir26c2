# Lectura en español — Cap. 11 · Parte 2: Los estudios y cómo convivir con la ambigüedad

> **Origen.** Capítulo 11, secciones 11.4.3 a 11.7, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Erik Kamsties**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1.** Se asumen conocidos los dos tipos de ambigüedad, los cuatro dominios y los cuatro destinos de un defecto.

---

## Lo que hay acá

Dos estudios empíricos con resultados que valen, y después **la sección más práctica de todo el libro**: cuatro estrategias concretas para reducir la ambigüedad al escribir. Esa última sección la podés aplicar en tu próximo entregable sin más.

---

## 1. El estudio de formalización 🔴

### La pregunta

¿Qué pasa con las ambigüedades **cuando alguien toma requisitos informales y construye con ellos un modelo formal**? ¿Se detectan en el camino, o pasan de largo?

### El diseño 🟢

**El material:** un documento de requisitos de unas nueve páginas sobre un producto de electrónica de consumo — un juguete electrónico. Contenía **42 requisitos textuales** y, sobre todo:

```
   57 defectos conocidos:
     38 ambigüedades
     13 defectos de incompletitud
      6 conflictos
```

**Un detalle metodológico que importa:**

> **Esos defectos NO se sembraron después de escribir el documento; fueron resultado de escribirlo.** Nos apoyamos en la observación de que **las primeras versiones de un documento de requisitos contienen montones de defectos aunque se escriban con cuidado.**

**Los participantes:** diecinueve estudiantes de informática de tercer año o superior, de dos universidades, trabajando en **equipos de dos o tres**. Cada equipo hizo la misma tarea —construir un modelo de requisitos— **pero usando un lenguaje de especificación distinto** (siete lenguajes en total, entre ellos UML).

**Y la variable clave del estudio, casi por accidente:**

> **Hubo una diferencia en la participación del cliente entre las dos universidades.** En una, **el cliente estuvo involucrado desde el comienzo** del proceso de formalización. En la otra, **el cliente se involucró solo al final**, cuando el modelo terminado se evaluaba en una entrevista.

### La hipótesis 🔴

Los autores esperaban que **no hubiera diferencias entre los lenguajes**, pero sí **entre los tipos de defecto**. El razonamiento:

> **Un lenguaje de especificación obliga al ingeniero a ser preciso** — es decir, a resolver las ambigüedades antes de crear el modelo. Así, **las ambigüedades podrían detectarse durante la formalización, pero de todos modos volverse enunciados inequívocamente correctos o inequívocamente incorrectos.**
>
> Por otro lado, **la estructura que el lenguaje impone ayuda a detectar inconsistencias e incompletitud.**

### Los resultados 🔴🔴

#### Resultado 1 — Formalizar NO detecta ambigüedades

> **Un equipo reportó en promedio el 14 % de las ambigüedades conocidas, pero el 39 % de los defectos de incompletitud conocidos.**

Y la conclusión:

> **Este resultado es notable. Muestra que las ambigüedades NO SE DETECTAN por el mero hecho de formalizar los requisitos informales. Si el ingeniero no es consciente de una ambigüedad mientras desarrolla el modelo, el lenguaje de especificación NO AYUDA a detectarla.**
>
> En cambio, **el lenguaje sí parece ayudar a detectar defectos de incompletitud y conflictos**, porque se reportaron con más frecuencia de lo esperado.

#### Resultado 2 — Las ambigüedades se resuelven sin darse cuenta 🔴

> **Un equipo resolvió en promedio el 57 % de las ambigüedades conocidas, pero solo el 16 % de los defectos de incompletitud, SIN PREGUNTARLE AL CLIENTE.**
>
> **Durante las entrevistas finales se hizo evidente que los equipos a menudo NO RECONOCÍAN LAS AMBIGÜEDADES COMO TALES.** Concluimos entonces que **las ambigüedades se remueven inconscientemente con más frecuencia que otros tipos de defecto.**

Y la advertencia:

> **La desambiguación inconsciente es un problema serio, porque los supuestos implícitos tienen más probabilidad de estar equivocados cuando el sistema es más complejo** que en nuestro estudio.

#### Resultado 3 — Las ambigüedades se transforman, no se reenvían 🔴

Este es el resultado central del capítulo:

| Tipo de defecto | Reenviados | Transformados |
|---|---|---|
| **Incompletitud** | **21-31 %** | **4-13 %** |
| **Ambigüedades** | **8-9 %** | **20-37 %** |

**Los dos tipos de defecto se comportan al revés uno del otro:**

```
   INCOMPLETITUD ─► si no se detecta, SE REENVÍA
                    (sigue estando, igual, visible)

   AMBIGÜEDAD ────► si no se detecta, SE TRANSFORMA
                    (se malinterpreta y se vuelve
                     un enunciado INCORRECTO)
```

> **Este comportamiento de las ambigüedades es un problema serio, ya que semejante malinterpretación puede pasar desapercibida por la reticencia de los clientes a leer requisitos escritos en lenguaje artificial. Las ambigüedades, si se notan, necesitan clarificación INMEDIATA. Si no, el número de malinterpretaciones crece.**

#### Resultado 4 — El efecto de la participación del cliente 🔴🔴

Y este es el hallazgo más accionable de todo el capítulo:

| | Ambigüedades **removidas** | Ambigüedades **transformadas** (mal resueltas) |
|---|---|---|
| **Cliente involucrado desde el principio** | **72 %** | **20 %** |
| **Cliente involucrado solo al final** | **55 %** | **37 %** |

> **Los equipos sin acceso al cliente resolvieron MAL el doble de ambigüedades** que los equipos que lo tenían disponible desde el principio.

Y un detalle del análisis que lo refuerza:

> Analizamos las ambigüedades removidas por los dos grupos. **Cada ambigüedad reportada y removida por un equipo con cliente fue también reconocida y removida por algún equipo sin cliente. La diferencia está en la FRECUENCIA**: más equipos pudieron remover una ambigüedad porque tenían acceso al cliente.
>
> **Cualquier ambigüedad que un equipo remueve sin reportarla puede ser malinterpretada inconscientemente por otro equipo, y puede generar una pregunta en un tercero. Si esa pregunta no se responde, el número de ambigüedades transformadas crece.**

> ⚠️ **Cruce con la cátedra — esto es directamente aplicable a tu TP.** El dato es contundente: **tener a quién preguntarle, y preguntarle durante el trabajo y no al final, reduce a la mitad los errores de interpretación.**
>
> En tu materia el equivalente del "cliente" son los docentes y el foro de consultas. Y hay un detalle del cronograma que se vuelve relevante: **el foro de consultas responde típicamente en la clase siguiente.** Eso significa que una duda que surge el viernes se responde el jueves — pero **el TP se entrega el miércoles**. La ventana está apretada.
>
> La lección operativa: **las dudas de interpretación hay que levantarlas apenas aparecen, no la noche anterior a entregar.** Cada día que pasa con una ambigüedad sin resolver es un día en que alguien del equipo la resuelve por su cuenta, sin avisar, y probablemente distinto de como la resolvió otro.

---

## 2. El estudio de inspección 🔴

### La motivación

> **La sección anterior ilustró que la ambigüedad es inevitable y que no podemos confiar en la formalización para hacer aflorar todas las ambigüedades. Por lo tanto, necesitamos una técnica para detectarlas ANTES de que se desarrollen los requisitos formales.**

Y una condición:

> **Las ambigüedades dependen del contexto: una técnica efectiva debe estar adaptada a un dominio de aplicación particular.**

### La lista de verificación de ambigüedad 🔴

Los tipos identificados en la Parte 1 **se mapean fácilmente a una lista de verificación**. La recomendación de los autores: **crear una lista separada para ambigüedad y poner ahí los tipos importantes de ambigüedad de ingeniería.**

Esta es la lista que proponen:

| Ítem | Qué preguntar |
|---|---|
| **Ambigüedad léxica** | **¿Alguna palabra del requisito tiene varios significados?** Chequear homonimia y polisemia. Tener presente que la ambigüedad léxica surge en particular **del uso concreto de la palabra en el contexto de la IR** — en el documento, el dominio de aplicación o el dominio del sistema |
| **Polisemia sistemática** | **(1) Objeto-clase:** ¿una palabra puede referirse a una clase de objetos o solo a un objeto particular de esa clase? · **(2) Proceso-producto:** ¿puede referirse a un proceso o al producto de ese proceso? · **(3) Volátil-persistente:** ¿refiere a una propiedad volátil o a una persistente del objeto? |
| **Ambigüedad referencial** | **¿Alguna referencia del requisito puede apuntar a más de un elemento** introducido antes en la oración o en una oración previa? Incluye **pronombres** (*eso*), **frases nominales definidas** (*los caminos*) y **algunas elipsis** (*Si A… Si B… Si no…*) |
| **Ambigüedad de dominio** | **¿Es ambiguo el requisito respecto de lo que se sabe del dominio de aplicación o de desarrollo?** |

> ⚠️ **Cruce con la cátedra.** Esta tabla es **una rúbrica de revisión lista para usar**. Cuatro preguntas que se corren sobre cualquier entregable antes de mandarlo, y que atacan cosas distintas de las que ataca la búsqueda de frases débiles del capítulo 8.
>
> Las dos herramientas se complementan: **el capítulo 8 te dice qué palabras no usar** (*si es posible, adecuado, rápido*); **este te dice qué preguntarle a las palabras que sí usaste.**

### Por qué la lista no alcanza 🔴

> **Las listas de verificación dan apoyo para detectar ambigüedades, pero hay una cantidad de tipos distintos y sutiles, y no todos entran en una lista efectiva.**

Por eso **se usa lectura basada en escenarios además de la lista**. La idea de la lectura por escenarios:

> Proveerle al inspector **un escenario operativo, que le exige primero CREAR UNA ABSTRACCIÓN del producto** —del documento de requisitos, en este caso— **y después responder preguntas analizando esa abstracción**, con un énfasis o rol particular.

El ejemplo genérico: **el escenario le pide al inspector que cree casos de prueba como abstracción del documento**, y una pregunta podría ser *"¿tenés toda la información necesaria para desarrollar un caso de prueba?"* Si falta información, **puede haber detectado un defecto.**

> Notá que es la misma lógica que viste dos veces: la **lectura basada en perspectivas** del capítulo 8, y el **test de la verificabilidad** (si no podés escribir el caso de prueba, el requisito está mal). **La técnica general es: no leas el documento — hacé algo con él, y fijate dónde te trabás.**

### La técnica concreta 🟢

La abstracción que eligieron es una **especificación de caja negra**, por su **simplicidad conceptual y su falta de estados**:

> La identificación de estados útiles **es una tarea no trivial que lleva tiempo; las especificaciones de caja negra permiten posponerla.**

> **Una especificación de caja negra es una vista completamente externa del sistema: el comportamiento se describe asignándole una RESPUESTA a cada HISTORIA DE ESTÍMULOS posible.**

La tabla que se construye tiene cinco columnas:

| Columna | Qué contiene |
|---|---|
| **Etiqueta** | Identificador único de la transición, **para trazabilidad hacia adelante** |
| **Estímulo** | Una entrada particular al sistema |
| **Respuesta** | La salida del sistema cuando ocurre ese estímulo y la condición es verdadera |
| **Condición** | **Las condiciones históricas** bajo las cuales se genera la respuesta — una historia particular de estímulos |
| **Traza** | **Para trazabilidad hacia atrás**: el identificador del requisito informal del que se derivó la transición |

Y una distinción útil sobre las respuestas:

```
   ACCIÓN     ──► instantánea
   ACTIVIDAD  ──► arranca cuando ocurre el estímulo y
                  termina sola o cuando ocurre la
                  respuesta siguiente sobre ese objeto,
                  lo que pase primero
```

### Las preguntas del escenario 🔴

Esta es la parte transferible. Al construir la tabla, para cada requisito se pregunta:

**Sobre el ESTÍMULO — ¿puede interpretarse de varias maneras?** Puede pasar cuando:

```
   · la frase describe un PERÍODO DE TIEMPO, no un instante
   · se usan cuantificadores, negaciones o conectivos
     lógicos (y, o) para describir una condición compleja
   · el estímulo se describe RELATIVO A OTRO estímulo
     (después de, antes de) y se referencia más de uno
   · el nombre del estímulo es léxicamente ambiguo y
     denota más de un estímulo introducido antes
```

**Sobre la RESPUESTA — ¿puede interpretarse de varias maneras?** Puede pasar cuando:

```
   · una frase verbal describe una respuesta que puede
     interpretarse como ejecutada UNA VEZ (una acción)
     o COMO ACTIVIDAD hasta la respuesta siguiente
   · el nombre de la respuesta es léxicamente ambiguo
```

**Sobre la CONDICIÓN — ¿puede interpretarse de varias maneras?** Puede pasar cuando:

```
   · pueden derivarse varias condiciones históricas
     por GENERALIDAD o VAGUEDAD
   · se usan cuantificadores, negaciones o conectivos
     para una condición histórica compleja
   · la condición refiere ambiguamente a condiciones
     descritas en OTROS requisitos
```

**Y un segundo paso, de chequeo:** comparar el documento con la tabla construida, asegurándose de haber mapeado todos los requisitos. Después preguntar:

```
   · ¿Hay requisitos que ahora interpretás DISTINTO,
     después de haber construido la tabla?
   · ¿Hay dos transiciones que NO SON DISJUNTAS?
     Si las hay, chequear si los requisitos admiten
     varias interpretaciones:
       (1) propiedades del dominio impiden que ambas
           condiciones sean verdaderas a la vez
       (2) los requisitos describen comportamiento
           NO DETERMINISTA: ambas transiciones pueden ocurrir
       (3) si ambas condiciones son verdaderas,
           AMBAS respuestas son deseadas
```

> ⚠️ **Cruce con la cátedra.** Dos cosas robables sin necesidad de construir tablas de caja negra:
>
> **1. La primera pregunta del paso 2** —*"¿hay requisitos que ahora interpretás distinto después de haber hecho el modelo?"*— es el mejor detector de ambigüedad de bajo costo que hay en el capítulo. **Construir el modelo cambia lo que entendés del texto**, y ese cambio es exactamente donde estaba la ambigüedad. Vale para casos de uso: después de diagramar, releé el enunciado y fijate si ahora dice otra cosa.
>
> **2. "¿Es un período o un instante?"** es una pregunta que encuentra ambigüedades reales todo el tiempo. *"Cuando el usuario está conectado"*, *"mientras la reserva esté vigente"*, *"al finalizar el día"* — todas admiten lectura de instante y de intervalo.

### Los resultados de la inspección 🔴

**El diseño:** dieciocho estudiantes, seis equipos de tres. Cada uno inspeccionó el documento entero. **La inspección duró 90 minutos.**

**Los números:**

| | Falsos positivos | Defectos | Ambigüedades | Incompletitud | Conflictos |
|---|---:|---:|---:|---:|---:|
| **Individual** | 7,8 | 7,6 | **5,1** | 2,4 | 0,1 |
| **Equipo (3 personas)** | 17,2 | 17,9 | **12,2** | 5,5 | 0,2 |
| **Los 18 juntos** | — | 40 de 57 | **27 de 38** | 12 de 13 | 1 de 6 |

**Los tres hallazgos:**

**1. Encontraron defectos que el estudio anterior no había visto.** La serie de experimentos **llevó a detectar 27 defectos adicionales, la mayoría ambigüedades.** Los autores se vieron **obligados a aceptar todo reclamo de ambigüedad que no fuera espurio**, si efectivamente había más de una interpretación posible — **aunque ellos, los autores, supieran cuál era la correcta.**

**2. El equipo funciona mejor que el individuo.**

> **Un equipo de tres revisores pudo detectar 12,2 ambigüedades, mientras un revisor solo detectó 5,1. Es decir, los equipos parecen ser útiles al buscar ambigüedades.**

**3. Pero ni con dieciocho personas se encuentran todas.**

> **Ni siquiera 18 revisores fueron capaces de encontrar las 38 ambigüedades: encontraron solo 27.**

Y una nota sobre el alcance de la técnica: **parece útil también para identificar incompletitud, pero inefectiva para detectar conflictos** — probablemente por la tabla de caja negra, que facilita ver ciertos tipos de incompletitud.

---

## 3. El cruce de los dos estudios 🔴

Acá viene la conclusión que ordena todo.

### El planteo

> Los resultados indican que **no podemos esperar detectar todas las ambigüedades con recursos realistas.** El documento tenía 38; un equipo de tres revisores que dedique 4,5 horas en total puede esperar detectar 12,2.
>
> **Sin embargo, NO HACE FALTA detectarlas todas: el estudio de formalización mostró que el 72 % de las ambigüedades se interpretaron correctamente.** La mayoría del 28 % restante se malinterpretó.

**La pregunta que sigue es la buena:**

> **¿Puede la inspección agregar algo a la formalización? Es decir: ¿son las técnicas de inspección capaces de detectar justamente los defectos que TIENDEN A MALINTERPRETARSE?**

### El resultado 🔴

Cruzaron los datos de los dos estudios. Dividieron las 38 ambigüedades en dos grupos: las **"nunca malinterpretadas"** (interpretadas correctamente por todos los equipos) y las **"malinterpretables"** (malinterpretadas por al menos un equipo).

| Promedio de ambigüedades | Detectadas por el equipo de inspección | No detectadas | Total |
|---|---:|---:|---:|
| **Interpretadas correctamente** por los especificadores | 2,5 | 24,8 | 27,3 |
| **Efectivamente malinterpretadas** por los especificadores | **9,7** | **1,0** | 10,7 |
| **Total** | 12,2 | 25,8 | 38 |

**Leé la fila del medio.** De las 10,7 ambigüedades que efectivamente se malinterpretaron, **el equipo de inspección detectó 9,7**. Es decir:

> **Hasta el 91 % de las ambigüedades que los especificadores efectivamente malinterpretaron podrían haber sido detectadas por los inspectores.**

> ⚠️ **Cruce con la cátedra — este es el resultado más importante del capítulo.** La técnica **no encuentra todas las ambigüedades: encuentra las que importan.**
>
> Encuentra el 32 % del total (12,2 de 38), lo cual suena flojo. Pero de las que **efectivamente iban a causar daño**, encuentra el 91 %. Las que se le escapan son, en su enorme mayoría, **ambigüedades que la gente igual iba a interpretar bien**.
>
> Y ahí está la lección de fondo: **la meta no es escribir un documento sin ninguna ambigüedad posible** —eso es inalcanzable y el propio capítulo lo dice. **La meta es que no queden ambigüedades que se vayan a resolver mal.**

---

## 4. Cómo convivir con la ambigüedad 🔴🔴

Esta sección es la más práctica del capítulo y probablemente del libro. Cuatro estrategias.

### 4.1 Aumentar la precisión del lenguaje natural 🔴

**Glosarios, guías de estilo, patrones de oración y lenguajes controlados** aumentan la precisión y reducen la ambigüedad.

#### El glosario

> **Un glosario o diccionario define los términos y frases importantes usados en un documento de requisitos. Así, ayuda a evitar la ambigüedad léxica.**
>
> **Requiere un esfuerzo considerable crearlo y validarlo, pero el esfuerzo se paga, porque puede reutilizarse en proyectos futuros del mismo dominio de aplicación.**

> ⚠️ **Cruce con la cátedra.** Acá está el glosario listado como **la primera contramedida contra la ambigüedad**, con su costo reconocido y su justificación económica. Es el mismo argumento que viste desde otros ángulos: en el capítulo 8 (definir todos los términos relevantes es parte de la **completitud**), en el capítulo 10 (las abstracciones del dominio se representan mediante **conjuntos de términos**) y en el capítulo 6 (cambiar el vocabulario del dominio genera cambios grandes: **factor de impacto M3**).
>
> Cuatro capítulos distintos, escritos por equipos distintos, llegando al mismo lugar. **Si te preguntan por qué se construye un léxico del dominio, tenés cuatro respuestas independientes.**

#### Las guías de estilo y los patrones de oración

**Una guía de estilo ayuda al autor a evitar ambigüedades.** Y los **patrones de oración** se propusieron **para darle al autor de requisitos apoyo al articularlos** — una estructura fija donde encajar lo que hay que decir.

#### El lenguaje controlado

> **Un lenguaje controlado es un subconjunto precisamente definido del lenguaje natural, para uso en entornos específicos. La ambigüedad inherente se reduce mediante una gramática restringida y un vocabulario fijo.**

### 4.2 Proveer más información de contexto 🔴

La cita con que abren la estrategia vale por sí sola:

> **"El contexto le da significado a las descripciones anclándolas en la realidad."**

Y los mecanismos concretos, cada uno con su función:

| Mecanismo | Qué aporta |
|---|---|
| **Comentario** | **Explica el trasfondo** de un requisito |
| **Justificación** (*rationale*) | Describe **POR QUÉ hace falta** el requisito |
| **Criterio de ajuste** (*fit criterion*) | **Describe una condición que el producto debe cumplir para satisfacer el requisito.** Cada criterio de ajuste **provee información contextual y deja menos lugar a la interpretación** |
| **Caso de prueba** | **Una forma más elaborada de criterio de ajuste**: describe explícitamente una entrada posible y su salida esperada |
| **Requisito inverso** | **Describe funcionalidad que el producto NO realiza** |
| **Información de trazabilidad** | **Las dependencias entre requisitos ayudan a desambiguar**, si los vínculos identifican requisitos estrechamente relacionados que dan suficiente contexto |

**Y una advertencia sobre el requisito inverso:**

> **Los requisitos inversos se usan mal a menudo para expresar requisitos no funcionales** — por ejemplo, *"el sistema no debe perder datos del usuario"*, que en realidad **es un requisito de confiabilidad**.
>
> **En su esencia, un requisito inverso DESCARTA INTERPRETACIONES POSIBLES de uno o más requisitos funcionales.**

> ⚠️ **Cruce con la cátedra — dos cosas muy usables.**
>
> **1. El criterio de ajuste** es la herramienta más directa de esta lista: **agregarle a cada requisito la condición concreta que lo satisface** cierra la puerta a interpretaciones. Es prácticamente lo mismo que el test de la verificabilidad del capítulo 8, pero como parte del entregable en vez de como chequeo.
>
> **2. El requisito inverso, bien entendido,** es una técnica que casi nadie usa: **decir explícitamente qué NO hace el sistema.** Suena redundante y no lo es — descarta lecturas. *"El sistema registra el pedido pero NO reserva el stock"* elimina de un plumazo una interpretación que iba a aparecer sí o sí.

### 4.3 Establecer convenciones de interpretación 🟡

> Un ejemplo podría ser: *"las reglas de la lógica booleana se aplican a los enunciados lógicos de los requisitos"*.
>
> **Las convenciones deben ser claras tanto para quien escribe como para quien lee. Si no, pueden ocurrir malinterpretaciones.**

### 4.4 Herramientas 🟡

Hay dos clases:

- **Basadas en analizador sintáctico:** intentan analizar las oraciones para identificar sus partes componentes. **La existencia de más de un análisis posible es señal de una ambigüedad.**
- **De coincidencia de patrones:** buscan **instancias de un conjunto dado de palabras, frases y afinidades léxicas consideradas ambiguas.**

**Y el límite fundamental de todas:**

> **Todas las herramientas son capaces de encontrar ambigüedad lingüística, pero SON INCAPACES DE ENCONTRAR LA MAYORÍA DE LAS AMBIGÜEDADES DE INGENIERÍA.**
>
> **Es decir: las herramientas pueden usarse en una primera pasada, pero las inspecciones son inevitables para detectar las ambigüedades de ingeniería.**

---

## 5. Las dos recomendaciones finales 🔴

Basándose en los estudios, los autores hacen dos recomendaciones concretas.

### Recomendación 1 — Inspeccionar antes de formalizar

> **Como los lenguajes de especificación imponen precisión, una ambigüedad puede volverse un requisito formal inequívocamente EQUIVOCADO, que puede pasar desapercibido por la reticencia de los clientes a leer requisitos escritos en lenguaje artificial.**
>
> **Recomendamos la inspección de los requisitos informales con énfasis en las ambigüedades, para evitar estos problemas. Las inspecciones deberían apuntar a las ambigüedades de ingeniería.**
>
> **El tamaño del equipo de inspección debería ser de al menos dos, para permitirles a los inspectores INTERCAMBIAR SUS INTERPRETACIONES.**

### Recomendación 2 — El cliente participa DURANTE, no después

> **El desarrollo de modelos de requisitos a partir de requisitos informales es tarea de los ingenieros de requisitos, no de los clientes o usuarios.**
>
> **Sin embargo, recomendamos la participación de clientes y usuarios DURANTE el desarrollo de esos modelos, NO DESPUÉS, para clarificar las ambigüedades observadas lo antes posible.**

---

## 6. Conclusión del capítulo 🔴

Los autores recapitulan:

> **La ambigüedad de requisitos no se limita a ambigüedades lingüísticas simples**, como las distintas lecturas de una oración por una frase preposicional. **Este capítulo enfatizó el papel del contexto** e identificó los cuatro dominios: el documento de requisitos, el dominio de aplicación, el dominio del sistema y el dominio del desarrollo.
>
> **Las ambigüedades se reportan menos seguido, pero se resuelven inconscientemente más seguido que otros tipos de defecto. Esto es un problema serio, porque el conocimiento contextual de clientes y desarrolladores usualmente difiere.** Los supuestos implícitos **tienen probabilidad de estar equivocados cuando un sistema es más complejo** que el del estudio.
>
> **Concluimos que un ingeniero de requisitos NO DEBERÍA CONFIAR en la formalización de los requisitos informales para detectar ambigüedades.**

Y una precisión terminológica en el cierre que vale la pena:

> **Las ambigüedades no pueden considerarse defectos POTENCIALES, porque también transmiten el significado correcto — pero SON DEFECTOS REALES.** Como muestra nuestro estudio, **una cantidad considerable de ambigüedades tiende a malinterpretarse (del 20 % al 37 % según la participación del cliente). Es probable que ese número suba si el dominio es más complicado** que un simple producto de electrónica de consumo.

---

## Mapa de la Parte 2

```
   ESTUDIO 1 — FORMALIZAR
   38 ambigüedades · 13 incompletitudes · 6 conflictos

   formalizar NO detecta ambigüedades:
     14 % de las ambigüedades reportadas
     39 % de las incompletitudes reportadas

   las ambigüedades se resuelven SIN DARSE CUENTA:
     57 % auto-resueltas (vs 16 % de incompletitudes)

   y el comportamiento opuesto:
     INCOMPLETITUD ─► se REENVÍA (21-31 %)
     AMBIGÜEDAD ────► se TRANSFORMA (20-37 %)

   ══► CLIENTE PRESENTE DESDE EL PRINCIPIO ◄══
     removidas 72 % · mal resueltas 20 %
   ══► CLIENTE SOLO AL FINAL ◄══
     removidas 55 % · mal resueltas 37 %
   → el doble de errores de interpretación

   ─────────────────────────────────────────────

   ESTUDIO 2 — INSPECCIONAR
   equipo de 3, 90 minutos → 12,2 de 38 ambigüedades
   uno solo → 5,1 · dieciocho personas → 27 de 38

   ══► EL CRUCE DE LOS DOS ESTUDIOS ◄══
   de las 10,7 que EFECTIVAMENTE se malinterpretaron,
   la inspección detectó 9,7 → 91 %

   la técnica no encuentra todas: ENCUENTRA LAS QUE IMPORTAN

   ─────────────────────────────────────────────

   CÓMO CONVIVIR — 4 estrategias
   1. PRECISIÓN: glosario · guía de estilo · patrones
      de oración · lenguaje controlado
   2. CONTEXTO: comentario · justificación · criterio
      de ajuste · caso de prueba · requisito inverso
      · trazabilidad
   3. CONVENCIONES de interpretación
   4. HERRAMIENTAS (solo encuentran las lingüísticas)

   RECOMENDACIONES
   · inspeccionar ANTES de formalizar, equipo de 2+
   · el cliente participa DURANTE, no después
```

---

## Preguntas para chequear que quedó

1. ¿Cuántos defectos de cada tipo tenía el documento del estudio? ¿Por qué importa que no hayan sido sembrados?
2. ¿Cuál era la hipótesis sobre lo que un lenguaje de especificación ayuda a detectar y lo que no?
3. ¿Qué porcentaje de ambigüedades y de incompletitudes reportó un equipo en promedio? ¿Qué muestra esa diferencia?
4. ¿Qué significa que las ambigüedades se "auto-resuelvan" y por qué es un problema serio?
5. Explicá la diferencia de comportamiento entre incompletitud y ambigüedad cuando no se detectan.
6. ¿Qué efecto tuvo la participación del cliente sobre las ambigüedades removidas y transformadas?
7. ¿Por qué una ambigüedad removida por un equipo sin reportarla puede aumentar los errores de otro equipo?
8. Nombrá los cuatro ítems de la lista de verificación de ambigüedad.
9. ¿Por qué las listas de verificación no alcanzan?
10. ¿En qué consiste la lectura basada en escenarios? ¿Qué se le pide al inspector que haga antes de responder preguntas?
11. ¿Por qué eligieron la especificación de caja negra como abstracción?
12. Nombrá las cinco columnas de la tabla y para qué sirven las dos de trazabilidad.
13. Diferenciá una acción de una actividad.
14. Nombrá tres situaciones en que un estímulo puede interpretarse de varias maneras.
15. ¿Por qué "¿hay requisitos que ahora interpretás distinto?" es una buena pregunta de detección?
16. ¿Cuántas ambigüedades detecta un equipo de tres frente a un revisor solo? ¿Y dieciocho personas?
17. ¿Por qué la técnica es inefectiva para detectar conflictos?
18. Del cruce de los dos estudios: ¿qué porcentaje de las ambigüedades efectivamente malinterpretadas detectó la inspección? ¿Por qué ese número importa más que el 32 % del total?
19. Nombrá las cuatro estrategias para convivir con la ambigüedad.
20. ¿Qué evita un glosario y cómo se justifica su costo?
21. Nombrá seis mecanismos para proveer más contexto y decí qué aporta cada uno.
22. ¿Qué es un criterio de ajuste y por qué reduce la ambigüedad?
23. ¿Qué es un requisito inverso, cómo se usa mal, y cuál es su función real?
24. ¿Cuál es el límite fundamental de todas las herramientas automáticas?
25. ¿Por qué el equipo de inspección debe tener al menos dos personas?
26. ¿Por qué las ambigüedades son defectos reales y no potenciales?

---

**FIN DEL CAPÍTULO 11 — PARTE 2**

**FIN DEL CAPÍTULO 11**

*Sigue el capítulo 12: soporte a la decisión en ingeniería de requisitos, en 2 partes.*
