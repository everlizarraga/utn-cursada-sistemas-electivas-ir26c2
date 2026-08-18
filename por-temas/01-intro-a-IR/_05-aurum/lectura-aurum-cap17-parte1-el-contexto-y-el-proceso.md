# Lectura en español — Cap. 17 · Parte 1: El contexto y el proceso paso a paso

> **Origen.** Capítulo 17, secciones 17.1 a 17.3, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Nur Yilmaztürk**, ABB Corporate Research, Suecia.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.

---

## Por qué este capítulo vale

Es un caso industrial de una empresa que **adaptó el Proceso Unificado** para su línea de productos y midió qué tan bien salieron los requisitos.

**Y trae dos cosas que te sirven mucho:**

1. **Un flujo de trabajo completo, paso a paso**, desde la primera entrevista hasta los casos de prueba — con quién participa en cada paso y qué artefacto sale. Es el proceso más detallado de todo el libro y **está construido alrededor de casos de uso**.
2. En las Partes 2 y 3, **veintiséis atributos de calidad** con sus relaciones entre sí y las métricas concretas que usaron para medirlos. Es la ampliación del capítulo 8.

---

## 1. El costo de los requisitos malos 🔴

El capítulo arranca con la evidencia, que ya conocés pero acá viene con un dato nuevo:

> **El costo de los requisitos de "mala calidad" se estudia desde principios de los 70.** El estudio de Boehm sobre 63 proyectos de software de tres empresas **ilustró que el costo del cambio crece exponencialmente a medida que el proyecto avanza.**
>
> **El costo relativo de reparación es DOSCIENTAS VECES MAYOR en la fase de mantenimiento** que si se detecta en la fase de requisitos.

**Y la escalada se apoya en dos factores:**

```
   1. LA DEMORA desde que el defecto se introdujo hasta
      que se lo detectó
   2. LA CANTIDAD DE RETRABAJO necesaria para corregir
      tanto el defecto original COMO LOS DEFECTOS
      CONSECUENTES de las etapas posteriores
```

**Y el dato nuevo:**

> **El 56 % de los errores detectados durante las pruebas pueden rastrearse a errores de requisitos.**

> ⚠️ **Cruce con la cátedra.** Ese 56 % es un número que conviene tener: **más de la mitad de lo que se encuentra probando el software no es un error de programación — es un error de requisitos que viajó hasta ahí.**
>
> Y notá el segundo factor de la escalada: no se paga solo por arreglar el defecto original, **se paga por arreglar todo lo que se construyó encima.** Es la misma cadena del capítulo 6: un requisito equivocado produce diseño equivocado, código equivocado y pruebas equivocadas.

### Qué aporta un proceso iterativo 🟡

> **La naturaleza iterativa del Proceso Unificado ayuda a eliminar esos riesgos** integrando el producto progresivamente a lo largo del ciclo de vida, **gestionando el cambio y la fluencia de requisitos de manera controlada, aprendiendo temprano y mejorando incrementalmente, y detectando fallas temprano** — construyendo así mayor calidad a lo largo de varias iteraciones.

**Pero con una salvedad:**

> **El Proceso Unificado es un proceso GENÉRICO y es inevitable ADAPTARLO según las necesidades de un proyecto particular** o de los proyectos de un departamento específico, para mayor eficiencia y efectividad.

> ⚠️ **Cruce con la cátedra.** Retené la idea de **fluencia de requisitos** (*requirements creep*): no es que los requisitos cambien de golpe, es que **se van agrandando de a poco sin que nadie decida agrandarlos.** Cada pedido chico parece razonable; la suma no lo es. Es el mismo fenómeno que el capítulo 13 llamaba **sobrecarga del repositorio**.

---

## 2. El contexto 🟢

**La empresa:** un grupo industrial grande, formado en 1988 por la fusión de dos empresas centenarias, con unos 105.000 empleados en cerca de 100 países. Opera en **automatización y tecnologías de potencia.**

**El producto:** una línea de sistemas intensivos en software que **proveen a los laminadores de control en línea preciso de la planitud de tiras laminadas en frío desde hace más de 30 años.**

**Qué hace el sistema:** mide la planitud, analiza y almacena los datos, genera salida para controles automáticos, y presenta datos en pantallas informativas. **Están diseñados para mantenimiento mínimo y máximo tiempo de actividad**, para asegurar producción continua sin perturbaciones y minimizar los niveles de descarte.

**El desafío:** las generaciones tempranas eran sistemas basados en controladores lógicos programables, **y se migraron a una plataforma basada en Java.** Eso llevó a la empresa a necesitar **un cambio en su manera de trabajar.**

**La solución:** adaptaron el Proceso Unificado **"de manera ágil"**, con tres decisiones centrales:

```
   · involucrar ACTIVA Y FUERTEMENTE a interesados de
     perfiles distintos —clientes externos E INTERNOS—
     durante todo el ciclo de vida
   · preparar los CASOS DE PRUEBA ANTES DE CODIFICAR
   · tener PRUEBAS CONTINUAS durante el desarrollo
```

> ⚠️ **Cruce con la cátedra.** La segunda decisión —**casos de prueba antes de codificar**— es exactamente lo que el capítulo 8 llamaba **creación temprana de casos de prueba**, y por la razón que allí se daba: si no podés derivar el caso de prueba, el requisito está mal. Acá se lo institucionalizó como regla del proceso.

---

## 3. El proceso, paso a paso 🔴🔴

Esta es la sección más aprovechable de la Parte 1. Vale seguirla en orden porque **cada paso dice quién participa, qué se produce y qué se hace con eso.**

### Paso 1 — Elicitar

> **El primer paso es elicitar información de los interesados para entender sus necesidades.**
>
> **El proceso IMPONE la participación de clientes externos con conocimiento de negocio Y clientes internos con conocimiento técnico del dominio.**
>
> **Recomienda ENTREVISTAS y TALLER DE REQUISITOS como técnicas.**

### Paso 2 — El documento de visión 🔴

Los hallazgos se usan como **entrada primaria para definir las características del producto** — es decir, **los requisitos de alto nivel, que se describen en un documento de VISIÓN.**

**Y un detalle de diseño del documento que vale la pena:**

> **Una visión PUEDE INCLUIR CARACTERÍSTICAS QUE NO ENTRAN EN EL ALCANCE del proyecto ni en los planes de negocio existentes — pero que deben conservarse PARA REFERENCIA FUTURA.**

> ⚠️ **Cruce con la cátedra.** Ese detalle es la versión "hacia arriba" del mecanismo de **quedar en espera** del capítulo 14: lo que no entra ahora **no se tira, se guarda con su lugar en el documento.** Y conecta con la regla del capítulo 13 de no borrar los requisitos descartados.
>
> Es una decisión de proceso simple con un efecto grande: **la gente sigue proponiendo si sabe que lo que propone no desaparece.**

### Paso 3 — Priorizar las características

> **Los interesados priorizan las características BASÁNDOSE EN ATRIBUTOS ACORDADOS DE ANTEMANO**, para identificar el conjunto final que va a atenderse en esa iteración del proyecto.

> Notá el *"acordados de antemano"*: es exactamente **los criterios de juicio** que el capítulo 7 exigía acordar **antes** de comparar opciones.

### Paso 4 — Revisar, aprobar y versionar 🔴

> **Antes de pasar a la identificación de requisitos de nivel más bajo, el documento de Visión completo Y LOS RESULTADOS DE LA PRIORIZACIÓN se revisan y aprueban POR TODOS LOS INTERESADOS QUE PARTICIPARON DE LA ELICITACIÓN.**
>
> Finalmente, la Visión aprobada **junto con la matriz de priorización se ingresa a la base de gestión de configuración y se etiqueta como "Aprobado – Iteración X".**

> ⚠️ **Cruce con la cátedra.** Tres cosas de este paso:
>
> **1. Los mismos que elicitaron son los que aprueban.** No es un comité distinto que revisa después.
> **2. Se aprueba la priorización, no solo el contenido.** El acuerdo incluye el orden, no solo la lista.
> **3. Queda versionado y etiquetado.** Eso es la **línea base** del capítulo 6 — la instantánea contra la cual se comparan los cambios posteriores.

### Paso 5 — El taller de casos de uso 🔴

> **El MISMO grupo de interesados se reúne en un TALLER DE CASOS DE USO para definir los requisitos funcionales del sistema.**

Y el detalle de cómo se trabaja:

```
   · el grupo inicial de ACTORES y CASOS DE USO se deriva
     de las características apropiadas
   · se compilan en un MODELO DE CASOS DE USO y se
     ilustran en diagramas DURANTE LA REUNIÓN, con
     una herramienta
   · se ingresan también DESCRIPCIONES BREVES de cada
     actor y cada caso de uso
   · los resultados se documentan en un RELEVAMIENTO
     DEL MODELO DE CASOS DE USO
   · siguen ALGUNAS REUNIONES DE REVISIÓN con los mismos
     asistentes, hasta llegar a una versión aprobada
```

> ⚠️ **Cruce con la cátedra — este paso es directamente aplicable.** Fijate que **los casos de uso se construyen EN LA REUNIÓN, con los interesados presentes y con la herramienta proyectada** — no los dibuja el analista después en su casa.
>
> Eso cambia lo que el diagrama es: **deja de ser el registro de lo que el analista entendió y pasa a ser el artefacto sobre el cual el grupo se pone de acuerdo.** Y conecta con lo que viste en el capítulo 12: *usamos los modelos para entender la realidad*, no al revés.
>
> Y notá **de dónde salen los casos de uso**: se derivan de las características de la Visión. **La traza hacia arriba queda hecha por construcción.**

### Paso 6 — Lo que no encaja en casos de uso 🔴

> **Las características que NO PUDIERON TRAZARSE a requisitos funcionales en casos de uso** —por ejemplo aquellas que implican requisitos no funcionales, como los de rendimiento— **se revisan de nuevo para compilar un documento de ESPECIFICACIONES SUPLEMENTARIAS.**
>
> Como cualquier otro artefacto formal del proceso, **también se revisa, se aprueba y se controla su versión.**

> ⚠️ **Cruce con la cátedra — esta es la solución más limpia que hay en el libro al problema de dónde van los requisitos no funcionales.**
>
> El mecanismo es elegante: **se intenta trazar cada característica a un caso de uso; lo que no traza, va a un documento aparte.** No se fuerza a los no funcionales dentro de los casos de uso —donde no entran— ni se los pierde.
>
> Y resuelve la debilidad que el capítulo 14 le reconocía a los métodos ágiles: allí los no funcionales *"se recolectan implícitamente"* y no había técnica. Acá **hay un artefacto con nombre y un criterio para poblarlo.**

### Paso 7 — Priorizar los casos de uso

> **Los casos de uso identificados se priorizan según un conjunto de atributos acordados de antemano, EN UNA SESIÓN SEPARADA, por el mismo equipo de requisitos.**
>
> **Los evaluados como de alta prioridad se asignan al ESPECIFICADOR DE REQUISITOS para su detalle.**

> Notá que la priorización se hace **dos veces y en dos niveles**: primero sobre las características de alto nivel, después sobre los casos de uso derivados. Y **solo los prioritarios se detallan** — que es exactamente lo que el capítulo 16 señalaba: *la prioridad decide también cuánto se investiga.*

### Paso 8 — El detalle 🔴

> **El especificador de requisitos, CON ASISTENCIA DE LOS USUARIOS FINALES tanto de clientes externos como internos, describe en detalle los flujos de cada caso de uso** en documentos de especificación separados.
>
> También escribe **los requisitos suplementarios al nivel de detalle necesario para pasarlos a las etapas siguientes** del desarrollo.

**Y si hace falta, se abren sub-especificaciones:**

```
   · descripciones de INTERFAZ DE USUARIO
   · ALGORITMOS DE CONTROL
   · descripciones de SEÑALES digitales y analógicas
```

### Paso 9 — Los casos de prueba, en paralelo 🔴

> **Apenas la primera versión de una especificación está lista, SE PASA A LOS DISEÑADORES DE PRUEBA para que preparen los casos de prueba.**

### Paso 10 — La revisión, con quiénes 🔴

Y acá viene el detalle más aprovechable del proceso entero. **Cada especificación se revisa por un grupo que incluye:**

```
   · clientes EXTERNOS con conocimiento de negocio
   · clientes INTERNOS con conocimiento técnico del dominio
   · el ESPECIFICADOR de requisitos
   · los USUARIOS FINALES que asistieron durante el detalle
   · el ARQUITECTO de software
   · el DISEÑADOR
   · el DISEÑADOR DE PRUEBAS
```

> ⚠️ **Cruce con la cátedra — esta lista es una respuesta directa a algo del capítulo 8.** Allí se decía que **cada atributo de calidad que querés asegurar te dice a quién tenés que sentar en la mesa**: los que prueban aseguran verificabilidad, los desarrolladores aseguran factibilidad.
>
> Acá está la mesa armada: **están los siete, y cada uno atiende un atributo distinto.** El cliente externo valida corrección; el arquitecto y el diseñador, factibilidad e independencia de diseño; el diseñador de pruebas, verificabilidad; los usuarios finales, comprensibilidad y completitud.
>
> Es además una implementación de la **lectura basada en perspectivas** del capítulo 8, sin llamarla así.

### Paso 11 — Aprobación y diseño

> **Tras la aprobación, cada documento se ingresa a la base de gestión de configuración y se etiqueta como "Aprobado – Iteración X". Después, el equipo de diseño empieza a trabajar** en el diseño arquitectónico y detallado.

### Paso 12 — Actualizar y aprobar las pruebas

> **Los casos de prueba se actualizan según los cambios finales de las especificaciones relacionadas, SE REVISAN Y SE APRUEBAN por el equipo de requisitos Y el equipo de pruebas** antes de versionarse y pasarse al equipo de pruebas.

### Y en paralelo, todo el tiempo 🔴

> **Paralelamente a todas las actividades anteriores, el equipo de proyecto TAMBIÉN RECOLECTA CONTINUAMENTE TERMINOLOGÍA EN UN GLOSARIO DEL PROYECTO.**

> ⚠️ **Cruce con la cátedra.** Reparen en esa última línea, que es corta y fácil de saltear: **el glosario no es un paso del proceso — es una actividad continua que corre en paralelo a todo lo demás.**
>
> Es la quinta vez que el libro llega a lo mismo desde un lugar distinto: el capítulo 6 (cambiar el vocabulario del dominio genera cambios grandes en la arquitectura), el capítulo 8 (definir todos los términos es parte de la completitud), el capítulo 10 (las abstracciones del dominio son conjuntos de términos), el capítulo 11 (el glosario es la primera contramedida contra la ambigüedad), y ahora este: **el glosario se construye durante todo el proyecto, no antes ni después.**

---

## El proceso completo, de un vistazo 🔴

```
   ELICITAR ─────────► entrevistas + taller
                       (clientes EXTERNOS con conocimiento
                        de negocio + INTERNOS con
                        conocimiento técnico)
        ↓
   VISIÓN ───────────► características = requisitos de
                       alto nivel
                       (lo que no entra en el alcance
                        SE CONSERVA para el futuro)
        ↓
   PRIORIZAR ────────► por atributos ACORDADOS DE ANTEMANO
        ↓
   REVISAR + APROBAR ► por LOS MISMOS que elicitaron
        ↓             → versionado: "Aprobado – Iteración X"
        ↓
   TALLER DE CASOS ──► actores + casos de uso derivados
   DE USO              DE LAS CARACTERÍSTICAS
                       (se construyen EN LA REUNIÓN)
        ↓
   lo que NO traza ──► ESPECIFICACIONES SUPLEMENTARIAS
   a un caso de uso    (ahí van los no funcionales)
        ↓
   PRIORIZAR los ────► solo los de alta prioridad
   casos de uso        se detallan
        ↓
   DETALLAR ─────────► el especificador CON los usuarios
                       finales
        ↓
   CASOS DE PRUEBA ──► apenas hay primera versión
   (en paralelo)
        ↓
   REVISAR ──────────► 7 perfiles distintos en la mesa
        ↓
   APROBAR ──────────► versionado → empieza el DISEÑO

   ══► y en PARALELO A TODO: el GLOSARIO del proyecto ◄══
```

---

## Preguntas para chequear que quedó

1. ¿Cuánto más cara es la reparación en mantenimiento que en la fase de requisitos?
2. ¿Cuáles son los dos factores en que se apoya la escalada del costo?
3. ¿Qué porcentaje de los errores detectados en pruebas se rastrea a errores de requisitos?
4. ¿Qué es la "fluencia" de requisitos y por qué es distinta de un cambio?
5. ¿Por qué es inevitable adaptar un proceso genérico?
6. ¿Cuáles fueron las tres decisiones centrales al adaptar el proceso?
7. ¿Por qué preparar casos de prueba antes de codificar? ¿Con qué idea del capítulo 8 se conecta?
8. ¿Quiénes participan obligatoriamente de la elicitación y qué aporta cada perfil?
9. ¿Qué es el documento de Visión y qué contiene?
10. ¿Por qué se conservan en la Visión características que no entran en el alcance?
11. ¿Qué dos cosas se aprueban antes de pasar a los requisitos de nivel más bajo?
12. ¿Qué significa etiquetar como "Aprobado – Iteración X" y con qué concepto del capítulo 6 se conecta?
13. ¿Cómo se construyen los casos de uso en el taller? ¿Qué cambia respecto de dibujarlos después?
14. ¿De dónde se derivan los actores y casos de uso? ¿Qué consecuencia tiene para la trazabilidad?
15. ¿Qué pasa con las características que no se pueden trazar a un caso de uso? ¿Por qué es una buena solución?
16. ¿Cuántas veces se prioriza en el proceso y sobre qué?
17. ¿Qué se hace solo con los casos de uso de alta prioridad?
18. Nombrá los siete perfiles que participan de la revisión de cada especificación. ¿Qué atributo de calidad atiende cada uno?
19. ¿Cuándo se preparan los casos de prueba respecto de la especificación?
20. ¿Cuándo se construye el glosario del proyecto? ¿Por qué ese detalle importa?

---

**FIN DEL CAPÍTULO 17 — PARTE 1**

*Sigue en la Parte 2: los veintiséis atributos de calidad de los requisitos, los problemas que encontraron al compararlos entre fuentes, y las relaciones entre atributos —incluyendo los casos en que mejorar uno empeora otro.*
