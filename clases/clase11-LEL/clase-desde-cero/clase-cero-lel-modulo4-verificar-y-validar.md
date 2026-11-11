# Clase desde cero — LEL — Módulo 4: Verificar y validar: encontrar los errores de un LEL

**Serie:** Clase desde cero — LEL (módulo 4 de 4) · **Materia:** Ingeniería de Requisitos · **Unidad:** clase11
**Versión provisoria (4/11):** se actualiza con lo que la cátedra corrija en la clase del 5/11, que es de verificación de LEL y escenarios.

---

## Sobre este documento

**Qué cubre:** la diferencia entre verificar y validar, la lista DEO (cómo se anota lo que está mal), los cuatro grupos de defectos con la señal que delata a cada uno, una lista de control de seis puntos, lo justo de Obsidian para el parcial y el TP, y dos talleres resueltos: el borrador de IA de la veterinaria, símbolo por símbolo, y el LEL de Vida Sana del módulo 3.

**Qué NO cubre:** nada nuevo sobre cómo se escribe un símbolo (módulos 1 y 2) ni sobre las etapas (módulo 3). Este módulo es el que más se parece a lo que te van a tomar.

## De dónde venís

De los tres módulos anteriores: el símbolo y sus tipos, los dos principios, sinónimos y homónimos, las reglas de forma y contenido para describir, y un LEL de Vida Sana sin revisar.

---

## 1. 🔴 Verificar y validar: dos preguntas distintas

Tenés un LEL terminado. Hay dos cosas que pueden estar mal, y se controlan por separado:

| | **Verificar** | **Validar** |
|---|---|---|
| **La pregunta** | ¿Está *bien construido*? | ¿Es *el vocabulario que el negocio usa de verdad*? |
| **Quién lo hace** | Los analistas, entre ellos | Los clientes y usuarios, en su lugar de trabajo |
| **Contra qué** | El modelo del LEL, las plantillas de cada tipo, las reglas de forma y contenido | La realidad del negocio: lo que la gente sabe y dice |
| **Cómo** | Una **inspección**: revisión sistemática con una lista de control, en tres pasos (planear, preparar, reunirse), con tres roles (inspector, moderador, escriba) | Entrevistas estructuradas o reuniones: se le lee cada símbolo al usuario y él confirma, corrige o agrega |
| **Qué busca** | Defectos de construcción: tipo mal asignado, referencia sin marcar, sinónimo oculto, oración sin símbolos | Nociones e impactos equivocados, símbolos que faltan, sinónimos y homónimos que nadie vio |
| **Resultado** | Una lista de DEOs (las discrepancias, errores y omisiones encontradas; se explica en la sección 2) que vuelve a **Describir** | Una lista de DEOs que vuelve a **Recolectar** y a **Describir** |

Dos detalles de la validación: no se controla todo el LEL con cada usuario, sino los símbolos que le competen (al cajero, los de caja). Y es fácil, porque el LEL está escrito en el idioma del usuario: no hay que explicarle ninguna notación.

Un ejemplo de cada una con la tienda del módulo 1:
- **Verificar** encuentra que `Cancelar(1)` está clasificado como objeto. No hace falta hablar con nadie de la tienda: con la plantilla alcanza para ver que es una acción, o sea un verbo.
- **Validar** encuentra que en la tienda nadie dice "legajo del cliente", dicen "carpeta del cliente". Eso no lo podés ver desde tu escritorio: te lo dice el usuario.

> 🎓 **Para el parcial, si te preguntan: ¿qué diferencia hay entre verificar y validar el LEL?**
> Verificar controla que el LEL esté bien construido: lo hacen los analistas mediante inspección, contra el modelo, las heurísticas y los formularios de inspección (las planillas con que se registra la revisión). Validar controla que sea el vocabulario real del negocio: lo hacen clientes y usuarios en entrevistas o reuniones, leyendo cada símbolo. Ambas producen listas de DEOs que realimentan las etapas anteriores.

## 2. 🔴 La lista DEO

Cuando verificás o validás, lo que encontrás se anota en una **lista DEO**. Cada letra es una clase de problema:

| Letra | Nombre | Qué es | Ejemplo |
|---|---|---|---|
| **D** | **Discrepancia** (o **defecto**) | Lo escrito contradice lo que dice el negocio o lo que confirma el usuario; o dos partes del LEL se contradicen entre sí | El LEL dice que la clínica da de alta al paciente; el negocio dice que lo hace el veterinario |
| **E** | **Error** | Una entrada no cumple las reglas de forma del símbolo: tipo, plantilla, infinitivo, singular, noción e impacto en su lugar | Un objeto clasificado como sujeto; un verbo que no está en infinitivo |
| **O** | **Omisión** | Falta un símbolo, una noción, un impacto o una referencia necesaria | "Veterinario" aparece en todas las descripciones y no tiene entrada |

> ⚠️ **Nota de cátedra sobre la D.** En la materia la D se lee de las dos formas, "discrepancia" y "defecto", y la distinción entre D y E no es tajante. El criterio que usa la cátedra: un **tipo mal asignado** (objeto puesto como sujeto) es un **error**; una **referencia sin marcar** (falta de circularidad) es un **defecto**; **dos definiciones que se contradicen** dentro del LEL, o una que contradice al negocio, es una **discrepancia**. Ojo con esto: la circularidad también es una "regla de construcción", pero una referencia sin marcar **no va como E, va como D (defecto)**. En el parcial, si dudás entre D y E, clasificalo y **explicá en una línea el criterio**. Lo que se evalúa es que detectes el problema y lo corrijas, no la letra.

**Cómo se redacta cada entrada de la lista.** Tres cosas, siempre: el símbolo, qué está mal (concreto, citando), y la corrección propuesta.

> `Consulta` · **E** (clasificación) · Está como sujeto, pero no realiza ninguna acción: le hacen cosas (se crea, se registra). Es un objeto. · **Corrección:** mover a Objetos y reescribir la noción con la plantilla de objeto.

Eso es lo que la cátedra espera ver. Una lista de palabras sueltas ("está mal Consulta") no alcanza.

> 🎓 **Para el parcial, si te preguntan: ¿qué es una lista DEO?**
> Es la lista de discrepancias (o defectos), errores y omisiones detectadas al verificar o validar el LEL. Una discrepancia contradice al negocio o al propio LEL; un error incumple las reglas de construcción; una omisión es un símbolo, noción, impacto o referencia que falta. Cada entrada indica el símbolo, el problema y la corrección, y la lista realimenta las etapas de Recolectar y Describir.

## 3. 🔴 Los cuatro grupos de defectos y su señal

Para verificar en serio hace falta saber **qué buscar** y **cómo se nota**. Los defectos de un LEL se agrupan en cuatro familias, y cada una deja una señal.

| Grupo | Qué está mal | Casos | **La señal que lo delata** |
|---|---|---|---|
| **Descripción** | El símbolo está mal descripto, incompleto, o descripto como si fuera de otro tipo | La noción dice cómo actúa (eso es impacto); hay oraciones de otro símbolo metidas acá; falta noción o impacto; un sujeto cuyo impacto no lista acciones | Noción e impacto parecen intercambiados; una entrada muy corta para un símbolo que todos mencionan; el estilo no coincide con la plantilla del tipo |
| **Clasificación** | Tipo mal asignado | Objeto como sujeto; verbo sin infinitivo que se confunde con objeto; un estado pegado al sujeto en vez de aparte | El nombre no está en infinitivo; el símbolo "no hace nada" pero está en sujetos; la descripción no entra en la plantilla del tipo |
| **Identificación** | Faltan símbolos, sobran, o hay sinónimos mal resueltos | Símbolo omitido; dos entradas para lo mismo (sinónimo no unificado); sinónimos parciales unidos; un símbolo del lenguaje común metido como si fuera del negocio | Una palabra se repite en varias descripciones sin tener entrada; dos entradas con descripciones casi iguales; un símbolo con muy pocas referencias y al que casi nadie menciona |
| **Referencia** | Las referencias a otros símbolos faltan o están mal usadas | Palabra que es símbolo escrita sin marcar; símbolo usado con su significado común y no el del negocio | Un símbolo que no menciona a ningún otro; un símbolo que nadie menciona; una oración sin corchetes |

La señal que más usa la cátedra, y que Obsidian muestra en un dibujo, es la última: **un símbolo que no menciona a otros, o que ningún otro menciona, hay que revisarlo**. Es señal de alerta, no condena: a veces solo faltó marcar un enlace.

> 🎓 **Para el parcial, si te preguntan: ¿qué tipos de defecto se verifican en un LEL?**
> De descripción (símbolos mal descriptos, incompletos o incompatibles con su tipo), de clasificación (tipo mal asignado, por ejemplo un verbo que no está en infinitivo), de identificación (símbolos omitidos, sinónimos incorrectos o símbolos incluidos de más) y de referencia (faltan referencias a otros símbolos o se usan mal). La señal de alerta típica es un símbolo que no menciona a otros o que ningún otro menciona.

🕳️ **Madriguera — los formularios de inspección.** El trabajo original sobre inspección del LEL define catorce formularios para la reunión de inspección (carátula, resumen cuantitativo, comprobación sintáctica…). La cátedra se queda con la idea de inspección y la lista de control de abajo. *Volvé al camino.*

## 4. 🔴 La lista de control de seis puntos

Es lo que pasás por cada símbolo cuando verificás. Es la misma lista con la que la cátedra revisa.

1. **Sintaxis:** formato uniforme en todas las entradas; nombres en singular; verbos en infinitivo.
2. **Componentes:** todo símbolo tiene noción e impacto; no hay sinónimos ocultos (dos entradas que describen lo mismo).
3. **Clasificación:** el tipo es correcto y la descripción sigue la plantilla de ese tipo.
4. **Uso de símbolos:** toda referencia está marcada, con el nombre completo, y con el significado del negocio.
5. **Principios:** circularidad (toda oración menciona otro símbolo; todo símbolo es mencionado) y vocabulario mínimo (nada de jerga ajena).
6. **Jerarquías:** si hay género y subtipos, las descripciones son coherentes entre sí y la noción del subtipo nombra al género.

Cómo se usa: símbolo por símbolo, punto por punto. Lo que falla va a la lista DEO con su letra, su grupo y su corrección.

## 5. 🟡 Obsidian, lo justo para el parcial y el TP

Obsidian es un programa de notas. No inventó el LEL: es la herramienta que lo hace visible, navegable y revisable. Lo que necesitás saber:

| Cosa del LEL | Cómo se ve en Obsidian |
|---|---|
| El LEL entero | Una **bóveda**: una carpeta en tu disco. Se crea con "Crear bóveda local" y se le da un nombre y una ubicación. Para importar un LEL que te dieron, copiás su carpeta adentro de la carpeta de la bóveda y aparece solo |
| Un símbolo | Una **nota**: un archivo de texto `.md` con el nombre del símbolo |
| El tipo | Una **carpeta** por tipo (Sujetos, Objetos, Verbos, Estados) y, en la cabecera de la nota, una **propiedad** `tipo` y una etiqueta `#lel/sujeto` |
| Los sinónimos | La propiedad **aliases** (nombres alternativos) en la cabecera. Cualquiera de los nombres abre la misma nota. ⚠️ El nombre de la propiedad tiene que ser exactamente `aliases`: si la llamás `sinonimos` o `sinónimo`, como en el borrador de la veterinaria, queda como texto informativo y no enlaza nada |
| Noción e impacto | Dos títulos (`## Noción`, `## Impacto`) con viñetas debajo |
| Una referencia | Un **enlace** `[[Producto]]`. Para plural o conjugación, `[[Producto\|productos]]`: se lee "productos", apunta a Producto |
| Navegar | Con Ctrl apretado, pasás el mouse por un enlace y aparece una vista previa de esa nota; hacés clic y vas |
| Circularidad | El panel de **enlaces entrantes** (quién menciona a esta nota) y **salientes** (a quién menciona). Y el panel **"menciones no enlazadas"**: palabras que son nombres de símbolos pero están escritas sin corchetes. Es el detector automático del defecto de referencia |
| La red completa | La **vista de grafo**: cada nota es un punto, cada enlace una línea. Los puntos más grandes son los más mencionados |
| Colores por tipo | En el grafo, **grupos**: un filtro `tag:#lel/sujeto` con un color, otro para objeto, etc. Así ves de un vistazo si hay muchos sujetos, pocos verbos |
| La señal de alerta | En el grafo, el interruptor **huérfanos**: activado, las notas sin ningún enlace se ven, sueltas; desactivado, se ocultan. Dejalo activado para verificar. Ojo: un punto **gris** es una nota sin tipo asignado; un punto **suelto** es una nota sin conexiones. Son dos problemas distintos |

Para el parcial no te van a pedir operar Obsidian. Te van a pedir que sepas **qué muestra**: que el grafo hace visible la circularidad, que el nodo suelto es la señal de alerta, que los alias resuelven los sinónimos.

## 6. 🔴 Taller resuelto 1: el borrador de IA de la veterinaria

**El caso.** Una clínica veterinaria, descripta en un párrafo:

> Una clínica veterinaria atiende a sus pacientes. Cada paciente tiene un dueño, también llamado propietario. La primera vez que llega, el veterinario debe dar de alta al paciente junto con su dueño. Luego, el propietario puede solicitar turno y se le asigna un horario en la agenda del veterinario. Cuando el paciente concurre a la consulta, el turno pasa a ser un turno atendido. Durante la consulta, el veterinario documenta el motivo de consulta y el diagnóstico en el historial clínico. Si corresponde, prescribe un tratamiento. El historial clínico está disponible para el veterinario y el dueño.

A partir de ese texto, una IA generó un LEL de doce símbolos: tres sujetos (Consulta, Dueño, Propietario), seis objetos (Clínica, Historial clínico, Motivo de consulta, Paciente, Tratamiento, Turno), dos verbos (Dar De Alta Paciente, Solicitando Turno) y un estado (Turno Atendido). Las definiciones *suenan* bien. La consigna: revisarlo y armar la lista DEO.

**Método.** Primero, leer el texto del negocio y anotar el vocabulario que debería estar (la nube de palabras: clínica, paciente, dueño/propietario, veterinario, dar de alta, turno, agenda, consulta, turno atendido, motivo de consulta, diagnóstico, historial clínico, tratamiento, prescribir). Después, pasar la lista de control por cada símbolo.

### 6.1 La lista DEO del borrador

Los primeros siete son los que salen a simple vista; los demás, los que aparecen al leer con la lista de control.

| # | Símbolo | Qué está mal | Letra | Grupo | Corrección |
|---|---|---|---|---|---|
| 1 | `Dueño` y `Propietario` | Son dos entradas, pero el texto dice "dueño, también llamado propietario": misma persona, mismas acciones. Además, las dos nociones tienen acciones adentro ("Solicita turnos y recibe información…", "Se registra en el sistema…"), que son impacto | **E** | Identificación (sinónimo no unificado) + Descripción | Una sola entrada `Dueño / Propietario`; en Obsidian, `Propietario` como alias; unificar, y pasar las acciones de la noción al impacto |
| 2 | `Veterinario` | No existe como símbolo, y "el veterinario" aparece en nueve de las doce descripciones, siempre sin marcar. Es el sujeto principal del negocio | **O** | Identificación (símbolo omitido) | Crear el sujeto `Veterinario` y marcar todas las menciones |
| 3 | `Consulta` | Está en Sujetos, pero no hace nada: "es creada", "queda incorporada". Le hacen cosas. Además la noción dice "Registro de la atención…": el registro es el historial, no la consulta; y menciona "motivo, diagnóstico" sin marcar | **E** | Clasificación + Descripción | Mover a Objetos y reescribir la noción: la consulta es la atención, no su registro; marcar motivo y diagnóstico |
| 4 | `Prescribir tratamiento` | El texto dice "prescribe un tratamiento" y no hay verbo para esa acción | **O** | Identificación (símbolo omitido) | Crear el verbo `Prescribir tratamiento` |
| 5 | `Diagnóstico` | El texto lo nombra como lo que el veterinario documenta; no tiene entrada, y `Consulta` lo menciona sin marcar | **O** | Identificación (símbolo omitido) | Crear el objeto `Diagnóstico` **y enlazarlo** desde Consulta e Historial clínico. Si lo creás y no lo enlazás, queda suelto: señal de alerta nueva |
| 6 | `Solicitando Turno` | El verbo está en gerundio | **E** | Clasificación / sintaxis | `Solicitar Turno` |
| 7 | `Agenda` | Se menciona tres veces sin ser símbolo: "agenda de un veterinario" (`Turno`), "agenda de la clínica" (`Solicitando Turno`) y "agendas de turnos" (`Clínica`). Caso gris: puede ser la agenda de cualquiera o el objeto donde se asignan los turnos | **O** (posible) | Identificación | **Consultar al usuario.** Si es del negocio, crear el objeto `Agenda`. Si se incluye bien definido y después no hacía falta, no pasa nada |
| 7b | `Solicitando Turno` | Dice que la agenda es "de la clínica" y que "la clínica verifica disponibilidad y asigna un veterinario y horario". El texto dice que el horario se asigna "en la agenda del veterinario", y no dice que alguien asigne un veterinario | **D** | Descripción (contradice al negocio) | "Se asigna un horario en la agenda del [[Veterinario]]"; sacar la asignación de veterinario |
| 8 | `Paciente` | La noción dice lo que le pasa ("es dado de alta", "acumula consultas") y el impacto dice lo que es ("animal registrado en la clínica…"). Están **al revés** | **E** | Descripción (mal descripto) | Intercambiar: la noción es "Animal registrado en la clínica bajo la responsabilidad de un dueño…"; el impacto, las acciones |
| 9 | `Dar De Alta Paciente` | El impacto dice "La clínica registra al paciente". El texto dice que lo hace **el veterinario** | **D** | Descripción (contradice al negocio) | "El [[Veterinario]] registra al [[Paciente]] y lo asocia al [[Dueño]]" |
| 10 | `Dar De Alta Paciente` | "El paciente queda habilitado para solicitar turnos". El texto dice que el turno lo solicita el **propietario**, no el paciente | **D** | Descripción | "El [[Dueño]] queda habilitado para [[Solicitar Turno]]" |
| 11 | `Turno` | La noción inventa cuatro estados: "pendiente, confirmado, cancelado, atendido". El texto solo habla de turno atendido | **D** | Descripción (información que el negocio no dio) | Dejar solo lo que el texto respalda; lo demás, a consultar al usuario |
| 12 | `Turno`, `Dueño`, `Clínica`, `Turno Atendido`, `Solicitando Turno` | Hablan de cancelar, reprogramar, confirmar, "notificar al dueño ante cambios", "turno en estado pendiente" y "el dueño recibe confirmación". Nada de eso está en el texto | **D** | Descripción | Sacar, o anotar como duda para validar. Es el riesgo típico de un borrador de IA: completa con lo que *suele* pasar en una clínica, no con lo que dijo el cliente |
| 12b | `Propietario`, `Dar De Alta Paciente` | Hablan de "el sistema": "se registra en el sistema", "incorporar al sistema de la clínica". No hay ningún sistema de software en el texto: el LEL describe el negocio **actual**, con sus papeles. Y `Dar De Alta Paciente` lista datos ("nombre, especie, raza, fecha de nacimiento") que nadie dio | **D** | Descripción / vocabulario mínimo | Sacar "sistema"; los datos del paciente, a consultar |
| 13 | `Clínica` | Está como objeto, pero sus impactos son acciones que realiza: "gestiona la agenda", "almacena los historiales", "notifica". Una organización que actúa es un sujeto. El texto arranca con "una clínica veterinaria **atiende** a sus pacientes": argumento para sujeto | **E** (posible) | Clasificación (o descripción incompatible con el tipo) | Decidir: si la clínica *actúa* en el negocio, es sujeto; si solo es el lugar, es objeto y los impactos se reescriben como acciones que se le aplican |
| 14 | `Motivo de consulta` | La noción tiene "Lo informa el dueño": es una acción, va en el impacto, y además el texto no dice quién lo informa | **E** | Descripción | Noción: "Es la razón por la que el [[Paciente]] va a la [[Consulta]]". Impacto: "El [[Veterinario]] lo documenta en el [[Historial clínico]]" |
| 15 | `Historial clínico` | "Se genera automáticamente", "se archiva en el fichero del establecimiento", "es la fuente de verdad": tres cosas que el texto no dice, con palabras ajenas al negocio. Y no nombra el diagnóstico, que el texto sí pone en el historial | **D** | Descripción / vocabulario mínimo | Dejar lo que el texto respalda: el veterinario documenta en él el motivo de consulta y el diagnóstico; registra tratamientos; lo ven el veterinario y el dueño. Cuándo se crea: consultar |
| 16 | `Tratamiento` | "Puede incluir medicamentos, dosis y duración" y "sus instrucciones de seguimiento": detalle que el negocio no dio | **D** | Descripción | Sacar o consultar |
| 17 | Varios | "Diagnóstico", "agenda", "veterinario" aparecen sin corchetes en muchas descripciones | **D** (defecto) | Referencia | Se resuelve al crear los símbolos de 2, 5 y 7 y marcar |
| 18 | Varios | `Consulta` se escribe con mayúscula en los enlaces y el resto en minúscula; en `[[dueño\|Duenio]]` el texto visible del enlace está mal tipeado | **E** | Sintaxis (formato no uniforme) | Unificar el formato |

Veinte entradas de doce símbolos. Es normal: un borrador de IA tiene definiciones que suenan bien y están mal. Los tres vicios que se repiten: **inventa** lo que el negocio no dijo (7b, 11, 12, 12b, 15, 16), incluido un "sistema" que no existe; **confunde noción con impacto** (1, 8, 14); y **rompe el vocabulario mínimo** con palabras de afuera ("fuente de verdad", "fichero del establecimiento", "responsable legal").

### 6.2 Cuatro símbolos corregidos

Así quedan los que más cambian. Fijate que cada oración menciona otro símbolo, que casi no hay nada que el texto no diga (lo único inferido está marcado), y que la plantilla del tipo se respeta.

> ### Dueño / Propietario
> *Tipo: Sujeto · Alias: Propietario*
>
> **Noción**
> - Es la persona responsable de uno o más [[Paciente|pacientes]] de la [[Clínica]].
>
> **Impacto**
> - Realiza [[Solicitar Turno]] para su [[Paciente]].
> - Es registrado por el [[Veterinario]] al realizar [[Dar de Alta Paciente]].
> - Puede consultar el [[Historial clínico]] de su [[Paciente]].

> ### Veterinario
> *Tipo: Sujeto*
>
> **Noción**
> - Es el profesional de la [[Clínica]] que atiende a los [[Paciente|pacientes]].
>
> **Impacto**
> - Realiza [[Dar de Alta Paciente]] la primera vez que llega un [[Paciente]].
> - Atiende la [[Consulta]] de un [[Turno]].
> - Documenta el [[Motivo de consulta]] y el [[Diagnóstico]] en el [[Historial clínico]].
> - Realiza [[Prescribir tratamiento]] si corresponde.

> ### Consulta
> *Tipo: Objeto* (antes estaba como sujeto)
>
> **Noción**
> - Es la atención de un [[Paciente]] por el [[Veterinario]] en un [[Turno]].
> - Incluye el [[Motivo de consulta]], el [[Diagnóstico]] y, si corresponde, un [[Tratamiento]].
>
> **Impacto**
> - Al realizarse, el [[Turno]] pasa a [[Turno Atendido]].
> - El [[Veterinario]] la documenta en el [[Historial clínico]].

> ### Solicitar Turno
> *Tipo: Verbo* (antes "Solicitando Turno")
>
> **Noción**
> - Lo realiza el [[Dueño]] para que su [[Paciente]] sea atendido por el [[Veterinario]].
>
> **Impacto**
> - Se asigna un horario en la agenda del [[Veterinario]].
> - Genera un [[Turno]].
> - No puede realizarse si el [[Paciente]] no fue dado de alta mediante [[Dar de Alta Paciente]]. *(Inferido del "luego" del texto: confirmar con el usuario.)*

Dos detalles. En `Solicitar Turno`, "agenda" sigue sin corchetes porque es el caso gris del punto 7, pendiente de consultar; si el usuario confirma que es un objeto del negocio, se crea y se marca. Y la última oración está marcada como inferida: el texto dice "la primera vez… da de alta. Luego, el propietario puede solicitar turno", lo que sugiere el orden pero no lo afirma. Así se anota una inferencia en un LEL honesto: visible, para validarla.

## 7. 🔴 Taller resuelto 2: los nueve símbolos de Vida Sana

El LEL del módulo 3, pasado por la lista de control:

| # | Símbolo | Qué está mal | Letra | Grupo | Corrección |
|---|---|---|---|---|---|
| 1 | `Cupo`, `Carpeta de clases`, `Ficha que lleva el socio`, `Contratar plan`, `Recuperar clase` | Se mencionan con corchetes pero no tienen entrada | **O** | Identificación | Describirlos. En Obsidian aparecen como enlaces a notas que no existen |
| 2 | `Junta Directiva` | Es core (son los que piden el software) y no está descripta | **O** | Identificación | Crear el sujeto |
| 3 | `Clase` | La noción nombra cuatro actividades con profesor. Los sectores de cardio y musculación no tienen profesor y no entran en "clase": ¿son otro símbolo (`Sector`) o un tipo de clase? | **O** (posible) | Identificación / jerarquía | Consultar al usuario. Es el gris `Sector` del módulo 3 |
| 4 | `Lista de espera` | El impacto dice que el profesor llama al primero "cuando un socio realiza Avisar ausencia". El enunciado dice "si un socio inscripto se baja": ¿bajarse y avisar ausencia son lo mismo? | **D** (posible) | Descripción | Consultar. Si son distintos, falta un verbo |
| 5 | `Reformer` | En la lista de candidatos del módulo 3 quedó como core (define el cupo de pilates), y ninguno de los nueve lo describe ni lo menciona: `Clase` dice "cupo de ocho socios" sin decir de dónde sale | **O** | Identificación | Describir el objeto `Reformer` y mencionarlo desde `Clase` o desde `Cupo` |
| 6 | `Turno` | Aparece repetido en el enunciado ("3 turnos a la mañana", "ofrecerles asistir en otro turno") y ningún símbolo lo usa. Es el sinónimo parcial de `Clase` del módulo 2 | **O** (posible) | Identificación | Consultar si es un concepto propio; si lo es, describirlo |

**Un chequeo que pasó**, y que conviene hacer siempre: `Socio` dice "Es registrado por el [[Profesor]] en la [[Ficha del socio]]", una acción recibida, en pasiva. Verificá que `Profesor` tenga la acción espejo en su impacto. La tiene ("Registra al Socio en la Ficha del socio"). Si no la tuviera, sería una omisión en `Profesor`.

Nada de clasificación ni de forma: los nueve siguen la plantilla, están en singular e infinitivo, y toda oración menciona otro símbolo. Lo que falta es **completitud** (omisiones: siete símbolos por describir) y tres dudas para validar con el usuario. Eso es normal para una primera versión: la verificación encuentra lo que falta, y la validación resuelve los grises.

## 8. 🔴 El puente a los escenarios

El LEL no es un fin en sí mismo. Cuando está verificado y validado, se usa para construir los **escenarios**: descripciones de las situaciones del negocio (la serie siguiente). La conexión es directa:

- **Los impactos de los sujetos y de los verbos dan origen a los escenarios.** Cada acción que un sujeto realiza ("el socio se inscribe a una clase") es una situación candidata a escenario.
- **Los actores de un escenario son sujetos del LEL; los recursos son objetos del LEL.** Mismo vocabulario, sin inventar nombres nuevos.
- **Todo escenario y todo requisito se escriben con los símbolos del LEL**, marcados. Así se puede rastrear hacia atrás (¿de qué símbolo salió este requisito?) y hacia adelante (¿qué escenarios usan este símbolo?).

Ejemplo con el pasaporte, el caso que usa la cátedra: el sujeto `Solicitante` tiene el impacto "paga el trámite". De ahí sale el escenario actual *Cobrar el trámite* (el cajero informa el importe). De ese, el escenario futuro con el software (el cajero consulta el importe ingresando un número de control). Y de ese, los requisitos: RF "el cajero cobra el trámite"; RNF "el número de control es único para cada trámite". Cuatro pasos, un solo vocabulario.

> 🎓 **Para el parcial, si te preguntan: ¿qué relación hay entre el LEL y los escenarios?**
> El LEL es el punto de partida de los escenarios: los impactos de los símbolos sujeto y verbo originan los escenarios candidatos, y los actores y recursos de cada escenario son sujetos y objetos del LEL. Como escenarios y requisitos se escriben con los símbolos del LEL, el léxico es el ancla de la trazabilidad hacia atrás y hacia adelante.

## 9. Hilos cerrados

- "Producto" sin corchetes (módulo 1): falta de circularidad; en Obsidian, el panel de menciones no enlazadas lo detecta solo.
- "¿Cómo sé si mi LEL está bien?" (módulo 2): con la lista de control de seis puntos y la lista DEO.
- "El LEL de Vida Sana sin revisar" (módulo 3): revisado en la sección 7; le faltan siete símbolos y tiene tres dudas para el usuario.
- "¿Para qué sirve el LEL después?": sección 8. Sigue en la serie de Escenarios.

---

## Checkpoint del módulo 4

Respondé sin mirar el texto. Sin respuestas acá: van al complemento.

1. Explicá con un ejemplo de la tienda qué encuentra la verificación y qué encuentra la validación, y por qué una no puede reemplazar a la otra.
2. Clasificá como D, E u O, con el criterio de la cátedra: (a) `Cuota` está en Verbos; (b) el LEL dice que la cuota se paga al vendedor y el negocio dice que al cajero; (c) `Factura` no menciona ningún otro símbolo; (d) no existe el símbolo `Cajero` aunque tres entradas lo nombran.
3. Para cada grupo de defectos (descripción, clasificación, identificación, referencia) decí cuál es la señal que te hace sospecharlo.
4. ¿Qué diferencia hay, en el grafo de Obsidian, entre un nodo gris y un nodo suelto? ¿Qué problema indica cada uno?
5. En el borrador de la veterinaria, ¿por qué `Clínica` es un caso para pensar y no un error evidente? ¿Qué decidirías vos y por qué?
6. Escribí la entrada de la lista DEO para `Paciente` del borrador, con el formato completo: símbolo, problema, letra, grupo y corrección.
7. ¿Por qué un borrador hecho por IA tiende a tener discrepancias? Nombrá dos ejemplos del taller.
8. Dado el impacto "Realiza [[Avisar ausencia]]" del sujeto `Socio`, ¿qué escenario candidato sale de ahí y quiénes serían sus actores y recursos, en términos del LEL?

## Qué viene después

Terminaste la serie de LEL. Lo que sigue es la serie **Clase desde cero — Escenarios**, que arranca justo donde termina la sección 8: una situación del negocio, escrita con los símbolos del LEL, con sus partes, sus episodios y su validación.

Este módulo se actualiza con lo que la cátedra corrija en la clase del 5/11.

---

**FIN DEL MÓDULO 4 — Clase desde cero — LEL**
