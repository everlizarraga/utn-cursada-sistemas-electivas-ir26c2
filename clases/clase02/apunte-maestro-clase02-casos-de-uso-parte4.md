# APUNTE MAESTRO — Clase 02 · Casos de Uso — Parte 4

**Ingeniería de Requisitos — clase02 (20/08/2026) · Parte 4 de 4**
**Esta parte:** el televisor armado de punta a punta, el mapa de qué se modela y qué no, los otros dos sistemas de la unidad con sus criterios, la información operativa de la clase y el checkpoint de la unidad.
**Ya viste:** Parte 1 — qué es un CU · Parte 2 — actores · Parte 3 — relaciones.

**Marcas:** 🔴 central y evaluable · 🟡 secundario · 🟢 mencionado al pasar.
**Notación ASCII:** la misma de las Partes 2 y 3 (`──▷` generalización con triángulo hueco en el general · `--inc-->` / `--ext-->` punteadas con su estereotipo).

---

## 🔴 1. El televisor, armado de punta a punta

Todo lo de las tres partes anteriores, junto. El inventario completo primero, y después los fragmentos — los que ya viste se citan, los nuevos se dibujan.

### El inventario

| Actor | Casos de uso propios | Relaciones que cuelgan |
|---|---|---|
| **Televidente** (principal, arriba de la cadena) | Encender TV · Apagar TV · Cambiar canal · Seleccionar canal · Ajustar resolución | Encender y Apagar incluyen Tomar time-stamp; Apagar incluye Acumular tiempo de uso; cada función se generaliza en sus formas (control remoto / botonera / app…) |
| **Instalador / Admin / Configurador** (hereda del Televidente) | Conectar entrada | Conectar entrada se especializa en Conectar WiFi y Conectar TDA |
| **Técnico** (hereda del Instalador) | Realizar mantenimiento | Incluye Consultar horas de uso, que es extendido por Derivar a garantía |
| **Tiempo/Reloj** (secundario, punteado) | — | Asociado a Tomar time-stamp |
| **TDA** (secundario, punteado) | — | Asociado a Conectar TDA |
| **Access point** (secundario, punteado) | — | Asociado a Conectar WiFi |

Dos aclaraciones del inventario:

- **Seleccionar canal** es un caso de uso distinto de Cambiar canal — la diferencia de intención de la Parte 1 (zapping vs ya sé qué quiero ver) se sostiene hasta el diagrama final.
- **Ajustar resolución** puede modelarse como caso de uso: es cambiar una configuración, una función con flujo describible. Que el pedido liste *qué* resoluciones se aceptan es otra cosa — eso es la condición, y va en la tabla de la sección 2.

### Los fragmentos

**La cadena de actores** — la viste completa en la Parte 2, sección 6: Técnico ▷ Instalador ▷ Televidente, triángulo hueco siempre en el padre.

**Las funciones del Televidente y sus formas** — la generalización de Apagar TV está dibujada en la Parte 3, sección 1. El mismo esquema se repite para Encender, Cambiar y Seleccionar: se dibuja completo para una función y el patrón queda declarado para las demás — dibujarlo cuatro veces no agrega información, y un diagrama también se juzga por lo que decide no repetir.

**El mecanismo de las horas de uso** — Parte 3, sección 4: Encender y Apagar incluyen Tomar time-stamp (reusabilidad), Apagar incluye Acumular tiempo de uso (destacar), y el actor Tiempo, punteado, asociado a Tomar time-stamp.

**El Técnico y la garantía** — Parte 3, sección 6: mantenimiento → inc → consulta ← ext ← garantía.

**El Instalador y las entradas** — este es el fragmento nuevo:

```
 [actor] INSTALADOR ────( Conectar entrada )
                               △    △
        ( Conectar WiFi ) ─────┘    └───── ( Conectar TDA )
               │                                  │
        [actor] ACCESS POINT ╌╌          [actor] TDA ╌╌      ← secundarios, punteados
```

Leelo con las reglas ya vistas: conectar la entrada es la función general; **con qué** se conecta son sus formas — WiFi o antena digital — así que hay polimorfismo y se resuelve por generalización. Y cada sistema externo se asocia **con el caso de uso específico que le corresponde** (Parte 2, sección 7): el access point con Conectar WiFi, la TDA con Conectar TDA — nunca con el óvalo general.

**Lo que te queda a vos:** el pedido también hablaba de una salida de sonido surround y de una salida para un sistema de grabación. El patrón para modelarlos es exactamente el que acabás de ver — función de conexión, especialización si hay formas, sistema externo asociado a lo específico. Aplicarlo a esos dos conectores es el ejercicio natural para comprobar que el patrón es tuyo.

---

## 🔴 2. Qué se modeló y qué no: el mapa RF/RNF del pedido

La promesa de la Parte 1, cumplida. El pedido del televisor, requerimiento por requerimiento:

| Requerimiento del pedido | Tipo | ¿Al diagrama? | Cómo |
|---|---|---|---|
| Encender presionando botón o por control remoto | RF | ✅ | Encender TV + generalización (las dos vías) |
| Cambiar de canal (botón o control) | RF | ✅ | Cambiar canal + generalización |
| Seleccionar cualquier canal disponible | RF | ✅ | Seleccionar canal (CU distinto de Cambiar) |
| Acepta resoluciones 4K y 1920×1080 | RNF | ❌ | Es una condición; la *función* de ajustarla sí puede ser CU |
| Conectarse a sonido surround / TDA / WiFi / grabación | RF | ✅ | Conectar entrada y sus especializaciones; externos como actores secundarios |
| Superar 10.000 horas de uso antes del mantenimiento | RNF | ❌ como CU… | …pero **genera** casos de uso: ver abajo |
| Estar en el mercado para cierta fecha | RNF | ❌ | Restricción; nada que dibujar |
| Respetar propiedad intelectual y normas de redes | RNF | ❌ | Restricciones legales; nada que dibujar |

**El caso finito de la tabla — el RNF que genera casos de uso.** Las 10.000 horas no son una función: son un umbral, y como tal no se dibujan. Pero para que ese umbral sea *verificable* — la palabra con la que se corrige todo en esta materia — el sistema necesita funciones que no estaban pedidas: tomar el time-stamp, acumular el uso, consultarlo, y derivar a garantía cuando corresponde. **Cuatro casos de uso derivados de un requerimiento que no se modela.** Es la versión sofisticada de la regla de la Parte 1: lo que nadie pidió también se modela, cuando se deriva de lo que sí se pidió.

**Para el parcial, si te preguntan si un RNF puede aparecer en el diagrama de casos de uso**
Un requerimiento no funcional no se modela como caso de uso: es una condición o restricción, no una función. Pero un RNF puede generar casos de uso: para que la condición sea verificable, el sistema puede necesitar funciones derivadas (en el televisor, el umbral de 10.000 horas de uso genera Tomar time-stamp, Acumular tiempo de uso, Consultar horas de uso y Derivar a garantía). Se modelan las funciones derivadas, nunca la condición en sí.

---

## 🟡 3. La Discoteca: el sistema para aplicar todo

El segundo sistema de la unidad, sobre el que vas a trabajar. El pedido, en resumen: una persona con una colección de música en medios físicos quiere un sistema donde pueda **dar de alta medios** — vinilos que pueden ser LP o single, excepcionalmente parte de un álbum doble o triple, con dos lados (A y B); CDs que también pueden ser singles o de álbum múltiple pero sin lados; cassettes con las mismas características de edición que los vinilos —, **dar de alta canciones**, y **buscar una canción por título** para saber si la tiene y dónde (autor, intérprete, original o cover, año, medio, lado y pista si corresponde, duración, calificación). De todos los medios interesa el año de lanzamiento. El pedido cierra con dos preguntas abiertas: **cómo debería identificarse en el sistema y cuál sería su rol**, y **cómo cambiaría el diseño si a futuro se incorporan las listas de reproducción de Spotify** (que tienen nombre, duración y se asocian a un momento o ambiente: viaje, fiesta, running, relajación).

El sistema queda como trabajo — pero la unidad ya dejó sentados los criterios para las dos preguntas abiertas:

- **El rol** se resuelve con la regla de la Parte 2: nombre específico que refleje qué quiere hacer frente al sistema. El dueño de la colección es un melómano, un coleccionista — cualquier nombre del dominio antes que "usuario".
- **Spotify** se resuelve con la Parte 2, sección 7: es un **sistema externo** — actor secundario, asociado al caso de uso **específico**, y el verbo desde el punto de vista de **tu** sistema: la canción se **importa** (Spotify la exporta; tu producto es la discoteca). Y un dato más que quedó dicho: entre cargar una canción a mano e importarla desde Spotify hay **polimorfismo** — son dos formas, con recursos distintos, de lograr que la canción entre al sistema; se relacionan por generalización, no como funciones sueltas.

---

## 🔴 4. Regla de entrega: las decisiones de diseño se aclaran

Regla operativa para todos los diagramas que entregues en la materia, nacida de una situación concreta: en una app de mensajería se pueden mandar muchísimos tipos de adjuntos, y modelarlos todos infla el diagrama. Algunos merecen tratamiento propio — el audio, por ejemplo, tiene comportamiento diferenciado: se graba, se puede cancelar, detener, enviar. Otros se pueden simplificar. ¿Y cómo sabe el corrector que simplificaste a propósito y no que te olvidaste?

**Toda decisión de diseño que tomes para simplificar el diagrama se agrega como aclaración escrita.** "Se modelan los adjuntos de audio por su comportamiento propio; el resto se agrupa en X por simplicidad" — una línea. Con la aclaración, la simplificación es una decisión de diseño defendible; sin ella, es indistinguible de un olvido, y se corrige como olvido.

Esto conecta con algo que ya sabés de la cursada: se acepta una solución distinta de la propuesta **si está justificada**. La aclaración es el vehículo de esa justificación.

---

## 🟡 5. Información operativa de la clase

**Del diagnóstico entregado:**
- Todos los entregables del diagnóstico están **aprobados** — era diagnóstico, servía para mapear el punto de partida. La devolución es **individual, por escrito, a partir del martes 25/08**.
- Lo que el diagnóstico reveló a nivel curso, y que esta unidad vino a corregir: la herencia entre actores se intentó usar sin dominarse (por qué un actor hereda de otro), y hubo nombres genéricos. La notación UML estuvo en general bien, con excepciones puntuales.
- La vara de la cursada, dicha explícitamente: si al final del cuatrimestre harías el caso de uso igual que en el diagnóstico, algo falló. La respuesta esperada es que no.

**Tareas que quedaron abiertas:**
- **CU Grupal 1** — el diagrama de casos de uso del sistema asignado a cada equipo (equipo 6: WhatsApp), continuando el trabajo de usuarios/stakeholders de la clase 1. Entrega: **miércoles 26/08, 21:00**.
- El ejercicio de la **Discoteca**, trabajado en clase, también quedó como entrega. La modalidad exacta (individual o grupal) — confirmar en el aula virtual.

**Reglas y ritmo de cursada mencionados:**
- Entregas: siempre **miércoles 21:00**.
- Arranque de clases: **presencial 19:15 · virtual 19:05**, sin esperar rezagados.
- Quedaron **6 equipos definitivos** (hubo un desfasaje administrativo de inscripción entre sistemas; no es decisión pedagógica).
- Las clases presenciales son pocas y muy recomendadas: el trabajo en equipo presencial es preparatorio para el parcial, y una de las próximas incluye un juego de interpretación de roles.
- Material publicado en el aula virtual tras la clase: una resolución propuesta del ejercicio del televisor y la presentación del tema.

---

## ✅ Checkpoint de la unidad

Diez preguntas, sin respuestas — las respuestas van al complemento, después de que las pelees solo.

1. ¿Qué es un caso de uso y desde qué punto de vista se nombra?
2. "Gestionar televisor" aparece como caso de uso en un parcial. Escribí el argumento completo por el que está mal, usando el test del flujo y la cohesión funcional.
3. ¿Por qué "datos" e "información" están prohibidas en el nombre de un caso de uso? ¿Sobre qué opera un verbo, y qué relación tiene eso con los atributos?
4. ¿Qué significa que un actor es un rol y no una persona? Dá los dos motivos por los que la distinción importa.
5. ¿Cuáles son las dos formas válidas de dibujar herencia entre actores? ¿Qué pasa si el diagrama no refleja ninguna?
6. ¿Qué es un actor abstracto, para qué se crea, y qué pasa con la herencia dos escalones más abajo?
7. ¿Bajo qué condición existe generalización entre casos de uso? ¿Qué es el caso de uso general y qué tienen las especializaciones que él no tiene?
8. Un compañero dibujó "Loguearse" incluido con `inc` en los cinco casos de uso de su sistema. Explicale el error y decile dónde va el login en su modelo.
9. ¿Por qué todo caso de uso llamado "Verificar X" o "Controlar X" trae una extensión? ¿Qué relación hay entre la extensión y la decisión por defecto?
10. En una app, la acción B solo puede ocurrir inmediatamente después de la acción A, y es opcional. En otra, la acción D requiere que en algún momento previo se haya hecho C. ¿Cómo se modela cada situación y por qué son distintas?

---

**FIN DE LA PARTE 4 — FIN DEL APUNTE MAESTRO DE LA CLASE 02**
