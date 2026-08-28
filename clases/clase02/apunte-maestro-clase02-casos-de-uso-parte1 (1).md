# APUNTE MAESTRO — Clase 02 · Casos de Uso — Parte 1

**Ingeniería de Requisitos — clase02 (20/08/2026) · Parte 1 de 4**
**Esta parte:** qué es un caso de uso, el test para detectar lo que NO lo es, y las reglas de nombrado con las que se corrige.
**Vienen después:** Parte 2 — actores · Parte 3 — relaciones (generalización, include, extend) · Parte 4 — los sistemas trabajados de punta a punta, info operativa y checkpoint de la unidad.

**Marcas:** 🔴 central y evaluable · 🟡 secundario · 🟢 mencionado al pasar.

---

## 🔴 1. El sistema de toda la unidad: un televisor

Toda la clase gira alrededor de un mismo sistema, así que conviene tenerlo presente antes de cualquier definición.

El sistema es un **televisor**, descrito por un pedido con estas necesidades:

- El usuario puede **encenderlo**, **cambiar de canal** y **seleccionar cualquier canal disponible** — cada cosa presionando un botón del televisor o a través de un control remoto.
- Acepta las resoluciones de pantalla 4K y 1920×1080.
- Debe poder **conectarse** a un sistema de sonido surround, a una antena digital (por ejemplo TDA), a un access point inalámbrico (WiFi) y a un sistema de grabación por salida de audio-video.
- Debe **superar las 10.000 horas de uso** antes de necesitar mantenimiento de un técnico.
- Debe respetar disposiciones legales (propiedad intelectual de los contenidos, normas de redes inalámbricas y digitales) y llegar al mercado en cierta fecha.

> 🕳️ **Madriguera — TDA**
> Televisión Digital Abierta: la señal de TV digital gratuita por antena en Argentina. Acá es solo "una de las entradas de señal del televisor".
> *Volvé al camino — esto se profundiza aparte, otro día.*

Primera decisión antes de dibujar nada, y conecta directo con la clase 1: **en un diagrama de casos de uso solo se modelan los requerimientos funcionales.** De la lista de arriba, las funciones (encender, cambiar, conectar…) van al diagrama; las condiciones y restricciones (resoluciones aceptadas, las 10.000 horas como umbral, normas legales, fecha de salida) son requerimientos no funcionales y **no** se dibujan como casos de uso. En la Parte 4 vas a ver que uno de esos RNF igual termina *generando* casos de uso — pero eso es otra cosa que dibujarlo como si fuera una función.

Con el sistema en la cabeza, la pregunta que ordena todo lo demás: **¿qué quiere lograr el que está parado frente al televisor?**

---

## 🔴 2. Qué es un caso de uso

Un **caso de uso es una función que el actor pretende que el sistema le resuelva, nombrada desde el punto de vista del actor.**

La pregunta que lo define no es "¿qué hace el sistema?" sino:

> **"¿Qué quiero yo que vos me resuelvas?"**

Ese "yo" es el actor — el monigote parado al lado del diagrama. No es lo que el sistema dice que da; es lo que el actor quiere obtener.

De acá sale la conexión con la clase 1: **el caso de uso está directamente relacionado con los requerimientos funcionales.** Y los no funcionales también tienen su lugar en esta frase: **lo no funcional es *bajo qué condiciones* logro esa función.** Encender el televisor es la función; que acepte 4K es una condición sobre cómo la disfruto.

### La notación mínima

El diagrama arranca con tres elementos, y la notación se corrige sin margen:

```
 [actor]
Televidente ────────( Encender TV )
```

- El **actor** es el monigote (acá lo vas a ver como `[actor] Nombre`; en papel, dibujá siempre el monigote).
- El **caso de uso** es un **óvalo** con el nombre adentro. No es un círculo, no es un rectángulo, no es un cuadrado: **óvalo**.
- La **línea de asociación** que los une es **llena y sin flecha**. ¿Por qué sin flecha? Porque no es un disparo único en una dirección: entre el actor y la función hay un **ida y vuelta** — pido, el sistema responde, aporto algo más — hasta que la función queda resuelta. Una flecha diría algo que no es cierto.
- Los **actores principales** — los que tienen los principales requerimientos — van siempre **a la izquierda** del gráfico.

**Para el parcial, si te preguntan qué es un caso de uso**
Un caso de uso es una función que el actor pretende obtener del sistema, definida desde el punto de vista del actor, y está directamente relacionado con un requerimiento funcional. Se representa como un óvalo unido al actor por una línea llena sin flecha.

---

## 🔴 3. El test del flujo: cómo detectar lo que NO es un caso de uso

Frente al televisor, alguien propone como caso de uso **"Obtener información"**. Suena razonable. Otro propone **"Interactuar con el televisor"**. También suena razonable. Los dos están mal, y el test para verlo es siempre el mismo.

**El test:** todo caso de uso trae consigo una plantilla con su **flujo normal** — la secuencia de pasos que lo resuelve (la plantilla completa está en la sección 7). Entonces: *describí el flujo normal, paso a paso.*

- ¿Cuál es el flujo de "Obtener información"? …¿Interactuando con el sistema? ¿Y cómo se describe "interactuar", paso a paso? No se puede. **Si no podés describir el flujo sin ambigüedad, no es un caso de uso.**
- ¿Y "Interactuar con el televisor"? Al intentar describirlo aparece de todo: lo prendo, lo apago, cambio el canal, subo el volumen, bajo el volumen… Todo metido en el mismo óvalo.

Ese óvalo-de-todo tiene nombre: un **bodoque** — un módulo con **muy alto acoplamiento y muy baja cohesión**.

> 🕳️ **Madriguera — acoplamiento y cohesión**
> Acoplamiento: cuánto depende un módulo de otros (se busca bajo). Cohesión: cuán enfocado está un módulo en una sola responsabilidad (se busca alta). Acá alcanza con la idea; el detalle es tema de diseño.
> *Volvé al camino — esto se profundiza aparte, otro día.*

### Cohesión funcional, aplicada al caso de uso

La mejor cohesión que puede tener un módulo es la **cohesión funcional**: el módulo hace **una única función**. Y esto aplica igual a una clase, a una actividad… y a un caso de uso. **Un caso de uso = una función.** Por eso no "interactúo": o lo prendo, o lo apago, o cambio el canal, o subo el volumen. Una cosa.

¿Qué gano haciendo una sola cosa por caso de uso?

1. **Control**: sé exactamente qué resuelve cada pieza.
2. **Testeabilidad**: tengo una serie de pasos finitos y discretos que puedo ejecutar y verificar si funciona o no — por ejemplo, al final del primer sprint de desarrollo.

> 🕳️ **Madriguera — sprint**
> Iteración corta de desarrollo (típicamente 1-4 semanas) al final de la cual hay algo funcionando para mostrar y probar. Acá solo importa la idea de "un corte donde testeo".
> *Volvé al camino — esto se profundiza aparte, otro día.*

```
❌  ( Interactuar con el televisor )      ← bodoque: no se puede describir,
                                            no se puede testear

✅  ( Encender TV )  ( Apagar TV )  ( Cambiar canal )  ( Subir volumen ) ...
    una función por óvalo → describible, testeable, con control
```

### El mismo juicio, en los conectores — y la cohesión mala tiene nombre

El bodoque tiene una versión más sutil, que no parece bodoque a simple vista. Mirá la parte trasera del televisor: HDMI, VGA, audio RCA, componente, antena, euroconector, salida óptica… ¿Y si modelo un único caso de uso **"Conectar periférico"** que los cubra a todos?

Pensalo con las dos varas de diseño:

- **Acoplamiento**: ese caso de uso necesita *todos los tipos de conectores* como dato de entrada — depende de todo el panel. **Alto acoplamiento.**
- **Cohesión**: su escenario sería una serie de "IF es HDMI… IF es VGA… IF es antena…". Esa cohesión también tiene nombre: **cohesión lógica** — el módulo agrupa cosas "parecidas" y las distingue a puro IF adentro. Es la cohesión mala: escenario inmantenible y difícil de testear.

La salida es la de siempre: **modelar cada "Conectar X" por separado**. Cada caso de uso requiere solo *su* tipo de conector como entrada (**bajo acoplamiento**) y su escenario no tiene IFs — a lo sumo, verificar que el conector exista (**cohesión funcional**). Un cable, un óvalo, una función.

Fijate cómo la palabra **función** unifica todo el hilo: cohesión **funcional** → un caso de uso es una **función** que pretende el actor → relacionado con un requerimiento **funcional**. No es casualidad: es el mismo concepto mirado desde tres lugares.

**Para el parcial, si te preguntan por qué "Obtener información" no es un caso de uso**
Porque es ambiguo: no se puede describir su flujo normal paso a paso ni definir cómo verificarlo. Un caso de uso representa una única función específica del actor (cohesión funcional); un nombre genérico agrupa muchas funciones en un módulo de baja cohesión que no se puede describir ni testear.

---

## 🔴 4. Verbos vetados: los sensoriales y los del sistema

En esta materia vas a escuchar todo el tiempo dos palabras: **ambiguo** y **específico**. Si algo es ambiguo, no puedo imaginarme cómo se resuelve ni qué pretende resolver — y eso lo descalifica. Los primeros candidatos a caer por ambiguos son ciertos verbos.

**Los sensoriales: ver, escuchar, oír.** No son casos de uso. ¿Qué hago para ver? Abro los ojos. ¿Para escuchar? Nada — escucho, salvo que me tape los oídos. Son funciones del cuerpo: pasivas, no son acciones que me permitan tomar una decisión, hacer un análisis o una interpretación. Lo que el actor quiere del televisor no es "ver": es que el sistema le dé contenido para ver — y eso se nombra por la acción activa que lo logra.

**Los del sistema: "Mostrar".** "Mostrar" está mal por otra razón: es el punto de vista **del sistema** ("el sistema muestra"), no del actor. El nombre correcto nace de la intención del actor, con un verbo activo desde su lado del mostrador.

---

## 🔴 5. Las reglas de nombrado

Consolidadas en una tabla — son las reglas contra las que se corrige cada óvalo:

| Regla | ❌ Mal | ✅ Bien |
|---|---|---|
| **Verbo en infinitivo**, nunca gerundio ni conjugado | Cambiando canal | Cambiar canal |
| **Un verbo + un objeto** — el verbo solo no alcanza | Cambiar | Cambiar canal |
| **Un solo verbo** — una función por óvalo | Prender y apagar TV | Encender TV / Apagar TV |
| **Punto de vista del actor**, no del sistema | Mostrar turnos | Consultar turnos |
| **Verbo activo**, no sensorial | Ver contenido | Reproducir contenido |
| **Sobre objetos, no sobre datos** | Ingresar datos | Registrar venta |
| **Específico, no ambiguo** | Obtener información | Consultar saldo |

**Las palabras prohibidas: "datos" e "información".** Ponerlas en el nombre de un caso de uso **descuenta medio punto, directo**. La razón de fondo: el verbo se ejecuta **sobre un objeto**, no sobre un dato. El objeto es el que está modelado *con* datos — sus atributos, que toman valores distintos en cada instancia. "Ingresar datos" no dice nada; "Registrar venta" dice exactamente sobre qué objeto opera la función.

**Dos parecidos que son casos de uso distintos:**

- **Cambiar canal ≠ Seleccionar canal.** Cambiar es el zapping: no sé qué ver y voy pasando. Seleccionar es que ya sé qué canal o contenido quiero. Distinta intención → distinto caso de uso.
- **Encender ≠ Apagar.** Son dos cambios de estado distintos, con condiciones de arranque distintas. Dos óvalos, siempre.

☕ Esto es la **regla del café con leche** de la clase 1, ahora aplicada a casos de uso: arrancá con los óvalos separados y granulares; si después resulta que eran lo mismo, los unís — al revés no se puede.

---

## 🔴 6. Lo que nadie pidió también se modela

En el pedido del televisor, nadie escribió "quiero apagarlo". ¿Entonces Apagar TV no va? Va — y entender por qué es central para todos los TPs que vienen.

El que pide un sistema describe lo que le importa; hay funciones que **se derivan** de su pedido aunque no las haya dicho. Para encender el televisor, tuvo que estar apagado; si lo enciende, en algún momento lo va a querer apagar. Yo lo pongo aunque no me lo pida, porque **sé que lo necesita**: se deriva de todo lo que me pidió.

La regla general: **el diagrama no es una transcripción literal del enunciado.** Pueden — y suelen — aparecer casos de uso que ningún usuario nombró, derivados de lo que entendemos del negocio. Ojo con el equilibrio: derivar no es inventar. Lo derivado se justifica desde el pedido real; lo inventado de la nada es agregarle al sistema funciones que nadie necesita.

---

## 🔴 7. La plantilla: precondición y poscondición

Cada caso de uso, además del óvalo en el diagrama, se documenta con una plantilla. Su esqueleto:

```
┌─────────────────────────────────────────────┐
│ CASO DE USO: (nombre)          ACTOR: ...   │
│ OBJETIVO: ...                               │
│ PRECONDICIÓN: ...                           │
├──────────────────────┬──────────────────────┤
│ FLUJO NORMAL         │ FLUJO ALTERNATIVO    │
│ 1. ...               │ ...                  │
│ 2. ...               │                      │
├──────────────────────┴──────────────────────┤
│ POSCONDICIÓN: ...                           │
└─────────────────────────────────────────────┘
```

El flujo normal es el camino donde todo sale bien; el alternativo, lo que pasa cuando algo falla o se desvía. Y hay dos campos que van de la mano y que conviene saber definir con precisión quirúrgica:

**Precondición: las condiciones que tienen que estar dadas ANTES, para que el caso de uso pueda EMPEZAR.** No para terminarlo — para *empezarlo*. Para encender el televisor, tiene que estar apagado. Para apagarlo, encendido. La precondición **habilita el inicio**; es previa por definición (la palabra lo dice: *pre*).

**Poscondición: cumplimiento de un objetivo.** Tres palabras, y esa es la definición. ¿Para qué ejecuté todo el flujo? Para lograr un objetivo. Si recorrí el flujo completo, tengo que haber cumplido el objetivo — o hubo un fallo (se cortó la luz, se rompió algo: flujo alternativo) y no llegué. Y una vara fina que la acompaña: el flujo no puede hacer **ni cosas de más** que excedan el objetivo, **ni cosas de menos** que no lleguen a cumplirlo.

Los dos conceptos se retoman con lupa más adelante en la materia, cuando lleguen los escenarios.

**Para el parcial, si te preguntan precondición y poscondición**
La precondición es el conjunto de condiciones que deben estar dadas antes de que el caso de uso pueda comenzar a ejecutarse (habilita el inicio, no la finalización): para Encender TV, el televisor debe estar apagado. La poscondición es el cumplimiento del objetivo del caso de uso: al completarse el flujo normal, el objetivo quedó logrado, sin acciones de más ni de menos.

---

## Cierre de la Parte 1

Ya sabés qué es un caso de uso, cómo se detecta un impostor y cómo se nombra uno de verdad. Lo que falta es el otro lado de la línea: **quién** pide. En la Parte 2: por qué "Usuario" como nombre de actor descuenta puntos, qué significa que un actor sea un rol y no una persona, los actores que no son humanos (incluido uno inesperado: el Tiempo), el actor abstracto, y cómo se hereda entre actores.

**FIN DE LA PARTE 1**
