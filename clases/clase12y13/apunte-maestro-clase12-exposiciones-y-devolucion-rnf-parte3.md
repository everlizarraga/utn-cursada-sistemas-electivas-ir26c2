# Apunte maestro — Clase 12 · Parte 3
## La devolución de los RNF del primer parcial

> **Sobre esta parte.** Es lo más evaluable de la clase. Se repasan los requisitos no funcionales (RNF) que se escribieron en el primer parcial, sobre el caso de la aplicación de recetas de pastelería: cuántos estuvieron bien, cuáles fueron los cinco errores más repetidos, cómo se corrige cada uno y qué preguntas hacerse antes de dar por terminado un RNF. Sirve para el **recuperatorio**, para la entrega de **RF y RNF del TP integrador** y para la práctica del 12/11. Cierra con la información operativa y el checkpoint de toda la clase.
>
> **De dónde venís.** Se asume lo visto sobre RF, RNF y reglas de negocio en las clases anteriores. Igual, todo lo que esta clase volvió a explicar está acá completo.

---

## 1. 🔴 El parcial en números

Se corrigieron **70 requisitos**, repartidos en 18 bloques:

| Resultado | Cantidad | Porcentaje |
|---|---|---|
| **Mal** | 42 de 70 | 60 % |
| **Mejorable** (iban por buen camino, pero no llegaron) | 13 de 70 | 19 % |
| **Bien** | 15 de 70 | 21 % |

```
[████████████████████████ Mal 60% ████████████████████████|███ Mejorable 19% ███|███ Bien 21% ███]
```

**Más de la mitad no pasó la prueba.** Los RNF fueron un punto flojo de casi todos, y por eso la cátedra les dedica esta devolución y una práctica en clase antes del segundo parcial. Los errores se analizan **sin nombres**: acá los únicos culpables son los requisitos. El objetivo no es exponer errores, sino entender **por qué está mal** cada uno y **cómo se llega a hacerlo bien**.

## 2. 🔴 Lo que salió bien, y el "0.X"

Antes de los errores, un caso donde casi todos acertaron, que sirve para ver qué es un RNF bien hecho.

La funcionalidad estrella del parcial fue el **reconocimiento de fotos** de recetas. **Doce requisitos** le pusieron un límite de tiempo, y casi todos con **valor y unidad**: 3 s, 5 s, 8 s, 10 s, 15 s, 30 s. **Eso estuvo muy bien.**

El problema apareció en uno solo:

> *"…el tiempo máximo de respuesta es de **0.X** segundos."*

"0.X" es un **ejemplo para completar**, no un valor. Escrito así, **no se puede verificar**: ¿cuánto vale X? **Es una ambigüedad.**

El ejemplo que ya todos tienen incorporado sigue siendo válido para usar en un parcial: *"La resolución de la imagen es de 1920 × 1080"*.

**¿Y qué número hay que poner?** **Cualquiera es válido.** La cátedra no evalúa si 3, 8 o 30 segundos es mucho o poco para transcribir una imagen: eso es una cuestión de factibilidad que se discute en la realidad, con el negocio y con el área técnica. Lo que evalúa es que el requisito **no sea ambiguo**, y para eso el número **tiene que estar**. Importa que sea un número, no cuál.

## 3. 🔴 Qué es un RNF (y qué tiene que tener)

Los doce requisitos de tiempo que salieron bien muestran la idea. Un RNF **restringe** una funcionalidad. En los libros de la materia, la palabra que más se repite al definir un no funcional es ***constraint***: **restricción**. El RNF no dice qué hace el sistema. Dice **bajo qué condición** se tiene que dar algo que el sistema hace.

De ahí salen sus tres rasgos:

1. **Está ligado a un RF.** Primero está la funcionalidad (reconocer la foto). El RNF la encierra (en cuánto tiempo).
2. **Se puede medir o verificar.** Tiene que existir una forma de comprobar si se cumple.
3. **Tiene objeto, atributo, valor y unidad**, cuando se escribe con la plantilla:

| Parte | Pregunta | Ejemplo |
|---|---|---|
| **Objeto** | ¿Sobre qué cosa del dominio? | proceso de reconocimiento de imagen |
| **Atributo** | ¿Qué característica de esa cosa? | tiempo máximo |
| **Valor** | ¿Cuánto? | 5 |
| **Unidad** | ¿En qué se mide? | segundos |

El verbo es **"ser" conjugado** (es, son): *"El tiempo máximo del proceso de reconocimiento de imagen **es** de 5 segundos."* También se acepta **"debe ser"**. **"Debería"** no: lo vuelve optativo (§6).

**La plantilla ayuda, pero no es obligatoria.** Si seguís la fórmula con el verbo "es", seguro escribiste un RNF. Pero hay RNF válidos que no la siguen al pie de la letra, siempre que sigan siendo **verificables** y sigan **restringiendo** una funcionalidad. Por ejemplo, *"La integración con la plataforma de pagos externa es mediante API REST"* no tiene un número, pero se puede verificar: o la solución tiene esa API o no la tiene (§4.2).

> **API REST:** forma estándar de que dos sistemas se comuniquen por internet mediante pedidos y respuestas; acá, cómo se conecta la aplicación con la plataforma de pagos.

> **Para el parcial, si te preguntan:** *¿Qué es un requisito no funcional?*
> Es una restricción sobre una funcionalidad del sistema: no describe qué hace el sistema sino bajo qué condiciones debe hacerlo, y tiene que poder medirse o verificarse. Con la plantilla se escribe con objeto, atributo, valor y unidad y el verbo "ser", por ejemplo: "el tiempo máximo del proceso de cobro de una receta es de 5 segundos".

## 4. 🔴 El top 5 de errores

| Puesto | Error | Casos |
|---|---|---|
| 1 | RF disfrazados de RNF | 13 |
| 2 | Reglas de negocio colándose | 8 |
| 3 | Adjetivos mágicos | 7 |
| 4 | "Lo hace otro" | 6 |
| 5 | Plantilla a la fuerza | 4 |

```
1. RF disfrazados de RNF        █████████████ 13
2. Reglas de negocio colándose  ████████       8
3. Adjetivos mágicos            ███████        7
4. "Lo hace otro"               ██████         6
5. Plantilla a la fuerza        ████           4
```

*(El conteo es sobre los 70 requisitos; un mismo requisito puede sumar más de un error.)*

Se recorren del 5 al 1, cada uno con lo que se escribió, por qué no es un RNF y el RNF que sí se podía escribir.

### 4.1 Puesto 5 — Plantilla a la fuerza (4 casos)

**Lo que se escribió:**
> *"Un pastelero puede tener varias versiones de una misma receta. Objeto: receta. Atributo: diferentes versiones. Valor: mayor a 1. Unidad: c/u."*

**Por qué no funciona.** Pasa cuando uno tiene una idea y la quiere meter en la plantilla porque se acuerda de que había que poner objeto, atributo, valor y unidad. Pero **la idea no es una restricción: es una funcionalidad**, *"El pastelero podrá crear versiones de una receta"*. Por eso la plantilla no encaja:

- **"Diferentes versiones" no es un atributo.** Si pensás la receta como un objeto, sus atributos son sus campos o cualidades (nombre, tiempo de preparación…). "Tener versiones" no es un campo.
- **"Mayor a 1" no es un límite.**
- **"c/u" no es una unidad de medida.**

**El RNF que sí se podía escribir:**
> **La cantidad máxima de versiones de una receta es de 10.**

| Objeto | Atributo | Valor | Unidad |
|---|---|---|---|
| receta | cantidad máxima de versiones | 10 | versiones |

**Lección:** si no reconocés fácilmente que estás describiendo un **atributo de un objeto**, algo hace ruido. Primero identificá el RF; después buscá qué se puede limitar de él.

### 4.2 Puesto 4 — "Lo hace otro" (6 casos)

**Lo que se escribió:**
> *"El cobro se procesa por una plataforma de pagos externa."*

**Por qué no es un RNF.** Dice **quién** cobra, no **qué tan bien**, **qué tan rápido** ni **cuánto**. Es una **decisión de diseño** atada al RF *"comprar una receta"*, y no hay nada para medir. Además, el verbo no es "ser": es **"procesar"**, una acción, y eso ya indica que se está hablando de una función y no de una restricción.

**Un RNF ligado a ese RF:**
> **El tiempo máximo del proceso de cobro de una receta paga es de 5 segundos.**

| Objeto | Atributo | Valor | Unidad |
|---|---|---|---|
| proceso de cobro | tiempo máximo | 5 | segundos |

*(El mismo grupo que escribió el requisito con error lo escribió bien en el requisito siguiente.)*

El RF ligado sale fácil porque los casos de uso estuvieron bastante bien en los parciales: si el caso de uso es *comprar una receta*, la pregunta es **cómo restringirlo**. Y no todo RNF tiene que ser un "máximo": también hay mínimos, formatos y valores fijos.

**Otras formas válidas, si lo que interesa es la plataforma.** Decir "una plataforma de pagos que no sabemos cuál es procesa el cobro" no es lo mismo que nombrarla:

- *"La plataforma de pagos externa es PayPerTIC."* Es más una definición que un RNF en sentido estricto, pero tiene un valor concreto y dice contra quién se va a hacer la integración, y contra quién reclamar si hay fallas. Se puede verificar que los pagos los procese esa plataforma.
- *"La integración con la plataforma de pagos externa es mediante API REST."* Es una restricción de interfaz: dice qué hay que contemplar para lograr la integración. Se puede verificar que la solución tenga esa API.

> **PayPerTIC:** plataforma argentina de cobros online (la usa, por ejemplo, el Club Ferro Carril Oeste). Acá es solo un ejemplo de proveedor con nombre propio.

**Lección:** con un servicio externo, lo que se mide es **tiempo, disponibilidad o precisión**, o se fija **cuál** es y **cómo** se integra.

### 4.3 Puesto 3 — Adjetivos mágicos (7 casos)

**Palabras que aparecieron:** *legibles · responsive · claro · exacto · cifrada.*

¿Con qué regla se mide "legible"? ¿Con una de 20 centímetros?

**Por qué no son RNF.** Son adjetivos sin instrumento de medición. Dos personas pueden opinar distinto sobre si algo es "claro", y nadie puede probar que se cumple.

**No todos están igual de mal.** "Responsive" no termina de estar mal: le falta **acotarse**, por ejemplo indicando en qué plataformas (iOS, Android) o para qué funcionalidades. El problema no es la palabra en sí, sino que quede sin nada que se pueda chequear.

> **Responsive:** diseño de interfaz que se adapta automáticamente al tamaño de la pantalla (celular, tablet, computadora).

**Lección:** **¿con qué lo mido? Si no hay instrumento, no hay RNF.** No hace falta seguir la plantilla al pie de la letra, pero sí poder corroborarlo, como en el caso de la API: eso se chequea.

### 4.4 Puesto 2 — Reglas de negocio colándose (8 casos)

**Lo que se escribió:**
> *"Los usuarios no deben publicar recetas copiadas."*

**¿Qué puede hacer el sistema?** Nada para **impedirlo**. Copiar una receta es "ley de la vida": pasa con o sin aplicación. El sistema no puede evitar que alguien copie. Lo que sí puede es **dejar denunciar** la receta y a la persona, y a partir de ahí restringir la cuenta o dar de baja al usuario. Eso es un **RF** del caso de uso de denuncia, no un RNF.

**La regla para detectarlo:**

> **Si existe igual a mano, es regla de negocio.**

Es la misma idea del centro de entrenamiento: *el socio tiene que pagar la cuota para entrenar*. La va a pagar con un sistema sofisticado o en efectivo, pero no puede asistir si no paga, haya o no sistema. Eso es una regla de negocio. (Y el profe tampoco puede impedir que se copien en un examen… pero se entera.)

**Un RNF ligado a la denuncia:**
> **El largo máximo del campo "motivo de la denuncia de una receta" es de 300 caracteres.**

| Objeto | Atributo | Valor | Unidad |
|---|---|---|---|
| motivo de la denuncia | largo máximo | 300 | caracteres |

> **Para el parcial, si te preguntan:** *¿Cómo distinguís una regla de negocio de un RNF?*
> La regla de negocio es una política del negocio que existe con o sin sistema: si se cumpliría igual a mano, es regla de negocio. El RNF, en cambio, es una restricción medible sobre una funcionalidad del sistema, con objeto, atributo, valor y unidad.

### 4.5 Puesto 1 — RF disfrazados de RNF (13 casos)

**Lo que se escribió:**
> *"Para cada ingrediente indico cantidad, unidad de medida y observaciones."*

**¿Qué se mide acá? Nada.** Es la **lista de datos de un ingrediente**, y eso va en el RF de registrar recetas. Un RNF **no lista datos**: tiene objeto, atributo, valor y unidad.

Mirá el verbo: **"indico"**. No es "ser". Cuando el verbo no es "ser", hay que sospechar de un **sujeto tácito**: acá, el pastelero, que indica la cantidad, la unidad de medida y las observaciones de cada ingrediente. Eso es **lo que hace un actor**, es decir, uno o varios **pasos del escenario del caso de uso "registrar receta"**.

**El matiz.** Escrito como *"Los atributos del ingrediente son: cantidad, unidad de medida y observaciones"*, quedaría más cerca de una restricción, porque sin saber cuántos gramos de harina poner difícilmente salga la preparación. Pero en realidad sería una **definición de la estructura de datos**, con sus atributos obligatorios, sus claves, etc. Y si se agregaran validaciones (por ejemplo, avisar que para esa proporción hay demasiada harina), eso ya sería **funcional**, no un RNF.

**Un RNF ligado a ese RF:**
> **El largo máximo de las observaciones de un ingrediente es de 200 caracteres.**

| Objeto | Atributo | Valor | Unidad |
|---|---|---|---|
| observaciones | largo máximo | 200 | caracteres |

**Casi 1 de cada 5 requisitos cayó acá: mucha lista, nada para medir.**

## 5. 🟡 Menciones especiales: cuatro requisitos, tres atributos de calidad

Dos no son **realistas**, uno no es **verificable** y uno no es **consistente**.

### 5.1 No es realista: la harina en centímetros

> *"La unidad de medida de un ingrediente es en centímetros."*

La harina no se mide en centímetros, ni en centímetros cúbicos. En pastelería, los secos van en **gramos** o **tazas** y los líquidos en **centímetros cúbicos** o **mililitros**. Lo único que va en centímetros es, por ejemplo, el diámetro del molde (28 cm), y **el molde no es un ingrediente**: es un elemento que se usa.

La estructura del requisito era correcta ("la unidad de medida de un ingrediente es…"). **Lo que falló fue el valor**, que no tiene sentido en el dominio. Si no estás seguro de un valor del dominio, mejor encarar el requisito por otro lado que escribir algo que no tiene sentido.

### 5.2 No es verificable: el 0.X

> *"…el tiempo máximo de respuesta es de 0.X segundos."*

Ya visto en §2: sin un valor concreto no hay forma de comprobar si se cumple.

### 5.3 No es consistente: la tasa de error que mide aciertos

> *"La tasa de error… debe ser menor a 95. Nota: palabras correctas / palabras totales × 100."*

El requisito habla de **errores**, pero la fórmula calcula **aciertos**. ¿Medimos lo bueno o lo malo? La aclaración de cómo se calcula estaba bien planteada como idea; lo que estaba al revés era la cuenta. Para una tasa de **error**, la fórmula es *palabras **incorrectas** / palabras totales × 100*.

### 5.4 No es realista, y tiene un problema de sujeto: la selfie en PDF

> *"Las fotografías de las recetas deben aceptar como formato JPG / PDF."*

Dos problemas:

1. **PDF no es un formato de foto.** Un comprobante de pago puede bajarse en PDF, pero eso no es una fotografía.
2. **La fotografía está puesta como sujeto que hace algo** ("acepta"). Una fotografía **es un objeto**: no hace nada, se le hacen cosas a ella. Quien verifica el formato al cargar la imagen es la aplicación.

Otro grupo lo escribió bien:
> **"Los formatos de las fotos son JPG y PNG."**

Con ese RNF, lo que hará la aplicación al cargar una imagen es verificar que el archivo esté en uno de esos formatos.

**¿Se pueden inventar valores que el enunciado no da** (por ejemplo, los formatos de imagen)? **Sí**, siempre que sean **comprobables** y **coherentes con el dominio**. Es normal tener que asumir bajo qué restricciones se resuelve el sistema. No importa si el número es grande o chico; importa que haya un número y que tenga sentido en el contexto.

## 6. 🔴 Ejercicio: ¿qué es cada uno?

Cuatro categorías: **RF · RNF · Regla de negocio · Restricción sin medir**. Clasificá antes de mirar la tabla.

1. *"Los medios de pago son tarjeta y transferencia."*
2. *"La búsqueda de recetas debería durar 5 segundos como máximo."*
3. *"El administrador necesita que el sistema muestre cantidad de usuarios reportados."*
4. *"El acceso al sistema es con usuario y contraseña."*

| N.º | Respuesta | Por qué |
|---|---|---|
| 1 | **Regla de negocio** | Existiría aunque se cobrara en mano: es una política del negocio. Además es **ambigua**: ¿tarjeta de débito o de crédito? |
| 2 | **RNF (casi)** | Se mide, pero **"debería" lo vuelve optativo**: con "debe" o "es" queda bien. Además, lo que se restringe no es la "duración de la búsqueda" sino el **tiempo de respuesta**: *"El tiempo máximo de respuesta de la búsqueda de recetas es de 5 segundos."* |
| 3 | **RF** | Describe algo que hace el sistema, pero está **escrito como necesidad** del administrador. Los RF resuelven lo que los usuarios necesitan, pero **no se redactan como necesidades, deseos ni aspiraciones**. |
| 4 | **Restricción sin medir** | Está relacionada con la seguridad y se puede verificar, pero no tiene objeto, atributo, valor y unidad. |

**Por qué la 1 es regla de negocio.** El negocio puede decidir mañana: "la tarjeta me cobra mucha comisión, acepto transferencia y efectivo, y se terminó la tarjeta". Y después puede venir ARCA y decirle que está obligado a aceptar débito, y la tarjeta vuelve.

> **ARCA:** Agencia de Recaudación y Control Aduanero, el organismo fiscal argentino (ex AFIP). Son **decisiones del negocio** (o de la normativa), no restricciones técnicas del sistema.

**Sobre la 2, un matiz.** Fijar que la búsqueda responda en menos de 5 segundos también es, en el fondo, una **propuesta al negocio**: después hay que ver la factibilidad técnica de cumplirlo.

> ⚠️ **En una clase anterior, una frase sobre medios de pago se clasificó como no funcional** (una restricción del medio, cuando el cliente la exige). La cátedra reconoció que en el documento de aquella clase figura como no funcional y que es un punto discutido. En esta clase, sin embargo, clasificó explícitamente *"los medios de pago son tarjeta y transferencia"* como **regla de negocio**, con el argumento de arriba. **Para el examen: regla de negocio**, y conviene escribir la justificación ("existiría aunque se cobrara en mano; es una decisión del negocio que puede cambiar").

> **Para el parcial, si te preguntan:** *Clasificá "Los medios de pago son tarjeta y transferencia" y justificá.*
> Es una regla de negocio: existiría aunque el cobro se hiciera en mano, y es una decisión del negocio que puede cambiar (por costos de comisión o por normativa) sin que cambie la funcionalidad de pagar. Además, como está escrita es ambigua, porque no aclara si la tarjeta es de débito o de crédito.

## 7. 🔴 El mejor RNF del parcial

> **"El tiempo máximo del proceso de reconocimiento de imagen (desde el instante que se sube la foto hasta que se devuelven los datos) debe ser de 5 segundos."**

(Con "es de 5 segundos" también queda bien.)

| Objeto | Atributo | Valor | Unidad |
|---|---|---|---|
| proceso de reconocimiento de imagen | tiempo máximo | 5 | segundos |

**Lo que lo hace excelente:** el paréntesis dice **desde cuándo hasta cuándo** se mide. Así cualquiera lo puede verificar de la misma manera, y quien lo pruebe sabe exactamente cómo hacer la medición.

**Cómo mejorarlo todavía:** aclarar **bajo qué condiciones** valen esos 5 segundos, porque no es lo mismo transcribir una foto borrosa que una nítida. Por ejemplo, agregando *"para un archivo de hasta 5 MB y una resolución de 1200 DPI"* (o tantos píxeles). Así quedan definidos el **tamaño** y la **definición** del archivo.

> **DPI** (*dots per inch*, puntos por pulgada): medida de la resolución de una imagen escaneada o impresa; a más DPI, más detalle.

## 8. 🔴 Antes de entregar: tres preguntas y dos señales de alerta

### 8.1 Las tres preguntas, en orden

| Pregunta | Si la respuesta es… | Entonces… |
|---|---|---|
| **1. ¿Existiría sin el sistema?** | Sí, se cumple igual a mano | Es una **regla de negocio**. |
| **2. ¿Describe qué hace el sistema o qué datos tiene?** | Sí | Es un **RF**. Buscá el RNF ligado a esa funcionalidad. |
| **3. ¿Con qué lo mido?** | Objeto, atributo, valor y unidad | Si falta uno, **todavía no es un RNF**. |

Y, por favor: **los ingredientes no se miden en centímetros.**

**Cómo se compatibiliza la pregunta 3 con lo de §3.** La pregunta 3 es el filtro por defecto. La cátedra acepta algunas restricciones verificables sin número, como *"la integración con la plataforma de pagos externa es mediante API REST"*, siempre que sigan restringiendo una funcionalidad concreta. En el ejercicio de §6, en cambio, *"el acceso al sistema es con usuario y contraseña"* se clasificó como restricción sin medir. **Ante la duda, en el examen, llevalo a objeto, atributo, valor y unidad.**

### 8.2 Las dos señales de alerta: me detengo si…

**1. El sujeto de la oración es un actor.** El pastelero, el administrador o el socio no tienen nada que ver acá. Si el sujeto es un actor, se está describiendo **lo que hace alguien**: una función. Un RNF no dice qué hace alguien, sino **bajo qué condiciones** va a recibir el resultado de lo que pretende hacer.

**2. El verbo no es "ser" conjugado.** Si el verbo es *procesar, indicar, aceptar, necesitar, publicar…*, hay altas chances de estar escribiendo un RF. (Vale repasar la conjugación del verbo "ser" en indicativo: *es, son, será…*)

**Si aparece cualquiera de las dos, se borra y se vuelve a empezar**, cambiando el foco hacia **qué se puede limitar** de esa funcionalidad.

Una tercera señal, relacionada: **un objeto puesto a hacer algo** ("la fotografía acepta…"). Los objetos no hacen nada: se les hacen cosas (§5.4).

> ⚠️ **En una clase anterior se aceptó un RNF con un actor como sujeto** (*"El socio necesita conexión de internet para completar el pago"*). Con la señal de alerta que la cátedra ya había dado en el parcial y que esta clase repite, ese tipo de redacción ya no conviene. **Para el examen: aplicá la señal de alerta**: si el sujeto es un actor, reescribí con el verbo "ser" sobre un objeto.

> **Para el parcial, si te preguntan:** *¿Cómo te das cuenta de que escribiste un RF disfrazado de RNF?*
> Porque el sujeto de la oración es un actor o el verbo no es "ser" conjugado: en ese caso se está describiendo lo que alguien hace, que es una función. Un RNF describe una restricción medible sobre esa función, con objeto, atributo, valor y unidad.

## 9. 🟡 Por qué tanta insistencia con la redacción

No es una cuestión de estilo literario: no se trata de escribir como Borges o como Cortázar. Se busca que lo que se redacta tenga **atributos mínimos de calidad**:

- **completo**;
- **coherente** (consistente, sin contradecirse);
- **verificable** y **medible**;
- **no ambiguo**: una **interpretación unívoca** para quien lo lee.

**Si una redacción admite dos interpretaciones posibles, ya hay un problema.** Las menciones especiales de §5 son exactamente eso: requisitos que no son realistas, uno que no es verificable y uno que no es consistente.

## 10. 🟡 Información operativa

- **Esta devolución** (el top 5 con sus correcciones) se sube al aula para leerla con tiempo y empezar a aceitar la redacción de RNF. En el aula también está el documento de una actividad anterior donde se ven los requisitos originales y cómo quedaron corregidos: sirve para identificar los errores que uno suele repetir.
- **12/11 (presencial): práctica pre parcial.** Se trabaja **con los propios requisitos del parcial**: cada uno vuelve a los suyos, analiza por qué están mal y los reescribe, con dinámicas en clase. Según el cronograma, la práctica incluye también escenarios y LEL.
- **19/11: segundo parcial** (LEL y escenarios, según el cronograma).
- **26/11: recuperatorio** y presentación del **TP integrador**. Las otras instancias de recuperación son las **tres fechas de final**: como es segundo cuatrimestre, las actas se pueden cerrar hasta febrero.
- **Para el recuperatorio** se pueden inventar los valores que el enunciado no dé, siempre que sean coherentes con el dominio y comprobables (§5.4).
- **05/11 (clase siguiente):** las tres exposiciones que faltan (Parte 2, §7), ejercicios de escenarios y LEL, y la **entrega de LEL**.
- **Foro:** hay que participar comparando **qué dice la IA sobre escenarios y casos de uso**; se le pueden sumar historias de usuario (descripciones breves de una funcionalidad desde el punto de vista de quien la usa). Si el foro aparece bloqueado, la cátedra lo está revisando.
- **Cronograma:** el de la página de la materia se va a corregir. Las fechas válidas son las de esta lista.

---

## 🔴 ✅ Checkpoint de la clase 12

*(Sin respuestas: van en el complemento.)*

1. ¿Por qué se dice que LASCAD "generó su propia carga", si la demanda de ese día fue normal?
2. ¿Qué significa que LASCAD "hizo exactamente lo que le pidieron", y por qué eso fue el problema?
3. ¿Por qué se discute la conclusión de que LASCAD "no falló en un sentido técnico"? ¿Qué es un fracaso sociotécnico?
4. ¿Qué tenía de malo el documento de requisitos del Virtual Case File, más allá de su tamaño?
5. ¿Qué diferencia hay entre "no hay evidencia de que vaya a fallar" y "hay evidencia de que va a funcionar"?
6. Al exponer un caso de investigación, ¿por qué es tan importante explicar el dolor que la organización quería resolver?
7. ¿Por qué "0.X segundos" no es un RNF válido, si cualquier número lo sería?
8. ¿Cuáles son las tres preguntas que conviene hacerse antes de dar por terminado un RNF?
9. Corregí: *"Las fotografías de las recetas deben aceptar como formato JPG / PDF."* ¿Qué problemas tiene?
10. ¿Por qué "los medios de pago son tarjeta y transferencia" es una regla de negocio y no un RNF?

---

**FIN DE LA PARTE 3 — FIN DEL APUNTE MAESTRO DE LA CLASE 12**
