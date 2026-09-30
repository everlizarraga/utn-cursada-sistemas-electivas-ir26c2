# 📘 APUNTE MAESTRO — Clase 07 · Repaso de RF y RNF, simulacro y quiz — Parte 2

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Unidad:** `clase07` · Jueves 24/09/2026 · Virtual (Zoom)
**Parte 2:** el simulacro ParkingDog en salas, el quiz de repaso y la información operativa de la clase.

---

## Sobre esta parte

**Qué cubre:** el enunciado del simulacro (un parcial de 2023) y lo que se corrigió en las salas: quiénes son actores y quiénes no, por qué un sensor o una cámara no son funciones, y la diferencia entre tiempo real y en línea · el quiz de repaso, pregunta por pregunta, con lo que se aclaró de cada una · la información operativa: entregas, cuestionarios del integrador, y el formato del parcial del 01/10.

**Qué NO cubre:** la resolución completa del simulacro párrafo por párrafo. Eso está en la profundización de esta clase (`profundizacion-clase07-parkingdog-parrafo-a-parrafo`).

**Marcas:** 🔴 central, evaluable · 🟡 secundario · 🟢 al pasar · 🕳️ madriguera.

## De dónde venís

De la Parte 1: la sintaxis del RNF, el actor que desaparece, componente + característica, sistema = software + hardware. De las primeras clases: actores, herencia, inclusión y extensión.

---

## 1. 🔴 El simulacro: ParkingDog

Es un parcial de hace unos años (2023), y se usa como práctica desde entonces porque tiene el mismo formato que el parcial escrito: un enunciado con un componente de hardware, y dos consignas. Se resuelve en equipo, en la carpeta de Drive, y se entrega con feedback.

### 1.1 El enunciado

**Estacionamiento para Mascotas.** La empresa MascotaCare S.A. está desarrollando un nuevo concepto de cuidado canino: confort y seguridad para la mascota cuando no puede estar con su dueño por unas pocas horas. Solución ideal para supermercados o restaurantes donde los dueños no pueden entrar con el animal.

Lo llamaron **ParkingDog (PD)**: cuchas inteligentes y seguras instaladas en veredas, parques o puertas de locales, más una **app mobile** para interactuar con los dueños. Cada PD aloja un solo perro (se piensan prototipos para más de uno y para otras mascotas).

Los PD tienen **puerta de vidrio** para que el dueño vea a su perro, que queda cerrada al iniciar el servicio. Cada PD tiene **dispensador de agua**, **dispensador de comida**, y clima controlado (**entre 22 y 25 grados**). Tienen **cámara interna** para que el dueño vea a la mascota desde la app. La modalidad de agua, el tipo y la cantidad de comida dependen de **la raza** (la indica el cliente al iniciar) y **del peso**, obtenido con **una balanza electrónica** incorporada.

Los dueños tienen una **tarjeta de contacto** que lee **el lector del PD**, que identifica al usuario e indica si puede usarlo o no. Si el PD está en uso, solo puede finalizarlo quien lo inició con su tarjeta, o **personal autorizado con tarjeta de mantenimiento**. El dueño solo puede usar **un PD a la vez**.

Si el PD está disponible, la **pantalla táctil** informa que el usuario es válido y pide un **código numérico de autenticación**; si es correcto se abre la puerta y **el servicio comienza al abrirse la puerta**.

Acceso por **membresía mensual** por débito en tarjeta, con **1 hora bonificada**. El tiempo extra se factura **por hora sin fraccionamiento** (59 minutos = 1 hora; 61 minutos = 2 horas). Se abona excedente de **agua** (½ litro incluido, cada ½ litro adicional se paga) y de **alimento** (ración inicial según los parámetros, cada 200 gramos extra se paga).

Al finalizar el uso, el PD inicia una **secuencia de autolimpieza** (unos 2 minutos desde que el último usuario cierra la puerta) durante la cual no se puede usar. En **mantenimiento** no se puede usar hasta que un técnico lo reactive con su tarjeta.

Desde la app, el dueño puede **ver los PD disponibles en su zona**; si está usando uno, **ver a su mascota** por la cámara, **dispensarle más agua y alimento**, **verificar la temperatura**, **saber el tiempo que lleva**, **informar un inconveniente** y **comunicarse con soporte**.

**Consigna 1.** Trabajaste en la concepción del producto y en la app. Hay que lanzarlo: entregale a marketing la descripción de las funcionalidades que brindan el PD y la app a los dueños, para un folleto con especificaciones técnicas. **5 requerimientos funcionales y 5 no funcionales, de interés de los dueños de mascotas.**

**Consigna 2.** **Diagrama de casos de uso**: actores, casos de uso y relaciones, con nomenclatura UML.

### 1.2 Qué se corrigió en las salas

**Actores.** La primera duda de todos los equipos: ¿la mascota es actor? ¿El ParkingDog es actor?

- **La mascota no.** Parece que interactúa (come, toma agua), pero no tiene un objetivo frente al sistema. El que tiene el objetivo es el dueño, que la pone ahí.
- **El ParkingDog tampoco.** Es tentador ponerlo como actor secundario "porque interactúa con la app". Pero volvé a la definición: un sistema es un conjunto de elementos interrelacionados con un objetivo común. **La cucha es parte del sistema**, e incorpora componentes que permiten lograr el objetivo. Es parte de la solución, y en ese contexto no puede ser actor.
- **Los actores identificados:** el **dueño de la mascota**, y eventualmente el **técnico de mantenimiento**, que aparece más adelante en la descripción con su tarjeta.

**Componentes no son funciones.** Un equipo escribió como RF "tener un sensor que controle los niveles de comida y agua" y como RNF "informar cada 30 minutos los niveles". El sensor no es funcional, porque no está escrito desde el punto de vista del actor. ¿Cuál es la función que quiere lograr el dueño? **Saber si la mascota tiene comida y agua y cuánto consumió; dispensarle más; conocer el estado de la mascota.** ¿Cómo lo logra? Con un sensor, con una balanza. El sensor es el **cómo**.

Lo mismo con la cámara: "una cámara conectada a internet para monitoreo" no es un RF, porque no aparece el actor como sujeto. La función es **monitorear a la mascota**; la cámara, con sus características, es el RNF. **En los funcionales tiene que aparecer el actor. En los no funcionales aparece el elemento del sistema que se mide para lograr lo que el actor quiso.**

**"Monitorear en tiempo real": no.** El equipo quiso escribir "el dueño monitorea a la mascota en tiempo real". Y la pregunta fue: ¿por qué no es en tiempo real? Va en §2.

**Sobre los 5 RF y 5 RNF.** El texto dice lo que el cliente dice; hay que dar la funcionalidad sin necesidad de usar las palabras del texto. Y del mismo párrafo suelen salir un RF y un RNF: "el dueño solo puede usar un PD a la vez" está pegado al lector de tarjeta.

## 2. 🔴 Tiempo real no es en línea

En el ParkingDog hay cosas que **sí** funcionan en tiempo real, y hay que saber cuáles.

**Tiempo real: sensor + actuador.** La temperatura oscila entre 22 y 25 grados: eso es un RNF (el rango). ¿Dónde está el tiempo real? En que hay un **sensor** que mide, y si baja de 22 un **actuador** manda calor, y si pasa de 25 manda frío. Es un **termostato**. Tiene un sensor que verifica y un actuador que actúa en función de lo que el sensor censó, para cambiar el estado. Lo mismo el agua: el sensor dice "agua cero", se habilita el dispensador; pero no puede dispensar eternamente, dispensa hasta el tope, y otro sensor mide cuánto dispensó. Eso es tiempo real.

**En línea: entrás y mirás.** Ver a la mascota por la cámara **no** es tiempo real, porque nada actúa en función de que la mascota se movió. No hay un elemento que reaccione y diga "señor, fíjese que la mascota se movió". Si dejás una cámara en tu casa y te llega una notificación de movimiento, **la cámara actuó en tiempo real** (tiene sensor y actuador) y **vos te enteraste en línea**. En el PD, entrás a la app, ves la cámara porque estás conectado, y mirás qué hace la mascota. Eso es en línea.

**Y un tercer elemento: la criticidad.** El tiempo real tiene sensor, actuador, y **riesgo**: si no actúa a tiempo, pasa algo. La puerta automática del aeropuerto o de una farmacia: el sensor te detecta, la puerta se abre; si no se abre, te quedás sin nariz. Eso es tiempo real.

```
   TIEMPO REAL                              EN LÍNEA
   sensor mide → actuador actúa             entrás y mirás algo que pasa ahora
   + criticidad (si no actúa, hay daño)     nada actúa por sí solo
   termostato 22-25 · dispensador           ver la mascota por la cámara
   hasta el tope · puerta automática        consultar el tiempo transcurrido
```

**Ojo con "tiempo real", "automatizado", "automático":** son capciosos para la redacción. En todos lados te venden que todo es en tiempo real; no es tan así, es en línea. En el funcional hay que entender **qué se quiere hacer**; en el no funcional, **qué elementos se definen para lograrlo**.

> **Para el parcial, si te preguntan:** *¿Qué diferencia hay entre un sistema de tiempo real y una consulta en línea?*
> Un sistema de tiempo real tiene un sensor que mide, un actuador que actúa en función de lo medido, y criticidad: si no actúa a tiempo se produce un daño (un termostato, una puerta automática). En línea es acceder a información actual sin que nada actúe por sí solo (ver una cámara desde la app). La mayoría de lo que se llama "tiempo real" es en línea, y ninguna de las dos expresiones sirve en un RNF sin un valor con unidad.

## 3. 🔴 El quiz de repaso

Ocho preguntas en modo competencia, con lo que se aclaró de cada una. Es un adelanto del tipo de pregunta del parcial.

### 3.1 Qué y cómo, en un contexto de reservas

Unir con flechas: dado un sistema de reservas de alojamiento, qué es el **qué** (el caso de uso: *registrar propietario*, *consultar casa disponible*) y qué es el **cómo** (la restricción: el medio, el mensaje, el objeto). La mayoría acertó. Es la misma distinción de toda la Parte 1.

### 3.2 Herencia entre actores

Tres actores: alumno, docente y usuario. Alumno y docente comparten las interacciones definidas para usuario (por ejemplo, iniciar sesión). ¿Cómo se modela?

- A. El alumno y el docente heredan de usuario. ✅
- B. Usuario hereda de alumno y docente.
- C. Alumno y docente incluyen a usuario.
- D. Usuario extiende a alumno y docente.

**Es un error frecuente de parcial**: acá es donde se suele pisar el palito. La correcta es **A**: en el diagrama, alumno y docente heredan de usuario, que es el que efectivamente tiene el caso de uso.

Dos aclaraciones que salieron:

- **"Usuario" como actor no está mal en este contexto.** No se puede unificar a docentes y alumnos en un concepto del negocio ("comunidad académica" queda disperso), pero tanto el docente como el alumno **son usuarios del SIU Guaraní**. Por eso se habilita "usuario".
- **Inclusión y extensión no son relaciones entre actores.** Son relaciones **entre casos de uso**. No se incluye un actor en otro. Quien puso C o D confundió la naturaleza de la relación.

> **Para el parcial, si te preguntan:** *Alumno y docente comparten las interacciones definidas para usuario. ¿Cómo se modela?*
> Alumno y docente heredan de usuario: se dibuja la generalización entre actores, con usuario conectado al caso de uso compartido. Inclusión y extensión no aplican porque son relaciones entre casos de uso, nunca entre actores.

### 3.3 Dos stakeholders con requisitos incompatibles

El cliente dice que se tiene que poder modificar una reserva hasta cinco minutos antes; el área gerencial dice que no se permiten modificaciones después de 24 horas antes. ¿Cómo lo resolvés? Respuesta libre; salió una nube de palabras:

*Consultar · llegar a un acuerdo · negociar con los stakeholders y definir cuál queda · mediar · entender el porqué de la restricción · detectar y documentar el conflicto · ver con cada stakeholder la necesidad de su pedido · un tiempo intermedio · pros y contras · solicitar la definición del cliente.*

Está todo bien. Y una precisión: **acá el que paga es el cliente**. "Yo quiero modificar cinco minutos antes; el área gerencial me trae un problema; yo pago la solución, chau": no hay negociación posible, o por lo menos se negocian otros valores que no sean cinco minutos. Entender por qué quieren ese requisito y la justificación de cada uno es lo que se hace.

### 3.4 Voz pasiva

¿Cuál presenta voz pasiva?

- El profesor registra asistencia.
- El socio reserva una clase.
- **El huésped deberá ser validado por un representante.** ✅
- El sistema notifica al usuario.

La tercera. Lo bueno que tiene es que **dice quién lo hace** (por un representante). Lo peor hubiera sido "el huésped deberá ser validado", y listo: ¿quién lo valida? Peor todavía.

De acá salió una casi-regla: **en el caso de uso, usá presente**. Actor, verbo en presente, objeto: no hay margen de error. Cuando empezás a conjugar en futuro ("deberá ser validado"), se arma algo. **Presente indicativo, afirmativo, diciendo quién tiene la necesidad o la responsabilidad.** No quedan dudas.

Y se conecta con la corrección de las minutas: **"se acordó", "se identificó", "se llegó a un acuerdo"**. "Se acordó" es lo peor, porque hubo integrantes en esa reunión, y quizás no todos estaban de acuerdo; hubo una parte que acordó. Si después hay que reclamar el cumplimiento de ese acuerdo, o si esa definición no se cumplió, **hay que saber quién avaló y a quién reclamarle**. "La junta directiva acordó que los profesores no toman más asistencia": ahí está el responsable; no le reclames a los profesores. Por eso hay que evitar el "se" impersonal y la voz pasiva con sujeto tácito: los responsables de las decisiones tienen que quedar claros, porque impactan cuando el proyecto avanza.

Y la cuarta opción, "el sistema notifica al usuario", no es voz pasiva, pero **no se redacta desde el sistema**: se escribe desde el actor, *el usuario recibe una notificación*.

### 3.5 Verificable no es lo mismo que completo

"Este requisito es correcto porque podemos probarlo; por lo tanto, está completo." ¿Verdadero o falso? Opciones: son propiedades diferentes · verdadero solo para los funcionales · falso, no puede ser verificable · verdadero, un verificable es completo necesariamente.

**Son propiedades diferentes**, e independientes. Un requisito puede ser medible, lo podés probar en una cantidad finita de pasos, y eso no quiere decir que esté completo. Conviene pensarlo con el **contraejemplo**, como en Discreta: *el inicio de sesión es con credenciales*. Lo puedo probar (entro con mis credenciales), pero ¿qué credenciales? ¿mail, contraseña, usuario? ¿quién las creó? No está completo; tengo muchas preguntas; se puede interpretar de varias maneras.

### 3.6 Las características de calidad, de memoria

Sin abrir el documento: las características que tiene que cumplir un requisito. Las respuestas correctas eran las de la base (no ambiguo, consistente, completo, realista, rastreable, verificable). Aparecieron además "escrito desde el punto de vista del usuario" y "medible", que están bien. Y apareció "claro": ¿cómo medís que algo es claro? Para el que escribió el pliego de las impresoras estaba claro que las copias las garantizaba el organismo; para el que lo leyó, que las garantizaba la impresora. "Claro" se da porque es **no ambiguo**. Hay que elegir las palabras.

### 3.7 Análisis sintáctico de un RNF

Unir cada parte de la oración con objeto, atributo, valor y unidad. Los dos que quedan más fijos son la resolución de una foto y el tiempo de notificación:

> *La resolución máxima de la foto es de 1080 × 1920 píxeles.* Objeto: foto · Atributo: resolución máxima · Valor: 1080 × 1920 · Unidad: píxeles.

### 3.8 Inclusión o extensión: el descuento

Un modelo tiene *Comprar producto* ──include──▶ *Aplicar descuento*, porque **algunos** clientes tienen descuento. ¿Qué problema tiene?

- A. Ninguno: include representa comportamiento opcional.
- B. Debería usar extend, porque el comportamiento ocurre opcionalmente.
- C. Debería usar herencia entre casos de uso.
- D. Debería eliminar el caso de uso porque los descuentos pertenecen al dominio.

Por lo que ya sabés de las relaciones: la inclusión es lo que se hace **siempre**, adentro del flujo; la extensión es lo excepcional, **bajo condición**. "Algunos clientes tienen descuento" es una condición. La respuesta es **B**: *Aplicar descuento* extiende a *Comprar producto*.

> **Para el parcial, si te preguntan:** *"Comprar producto" incluye "Aplicar descuento", pero solo algunos clientes tienen descuento. ¿Está bien modelado?*
> No. La inclusión representa comportamiento que se ejecuta siempre dentro del flujo del caso de uso base. Un comportamiento que ocurre solo bajo una condición (tener descuento) se modela con extensión: "Aplicar descuento" extiende a "Comprar producto".

## 4. 🔴 Información operativa de la clase

### 4.1 Entregas y correcciones

- **Simulacro ParkingDog:** se termina de trabajar y se entrega el **viernes 25/09 a las 19:00**, último llamado. Se entrega el **link al Lucidchart o un documento editable**. **Nunca PDF**, porque no se puede escribir encima para corregir. A cada equipo se le dieron pautas en su sala.
- **Casos de uso sobre los requisitos de otro equipo** (el trabajo de la clase anterior): se revisan los documentos compartidos; si querés agregar o resolver algo más, hay tiempo hasta el **viernes 25/09 a las 19:00**.
- **Minutas:** todos recibieron devolución. Atender lo corregido: carátula, contenido, objetivo, y la estética (lectura agradable).

### 4.2 Los cuestionarios del integrador

La consigna era corregirlos según la devolución dada en clase y **distribuirlos** a los socios para tener respuestas. Ningún equipo los envió (se esperaba una devolución escrita, o no quedó claro que había que hacerlo). Consecuencias:

- Hay una **devolución general escrita**, la misma para todos, que se sube como corrección a cada equipo. Aplicar lo que corresponda: agregar una carátula y una introducción, ordenar las preguntas, revisar que las que no tienen que ser abiertas no lo sean.
- Como no se enviaron, **no se toman como material para la clase siguiente** (la de la entrevista).
- La idea sigue en pie: **corregir, distribuir**, y trabajar el análisis de las respuestas **después del parcial de entrevista**.

### 4.3 El parcial del 01/10: entrevista

- **Modalidad:** **role-playing**. Es la dinámica que se hizo en clase con la entrevista (tu grupo y el otro grupo) y la de negociación. Esas fueron las prácticas.
- **Enunciado:** llega el **viernes 25/09**, con el contexto sobre el que hay que preparar las preguntas, qué se puede y qué no se puede preguntar, y cómo ir preparado **según el rol que te toque**. Te puede tocar el rol de **cliente**: en ese caso, ¿qué responderías? Hay que tener una idea del contexto de los dos lados. Al final del enunciado va una **mini rúbrica**.
- **El contexto es simple**, algo que se viene hablando. Lo que importa es una buena entrevista para tener un buen resultado. **Al final sale la minuta.**
- **Se evalúa** más que la entrevista en sí: las habilidades del entorno de la entrevista: ser receptor, ir cambiando la entrevista a medida que avanza, chequear cada requisito, manejar el tiempo.
- **Fecha, hora y lugar:** jueves **01/10 a las 19:00, presencial en Campus**. Los horarios de cada reunión se organizan; no son todas a las 19.
- **Es muy difícil de recuperar.** La recomendación: si podés, tomate el día de estudio; si es complicado, se firma certificado.

### 4.4 Otros

- El **TP de investigación** ya está publicado en el aula.
- **Se van a subir más ejercicios de casos de uso** y de redacción, para que el parcial no sorprenda.
- Sobre **elicitación**, el único tip: leer el material de lectura de técnicas de elicitación que está en el aula virtual, donde están todas las técnicas que hay que saber.

---

## ✅ Checkpoint — Parte 2

1. ¿Por qué la mascota no es actor del ParkingDog? ¿Y por qué la cucha tampoco?
2. ¿Cuáles son los dos actores identificados en el simulacro?
3. "Tener un sensor de comida" no es un RF. ¿Cuál es la función del dueño, y qué lugar ocupa el sensor?
4. ¿Qué tiene un sistema de tiempo real que no tiene una consulta en línea? Dá el ejemplo del termostato y el de la cámara.
5. ¿Por qué "el dueño monitorea a la mascota en tiempo real" está mal escrito?
6. Alumno y docente comparten las interacciones de usuario: ¿qué relación se usa y cuáles no aplican entre actores?
7. ¿Qué hace el ingeniero de requisitos ante dos stakeholders con pedidos incompatibles, y quién decide?
8. ¿Por qué "se acordó" en una minuta es un problema? ¿Cómo se escribe?
9. ¿Un requisito verificable es necesariamente completo? Dá el contraejemplo.
10. "Comprar producto" incluye "Aplicar descuento", solo para algunos clientes. ¿Qué está mal?
11. ¿Cómo es el parcial del 01/10, qué se evalúa, y qué sale al final?

**FIN DE LA PARTE 2 — FIN DEL APUNTE MAESTRO DE LA CLASE 07**
