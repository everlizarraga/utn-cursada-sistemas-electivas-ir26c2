# 🔬 PROFUNDIZACIÓN — Clase 07 · ParkingDog párrafo por párrafo

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Unidad:** `clase07` · Tema único: resolver el simulacro ParkingDog con el método completo
**Marcas:** 🔴 central · 🟡 secundario · 🟢 al pasar · 🕳️ madriguera

---

## Sobre este documento

Un solo tema: **cómo se resuelve el simulacro ParkingDog de punta a punta**, párrafo por párrafo, con el mismo método que se aplica al gimnasio: de cada párrafo, qué RF, qué RNF, qué regla de negocio, qué preguntas quedan, y qué no sale de ahí. Después, las dos consignas del simulacro resueltas (5 RF + 5 RNF para el folleto, y el diagrama de casos de uso), los errores comunes que aparecieron al resolverlo, y ejercicios con respuestas.

**Qué se asume:** el apunte maestro de la clase 07 (el enunciado completo está en su Parte 2, §1.1), y las reglas de redacción de RF y RNF de las clases 04 y 06. Acá no se repiten: se aplican.

**Sobre los valores:** el enunciado trae algunos números (22 a 25 grados, ½ litro, 200 gramos, 2 minutos, 1 hora). Cuando un RNF necesita un valor que el enunciado no trae, se inventa uno razonable y se marca `[supuesto]`. Es lo que se espera en un parcial.

---

## 1. 🔴 Antes de escribir: actores y límite del sistema

Lo primero, siempre, es decidir **qué está adentro del sistema y quién es actor**. En este enunciado la trampa está servida, porque hay un objeto físico con nombre propio (la cucha) y un ser vivo (el perro).

```
              ┌────────────────── SISTEMA ──────────────────┐
              │                                              │
  [Dueño de   │  app mobile        cucha (PD):               │   [Técnico de
   mascota] ──┤                    lector de tarjeta,        ├── mantenimiento]
              │  software de       pantalla táctil, puerta,  │
              │  gestión: membre-  cámara, dispensadores,    │
              │  sías, servicios,  balanza, clima, sensores   │
              │  facturación                                  │
              └──────────────────────────────────────────────┘
                     ▲                          ▲
             [Plataforma de pago]        [Soporte técnico]
```

**Actores primarios:** el **dueño de la mascota** (tiene casi todos los objetivos) y el **técnico de mantenimiento** (finaliza servicios con su tarjeta, pone el PD en mantenimiento y lo reactiva).

**Actores secundarios:** la **plataforma de pago** (el débito de la membresía y de los excedentes se hace contra un sistema externo), **soporte técnico** (la app permite comunicarse con él: es quien recibe), y **el Tiempo** para todo lo que se factura por hora y se mide en minutos.

**No son actores:**
- **La mascota.** Come, toma agua, se la ve por la cámara, pero no tiene ningún objetivo frente al sistema: el objetivo es del dueño que la deja.
- **El ParkingDog.** Es parte del sistema. Un sistema es un conjunto de elementos interrelacionados con un objetivo común, y la cucha es uno de esos elementos, con sus componentes adentro. Ponerlo como actor secundario "porque interactúa con la app" es el error más frecuente de este enunciado.
- **Los componentes:** lector, cámara, balanza, dispensadores, termostato. Están adentro.
- **MascotaCare S.A.** Es la empresa que pide el sistema (el cliente), no un rol que lo use. Si apareciera "el administrador de MascotaCare consulta la facturación", sería otro actor; el enunciado no lo trae.

## 2. 🔴 Párrafo por párrafo

El formato: 📄 párrafo · 🔍 qué hay · ✅ RF · 📏 RN · ⚙️ RNF · ❓ preguntas · 🚫 lo que no sale.

### Párrafo 1 — El concepto

📄 *La empresa MascotaCare S.A. está desarrollando un nuevo concepto orientado al cuidado canino, brindando el mejor confort posible y seguridad a la mascota cuando no pueda estar al cuidado de su dueño por unas pocas horas.*

🔍 Contexto puro. "El mejor confort posible" y "seguridad" son objetivos de negocio, no requisitos: no se miden. Lo único aprovechable es el dominio: cuidado canino, pocas horas.

✅ RF: ninguno · 📏 RN: ninguna · ⚙️ RNF: ninguno.

❓ P-01. ¿"Pocas horas" tiene un máximo? (Va a importar para la facturación.)

🚫 "El sistema garantiza la seguridad de la mascota": no se puede verificar. La seguridad se traduce en RNF concretos más adelante (puerta cerrada, clima, identificación).

### Párrafo 2 — Dónde se usa

📄 *Es una solución ideal para supermercados o restaurantes, a los cuales los dueños de las mascotas no pueden ingresar con el animal.*

🔍 Contexto de uso. Nada que un actor haga con el sistema.

✅ ninguno · 📏 ninguna · ⚙️ ninguno · ❓ ninguna · 🚫 nada.

### Párrafo 3 — Qué es el ParkingDog

📄 *A este concepto lo llamaron ParkingDog (PD), el cual consta de cuchas inteligentes y seguras, instaladas en espacios comunes o públicos como ser veredas o parques o en las puertas de los locales que requieran el servicio y una app mobile para interacción con los dueños de las mascotas. Cada PD estará acondicionado especialmente para albergar un solo perro (en un principio solo para uno, ya se está pensando realizar prototipos para poder alojar más de uno e incluso otros tipos de mascotas).*

🔍 Aparece **el límite del sistema**: cucha + app. Aparece un número (**un solo perro**), que es una **capacidad física del componente**: RNF. Y aparece algo que **no** entra: los prototipos futuros ("ya se está pensando"). Eso no es alcance de este sistema.

✅ RF: ninguno directo.

📏 RN: ninguna (la capacidad de un perro es propiedad de la cucha, no política de la empresa; se escribe como RNF).

⚙️ RNF:
```
RNF-01  La capacidad de alojamiento de un PD es de un perro.
RNF-02  La plataforma de la app mobile es Android e iOS.                        [supuesto]
```

❓ P-02. ¿La app también sirve para contratar la membresía, o eso se hace en otro canal?

🚫 "El sistema permite alojar más de una mascota en el futuro." Fuera de alcance: no se especifica lo que se está pensando.

### Párrafo 4 — Qué tiene cada cucha

📄 *Los PD contarán con una puerta de vidrio para que el dueño pueda ver a su can en todo momento, puerta que quedará cerrada una vez que inicie el servicio de Parking. Cada PD cuenta con un dispensador de agua, otro de comida y está acondicionado para que la mascota no sufra ninguna inclemencia climática (el ambiente interno oscila entre los 22 y 25 grados). Los PD vienen dotados con una cámara interna para que el dueño de la mascota pueda visualizarla desde la app en su celular. La modalidad en la cual el PD dispensa el agua, el tipo de comida y la cantidad dependerá de la raza del perro (que debe indicar el cliente al iniciar el servicio) y del peso de la misma que se obtiene mediante una balanza electrónica incorporada.*

🔍 El párrafo de los **componentes**: puerta, dispensadores, clima, cámara, balanza. Ninguno es una función; cada uno es **un objeto con una característica**. Pero detrás de cada componente hay **una función del dueño**: ver a la mascota (cámara), que coma y tome agua (dispensadores). Y hay una acción del dueño explícita: **indica la raza al iniciar el servicio**. Y un rango: **22 a 25 grados**. Y un hecho: la puerta queda **cerrada al iniciar**.

✅ RF:
```
RF-01  El dueño ve a su mascota desde la app.                      (por la cámara; en línea, no tiempo real)
RF-02  El dueño indica la raza de su perro al iniciar el servicio.  (se va a absorber en Iniciar servicio)
```

📏 RN:
```
RN-01  La ración inicial de alimento y la modalidad de agua se determinan por la raza y el peso del perro.
RN-02  La puerta del PD queda cerrada desde que inicia el servicio.
```
RN-02 podría discutirse como RNF (estado de un componente). Se escribe como regla porque es una **política de seguridad del servicio**, no una medida.

⚙️ RNF:
```
RNF-03  El material de la puerta del PD es vidrio.
RNF-04  La temperatura interna del PD es de entre 22 y 25 grados centígrados.
RNF-05  La resolución mínima de la cámara interna es de 720p.                  [supuesto]
RNF-06  El tiempo máximo entre la imagen captada por la cámara y su visualización en la app
        es de 3 segundos.                                                      [supuesto]
RNF-07  La precisión de la balanza es de ±100 gramos.                          [supuesto]
```
RNF-04 es el ejemplo de **tiempo real** del enunciado: hay un sensor de temperatura y un actuador que calienta o enfría, y el rango es lo que se especifica. No se escribe "el PD controla la temperatura en tiempo real": se escribe el rango.

❓ P-03. ¿Qué pasa si la balanza da un peso fuera del rango de la raza indicada? ¿Se avisa al dueño?

🚫 "El sistema debe tener una cámara para monitoreo en tiempo real." Tres errores: sujeto, componente como función, y "tiempo real" donde es en línea.

### Párrafo 5 — La tarjeta de contacto

📄 *Los dueños de mascotas contarán con una tarjeta de contacto, la cual puede ser leída por el lector instalado en el PD, que identifica al usuario y le indica si puede utilizarlo o no.*

🔍 "Contarán con una tarjeta" es la trampa de "tener una cosa": no es una acción, es el **medio de identificación**. La función del dueño es **identificarse** en el PD.

✅ RF:
```
RF-03  El dueño se identifica en el PD.
```

📏 RN: ninguna todavía (la condición de "si puede utilizarlo" sale del párrafo 6 y 8: un PD a la vez, membresía vigente).

⚙️ RNF:
```
RNF-08  El medio de identificación del dueño en el PD es una tarjeta de contacto.
RNF-09  El tiempo máximo de respuesta del lector, desde que se apoya la tarjeta hasta que la
        pantalla informa si el usuario es válido, es de 2 segundos.          [supuesto]
```

❓ P-04. ¿"Tarjeta de contacto" es de proximidad (NFC) o de banda? Define la tecnología del lector.

🚫 "El lector identifica al usuario." El lector es un componente; no es sujeto de un RF.

### Párrafo 6 — Quién finaliza, y un PD por vez

📄 *Si el PD está en uso, sólo puede finalizar su utilización quien inició el servicio con su tarjeta o un personal autorizado de la firma con su correspondiente tarjeta de mantenimiento. El dueño de mascota sólo puede estar utilizando un PD a la vez.*

🔍 Dos verbos de actores: **finalizar** (el dueño, o el técnico). Dos políticas: quién puede finalizar; un PD por dueño. Y aparece el **segundo actor** con su medio propio (tarjeta de mantenimiento).

✅ RF:
```
RF-04  El dueño finaliza el servicio de guarda de su mascota.
RF-05  El técnico de mantenimiento finaliza un servicio de guarda en curso.
```

📏 RN:
```
RN-03  Un servicio en curso solo puede finalizarlo quien lo inició o un técnico de mantenimiento.
RN-04  Un dueño puede tener en uso un solo PD a la vez.
```

⚙️ RNF:
```
RNF-10  El medio de identificación del técnico en el PD es una tarjeta de mantenimiento.
```

❓ P-05. Si el dueño pierde la tarjeta con la mascota adentro, ¿cómo recupera a su perro? (Es la pregunta que cualquier dueño va a hacer.)

🚫 "El sistema valida que el dueño no tenga otro PD en uso." Es RN-04 aplicada dentro del escenario de Iniciar servicio; no es un RF aparte.

### Párrafo 7 — Cómo arranca el servicio

📄 *En caso de que el PD esté disponible, la pantalla táctil informará que es un usuario válido y requerirá el código numérico de autenticación, si es correcto se abrirá la puerta permitiendo ingresar al perro (el servicio comienza desde el momento mismo que se abre la puerta).*

🔍 La **secuencia de inicio**: identificación (párrafo 5) → autenticación con código → apertura → comienza el servicio. Todo eso es **un caso de uso**: Iniciar servicio, con la identificación y la autenticación incluidas. El "comienza al abrirse la puerta" es una regla de negocio importantísima para la facturación.

✅ RF:
```
RF-06  El dueño inicia el servicio de guarda de su mascota en un PD disponible.
RF-07  El dueño se autentica con su código numérico.             (incluido en Iniciar servicio)
```
RF-02 (indicar la raza) queda absorbido en RF-06: es un dato de entrada del inicio.

📏 RN:
```
RN-05  El servicio de guarda comienza en el momento en que se abre la puerta del PD.
RN-06  Solo se inicia un servicio en un PD en estado disponible.
```

⚙️ RNF:
```
RNF-11  El dispositivo de interfaz del PD con el dueño es una pantalla táctil.
RNF-12  El código de autenticación es numérico, de 4 dígitos.                 [supuesto: longitud]
RNF-13  El tiempo máximo de apertura de la puerta, desde que el código se valida, es de 2 segundos. [supuesto]
```

❓ P-06. ¿Cuántos intentos de código fallidos se permiten? ¿Qué pasa después?
❓ P-07. ¿Dónde y cuándo define el dueño su código?

🚫 "La pantalla informa que el usuario es válido." Es un paso del escenario de Iniciar servicio, no un RF.

### Párrafo 8 — Membresía y facturación

📄 *Para acceder al servicio se requiere el pago de una membresía mensual por débito en tarjeta, que permite el uso de los PD con 1 hora bonificada. El tiempo extra de servicio se paga por tiempo de uso, facturable por hora sin fraccionamiento (59 minutos = 1 hora, 61 minutos = 2 horas) y además se abona por excedente de uso de agua (ni bien comienza el servicio se tiene ½ litro de agua disponible, luego por cada ½ litro adicional se debe abonar extra) y excedente de alimento (como ración inicial se tiene la cantidad estipulada por los parámetros nombrados y luego se debe abonar por cada 200 gramos extra).*

🔍 El párrafo de las **reglas de negocio**: casi todo es política de cobro. Y dos funciones del dueño: **contratar la membresía** y, derivada, **consultar lo consumido y facturado** (si te cobran excedentes, querés verlos). Y un RNF sobre el medio de pago.

✅ RF:
```
RF-08  El dueño contrata la membresía mensual.
RF-09  El dueño consulta el consumo y la facturación de un servicio.          ← derivado
```

📏 RN:
```
RN-07  El acceso al servicio requiere una membresía mensual vigente.
RN-08  La membresía incluye 1 hora de servicio bonificada.
RN-09  El tiempo extra se factura por hora completa, sin fraccionamiento (59 min = 1 h; 61 min = 2 h).
RN-10  Cada servicio incluye ½ litro de agua; cada ½ litro adicional se cobra.
RN-11  Cada servicio incluye la ración inicial según raza y peso; cada 200 g adicionales se cobran.
```

⚙️ RNF:
```
RNF-14  El medio de pago de la membresía y de los excedentes es débito en tarjeta.
RNF-15  La integración con la plataforma de pago es por medio de APIs.          [supuesto]
```

❓ P-08. ¿La hora bonificada es por mes o por cada uso? El enunciado no lo dice, y cambia todo el cobro.
❓ P-09. ¿Los excedentes se debitan al finalizar cada servicio o con la membresía del mes siguiente?

🚫 "El sistema calcula el excedente automáticamente." Sistema como sujeto, verbo hueco y "automáticamente". Lo que hay son RN-09 a RN-11, que se aplican en el escenario de Finalizar servicio.

### Párrafo 9 — Autolimpieza y mantenimiento

📄 *Una vez que finaliza el uso del PD por parte de una mascota, el PD inicia su secuencia de autolimpieza por lo que el PD no se puede utilizar hasta que culmine la misma y quede en estado disponible. El proceso dura cerca de 2 minutos desde que el último usuario cierra la puerta. Adicionalmente, cuando se están haciendo arreglos, el PD estará en estado de mantenimiento sin poder ser utilizado por usuarios hasta que un técnico de la firma vuelva a ponerlo en funcionamiento mediante su tarjeta de mantenimiento.*

🔍 Aparecen **los estados del PD**: en uso → autolimpieza → disponible; y mantenimiento. La autolimpieza **no la dispara nadie**: la dispara el cierre de la puerta. Es parte de lo que pasa al finalizar el servicio (poscondición), no un caso de uso de un actor. Y hay dos funciones del técnico: poner en mantenimiento y reactivar.

✅ RF:
```
RF-10  El técnico de mantenimiento pone un PD en estado de mantenimiento.
RF-11  El técnico de mantenimiento reactiva un PD en mantenimiento.
```

📏 RN:
```
RN-12  Al finalizar un servicio, el PD pasa a autolimpieza y no puede usarse hasta quedar disponible.
RN-13  Un PD en mantenimiento no puede usarse hasta que un técnico lo reactive.
```

⚙️ RNF:
```
RNF-16  La duración máxima de la secuencia de autolimpieza, desde que se cierra la puerta, es de 2 minutos.
```
"Cerca de 2 minutos" en el enunciado; "máxima de 2 minutos" en el RNF: el RNF no puede decir "cerca de".

❓ P-10. ¿Un PD en autolimpieza aparece como "no disponible" en la app, o desaparece del mapa?

🚫 "El PD se autolimpia." El PD no es actor. La autolimpieza es un estado que se dispara al cerrar la puerta y se describe en el escenario de Finalizar servicio.

```
   Estados del PD (para el escenario, no para el diagrama de casos de uso):

   disponible ──inicia servicio──▶ en uso ──finaliza──▶ autolimpieza ──2 min──▶ disponible
        │                                                                          ▲
        └────── técnico pone en mantenimiento ──▶ mantenimiento ──técnico reactiva─┘
```

### Párrafo 10 — La app

📄 *Mediante la aplicación mobile de MascotaCare el dueño podrá verificar los PD disponibles en su zona. Si el dueño está utilizando alguno de los PD puede visualizar a su mascota en la app por medio de la cámara instalada, como así también dispensarle más agua y alimento, verificar la temperatura en la cabina, saber el tiempo que lleva utilizándola, informar de algún inconveniente o problema con el PD y comunicarse con el soporte técnico si fuese necesario.*

🔍 El párrafo más generoso en RF: es una **lista de funciones del dueño**, ya escritas casi desde el actor. Solo hay que separarlas (una por verbo) y sacar los medios.

✅ RF:
```
RF-12  El dueño consulta los PD disponibles en su zona.
RF-01  El dueño ve a su mascota.                                   (ya estaba; el medio es la cámara)
RF-13  El dueño dispensa agua adicional a su mascota.
RF-14  El dueño dispensa alimento adicional a su mascota.
RF-15  El dueño consulta la temperatura de la cabina.
RF-16  El dueño consulta el tiempo transcurrido del servicio.
RF-17  El dueño informa un inconveniente con el PD.
RF-18  El dueño se comunica con soporte técnico.
```

📏 RN:
```
RN-14  Las funciones sobre un PD (ver, dispensar, consultar) solo están disponibles para el dueño
       con un servicio en curso en ese PD.
```

⚙️ RNF:
```
RNF-17  El tiempo máximo entre la orden de dispensar y la dispensación efectiva es de 5 segundos.  [supuesto]
RNF-18  El medio de comunicación con soporte técnico es chat dentro de la app.                    [supuesto]
```

❓ P-11. ¿"Su zona" es un radio fijo (cuántos metros) o la zona del mapa que el dueño mira?
❓ P-12. Dispensar más agua o alimento suma excedente (RN-10, RN-11): ¿la app avisa el costo antes de dispensar?

🚫 "El dueño monitorea a la mascota en tiempo real." Es en línea. El RNF que corresponde es RNF-06 (retardo máximo de la imagen).

## 3. 🔴 Consolidación

| | Cantidad |
|---|---|
| RF (dueño) | 14 · RF-01, RF-03, RF-04, RF-06 a RF-09, RF-12 a RF-18 (RF-02 absorbido en RF-06 como dato de entrada; RF-07 se modela como caso de uso incluido en Iniciar servicio) |
| RF (técnico) | 3 · RF-05, RF-10, RF-11 |
| Reglas de negocio | 14 · RN-01 a RN-14 |
| RNF | 18 · RNF-01 a RNF-18 (8 con valor del enunciado, 10 supuestos) |
| Preguntas | 12 · P-01 a P-12 |

**Omisiones detectadas** (las ocho preguntas sobre el conjunto): el dueño **se registra** en MascotaCare y **registra a su mascota** (raza) antes de contratar; el dueño **define su código** numérico (P-07); el dueño **da de baja** su membresía. Ninguno está en el enunciado; los tres son complementos obvios y se agregan como derivados.

**Consistencia:** RN-04 (un PD por vez) y RN-06 (solo en PD disponible) se aplican las dos en el escenario de Iniciar servicio, sin contradicción. RN-08 (1 hora bonificada) es ambigua por P-08: no es inconsistencia, es información que falta.

## 4. 🔴 Consigna 1: cinco y cinco para el folleto

La consigna pide **5 RF y 5 RNF de interés de los dueños**, para marketing. El criterio de selección es **qué le importa a un dueño que va a dejar a su perro**: verlo, que esté bien, saber cuánto lleva, poder ubicar una cucha, y que no lo saque nadie más. No es "los cinco primeros de la lista": es una elección justificada.

**Cinco RF:**
```
1. El dueño consulta los PD disponibles en su zona.                         (RF-12)
2. El dueño ve a su mascota desde la app durante el servicio.               (RF-01)
3. El dueño dispensa agua y alimento adicionales a su mascota desde la app. (RF-13 + RF-14, a nivel alto)
4. El dueño consulta el tiempo transcurrido y la temperatura de la cabina.  (RF-15 + RF-16)
5. El dueño se comunica con soporte técnico desde la app.                   (RF-18)
```
Si en el parcial te piden cohesión estricta, el 3 y el 4 se abren en dos cada uno y elegís cinco entre los siete. Para un folleto, agruparlos a nivel alto es defendible; decilo.

**Cinco RNF:**
```
1. La temperatura interna del PD es de entre 22 y 25 °C.                                   (RNF-04)
2. La capacidad de alojamiento de un PD es de un perro.                                    (RNF-01)
3. El medio de identificación del dueño es una tarjeta de contacto, más un código numérico
   de autenticación.                                                                       (RNF-08 + RNF-12)
4. El material de la puerta del PD es vidrio, y queda cerrada durante todo el servicio.    (RNF-03 + RN-02)
5. La duración máxima de la autolimpieza entre servicios es de 2 minutos.                  (RNF-16)
```
Fijate el 3 y el 4: al dueño le importan como **seguridad**, y en el folleto se leen así, pero siguen escritos como objeto + atributo + valor. Lo que **no** va en el folleto: RNF-15 (APIs), RNF-07 (precisión de la balanza). Son de interés del desarrollador o de la empresa, no del dueño; la consigna lo pide explícitamente.

## 5. 🔴 Consigna 2: el diagrama de casos de uso

```
                    ┌──────────────────── Sistema ParkingDog ────────────────────┐
                    │                                                              │
   [Dueño de   ─────┼─ ( Contratar membresía ) ─────────────────────────────────────┼─· · · [Plataforma
    mascota]   ─────┼─ ( Consultar PD disponibles en zona )                         │          de pago]
               ─────┼─ ( Iniciar servicio ) ──inc──▶ ( Identificarse en el PD )      │
               ─────┼─                     ──inc──▶ ( Autenticarse con código )     │
               ─────┼─ ( Finalizar servicio ) ──inc──▶ ( Identificarse en el PD )   │
               ─────┼─                       ◀──ext── ( Cobrar excedente ) ──────────┼─· · · [Plataforma
               ─────┼─                             [superó 1 h, ½ l o ración]        │          de pago]
               ─────┼─ ( Ver mascota )                                              │
               ─────┼─ ( Dispensar agua adicional )                                 │
               ─────┼─ ( Dispensar alimento adicional )                             │
               ─────┼─ ( Consultar temperatura de cabina )                          │
               ─────┼─ ( Consultar tiempo transcurrido ) ──inc──▶ ( Tomar fecha      │
               ─────┼─ ( Informar inconveniente )                    y hora ) ──────┼─· · · [Tiempo]
               ─────┼─ ( Contactar soporte técnico ) ───────────────────────────────┼─· · · [Soporte
                    │                                                              │          técnico]
   [Técnico de ─────┼─ ( Finalizar servicio )   ← el mismo caso de uso de arriba    │
    mantenimiento] ─┼─ ( Poner PD en mantenimiento )                                │
               ─────┼─ ( Reactivar PD )                                             │
                    └──────────────────────────────────────────────────────────────┘
```

**Decisiones, cada una con su justificación:**

1. **Iniciar servicio incluye Identificarse y Autenticarse.** Siempre pasa (párrafo 7). Inclusión.
2. **Finalizar servicio incluye Identificarse.** Solo finaliza quien se identifica con tarjeta (RN-03). Inclusión. El técnico se conecta al mismo caso de uso: mismo objetivo, distinta tarjeta; la diferencia de tarjeta es RNF-08 vs. RNF-10, no dos casos de uso.
3. **Cobrar excedente extiende Finalizar servicio.** Solo si se superó la hora, el medio litro o la ración (RN-09 a RN-11). Extensión, bajo condición. Si el excedente fuera de todos los servicios, sería inclusión; no lo es.
4. **Tomar fecha y hora con el actor Tiempo**, incluido en Consultar tiempo transcurrido (y en Cobrar excedente, que necesita las horas). Es el caso de uso derivado de RN-05 y RN-09: para facturar por hora hay que saber cuándo se abrió la puerta.
5. **La autolimpieza y el termostato no están.** No son casos de uso: la autolimpieza es poscondición de Finalizar servicio (RN-12), y el clima es RNF-04 con sensor y actuador que funcionan solos.
6. **Ni la mascota ni el PD son actores** (§1).
7. **Sin generalización.** No hay dos formas de lograr lo mismo que justifiquen una. Si el dueño pudiera finalizar desde la app además de con la tarjeta, ahí sí: Finalizar con tarjeta / Finalizar desde la app, ambos especializando Finalizar servicio. El enunciado no lo dice.

> ⚠️ **Notación:** en la entrega, elipses, monigotes, rectángulo del sistema, «include» y «extend» con la punta bien orientada (del que incluye al incluido; del que extiende al base). El esquema de arriba es texto; el diagrama se dibuja en Lucidchart con UML estricto.

> **Para el parcial, si te preguntan:** *¿Por qué el ParkingDog no es un actor del sistema?*
> Porque un sistema es un conjunto de elementos interrelacionados con un objetivo común, y la cucha es uno de esos elementos: forma parte de la solución e incorpora los componentes (lector, cámara, dispensadores, balanza) que permiten lograr el objetivo. Un actor es un rol externo con un objetivo propio frente al sistema; el PD no tiene objetivos, los tiene el dueño de la mascota que lo usa.

## 6. 🔴 Errores comunes al resolver este simulacro

| Error | Por qué aparece | Cómo se evita |
|---|---|---|
| La mascota como actor | "Come, toma agua, interactúa" | Preguntá quién tiene el objetivo: el dueño |
| El PD como actor secundario | "Interactúa con la app" | Es parte del sistema; sus componentes también |
| "Tener un sensor / una cámara" como RF | Se confunde componente con función | La función es del dueño (saber, ver, dispensar); el componente es RNF |
| "Monitorear en tiempo real" | Se copia el lenguaje comercial | Es en línea; el RNF es el retardo máximo con unidad |
| "El sistema calcula el excedente automáticamente" | Sistema como sujeto + verbo hueco + "automáticamente" | Reglas de negocio (RN-09 a RN-11) aplicadas en el escenario de Finalizar |
| La facturación por hora como RNF | Es un número, entonces "se mide" | Es política de cobro: existe con o sin sistema. Regla de negocio |
| "Cerca de 2 minutos" copiado al RNF | Se transcribe el enunciado | El RNF dice "máxima de 2 minutos": un valor, no una aproximación |
| RNF con el dueño como sujeto ("el dueño puede ver a su mascota en HD") | Se mezcla el RF con su restricción | RF: el dueño ve a su mascota. RNF: la resolución mínima de la cámara es de 720p |
| Cinco RF "de interés del dueño" que son de interés del desarrollador | No se lee la consigna | APIs, precisión de balanza y estados internos no van al folleto |
| Autolimpieza como caso de uso | Tiene nombre y duración | Nadie la dispara: es poscondición de Finalizar servicio |

## 7. ✏️ Ejercicios (respuestas al final)

**E1.** Un equipo escribió: *"RF: El ParkingDog dispensa la ración inicial de comida según la raza y el peso."* Clasificalo y reescribí lo que corresponda.

**E2.** Escribí el RNF que reemplaza a *"la app funciona en tiempo real"*, con objeto, atributo, valor y unidad, marcando el supuesto.

**E3.** ¿"Cobrar excedente" debería ser inclusión o extensión de "Finalizar servicio"? Justificá con la regla y con el enunciado.

**E4.** Del párrafo 8, alguien sacó este RNF: *"El tiempo extra se factura por hora sin fraccionamiento."* ¿Es un RNF? Si no, ¿qué es y dónde se aplica?

**E5.** Proponé un RF que no esté en el enunciado, sea un complemento obvio, y escribí qué regla o RNF tiene que respetar para ser consistente.

---

## Respuestas

**E1.** No es un RF: el sujeto es un componente del sistema y describe un comportamiento interno (sensor y actuador: es tiempo real). Se abre en: **RN-01** *La ración inicial de alimento se determina por la raza y el peso del perro* (política), y un RNF sobre el componente: *La precisión de la balanza es de ±100 gramos [supuesto]*. La función del dueño que hay detrás ya existe: *El dueño inicia el servicio indicando la raza*.

**E2.** *El tiempo máximo entre la imagen captada por la cámara y su visualización en la app es de 3 segundos [supuesto].* Objeto: imagen de la cámara · Atributo: retardo máximo de visualización · Valor: 3 · Unidad: segundos. "Tiempo real" no se puede verificar; un retardo máximo, sí.

**E3.** **Extensión.** La regla: inclusión es lo que se hace siempre dentro del flujo; extensión es lo excepcional, bajo condición. El enunciado: el excedente existe solo si el servicio superó la hora bonificada, el medio litro de agua o la ración inicial (RN-09 a RN-11). Muchos servicios terminan sin excedente, así que el cobro es condicional: *Cobrar excedente* extiende a *Finalizar servicio* con la condición "superó algún incluido".

**E4.** No es un RNF: no describe una propiedad medible de un componente ni una restricción sobre cómo funciona una función; describe **cómo cobra la empresa**, y eso existe aunque el cobro se haga a mano. Es la **regla de negocio RN-09**, y se aplica dentro del escenario de *Finalizar servicio* (o de su extensión *Cobrar excedente*), al calcular el importe.

**E5.** Por ejemplo: *El dueño registra a su mascota con su nombre y raza.* Complemento obvio de "indica la raza al iniciar el servicio": si la mascota está registrada, la raza no se pide cada vez. Para ser consistente: debe respetar RN-01 (la raza determina la ración) y no contradecir RF-06 (que sigue permitiendo indicar la raza si la mascota no está registrada, o se reemplaza por seleccionarla). Y RNF-01: un perro por PD, así que al iniciar se elige **una** mascota registrada.

---

**FIN DE LA PROFUNDIZACIÓN — ParkingDog párrafo por párrafo**
