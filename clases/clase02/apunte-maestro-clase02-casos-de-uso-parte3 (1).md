# APUNTE MAESTRO — Clase 02 · Casos de Uso — Parte 3

**Ingeniería de Requisitos — clase02 (20/08/2026) · Parte 3 de 4**
**Esta parte:** las tres relaciones entre casos de uso — generalización, inclusión y extensión — y las dos fronteras donde se cae todo el mundo: relación vs precondición, y caso de uso vs proceso.
**Ya viste:** Parte 1 — qué es un CU y cómo se nombra · Parte 2 — actores. **Viene:** Parte 4 — los sistemas de punta a punta, info operativa y checkpoint.

**Marcas:** 🔴 central y evaluable · 🟡 secundario · 🟢 mencionado al pasar.
**Notación ASCII de esta parte** (en papel, la notación real se corrige):
- `──▷` generalización: línea **llena**, **triángulo hueco** apoyado en el general (igual que la herencia de la Parte 2).
- `--inc-->` inclusión: línea **punteada** con el estereotipo **inc** sobre la línea.
- `--ext-->` extensión: línea **punteada** con el estereotipo **ext** sobre la línea.

---

## 🔴 1. Generalización: distintas formas de lograr lo mismo

Volvé a Apagar TV. El pedido original ya lo decía para encender y cambiar: *presionando el botón del televisor o a través de un control remoto*. Dos formas. Y pueden ser más: me compré un teléfono con la app del fabricante y lo apago desde la app, o lo maneja la domótica de la casa con un timer — "todos los días a las 7:00 encendete en tal canal".

> 🕳️ **Madriguera — domótica**
> Automatización del hogar: dispositivos del hogar controlados por reglas y horarios. Acá es solo "otra vía más para ejecutar la misma función".
> *Volvé al camino — esto se profundiza aparte, otro día.*

¿Qué objetivo tengo? Uno: **apagar el televisor**. ¿De cuántas formas puedo lograrlo? Varias. Distintas variantes de la misma función, sin condiciones entre ellas: cada vez que apago, uso **una o la otra** — nunca las dos, nunca "una por defecto y otra si falla". Eso tiene nombre, y lo conocés de programación: **polimorfismo**. Distintas implementaciones de la misma operación.

Cuando hay polimorfismo, hay **especializaciones**, y la relación entre ellas y la función general es la **generalización**:

```
                          ◁── ( Apagar TV con control remoto )
 ( Apagar TV )            ◁── ( Apagar TV desde botonera )
                          ◁── ( Apagar TV desde app )
```

Cómo leer cada pieza — y esto es definición de parcial:

- **El caso de uso general (Apagar TV) es abstracto: no se implementa, no tiene escenario. Es una interfaz.** Exactamente el mismo concepto que una clase abstracta o una interfaz en programación: declara *qué* función existe, no *cómo* se ejecuta.
- **Las especializaciones son los casos de uso que sí se implementan: cada una tiene su escenario desarrollado.** Apagar con control remoto tiene sus pasos; apagar desde la app, los suyos.
- **Pueden sumarse especializaciones a medida que surgen formas nuevas** de resolver la misma función. Mañana aparece "Apagar TV por aplauso" y se agrega un óvalo más, sin tocar nada de lo existente. Eso es el polimorfismo trabajando a tu favor.
- **El verbo se repite**: apagar, apagar, apagar. Es la señal visual de que es la misma función en todas. (Hay quien no repite el verbo en las especializaciones; repetirlo hace el diagrama mucho más fácil de entender, y es lo que vas a hacer acá.)
- **Notación**: línea llena, **triángulo de punta hueca apoyado en el caso de uso general**. La misma punta hueca que la herencia entre actores — y se corrige igual de estricto.

**Para el parcial, si te preguntan cuándo hay generalización entre casos de uso**
Cuando existe polimorfismo: distintas formas de implementar una misma función, excluyentes entre sí en cada ejecución (se instancia una o la otra). El caso de uso general es abstracto —no se implementa, no tiene escenario, funciona como interfaz— y las especializaciones son las que se implementan, cada una con su escenario. Notación: línea llena con triángulo hueco apoyado en el caso de uso general, repitiendo el verbo.

---

## 🔴 2. El contraejemplo: lo que la generalización NO es

El error típico es modelar esas variantes con las otras dos relaciones. Vale la pena verlo tachado:

```
❌  ( Apagar TV ) <--ext-- ( Apagar TV con control remoto )     ← MAL
❌  ( Apagar TV ) <--inc-- ( Apagar TV con control remoto )     ← MAL
✅  ( Apagar TV ) ◁─────── ( Apagar TV con control remoto )     ← generalización
```

¿Por qué no son extensiones? Porque las especializaciones **no son vías excepcionales ni condicionales**. No es que "siempre apago con el control y, si se quedó sin pilas, excepcionalmente uso el botón" — ese sería otro modelo, el de una condición anormal que se trata aparte (y eso sí es una extensión, sección 6). Acá las vías son equivalentes y excluyentes en cada ejecución: elijo una, punto. Instancio una o la otra.

¿Y por qué no son inclusiones? Porque nada se está ejecutando "adentro" de nada: apagar desde la app no es un paso dentro del flujo de Apagar TV — **es** Apagar TV, implementado de una forma concreta.

---

## 🟡 3. El colectivo: qué quiero vs cómo lo logro

El mismo concepto, en un dominio que usás todos los días. Subís al colectivo y pagás. Antes era con la SUBE; hoy no tenés carga y apoyás la tarjeta de débito; o generás un QR; o pagás con el reloj en la muñeca. ¿Y qué te dice la maquinita en todos los casos? **"Gracias, pagaste."**

Entonces: ¿qué quería hacer el pasajero? ¿Quería *leer el QR*? ¿Quería *apoyar la tarjeta*? No. **Quería pagar.** Como historia de usuario: *"Yo, como pasajero, quiero pagar el pasaje para poder viajar"* — jamás "quiero leer el QR para poder pagar".

Por eso "Leer QR" o "Apoyar tarjeta" **no son casos de uso** del pasajero: son el **cómo** de una única función, **Pagar pasaje**. Hay polimorfismo — si hiciera falta detallarlo, las vías serían especializaciones de Pagar pasaje — pero nunca funciones base por derecho propio. La pregunta que separa las aguas, siempre: *¿qué quiere lograr el actor?* vs *¿de qué formas puede lograrlo?* Lo primero nombra el caso de uso; lo segundo, a lo sumo, sus especializaciones.

(Y de paso, el nombre del actor: **Pasajero**, no "usuario". Parte 2 en acción.)

---

## 🔴 4. Inclusión: lo que se hace siempre, adentro del flujo

Cambio de relación. Acordate del hilo abierto en la Parte 2: el televisor necesita saber cuánto tiempo estuvo encendido —las 10.000 horas de la garantía viven de eso— y el actor Tiempo entrega la fecha/hora cuando se lo consulta. ¿Cómo se engancha eso con las funciones del Televidente?

Cada vez que **enciendo**, el sistema toma el time-stamp. Cada vez que **apago**, también — y con los dos valores acumula el tiempo transcurrido encendido. Fijate las dos propiedades: se hace **siempre** (no a veces, no bajo condición), y ocurre **adentro del flujo** del caso de uso que lo dispara. Esa relación es la **inclusión**:

```
 ( Encender TV ) --inc--> ( Tomar time-stamp )╌╌╌ [actor] TIEMPO
 ( Apagar TV )   --inc--> ( Tomar time-stamp )

 ( Apagar TV )   --inc--> ( Acumular tiempo de uso )
```

**Cuándo se usa — las dos puertas de entrada:**

1. **Reusabilidad** (el uso principal): el mismo comportamiento se hace siempre **y lo hacen dos o más** casos de uso. Tomar time-stamp lo necesitan Encender y Apagar → se extrae a su propio óvalo y ambos lo incluyen, en vez de describirlo dos veces.
2. **Destacar**: ¿puedo incluir algo que hace **uno solo**? Sí — cuando me interesa que esa parte de la funcionalidad **se identifique a simple vista** en el diagrama. Acumular tiempo de uso lo hace solo Apagar TV; podría quedar como un paso interno del flujo y no dibujarse — pero quiero destacarlo: *quedate tranquilo que acá me fijo cuánto lo estuviste usando*.

**La advertencia: no abusar.** Si dibujo como inclusión cada paso interno de cada flujo, el diagrama se llena de óvalos y deja de decir algo. La inclusión se gana el lugar por reusabilidad o por valor de destacarla — no por existir como paso.

**Notación**: línea **punteada** con punta de flecha, **desde el caso de uso que incluye hacia el incluido**, con **inc** sobre la línea.

**Para el parcial, si te preguntan cuándo usar una inclusión**
Cuando un comportamiento se ejecuta siempre, como parte del flujo del caso de uso que lo incluye. Su uso principal es la reusabilidad (el comportamiento se repite en dos o más casos de uso y se extrae para no duplicarlo); también puede usarse con un solo caso de uso para destacar una parte de la funcionalidad que interese identificar a simple vista. La flecha punteada con "inc" va del caso de uso que incluye hacia el incluido. No se debe abusar de ella.

---

## 🔴 5. Frontera 1: la inclusión no es una precondición

Este es el error que más se dibuja, así que va con su propio juicio. El ejemplo clásico es el **cajero automático**, y hay bibliografía que lo modela así: *"para Retirar efectivo, lo primero es loguearse → Loguearse va como incluido"*. Suena razonable. **Está mal.**

Desarmalo con lo que ya sabés: ¿el login se ejecuta siempre *adentro del flujo* de Retirar efectivo? No — puedo loguearme y no retirar nada: hago una consulta de saldo y me voy. El login pasó **antes**, una vez, y me dejó habilitado. Eso tiene nombre desde la Parte 1: es la **precondición** de Retirar efectivo — *estar logueado*. Y la palabra lo delata: **pre**-condición, previa. **Si algo tiene que estar dado ANTES de que el caso de uso empiece, no puede estar "incluido" adentro de su flujo.** Son lugares distintos del tiempo.

Lo mismo con la cajera del sistema de cajas (Parte 2): se loguea al empezar el turno; capaz no pasa nadie y nunca cobra. Cuando alguien pasa, la precondición de Cobrar es estar logueada — no hay un login ejecutándose adentro de cada cobro.

La regla en limpio: **estar logueado HABILITA todas las funcionalidades — habilitar es cosa de precondición, no de inclusión.** Igual que en el televisor: que esté encendido habilita cambiar el canal y habilita apagarlo; que esté apagado habilita encenderlo. A nadie se le ocurriría dibujar "Encender TV" como incluido dentro de "Cambiar canal" — con el login es exactamente igual, solo que el error se disfraza mejor.

**Para el parcial, si te preguntan por qué el login no se modela como inclusión**
Porque estar logueado es una precondición: una condición previa que habilita el inicio de los demás casos de uso, no un comportamiento que se ejecute siempre dentro de sus flujos. Puedo loguearme y no ejecutar ninguna otra función, lo que demuestra que el login es independiente y previo. Login se modela como caso de uso propio (asociado al actor que corresponda) y "estar logueado" aparece como precondición en la plantilla de los casos de uso que lo requieran.

---

## 🔴 6. Extensión: lo excepcional, bajo condición

Tercera relación, y la que faltaba para cerrar el mecanismo de la garantía.

El Técnico llega a la casa. El televisor "se compró para el Mundial, solo se vieron los partidos, y ya falla". ¿El técnico confía en la palabra del televidente? ¿Mira la factura de compra? La factura dice cuándo se compró, no cuánto se usó — comprado hace cinco años no significa 10.000 horas si solo lo prendían diez minutos a la mañana para ver el clima. Por eso existe el mecanismo de la sección 4: el sistema **acumuló** el tiempo real de uso. Y el Técnico tiene una función propia para mirarlo: **Consultar horas de uso** — un caso de uso más, colgado directo del actor, igual que Realizar mantenimiento.

Y ahora la bifurcación del negocio: consultó, ¿y? Si las horas superan el umbral, sigue el camino normal — lo repara. Pero si el televisor tiene apenas unas horas de uso, pasa algo distinto: **lo deriva a la garantía**. Eso no ocurre siempre; ocurre **bajo una condición**, y cuando ocurre, reemplaza el camino normal. Esa relación es la **extensión**:

```
 [actor] TÉCNICO ────( Realizar mantenimiento )
        └───────────( Consultar horas de uso ) <--ext-- ( Derivar a garantía )
```

- Mantenimiento y consulta son **dos funciones independientes del Técnico**, cada una asociada directo al actor. Puede consultar las horas sin reparar nada, y cada una se dispara y se testea por separado. Que en la vida real el técnico consulte antes de decidir es orden temporal — y el orden, como vas a ver en la sección 8, no se dibuja como relación.
- La extensión: derivar a garantía sucede **solo si** se da la condición. La decisión por defecto es una (reparar); la excepcional es la otra (garantía). Y notá la economía del modelo: Consultar horas de uso tiene **una sola** relación colgando — la extensión, que es la que el negocio necesita.

**La heurística de la cátedra, para grabársela:** todo caso de uso que se llame **verificar, validar o controlar** trae una extensión colgando. ¿Por qué? Porque verificar significa mirar un valor y **tomar una decisión u otra**. Si después de controlar tomo siempre la misma decisión… no controlé nada. El control existe para que a veces pase otra cosa — y ese "a veces pasa otra cosa" es, por definición, una extensión.

**Notación**: línea **punteada**, **desde el caso de uso que extiende hacia el caso de uso base**, con **ext** sobre la línea. Ojo con el sentido: apunta al revés que la intuición — sale de la extensión (Derivar a garantía) y toca al base (Consultar horas de uso).

**Para el parcial, si te preguntan la diferencia entre inclusión y extensión**
La inclusión se ejecuta siempre, como parte del flujo del caso de uso que la incluye, y su criterio es la reusabilidad; la flecha punteada "inc" va del que incluye al incluido. La extensión se ejecuta solo bajo una condición: agrega el tratamiento de una vía excepcional al comportamiento normal; la flecha punteada "ext" va del caso de uso que extiende hacia el base. Regla práctica: los casos de uso de verificar/validar/controlar generan extensiones, porque controlar implica poder tomar una decisión distinta de la habitual.

---

## 🔴 7. La extensión en acción: bloquear y reportar

Un caso real para afilar la frontera entre extensión y precondición, ahora en una app de mensajería: **bloquear una cuenta** y **reportarla**. La app no te deja reportar de una — primero bloqueás, y recién ahí te ofrece la opción de reportar. ¿Cómo se modela Reportar respecto de Bloquear?

**Primera tentación: "estar bloqueada es la precondición de Reportar".** Suena igual que el login… pero no lo es, y la diferencia está en el tiempo: **todo ocurre en el mismo momento, dentro del mismo flujo**. No es que bloqueo hoy y, en otro momento, cuando quiera, reporto — el reporte solo existe como continuación inmediata del bloqueo. La precondición del cajero era algo previo y separado (me logueé a la mañana, retiro a la tarde); acá no hay separación: es un solo recorrido.

**Segunda pregunta: ¿es inclusión?** No — porque no se hace siempre. Bloquear y no reportar es perfectamente válido: *puede ser que lo bloquee y nada más*.

Algo que ocurre dentro del flujo de Bloquear, pero **opcionalmente**: eso es una **extensión**.

```
 ( Bloquear cuenta ) <--ext-- ( Reportar cuenta )
```

La vara para distinguir, en limpio: si la otra función puede ejecutarse **en otro momento, por separado** → lo previo es precondición. Si solo puede ocurrir **como parte del mismo recorrido**, y además es **opcional** → extensión. (Y si ocurriera siempre, sería inclusión — las tres preguntas, en ese orden, resuelven cualquier caso.)

---

## 🔴 8. Frontera 2: un caso de uso no es un proceso

Última regla de la parte, y es la que mantiene al diagrama siendo lo que es.

**Los casos de uso son independientes entre sí.** Cada uno se dispara por su cuenta, cambia el estado del sistema por su cuenta, y se testea por su cuenta —en forma discreta, como viste en la Parte 1—. Pueden compartir datos, pero **el diagrama de casos de uso no muestra secuencias ni flujos de datos entre ellos**. Para eso existen otros diagramas.

> 🕳️ **Madriguera — DFD**
> Diagrama de Flujo de Datos: el que modela procesos y cómo los datos viajan entre ellos. Es otra herramienta, para otra pregunta.
> *Volvé al camino — esto se profundiza aparte, otro día.*

De acá salen dos errores concretos:

**Error A — dibujar el orden real como inclusión.** "Para cambiar el canal, el televisor tiene que estar encendido… entonces ¿Encender TV no debería estar incluido en Cambiar canal?" No. Que en la vida real haya un orden no crea una relación en el diagrama: el orden vive en la **precondición** (Cambiar canal: *el televisor está encendido*). Cambiar canal es independiente — el televisor ya estaba encendido de antes, y yo lo cambio. Si dibujás la secuencia temporal como inclusiones, estás dibujando un proceso.

**Error B — encadenar relaciones.** Un caso de uso soporta **una relación más colgando** — una generalización, una extensión o una inclusión. Lo que no se puede es seguir la cadena: que el incluido incluya a otro, y ese a otro. En el momento en que encadenás, dejaste de modelar funciones y estás modelando un **proceso** con etapas — que es exactamente lo que este diagrama no es.

```
❌  ( A ) --inc--> ( B ) --inc--> ( C ) --inc--> ( D )     ← eso es un proceso disfrazado
```

**Para el parcial, si te preguntan por qué los casos de uso son independientes**
Porque cada caso de uso representa una función completa que se dispara, cumple su objetivo y se verifica en forma discreta por separado. El diagrama de casos de uso no modela secuencias ni flujos de datos entre casos de uso: el orden temporal real se expresa como precondición en la plantilla, no como relación en el diagrama, y encadenar inclusiones convierte el modelo en un proceso, que corresponde a otro tipo de diagrama.

---

## 🔴 9. Las tres relaciones, en una tabla

| Relación | Cuándo | Se ejecuta | Notación |
|---|---|---|---|
| **Generalización** | Polimorfismo: distintas formas de implementar la misma función (el verbo se repite; el general es abstracto, sin escenario) | Una **o** la otra, excluyentes en cada ejecución | Línea llena, triángulo hueco apoyado en el general |
| **Inclusión** (`inc`) | Reusabilidad: comportamiento que se repite en 2+ casos de uso; o para destacar una parte de la funcionalidad | **Siempre**, adentro del flujo del que incluye | Punteada, del que incluye al incluido, "inc" sobre la línea |
| **Extensión** (`ext`) | Vía excepcional bajo condición; todo verificar/validar/controlar trae una | **Solo si** se da la condición; opcional | Punteada, del que extiende al base, "ext" sobre la línea |

Y las dos fronteras que ninguna relación puede cruzar: lo **previo y separado** es precondición, no relación; lo **encadenado y secuencial** es un proceso, no un diagrama de casos de uso.

---

## Cierre de la Parte 3

Ya tenés la caja de herramientas completa: funciones bien nombradas, actores con su herencia, y las tres relaciones con sus fronteras. En la Parte 4 todo esto se junta: el televisor armado de punta a punta —incluyendo qué requerimientos del pedido se modelaron y cuáles no, y por qué—, el criterio aplicado a los otros dos sistemas de la unidad, la información operativa de la clase, y el checkpoint de toda la unidad.

**FIN DE LA PARTE 3**
