# 📘 APUNTE MAESTRO — Clase 07 · Repaso de RF y RNF, simulacro y quiz — Parte 1

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Unidad:** `clase07` · Jueves 24/09/2026 · Virtual (Zoom)
**Parte 1:** por qué los RNF son los difíciles; cómo se verifica uno; un caso real de requisito incompleto; la corrección en vivo de requisitos de la máquina expendedora; el sistema como software más hardware.

---

## Sobre esta parte

**Qué cubre:** el repaso de la redacción de RNF con foco en la sintaxis objeto-atributo-valor y en el "desde cuándo" · cómo se verifica una disponibilidad · un pliego real donde una preposición y una voz pasiva obligaron a reescribir todo · el cuadro RNF (qué pregunta responde, cómo se valida) y la distinción entre RNF transversales y RNF de una función · seis correcciones en vivo sobre requisitos de la máquina expendedora de pasajes · el sistema es software más hardware, y lo que eso implica para el integrador.

**Qué viene después:** Parte 2: el simulacro ParkingDog en salas (actores, componentes vs. funciones, tiempo real vs. en línea), el quiz de repaso y la información operativa, que incluye el formato del parcial del 01/10.

**Marcas:** 🔴 central, evaluable · 🟡 secundario · 🟢 al pasar · 🕳️ madriguera.

## De dónde venís

De las clases 04 y 06: la guía de RF y RNF de la cátedra (características de calidad, rol + verbo + objeto, objeto + atributo + valor + unidad, ISO 25010, reglas de negocio), las reglas de redacción que salieron de la corrección de los casos del gimnasio, y la lista DEO. Esta clase no vuelve a explicar nada de eso: lo da por leído y lo usa para corregir. Si algo no te suena, la clase desde cero de RF y RNF es el lugar.

---

## 1. 🔴 Lo que se corrige no es la identificación, es la redacción

Un punto de partida honesto: en las entregas de RF y RNF, lo que se identifica como requisito **sí son requisitos**. No es que estén mal detectados. Lo que se puede optimizar es **la forma en que están redactados**, para que tengan mejor calidad: que se puedan medir, que tengan una sola interpretación.

Los funcionales no son el problema. Un RF es algo que el usuario o el actor quiere lograr en su interacción con el sistema, y se escribe **desde el punto de vista del usuario**. Si siguen apareciendo "el sistema debe, el sistema debe, el sistema debe", es lo mismo de siempre: corregir el sujeto. Es lo más fácil de incorporar.

**Lo difícil son los no funcionales.** Y por eso esta parte es casi toda sobre ellos.

## 2. 🔴 La sintaxis del RNF: valor de qué atributo de qué objeto

Para que un RNF se pueda medir o entender de forma **unívoca**, hay que identificar las partes que componen la oración. Es una cuestión **sintáctica**: analizar la frase.

> *El tiempo máximo de entrega de una notificación es de 2 segundos.*

Lo que hay que entender es: **¿cuál es el valor, de qué atributo, y ese atributo a qué objeto pertenece?** Con eso identificado, se puede medir, se pueden definir métodos para medir, y se puede establecer si se cumplió o no la restricción sobre la funcionalidad.

Y una precisión que varias entregas ya traían bien: **desde cuándo**. *"El tiempo máximo de entrega de la notificación es de 2 segundos desde tal hecho"*: ahí está dicho desde qué momento se empieza a contar el tiempo que se va a contabilizar. Sin el "desde", el valor no tiene punto de partida.

## 3. 🔴 Cómo se verifica: el caso de la disponibilidad

> *La disponibilidad del software es de al menos el 99,9% del tiempo durante horario laboral.*

¿Por qué esta forma y no "el sistema debe estar disponible"? Porque la segunda todos la van a interpretar, pero pueden surgir **distintas interpretaciones sobre cómo validar** que la restricción se cumple. Con el porcentaje y el horario, la validación es concreta: **el equipo de operaciones tiene el registro de las caídas del sistema** y con eso verifica el valor. Y hay una segunda instancia, ya de operaciones: ante cada caída, un **análisis de causa y efecto** para entender qué pasó y cómo evitarlo.

Si escribís "el sistema debe estar disponible", no queda claro qué se está midiendo. Queda tácito. Y lo tácito no se verifica.

## 4. 🔴 Un caso real: el pliego de las impresoras

Un ejemplo de la vida real, para ver el impacto de un requisito incompleto.

> **ONTI** (Oficina Nacional de Tecnologías de Información) es el organismo que define las especificaciones técnicas y los modelos de pliego de todo lo que compra el Estado: hardware, sistemas, redes, impresoras. Quien compra tiene que ajustarse a esas especificaciones o justificar por qué no lo hace.

Un pliego de servicio de impresión tenía una columna que decía: **"cantidad de copias garantizadas por impresora"**. Y se completa con un número: mil, dos mil. Una impresora tiene un índice de productividad: cuántas copias puede hacer sin que empiece a fallar. Entonces, ¿qué quiere decir "mil copias garantizadas por impresora"? ¿Es lo que la impresora **resiste**? ¿O es lo que el organismo **se compromete a imprimir** como mínimo, para que el proveedor calcule su retorno de inversión, la reposición de insumos y la amortización?

Más abajo, el mismo pliego decía **"cantidad de copias garantizadas *para* la impresora"**. Cambió la preposición. "Por" suena a que la impresora garantiza; "para" suena a que el organismo garantiza.

El problema de fondo: **el verbo "garantizar" quedó en voz pasiva**. "Garantizadas por alguien", y no sabemos quién. Ni si era la impresora o el usuario. Resultado: uno interpretó una cosa, quien lo escribió interpretó otra, y **hubo que escribir todo de nuevo**, porque lo que siguió se basó en un supuesto que no era.

Lo que muestra: faltan elementos en la definición que hacen que el requisito sea **completo**. Al ser incompleto, no hay forma de verificar si es consistente ni nada más. Distintas interpretaciones, y el impacto es rehacer.

> **Para el parcial, si te preguntan:** *¿Qué problema tiene un requisito escrito en voz pasiva?*
> La voz pasiva deja el sujeto tácito: no dice quién realiza la acción o quién garantiza la condición ("cantidad de copias garantizadas por impresora": ¿garantiza la impresora o el comprador?). Eso vuelve al requisito ambiguo e incompleto, con más de una interpretación posible, y por lo tanto no verificable. Se escribe en presente indicativo, afirmativo, con el responsable explícito.

## 5. 🔴 Los ejemplos de la guía, con su porqué

Tres ejemplos de la guía de RF y RNF, con la razón que cada uno enseña.

**Tiempo de aprendizaje.** *El tiempo máximo de completitud de la inscripción es de 5 minutos, en la primera ejecución sin asistencia externa, para el 80% del personal de la Secretaría de Alumnos.* "Sin asistencia externa" quiere decir: una vez capacitado, lo terminás solo. ¿Por qué 80% y no todos? Porque puede haber usuarios a los que les cueste más aprender. Si lo aprendieron todos, bárbaro; pero hay que poner una métrica, y el mínimo es el 80%. Si estás debajo, hay algo que cambiar: las pantallas, la tipografía, la interfaz, o la capacitación.

**Capacidad de ser probado.** *Al menos el 80% de las funcionalidades se pueden testear con pruebas automatizadas.* Si lo escribís genérico ("se podrá probar con pruebas automatizadas"), probaste una, anduvo, y no sabés si cumpliste.

**Portabilidad.** Los sistemas operativos en los que tiene que correr, con su versión.

## 6. 🔴 El cuadro del RNF, y dos clases de RNF

A diferencia del RF, el RNF **define la restricción**: bajo qué condiciones se tiene que dar esa función. No cualquier condición.

| | RNF |
|---|---|
| ¿Qué pregunta responde? | ¿Cómo lo hace el sistema? ¿Bajo qué restricciones? |
| ¿Cómo se valida? | Midiendo una propiedad, verificando que se cumpla la propiedad definida |

Ese valor **puede cambiar según el modelo o la circunstancia**: para un contexto de carga puede ser un número y para otro, otro.

Y hay **dos clases de RNF**:

- **Transversales al sistema.** Cuestiones genéricas que no son intrínsecas a una función: la compatibilidad con el sistema operativo, el cumplimiento de la normativa de datos personales, la autenticación con doble factor. Cualquier función que hagas va a tener que pasar por ahí: entrás con doble factor sin importar qué vayas a hacer después.
- **De una función.** Las mismas funciones que definís tienen sus propias restricciones. Cuando vayas a desarrollar **el escenario de ese caso de uso**, esas condiciones se van a estar dando, o las tenés que contemplar para saber bajo qué condiciones se resuelve.

## 7. 🔴 Corrección en vivo: la máquina expendedora

Los seis casos siguientes son requisitos escritos para la máquina expendedora de pasajes de tren (el caso del Metro de Madrid). Cada uno viene con lo que tenía, por qué, y cómo queda. No importa quién lo escribió: como ejemplos, están buenísimos.

### 7.1 "Interactuar" no es una función

```
❌  Las formas de interacción con las máquinas expendedoras son a través de
    un teclado táctil y una interfaz interactiva hablada.
```

Está escrito como si fuera una acción del actor: "forma de interacción" aparece como objeto. Lo que interesa entender es **qué dispositivos** tiene la máquina para poder interactuar. Es como cuando definís una computadora: tengo puerto USB 2.0, HDMI, VGA. Enumerás qué características tiene el elemento, porque sabés que eso te va a dar la posibilidad de conectar un mouse o un proyector.

El problema de fondo: **"interactuar" no es una función**. ¿Cómo definís el escenario "interactuar"? Se describe a sí mismo. Cada instancia de interacción va a ser distinta. Interactuar con la máquina es **cómo** logro mi cometido; mi cometido es **comprar un pasaje** o **cargar una tarjeta**. No es ponerme a charlar con la máquina: la máquina expendedora no es un Arturito, es una máquina para vender pasajes.

```
   ¿Qué quiero hacer?    → comprar el pasaje         → función (RF), con el pasajero como sujeto
   ¿Cómo lo logro?       → con la máquina, tocando   → restricción (RNF), sin el pasajero
                            el timbre, por la ventanilla
```

Todo lo que sea **qué** quiero hacer, lo escribo con el actor como sujeto: ahí aparece el pasajero. Todo lo que sea **cómo** lo hace el pasajero, no aparece el pasajero: me centro en qué cosas tengo que completar.

```
✅  Los dispositivos de interfaz de la máquina con el pasajero son un teclado
    táctil y una interfaz interactiva de voz.
```

Ahora sí se puede medir: cuando recibo la máquina y la instalo, me aseguro de que dispone de un teclado táctil que funcione y una interfaz de voz. Abro la máquina, la enciendo, me fijo que los elementos estén. Lo **óptimo** sería un RNF por dispositivo (uno para el teclado, otro para la voz); como tienen los dos, se suman.

Un aviso hacia adelante: más adelante en la materia, cuando se identifiquen verbos del dominio, "interactuar" va a aparecer ("el pasajero interactúa con la máquina") y no se va a poder definir qué quiere decir en el contexto de la venta de pasajes. Porque no es una función objetivo del usuario.

### 7.2 La pantalla de 42 pulgadas: lo que se mide y lo que sobra

```
❌  La pantalla de la expendedora debe tener una medida de 42 pulgadas para
    mejorar la experiencia de usuarios con movilidad reducida.
```

Las 42 pulgadas están bien: eso es lo que interesa medir, que la pantalla tenga esa medida, ni más ni menos. Se puede afinar con un **rango** (un monitor "de 24" en realidad mide 23,2) o con el **área visible** (la diagonal puede ser 42 pero el área visible es menos por el marco, el *bezel*). El 42 queda.

Lo que **no** interesa es el "para qué": *para mejorar la experiencia de usuarios con movilidad reducida*. Se saca. Y además revela una confusión: si la movilidad es reducida, el problema **no es el tamaño de la pantalla, sino la altura a la que está**. Si ponés un monitor de 42 pulgadas muy alto, la persona con movilidad reducida no puede hacer nada por más que quiera. Son **dos cuestiones que se mezclaron**: la medida del hardware (42 pulgadas) y la altura de montaje (otro parámetro, otro RNF).

### 7.3 Los controles en la mitad inferior: sacar al actor

El mismo equipo escribió el RNF de accesibilidad así:

```
❌  Cuando el pasajero activa el comando de desplazamiento, la interfaz debe
    ubicar el 100% de los controles y botones dentro del 50% inferior de la pantalla.
```

"Cuando el pasajero activa…" ya mete una **acción del actor** que dispara algo. Eso es contar cómo se va a resolver el requisito funcional: hay un RF, **Ajustar altura de pantalla** (o Ajustar pantalla), y cuando se escriba **su escenario** se va a describir que la pantalla ubica todos los controles en el área inferior. En el RNF, lo que va es **lo que se mide**, para que cuando se defina el escenario se tenga en cuenta:

```
✅  Los controles y botones se ubican en la mitad inferior de la pantalla,
    en modo de baja altura.
```

Podés poner "todos los controles" para que quede claro que no queda ninguno afuera. Después, el pasajero mueve la pantalla hacia abajo y se cumple esta condición; la mueve hacia arriba porque es muy alto, y la condición se deshace y vuelve la interfaz normal.

Dos reglas que se desprenden:

- **Cuando definís un RNF, el actor desaparece.** No lo tenés en cuenta. Toda la parte de "cuando el pasajero activa el comando" no es necesaria en la definición.
- **El verbo del RNF es "ser".** Es, son, serán. "Será" en futuro está bien acá porque la ubicación se da en el marco de que se desplace la pantalla, no siempre. En general, verbo ser, y nada del actor.

**Los sujetos de las oraciones de los RNF son siempre algo medible**: un parámetro, algo físico. En realidad, el atributo del objeto, el valor que voy a medir. No aparecen ni el sistema ni el actor: que se da en el contexto del sistema es obvio.

### 7.4 "Siempre activo": hace falta un margen

```
❌  El sistema de facturación debe estar siempre activo. Si se cae, debe
    solucionarse lo antes posible.
```

Muy buen ejemplo, porque no pone parámetros: ¿cuánto tiempo se acepta que esté caído? Tampoco se puede poner "siempre activo": hay que darle un margen de error. Es el mismo caso de la disponibilidad del apunte: la disponibilidad es de tanto por ciento en tal contexto, 7×24, 5×9, lo que corresponda.

### 7.5 La cámara: un componente con una característica de calidad

Un equipo había escrito *"el sistema debe incorporar una cámara y una pantalla de 42 pulgadas"*, y la duda fue: si "el sistema debe" está mal, ¿cómo se redacta que el sistema tenga que tener una cámara?

No es una característica del sistema: es **un componente** del sistema, que se enumera y al que se le pone **una característica de calidad**. Lo que interesa saber de la cámara es qué características tiene que tener. Porque si decís "una cámara" y te traen una con rollo de los 90, no sirve. El celular tiene cámara, pero no es lo mismo la que se le da a un chico que la que usa alguien que publica contenido.

```
✅  La pantalla de interfaz con el usuario es de 42 pulgadas.
✅  La definición mínima de la cámara es de N megapíxeles.
```

El artículo del que salió el caso no especificaba la cámara, porque para su público no era importante. **En el contexto académico, se puede inventar el valor**; en un contexto laboral, vas y te fijás qué posibilidades hay. Y después ese valor se asocia a otros: si tenés una cámara muy potente no podés tener un procesador que no lo sea. Elementos interrelacionados entre sí.

### 7.6 Sistema = software + hardware

Lo anterior se conecta con la definición de sistema de las primeras materias: un conjunto de elementos interrelacionados entre sí con un objetivo común. **El software solo, sin hardware, no funciona**: está desarrollado, divino, bonito, pero hay que ponerlo operativo sobre un hardware. Son los dos componentes que se unen, y el límite del sistema hay que verlo con los dos adentro.

**Consecuencia para el integrador:** este cuatrimestre, en vez de presentar solo tres soluciones de software, algunos equipos van a tener que **definir el hardware asociado** para implementar esas soluciones.

> 🕳️ **Madriguera — SUBE, ARCA y los pliegos**
> Los ejemplos de pliegos, impresoras y máquinas expendedoras vienen del trabajo real en organismos públicos, donde cada compra pasa por una especificación técnica formal. Es el contexto donde un RNF ambiguo cuesta plata de verdad.
> *Volvé al camino: acá se usa solo como evidencia de por qué la sintaxis importa.*

> **Para el parcial, si te preguntan:** *¿Qué diferencia hay entre "el pasajero interactúa con la máquina" y "el pasajero compra un pasaje"?*
> "Comprar un pasaje" es la función: el objetivo que el actor quiere lograr, y se escribe con el actor como sujeto. "Interactuar" no es una función, porque no tiene un objetivo ni un escenario definible: describe cómo se logra el objetivo. El cómo se especifica como RNF, sin el actor, sobre los dispositivos de interfaz de la máquina ("los dispositivos de interfaz con el pasajero son un teclado táctil y una interfaz de voz").

---

## Info operativa de esta parte

- Las correcciones sobre el documento compartido de requisitos siguen: se van a seguir agregando comentarios, y hay tiempo hasta el **viernes 25/09 a las 19:00** para resolver o agregar.
- En el integrador, **algunos equipos van a tener que definir el hardware asociado** a las soluciones que propongan.

---

## ✅ Checkpoint — Parte 1

1. ¿Qué es lo que se corrige en las entregas de RF y RNF, si no es la identificación?
2. ¿Qué tres cosas hay que identificar en la sintaxis de un RNF para poder medirlo?
3. ¿Por qué "el sistema debe estar disponible" no se puede verificar, y cómo verifica el equipo de operaciones una disponibilidad del 99,9%?
4. ¿Qué dos problemas de redacción tenía "cantidad de copias garantizadas por impresora" y cuál fue la consecuencia?
5. ¿Por qué el tiempo de aprendizaje se define para el 80% del personal y no para todos?
6. ¿Qué diferencia hay entre un RNF transversal y un RNF de una función? Dá un ejemplo de cada uno.
7. ¿Por qué "interactuar" no es una función? ¿Cómo se reescribe el requisito de las formas de interacción?
8. En el requisito de la pantalla de 42 pulgadas, ¿qué se mide, qué sobra, y qué otro parámetro se estaba mezclando?
9. ¿Por qué "cuando el pasajero activa el comando de desplazamiento" no va en el RNF?
10. ¿Cómo se redacta que el sistema tenga una cámara?

## Qué viene en la Parte 2

El simulacro ParkingDog trabajado en salas: por qué ni la mascota ni la cucha son actores, por qué un sensor no es una función, y la diferencia entre tiempo real y en línea. Después, el quiz de repaso pregunta por pregunta, y la información operativa de la clase, con el formato del parcial del 01/10.

**FIN DE LA PARTE 1**
