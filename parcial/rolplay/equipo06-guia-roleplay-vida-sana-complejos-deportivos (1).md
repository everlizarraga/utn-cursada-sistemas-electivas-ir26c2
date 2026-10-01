# 🎯 EQUIPO 6 — Guía para el role-play: Complejos Deportivos Vida Sana

**Materia:** Ingeniería de Requisitos — UTN FRBA — 2C 2026
**Fecha del role-play:** jueves 01/10/2026 (1º parcial, presencial, 18-20 minutos)
**Entrega posterior:** minuta de reunión — jueves 08/10/2026 (la presentan ambas partes)

> **Cómo usar este documento.** Tiene cinco partes. Las partes 1, 2 y 5 son para **todos** (10 minutos de lectura). La parte 3 es el lado **entrevistador**, dividida en Entrevistador 1 a 5. La parte 4 es el lado **Junta Directiva**, dividida en cuatro roles. **El rol del equipo se asigna el mismo día con 5 minutos de preparación**, así que cada uno se prepara su número para los dos lados: el que es Entrevistador 3 (pagos) es el Director Financiero si nos toca Junta. Es el mismo tema, visto desde las dos sillas.

---

## PARTE 1 — Para todos: vocabulario y mercado

### 1.1 Glosario del negocio (usarlo en voz alta: la rúbrica evalúa "vocabulario del negocio")

| Término | Qué significa |
|---|---|
| **Turno** | La unidad que se vende: una cancha, en un horario, por una duración fija. Todo el sistema gira alrededor del turno. |
| **Grilla** | El calendario de turnos de una cancha: la vista de horarios ocupados y libres de un día. |
| **No-show** | El socio que reservó y no se presentó. Es el problema clásico del rubro: la cancha queda vacía y nadie más la puede usar. Por eso existen las señas y las penalidades. |
| **Seña** | Pago parcial al momento de reservar. Compromete al que reserva y reduce el no-show. |
| **Horario pico / horario valle** | Pico: cuando todos quieren jugar (martes 20 hs). Valle: horario muerto (martes 15 hs). Se llama "valle" por la forma de la curva de demanda. Los valles se llenan con promociones. |
| **Doble booking** | Dos reservas para la misma cancha en el mismo horario. El error que toda plataforma del rubro promete evitar. |
| **Cuota social** | Abono mensual fijo del socio, independiente de lo que consuma. En Vida Sana es la cuota del gimnasio; la pregunta es si da beneficios en las canchas. |
| **Socio / no socio** | Quien paga cuota social vs. quien viene solo a alquilar cancha. Define padrón, precios y permisos distintos. |
| **Titular de la reserva** | El jugador que reserva y responde por el turno (pago, cancelación). |
| **Lista de espera** | Cola de interesados en un turno ocupado; si se libera, el sistema avisa. El gimnasio ya la usa para las clases. |
| **Bolsa de jugadores** | Función de las apps del rubro para armar partido con gente suelta que busca completar equipo. |

### 1.2 Lo que ya existe en el mercado (criterio de rúbrica: "conocimiento de herramientas de software relevadas")

Hay plataformas argentinas específicas para paddle y fútbol 5 que resuelven casi todo lo que pide el enunciado: **ATC Sports**, **Canchero**, **CanchaManager**, **Reservá tu Cancha**, **Dónde Juego**.

Lo que traen de fábrica (y por lo tanto lo que la Junta puede estar imaginando sin decirlo):

- Grilla por cancha con disponibilidad en tiempo real y prevención de doble booking.
- Seña cobrada al reservar, integrada con Mercado Pago.
- Precios diferenciados por horario (pico/valle) y por tipo de cliente.
- Recordatorios automáticos por WhatsApp para bajar el no-show.
- Torneos con fixture y tabla de posiciones automáticos; bolsa de jugadores.
- Roles separados de dueño y staff; reportes de caja y ocupación.
- Arquitectura multi-sede (sirve si Vida Sana se expande).

**Para qué sirve saberlo:** como entrevistador, habilita la pregunta "¿evaluaron adoptar una plataforma de mercado y adaptarla, o prefieren desarrollo a medida?". Como Junta, da respuestas con vocabulario del rubro y permite decir "queremos algo como X pero integrado al gimnasio".

---

## PARTE 2 — Para todos: el negocio

### 2.1 Lo que existe hoy (Centro de Entrenamiento Vida Sana)

Gimnasio con 10 profesores. Clases de pilates, funcional, stretching y yoga; sectores de cardio y musculación. Planes de 4, 6, 8 y 12 clases. Hay **lista de espera**, **señas** y **aviso de ausencia con 1 día de anticipación**.

Problemas conocidos: **todo en papel**, cruzado en 4 carpetas; el socio se identifica con 3 letras del nombre + 2 del apellido → **colisiones de identificador**.

### 2.2 Lo que ya acordó la Junta en la reunión anterior (clase 5 — esto es memoria del personaje)

- La Junta reconoció una **pérdida del 5%** por pagos no registrados → decidió que **el cobro pase por la app**, nunca por los profesores.
- **Acceso por QR** (operativo en 45 días por una feria de fitness). Molinete en segunda etapa.
- **Cámaras** para contar asistentes y cruzar contra pagos.
- MVP por etapas.
- El **presidente viaja** y necesita ver **desde el celular**: clases dictadas, asistentes por clase, socios deudores, recaudación mensual.
- **Hoy una sola sucursal, con intención de expandirse.** Los complejos deportivos SON esa expansión.

### 2.3 Lo nuevo (enunciado del parcial)

Canchas de **paddle, fútbol 5 y golfito**. App con **inscripciones, reservas y pagos, promociones, redes de amigos y campeonatos, fidelización**. **El buffet está concesionado y queda fuera del alcance.** Las canchas se están instalando: **no hay personal ni operación todavía**, por eso no se entrevista a empleados.

### 2.4 La idea que ordena todo

Cada problema del gimnasio tiene su versión en las canchas:

| Gimnasio (hoy) | Canchas (a definir) |
|---|---|
| Lista de espera de la clase | Cola de reserva de cancha ocupada |
| Seña de la clase | Seña del turno |
| Aviso de ausencia con 1 día | Política de cancelación del turno |
| Colisión de identificadores | Identificación unívoca del socio |

**Lo nuevo se parece a lo viejo, pero nada está decidido todavía.** Entonces: como entrevistador, nunca "¿cómo hacen hoy las reservas?" (no hay reservas todavía) sino **"¿cómo quieren que funcione?"**. Como Junta, respondemos en términos de lo que queremos, apoyándonos en cómo ya funciona el gimnasio.

### 2.5 La regla de oro (viene de las correcciones de la profe a nuestra minuta anterior)

**Ninguna respuesta se da por cerrada hasta que tenga quién, cuánto y cuándo.**

- Entrevistador: repreguntar hasta obtener el número y el responsable. "Con tiempo" no es una respuesta; "7 días" sí.
- Junta: responder ya con el número y el responsable, sin esperar que nos lo saquen. Eso es "respuesta completa" en la rúbrica.
- **Evitar el "se" impersonal** al hablar y al escribir: "el socio cancela", no "se cancela"; "administración autoriza", no "se autoriza".

---

## PARTE 3 — Lado ENTREVISTADOR

**Estructura de la entrevista:** 5 bloques, ~18 minutos de preguntas base, 2 minutos de margen para repreguntar. Mayormente **preguntas abiertas** (dejan desarrollar); las cerradas se usan al final para fijar un dato puntual ("¿entonces la seña es obligatoria?").

**Preguntas prohibidas:** cargadas (transmiten nuestra opinión), inductoras (llevan a una respuesta), sesgadas (meten la respuesta adentro), críticas ("la entrevista es para investigar, no para evaluar").

Cada entrevistador arranca con un recuadro **🗺️ Lo que tenés que sacar de este bloque**: leelo primero. Es el panorama del bloque; si lo tenés claro, podés improvisar aunque te olvides las preguntas.

Después, cada pregunta tiene tres niveles:
- 🎯 **La pregunta** — es lo que decís.
- 📘 **Por qué** — no se lee en voz alta; es para entender qué buscás.
- 🟢 **Respuesta esperada** — no se lee; sirve para saber si te contestaron completo o falta repreguntar.

### Entrevistador 1 — Conductor: apertura, alcance y cierre (bloque 1: 2 min + bloque 5 cierre: 1 min)

> **🗺️ Lo que tenés que sacar de este bloque — leer primero**
> Dejar fijado el marco antes de que nadie pregunte detalles. Tenés que salir sabiendo cuatro cosas: **qué entra y qué no** (las tres canchas adentro, el buffet afuera por estar concesionado); si esto es **parte de la misma app del gimnasio o un sistema aparte**; si reservan **solo socios o también gente de afuera** (eso define padrón y precios); y **cuándo arrancan** las canchas, para saber qué tiene que estar listo el día uno. Si lográs eso en 2 minutos, el resto del equipo pregunta sobre terreno firme.

**Además de sus preguntas, el Entrevistador 1:** se presenta, presenta al equipo y los roles, declara objetivo y duración, controla el tiempo, y cierra.

**Apertura (decirla tal cual, 30 segundos):**
> "Buenas tardes, somos el equipo de analistas. Yo soy [nombre], coordino la entrevista; [nombre] va a tomar nota para la minuta; [nombres] van a consultar sobre reservas, pagos y la parte social. El objetivo de hoy es relevar cómo quieren que funcione la aplicación de los complejos deportivos; tenemos 20 minutos. En la reunión anterior acordamos que el cobro pase por la app y el acceso con QR; hoy queremos entender cómo se suman las canchas a eso."

🎯 **P1. "Para arrancar, ¿nos confirman qué servicios quedan dentro del alcance de esta solución y cuáles quedan afuera?"**
📘 Abierta: los deja declarar el límite. Si no mencionan el buffet, repreguntá: "¿el buffet concesionado queda fuera?". Muestra que viniste preparado.
🟢 Las tres canchas (paddle, fútbol 5, golfito) adentro; el buffet afuera por estar concesionado.

🎯 **P2. "¿Cómo imaginan la relación entre esto y la app del gimnasio: un mismo sistema o dos separados?"**
📘 Es la pregunta bisagra. NO decir "¿quieren que sea el mismo?": eso es inductora.
🟢 Un mismo sistema, mismo registro de socios. Si dicen "separado", repreguntá por qué y cómo se identifica al socio en los dos.

🎯 **P3. "¿Quién puede reservar una cancha: solo socios del gimnasio, o también personas de afuera?"**
📘 Define si hay padrón nuevo, precios diferenciados y registro distinto. Casi nadie la hace.
🟢 Socios y no socios, con precio diferenciado. Repreguntá: ¿el no socio necesita registrarse en la app?

🎯 **P4. "¿Cuándo prevén que las canchas empiecen a operar?"**
📘 Da el horizonte y habilita hablar de etapas: qué tiene que estar sí o sí el día uno.
🟢 Una fecha o un plazo en meses, y qué es imprescindible para esa fecha (reservas y pagos primero; campeonatos y fidelización después).

🎯 **P5 (opcional, si sobra tiempo en cualquier momento). "Existen plataformas de mercado como ATC o CanchaManager que ya resuelven grilla, señas y torneos. ¿Evaluaron adoptar una y adaptarla, o prefieren desarrollo a medida integrado al sistema del gimnasio?"**
📘 Cubre el criterio de rúbrica "conocimiento de herramientas de software relevadas". Casi ningún equipo lo va a cubrir.
🟢 Una postura y su razón: a medida por integración con el gimnasio, o de mercado por tiempo y costo.

**Cierre (decirlo tal cual, último minuto):**
> "Para cerrar, me llevo que [las tres cosas más fuertes que escuchaste: ej. las canchas se integran a la app del gimnasio, la reserva requiere seña, los campeonatos los organiza el complejo]. ¿Hay algo importante que no hayamos preguntado? Les vamos a hacer llegar una minuta con todo lo tratado para que la revisen y nos corrijan."

### Entrevistador 2 — Reservas (bloque 2: 5-6 min, es el núcleo)

> **🗺️ Lo que tenés que sacar de este bloque — leer primero**
> La reserva es el corazón del sistema: todo lo demás (pagos, campeonatos, premios) cuelga de ella. Tenés que salir con la **regla completa de una reserva**: con cuánta **anticipación** se puede hacer, cuánto **dura un turno** en cada deporte (no es lo mismo paddle que fútbol 5), **quién** reserva y responde por el turno (el titular), hasta cuándo se puede **cancelar** y qué pasa con lo pagado, y qué quieren que ocurra cuando la cancha **ya está ocupada** (acá tiene que aparecer la lista de espera, dicha por ellos). Cada respuesta tiene que cerrar con un número o un responsable; si te dan "con tiempo" o "se avisa", repreguntá.

🎯 **P1. "¿Con cuánta anticipación quieren que un socio pueda reservar una cancha?"**
📘 Fija la ventana de la agenda, que define cómo se arma la grilla.
🟢 Un número y quién lo define: "7 días, lo define administración y queremos poder cambiarlo". Si dicen "con tiempo", repreguntá por el número.

🎯 **P2. "¿Cuánto dura un turno en cada deporte?"**
📘 Paddle, fútbol 5 y golfito no duran lo mismo, y el turno es la unidad de la grilla.
🟢 Tres duraciones distintas (ej. 90 min fútbol 5, 60 min paddle, 45 min golfito). Si dan una sola para todo, repreguntá.

🎯 **P3. "¿Quién reserva: una persona por todo el grupo, o cada jugador confirma su lugar?"**
📘 Define si hay un titular responsable del pago o si el cobro se divide.
🟢 Un responsable nombrado: "reserva el titular y él responde por el turno".

🎯 **P4. "¿Hasta cuándo puede cancelarse una reserva, y qué pasa con lo que ya se pagó?"**
📘 Es la política de cancelación: la regla de negocio que más plata mueve.
🟢 Plazo y consecuencia: "hasta 24 hs antes administración devuelve; después el socio pierde la seña".

🎯 **P5. "Cuando la cancha ya está ocupada, ¿qué querrían que pase?"**
📘 Abierta a propósito, para que propongan ellos la cola de espera en vez de sugerírsela vos.
🟢 Lista de espera con aviso automático. Repreguntá **quién** avisa (el sistema) y **en cuánto tiempo** vence el lugar ofrecido.

**Repreguntas de reserva (si sobra tiempo):** ¿hay horarios distintos entre semana y fin de semana? ¿hay un máximo de reservas activas por socio?

### Entrevistador 3 — Pagos (bloque 3: 4 min)

> **🗺️ Lo que tenés que sacar de este bloque — leer primero**
> La Junta ya decidió que el cobro pase por la app porque perdía un 5% con pagos no registrados: la plata es su tema sensible. Tenés que salir con **cómo se cobra un turno**: si es **seña o total** y de cuánto; con qué **medios de pago** (cada uno es una integración, y el efectivo rompe el registro automático); qué pasa cuando corresponde **devolver** (quién autoriza y en cuánto tiempo); y si el **precio** es único o cambia según socio/no socio y horario pico/valle, y quién lo fija. Si lográs eso, en la minuta los requerimientos de pago salen con dueño, monto y plazo.

🎯 **P1. "Al momento de reservar, ¿cobran una seña o el total del turno? ¿De cuánto estamos hablando?"**
📘 Define si el sistema maneja pago parcial con saldo pendiente, que es bastante más complejo.
🟢 Porcentaje o monto: "seña del 50%, el saldo por la app antes del turno". Si dicen "una seña" sin número, repreguntá.

🎯 **P2. "¿Qué medios de pago quieren habilitar?"**
📘 Cada medio es una integración distinta; el efectivo rompe el registro automático (y la Junta ya perdió un 5% por eso).
🟢 Una lista cerrada (Mercado Pago, tarjeta, transferencia). Si incluyen efectivo, repreguntá **quién lo registra** y en qué momento.

🎯 **P3. "Cuando una cancelación da derecho a devolución, ¿quién la autoriza y en cuánto tiempo devuelven el dinero?"**
📘 Toda devolución necesita responsable y plazo; si no, es una regla sin dueño.
🟢 Un rol y un plazo: "la autoriza administración, dentro de las 48 hs, al mismo medio de pago".

🎯 **P4. "¿El precio del turno es el mismo para todos, o varía según el socio o el horario?"**
📘 Destapa la lista de precios como entidad propia, con vigencias y responsable.
🟢 Diferencian socio / no socio y pico / valle. Repreguntá **quién fija y actualiza** esos precios.

### Entrevistador 4 — Lo social: amigos, campeonatos y promociones (bloque 4: 4 min)

> **🗺️ Lo que tenés que sacar de este bloque — leer primero**
> Es lo más vago del enunciado: la Junta tiene la idea, no el detalle. Por eso es donde más hay que repreguntar y donde más se nota la calidad de la repregunta. Tenés que convertir tres palabras en cosas concretas: **"red de amigos"** → qué puede hacer un socio con ella (invitar, ver turnos, armar equipo); **"campeonatos"** → quién los organiza, cómo se inscriben y, sobre todo, **quién carga resultados y tabla** (nadie la pregunta); **"promociones"** → un ejemplo concreto, quién la crea y hasta cuándo vale. Si te contestan con un verbo sin sujeto ("se carga", "se organiza"), ahí está el "se" que la profe nos marcó: preguntá quién.

🎯 **P1. "¿Qué quieren que un socio pueda hacer con su red de amigos dentro de la app?"**
📘 Abierta a propósito: "red de amigos" no significa nada todavía. Les toca a ellos llenarla.
🟢 Acciones concretas: invitar a un partido, ver turnos de un amigo, armar equipo. Si contestan "conectarse", pedí un ejemplo de uso.

🎯 **P2. "¿Quién organiza los campeonatos y cómo se inscribe la gente?"**
📘 Separa al organizador del participante: dos roles con permisos distintos.
🟢 Un responsable (el complejo, o un socio que puede crearlo) y si la inscripción es por equipo o individual.

🎯 **P3. "¿Quién carga los resultados de cada partido y actualiza la tabla de posiciones?"**
📘 Nadie la hace, y sin ella el campeonato no funciona. Define un rol operativo nuevo.
🟢 Un responsable. Si dicen "se carga", ahí está el "se" impersonal: repreguntá quién.

🎯 **P4. "¿Qué tipo de promociones imaginan, y quién las crea y les pone vigencia?"**
📘 Promoción es regla de negocio pura: necesita dueño y fechas.
🟢 Un ejemplo concreto más un rol: "2x1 en horario valle, lo define la gerencia comercial, dura un mes".

### Entrevistador 5 — Fidelización (bloque 5: 2 min, antes del cierre del Entrevistador 1)

> **🗺️ Lo que tenés que sacar de este bloque — leer primero**
> "Fidelización" es una palabra, no una regla. Tenés que salir con la **mecánica completa del premio**: **qué conducta** del socio se premia (jugar seguido, traer gente, antigüedad), **cómo acumula y cómo canjea** (puntos, descuentos, turnos gratis, con número), y si el beneficio **vence** y quién define esas reglas. Son dos minutos: tres preguntas cortas, respuestas con número y responsable, y le pasás la palabra al Entrevistador 1.

🎯 **P1. "¿Qué comportamiento del socio quieren premiar con el programa de fidelización?"**
📘 Define el hecho que dispara el beneficio, que es lo que el sistema tiene que detectar.
🟢 Una conducta concreta: jugar seguido, traer socios nuevos, antigüedad.

🎯 **P2. "¿Cómo acumula el socio el beneficio y cómo lo usa: puntos, descuentos, turnos gratis?"**
📘 Separa la acumulación del canje, que son dos momentos distintos.
🟢 Una mecánica con número: "cada 10 turnos, uno gratis".

🎯 **P3. "¿Los beneficios tienen vencimiento, y quién define esas reglas?"**
📘 Sin vencimiento el pasivo crece para siempre; sin dueño la regla no se puede cambiar.
🟢 Un plazo y un rol: "vencen a los 6 meses, lo define la gerencia comercial".

**Al terminar, el Entrevistador 5 le pasa la palabra al Entrevistador 1 para el cierre.**

---

## PARTE 4 — Lado JUNTA DIRECTIVA

**Regla de la rúbrica:** las respuestas deben ser **dadas por el rol correspondiente, completas (quién, cuánto, cuándo) y con vocabulario del negocio**. Si te preguntan algo de otro rol, lo derivás en voz alta: "eso lo maneja mejor nuestro Director Financiero". Eso suma en "asignación e identificación de roles".

**Al presentarse, cada uno dice su rol en voz alta**, o la profe no puede evaluarlo.

> **Importante:** la Junta no es un bloque uniforme. Cada rol tiene su tema, sus números y lo que defiende. Las respuestas esperadas de la Parte 3 son el machete de cada rol; acá va el personaje completo.

### Rol A — Presidente de la Junta
**Guiño:** respondés al **Entrevistador 1** (alcance, integración, cierre). Acompañás en todo lo demás y derivás a quien corresponde.

**Qué te importa:** la visión. Vida Sana crece: hoy un gimnasio, mañana un complejo, pasado más sedes. Querés **un solo sistema**, un solo registro de socios, y ver todo **desde el celular** porque viajás.

**Qué defendés:**
- Las canchas se integran a la app del gimnasio: mismo socio, misma cuenta, mismo QR de acceso.
- Pueden reservar socios y no socios, pero el socio tiene precio preferencial (es el gancho para que se asocien).
- El buffet está concesionado: no entra.
- Etapas: primero reservas y pagos (eso tiene que estar el día uno), después campeonatos y fidelización.
- Herramientas: "miramos plataformas como ATC y CanchaManager; nos gusta lo que hacen, pero queremos algo integrado con el gimnasio, no dos apps".

**Tus números:** apertura prevista en ~3 meses; una sucursal hoy, segunda sede en evaluación; necesitás ver ocupación de canchas y recaudación mensual desde el celular.

### Rol B — Director de Operaciones
**Guiño:** respondés al **Entrevistador 2** (reservas).

**Qué te importa:** que la cancha nunca quede vacía y nunca se superponga. Tu enemigo es el **no-show** y el **doble booking**.

**Qué defendés:**
- Reserva con hasta **7 días** de anticipación; el plazo lo define administración y tiene que poder cambiarse.
- Turnos: **90 min fútbol 5, 60 min paddle, 45 min golfito**. Grilla de 8 a 24 hs; fines de semana desde las 9.
- **Reserva el titular** y responde por el turno completo.
- Cancelación sin costo hasta **24 hs antes**; después el socio pierde la seña. El socio cancela desde la app.
- Si la cancha está ocupada, el socio entra en **lista de espera**; si se libera, **el sistema avisa** al primero de la cola y tiene **2 horas** para confirmar.
- Máximo **2 reservas activas** por socio, para que nadie acapare.

**Apoyo:** "en el gimnasio ya tenemos lista de espera y aviso de ausencia con un día; queremos lo mismo en las canchas, pero automático".

### Rol C — Director Financiero
**Guiño:** respondés al **Entrevistador 3** (pagos).

**Qué te importa:** que **todo pago quede registrado**. En la reunión anterior reconocimos una pérdida del **5%** por cobros no registrados y decidimos que el cobro pase por la app. Esto se extiende a las canchas.

**Qué defendés:**
- **Seña del 50%** al reservar; el saldo también por la app, antes del turno.
- Medios: **Mercado Pago, tarjeta y transferencia**. Nada de efectivo en la cancha; si alguien paga en efectivo, lo registra administración en el mostrador.
- Devoluciones: las **autoriza administración**, dentro de las **48 hs**, al mismo medio de pago.
- Precios diferenciados: **socio / no socio** y **pico / valle**. La lista de precios la **fija la Junta** y la actualiza administración, con fecha de vigencia.
- Necesitás reporte de recaudación por cancha y por deporte, y lista de deudores.

### Rol D — Director Comercial
**Guiño:** respondés al **Entrevistador 4** (amigos, campeonatos, promociones) y al **Entrevistador 5** (fidelización).

**Qué te importa:** llenar los **horarios valle** y que el socio vuelva. Lo social es tu herramienta.

**Qué defendés:**
- **Red de amigos:** el socio puede invitar amigos a un partido, ver qué turnos tienen sus amigos y completar equipo. Un invitado no socio necesita cuenta en la app para que lo sumen.
- **Campeonatos:** los **organiza el complejo**; inscripción **por equipo** desde la app con un capitán responsable del pago; **el administrador del complejo carga los resultados** y el sistema arma la tabla.
- **Promociones:** por ejemplo **2x1 en horario valle** y descuento por cuota social al día; las **crea la gerencia comercial** con fecha de inicio y fin.
- **Fidelización:** premiar **frecuencia**: cada **10 turnos, uno gratis**; los beneficios **vencen a los 6 meses**; las reglas las define la gerencia comercial.

---

## PARTE 5 — Para todos: protocolo del día

**Antes de entrar:** imprimir este documento. La profe permite llevar la hoja con las preguntas.

**Si nos toca ENTREVISTADOR:**
1. Entrevistador 1 abre (presentación, roles en voz alta, objetivo, duración, frase de "venimos preparados").
2. Un integrante toma notas para la minuta durante toda la entrevista (puede ser el Entrevistador 5, que habla al final). Anotar **quién dijo qué, con números**.
3. Cada uno hace su bloque. El Entrevistador 1 marca el tiempo y corta si un bloque se pasa.
4. Ante una respuesta sin número o sin responsable, el que preguntó repregunta: "¿cuánto?", "¿quién?".
5. Escuchar: no completar frases, no saltar a conclusiones, no criticar la respuesta.
6. Entrevistador 1 cierra con resumen, "¿quedó algo afuera?" y promesa de minuta.

**Si nos toca JUNTA:**
1. Cada uno se presenta con su rol en voz alta.
2. Respondemos con el número y el responsable ya incluidos, sin esperar la repregunta.
3. Si la pregunta es de otro rol, se deriva en voz alta.
4. Si preguntan algo que no está en la ficha, inventamos **coherente con el personaje** (ej. Financiero: siempre que quede registrado; Operaciones: siempre que la cancha no quede vacía).
5. Si hablan del buffet: "está concesionado, no entra".
6. Si preguntan "¿cómo hacen hoy las reservas?": "las canchas todavía no operan; les contamos cómo queremos que funcione, basándonos en cómo ya hacemos en el gimnasio".

**Para la minuta del 08/10 (ambas partes la presentan):** registrar fecha, participantes y roles, lo tratado por bloque, decisiones con número y responsable, y lo que quedó pendiente. Sin "se" impersonal.

---

## ✅ Checklist del documento

- [x] Glosario con los términos que usan las preguntas y las fichas
- [x] Mercado relevado con nombres reales (criterio "herramientas de software")
- [x] Contexto del negocio: lo que existe, lo acordado antes, lo nuevo
- [x] 5 bloques de entrevista, cada uno con panorama "🗺️ Lo que tenés que sacar" + pregunta / por qué / respuesta esperada
- [x] Reparto Entrevistador 1 a 5 con apertura y cierre asignados
- [x] 4 fichas de Junta con guiño cruzado al entrevistador que las interpela
- [x] Protocolo del día para ambos lados
- [x] Regla quién / cuánto / cuándo y prohibición del "se" impersonal
