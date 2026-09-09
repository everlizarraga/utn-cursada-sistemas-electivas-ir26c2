# Casos de Uso – Metro de Madrid

> Conversión fiel a Markdown de TP_CU_MetroMadrid.pdf (1 página).

---

## Encabezado de página

*(Izquierda)* Logo institucional **UTN.BA** — símbolo circular con el isotipo de la UTN y el texto "UTN.BA" ("UTN" en negro, ".BA" en rojo), con la bajada: UNIVERSIDAD TECNOLÓGICA NACIONAL / FACULTAD REGIONAL BUENOS AIRES.

*(Derecha, en itálica)*

*Ingeniería de Requisitos*
*Casos de Uso – Metro de Madrid*

---

## Expendedora de pasajes del Metro de Madrid

El Metro de Madrid comenzó a instalar en 2021 nuevas máquinas expendedoras de pasajes (o títulos de viaje).

### [Fotografía — pantalla táctil de la máquina expendedora]

```
┌──────────────────────────────────────────────────────────────────────┐
│  [botón rojo cortado]                        [botón rojo cortado]    │
│              ┌────────────────────────────────┐                      │
│              │   Comprar sólo Tarjeta Multi   │                      │
│              └────────────────────────────────┘                      │
│  ┌───────────────────────────────┬────────────────────────────────┐  │
│  │ (pin)  Comprar billetes por   │ (logo Metro) Comprar por tipo  │  │
│  │        destino                │              de billete        │  │
│  └───────────────────────────────┴────────────────────────────────┘  │
│  ┌────────────────────────────────────────────────────────────────┐  │
│  │   [1]         [10]          [avión]        [calendario]        │  │
│  │  Billete    Billete 10     Aeropuerto        ...urístico       │  │
│  │  1 Viaje      viajes                                           │  │
│  │             ▔▔▔▔▔▔▔▔▔                                          │  │
│  │  ┌──────────────────┬──────────────────┬───────────────────┐   │  │
│  │  │ METROBÚS      ⓘ │ BILLETE       ⓘ │ BILLETE TFM    ⓘ │   │  │
│  │  │ 10 Viajes        │ COMBINADO        │ 10 Viajes         │   │  │
│  │  │ [iconos]         │ 10 Viajes        │ [icono TFM]       │   │  │
│  │  │                  │ [iconos]         │                   │   │  │
│  │  ├──────────────────┼──────────────────┼───────────────────┤   │  │
│  │  │ ...LLETE      ⓘ │ BILLETE       ⓘ │ BILLETE        ⓘ │   │  │
│  │  │ METROSUR         │ METRONORTE       │ METROESTE         │   │  │
│  │  │                  │ 10 Viajes        │ 10 Viajes         │   │  │
│  │  │                  │ [icono Metro]    │ [icono Metro]     │   │  │
│  │  └──────────────────┴──────────────────┴───────────────────┘   │  │
│  │                                          (globo) (bandera ES)  │  │
│  └────────────────────────────────────────────────────────────────┘  │
└──────────────────────────────────────────────────────────────────────┘
```

**Descripción:** fotografía tomada de frente y algo en escorzo de la pantalla táctil vertical de una máquina expendedora, dentro de una estación (a la derecha se ve la pared metálica y parte del cuerpo del equipo). Una mano de un pasajero entra desde el borde inferior izquierdo y señala con el índice la primera tarjeta de la grilla (METROBÚS).

En la pantalla se distinguen, de arriba hacia abajo:

- Dos botones rojos recortados por el borde superior de la foto, con el texto ilegible; entre ellos, un botón blanco: "Comprar sólo Tarjeta Multi".
- Una fila de dos pestañas: a la izquierda "Comprar billetes por destino", con un ícono de pin de ubicación amarillo sobre fondo claro; a la derecha "Comprar por tipo de billete", con el ícono del logo del Metro sobre fondo naranja y la pestaña resaltada en fondo oscuro (opción activa).
- Debajo, cuatro categorías con ícono: "Billete 1 Viaje" (cuadro verde con el número 1), "Billete 10 viajes" (cuadro naranja con el número 10, con una línea/subrayado azul que la marca como categoría seleccionada), "Aeropuerto" (ícono de avión rojo) y una cuarta cuyo texto queda parcialmente tapado por el reflejo de una luz, legible como "...urístico" (ícono de calendario rojo).
- Una grilla de seis tarjetas de producto, cada una con un ícono de información (ⓘ) en su esquina superior derecha: fila superior — "METROBÚS / 10 Viajes" (con íconos de metro, un recuadro con el número 1 y un ícono de transbordo/autobús), "BILLETE COMBINADO / 10 Viajes" (con tres íconos: metro, metro-autobús y TFM), "BILLETE TFM / 10 Viajes" (con el ícono TFM); fila inferior — "...LLETE METROSUR" (el inicio del texto queda cortado por el borde izquierdo de la foto y la cantidad de viajes queda tapada por la mano), "BILLETE METRONORTE / 10 Viajes" (ícono del rombo del Metro) y "BILLETE METROESTE / 10 Viajes" (ícono del rombo del Metro).
- Abajo a la derecha, un botón redondeado de idioma: ícono de globo terráqueo azul junto a la bandera de España.

En  base al video publicado en: https://www.youtube.com/watch?v=l_lfAWvSAUI:

- Identificar los requerimientos funcionales y no funcionales
- Realizar el caso de uso que refleje las funcionalidades provistas al pasajero

Encuentran más información en:

- https://www.metromadrid.es/es/nota-de-prensa/2024-02-14/la-comunidad-de-madrid-renueva-con-tecnologia-inteligente-las-maquinas-expendedoras-de-titulos-de-transporte-en-19-estaciones-de-metro

---

## Notas de conversión

- **Hipervínculos:** las dos URLs se extrajeron de las anotaciones del PDF y van completas inline. La segunda aparece cortada en el texto visible del original por el salto de línea ("...renueva-con- / tecnología-inteligente..."), lo que al copiarla del texto plano produce "renueva-contecnologia"; la URL real de la anotación es la transcrita.
- **Título de metadatos:** el PDF conserva en sus propiedades un título de otro enunciado ("Dado el siguiente enunciado y el Diagrama de CU que lo modela, indicar los errores que se encuentran en el mismo, justificando cada uno de ellos"), ajeno al contenido de esta página. Se transcribe acá como observación; no forma parte del cuerpo visible.
- **Doble espacio en el original:** "En  base al video publicado en:" figura con dos espacios; se transcribe tal cual.
- La fotografía de la pantalla se describió a partir de la verificación visual de la página rasterizada a 300 dpi. Los textos declarados ilegibles o cortados (botones rojos superiores, inicio de "BILLETE METROSUR", categoría "...urístico") se marcaron como tales y no se completaron.

---

**FIN DEL ARCHIVO FUENTE — Casos de Uso – Metro de Madrid**
