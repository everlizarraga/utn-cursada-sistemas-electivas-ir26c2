# Clase desde cero — RF y RNF — Módulo 3: El requerimiento no funcional

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Eje:** Centro de Entrenamiento Vida Sana
**Marcas:** 🔴 central · 🟡 secundario · 🟢 al pasar · 🕳️ madriguera · ✏️ tu turno

---

## Sobre este documento

**Qué cubre:** qué restringe un RNF y de dónde sale · la estructura objeto + atributo + valor + unidad, y la condición de medición · el verbo "ser" y por qué el actor desaparece · qué hacer cuando no hay unidad (un canal, un medio, una tecnología) · cómo se escribe un RNF sobre un componente (la credencial, el lector) · RNF de una función y RNF transversales · el catálogo de atributos (ISO/IEC 25010) · las palabras que suenan técnicas y no miden nada, con la diferencia entre tiempo real y en línea · de dónde sale el número cuando el enunciado no lo trae.

**Qué NO cubre:** cómo evaluar un RNF ya escrito contra las características de calidad (M4).

## De dónde venís

Del M2: sabés escribir un RF con rol + verbo + objeto en presente, y sabés que en la limpieza del Paso 5 quedaron cosas afuera: "por WhatsApp", "en 2 segundos", "con una credencial", "tiene que tardar poco". Este módulo es para eso que quedó afuera.

---

## 1. 🔴 El caso: "tiene que tardar poco"

En la mesa, los profesores dijeron que tomar asistencia en papel les llevaba **15 o 20 minutos** por clase. El equipo escribió:

```
El registro de asistencia tiene que tardar poco.
```

Y alguien preguntó: **¿cuánto es poco?** Silencio. Se negoció en voz alta: ¿10 segundos? Mucho. ¿5? ¿3? *Viste cuando aparecen los tres puntitos y decís "ok"…* Quedó en **2**. Y apareció una segunda aclaración importante: **el tiempo es del sistema, no del socio.** No es que el socio tiene 2 segundos para pasar la credencial; es que desde que la pasa hasta que el sistema confirma no pueden pasar más de 2 segundos.

Lo que quedó escrito:

```
✅  El tiempo máximo de confirmación del registro de asistencia,
    desde que el socio pasa su credencial, es de 2 segundos.
```

Fijate lo que pasó. "Poco" era una **opinión**; "2 segundos desde que pasa la credencial" es algo que **se mide con un cronómetro**. Y fijate también qué desapareció de la oración como protagonista: el socio está, pero como referencia del evento, no como sujeto. El sujeto es *el tiempo máximo de confirmación*. Eso es un RNF.

## 2. 🔴 Qué es un RNF y de dónde sale

El RF es fácil: dice lo que el actor quiere lograr. El RNF hace otra cosa: **eso que el actor quiere, lo va a lograr, pero bajo ciertas condiciones.** El RNF *restringe* al RF. Cuando alguien diseñe o construya la solución, va a tener que asegurarse de que esas condiciones se cumplan.

Los RNF especifican las **cualidades** del producto y actúan como **restricciones que limitan el diseño de la solución**: propiedades, criterios de calidad o restricciones que debe cumplir el sistema, sus datos, sus funcionalidades o sus componentes. Determinan **qué tan bien** el sistema hace lo que hace: velocidad, disponibilidad, seguridad, usabilidad, apariencia, con qué tecnología.

**De dónde salen.** De tres lugares:

1. **De la factibilidad.** ¿Hay dinero? ¿Hay gente capacitada? ¿Hay tiempo? Cada respuesta, bajada al detalle, se vuelve una restricción: la plata restringe la infraestructura, la gente restringe la tecnología, el tiempo restringe el alcance.
2. **De la calidad esperada.** Lo que el actor espera de la función además de que exista: que sea rápida, que no se caiga, que la pueda usar sin capacitación.
3. **De la tecnología y el entorno.** Un lector de credenciales, una pantalla, una integración con un medio de pago, el sistema operativo del celular.

Y una consecuencia que decide todo lo demás: **su característica más importante es que deben ser medibles o verificables.** Un RNF que no se puede medir no se puede verificar, y lo que no se puede verificar no se puede exigir. "Poco" no se exige. "2 segundos" sí.

## 3. 🔴 La estructura: objeto + atributo + valor + unidad

Esta es la forma con la que se corrige.

```
   El tiempo máximo de confirmación   del registro de asistencia   es de   2   segundos
   └──────────────┬───────────────┘   └────────────┬───────────┘  └─┬─┘  └┬┘  └───┬────┘
              ATRIBUTO                          OBJETO            SER   VALOR   UNIDAD
       la cualidad que se mide            el componente o proceso
                                          al que pertenece esa cualidad
```

**Objeto.** El componente o proceso afectado: la notificación, el registro de asistencia, la pantalla, el medio de acceso.

**Atributo.** La cualidad del objeto que se va a medir: tiempo máximo de respuesta, disponibilidad, tamaño, medio, cantidad de pasos.

**Valor.** El número esperado: 2, 99,9, 42, 30.

**Unidad.** La escala: segundos, porcentaje, pulgadas, minutos, clicks.

**Condición de medición (cuando hace falta).** Desde qué evento se cuenta, en qué horario, para quién: *desde que el socio pasa la credencial*; *en horario de apertura*; *para el 80% de los profesores*. Sin la condición, muchos valores no se pueden medir de forma unívoca: ¿2 segundos desde cuándo?

Tres reglas que salen de la estructura:

- **Me centro en el atributo de ese objeto.** Siempre hay un objeto; el objeto está asociado a lo que quiero medir; el atributo es *qué* del objeto mido; valor y unidad dicen *cuánto*.
- **Si cambia el objeto, cambia el valor.** El tiempo máximo de una notificación puede ser 2 segundos; el de un reporte de socios morosos, 3; el de un cierre de caja mensual, 2 minutos. No hay un "tiempo de respuesta del sistema": hay uno por objeto.
- **El sujeto de la oración es el atributo del objeto.** No el sistema, no el actor. Vas a §5 para entender por qué.

> **Para el parcial, si te preguntan:** *¿Cómo se redacta un requerimiento no funcional para que sea verificable?*
> Con la estructura objeto + atributo + valor + unidad, más la condición de medición cuando corresponde: se identifica el componente o proceso afectado, la cualidad que se va a medir, el límite numérico esperado y su escala. Ejemplo: "El tiempo máximo de confirmación del registro de asistencia, desde que el socio pasa su credencial, es de 2 segundos": objeto: registro de asistencia; atributo: tiempo máximo de confirmación; valor: 2; unidad: segundos; condición: desde que pasa la credencial.

### 3.1 Cinco ejemplos armados, uno por familia de atributo

| RNF | Objeto | Atributo | Valor | Unidad | Condición |
|---|---|---|---|---|---|
| El tiempo máximo de notificación al socio, desde el evento que la origina, es de 2 segundos. | notificación | tiempo máximo de entrega | 2 | segundos | desde el evento |
| La disponibilidad de la aplicación es de al menos el 99,9% del tiempo en horario de apertura (lunes a sábados de 8 a 20). | aplicación | disponibilidad | 99,9 | porcentaje | en horario de apertura |
| El tiempo máximo para completar la inscripción a una clase es de 5 minutos, en la primera ejecución y sin asistencia, para el 80% de los socios. | inscripción a una clase | tiempo de aprendizaje | 5 | minutos | primera vez, sin ayuda, 80% de los socios |
| Al menos el 80% de las funcionalidades especificadas se pueden probar con pruebas automatizadas. | funcionalidades del sistema | capacidad de ser probado | 80 | porcentaje | — |
| El tiempo máximo de instalación de la aplicación en un celular Android es de 10 minutos, sin intervención de soporte. | aplicación | tiempo de instalación | 10 | minutos | Android, sin soporte |

Mirá el tercero, porque tiene una sutileza: **combina dos métricas**. El tiempo (5 minutos) y la cobertura (80% de los socios). ¿Por qué 80 y no 100? Porque siempre va a haber alguien a quien le cueste más, y un RNF que exige que *todos* aprendan en 5 minutos no es realista. Si estás por debajo del 80%, tenés algo que cambiar: las pantallas, la tipografía, la capacitación.

## 4. 🔴 Cuando no hay número: canales, medios y componentes

Este es el caso que más confunde, porque la estructura de §3 tiene un "valor" y una "unidad", y a veces lo que hay que restringir **no es una magnitud**.

### 4.1 El canal de notificación

Del RF "el socio recibe el aviso de las clases disponibles" quedó afuera "por WhatsApp o email". Un equipo intentó descomponerlo:

```
   Objeto:    notificación
   Atributo:  medio / canal de comunicación
   Valor:     WhatsApp / email
   Unidad:    ……
```

La unidad quedó vacía, y no porque falte algo: **WhatsApp es un medio, no un número.** El RNF se escribe igual, con el verbo ser:

```
✅  Los medios de las notificaciones a los socios de clases disponibles
    son WhatsApp o email.
```

Objeto, atributo, valor. Sin unidad, porque no se mide una magnitud: se **verifica una propiedad**. ¿Cómo se verifica? Mirando por dónde salen las notificaciones. Hay procedimiento, entonces es verificable.

⚠️ **Atención.** En material escrito de la materia vas a leer que el RNF debe ser "estrictamente medible" con unidad. Y a la vez, restricciones de canal como esta se aceptan como RNF legítimos. Las dos cosas se reconcilian así: **una restricción de canal, medio o tecnología es válida sin unidad, pero por sí sola no mide nada**; conviene **acompañarla con una métrica de cumplimiento**. Para el parcial: escribí la restricción y agregale al lado la métrica, por ejemplo *la cantidad de notificaciones enviadas por minuto es de al menos 100* o *el porcentaje de notificaciones recibidas con éxito es de al menos 99%*. Así cubrís las dos lecturas.

### 4.2 Un componente: la credencial que quedó colgada en M1

Ahora sí se cierra el hilo. La frase era:

```
❌  El socio tendrá una credencial para poder ingresar.
```

"Tener una credencial" no es una acción del socio: es **el medio** por el que se ingresa. Objeto: medio de acceso. Atributo/valor: es una credencial.

```
✅  El medio de acceso al establecimiento es una credencial.
```

Y acá viene la regla general, que vale para cualquier componente: cámara, lector, pantalla, balanza, impresora.

> **Un componente no es una función. Es un objeto al que se le pone una característica.**

"Tiene que tener una cámara" no dice nada exigible: ¿cualquier cámara? ¿una de rollo? Lo que se especifica es **qué característica tiene que cumplir ese componente**: *la resolución mínima de la cámara es de 8 megapíxeles*; *el tamaño de la pantalla del mostrador es de 21 pulgadas*; *el lector de credenciales es de tecnología NFC*. Objeto: el componente. Atributo: la característica. Valor y unidad si hay; si no hay (NFC), verificable por inspección.

En el gimnasio, el caso de identificación de socios es exactamente esto. El enunciado dice que hoy identifican con "3 letras del nombre y 2 del apellido", que produce homónimos. El RNF que reemplaza eso:

```
✅  El identificador de socio es un código único por socio, asignado por el sistema.
```

Objeto: identificador de socio. Atributo: unicidad. Valor: único. Verificable: ¿hay dos socios con el mismo código? No. Cumple.

> **Para el parcial, si te preguntan:** *"El sistema debe incorporar una cámara": ¿es un requerimiento funcional?*
> No. Una cámara es un componente del sistema, no una funcionalidad de un actor. La función es lo que el actor quiere lograr con ella (por ejemplo, "el dueño monitorea a su mascota" o "el profesor verifica la ocupación del sector"), y el componente se especifica como RNF con una característica verificable: "la resolución mínima de la cámara es de 8 megapíxeles".

### 4.3 ¿En un contexto académico puedo inventar el valor?

Sí, y se espera que lo hagas. El enunciado del gimnasio no dice cuántos segundos, ni cuántos megapíxeles, ni qué porcentaje. En un proyecto real vas y lo relevás o lo consultás con el proveedor. En un parcial o un TP, **ponés un valor razonable y lo declarás como supuesto**: "se asume 2 segundos; a confirmar con la Junta". Lo que **no** podés hacer es dejar el atributo sin valor, porque entonces no es verificable, ni poner un valor absurdo (una disponibilidad del 100%, un tiempo de 0 segundos), porque no es realista.

## 5. 🔴 El verbo es "ser" y el actor desaparece

Dos reglas de forma que salen de todo lo anterior.

### 5.1 "Es", no "debe ser"

```
❌  El tiempo máximo de registro debe ser de 30 segundos.
✅  El tiempo máximo de registro es de 30 segundos.
```

El RNF describe una propiedad que el sistema **tiene**. Se escribe como **afirmación de un valor**: es, son. "Debe ser" suena a deseo o recomendación; "es" es la especificación. Casi todos los RNF bien escritos tienen el verbo ser (*es*, *son*, o *será* cuando la propiedad se da en una situación futura acotada: *en modo de baja altura, los controles se ubican en la mitad inferior de la pantalla*).

### 5.2 El actor no aparece

En el RF, el sujeto es el actor. En el RNF, **el sujeto es el atributo del objeto** que estás midiendo, y **el actor desaparece**. Tampoco aparece "el sistema": que la propiedad se da en el contexto del sistema es obvio.

```
❌  El socio recibirá la confirmación en menos de 2 segundos.       (RF y RNF mezclados)
❌  El sistema responde en menos de 2 segundos.                      (el sistema como sujeto)
✅  El tiempo máximo de confirmación del registro de asistencia es de 2 segundos.
```

El actor puede aparecer **como referencia del evento** ("desde que el socio pasa la credencial") o **como población de la condición** ("para el 80% de los socios"), pero nunca como quien hace la acción. Si en tu RNF el actor está haciendo algo, tenés un RF adentro: separalo.

⚠️ **Atención.** Hay un RNF del gimnasio que vas a encontrar aceptado en material de la materia con el actor como sujeto: *"El socio necesita conexión de internet para completar el pago"*. Salió de corregir un "se necesita conexión" (¿quién?), y en su momento se lo dio por bueno. Pero contradice la regla de que el actor desaparece. **Para el parcial:** escribilo con el objeto como sujeto: *"El pago del plan requiere conexión de internet del dispositivo del socio"* u *"El medio de pago en línea requiere conectividad del dispositivo del socio"*. Fijate que además esto obliga a decidir **de quién es la conexión**: si el socio paga desde su casa, es un recurso que él necesita; si paga en el mostrador con un posnet, la conectividad es del centro, y ahí lo que se escribe es *conectividad redundante*, para que nadie se vaya sin pagar. Mismo requisito, dos objetos, según quién ejecuta.

> **Para el parcial, si te preguntan:** *¿Qué diferencia de forma hay entre la redacción de un RF y la de un RNF?*
> En el RF el sujeto es el actor y el verbo es de acción en presente ("El socio se anota en una clase"). En el RNF el sujeto es el atributo del objeto que se mide o restringe, el verbo es "ser" y el actor no aparece como quien actúa ("El tiempo máximo de confirmación de la inscripción es de 2 segundos"); puede aparecer solo como referencia del evento o de la población medida.

## 6. 🔴 RNF de una función y RNF transversales

Hay dos clases de RNF, y conviene saber cuál estás escribiendo.

**RNF de una función.** Restringen **un RF concreto**: cuando se escriba el escenario de ese RF, esa condición se tiene que dar. *El tiempo máximo de confirmación del registro de asistencia es de 2 segundos* pertenece al RF "el socio registra su asistencia". Viajan pegados, y por eso se pide **al menos un RNF por cada RF**: la prueba de "registrar asistencia" no está aprobada si la confirmación tarda 8 segundos. Un RF puede tener dos RNF (tiempo y canal, por ejemplo).

**RNF transversales.** Restringen **todo el sistema**, sin importar qué función se ejecute: el sistema operativo, el cumplimiento de la ley de datos personales, el doble factor de autenticación, la disponibilidad general, el identificador único de socio. Cualquier función que se haga va a pasar por esa restricción.

```
                  RNF transversales
        ┌──────────────────────────────────────────┐
        │  disponibilidad 99,9% · identificador     │
        │  único · datos personales · Android/iOS  │
        │                                          │
        │   RF: anotarse ──── RNF: 2 s             │
        │   RF: avisar   ──── RNF: WhatsApp        │
        │   RF: pagar    ──── RNF: APIs, conexión  │
        └──────────────────────────────────────────┘
```

Cuando en M5 vayas párrafo por párrafo, los RNF de función van a salir pegados a cada RF, y los transversales van a salir del contexto general del negocio (o de tus supuestos declarados). Los dos son legítimos.

## 7. 🔴 El catálogo: de dónde salen los atributos

Los atributos que un RNF mide **no se inventan**: están catalogados en una norma internacional, la **ISO/IEC 25010**, que describe el modelo de calidad del software (forma parte de la familia ISO/IEC 25000, llamada SQuaRE). La norma divide la calidad en características que se pueden analizar, probar y medir. Por eso el RNF tiene que ser medible: hay una norma certificable detrás, y para certificar hay que medir.

**Ocho características del modelo de calidad del producto**, cada una con sus subcaracterísticas. Cada subcaracterística es un **atributo** que podés usar:

| Característica | Subcaracterísticas (atributos) | Cómo se mide típicamente |
|---|---|---|
| **Adecuación funcional** | completitud funcional · corrección funcional · pertinencia funcional | % de casos de uso del negocio cubiertos; tasa de defectos por funcionalidad |
| **Eficiencia de desempeño** | comportamiento temporal · utilización de recursos · capacidad | tiempo de respuesta; % de CPU bajo carga; transacciones por segundo; usuarios concurrentes |
| **Compatibilidad** | coexistencia · interoperabilidad | % de conformidad con estándares (APIs); colisiones con otros programas |
| **Usabilidad** | inteligibilidad · aprendizaje · operabilidad · protección frente a errores del usuario · estética · accesibilidad | tiempo para completar una tarea por primera vez; cantidad de pasos o clicks; puntuación en escalas de usabilidad; cumplimiento de normas de accesibilidad |
| **Fiabilidad** | madurez · disponibilidad · tolerancia a fallos · capacidad de recuperación | % de tiempo operativo (los "nueves": 99,9%); tiempo medio entre fallos; tiempo de recuperación |
| **Seguridad** | confidencialidad · integridad · no repudio · responsabilidad · autenticidad | vulnerabilidades detectadas; tiempo de detección de una brecha; cifrado; doble factor |
| **Mantenibilidad** | modularidad · reusabilidad · analizabilidad · capacidad de ser modificado · capacidad de ser probado | % de cobertura de pruebas; complejidad del código |
| **Portabilidad** | adaptabilidad · facilidad de instalación · capacidad de ser reemplazado | tiempo de instalación; cantidad de plataformas soportadas |

La versión 2023 de la norma agrega **seguridad física (safety)**: prevención de daños físicos o materiales causados por fallos del software. Importa en IoT y dispositivos médicos; en el gimnasio, poco.

**Cómo se usa el catálogo.** Cuando tenés un RF y te preguntás "¿qué RNF le corresponde?", recorré la tabla: ¿qué tan rápido (eficiencia)? ¿qué tan fácil de usar (usabilidad)? ¿qué tan disponible (fiabilidad)? ¿con qué se integra (compatibilidad)? ¿quién puede verlo (seguridad)? De cada pregunta puede salir un RNF con su atributo ya nombrado.

Para el gimnasio, mapeado:

| RF | Pregunta del catálogo | RNF | Característica → atributo |
|---|---|---|---|
| El socio registra su asistencia | ¿qué tan rápido? | El tiempo máximo de confirmación es de 2 segundos | eficiencia → comportamiento temporal |
| El profesor registra el presente de su clase | ¿qué tan fácil de aprender? | El tiempo máximo para registrar el presente de una clase, la primera vez y sin ayuda, es de 30 segundos para el 80% de los profesores | usabilidad → aprendizaje |
| El socio paga su plan | ¿con qué se integra? | La integración con la plataforma de pago es por medio de APIs | compatibilidad → interoperabilidad |
| La Junta consulta los pagos por socio | ¿quién puede verlo? | Los pagos por socio son visibles solo para la Junta Directiva | seguridad → confidencialidad |
| (transversal) | ¿qué tan disponible? | La disponibilidad de la aplicación es de al menos el 99,9% en horario de apertura | fiabilidad → disponibilidad |

> 🕳️ **Madriguera — el modelo de calidad de uso**
> La ISO 25010 tiene un segundo modelo, de *calidad de uso* (eficacia, eficiencia, satisfacción, ausencia de riesgo, cobertura del contexto), que mide la experiencia del usuario en contexto. La materia no trabaja métricas de ese modelo.
> *Volvé al camino: el catálogo que usás es el de calidad del producto, las ocho de arriba.*

> **Para el parcial, si te preguntan:** *¿Qué es la ISO/IEC 25010 y para qué sirve al escribir RNF?*
> Es el estándar internacional que define el modelo de calidad del software, dentro de la familia ISO/IEC 25000 (SQuaRE). Divide la calidad del producto en ocho características (adecuación funcional, eficiencia de desempeño, compatibilidad, usabilidad, fiabilidad, seguridad, mantenibilidad y portabilidad), cada una con subcaracterísticas medibles. Sirve como catálogo de los atributos que un RNF puede restringir, y como garantía de que ese atributo se puede medir.

## 8. 🔴 El RNF compromete: el caso de la disponibilidad

Antes de cerrar, un aviso sobre lo que un número implica.

*La disponibilidad de la aplicación es del 99,9%.* Suena a un número que se tira y listo. Pero pensá qué significa: **no se cae**. Y si se cae, hay que poder seguir operando en breve. Eso quiere decir que existe una contingencia: un sitio alternativo, algo que entra cuando lo principal falla. Si escribís 99,9% y no hay presupuesto ni infraestructura para esa contingencia, **nunca vas a lograr lo que escribiste**. El RNF no es una frase: es una exigencia sobre la arquitectura, el presupuesto y la operación. Por eso tiene que ser **realista**, y por eso quien lo escribe tiene que saber cómo se va a verificar: el equipo de operaciones necesita el registro de las caídas para calcular el porcentaje, y ante cada caída, un análisis de la causa.

En el gimnasio, un "quiero que esté disponible las 24 horas" se lleva a su forma general: disponibilidad, con porcentaje y ventana horaria. Y la ventana es honesta: de 8 a 20, lunes a sábados, porque fuera de eso el centro está cerrado y nadie va a pagar la contingencia de una madrugada.

> 🕳️ **Madriguera — SaaS y on-premise**
> Si la solución corre en la nube de un proveedor (*SaaS*), la disponibilidad se compra y el proveedor responde; si corre en infraestructura propia (*on-premise*), se construye y respondés vos. Cambia quién paga y quién atiende cuando se cae.
> *Volvé al camino: acá solo importa que la disponibilidad cuesta, y que el número compromete.*

## 9. 🔴 Las palabras que suenan técnicas y no miden nada

Tres palabras aparecen en casi todos los primeros RNF, y ninguna se puede verificar:

| Palabra | Por qué no sirve | Con qué se reemplaza |
|---|---|---|
| **"en tiempo real"** | ¿cuánto es? ¿2 segundos, 200 milisegundos? Y casi nunca es tiempo real de verdad (ver §9.1) | un tiempo máximo con unidad, desde un evento |
| **"online" / "en línea"** | ¿respecto de qué? ¿desde dónde? | el medio y la condición de acceso |
| **"automáticamente"** | ¿sin intervención de quién? | "sin intervención del personal", "sin asistencia de soporte" |

Y se suman **"rápido", "intuitivo", "amigable", "eficiente", "seguro"** a secas: adjetivos que cada lector mide con su propia vara. Cada uno se reemplaza por su atributo del catálogo con valor y unidad.

### 9.1 Tiempo real no es en línea

Esta distinción merece su espacio, porque "tiempo real" se usa en todos lados y casi nunca es cierto.

**Tiempo real** es cuando hay **un sensor que mide, un actuador que actúa en función de lo medido, y criticidad**: si no actúa a tiempo, hay un daño. El termostato de una cabina que mantiene entre 22 y 25 grados: el sensor mide, si baja de 22 el actuador manda calor, si sube de 25 manda frío. La puerta automática del aeropuerto: el sensor te detecta, el actuador la abre, y si no la abre te la comés. Eso es tiempo real.

**En línea** es cuando vos **entrás y mirás algo que está pasando ahora**, sin que nada actúe por sí solo. Ver a tu mascota por una cámara desde el celular no es tiempo real: es en línea. Nada reacciona porque la mascota se movió; vos entraste a mirar. Cuando la cámara de tu casa te manda una notificación de movimiento, la cámara actuó (eso sí tiene sensor y actuador), pero vos te enteraste en línea.

En el gimnasio, ¿hay algo en tiempo real? Prácticamente no: anotarse, avisar, pagar, consultar el presente son todas funciones en línea. Si alguien escribe *"el profesor ve en tiempo real quién llegó"*, lo que quiere decir es *"el profesor consulta en línea el presente de su clase"*, y el RNF que corresponde es de tiempo de actualización: *el tiempo máximo entre el registro de un ingreso y su visualización en la lista de presentes es de 5 segundos*.

**Ojo con tiempo real, con automático, con automáticamente:** son capciosos para la redacción, y en el parcial son un error si los usás sin valor.

> **Para el parcial, si te preguntan:** *¿Qué diferencia hay entre tiempo real y en línea?*
> Un sistema de tiempo real tiene un sensor que mide, un actuador que actúa en función de lo medido, y criticidad: si no responde a tiempo hay un daño (un termostato, una puerta automática). En línea es acceder a información actual sin que nada actúe por sí solo (ver una cámara desde el celular). La mayoría de lo que se vende como "tiempo real" es en línea, y en un RNF ninguna de las dos expresiones sirve sin un tiempo máximo con unidad.

---

## ✏️ Tu turno

Reescribí estos RNF con la estructura objeto + atributo + valor + unidad (+ condición), verbo ser, sin actor ni sistema como sujeto. Si el valor no está, inventalo razonable y marcalo como supuesto. Si alguno esconde un RF, separalo.

1. "El sistema debe procesar la actualización de una lista de espera (baja de un socio y oferta del cupo al siguiente inscripto) en un tiempo no mayor a 5 segundos."
2. "El sistema debe permitir que el 80% de los profesores puedan registrarse en el sistema en menos de 30 segundos."
3. "El inicio de sesión de los clientes debe realizarse en menos de 3 clicks."
4. "El presente de las clases debe estar disponible en todo el horario de apertura del gimnasio."
5. "Las notificaciones de cancelación de clase deberán ser enviadas por WhatsApp a los clientes en menos de 2 minutos desde la cancelación de la misma."
6. "El sistema debe garantizar la exactitud de los registros de horario, con una tasa de error del 0.1% en la asignación de turnos, evitando inconsistencias que afecten la confiabilidad de los datos de asistencia."

Pista para el 5, sin respuesta: adentro hay dos RNF (canal y tiempo) y una palabra del dominio que está mal ("clientes": en este negocio, el que va a la clase se llama socio; el cliente es la Junta).

## ✅ Checkpoint

1. ¿Qué es lo que un RNF restringe, y qué pasa con un RNF que no se puede medir?
2. Descomponé "la disponibilidad de la aplicación es de al menos el 99,9% en horario de apertura" en objeto, atributo, valor, unidad y condición.
3. ¿Por qué "si cambia el objeto, cambia el valor"? Dá dos objetos del gimnasio con tiempos distintos.
4. Un RNF sobre el canal (WhatsApp) no tiene unidad. ¿Es válido? ¿Qué le agregás para el parcial?
5. ¿Cómo se escribe un RNF sobre un componente como una cámara o un lector?
6. ¿Por qué el verbo del RNF es "ser" y no "debe ser"?
7. ¿Puede aparecer el actor en un RNF? ¿En qué lugar sí y en cuál no?
8. Diferencia entre RNF de una función y RNF transversal, con un ejemplo de cada uno.
9. ¿Para qué sirve la ISO 25010 cuando tenés un RF y no sabés qué RNF darle?
10. Explicá con el gimnasio por qué "el profesor ve en tiempo real quién llegó" está mal escrito y cómo queda.

## Qué viene en el Módulo 4

Ya sabés producir RF y RNF con la forma correcta. El módulo 4 es el otro lado del mostrador: **cómo se corrige**. Las seis características de calidad con su pregunta guía, la cohesión, por qué verificable y completo son cosas distintas, la lista DEO (defectos, errores y omisiones) y el checklist que te conviene pasar antes de entregar cualquier lista de requisitos.

**FIN DEL MÓDULO 3**
