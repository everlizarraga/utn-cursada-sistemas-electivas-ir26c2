# 📘 APUNTE MAESTRO — Clase 06
## Parte 1: Diseño de cuestionarios

**Materia:** Ingeniería de Requisitos · **Unidad:** clase06 · **Parte:** 1 de 4

---

### Qué cubre esta parte

El cuestionario como instrumento: cómo se arma uno que sirva, y cuáles son los errores de diseño que lo arruinan antes de que nadie lo responda. Es un bloque de criterio puro — no hay procedimiento que memorizar, hay decisiones que justificar.

**Leyenda de marcas:** 🔴 central, altamente evaluable · 🟡 secundario, puede aparecer · 🟢 mencionado al pasar.

---

## 1. El caso: un cuestionario que arranca pidiéndote el nombre 🔴

Te llega un cuestionario. Arriba dice que es sobre tu experiencia en el centro de entrenamiento al que vas. La primera consigna, antes de cualquier otra cosa, es:

```
1. Nombre y apellido: ______________________
```

Todavía no viste ni una pregunta. Ya sabés que lo que respondas va a quedar pegado a tu nombre.

**¿Qué te pasa como respondente?**

- **Te sentís observado.** Lo que estás por decir deja de ser una opinión y pasa a ser una declaración con tu firma.
- **Te sentís condicionado.** No sabés qué viene después. ¿Y si me preguntan por los profesores? ¿Y si después el profesor me hace hacer cincuenta abdominales de más porque opiné mal de él? Es una exageración deliberada, pero el mecanismo es real: anticipás consecuencias de lo que todavía no leíste.
- **Sentís que vas a tener que justificarte.** Si pongo que algo está mal, alguien va a venir a preguntarme por qué.

El resultado es siempre el mismo: **la respuesta se corre del tema y pasa a ser sobre vos.** Y lo que vos querías medir era el tema, no el cálculo político del que responde.

### El matiz importante: el anonimato ya estaba roto

Acá hay una vuelta de tuerca que conviene tener clara, porque es la que separa la respuesta de manual de la respuesta con criterio.

Un formulario web **no garantiza anonimato real**, y buena parte de la gente que responde lo intuye. Sabe que hay algún tipo de rastro: la cuenta con la que entró, el dispositivo, el momento en que respondió. A eso se lo llama **trazabilidad** — la posibilidad de reconstruir quién produjo un dato.

> 🕳️ **Madriguera — anonimato técnico y protección de datos**
> Qué garantías reales ofrece cada herramienta (formularios sin login, cifrado, disociación de datos personales) y qué exige la normativa de protección de datos es un tema propio, con su propia legislación.
> *Volvé al camino — para la materia alcanza con razonar el anonimato desde la percepción del que responde.*

Entonces: si el anonimato nunca fue total, ¿por qué molesta tanto pedir el nombre?

Porque **lo hace explícito**. Una cosa es sospechar que existe un rastro y otra distinta es que te pidan firmar arriba de todo. Lo primero deja margen para responder tranquilo; lo segundo activa la autocensura.

El caso extremo lo muestra bien. Hubo encuestadores profesionales que, para conseguir respuestas realmente sinceras y comprometidas, trabajaban **con cartas en papel** que el encuestado depositaba de forma anónima en un correo. Todo lo demás —el cara a cara, el teléfono, el formulario digital— deja al que responde asumiendo que hay trazabilidad. El papel anónimo la eliminaba, y con eso conseguían sinceridad.

### ¿Entonces nunca se pide el nombre?

No. **Puede corresponder**, y decir "nunca se pide" es tan equivocado como pedirlo siempre. Hay contextos donde identificarse es necesario: un reclamo que requiere seguimiento, un trámite, una respuesta que hay que poder devolver.

La regla no es una prohibición, es una pregunta: **¿lo necesito para el análisis, o lo estoy pidiendo por inercia?** Si no lo necesito, el costo (respuestas condicionadas) es mucho más alto que el beneficio.

> **📌 Para el parcial, si te preguntan**
> **¿Por qué es problemático pedir nombre y apellido al inicio de un cuestionario?**
> Porque condiciona la respuesta: el respondente se siente observado y anticipa tener que justificarse, con lo cual responde lo que le conviene y no lo que piensa. Ninguna herramienta digital garantiza anonimato total, pero pedir la identificación explícitamente elimina la percepción de privacidad y dispara la autocensura. Puede corresponder pedirla cuando el análisis realmente la requiere; si no, se reemplaza por variables de segmentación.

---

## 2. Si no pido el nombre, ¿cómo sé quién me respondió? 🔴

Acá viene la solución, y no es resignarse a no saber nada del que responde.

No necesitás saber **quién** es. Necesitás saber **de qué parte de la población viene**. Y eso se consigue con preguntas que caracterizan sin identificar:

| Variable | Ejemplo de pregunta | Para qué sirve |
|---|---|---|
| Rango etario | ¿Cuál es tu rango de edad? | Ver si las necesidades cambian con la edad |
| Género | ¿Con qué género te identificás? | Detectar diferencias por segmento |
| Antigüedad | ¿Hace cuánto sos socio del centro? | Distinguir al recién llegado del que tiene historia |
| Frecuencia | ¿Con qué frecuencia venís? | Separar al usuario intensivo del ocasional |
| Tipo de plan | ¿Qué plan tenés contratado? | Cruzar la respuesta con el uso real del servicio |

Estas variables cumplen **dos funciones distintas**, y conviene no confundirlas:

**Función 1 — Describir la población.** Saber cómo está compuesto el conjunto que respondió. Si el 90% de las respuestas viene de gente que arrancó hace menos de un mes, tu foto no representa al socio promedio, y necesitás saberlo antes de sacar conclusiones.

**Función 2 — Ponderar cada respuesta.** No todas las respuestas valen lo mismo para toda pregunta. Alguien que empezó hace tres semanas no puede opinar con la misma autoridad sobre el funcionamiento del lugar que alguien que viene hace cuatro años y le pasaron cosas. El que viene todos los días tiene una experiencia distinta del que viene una vez por semana.

```
        ┌──────────────────────────────────────────┐
        │  CUESTIONARIO                            │
        ├──────────────────────────────────────────┤
        │                                          │
        │  ▸ Introducción de contexto              │  → §6
        │                                          │
        │  ▸ Variables de segmentación             │  → describe y pondera
        │    (edad, antigüedad, frecuencia, plan)  │
        │                                          │
        │  ▸ Preguntas cerradas (valores           │  → el grueso del análisis
        │    discretos)                            │
        │                                          │
        │  ▸ Pregunta(s) abierta(s)                │  → solo donde se necesita
        │                                          │     que se explaye
        └──────────────────────────────────────────┘
```

> **📌 Para el parcial, si te preguntan**
> **¿Cómo se caracteriza a la población sin pedir identificación?**
> Con variables de segmentación: rango etario, género, antigüedad, frecuencia de uso, tipo de plan. Permiten dos cosas: describir cómo está compuesta la población que respondió, y ponderar cada respuesta según el perfil de quien la dio, ya que la experiencia de un usuario nuevo no tiene el mismo peso que la de uno con antigüedad.

---

## 3. Preguntas cerradas y preguntas abiertas 🔴

### La pregunta cerrada: valores discretos

Una pregunta cerrada ofrece un conjunto fijo y acotado de opciones. A ese conjunto se lo llama **valores discretos** — separados, contables, sin nada en el medio. Cinco opciones son cinco opciones, punto.

```
¿Qué tan conforme estás con la disponibilidad de turnos?

   ○ Muy conforme
   ○ Conforme
   ○ Indiferente
   ○ Disconforme
   ○ Muy disconforme
```

**La ventaja es el análisis.** Cuando te llegan ochenta respuestas, las cerradas ya vienen cuantificadas: contás cuántas cayeron en cada opción y tenés el panorama en minutos. No hay que leer nada, hay que sumar.

**Dos detalles de diseño que se pasan por alto:**

- **Opción única vs. opción múltiple.** Si las opciones son mutuamente excluyentes (*me molesta* / *no me molesta*), tiene que ser de opción única: no se puede responder las dos. Si la pregunta admite varias respuestas simultáneas (*¿qué actividades hacés?*), va múltiple. Elegir mal el tipo rompe el análisis.
- **La salida de escape.** Conviene prever una opción tipo *ninguna de las anteriores*, porque el conjunto que vos imaginaste puede no cubrir todos los casos reales.

### La pregunta abierta: campo libre

```
¿Cómo te sentirías si te penalizaran por no avisar una ausencia?

   ____________________________________________
```

**Los tres problemas, en orden de gravedad:**

1. **Abandono.** El respondente ve un campo en blanco, calcula el esfuerzo, y deja el cuestionario a la mitad. Perdiste no solo esa respuesta: perdiste todas las que venían después.
2. **Respuestas basura.** El que no quiere abandonar pero tampoco quiere escribir pone un punto, o cualquier cosa, y sigue. Tenés una respuesta registrada que no dice nada.
3. **Análisis lento.** Aun suponiendo que te respondan con sinceridad y compromiso —que es el mejor caso—, hay que leer cada respuesta una por una e interpretarla. Con ochenta respuestas abiertas, el análisis se te va de las manos.

### Entonces, ¿cuándo se justifica una abierta?

Cuando **de verdad estás invitando a que se explaye** y el conjunto de respuestas posibles no se puede anticipar.

Si podés listar las respuestas posibles, la pregunta es cerrada disfrazada de abierta, y la estás pagando cara. En el ejemplo de arriba, si lo que buscás es un sentimiento, el conjunto de sentimientos posibles es enumerable: molestia, indiferencia, aceptación, enojo. Eso va cerrado.

La abierta se guarda para el final, para lo que no viste venir: *¿hay algo más que quieras contarnos?*

**La regla operativa:** las preguntas abiertas son un recurso escaso. Cada una que ponés tiene un costo en abandono y en tiempo de análisis. Poné las mínimas, y donde realmente aporten.

> **📌 Para el parcial, si te preguntan**
> **¿Qué ventaja tiene una pregunta con valores discretos sobre una abierta?**
> Que las respuestas quedan cuantificadas: el análisis es rápido porque se cuentan las ocurrencias de cada opción, sin necesidad de leer e interpretar. La pregunta abierta, en cambio, aumenta el riesgo de abandono del cuestionario, admite respuestas sin contenido y exige un análisis manual mucho más lento. Se reserva para los casos en que se busca que el respondente se explaye y no se pueden anticipar las respuestas posibles.

---

## 4. Las opciones no se inventan: coherencia entre instrumentos 🔴

Esta es la sección más fácil de subestimar y la que más se cobra en la corrección.

### El caso

Querés saber con cuánta anticipación un socio debería avisar que no va a ir a una clase en la que está anotado. Ponés:

```
¿Con cuánta anticipación creés que deberías avisar que no vas
a asistir a una clase? (Indicar en horas): ______
```

Parece razonable. No lo es, por dos motivos distintos.

**Primer motivo — es abierta sin necesidad.** Ya vimos que si las respuestas posibles se pueden anticipar, la pregunta va cerrada. Acá se pueden.

**Segundo motivo, el importante — el parámetro ya existía y no lo usaste.** En la entrevista con los profesores había salido un dato concreto: el profesor necesita saber con **al menos tres horas de anticipación** que la clase se cae, porque pasado ese punto ya agarró el bolso y se subió al colectivo. Se toma dos colectivos, viaja una hora, llega al centro y se entera ahí de que se le bajaron todos.

Si dejás el campo abierto, el socio te va a poner "20 minutos" — y desde su lugar tiene razón, porque **él vive cerca**. El que se toma una hora de viaje es el profesor, no el socio. Cada grupo contesta desde su propia realidad, y si no ponés el parámetro del otro grupo sobre la mesa, la respuesta que obtenés no resuelve el problema que estabas tratando de resolver.

**La corrección:** las opciones se construyen con los parámetros que salieron de la otra técnica.

```
¿Con cuánta anticipación estarías dispuesto a avisar una cancelación?

   ○ Menos de 1 hora
   ○ Entre 1 y 3 horas
   ○ Entre 3 y 6 horas
   ○ Con más de 6 horas
   ○ El día anterior
```

Ahora sí: cada respuesta cae de un lado o del otro del umbral de tres horas, y podés decidir.

### El principio, en general

```
   ENTREVISTA                         CUESTIONARIO
   (junta directiva,                  (socios,
    profesores)                        universo amplio)
        │                                    │
        │  surge un parámetro:               │
        │  "mínimo 3 horas"                  │
        │                                    │
        └──────────► alimenta las opciones ──┘
                             │
                             ▼
                   ANÁLISIS CRUZADO
         ¿lo que dicen los socios ratifica
          o rectifica lo que dijeron los
              profesores y la dirección?
```

Las técnicas de elicitación **no son islas**. Cuando aplicás más de una sobre el mismo problema, están para contrastarse. Y solo se pueden contrastar si comparten los mismos parámetros.

El propósito concreto del cuestionario a los socios es **ratificar o rectificar** lo que salió de la entrevista con el otro grupo. Si las escalas no coinciden, no hay cruce posible: tenés dos conversaciones sueltas con dos grupos distintos, y ninguna forma de detectar si se contradicen.

**Un término que conviene fijar:** *ratificar* es confirmar lo que ya suponías; *rectificar* es corregirlo porque los datos dicen otra cosa. Las dos son resultados válidos y útiles del análisis. Un cuestionario que rectifica una hipótesis equivocada te acaba de salvar el proyecto.

### Analogía para fijarlo

El problema de fondo —gente que reserva y no avisa que no va— es el mismo que el de los **turnos médicos**. Alguien saca turno, no va, no cancela. El turno queda bloqueado para otro paciente que sí lo necesitaba, y el médico queda subocupado en el consultorio porque no vino nadie. El recurso se desperdicia por falta de aviso, exactamente igual que el cupo de una clase.

> **📌 Para el parcial, si te preguntan**
> **¿Qué relación debe existir entre una entrevista y un cuestionario aplicados al mismo problema?**
> Los parámetros que surgieron en la entrevista deben incorporarse como opciones de respuesta del cuestionario. Esto permite el análisis cruzado, que es el objetivo: contrastar si las respuestas de un grupo de usuarios ratifican o rectifican lo relevado con los stakeholders. Si cada instrumento usa escalas distintas, no hay forma de detectar discrepancias entre ambos grupos.

---

## 5. Adverbios de frecuencia: ambigüedad garantizada 🔴

```
¿Con qué frecuencia no pudiste anotarte a la clase que querías?

   ○ Muy frecuentemente
   ○ Frecuentemente
   ○ Ocasionalmente
   ○ Casi nunca
```

Está cerrada. Tiene valores discretos. Y sin embargo es una mala pregunta.

**El problema:** *frecuentemente* no significa lo mismo para dos personas distintas. La opción no tiene métrica, así que lo que estás midiendo no es la frecuencia real: es **la percepción del que responde**.

Un tipo intentó anotarse dos veces en todo el mes y las dos veces no pudo. Marca *muy frecuentemente*, y desde su experiencia tiene razón: le falló el 100% de los intentos. Otro intentó veinte veces y falló cuatro. Marca *ocasionalmente*.

**Fijate el lío que acabás de comprar:** ¿cuál de los dos está peor? Si mirás la tasa de fallo, el primero (100% contra 20%). Si mirás cuántas veces se quedó afuera alguien que quería entrenar, el segundo (cuatro contra dos). El adverbio no te dice cuál de las dos cosas estabas midiendo, y por eso las dos respuestas no son comparables entre sí.

### El mismo problema con la espera

```
¿Esperaste mucho en la fila?
```

Alguien apurado, con el colectivo por salir: dos minutos son *mucho*. Alguien entretenido con el celular: estuvo media hora y no se dio cuenta, marca que no esperó nada. Media hora **es** un montón. La percepción se comió el dato.

### La regla

**Si podés medirlo y estandarizarlo, preguntá directamente por el valor y ni menciones el adverbio.**

```
En el último mes, ¿cuántas veces intentaste anotarte a una clase y no había cupo?

   ○ Ninguna       ○ 1 o 2       ○ 3 a 5       ○ Más de 5
```

Ahora el que responde no tiene que interpretar nada. Elige entre valores que significan lo mismo para todos, y vos podés evaluarlos. El que responde ni siquiera necesita saber qué estás midiendo — solo tiene que ubicarse entre opciones concretas.

**¿Y si no hay forma de medirlo?** Ahí el adverbio es el mal menor, pero sabiendo lo que estás comprando: respuestas sujetas a percepción, más ambiguas, y un análisis más difícil de sostener.

### Conectá esto con lo que viene

Fijate lo que acabás de hacer: detectaste que una palabra admite **más de una interpretación** y por eso el dato no sirve. Eso se llama **ambigüedad**, y es exactamente el mismo defecto que vamos a perseguir en la Parte 3, pero aplicado a los requerimientos. El mecanismo es idéntico: si dos personas leen lo mismo y entienden cosas distintas, el artefacto está mal hecho.

> **📌 Para el parcial, si te preguntan**
> **¿Por qué "muy frecuentemente" es una opción de respuesta problemática?**
> Porque es un adverbio de frecuencia sin métrica asociada: no mide la frecuencia real sino la percepción del respondente, y dos personas con situaciones muy distintas pueden elegir la misma opción. Cuando la variable se puede medir y estandarizar, corresponde ofrecer valores concretos y no usar el adverbio. Es un caso de ambigüedad.

---

## 6. La introducción de contexto 🟡

Antes de distribuir un cuestionario hay que ponerle una introducción. Sin ella, el que lo recibe no tiene forma de saber en qué rol le están preguntando.

### Qué pasa si falta

Si la primera pregunta es *"¿hace cuánto sos socio?"*, ¿socio de qué? Puede ser socio de una tarjeta de crédito, socio de un club de fútbol, socio de una cooperativa. La respuesta llega igual, pero no sabés qué estás midiendo.

### Qué tiene que decir

- **Quiénes son ustedes y en qué marco preguntan.** Que es un trabajo en el contexto de una cursada universitaria. Es honesto y además ayuda: la gente colabora más con un trabajo de estudio que con algo que parece publicidad encubierta.
- **Sobre qué es.** Un análisis para una posible solución en un centro de entrenamiento.
- **En qué rol se le pide que responda.** *"Nos gustaría que nos respondas en tu rol de socio de un centro de entrenamiento."*

```
Estamos trabajando en el análisis de una solución para un centro de
entrenamiento, en el marco de una materia de la carrera de Ingeniería
en Sistemas de Información.

Nos gustaría que, en tu rol como socio de un centro de entrenamiento,
respondas el siguiente cuestionario. No te va a llevar más de X minutos
y las respuestas son anónimas.
```

### Un detalle que mejora todo el instrumento

Si conseguís que respondan personas que **efectivamente van a un gimnasio**, mucho mejor. Las respuestas dejan de ser al tun-tún y pasan a venir de la experiencia real. Difundirlo en un canal donde haya gente del perfil correcto vale más que difundirlo en cualquier lado.

---

## 7. El alcance: qué preguntar y qué no 🟡

Un cuestionario en este contexto apunta a **información sobre la solución que se está analizando**. No a mejoras del negocio en general.

**Fuera de alcance:**

```
❌ ¿Te parece que hay pocas bicicletas?
❌ ¿Qué clases te gustaría que sumaran?
❌ ¿El precio de la cuota te parece razonable?
```

Todo eso es legítimo y probablemente le interese mucho al dueño, pero es materia del área comercial del centro, no del análisis de requerimientos. Cada pregunta que gastás ahí es una que no hiciste sobre lo que necesitás.

**Dentro de alcance:**

```
✅ ¿Cómo te enterás de que se canceló una clase?
✅ ¿Alguna vez quisiste darte de baja de una clase y no supiste cómo?
✅ ¿Con cuánta anticipación te avisan cuando se libera un cupo?
```

**Una precisión, para que no se malinterprete el recorte:** que el alcance sea la solución no significa preguntar en abstracto. Las preguntas tienen que estar **ancladas en el lugar concreto** sobre el que se trabaja, con su vocabulario y sus situaciones reales. Lo que queda afuera es el tema comercial, no el contexto.

**El criterio para filtrar:** *esta respuesta, ¿me va a cambiar alguna decisión sobre la solución?* Si no, afuera.

---

## 8. Cantidad de respuestas 🟡

Cuatro respuestas no alcanzan para decidir nada. Con cuatro no hay variedad, no hay contraste, y cualquier conclusión que saques descansa sobre la opinión de cuatro personas que capaz son todas parecidas entre sí.

Hubo casos de grupos que difundieron el cuestionario en canales con mucha gente de la carrera y juntaron alrededor de **ochenta respuestas**. Con ese volumen aparece variedad, y recién ahí el análisis empieza a decir algo.

**Práctica:** distribuir ampliamente, aclarando siempre el contexto (§6), y apuntando a gente del perfil correcto cuando se pueda.

> 🕳️ **Madriguera — muestreo y representatividad estadística**
> Cuántas respuestas hacen falta para que una muestra sea estadísticamente representativa, y cómo se calcula el margen de error, es un tema con herramientas propias que se ven en Probabilidad y Estadística.
> *Volvé al camino — acá el criterio es cualitativo: más respuestas y más variadas, mejor decisión.*

---

## 9. La presentación también se corrige 🟡

Antes de divulgar cualquier documento —cuestionario, minuta, informe— hay que **revisar ortografía, acentos y signos de puntuación**.

No es una cuestión de estilo ni de prolijidad decorativa. Son dos cosas concretas:

**Primero, es tu presentación.** El documento sale de tu equipo hacia afuera: hacia el cliente, hacia los usuarios, hacia quien lo tenga que leer. Un cuestionario con faltas de ortografía en las opciones de respuesta le dice al que lo recibe que no le pusieron cuidado, y baja la predisposición a responderlo en serio.

**Segundo, y más grave: la redacción defectuosa produce ambigüedad.** Un signo de puntuación en el lugar equivocado puede cambiar lo que una pregunta significa. Y ya vimos en §5 que cuando el que lee puede entender dos cosas distintas, el dato que obtenés no vale.

Esto aplica igual a los cuestionarios, a las minutas y a todo lo que el equipo produzca.

---

## 10. Qué pasa después con el cuestionario 🟢

El instrumento no termina cuando lo armás. El ciclo completo es:

```
   DISEÑAR ──► REVISAR Y ──► DISTRIBUIR ──► RECOLECTAR ──► ANALIZAR
               CORREGIR                                        │
                  ▲                                            ▼
                  │                              ¿las respuestas RATIFICAN
         última oportunidad                       o RECTIFICAN lo relevado
         de arreglar algo                         con el otro grupo?
```

Fijate dónde está la única compuerta de corrección: **antes de distribuir**. Una vez que el cuestionario salió, lo que esté mal armado ya no se arregla — los datos van a llegar rotos y el análisis no los puede reparar.

El análisis de las respuestas es una instancia de trabajo en sí misma, posterior a la recolección, y ocurre más adelante en la cursada.

---

## ✅ Checkpoint — Parte 1

Respondé sin volver a mirar el apunte. Son preguntas conceptuales, formato de parcial: primera oración que ya responda, terminología de la materia, dos o tres oraciones.

1. ¿Por qué pedir nombre y apellido al inicio de un cuestionario afecta la calidad de las respuestas, incluso cuando el instrumento no garantiza anonimato real de todos modos?

2. Si no se pide identificación, ¿qué tipo de preguntas permiten igualmente caracterizar a la población? Nombrá tres y explicá las dos funciones que cumplen en el análisis.

3. ¿Qué ventaja concreta tiene una pregunta con valores discretos sobre una pregunta abierta, al momento de analizar las respuestas?

4. Nombrá los tres problemas de incluir preguntas abiertas y explicá en qué caso una abierta sí está justificada.

5. Un cuestionario pregunta con cuánta anticipación te gustaría avisar una cancelación y deja el campo libre. Tenés una entrevista previa con los profesores donde salió que necesitan tres horas de aviso. ¿Qué dos problemas tiene la pregunta y cómo la corregís?

6. ¿Qué significa que un cuestionario sirva para *ratificar o rectificar* lo relevado en una entrevista, y qué condición de diseño hace falta para que eso sea posible?

7. ¿Por qué "muy frecuentemente" es una opción de respuesta problemática? ¿Cuándo conviene reemplazarla y por qué?

8. ¿Qué tres cosas debe contener la introducción de un cuestionario antes de distribuirlo, y qué problema concreto aparece si falta?

9. Un cuestionario para el centro de entrenamiento incluye la pregunta "¿te parece que hay pocas bicicletas?". ¿Está dentro del alcance? Justificá con el criterio de filtrado.

10. Más allá de la prolijidad, ¿por qué la ortografía y la puntuación de un cuestionario son un problema de calidad del instrumento y no solo de presentación?

---

## Qué viene en la Parte 2

Hasta acá dimos por sentado que el cuestionario era la herramienta correcta. En la Parte 2 damos un paso atrás: **cómo se elige la técnica de elicitación**. Las etapas que toda técnica atraviesa, y las ventajas, desventajas y —sobre todo— los **riesgos** de la entrevista, el cuestionario y la observación, con las formas concretas de mitigarlos.

---

**FIN DE LA PARTE 1 — Clase 06**
