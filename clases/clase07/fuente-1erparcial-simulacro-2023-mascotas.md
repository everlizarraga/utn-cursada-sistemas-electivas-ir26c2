# Ingeniería de Requisitos — 1er Parcial 2023 / Simulacro: Estacionamiento para Mascotas

> Conversión fiel a Markdown de 1erParcial_Mascotas_Simulacro_23.pdf (2 páginas).

**Notas de conversión**

- El encabezado del documento (logo de UTN.BA a la izquierda y el texto en cursiva a la derecha) se repite en ambas páginas; se transcribe en cada una.
- En la página 1, la foto está insertada a la derecha de los párrafos que empiezan con "A este concepto…" y "Los PD contarán…". Aquí se ubica entre esos dos párrafos. Los textos impresos sobre la cuchita de la foto no son legibles en el PDF y no se transcriben.
- La nota al pie 1 contiene un hipervínculo. El texto visible es `www.dogparker.com` y el destino extraído de la anotación es `http://www.dogparker.com/`.
- Se transcribe tal cual la frase "del peso de la misma", que sigue a "la raza del perro". La concordancia es ambigua en el original, porque "la misma" puede referir a la raza o al perro.
- "RESOLUCION" aparece sin tilde en el encabezado original.

---

## Página 1

*[Logo: UTN.BA — Universidad Tecnológica Nacional, Facultad Regional Buenos Aires]*

*Ingeniería de Requisitos – 1ER PARCIAL*
*2023 / SIMULACRO*
*RESOLUCION GRUPAL*

**Estacionamiento para Mascotas**

La empresa MascotaCare S.A., está desarrollando un nuevo concepto orientado al cuidado canino, brindando el mejor confort posible y seguridad a la mascota cuando no pueda estar al cuidado de su dueño por unas pocas horas.

Es una solución ideal para supermercados o restaurantes, a los cuales los dueños de las mascotas no pueden ingresar con el animal.

A este concepto lo llamaron ParkingDog (PD)[^1], el cual consta de cuchas inteligentes y seguras, instaladas en espacios comunes o públicos como ser veredas o parques o en las puertas de los locales que requieran el servicio y una app mobile para interacción con los dueños de las mascotas. Cada PD estará acondicionado especialmente para albergar un solo perro (en un principio solo para uno, ya se está pensando realizar prototipos para poder alojar más de uno e incluso otros tipos de mascotas).

*[Foto: una cabina blanca con forma de casita, con techo a dos aguas, instalada en una vereda. El frente tiene una puerta de vidrio oscuro a través de la cual se ve un perro adentro. El lateral visible es de color verde agua y tiene una columna de íconos circulares fucsia con leyendas debajo, además de un cartel rosado en la parte superior. A la derecha, una persona parcialmente visible apoya la mano en el borde de la puerta.]*

Los PD contarán con una puerta de vidrio para que el dueño pueda ver a su can en todo momento, puerta que quedará cerrada una vez que inicie el servicio de Parking. Cada PD cuenta con un dispensador de agua, otro de comida y está acondicionado para que la mascota no sufra ninguna inclemencia climática (el ambiente interno oscila entre los 22 y 25 grados). Los PD vienen dotados con una cámara interna para que el dueño de la mascota pueda visualizarla desde la app en su celular. La modalidad en la cual el PD dispensa el agua, el tipo de comida y la cantidad dependerá de la raza del perro (que debe indicar el cliente al iniciar el servicio) y del peso de la misma que se obtiene mediante una balanza electrónica incorporada.

Los dueños de mascotas contarán con una tarjeta de contacto, la cual puede ser leída por el lector instalado en el PD, que identifica al usuario y le indica si puede utilizarlo o no.

Si el PD está en uso, sólo puede finalizar su utilización quien inició el servicio con su tarjeta o un personal autorizado de la firma con su correspondiente tarjeta de mantenimiento. El dueño de mascota sólo puede estar utilizando un PD a la vez.

En caso de que el PD esté disponible, la pantalla táctil informará que es un usuario válido y requerirá el código numérico de autenticación, si es correcto se abrirá la puerta permitiendo ingresar al perro (el servicio comienza desde el momento mismo que se abre la puerta).

Para acceder al servicio se requiere el pago de una membresía mensual por débito en tarjeta, que permite el uso de los PD con 1 hora bonificada. El tiempo extra de servicio se paga por tiempo de uso, facturable por hora sin fraccionamiento (59 minutos = 1 hora, 61 minutos = 2 horas) y además se abona por excedente de uso de agua (ni bien comienza el servicio se tiene ½ litro de agua disponible, luego por cada ½ litro adicional se debe abonar extra) y excedente de alimento (como ración inicial se tiene la cantidad estipulada por los parámetros nombrados y luego se debe abonar por cada 200 gramos extra).

[^1]: Modelo adaptado de [www.dogparker.com](http://www.dogparker.com/)

---

## Página 2

*[Logo: UTN.BA — Universidad Tecnológica Nacional, Facultad Regional Buenos Aires]*

*Ingeniería de Requisitos – 1ER PARCIAL*
*2023 / SIMULACRO*
*RESOLUCION GRUPAL*

Una vez que finaliza el uso del PD por parte de una mascota, el PD inicia su secuencia de autolimpieza por lo que el PD no se puede utilizar hasta que culmine la misma y quede en estado disponible. El proceso dura cerca de 2 minutos desde que el último usuario cierra la puerta. Adicionalmente, cuando se están haciendo arreglos, el PD estará en estado de mantenimiento sin poder ser utilizado por usuarios hasta que un técnico de la firma vuelva a ponerlo en funcionamiento mediante su tarjeta de mantenimiento.

Mediante la aplicación *mobile* de MascotaCare el dueño podrá verificar los PD disponibles en su zona. Si el dueño está utilizando alguno de los PD puede visualizar a su mascota en la app por medio de la cámara instalada, como así también dispensarle más agua y alimento, verificar la temperatura en la cabina, saber el tiempo que lleva utilizándola, informar de algún inconveniente o problema con el PD y comunicarse con el soporte técnico si fuese necesario.

1. Usted trabajó en la concepción del producto ParkingDog y en la definición de la app que utilizan los dueños de mascotas para la interacción con el PD.
   Deben lanzar el producto al mercado y publicitarlo, para lo cual debe brindar al área de marketing la descripción de las funcionalidades que brinda PD y la app a los dueños de mascotas, de forma tal que puedan ser incluidas en un folleto con especificaciones técnicas del producto. Se pide entonces que enumere los requerimientos funcionales y no funcionales que brindará al área de marketing para ser incluidos en el folleto.
   Deben ser 5 requerimientos funcionales y 5 no funcionales, que sean de interés de los dueños de mascotas.
2. Realice el **diagrama de casos de uso**, indicando actores, casos de uso y relaciones. Recuerde respetar la nomenclatura UML.

---

**FIN DEL ARCHIVO FUENTE — Ingeniería de Requisitos — 1er Parcial 2023 / Simulacro: Estacionamiento para Mascotas**
