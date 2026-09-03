# Ingeniería de Requisitos — Trabajo practico / Museo de Bellas Artes

> Conversión fiel a Markdown de TP_MuseoBellasArtes.pdf (2 páginas).

## Notas de conversión

- El original tiene 2 páginas con el mismo encabezado institucional repetido: logo **UTN.BA** (Universidad Tecnológica Nacional — Facultad Regional Buenos Aires) y las líneas en itálica "Ingeniería de Requisitos / Trabajo practico / Museo de Bellas Artes". Se transcribe una sola vez como título del archivo.
- El texto se presenta continuo, sin marcas de página: el corte entre la página 1 y la 2 parte una oración por la mitad ("…el Director disponen de / equipos PC con impresoras a color…").
- En la página 2, el subtítulo del logo ("Universidad Tecnológica Nacional / Facultad Regional Buenos Aires") aparece con las dos líneas superpuestas e ilegibles en el original: es un defecto de render del PDF, no contenido distinto.
- El PDF no contiene anotaciones URI: no hay hipervínculos que extraer.
- Las viñetas del original usan el carácter `o` en el primer nivel y `•` en el segundo; se transcriben como listas Markdown.
- Errores e irregularidades del original, transcriptos tal cual: "Trabajo practico" (sin tilde), "una obra pueda estar expuesta" (concordancia), "ó" acentuada en "por tema ó por tamaño", doble espacio en "ordenada por  conveniencia".

---

Dado el siguiente enunciado:

El nuevo Director del Museo de Bellas Artes ha solicitado a su Departamento de Informática que desarrolle un software para automatizar la gestión de sus obras, ya que necesita mantener el catálogo de obras de arte, donde la obra de arte característica es el cuadro.

Pero, además, el museo dispone de esculturas y de otros objetos. Cualquiera de estos tres tipos de elementos tiene un autor y pertenece a un periodo. Cada obra es valorada económicamente y se almacena su fecha de creación, su fecha de entrada en el museo y su fecha de última restauración.

Los cuadros y esculturas tienen un estilo. De los cuadros hay que recoger la técnica (óleo, acuarela, carboncillo…), y de las esculturas el material (bronce, piedra…). Para todas se guardan entre 1 y 5 fotografías, con la fecha de toma de las mismas.

La introducción de datos la realiza el usuario encargado del catálogo, pero cada obra y los datos que la describen se reciben de los proveedores de obras de arte. Las obras se ubican en salas por estilo, pero para muestras especiales (por ejemplo aniversario de un autor, o muestra de una época), pueden ser reubicadas, debiendo al final de la muestra, ser devueltas a la ubicación original.

Para las reubicaciones, el sistema deberá proveer de un algoritmo que permita a los empleados de logística del museo, realizar la menor cantidad de movimientos posibles, y con el menor recorrido entre salas, para evitar roturas o daños en las obras de arte (especialmente las esculturas).

Aclaración: las salas son contiguas, tienen como nombre el de un padrino del museo que las identifica (el padrino del museo es toda aquella persona que donó o dona fondos para su mantenimiento).

Cada ubicación en una sala, se identifica en forma numérica secuencial, por sala, se sabe si es pedestal para escultura, vitrina o espacio de colgado, y la superficie en metros cuadrados que tiene.

Las obras de arte se identifican con un código QR, que se genera en base a la nomenclatura nemotécnica históricamente utilizada por el museo (no disponemos de dicho formato de nomenclador). Este código puede ser leído por un lector láser específico, para evitar errores de tipeo en las consultas por código de catálogo.

- Se debe gestionar la restauración de obras de arte. El Departamento de Restauración se encarga de decidir qué obras de arte deben ser restauradas. Por tanto, una obra pueda estar expuesta o puede estar en restauración. En este último caso hay que recoger el tipo de restauración y el plazo estimado. Las obras de arte se restauran automáticamente cada cinco años, por lo que se requiere un alerta mensual que indique qué obras tienen que pasar a restauración en el siguiente mes. De realizar este trabajo en las obras se encarga el restaurador jefe.
- Los visitantes al museo pueden consultar los listados de obras por salas en un monitor suspendido en el vestíbulo principal del museo. Estas listas van desplazándose automáticamente. En la mitad de la pantalla se muestra la lista de obras expuestas (que se desplaza alfabéticamente), y en la otra mitad videos del proceso de restauración a obras.
- Cuando una ubicación en una sala queda libre por restauración, el director del Museo quiere poder decidir si ubica una obra del depósito o bien un cartel haciendo referencia a la restauración en curso. Para esto quiere saber si existen obras en depósito adecuadas para dicha ubicación, y una lista de las mismas ordenada por  conveniencia en base a dos criterios que puede seleccionar excluyentemente: por tema ó por tamaño.
  Si no existen obras en depósito adecuadas a ninguno de dichos criterios, entonces se colocará el cartel con referencia al motivo de la ausencia de la obra de su lugar.
- Se deben ofrecer servicios de consulta a diferentes tipos de usuarios:
  - El restaurador jefe debe poder consultar todas las obras de arte ordenadas por antigüedad y por fecha de última restauración.
  - El director del museo debe poder consultar la valoración de todas las obras del museo (la suma total).

El sistema debe disponer de controles de seguridad, por lo que es requisito indispensable que todos los usuarios se autentifiquen antes de poder utilizar el software.

El Departamento de Informática consta de un jefe de departamento, un analista y un especialista de soporte técnico de PCs.

Tanto el Departamento de Restauración como el encargado del catálogo y el Director disponen de equipos PC con impresoras a color, todo ello conectado a una red LAN.

El Museo no ha detectado fallas en el control de las restauraciones, pero gracias a la buena administración del Director anterior, se dispone de los fondos para el desarrollo antes detallado, incluyendo la contratación de personal de desarrollo que haga falta, por lo que las nuevas autoridades entienden que es el momento oportuno para llevar a cabo el proyecto.

1) Detallen **5** requerimientos funcionales, que no incluyan ABM de datos.
2) Detallen **3** requerimientos no funcionales que surgen a partir del enunciado.
3) Realicen el **Diagrama de Casos de Uso** del negocio descripto para el Museo

---

**FIN DEL ARCHIVO FUENTE — Ingeniería de Requisitos / Trabajo practico / Museo de Bellas Artes**
