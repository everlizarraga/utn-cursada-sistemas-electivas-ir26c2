# Lectura en español — Cap. 20 · Parte 1: El marco y las soluciones disponibles

> **Origen.** Capítulo 20, secciones 20.1 y 20.2, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Christof Ebert** (Alcatel) y **Roel J. Wieringa** (Universidad de Twente, Países Bajos).
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.

---

## El último capítulo

Cierra el libro. Y su intención no es resumir hacia atrás:

> Este capítulo **no mira tanto hacia atrás ni intenta dar un resumen tutorial, sino más bien INDICAR QUÉ VIENE Y QUÉ ES RELEVANTE** en la disciplina.

**Lo más aprovechable de esta Parte 1** es la definición de qué es la ingeniería de requisitos, la clasificación de tipos de requisitos, **y una lista de seis riesgos característicos** que funciona muy bien como checklist final.

---

## 1. Qué es la ingeniería de requisitos 🔴

La definición de apertura es de las mejores del libro porque **la ubica entre dos disciplinas**:

> **La ingeniería de requisitos es la rama de la ingeniería de sistemas que se ocupa de LAS PROPIEDADES Y RESTRICCIONES DESEADAS de los sistemas intensivos en software, LAS METAS a alcanzar en el entorno del software, y LAS SUPOSICIONES sobre ese entorno.**

Y su alcance: **desde la etapa de análisis del problema hasta la implementación y el mantenimiento.**

### La doble naturaleza 🔴

> **La ingeniería de requisitos es a la vez una disciplina ORIENTADA AL PROBLEMA y ORIENTADA A LA SOLUCIÓN.**

```
   COMO DISCIPLINA ORIENTADA AL PROBLEMA
   se conecta con la INGENIERÍA DE SISTEMAS:
   analiza los problemas de software que existen en el
   SISTEMA SOCIO-TÉCNICO donde el software va a jugar
   un papel
   → toma prestado de la GESTIÓN DE PRODUCTO y de la
     PSICOLOGÍA
   → trata de metas, de los interesados que tienen esas
     metas, y de los problemas a resolver dentro de
     restricciones de negocio dadas

   COMO DISCIPLINA ORIENTADA A LA SOLUCIÓN
   se conecta con la INGENIERÍA DE SOFTWARE:
   especifica las funciones deseadas, los atributos de
   calidad y otras propiedades del software que va a
   construirse o ensamblarse
```

**Y la síntesis:**

> **Como AMBAS visiones son válidas, la ingeniería de requisitos es UNA DISCIPLINA QUE MAPEA NECESIDADES A SOLUCIONES.**

> ⚠️ **Cruce con la cátedra.** Esa frase final es la mejor definición de una línea que hay en el libro, y conecta con el arco de tu materia: **entender → descubrir → modelar → especificar → validar.** Todo eso es el mapeo de necesidades a soluciones.
>
> Y notá que la orientada al problema **toma prestado de la gestión de producto y de la psicología** — no de la informática. Es otra manera de decir lo que atraviesa la serie: **la mitad del trabajo no es técnica.**

---

## 2. La clasificación de requisitos 🔴

La definición base que usan:

> **Un requisito es una CONDICIÓN O CAPACIDAD QUE NECESITA UN USUARIO para resolver un problema o alcanzar un objetivo.**

Y proponen una clasificación en **dos dimensiones cruzadas**, que es más fina que la que viste hasta ahora:

### Primera división: proceso contra producto

| | Ejemplos |
|---|---|
| **Requisitos de PROCESO** | **Costo · comercialización · plazo de entrega · distribución · organización · documentación** |
| **Requisitos de PRODUCTO** | Se subdividen en funcionales y no funcionales |

### Segunda división: para el usuario contra para el desarrollador 🔴

Y acá está lo interesante. **Cada tipo de requisito de producto se cruza con quién es su destinatario:**

| | **Para el USUARIO** | **Para el DESARROLLADOR** |
|---|---|---|
| **Funcionales** | **Interfaz de usuario · casos de uso · servicios** | **Arquitectura · balanceo de carga · alimentación eléctrica** |
| **No funcionales** | **Rendimiento · confiabilidad · usabilidad** | **Verificabilidad · mantenibilidad · bibliotecas y herramientas** |

> ⚠️ **Cruce con la cátedra — esta tabla es muy útil y es nueva respecto de lo que viste.** La distinción funcional/no funcional que trabajás en la materia **se cruza con una segunda pregunta: ¿a quién le sirve?**
>
> Y las dos celdas de la derecha son las que más se olvidan: hay requisitos **funcionales que al usuario no le importan** (balanceo de carga) y **no funcionales que solo le sirven al equipo** (verificabilidad, mantenibilidad).
>
> Es útil para revisar una lista de requisitos: **si todos tus no funcionales son de la celda del usuario —rendimiento, usabilidad— probablemente te falten los del desarrollador.** Y esos son los que después te complican el mantenimiento.

**Y una definición completa del proceso:**

> **La ingeniería de requisitos es EL ENFOQUE SISTEMÁTICO para recolectar, especificar, analizar, verificar, asignar, trazar y gestionar los requisitos —funcionales, no funcionales, de proceso— de un sistema, Y PARA ESTABLECER Y MANTENER UN ACUERDO entre el cliente/usuario y el equipo del proyecto SOBRE LOS REQUISITOS CAMBIANTES del sistema.**

---

## 3. La incertidumbre como problema de fondo 🔴

Esta sección explica algo que atraviesa todo el libro.

> **Un problema con el que la ingeniería de requisitos tiene que lidiar es que LOS REQUISITOS SON INCIERTOS. Eso es casi por definición**, y queda capturado en una vieja consigna de los analistas: **"lo voy a saber cuando lo vea".**
>
> **Esas incertidumbres AUMENTAN en mercados que cambian rápido.**

**Y de dónde vienen — dos causas de naturaleza muy distinta:**

```
   LIMITACIONES COGNITIVAS
   a los usuarios les cuesta IMAGINAR EL PRODUCTO y
   enunciar sus requisitos
   Y ADEMÁS: sus opiniones sobre sus PROPIOS requisitos
   EVOLUCIONAN POR EL SOLO EJERCICIO DE LA ELICITACIÓN

   CIRCUNSTANCIAS CAMBIANTES
   → y una vuelta de tuerca:
     ¡INTRODUCIR EL SISTEMA CAMBIA LA SITUACIÓN,
      Y POR LO TANTO CAMBIA LOS REQUISITOS!
```

**Y la consecuencia sobre la disciplina misma:**

> **La disciplina está fuertemente impactada por esa incertidumbre. Eso explica POR QUÉ LA INGENIERÍA DE REQUISITOS NO ES TAN "PRECISA" NI "BIEN DELIMITADA" como, por ejemplo, las pruebas de software o la gestión de proyectos.**

> ⚠️ **Cruce con la cátedra.** Esas dos causas son las mismas que viste en el capítulo 4 como **paradoja de la volatilidad**, pero acá están mejor separadas:
>
> **La primera es interna a la persona:** el ejercicio de elicitar **cambia lo que el usuario quiere**, porque lo obliga a pensar en cosas que no había pensado.
>
> **La segunda es externa:** el sistema, al entrar en funcionamiento, **modifica el mundo que había motivado sus propios requisitos.**
>
> Ninguna de las dos se puede evitar. Y la última frase es un buen consuelo para el estudiante: **si la ingeniería de requisitos te parece menos precisa que otras materias, no es tu impresión — es la naturaleza del problema.**

**Y el vínculo con el fracaso de proyectos, sostenido desde los años 70:**

> Se reporta **una relación clara entre gestión de requisitos y éxito del proyecto desde los años 70**, poniendo típicamente **la gestión insuficiente de requisitos EN LO ALTO DE LA LISTA de factores que contribuyen al fracaso.**

**Y el dato del informe más citado, de 2003:** sobre más de 13.000 casos, **solo el 34 % de los proyectos se consideró exitoso; el 15 % fueron fracasos completos y el 51 % restante quedó "desafiado"** —es decir, con sobrecosto o sobre-tiempo.

**Y un dato específico de requisitos que vale:**

> **Solo el 52 % de los requisitos originalmente asignados aparece en la versión final entregada.**

---

## 4. Los seis riesgos característicos 🔴🔴

Esta lista es lo más aprovechable de la Parte 1. **Seis maneras típicas de arruinar el trabajo de requisitos.**

```
   1. PASAR POR ALTO UN REQUISITO CRUCIAL

   2. REPRESENTACIÓN INADECUADA DEL CLIENTE

   3. MODELAR SOLO LOS REQUISITOS FUNCIONALES

   4. NO INSPECCIONAR LOS REQUISITOS

   5. INTENTAR PERFECCIONAR LOS REQUISITOS ANTES DE
      EMPEZAR LA CONSTRUCCIÓN

   6. REPRESENTAR LOS REQUISITOS EN FORMA DE DISEÑOS
```

> ⚠️ **Cruce con la cátedra — corré esta lista sobre cualquier entregable tuyo.** Cada riesgo tiene su capítulo detrás:
>
> - **1** → la completitud (capítulos 8 y 17) y el conocimiento del dominio (capítulo 2)
> - **2** → los interesados críticos para el éxito (capítulo 7) y el cliente único ágil (capítulo 14)
> - **3** → la debilidad reconocida de los métodos ágiles (capítulo 14) y las especificaciones suplementarias (capítulo 17)
> - **4** → las inspecciones (capítulo 8) y la carencia más extendida de las seis empresas (capítulo 18)
> - **5** → *"puede no estar nunca completa en todos los aspectos"* (capítulo 16)
> - **6** → la independencia del diseño (capítulo 17): *¿existe más de un diseño que lo cumpla?*
>
> Notá que **el 5 y el 6 son errores por exceso, no por defecto.** Se puede fallar por trabajar de más o por trabajar en el nivel equivocado.

### Las tres contramedidas 🔴

Y cómo se atienden esos riesgos durante la recolección, el análisis y la especificación:

| Contramedida | En qué consiste |
|---|---|
| **CATEGORIZAR** | **Agrupar los requisitos**, permitiendo un entendimiento de más alto nivel de las relaciones y dependencias, **aplicando consistentemente una plantilla de especificación** |
| **ORGANIZAR** | **Usar herramientas automatizadas** para asistir en el entendimiento y el trazado de los requisitos desde su origen hasta la asignación y la entrega, **aplicando gestión estricta del cambio** |
| **PRIORIZAR** | **Determinar el orden de consideración según la CRITICIDAD DE LA NECESIDAD y el NIVEL DE RIESGO ASOCIADO**, implementando en incrementos según las prioridades, **y sacando del alcance los de prioridad más baja** |

> Notá el criterio de priorización que proponen: **criticidad de la necesidad Y nivel de riesgo.** El riesgo como segundo eje es lo que faltaba en varias de las técnicas del capítulo 4, y es lo que la evaluación del capítulo 18 encontró ausente en cuatro de seis empresas.

---

## 5. Los estándares 🟢

Un mapa de qué estándar cubre qué:

| Estándar | Qué cubre |
|---|---|
| **ISO 15288** | Procesos del ciclo de vida **del SISTEMA** |
| **ISO 12207** | Procesos del ciclo de vida **del SOFTWARE** |
| **ISO 9001** | Guías generales para garantizar productos de calidad |
| **IEEE 1220** | El proceso de **ingeniería de sistemas** |
| **IEEE 1233 e IEEE 830** | **Gestión de requisitos**: técnicas genéricas para asegurar que las necesidades del cliente **se registren y se tracen** a lo largo del ciclo de vida |
| **ISO 9126** | **El estándar clave que cubre los requisitos NO FUNCIONALES** y clasifica los atributos genéricos de calidad |

---

## 6. Las dos preguntas de investigación 🔴

> **La investigación se enfocó en DOS PREGUNTAS MAYORES: cómo extraer los requisitos "CORRECTOS", y cómo lidiar con los requisitos QUE CAMBIAN.**

### Para extraer los correctos

```
   TÉCNICAS DE ELICITACIÓN Y ANÁLISIS
   crear escenarios y casos de uso · entrevistar a
   distintos interesados · extraer requisitos de un
   sistema existente · sintetizar requisitos a partir de
   necesidades y comportamientos del usuario · descubrir
   requisitos mediante experimentos o prototipos ·
   determinar marcos de problema

   TÉCNICAS PSICOLÓGICAS para identificar debilidades
   preguntas libres de contexto · talleres · análisis de
   distintos puntos de vista y esquemas de interacción ·
   teoría de la interacción · análisis de protocolo
```

### Para lidiar con el cambio

```
   · CICLOS DE VIDA EVOLUTIVOS Y PROTOTIPADO
     (desarrollo incremental, métodos ágiles)
   · ANÁLISIS DE SENSIBILIDAD
     (determinar la localización, alcance e impactos de
      los cambios · gestión de portafolio)
   · GESTIÓN PRÁCTICA DEL RIESGO
     (trazabilidad · análisis de impacto · mejor
      mantenibilidad · modularidad · AISLAR LAS
      FUNCIONALIDADES SUJETAS A CAMBIO)
```

### Y el diagnóstico incómodo 🔴🔴

Pero después de listar todo eso, los autores dicen algo importante:

> **Estas soluciones, sin embargo, NO SE USAN AMPLIAMENTE EN LA INDUSTRIA.**
>
> De hecho, **nos dimos cuenta en nuestros propios proyectos —y también en discusiones durante conferencias del área— de que, EXCEPTO EL DESARROLLO ITERATIVO, NINGUNA de las técnicas mencionadas LLEGÓ REALMENTE AL USO GENERALIZADO.**

**Y dos observaciones sobre por qué:**

> **Usar UNA técnica específica de elicitación del amplio abanico descrito ES INSUFICIENTE, POR LAS DEBILIDADES INHERENTES DE CADA TÉCNICA INDIVIDUAL.**
>
> De hecho, **los analistas experimentados LAS USAN MEZCLADAS, PERO SIN REGLAS ESPECÍFICAS que uno pueda transmitirle a los profesionales.**

**Y sobre el prototipado, que es el caso más notable:**

> **Las técnicas evolutivas combinadas con gestión repetitiva del riesgo —específicamente el PROTOTIPADO, que siempre se proclamó como la mejor manera de lidiar con la incertidumbre— RARA VEZ SE USAN EN LA PRÁCTICA. Los cambios se atienden principalmente A POSTERIORI.**

### El diagnóstico final 🔴

Y acá viene la explicación que los autores proponen, y que es la tesis del capítulo:

> **Sostenemos que el uso pobre de las soluciones disponibles ES A MENUDO UN PROBLEMA DE TRANSFERENCIA TECNOLÓGICA.**
>
> **UNA TÉCNICA AISLADA, tal como se la describe en la mayoría de las referencias, NO VA A AYUDAR — porque QUEDA POCO CLARO PARA EL PROFESIONAL CÓMO INTRODUCIRLA y qué OTRAS características del entorno tiene que observar.**

> ⚠️ **Cruce con la cátedra — este diagnóstico cierra una pregunta que la serie viene arrastrando.** El capítulo 19 preguntaba: *¿por qué unas técnicas se adoptan y otras, con la misma evidencia, no?* **Esta es la respuesta que proponen: no es un problema de las técnicas, es un problema de transferencia.**
>
> Y el argumento es preciso: **un paper describe qué hace la técnica, no cómo introducirla en una organización que ya tiene sus costumbres.** Falta el manual de instalación.
>
> Fijate además en el hallazgo sobre los expertos: **usan las técnicas mezcladas, pero no pueden explicar la regla.** Es exactamente lo que decía el capítulo 2 con el hallazgo de Hickey y Davis: **los expertos eligen bien y no saben explicitar cómo.**
>
> Eso significa que **la parte del oficio que más rinde es la que menos se puede enseñar en un libro.** Se aprende haciendo — que es, de paso, la justificación de que tu materia tenga tantos TP.

---

## 7. Las herramientas 🟡

### Las tres áreas

```
   1. BASES DE DATOS DE REQUISITOS
      los requisitos deben gestionarse en un almacén
      seguro y gestionado

   2. HERRAMIENTAS DE GESTIÓN DEL CAMBIO
      asegurar que el cambio sea un proceso de FLUJO DE
      TRABAJO cuyas etapas puedan definirse, con el flujo
      de información entre ellas parcialmente automatizado

   3. HERRAMIENTAS DE GESTIÓN DE TRAZABILIDAD
      recuperación automatizada de los vínculos entre
      requisitos, y desde los requisitos hacia otros
      artefactos
```

### Lo mínimo que deben soportar 🔴

Esta lista sirve como criterio de evaluación:

```
   · CAPTURAR requisitos individuales e identificarlos
   · CLASIFICARLOS y ordenarlos
   · ASOCIARLOS con más información: distintos tipos de
     requisito (cliente, sistema, software) o CON CASOS
     DE PRUEBA
   · LÍNEA BASE y gestión de configuración (por ejemplo,
     para preservar un resumen de estado con marca de
     tiempo)
   · INTERFACES ABIERTAS para conectarse a otras
     herramientas
```

**Y en la gama alta se espera además trazabilidad** no solo entre tipos de requisito, **sino con otros artefactos**: documentos de diseño, casos de prueba, planes de proyecto.

### La trayectoria típica y su trampa 🔴

Y acá hay un consejo práctico muy bueno:

> **La mayoría de las empresas empieza su soporte de herramientas sobre la base de PROCESADORES DE TEXTO O PLANILLAS. La evolución va después hacia una "base de datos chica" en un segundo paso.**
>
> **Cuando las demandas siguen creciendo, las empresas se dan cuenta de que CUALQUIER HERRAMIENTA CASERA VA A SIGNIFICAR MUCHO ESFUERZO RECURRENTE, y empiezan a mirar herramientas comerciales.**

**Y la trampa:**

> **Cambiar tan tarde en el ciclo de uso a menudo significa que sus propios usuarios PIDEN PRESERVAR TODA ESA LINDA FUNCIONALIDAD CASERA.**
>
> Aunque **los vendedores normalmente disfrutan de ese tipo de adaptación, ya que les genera ingreso recurrente**, recomendamos **ser cuidadosos: seleccionar una herramienta comercial que esté CERCA DE LAS NECESIDADES TÍPICAS DE USO Y DESPUÉS NO CAMBIARLA**, excepto por el diseño de reportes y los parámetros de estado o ruteo. **Eso mantiene manejable el costo del ciclo de vida de la herramienta.**

> ⚠️ **Cruce con la cátedra.** El consejo tiene una lógica que vale más allá de las herramientas de requisitos: **elegí algo que ya se parezca a lo que necesitás, y después no lo toques.**
>
> Y notá el conflicto de interés que señalan al pasar: **al vendedor le conviene que personalices, porque eso genera ingreso recurrente.** Es un buen recordatorio de que quien te aconseja sobre una herramienta puede no tener tus mismos intereses.

---

## Mapa de la Parte 1

```
   QUÉ ES LA IR
   "una disciplina que MAPEA NECESIDADES A SOLUCIONES"
   orientada al PROBLEMA (toma de gestión de producto
   y psicología) + orientada a la SOLUCIÓN (ingeniería
   de software)

   ─────────────────────────────────────────────

   CLASIFICACIÓN EN DOS DIMENSIONES
                     para el USUARIO   para el DESARROLLADOR
   FUNCIONALES       interfaz, casos   arquitectura,
                     de uso, servicios balanceo de carga
   NO FUNCIONALES    rendimiento,      VERIFICABILIDAD,
                     usabilidad        MANTENIBILIDAD
   (+ requisitos de PROCESO: costo, plazo, distribución)

   ─────────────────────────────────────────────

   LA INCERTIDUMBRE — 2 causas
   COGNITIVA: el ejercicio de elicitar CAMBIA lo que
              el usuario quiere
   EXTERNA:   introducir el sistema CAMBIA LA SITUACIÓN
              que motivó sus propios requisitos

   → por eso la IR NO ES tan precisa como las pruebas
     o la gestión de proyectos

   solo el 52 % de los requisitos originalmente asignados
   llega a la versión final

   ─────────────────────────────────────────────

   ══► LOS 6 RIESGOS ◄══
   1. pasar por alto un requisito crucial
   2. representación inadecuada del cliente
   3. modelar SOLO los funcionales
   4. no inspeccionar los requisitos
   5. querer PERFECCIONARLOS antes de construir
   6. representarlos EN FORMA DE DISEÑOS
      (el 5 y el 6 son errores POR EXCESO)

   contramedidas: CATEGORIZAR · ORGANIZAR · PRIORIZAR
   (por criticidad Y POR RIESGO)

   ─────────────────────────────────────────────

   ══► EL DIAGNÓSTICO ◄══
   salvo el desarrollo iterativo, NINGUNA técnica llegó
   al uso generalizado
   los expertos las usan MEZCLADAS pero SIN REGLAS
   TRANSMISIBLES
   → es un problema de TRANSFERENCIA TECNOLÓGICA:
     los papers dicen qué hace la técnica,
     no CÓMO INTRODUCIRLA
```

---

## Preguntas para chequear que quedó

1. ¿Cuál es la intención declarada de este último capítulo?
2. Definí ingeniería de requisitos según el capítulo. ¿Cuál es su alcance temporal?
3. Explicá la doble naturaleza de la disciplina. ¿De qué disciplinas toma prestado la parte orientada al problema?
4. ¿Cuál es la definición de una línea que dan al final de esa discusión?
5. Nombrá ejemplos de requisitos de proceso.
6. Completá la tabla de dos dimensiones con un ejemplo en cada celda.
7. ¿Cuáles son los requisitos no funcionales "para el desarrollador" y por qué se olvidan?
8. Nombrá las dos causas de la incertidumbre de los requisitos.
9. ¿Por qué el ejercicio de elicitar cambia lo que el usuario quiere?
10. ¿Por qué introducir el sistema cambia los requisitos?
11. ¿Por qué la ingeniería de requisitos no es tan precisa como las pruebas de software?
12. ¿Qué porcentaje de los requisitos originalmente asignados llega a la versión final?
13. Nombrá los seis riesgos característicos.
14. ¿Cuáles dos de los seis son errores por exceso y no por defecto?
15. Nombrá las tres contramedidas y en qué consiste cada una.
16. ¿Qué dos criterios propone para priorizar?
17. ¿Qué cubren IEEE 830 e ISO 9126 respectivamente?
18. ¿Cuáles son las dos preguntas mayores de la investigación en el área?
19. ¿Qué técnica es la única que llegó al uso generalizado, según los autores?
20. ¿Por qué usar una sola técnica de elicitación es insuficiente?
21. ¿Qué hacen los analistas experimentados y qué problema tiene eso para la enseñanza?
22. ¿Cuál es el diagnóstico sobre por qué las soluciones disponibles no se usan?
23. Nombrá las tres áreas de herramientas de soporte.
24. ¿Qué cinco cosas debe soportar como mínimo una herramienta de requisitos?
25. Describí la trayectoria típica de adopción de herramientas y cuál es la trampa al final.
26. ¿Qué conflicto de interés señalan sobre los vendedores de herramientas?

---

**FIN DEL CAPÍTULO 20 — PARTE 1**

*Sigue en la Parte 2 —la última de la serie—: las cuatro tendencias, las habilidades del ingeniero de requisitos, y hacia dónde va la disciplina.*
