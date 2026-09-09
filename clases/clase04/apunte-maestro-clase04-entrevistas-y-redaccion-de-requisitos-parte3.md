# 📘 APUNTE MAESTRO — Clase 04 · Entrevistas y redacción de requisitos — Parte 3

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Unidad:** `clase04` · Jueves 03/09/2026 · Presencial (Campus)
**Parte 3:** RF y RNF — el marco: qué tiene que cumplir un requerimiento, cómo se redacta un RF, cómo se redacta un RNF, y qué es una regla de negocio.

---

## Sobre esta parte

**Qué cubre:** las seis características de calidad que todo requerimiento debe cumplir, con su pregunta guía · el RF como definición del "qué" y sus dos niveles de redacción · el RNF como restricción que limita la solución, de dónde sale y la estructura objeto + atributo + valor + unidad que lo hace medible · la tabla comparativa RF vs. RNF · las reglas de negocio como tercera categoría que no hay que confundir.

**Qué viene después:** Parte 4 — ISO/IEC 25010, el catálogo de dónde salen las cualidades que un RNF puede medir, con ejemplos resueltos. Parte 5 — la defensa: escribir bien y detectar lo mal escrito, con los casos trabajados en clase.

**Marcas:** 🔴 central, evaluable · 🟡 secundario · 🟢 mencionado al pasar · 🕳️ madriguera.

## De dónde venís

De la clase 01: qué es un requerimiento funcional y uno no funcional. Esta parte no repite la definición: la afina, la vuelve operativa y le agrega las estructuras con las que la cátedra espera que los escribas. De la Parte 2: la información relevada en la mesa, que ahora hay que convertir en requerimientos. De Análisis de Sistemas: factibilidad.

---

## 1. 🔴 Antes de escribir: lo que un requerimiento tiene que cumplir

Arrancá con algo que pasó en la mesa, cinco minutos después de terminar la entrevista.

El equipo escribió: **"RF: agilizar el registro de asistencias."** Lo tachó casi enseguida. ¿Por qué? Porque *agilizar* no se puede verificar. ¿Cuánto es ágil? ¿Cómo sabés si lo lograste? Dos personas que lo lean van a entender cosas distintas. El requerimiento suena bien y no sirve para nada.

Eso es lo que estas seis características detectan. Son el filtro por el que pasa cualquier requerimiento —funcional o no funcional— antes de darse por escrito. Y son, casi palabra por palabra, el vocabulario con el que se corrige.

**No ambiguo (especificidad).** El requerimiento tiene la especificidad necesaria para que **todos lo interpreten de la misma manera**. Si dos personas pueden entender cosas distintas al leerlo, es ambiguo. *Agilizar* es ambiguo. *El tiempo máximo de registro es de 2 segundos* no.

**Consistente (coherencia).** No se contradice a sí mismo ni contradice otros requisitos. Y además, **está expresado desde el punto de vista del actor o interesado correspondiente**: se sabe de quién es, quién lo ejecuta o a quién afecta.

**Completo.** Tiene el detalle suficiente para respaldar el negocio: toda la información necesaria para entender qué se necesita **sin tener que adivinar** lo que falta.

**Realista.** Considera las restricciones del ambiente: se puede diseñar, desarrollar e implementar con los recursos disponibles del proyecto — tiempo, presupuesto, personal y tecnología.

**Rastreable (trazabilidad).** Se lo puede seguir durante todo el proyecto. De cualquier requerimiento tiene que poder identificarse:
- de dónde surgió,
- quién lo solicitó,
- qué componentes del sistema afecta,
- qué casos de uso, reglas de negocio o pruebas se relacionan con él.

**Verificable (testeable / medible).** Existe una forma **objetiva** de comprobar si se cumple o no. Acá la exigencia se parte en dos, y esa partición organiza el resto de la unidad:
- Los **RF** deben ser testeables mediante una **cantidad finita de pasos** que validen su comportamiento.
- Los **RNF** deben ser **estrictamente medibles**, usando una estructura de objeto, atributo, valor y unidad que vas a ver en la sección 3.

Las seis, como preguntas para hacerle a lo que acabás de escribir:

| Característica | Pregunta guía |
|---|---|
| No ambiguo | ¿Existe una única interpretación posible? |
| Consistente | ¿Se contradice consigo mismo o con otros requisitos? |
| Completo | ¿Contiene todos los elementos necesarios para comprenderlo y desarrollarlo? |
| Realista | ¿Puede implementarse con las restricciones del proyecto? |
| Rastreable | ¿Puede identificarse claramente su origen y sus impactos? |
| Verificable | ¿Puedo comprobar su cumplimiento? ¿Hay un procedimiento? |

> **Para el parcial, si te preguntan:** *¿Qué características debe cumplir un requerimiento bien especificado?*
> Debe ser no ambiguo (una única interpretación), consistente (no se contradice y está expresado desde el actor correspondiente), completo (no obliga a adivinar información faltante), realista (implementable con los recursos del proyecto), rastreable (se conoce su origen, solicitante e impactos) y verificable (existe una forma objetiva de comprobar su cumplimiento: pasos finitos para un RF, medición para un RNF).

## 2. 🔴 El requerimiento funcional: la definición del "qué"

Los RF describen **las acciones que el sistema debe ejecutar**. Definen *qué* debe hacer el sistema: los servicios, comportamientos o funcionalidades que tiene que proporcionar. Es lo que vos pretendés de tu solución, y se puede definir a nivel sistema o a nivel software.

Como principio, **los RF son independientes de la tecnología** con la que se implementen. "El socio registrará su ingreso" no dice si es con QR, con tarjeta magnética o con huella. Eso vendrá después, y probablemente como restricción no funcional.

Una especificación de RF exitosa tiene el **nivel de detalle suficiente** para que el desarrollador construya el producto correcto con el mínimo de aclaraciones adicionales. Ni tan abstracto que no se sepa qué construir, ni tan detallado que ya sea diseño.

### 2.1 Cómo se redacta: dos niveles

**Nivel alto — definición de capacidad.** Estructura simplificada: **verbo en infinitivo + objeto.**

> *Registrar alumno.*

Es la forma más abstracta, bien macro. Es el nivel del caso de uso: nombra la capacidad sin decir quién ni con qué datos.

**Nivel detallado — especificación técnica.** Estructura: **rol + verbo + objeto**, desglosando los parámetros de entrada para garantizar que el resultado sea testeable y consistente.

> *La **secretaría de alumnos** [ROL] **registrará / podrá registrar** [VERBO] **un alumno** [OBJETO] con su DNI, apellido, nombre, teléfono, email, fecha de ingreso y carrera.*
> Variable (x): datos del alumno.

Fijate qué hace cada pieza. El **rol** dice quién ejecuta: es lo que vuelve al requerimiento consistente desde el punto de vista del actor. El **verbo** es la acción. El **objeto** es sobre qué recae. Y la **variable** —los datos que entran— es lo que lo vuelve completo y testeable: sabés exactamente qué tiene que aceptar el sistema para que el RF se considere cumplido.

Al nivel alto se le agrega detalle para llegar al detallado: verbo + objeto, y después más detalle.

**Historia de usuario** es otra forma de escribir lo mismo, con la plantilla "como [rol], quiero [acción] para [beneficio]"; se menciona como alternativa que eventualmente se puede practicar, pero no es la estructura que se pide acá.

### 2.2 Los dos niveles resuelven una discusión que tuviste en la mesa

Cuando el equipo intentó escribir el RF de discapacidad, apareció la duda: **¿queremos que el profesor registre al socio con discapacidad, o que el socio se autoregistre?** Son dos cosas distintas, y parecía que había que elegir.

No hay que elegir todavía. A nivel alto, **"Registrar socio"** cubre las dos: la capacidad existe sin importar quién la ejecute. Podés tener ese requerimiento de ambos. Después, a nivel detallado, sí aparece el rol: *el profesor registrará al socio con…*, o *el socio se registrará como socio con discapacidad*, cada uno con sus datos. Un requerimiento a nivel alto puede abrirse en varios a nivel detallado, uno por rol.

> **Para el parcial, si te preguntan:** *¿Cómo se redacta un requerimiento funcional?*
> A nivel alto, con verbo en infinitivo + objeto ("Registrar alumno"), que define la capacidad. A nivel detallado, con rol + verbo + objeto más los parámetros de entrada ("La secretaría de alumnos registrará un alumno con su DNI, apellido, nombre…"), que lo vuelve testeable y consistente desde el actor.

## 3. 🔴 El requerimiento no funcional: cómo lograrlo, según restricciones

### 3.1 Qué es y de dónde sale

El RF es fácil de entender: dice lo que quiero hacer. El RNF es un poco más complicado, porque lo que hace es esto: **eso que vos querés, lo vas a poder lograr, pero bajo ciertas condiciones.** El RNF *restringe* al RF. Cuando hago el desarrollo o el diseño, tengo que asegurarme de que esas condiciones se cumplan.

Los RNF especifican **las cualidades del producto** y actúan como **restricciones que limitan el diseño de la solución**. Describen propiedades, criterios de calidad o restricciones que debe cumplir el sistema, sus datos, sus funcionalidades o sus componentes. Determinan **qué tan bien** el sistema realiza sus funciones: usabilidad, rapidez, confiabilidad, seguridad, apariencia.

¿De dónde salen esas condiciones? De algo que ya conocés de Análisis de Sistemas: la **factibilidad** — el análisis de si un proyecto puede hacerse. Tres elementos la componen: **¿hay dinero suficiente? ¿hay recursos capacitados? ¿hay tiempo para implementarlo?** Esos tres elementos, cuando se los baja al detalle, se traducen en requerimientos no funcionales. La plata restringe la infraestructura, la gente restringe la tecnología que podés usar, el tiempo restringe el alcance.

Y hay una consecuencia de fondo: **su característica más crítica es que deben ser estrictamente medibles.** Un RNF que no se puede medir no se puede verificar, y por lo tanto no se puede exigir. Vas a ver en la Parte 4 que ese "medible" no es un capricho: hay una norma internacional certificable detrás, y para certificar hay que medir.

### 3.2 La estructura: objeto + atributo + valor + unidad

Esta es la buena práctica que la cátedra espera, y con la que corrige. No es la única forma de escribir un RNF; es la que asegura que sepas **qué tenés que medir** y **cuál es el valor esperado**.

> **Objeto:** el componente o proceso afectado.
> **Atributo:** la cualidad a medir.
> **Valor:** el límite numérico esperado.
> **Unidad:** la escala de medición.

El ejemplo canónico:

> *El tiempo máximo de entrega de una notificación es de 2 segundos.*
> - **Objeto:** notificación
> - **Atributo:** tiempo máximo de entrega
> - **Valor:** 2
> - **Unidad:** segundos

Un RNF bien definido es **objeto + característica/restricción identificable + verificable.** Y el foco está en un lugar preciso: **me centro en la descripción del atributo de ese objeto.** Siempre aparece el objeto; el objeto está asociado a lo que quiero medir; el atributo es *qué* del objeto mido; el valor y la unidad dicen *cuánto*. Si cambia el objeto —de notificación a reporte—, cambia el valor del atributo que mido.

Desglosalo con un caso de la mesa. Los profesores decían que tomar asistencia en papel les llevaba 15 o 20 minutos; el equipo escribió que el registro de asistencia tenía que tardar poco. ¿Cuánto es poco? Se negoció en voz alta: ¿10 segundos? ¿5? ¿3? *Viste cuando aparecen los tres puntitos y decís "ok"…* Quedó en 2. Y se aclaró algo importante: **el tiempo es del sistema, no del socio.** No es que el socio tiene 10 segundos para escanear; es que desde que el socio escanea hasta que el sistema confirma no pueden pasar más de 2 segundos. Objeto: registro de asistencia (o su notificación). Atributo: tiempo máximo de respuesta. Valor: 2. Unidad: segundos.

Las cualidades que se pueden medir tienen su catálogo, y también sus formas típicas de medida. Esta tabla las resume; el catálogo completo, por norma, es la Parte 4.

| Propiedad | Medida |
|---|---|
| Velocidad (*speed*) | Transacciones procesadas por segundo · Tiempo de respuesta a usuario/evento · Tiempo de refresco de pantalla |
| Tamaño (*size*) | Mbytes · Cantidad de chips ROM |
| Facilidad de uso (*ease of use*) | Tiempo de capacitación · Cantidad de pantallas de ayuda |
| Confiabilidad (*reliability*) | Tiempo medio hasta el fallo · Probabilidad de no disponibilidad · Tasa de ocurrencia de fallos · Disponibilidad |
| Robustez (*robustness*) | Tiempo de reinicio tras un fallo · Porcentaje de eventos que causan fallo · Probabilidad de corrupción de datos ante un fallo |
| Portabilidad (*portability*) | Porcentaje de sentencias dependientes de la plataforma · Cantidad de sistemas destino |

### 3.3 El RNF condiciona la arquitectura: el caso de la disponibilidad

El ejemplo más común: *la disponibilidad de la solución tiene que ser del 99,9% del tiempo.* Suena a un número que se tira y listo. Pero pensá qué implica: esto **no se cae**. Y si se cae, tengo que poder seguir operando en breve. Eso significa que tengo algún esquema de contingencia —un sitio alternativo, algo que entra cuando lo principal falla— para lograr esa separación entre "se cayó" y "dejé de operar".

Ahora: si escribo 99,9% pero no tengo herramientas para armar esa contingencia —ni una lista de qué hacer, ni infraestructura, ni nada— **no voy a lograr nunca el cometido de la disponibilidad.** El RNF no es una frase: es una exigencia sobre la arquitectura, el presupuesto y la operación. Escribirlo compromete a construir lo que hace falta para cumplirlo. Por eso tiene que ser realista.

🕳️ **Madriguera — SaaS, on-premise y el soporte**
*SaaS* (software como servicio) es cuando el proveedor tiene la solución en su nube y te asegura el soporte y la disponibilidad; *on-premise* es cuando la solución corre en tu propia infraestructura. Cambia quién responde cuando algo se cae: con SaaS, el proveedor; on-premise, cuando pedís asistencia el proveedor tiene que confiar en que el incidente es de su solución y no de tu red — y el costo del soporte es distinto. *Volvé al camino — acá solo importa que la disponibilidad se compra o se construye, y en ambos casos cuesta.*

> **Para el parcial, si te preguntan:** *¿Cómo se redacta un requerimiento no funcional para que sea verificable?*
> Con la estructura objeto + atributo + valor + unidad: se identifica el componente o proceso afectado, la cualidad que se va a medir, el límite numérico esperado y su escala. Ejemplo: "El tiempo máximo de entrega de una notificación es de 2 segundos" — objeto: notificación; atributo: tiempo máximo de entrega; valor: 2; unidad: segundos.

## 4. 🔴 RF y RNF, lado a lado

| Criterio | Requisito Funcional (RF) | Requisito No Funcional (RNF) |
|---|---|---|
| **Propósito** | Define funcionalidades, servicios o comportamientos que el sistema debe proporcionar. | Define propiedades, restricciones o criterios de calidad que deben cumplir el sistema, los datos o las funcionalidades. |
| **Pregunta que responde** | ¿Qué debe hacer el sistema? | ¿Cómo lo hace el sistema? ¿Qué restricciones debe cumplir? |
| **Testeabilidad** | Se valida ejecutando una funcionalidad y verificando que el resultado esperado se obtenga, cumpliendo sus RNF asociados. | Se valida midiendo una propiedad o verificando el cumplimiento de una restricción. |
| **Relación con objetos del dominio** | Suele originar operaciones o casos de uso. | Suele asociarse a atributos, restricciones o reglas sobre objetos y funcionalidades. |
| **Dependencia tecnológica** | No debería depender de detalles de implementación. | Puede verse influenciado por restricciones técnicas, regulatorias o del entorno operativo. |
| **Origen** | Necesidades y objetivos de usuarios y stakeholders. | Necesidades de calidad, restricciones del negocio, normativas o limitaciones técnicas. |
| **Ejemplo** | El huésped puede reservar una cochera. | El tiempo máximo de confirmación de una reserva es de 2 segundos. |

Tres filas merecen una segunda lectura.

**Testeabilidad.** Mirá cómo se cruzan: el RF se valida ejecutándolo *cumpliendo sus RNF asociados*. Es decir, la prueba de "reservar cochera" no está aprobada si la confirmación tarda 8 segundos. El RNF viaja pegado al RF que restringe — por eso en la mesa se pidió **al menos un RNF por cada RF**, y por eso un mismo RF puede tener dos RNF (tiempo de respuesta y canal de notificación, por ejemplo).

**Relación con el dominio.** El RF suele convertirse en un caso de uso; el RNF, en una restricción sobre un atributo. Eso explica algo que vas a ver en la Parte 5: el verbo de un RNF suele ser **"es"** — un estado, un valor — y no una acción.

**Dependencia tecnológica.** El RF no elige tecnología. El RNF sí puede: "la integración con el medio de pago es por medio de APIs" es un RNF legítimo, porque restringe *cómo* se implementa "el socio pagará las cuotas".

## 5. 🔴 Reglas de negocio: la tercera categoría

Hay una tercera cosa que aparece en toda entrevista y que **no es RF ni RNF**, y confundirla con cualquiera de los dos es error corregible.

Una **regla de negocio** describe una política, restricción o norma **del negocio**, que existe **independientemente del sistema**.

> *Un cliente no puede solicitar un préstamo si tiene más de 3 cuotas impagas.*

Esa regla existe aunque el proceso se haga en papel, en Excel o en un sistema informático. No es algo que el sistema *hace* (RF), ni una cualidad que el sistema *tiene* (RNF). Es una condición del dominio que el sistema debe **respetar**.

Del centro de entrenamiento salieron varias en la mesa, y se las señaló como tales:
- *Las cuotas se cobran del 1 al 10 de cada mes.*
- *El socio debe tener la cuota paga para poder realizar actividades.*
- *Si una clase no tiene al menos tres inscriptos, se cancela.*
- *Solo los socios que avisaron una ausencia pueden recuperar la clase.*

Ninguna de esas es "el socio pagará las cuotas" (eso es el RF, nivel alto, bien macro) ni "el socio podrá pagar con tarjeta de crédito" (que ya es una especificación del medio, discutida en la Parte 5). Son las condiciones bajo las cuales el negocio opera, con o sin software.

> **Para el parcial, si te preguntan:** *¿Qué diferencia hay entre un requisito y una regla de negocio?*
> La regla de negocio es una política, restricción o norma propia del dominio de la organización, que existe independientemente del sistema (por ejemplo, "un cliente con más de 3 cuotas impagas no puede pedir un préstamo"). Los requisitos describen lo que el sistema debe hacer (RF) o las cualidades y restricciones que debe cumplir (RNF); el sistema debe respetar las reglas de negocio, pero no son requisitos del sistema.

---

## Info operativa de esta parte

- La cátedra publicó en el aula virtual su **guía de RF y RNF**, que es el documento contra el que se corrige la redacción. Este apunte la absorbe completa entre esta parte y la siguiente; no hace falta ir a buscarla para estudiar, pero es la referencia formal para citar en un entregable.
- En la ejercitación de la clase se pidió **al menos un RNF por cada RF**; se admitió que dos RNF restrinjan al mismo RF.

---

## Qué viene en la Parte 4

Los atributos que un RNF puede medir no se inventan: están catalogados en la ISO/IEC 25010, el modelo de calidad del producto de software. Ocho características, cada una con sus subcaracterísticas, cómo se mide y qué errores comunes la comprometen. Y cinco ejemplos resueltos, uno por característica, escritos con la estructura de esta parte.

**FIN DE LA PARTE 3**
