# Lectura en español — Cap. 11 · Parte 1: Qué es la ambigüedad de un requisito

> **Origen.** Capítulo 11, secciones 11.1 a 11.4.2, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Erik Kamsties**, Universidad de Duisburg-Essen, Alemania.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.

---

## Leé este capítulo entero

De los veinte del libro, **este es el que más directamente explica el criterio con el que te corrigen**. La cátedra penaliza la ambigüedad y corrige con el léxico de *no ambiguo, sin doble interpretación*. Este capítulo es lo único en todo el libro que **desarma la ambigüedad en tipos, muestra por qué es más profunda de lo que parece, y da técnicas concretas para detectarla.**

Y trae un hallazgo empírico que conviene tener presente desde ahora:

> **La ambigüedad es el único tipo de defecto que la gente RESUELVE SIN DARSE CUENTA de que existía.** Los defectos de incompletitud y los conflictos, si no se detectan, pasan de largo tal cual. **Las ambigüedades, si no se detectan, se malinterpretan** — alguien elige una lectura, sigue adelante convencido, y nadie se entera.

---

## 1. El problema 🔴

### El estado de la práctica

> **En la ingeniería de requisitos industrial, el lenguaje natural es la representación más frecuentemente usada.** Los diagramas y otras representaciones semi-formales suelen usarse como complemento. **Las especificaciones totalmente formalizadas son raras.**

Un relevamiento en línea da los números:

```
   79 %  lenguaje natural común
   16 %  lenguaje natural estructurado
    5 %  lenguaje formalizado
```

### Por qué la ambigüedad es peligrosa 🔴

El párrafo central del capítulo, y conviene leerlo despacio:

> **Los interesados a menudo NI SIQUIERA SON CONSCIENTES de que hay una ambigüedad en un requisito** — es decir, la ambigüedad **no es intencional**.
>
> **Cada interesado obtiene de la lectura un entendimiento que difiere del de los demás, SIN RECONOCER ESA DIFERENCIA.**
>
> En consecuencia, **los desarrolladores diseñan e implementan un sistema que no se comporta como los usuarios pretendían — pero los desarrolladores creen honestamente que siguieron los requisitos.**
>
> Además, **los componentes fallan al interactuar correctamente**, porque el mismo requisito se asignó a componentes distintos **y los distintos desarrolladores lo interpretaron de manera diferente.**

> ⚠️ **Cruce con la cátedra.** Fijate en lo que hace peligrosa a la ambigüedad: **no produce discusión.** Un requisito contradictorio se discute; un requisito incompleto genera preguntas. Un requisito ambiguo **produce acuerdo aparente** — todos creen haber entendido lo mismo, nadie pregunta nada, y el problema aparece meses después cuando las piezas no encajan.
>
> Es exactamente el mismo mecanismo que la **brecha cultural** del capítulo 2: *"el hecho de que esta situación exista suele pasar desapercibido, a menos que se le preste atención específica al problema."*

**Una aclaración de alcance:** la ambigüedad **también es una característica del lenguaje natural** y puede usarse intencionalmente —por ejemplo, **para posponer decisiones que se consideran de diseño**. El capítulo se enfoca en la **no intencional**.

---

## 2. La distinción central: lingüística contra de ingeniería 🔴🔴

Esta es la contribución principal del capítulo, y es lo que hay que llevarse.

| | **Ambigüedad lingüística** | **Ambigüedad de ingeniería de software** |
|---|---|---|
| **Depende del contexto** | **No** — es independiente del contexto | **Sí** |
| **Quién la puede ver** | **Cualquier lector con oído para el idioma** | **Solo un lector que conozca el dominio del proyecto** |

### El ejemplo de ambigüedad lingüística

```
   "El producto debe mostrar el clima para las
    próximas 24 horas."

   La frase "para las próximas 24 horas" puede
   engancharse al VERBO (mostrar) o al SUSTANTIVO (clima):

   → el producto debe mostrar el clima ACTUAL y seguir
     haciéndolo durante las próximas 24 horas

   → el producto debe mostrar el clima PRONOSTICADO
     para las próximas 24 horas
```

### El ejemplo de ambigüedad de ingeniería 🔴

Este es el mejor ejemplo del capítulo y vale la pena en detalle. Es un requisito sobre el nivel de agua de un tanque, que varía continuamente:

```
   "Apagar las bombas si el nivel de agua permanece
    por encima de 100 metros durante más de 4 segundos."
```

**Hay cuatro interpretaciones posibles.** Apagar las bombas si, en los últimos 4 segundos, el nivel de agua…

```
   1. …PROMEDIO estuvo por encima de 100 m
   2. …MEDIANO estuvo por encima de 100 m
   3. …CUADRÁTICO MEDIO estuvo por encima de 100 m
   4. …MÍNIMO estuvo por encima de 100 m
```

**Qué pasó en la realidad:**

> **Los ingenieros de software no notaron esta ambigüedad y asumieron silenciosamente la cuarta interpretación.** Desafortunadamente, bajo esa interpretación, **con olas rápidas y considerables en el tanque, el nivel de agua puede estar peligrosamente alto sin disparar el apagado.**

Y la observación que lo cierra:

> **En general, la interpretación de la ambigüedad es en gran medida función del trasfondo del lector. Por ejemplo, en muchas otras áreas de ingeniería, la interpretación estándar sería la tercera.**

### Cuál importa más 🔴

Los autores son categóricos:

> **Las ambigüedades de ingeniería son MÁS IMPORTANTES que las lingüísticas.**

**Por qué.** Aunque una oración de requisito pueda ser ambigua por múltiples sentidos de una palabra o múltiples lecturas sintácticas, **los experimentos psicolingüísticos muestran que a menudo hay UNA LECTURA PREFERIDA una vez que se consideran la semántica y el contexto.**

Y el dato duro de sus propias investigaciones:

> **En los documentos de requisitos que investigamos, las ambigüedades de ingeniería constituyen la mayoría, mientras que las puramente lingüísticas jugaron un papel menos significativo.**
>
> **El documento usado en los estudios de este capítulo contiene 4 ambigüedades lingüísticas pero 34 de ingeniería.**

> ⚠️ **Cruce con la cátedra — esto cambia dónde hay que mirar.** La reacción instintiva ante "no seas ambiguo" es corregir la redacción: acomodar pronombres, evitar palabras con doble sentido. **Ese trabajo atiende la minoría del problema.**
>
> El grueso de la ambigüedad **no está en cómo escribiste la oración: está en lo que diste por supuesto del dominio.** El ejemplo del tanque no tiene ningún error de redacción — es una oración perfectamente clara en castellano. Es ambigua porque **no dice qué se entiende por "el nivel de agua" cuando el nivel varía todo el tiempo**.
>
> La consecuencia práctica: **la ambigüedad que te va a costar no la vas a encontrar releyendo tu texto. La vas a encontrar preguntándote qué supusiste del negocio sin decirlo.**

---

## 3. Qué se venía haciendo, y por qué no alcanza 🔴

### La solución más recomendada, y su límite

> **La solución más recomendada al problema de la ambigüedad es usar un lenguaje de especificación formal o semi-formal —como UML— en vez de lenguaje natural.** Esos lenguajes tienen una semántica más o menos bien definida, así que el grado de ambigüedad **al menos disminuye significativamente, si no se elimina.**

**Pero hay cuatro problemas:**

```
   1. NO HAY ESCAPE del lenguaje natural: los requisitos
      iniciales se escriben en lenguaje natural

   2. Aun si se pasa directamente a un lenguaje formal,
      LA AMBIGÜEDAD PUEDE GOLPEAR EN LA TRANSICIÓN

   3. Un requisito informal ambiguo termina convertido
      en un requisito formal INEQUÍVOCAMENTE CORRECTO
      O INEQUÍVOCAMENTE INCORRECTO

   4. Una malinterpretación PUEDE PASAR DESAPERCIBIDA,
      porque los expertos del dominio del cliente a menudo
      NO PUEDEN LEER el lenguaje formal lo suficientemente
      bien como para detectar un significado distinto del
      que tenían en mente
```

Y un quinto, económico: **no suele ser costo-eficiente formalizar una especificación entera.**

> ⚠️ **Cruce con la cátedra — importante.** El punto 3 es el mecanismo exacto del daño, y explica algo que parece paradójico: **formalizar puede empeorar el problema en vez de resolverlo.**
>
> Antes de formalizar, la ambigüedad es visible como tal — el texto admite dos lecturas y alguien podría notarlo. **Después de formalizar, el diagrama dice UNA cosa sola.** Si el que formalizó eligió mal, el error ya no se ve como ambigüedad: se ve como una decisión tomada. Y el cliente no puede revisarla porque no sabe leer el diagrama.
>
> Es un argumento fuerte a favor de **revisar el texto ANTES de diagramar**, no después. Y de que el diagrama vuelva al cliente acompañado de una explicación en su idioma.

### Las técnicas de inspección existentes 🟡

**La más efectiva:**

> **Entregarles los requisitos a varios interesados distintos, pedirle a cada uno una interpretación, y comparar las interpretaciones después. Si las interpretaciones difieren, los requisitos son ambiguos.**

**Su límite:** **solo es económicamente viable para conjuntos chicos de requisitos.**

**Las listas de verificación.** Existen listas detalladas de palabras ambiguas usadas a menudo en requisitos. **Ayudan a encontrar muchas ambigüedades lingüísticas, pero no abordan las de ingeniería.**

**Y una crítica muy filosa a la práctica habitual:**

> Algunas técnicas de inspección **asumen que los inspectores son capaces de detectar ambigüedades solo leyendo**; no dan ninguna guía sobre cómo encontrarlas. **Suele haber un solo ítem de la lista que pregunta: "¿es ambiguo el requisito?"**
>
> **El problema mayor de la ambigüedad es NO SER CONSCIENTE DE ELLA. Por lo tanto, simplemente preguntar si hay una ambigüedad no ayuda mucho.**

**Las herramientas de procesamiento de lenguaje natural** también pueden detectarlas, pero con dificultades: a veces **requieren restringir la sintaxis**; a veces **requieren programación experta** para poder analizar texto arbitrario; y **tienden a levantar muchas más ambigüedades de las que un humano percibe realmente.**

---

## 4. La definición nueva 🔴

> **Definimos un requisito como AMBIGUO si tiene múltiples interpretaciones A PESAR DEL CONOCIMIENTO DEL CONTEXTO POR PARTE DEL LECTOR.**

**No importa** si el autor introdujo la ambigüedad sin querer pero sabe qué quiso decir, o si la introdujo a propósito para incluir todas las interpretaciones posibles.

**Y por qué el contexto es parte de la definición:**

> **Es importante tener en cuenta el contexto, porque no puede esperarse que un documento de requisitos sea autocontenido de manera tal que un lector ingenuo arbitrario pudiera entenderlo.**

> Es una definición honesta y práctica: **si no incluís el contexto, todo requisito es ambiguo** — cualquier texto admite lecturas absurdas si el lector no sabe nada del dominio. La ambigüedad que importa es la que persiste **aun sabiendo de qué se está hablando.**

---

## 5. La taxonomía 🔴

### 5.1 Ambigüedad lingüística 🟡

Los autores se restringen a los tipos que la literatura no había tratado con suficiente profundidad. **La mayoría de las ambigüedades lingüísticas no causan problemas, porque se resuelven fácilmente con los requisitos que las rodean.**

#### Polisemia y homonimia

| | Definición | Ejemplo |
|---|---|---|
| **Polisemia** | Una palabra tiene **varios significados RELACIONADOS** | *verde*: el color, atractivo, joven, vigoroso, no maduro |
| **Homonimia** | Una palabra tiene **significados NO RELACIONADOS** | *banco*: asiento, entidad financiera, conjunto de peces |

**Y cuál es peor:**

> **Las polisemias son un problema mucho mayor en los documentos de requisitos que los homónimos.** Los significados de una polisemia **están relacionados** — es decir, **hace falta información contextual más detallada para desambiguarla.**

> El razonamiento es bueno: con un homónimo, el contexto te salva casi siempre (nadie confunde el banco de la plaza con el banco donde tenés la cuenta). **Con una polisemia, los dos sentidos son vecinos, y por eso pueden convivir en la misma oración sin que salte la alarma.**

**El ejemplo del capítulo:** en un requisito sobre un juguete electrónico, la palabra que nombra al juguete **se usa tanto como nombre del dispositivo electromecánico como de la criatura simulada por ese dispositivo.** Entonces "se restablece a sus valores por defecto" puede referirse **al juguete entero o solo a la criatura.**

#### Polisemia sistemática 🔴

> **La polisemia sistemática se aplica a UNA CLASE DE PALABRAS**, no a una palabra particular.

El ejemplo que dan es la **ambigüedad volátil-persistente**, que surge cuando una palabra refiere **o bien a una propiedad volátil, o bien a una propiedad persistente de un objeto**:

```
   "Cuando el usuario presiona los botones L y R
    simultáneamente, la alarma se apaga."

   "se apaga" puede referirse a:
   → la alarma que está sonando AHORA
   → la CAPACIDAD GENERAL del sistema de emitir alarmas
```

*(Más adelante el capítulo lista otras dos polisemias sistemáticas: la ambigüedad **objeto-clase** —una palabra puede referirse a una clase de objetos o a un objeto particular de esa clase— y la **proceso-producto** —una palabra puede referirse a un proceso o al producto de ese proceso.)*

> ⚠️ **Cruce con la cátedra.** Las tres polisemias sistemáticas son un checklist corto y muy aplicable a cualquier entregable:
>
> - **¿Objeto o clase?** *"El usuario ve el pedido"* — ¿un pedido concreto o la lista de pedidos?
> - **¿Proceso o producto?** *"La facturación se archiva"* — ¿el proceso de facturar o la factura emitida?
> - **¿Volátil o persistente?** *"Se cancela la reserva"* — ¿esta reserva, o la posibilidad de reservar?
>
> Son tres preguntas que se corren rápido sobre un texto y encuentran cosas reales.

### 5.2 Ambigüedad de ingeniería: los cuatro dominios 🔴🔴

Las ambigüedades de ingeniería **surgen del contexto que hay que considerar**. Ese contexto se subdivide en cuatro dominios:

```
   1. EL DOCUMENTO DE REQUISITOS del que el requisito
      considerado forma parte

   2. EL DOMINIO DE APLICACIÓN
      el entorno organizacional y los comportamientos
      de los agentes externos

   3. EL DOMINIO DEL SISTEMA
      modelos conceptuales de los sistemas de software
      y sus comportamientos

   4. EL DOMINIO DEL DESARROLLO
      modelos conceptuales de los productos y procesos
      de desarrollo
```

#### Ambigüedad del documento de requisitos 🔴

> Ocurre si un requisito **admite varias interpretaciones respecto de lo que se sabe de OTROS REQUISITOS del documento.**
>
> **Un requisito aislado rara vez es autocontenido.** Usualmente tiene referencias implícitas o explícitas a otros requisitos. **El lector debe conocer los requisitos relacionados para entender un requisito correctamente.**

Surge de **referencias pronominales** y de **frases nominales definidas**:

```
   "El producto debe mostrar todos los caminos que se
    prevé que se congelen."

   La frase "los caminos" puede referirse a más de un
   conjunto de caminos especificado antes en el documento.
```

#### Ambigüedad del dominio de aplicación 🔴

> Ocurre si un requisito admite varias interpretaciones **respecto de lo que se sabe del dominio de aplicación.**

**El ejemplo del tanque de agua es de este tipo** — y como ya viste, **solo es observable para alguien con conocimiento del dominio de aplicación.**

#### Ambigüedad del dominio del sistema 🟡

```
   "Si el temporizador expira antes de recibir una
    indicación de desconexión, el gestor solicita la
    desconexión del transporte con un pedido de
    desconexión. El temporizador se cancela al recibir
    una indicación de desconexión."

   Es ambiguo SI LA SEGUNDA ORACIÓN forma parte o no
   del condicional de la primera.
```

*(Los autores aclaran que este caso concreto podría desambiguarse por sentido común —cancelar un temporizador ya expirado probablemente tenga poco sentido— pero que la oración ilustra bien el problema.)*

#### Ambigüedad del dominio del desarrollo 🔴

Y esta es la más sutil de las cuatro:

```
   "Las puertas del ascensor nunca se abren en un piso
    a menos que el ascensor esté detenido en ese piso."

   Queda abierto SI el enunciado es un requisito a
   implementar en el software, O SI puede asumirse
   que ya lo provee el hardware.
```

> Es decir: **el enunciado puede interpretarse como INDICATIVO o como OPTATIVO.**

Y el capítulo señala la convención que existe para resolverlo:

> **En los documentos de requisitos estadounidenses se usa a menudo la palabra *shall* para identificar requisitos —en modo optativo— reservando *will* para enunciados en modo indicativo, que serán verdaderos sobre el entorno en el futuro.**

> ⚠️ **Cruce con la cátedra — muy aprovechable.** Esta es **exactamente la distinción entre requisito y suposición** que viste en el capítulo 9 (meta / requisito / suposición), pero vista como un problema de ambigüedad:
>
> **Optativo = "esto debe pasar y el sistema tiene que garantizarlo"** → es un requisito.
> **Indicativo = "esto va a ser verdad del entorno"** → es una suposición.
>
> Y el punto clave: **si el enunciado no marca cuál de los dos es, el lector elige.** El castellano no tiene la pareja *shall/will*, pero sí tiene el problema: *"las puertas no se abren en movimiento"* no dice si el sistema lo impide o si es un hecho del hardware.
>
> **La solución práctica:** usar formulaciones que dejen claro quién es el responsable. *"El sistema debe impedir que…"* es inequívocamente optativo; *"El hardware garantiza que…"* es inequívocamente indicativo.

**Y una nota final sobre esta familia:**

> **Las ambigüedades de ingeniería son específicas del contexto. Los requisitos de un sistema de información sufren ambigüedades de ingeniería DISTINTAS de las de un sistema embebido.**

---

## 6. De dónde viene la ambigüedad 🔴

La ingeniería de requisitos puede entenderse como un proceso a lo largo de **tres dimensiones**:

```
   INICIO                              FINAL
   informal        ESPECIFICACIÓN      formal
   incompleto      (completitud)       completo
   vistas          ACUERDO             vista
   personales      (agreement)         común
                   REPRESENTACIÓN
```

> **La ambigüedad es un fenómeno transversal, que atraviesa las tres dimensiones. Es típica de las fases iniciales del proceso.**

Y de ahí salen **tres fuentes**:

| Fuente | Cómo genera ambigüedad |
|---|---|
| **Falta de completitud** | **Los requisitos incompletos pueden llevar a ambigüedad sobre qué se quiso decir. Cuanto más completos son los requisitos, menos ambiguos son** |
| **Falta de acuerdo** | **Las vistas individuales en conflicto pueden resultar en ambigüedad** — las expectativas y metas divergentes de los individuos llevan a interpretaciones distintas |
| **Representación** | **Los requisitos informales son inevitablemente ambiguos**; los formales son significativamente menos ambiguos, pero **igual dejan lugar a la ambigüedad**. Este tipo se debe a **las debilidades del lenguaje natural** —en particular su potencia para expresar conceptos técnicos— **y a la falta de uso apropiado del lenguaje** |

> ⚠️ **Cruce con la cátedra.** La primera fila establece una relación que conviene tener clara: **incompletitud y ambigüedad no son problemas independientes.** Lo que no está dicho, el lector lo completa — y ahí es donde entra la interpretación. **Un requisito incompleto se vuelve ambiguo por omisión**, aunque cada palabra que tenga esté bien elegida.

---

## 7. Los cuatro destinos de un defecto 🔴

Esta clasificación es la base del estudio empírico de la Parte 2, y vale por sí sola.

Cuando un defecto está en los requisitos informales y después se produce un modelo formal, **al defecto le puede pasar una de cuatro cosas**:

| Destino | Qué pasó |
|---|---|
| **Identificado y removido** | **El defecto fue reconocido y REPORTADO AL CLIENTE**, sea al leer el requisito informal o al formalizarlo. **Con la respuesta del cliente, el defecto se elimina** |
| **Auto-resuelto** | **El defecto fue removido, pero NO SE DISCUTIÓ CON EL CLIENTE**: lo removió el especificador, por ejemplo usando su conocimiento de trasfondo |
| **Reenviado** | **El mismo defecto de los requisitos informales queda incluido en el modelo.** Por ejemplo, un requisito incompleto que no se reconoció y se volvió un enunciado incompleto en el modelo |
| **Transformado** | **Un defecto se transformó en OTRO TIPO de defecto en el modelo.** Por ejemplo: **un requisito ambiguo fue MALINTERPRETADO y se volvió un enunciado INCORRECTO** |

```
   IDENTIFICADO ─► se preguntó y se arregló ✓
   AUTO-RESUELTO ► se arregló SIN PREGUNTAR
                   (puede haber salido bien... o no)
   REENVIADO ────► sigue estando, igual que antes
   TRANSFORMADO ─► ahora es OTRA COSA, y peor:
                   ya no se ve como ambigüedad,
                   se ve como una decisión tomada
```

> ⚠️ **Cruce con la cátedra.** Los dos del medio son los peligrosos, y por razones distintas.
>
> **Auto-resuelto** suena bien pero no lo es: alguien tomó una decisión sobre el dominio **usando su propio criterio, sin consultar**, y nadie sabe que la tomó. Si acertó, bien; si no, el error queda enterrado.
>
> **Transformado** es el peor de los cuatro. **El defecto no desaparece: cambia de forma y se vuelve invisible.** Una ambigüedad transformada ya no es un texto que admite dos lecturas — es un diagrama que dice una sola cosa, la equivocada, con toda la autoridad de un artefacto formal.

---

## Mapa de la Parte 1

```
   POR QUÉ ES PELIGROSA
   nadie se da cuenta → NO PRODUCE DISCUSIÓN
   cada uno entiende algo distinto sin notar la diferencia
   los desarrolladores creen honestamente haber seguido
   los requisitos

   ─────────────────────────────────────────────

   ══► LOS DOS GRANDES TIPOS ◄══

   LINGÜÍSTICA            DE INGENIERÍA
   independiente          DEPENDE del contexto
   del contexto
   la ve cualquiera       solo la ve quien CONOCE
   con oído               EL DOMINIO
   se resuelve casi       ES LA QUE IMPORTA
   siempre sola

   en el documento estudiado: 4 lingüísticas · 34 de ing.

   ─────────────────────────────────────────────

   LINGÜÍSTICAS
   polisemia (significados RELACIONADOS) ← peor
   homonimia (significados NO relacionados)
   polisemia sistemática:
     objeto-clase · proceso-producto · volátil-persistente

   DE INGENIERÍA — los 4 dominios
   1. del DOCUMENTO ("los caminos" ¿cuáles?)
   2. de APLICACIÓN (el nivel del tanque: ¿promedio?
      ¿mediano? ¿mínimo?)
   3. del SISTEMA (¿la segunda oración está dentro del if?)
   4. del DESARROLLO (¿es requisito o es un hecho
      del entorno? optativo vs indicativo)

   ─────────────────────────────────────────────

   TRES FUENTES: falta de completitud · falta de acuerdo
   · representación

   LOS 4 DESTINOS DE UN DEFECTO
   identificado (se preguntó) · auto-resuelto (se decidió
   solo) · reenviado (sigue igual) · TRANSFORMADO
   (cambió de forma y ahora es invisible)
```

---

## Preguntas para chequear que quedó

1. ¿Qué porcentaje de los documentos de requisitos se escribe en lenguaje natural común?
2. ¿Por qué la ambigüedad no produce discusión? ¿Qué la hace distinta de una contradicción?
3. ¿Qué pasa cuando el mismo requisito ambiguo se asigna a componentes distintos?
4. Diferenciá ambigüedad lingüística de ambigüedad de ingeniería en las dos dimensiones de la tabla.
5. Explicá el ejemplo del clima y las 24 horas. ¿Por qué es lingüística?
6. Explicá el ejemplo del tanque de agua. ¿Cuántas interpretaciones hay y cuál asumieron los ingenieros? ¿Con qué consecuencia?
7. ¿Por qué las ambigüedades de ingeniería son más importantes que las lingüísticas? Dé el argumento y el dato.
8. ¿Por qué formalizar en UML no resuelve el problema? Nombrá los cuatro motivos.
9. Explicá por qué formalizar puede volver el problema *menos* visible.
10. ¿Cuál es la técnica de inspección más efectiva y cuál es su límite?
11. ¿Por qué preguntar "¿es ambiguo este requisito?" en una lista de verificación no sirve de mucho?
12. Definí requisito ambiguo según el capítulo. ¿Por qué el contexto es parte de la definición?
13. Diferenciá polisemia de homonimia. ¿Cuál es peor en requisitos y por qué?
14. ¿Qué es una polisemia sistemática? Nombrá las tres que menciona el capítulo con un ejemplo propio de cada una.
15. Nombrá los cuatro dominios de los que surgen las ambigüedades de ingeniería.
16. Dé un ejemplo de ambigüedad del documento de requisitos.
17. Explicá la ambigüedad indicativo/optativo con el ejemplo del ascensor. ¿Cómo se resuelve en inglés? ¿Cómo lo resolverías en castellano?
18. ¿Con qué distinción del capítulo 9 se conecta la ambigüedad del dominio del desarrollo?
19. Nombrá las tres fuentes de ambigüedad.
20. ¿Por qué la incompletitud genera ambigüedad?
21. Nombrá los cuatro destinos posibles de un defecto e identificá cuáles dos son los más peligrosos y por qué.

---

**FIN DEL CAPÍTULO 11 — PARTE 1**

*Sigue en la Parte 2: los dos estudios empíricos —qué le pasa a las ambigüedades cuando se formalizan los requisitos, y cuántas puede encontrar un equipo de inspección—, la técnica de lectura para detectarlas, y las recomendaciones para convivir con la ambigüedad.*
