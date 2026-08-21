# APUNTE MAESTRO — Clase 02 · Casos de Uso — Parte 2

**Ingeniería de Requisitos — clase02 (20/08/2026) · Parte 2 de 4**
**Esta parte:** actores — rol vs persona, cómo se nombran, los que se derivan del pedido, la herencia entre actores, el actor abstracto, los no humanos y el Tiempo.
**Ya viste:** Parte 1 — qué es un caso de uso y cómo se nombra. **Vienen:** Parte 3 — relaciones entre casos de uso · Parte 4 — los sistemas de punta a punta, info operativa y checkpoint.

**Marcas:** 🔴 central y evaluable · 🟡 secundario · 🟢 mencionado al pasar.
**Notación ASCII de esta parte:** `hijo ──▷ padre` representa la herencia (en papel: línea llena con **triángulo hueco** apoyado en el padre).

---

## 🔴 1. Un actor es un rol, no una persona

Volvé al televisor de la Parte 1. Alguien tiene que estar del lado izquierdo de la línea. La primera tentación es llamarlo **"Usuario"** — y ese nombre está mal por partida doble.

**Primero, es genérico y ambiguo.** ¿Qué hace un usuario? **Usa.** ¿Y cómo se describe "usar"? No se puede: es exactamente el mismo problema de la Parte 1 con "Interactuar" — no hay flujo describible, no hay criterio de aceptación posible para "usar".

> 🕳️ **Madriguera — criterio de aceptación**
> La condición verificable que dice cuándo una funcionalidad está bien hecha ("dado X, cuando Y, entonces Z"). Acá alcanza con la idea: si no se puede escribir para un nombre, el nombre es ambiguo.
> *Volvé al camino — esto se profundiza aparte, otro día.*

**Segundo, no dice qué quiere esa persona del sistema.** El nombre del actor tiene que reflejar **qué quiere hacer** frente al sistema. Para el televisor, el nombre correcto es **Televidente**: específico, y su intención se lee en el nombre.

**La definición: un actor es un ROL.** No una persona, no un puesto de trabajo. Es un sombrero: alguien se pone el sombrero de Televidente y, mientras lo tiene puesto, *es* ese actor. Después se lo saca, se pone otro sombrero, y es otro rol — **la misma persona, instanciada en roles distintos**. Por eso también puede haber cincuenta personas distintas usando el mismo sombrero: siguen siendo un solo actor.

Un matiz para sistemas con perfiles: si el sistema define perfiles de usuario (perfil administrador, perfil cajera), el actor se nombra con **el nombre del perfil** — nunca "Usuario" a secas.

**Para el parcial, si te preguntan qué es un actor**
Un actor es un rol que alguien o algo juega frente al sistema, no una persona ni un puesto. Varias personas pueden instanciar el mismo rol, y una misma persona puede instanciar varios roles distintos según el momento. El nombre debe ser específico y reflejar qué quiere hacer ese rol respecto del sistema ("Televidente", no "Usuario", que es genérico y ambiguo).

---

## 🟡 2. Historia de usuario: la misma regla, dicha en ágil

En metodologías ágiles, la funcionalidad se captura como **historia de usuario**, con esta forma fija:

> "Yo, como **[rol]**, quiero **[hacer tal cosa]** para **[lograr tal otra]**."

Fijate que la plantilla misma exige lo que venimos diciendo: un rol (no "usuario" genérico), una acción concreta y un objetivo. Nunca vas a leer "yo como usuario quiero **usar** para poder lograr algo" — se dice "yo como usuario quiero **acceder a la tabla**": la acción siempre es específica. Es la misma disciplina de nombrado, en otro formato.

---

## 🔴 3. Los actores que se derivan del pedido

En la Parte 1 viste que hay **casos de uso** que nadie pidió y se derivan igual. Con los **actores** pasa lo mismo, y el televisor trae dos.

### El Técnico

Entre las necesidades del televisor había un requerimiento no funcional: superar las 10.000 horas de uso antes de necesitar **mantenimiento de un técnico**. La condición de las 10.000 horas no se dibuja — pero leela de nuevo: ahí adentro hay una persona. El televisor se rompe, llamo al técnico, y el técnico ¿qué hace frente al aparato?

- Lo **enciende** — para ver cómo se ve, para entrar al menú.
- Puede **cambiar el canal** — para probar si sintoniza bien.
- Lo **apaga** — aunque después lo desarme.
- Y hace algo que el Televidente no hace: **Realizar mantenimiento**.

Apareció un actor nuevo, derivado de un RNF. Y con él, una pregunta legítima: cuando el técnico "realiza mantenimiento", el sistema como software ¿no está haciendo nada? ¿Eso puede ser un caso de uso? **Sí.** El televisor manifiesta un comportamiento (falla, se ve mal, hace ruido) y el técnico, frente al aparato, ejecuta la acción que lo resuelve — o al menos lo diagnostica. Es una acción sobre el sistema, y eso alcanza.

El paralelo con un sistema más típico lo deja claro. Pensá en un sistema de cajas para atención al público: el perfil **administrador** no cobra — lo que hace es **configurar**: crear un usuario para la cajera nueva, asignarle un perfil, generarle una primera contraseña que ella va a estar obligada a cambiar en el primer logueo. El administrador "no opera" el negocio, y sin embargo todo eso son casos de uso: acciones sobre el sistema.

### El Instalador / Administrador / Configurador

Tercer actor del televisor, también derivado. El televisor interfacea con otros sistemas — antena digital, WiFi, salidas de audio y video. ¿Quién conecta todo eso?

Pensá en el televisor expuesto en una farmacia o un banco, mostrando los turnos del sistema de cajas; o el del hall de la estación, mostrando los horarios de trenes. El que hizo esa configuración **no es el televidente que mira**, y tampoco necesita ser el técnico que repara. Es alguien intermedio: puede llamarse **Instalador**, **Administrador** o **Configurador** — lo que va a hacer es **configurar** el aparato. Para probar que la conexión de entrada y la salida están bien, también enciende, cambia el canal y apaga.

Tres actores entonces, con capacidades escalonadas: el Televidente hace lo básico; el Instalador hace lo del Televidente **y además** configura; el Técnico hace todo eso **y además** repara. Ese escalonamiento tiene nombre, y es la sección que viene.

---

## 🔴 4. Herencia entre actores: qué significa y cómo se dibuja

**Un actor hereda de otro cuando puede hacer todo lo que hace el otro, y además tiene funciones propias.** El hijo absorbe las capacidades del padre sin redibujarle las líneas: no le repito al Técnico los óvalos de Encender, Cambiar y Apagar — digo que hereda del que ya los tiene.

**La regla que define si hay herencia: la herencia está en QUÉ puedo hacer, no en CÓMO lo hago.** Este es el error clásico: dibujar "Usuario con control remoto" y "Usuario con botón" como actores distintos. No son roles distintos — cualquiera de los dos puede hacer las mismas funciones por cualquiera de las dos vías. El *cómo* se resuelve de otra manera (lo vas a ver en la Parte 3 con la generalización de casos de uso); el actor se hereda solo por el *qué*.

La condición para dibujarla es que el diagrama refleje una de estas **dos formas** — si no se refleja ninguna, no es herencia:

**Forma A — el hijo suma funciones propias.** El padre tiene sus casos de uso; el hijo no repite nada del padre y tiene los suyos:

```
 [actor] Padre ────( CU 1 )
       △          ( CU 2 )
       │
 [actor] Hijo ────( CU propio )
```

El hijo puede hacer CU 1, CU 2 **y** su CU propio. (Es el mismo espíritu que supertipo/subtipo: lo común arriba, lo excluyente abajo en cada uno.)

**Forma B — varios hermanos comparten UNA función del padre.** Actores distintos con funciones distintas, que heredan de un padre que tiene una única función común a todos:

```
 [actor] A ────( CU de A )          [actor] B ────( CU de B )
        └──────────▷  [actor] C  ◁──────────┘
                          │
                     ( CU común )
```

A y B son hermanos; los dos pueden hacer el CU común de C, cada uno además de lo suyo.

**Notación — y esto se corrige:** línea **llena** con **triángulo de punta hueca apoyado en el padre**. Exactamente igual que la herencia entre clases. La flecha sale del hijo y el triángulo toca al padre, nunca al revés.

**Para el parcial, si te preguntan cuándo hay herencia entre actores**
Cuando un actor puede hacer todo lo que hace otro y además tiene funciones propias. La herencia se define por QUÉ puede hacer cada rol, nunca por CÓMO lo hace (dos vías de ejecución no crean dos actores). Se dibuja con línea llena y triángulo hueco apoyado en el actor padre, y el diagrama debe reflejar una de las dos formas: hijo con funciones propias que hereda las del padre, o hermanos que heredan una función común de un padre.

---

## 🔴 5. El actor abstracto

Volvé al sistema de cajas, ahora completo, porque acá aparece la pieza que faltaba.

- La **Cajera** puede abrir la caja, cerrarla, **cobrar**.
- La **Supervisora** puede hacer cosas que la cajera no: una extracción de dinero, un control. Y además **hereda de la Cajera**: si a la cajera le pasó algo, la supervisora puede cobrar y abrir/cerrar caja también. (Forma A: funciones propias + todo lo de la madre.)

```
 [actor] Cajera ──────( Abrir caja )( Cerrar caja )( Cobrar )
       △
       │
 [actor] Supervisora ──( Realizar extracción )( Realizar control )
```

Ahora, el detalle: para hacer **cualquiera** de esas acciones, las dos tienen que **identificarse** en el sistema — hay que saber quién cobró, quién hizo la extracción. ¿Le dibujo "Login" a la Cajera, "Login" a la Supervisora, y así a cada rol que aparezca? No. Se crea un actor **arriba de todas**, cuya única función es el Login:

```
 [actor] Usuario de caja ────( Login )        ← ABSTRACTO: no se instancia nunca
       △
       │
 [actor] Cajera ─────( Abrir caja )( Cerrar caja )( Cobrar )
       △
       │
 [actor] Supervisora ──( Realizar extracción )( Realizar control )
```

Ese actor de arriba es un **actor abstracto**: **no se va a instanciar nunca** — nadie se pone ese sombrero directamente; existe para agrupar lo común que todos los roles concretos heredan. (Es la Forma B vista desde arriba: un padre con una única función que varios heredan.)

Dos detalles finos:

- **El nombre.** "Usuario" a secas cae otra vez en lo genérico — conviene un nombre más representativo del dominio: "Usuario de caja", "Operador de cobranzas". La regla de granularidad del nombre aplica a los abstractos igual que a todos.
- **La transitividad.** ¿Lo que la Cajera hereda del abstracto le llega también a la Supervisora, que está dos escalones abajo? **Sí — la herencia es transitiva.** ¿Hace falta dibujar además una flecha directa de Supervisora al abstracto? A priori no: la cadena ya lo dice. Ponerla no está mal — pero no es necesaria.

Contraste que confirma la regla del *qué*: en este mismo sistema, el perfil **Administrador** (el que crea usuarios y asigna perfiles) **no** hereda de la Cajera — no tiene perfil para cobrar, no puede hacer lo que ella hace. Sin el *qué* compartido, no hay herencia, por más que ambos "usen el sistema".

¿Y se puede crear un actor abstracto en el televisor — un "alguien que opera la tele" arriba de todos? Poder, se puede. La pregunta es si hay una razón: acá no hay una función común que valga la pena subir (como era el Login), así que no se justifica. El abstracto se crea cuando conviene, no por deporte.

**Para el parcial, si te preguntan qué es un actor abstracto**
Es un actor que no se instancia nunca: ningún usuario concreto juega ese rol directamente. Existe para agrupar una funcionalidad común (por ejemplo, Login) que todos los actores concretos heredan, evitando repetir la asociación en cada uno. La herencia desde él es transitiva hacia toda la cadena de hijos.

---

## 🔴 6. La cadena del televisor

Aplicá todo lo anterior a los tres actores derivados en la sección 3, y queda la jerarquía completa del sistema:

```
 [actor] TELEVIDENTE ────( Encender TV )( Apagar TV )( Cambiar canal ) ...
       △
       │
 [actor] INSTALADOR / ADMIN / CONFIGURADOR ────( Conectar entrada ) ...
       △
       │
 [actor] TÉCNICO ────( Realizar mantenimiento ) ...
```

- El Instalador hereda del Televidente: puede encender, cambiar y apagar (lo necesita para probar conexiones) y suma la configuración.
- El Técnico hereda del Instalador: puede todo lo anterior — hasta configurarte el WiFi si hace falta, ahí está la transitividad funcionando — y suma el mantenimiento.
- Triángulo hueco siempre apoyado en el padre; el padre de todos (Televidente) queda arriba de la cadena.

Los casos de uso de cada nivel se completan en la Parte 4, cuando el sistema se arme entero.

---

## 🔴 7. Actores no humanos: los sistemas externos

Aunque se dibuje como monigote, **un actor puede ser algo, no alguien** — típicamente, otro sistema que interactúa con el nuestro. El televisor tiene dos claros:

- **TDA** — la antena digital que le entrega señal.
- **Access point (WiFi)** — el equipo que le da la conexión inalámbrica.

En general, todo componente o sistema externo con el que el sistema interfacea puede modelarse como actor. Y la regla de oro para relacionarlos: **el sistema externo se asocia con el caso de uso específico que le corresponde** — TDA con Conectar TDA, el access point con Conectar WiFi. No con un óvalo genérico de "conectar cosas".

**Dónde van y cómo se dibujan:** los actores **principales** — los que tienen los principales requerimientos — van a la **izquierda**; los sistemas externos son típicamente actores **secundarios** y van a la **derecha**, dibujados con **trazo punteado**. Y son opcionales: **pueden estar o no estar** en el diagrama — omitirlos no está mal, porque el verbo del caso de uso ya está nombrado desde el punto de vista del actor principal.

### El punto de vista, otra vez: ¿importar o exportar?

Cuando el actor es un sistema externo, el nombre del caso de uso sigue la misma regla de siempre — pero ahora hay dos sistemas en juego y hay que elegir el punto de vista. Pensá en un sistema para administrar una discoteca personal (vinilos, CDs, cassettes) que quiere traerse las listas de reproducción de Spotify. ¿El caso de uso se llama "Exportar canción" o "Importar canción"?

Preguntate **cuál es tu producto**. Tu sistema es la discoteca — el melómano quiere **traer** la canción hacia su sistema. Desde el punto de vista de tu producto, la canción se **importa**. Que Spotify la exporte es el punto de vista del otro sistema, y el diagrama es del tuyo. El actor externo Spotify se asocia entonces con **Importar canción** — el caso de uso específico, nombrado desde tu lado del mostrador.

---

## 🔴 8. El Tiempo como actor

Hay funcionalidades que ningún actor evidente dispara activamente: las **temporales, programadas o de notificación**. Algo tiene que pasar "a las 7:00", o "cada vez que se cumpla X tiempo" — ¿quién aprieta ese botón?

Para eso se modela **el Tiempo (o Reloj) como actor**. La idea suena rara la primera vez, y la forma de domesticarla es esta: usar al Tiempo como actor es como **llamar al 113** — el servicio telefónico de la hora. Le pregunto: "¿qué valor tenés?", y me contesta "son las 17:19". Eso es todo lo que hace el actor Tiempo: **entregar el valor de fecha/hora cuando el sistema se lo consulta**.

```
 ( Tomar time-stamp / fecha y hora ) ─────── [actor] TIEMPO/RELOJ    ← punteado
```

El Tiempo es un actor secundario: va a la derecha, con trazo punteado. Y una advertencia que después se corrige en los diagramas: si vas a usar el actor Tiempo, **cuidado con qué caso de uso lo relacionás** — se relaciona con el caso de uso que efectivamente le consulta el valor (acá, el que toma el time-stamp), no con cualquier función que "tenga que ver con tiempo".

¿Y para qué quiere el televisor un time-stamp? Acordate de las 10.000 horas de la garantía: alguien tiene que poder saber cuánto tiempo estuvo encendido el aparato. Cómo se engancha ese mecanismo con Encender TV y Apagar TV es historia de la Parte 3, porque necesita una relación que todavía no viste: la inclusión.

---

## Cierre de la Parte 2

Ya tenés los dos lados de la línea: funciones bien nombradas (Parte 1) y roles bien definidos, con su herencia y sus variantes no humanas (esta parte). Falta lo que pasa **entre los óvalos**: en la Parte 3, las tres relaciones entre casos de uso — la generalización (y el polimorfismo que la habilita), la inclusión y la extensión — más las dos fronteras donde todo el mundo se equivoca: relación vs precondición, y caso de uso vs proceso.

**FIN DE LA PARTE 2**
