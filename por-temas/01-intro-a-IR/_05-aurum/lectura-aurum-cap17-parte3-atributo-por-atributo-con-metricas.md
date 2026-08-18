# Lectura en español — Cap. 17 · Parte 3: Atributo por atributo, con métricas

> **Origen.** Capítulo 17, secciones 17.4.1 a 17.5, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Nur Yilmaztürk**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 2.** Se asumen conocidos los veintiséis atributos y los tres tipos de relación entre ellos.

---

## Cómo leer esta parte

Para cada atributo el capítulo da cuatro cosas: **la definición**, **cómo se relaciona con otros**, **qué hace el proceso al respecto** y **cómo lo midieron**.

Lo más aprovechable son **las métricas**: son indicadores simples, casi todos cocientes, que se pueden calcular sobre cualquier entregable sin herramientas especiales. Y **el ejemplo de reescritura del requisito ambiguo** en la sección 2, que es el mejor del libro.

---

## 1. Factible 🔴

> **Un requisito es alcanzable / factible / realizable si y solo si EXISTE AL MENOS UN DISEÑO E IMPLEMENTACIÓN que lo implemente correctamente A UN COSTO DEFINIBLE.**

### Lo que el proceso no cubre 🟡

> **No hay medios particulares recomendados por el proceso para asegurar o medir la factibilidad de todos los tipos de requisitos en una etapa temprana.**

La única actividad relacionada es construir **una prueba de concepto arquitectónica**, que ayuda a determinar si existe una solución que satisfaga los requisitos arquitectónicamente significativos — **pero no cubre todos los requisitos.**

### Las dos preguntas que hay que responder 🔴

Para una empresa industrial con inversión considerable, plazos ajustados y competencia severa, **es vital saber:**

```
   (i)  ¿es TÉCNICAMENTE POSIBLE lograr los requisitos
        identificados?
   (ii) ¿es posible lograrlos DENTRO DE LOS LÍMITES
        impuestos por tiempo y presupuesto?
```

**Cómo resuelven la primera:** **incluyendo a los desarrolladores en las revisiones** de los artefactos de requisitos.

**Y una regla de manejo elegante para lo infactible:**

> En el documento de Visión, la factibilidad no es una calidad de alta prioridad. Pero **si una característica se determina infactible con el conocimiento técnico de hoy, SE ANOTA durante la reunión de revisión para negociarla con los interesados.**
>
> **Si los interesados insisten en mantener el requisito, se lo ANOTA CON "NO INCLUIR EN UNA VERSIÓN INMEDIATA".**
>
> **Los requisitos infactibles PUEDEN QUEDARSE en la Visión, pero NO SE TRAZAN HACIA ADELANTE hacia ningún caso de uso ni requisito de nivel inferior** — al menos hasta la iteración siguiente o hasta que haya una mejora tecnológica en el área.

> ⚠️ **Cruce con la cátedra.** Ese mecanismo es muy bueno y transferible: **no se discute con el interesado ni se borra su pedido. Se lo deja donde está, marcado, y se corta la traza hacia abajo.**
>
> Resuelve las dos cosas a la vez: el interesado no pierde su requisito (y sigue participando), y el equipo no construye sobre algo imposible. **La factibilidad se hace exigible recién en el nivel donde se define el trabajo real** — casos de uso y especificaciones — no en la visión.

### La factibilidad financiera 🟢

Para la segunda pregunta, **preparan escenarios y calculan la duración y el costo del proyecto en cada uno.** Cinco escenarios: **el peor caso posible, el mejor, y tres casos óptimos** que muestran el avance probable, muy probable y más probable.

Los escenarios se diferencian por:

```
   · cantidad de SEMANAS por iteración
   · cantidad de DESARROLLADORES involucrados
   · cantidad de CASOS DE USO identificados para todo
     el sistema
   · cantidad de SEMANAS a gastar en cada caso de uso
   · las CARACTERÍSTICAS de cada desarrollador
```

**Y cómo tratan los no funcionales en el cálculo:**

> **Consideramos nuestros "requisitos suplementarios" COMO FACTORES TÉCNICOS, e incluimos su efecto en los cálculos INDIRECTAMENTE, VÍA LA COMPLEJIDAD DE LOS CASOS DE USO.**
>
> **Finalmente decidimos la complejidad de los casos de uso clasificándolos en una escala de 5 puntos**, donde 5 ilustra la complejidad más alta.

**Qué se hace con el resultado:**

> Al completar los cálculos, **comparamos la situación existente con los resultados de los distintos escenarios, y determinamos SI EL PROYECTO ES DEMASIADO OPTIMISTA** sobre la cantidad y el contenido de los requisitos a cumplir.

**Cuándo se mide:** **al menos una vez al comienzo del proyecto.** Según la volatilidad de los requisitos y los cambios en el entorno, **puede repetirse al comienzo de cada iteración.**

---

## 2. Claro / preciso / significativo 🔴🔴

> **Un requisito es claro / preciso / significativo si y solo si (a) SE USAN CANTIDADES NUMÉRICAS SIEMPRE QUE SEA POSIBLE, y (b) se usan los niveles de precisión apropiados para todas las cantidades numéricas.**
>
> **Mantener un alcance adecuado —proveer una cantidad definida de información, EVITANDO ENUNCIADOS DE MADRE** como *"proveerá un servicio continuo"* o *"asegurará la más alta seguridad del sistema"*— **es vital para la claridad.**

> 🕳️ **"Enunciado de madre"** (*motherhood statement*) — una afirmación con la que nadie puede estar en desacuerdo y que por eso mismo no dice nada. *"El sistema debe ser confiable."* Como decir que la maternidad es buena. Volvé al camino.

### El ejemplo de reescritura 🔴🔴

Y acá viene el mejor ejemplo del capítulo, tomado de un proyecto real.

**Lo que el departamento de comercialización pidió originalmente:**

```
   "El sistema debe tener un tiempo de cómputo rápido."
```

**Las preguntas que el equipo de desarrollo no podía responder:**

> **"¿Cuán rápido es suficientemente rápido?"**
>
> **"Podemos tener varias configuraciones del sistema — ¿de cuál estamos hablando? La velocidad del tiempo de cómputo DIFIERE según si es un sistema monolítico o uno distribuido; según si es un sistema solo de medición o un sistema de control completo."**

**Y en qué se convirtió el requisito:**

```
   "Un cómputo completo de las funciones principales,
    desde el momento en que se recibe la señal TCP/IP
    del Sistema de Medición Base hasta que se emite una
    salida (comunicación externa no incluida),
    para un sistema de medición de planitud de nodo único
    de un laminador reversible con 64 zonas de medición,
    NO DEBE SER MAYOR A 6,0 MILISEGUNDOS."
```

**Y el diagnóstico de los autores:**

> **El problema con este requisito no era solo que estuviera enunciado ambiguamente, SINO TAMBIÉN QUE FALTABA MUCHÍSIMA INFORMACIÓN VITAL.**
>
> **En consecuencia podemos inferir que LA INCOMPLETITUD PUEDE LLEVAR A REQUISITOS POCO CLAROS — o dicho de otro modo, LA COMPLETITUD PUEDE AUMENTAR LA POSIBILIDAD de tener requisitos claros.**

> ⚠️ **Cruce con la cátedra — este ejemplo es el mejor material que hay en el libro para entender qué significa "verificable".** Comparalo con lo que viste antes:
>
> El **capítulo 3** decía que *"debe ser lo más rápido posible"* no es un requisito hasta tener métrica. El **capítulo 8** decía que verificable significa que existe un proceso para chequear si se cumple. El **capítulo 11** decía que la ambigüedad de ingeniería está en lo que se dio por supuesto del dominio.
>
> **Acá están las tres cosas en un solo caso.** Y notá qué hizo falta agregar para pasar de una versión a otra:
>
> - **el número** (6,0 ms) → verificabilidad
> - **los límites de la medición** (desde qué señal hasta qué salida, qué se excluye) → no ambigüedad
> - **la configuración exacta** (nodo único, laminador reversible, 64 zonas) → completitud
>
> **Ninguno de los tres sobra, y ninguno se le podía ocurrir a alguien que no conociera el dominio.** Es la mejor ilustración de por qué el analista necesita al experto.

### Lo que aporta el proceso 🟡

> **Provee PLANTILLAS Y EJEMPLOS que dan estructura y guía para el contenido de distintos tipos de requisito**, y **recomienda revisar los artefactos contra PUNTOS DE CONTROL** que incluyen criterios para cumplir el atributo.

Algunos de esos puntos de control para claridad:

```
   · está claro CÓMO Y CUÁNDO empieza y termina el flujo
     de eventos del caso de uso
   · está claro QUIÉN DESEA realizar el caso de uso
   · el PROPÓSITO del caso de uso también está claro
   · las INTERACCIONES DEL ACTOR y la información
     intercambiada están claras
   · el modelo presenta claramente el COMPORTAMIENTO
     del sistema
   · la introducción del modelo provee un PANORAMA CLARO
     del propósito y la funcionalidad del sistema
```

> ⚠️ **Cruce con la cátedra.** Esos seis puntos son **una lista de verificación lista para usar sobre un modelo de casos de uso.** Se corren en cinco minutos sobre cualquier entregable, y las tres primeras encuentran problemas reales casi siempre: *¿cuándo empieza?*, *¿cuándo termina?*, *¿quién lo quiere?*

**Cómo lo aseguraron en la práctica:** no midieron la claridad directamente, sino que **aseguraron un acuerdo común sobre su existencia mediante revisiones** por los interesados: los expertos del dominio, los representantes de los clientes externos que compraron el sistema, y los representantes de los clientes internos que usan los requisitos en los pasos siguientes.

---

## 3. Completo 🔴

> **Un requisito individual es completo si ES CAPAZ DE MANTENERSE SOLO cuando se lo separa de otros requisitos y NO NECESITA AMPLIFICACIÓN ADICIONAL.**

**Y un conjunto es completo si y solo si:**

```
   (a) incluye TODOS los requisitos significativos —de
       funcionalidad, rendimiento, restricciones de
       diseño, atributos o interfaces externas
   (b) involucra TODAS LAS RESPUESTAS del software A TODAS
       LAS CLASES REALIZABLES DE DATOS DE ENTRADA en todas
       las situaciones realizables — incluyendo respuestas
       a valores de entrada VÁLIDOS E INVÁLIDOS
   (c) todas las figuras, tablas y diagramas están
       ETIQUETADAS Y REFERENCIADAS; TODOS LOS TÉRMINOS
       ESTÁN DEFINIDOS; se proveen las unidades de medida
   (d) NINGUNA sección está marcada como "a determinar"
   (e) cubre todas las asignaciones del nivel superior
   (f) NO debe incluir situaciones que no se van a
       encontrar ni capacidades innecesarias
```

> ⚠️ **Cruce con la cátedra.** La condición (b) es la más exigente y la más olvidada: **todas las respuestas a todas las entradas, incluyendo las inválidas.** Un caso de uso que solo describe el camino feliz no cumple esta condición.
>
> Y la (c) vuelve a traer **la definición de todos los términos** como componente de la completitud — la sexta vez en la serie.
>
> La (f) es la que menos se espera: **un conjunto con cosas de más tampoco es completo.** Completitud no es "cuanto más, mejor".

### Cómo se logra 🔴

Cuatro mecanismos que el capítulo destaca:

**1. Organizar según una plantilla.** Ayuda a **entender la estructura de una funcionalidad y VUELVE MÁS FÁCIL IDENTIFICAR SI FALTA ALGO.**

**2. Ejecutar los requisitos** vía prototipado o simulación. Le da a los interesados oportunidad de validar **y de reflexionar sobre los que faltan.**

**3. Enfocarse en las TAREAS DEL USUARIO en vez de en las funciones del sistema.** Y acá está el argumento a favor de los casos de uso:

> **Enfocarse en las tareas del usuario durante la elicitación EVITA PASAR POR ALTO REQUISITOS, así como INCLUIR REQUISITOS QUE NO SON NECESARIOS. Para ese fin, USAR CASOS DE USO PARA CAPTURAR REQUISITOS ES EL MEDIO IDEAL.**
>
> Además, **la naturaleza SEMI-FORMAL de los casos de uso vuelve fácil para los interesados leer y entender un documento, y eventualmente DAR RETROALIMENTACIÓN SOBRE LAS PARTES QUE FALTAN.**

**4. El desarrollo iterativo.** **Cada iteración resulta en una versión ejecutable, lo que facilita identificar los requisitos faltantes** para atenderlos en las siguientes.

### Lo que agregaron en la práctica 🔴

> Aseguramos que la versión producida al final de una iteración **se ejecutara y se probara continuamente EN UN ENTORNO QUE SIMULABA UN ENTORNO TÍPICO DE CLIENTE FINAL.**
>
> **VER ESCENARIOS DE LA VIDA REAL AUMENTÓ EL NIVEL DE INTERÉS, LA CONCENTRACIÓN Y LA COMPRENSIÓN DE LOS INTERESADOS**, y así **abrió discusiones nuevas que llevaron a identificar requisitos nuevos, insuficientemente descritos o faltantes.**

> ⚠️ **Cruce con la cátedra.** Esa observación es útil y va más allá del contexto: **la gente presta más atención a lo que se parece a su realidad.** Mostrar el sistema con datos y escenarios reconocibles produce más hallazgos que mostrarlo con datos de prueba.

### Las métricas de completitud 🔴

Y acá vienen los indicadores concretos:

| Métrica | Qué mide y qué indica |
|---|---|
| **Casos de uso trazados hacia atrás a características ÷ total de casos de uso** | **Completitud del modelo de casos de uso.** Un valor bajo indica **casos de uso SIN ORIGEN** |
| **Requisitos suplementarios trazados a características ÷ total de requisitos suplementarios** | **Completitud de las especificaciones suplementarias.** Un valor bajo indica **requisitos no funcionales sin origen** |
| **Cantidad de "incompletos" en una especificación de caso de uso** | Se reconocen como incompletos: *a determinar, a especificar, no definido, no determinado*. Son **indicadores de riesgo** |
| **Cantidad de "incompletos" en una especificación suplementaria** | Ídem |

**Y la regla de manejo de los incompletos, que es muy buena:**

> El proceso **impone MINIMIZAR el uso de incompletos, PERMITE su uso SI Y SOLO SI van seguidos de información sobre CUÁNDO Y POR QUIÉN se va a atender la parte incompleta, y CONSIDERA ALTO RIESGO para el proyecto SI LA CANTIDAD DE INCOMPLETOS NO DISMINUYÓ DESPUÉS DE DOS ITERACIONES CONSECUTIVAS.**

> ⚠️ **Cruce con la cátedra — esta regla es directamente robable.** Tiene tres partes y las tres son buenas:
>
> **1. Se permite escribir "a determinar".** No se finge que todo está resuelto.
> **2. Pero solo con dueño y fecha.** *"A determinar"* solo no vale; *"a determinar por el área de finanzas antes del 15/09"* sí.
> **3. Y se mide la tendencia, no el número.** Que haya incompletos es normal; **que no bajen en dos iteraciones es la señal de alarma.**
>
> Y la primera métrica —casos de uso sin origen— es el control de trazabilidad más simple que existe: **recorrer los casos de uso y preguntar de qué característica sale cada uno.** Los huérfanos son sospechosos, exactamente como decía el capítulo 5.

---

## 4. Conciso 🟡

> **Un requisito o conjunto es conciso si ES TAN CORTO COMO SEA POSIBLE SIN AFECTAR ADVERSAMENTE NINGUNA OTRA CALIDAD.**

**Las tres cosas que lo comprometen:**

```
   1. EXCEDERSE CON LA COMPLETITUD aumenta el tamaño
      y pone en peligro la concisión
   2. incluir CÓMO se cumple el requisito en términos de
      diseño o implementación → información innecesaria
      → menos conciso
   3. la REDUNDANCIA, que los especificadores usan a
      menudo para aumentar la comprensibilidad
```

Sobre el segundo punto, la regla:

> **Un requisito, sin importar en qué formato esté, DEBE ENUNCIAR SOLO LO QUE SE REQUIERE Y NO CÓMO SE VA A CUMPLIR.**

**Y una observación honesta del caso:**

> **Los dos primeros proyectos probaron que la concisión del modelo de casos de uso o de las especificaciones NO CONSTITUÍA UN RIESGO ALTO** para el proyecto ni para la calidad del producto final. **En consecuencia, NO SE LA ABORDÓ en los proyectos siguientes.**

> Ese último párrafo es un buen ejemplo de la tesis del capítulo: **se mide, se ve que no es un problema en este contexto, y se deja de gastar esfuerzo ahí.** No todos los atributos importan igual en todos los proyectos.

---

## 5. Correcto 🟡

> **Un requisito es correcto si DESCRIBE CON EXACTITUD UNA FUNCIONALIDAD A ENTREGAR.** Un conjunto es correcto si y solo si **cada requisito enunciado es uno que el software debe cumplir.**

**Las relaciones que señalan:**

```
   · EJECUTAR los requisitos permite a los interesados
     VALIDARLOS → asegura corrección
   · los requisitos INCONSISTENTES impiden establecer
     corrección: es difícil saber cuál de los que están
     en conflicto es el correcto, SI ES QUE ALGUNO LO ES
   · un requisito es correcto SI ES NECESARIO
   · un requisito es correcto SI PUEDE TRAZARSE HACIA
     ATRÁS a su fuente de nivel superior — naturalmente,
     A CONDICIÓN DE QUE ESA FUENTE SEA CORRECTA
```

**Y una crítica al proceso estándar:**

> **Sugiere involucrar a los usuarios finales en las revisiones SOLO SI ES POSIBLE.** Provee guías para generar casos de prueba, **pero deja su preparación hasta que se programa el trabajo de implementación. Tampoco requiere revisar los casos de prueba.**
>
> **Al recomendar el uso de herramientas que no proveen facilidades de chequeo de consistencia, EL PROCESO OBSTACULIZA el logro de la corrección.**

> ⚠️ **Cruce con la cátedra.** La última condición es la más interesante: **un requisito es correcto si se traza a una fuente correcta.** La corrección **se hereda hacia abajo** — y eso significa que un error en el nivel alto contamina todo lo que cuelga de él.
>
> Es la misma advertencia que el capítulo 9 hacía sobre los enfoques basados en metas: *los errores en las metas de alto nivel cometidos temprano tienen un efecto de arrastre mayor y perjudicial.*

---

## 6. Independiente del diseño 🔴

> **Un requisito o conjunto es independiente del diseño si y solo si EXISTE MÁS DE UN DISEÑO E IMPLEMENTACIÓN que lo implemente correctamente.**

**Lo que el proceso aporta:** solo **información breve sobre cómo distinguir el "qué" del "cómo"** en las guías del modelo de casos de uso. Plantillas y ejemplos **útiles pero no suficientes.**

**Y la solución que agregaron:**

> Para asegurar la independencia de diseño, **se impone INCLUIR AL ARQUITECTO DE SOFTWARE Y A LOS DISEÑADORES en la revisión de los artefactos de requisitos, PARA QUE PUEDAN SEÑALAR AQUELLOS DETALLES QUE PUEDEN LIMITAR SU CAPACIDAD DE CONSIDERAR ALTERNATIVAS DE DISEÑO** y sintetizar la más óptima.

> ⚠️ **Cruce con la cátedra — esta es la mejor definición operativa de "qué, no cómo" que hay en el libro.**
>
> En vez de dar una regla abstracta, da **un test**: *¿existe más de un diseño que cumpla este requisito?* Si la respuesta es no —si solo hay una manera de implementarlo— **el requisito ya contiene una decisión de diseño.**
>
> Y la solución práctica es igual de buena: **poner al arquitecto en la revisión y que él diga qué le está atando las manos.** El analista no siempre puede ver que escribió una decisión de diseño; el que va a diseñar sí.

---

## 7. Consistencia externa e interna 🔴

### Externa

> **Un conjunto es externamente consistente si y solo si NINGÚN REQUISITO ENTRA EN CONFLICTO CON DOCUMENTACIÓN DE PROYECTO YA ESTABLECIDA COMO LÍNEA BASE.**

**Por qué eligieron esa definición** y no la tradicional (cumplimiento con los documentos precedentes):

```
   (i)  para manejar las inconsistencias como parte de
        la GESTIÓN FORMAL DE CAMBIOS
   (ii) para EXTENDER el contexto de inconsistencia
        externa MÁS ALLÁ de los documentos de requisitos
        de alto nivel: incluir el plan de proyecto,
        una versión de la iteración anterior, etc.
```

**Y la relación con la trazabilidad, que es directa:**

> **Si hay un vínculo desde cada requisito de bajo nivel hacia un requisito de nivel superior —es decir, TRAZABLE HACIA ATRÁS— entonces el conjunto ES EXTERNAMENTE CONSISTENTE con los requisitos de alto nivel.**
>
> **De la misma manera, si hay un vínculo desde cada requisito hacia al menos un requisito de nivel inferior o hacia otro artefacto de desarrollo —diagrama de secuencia, diagrama de clases, caso de prueba— es decir, TRAZABLE HACIA ADELANTE — entonces está en acuerdo** con lo que se está desarrollando.

### Interna

> **Un conjunto es internamente consistente si y solo si NINGÚN SUBCONJUNTO de requisitos entra en conflicto. SE USA EL MISMO TÉRMINO PARA EL MISMO ÍTEM en todos los requisitos del conjunto.**

**Lo que la afecta:**

```
   · si un conjunto NO ESTÁ ORGANIZADO, puede ser difícil
     identificar las inconsistencias
   · la REDUNDANCIA que usamos para aumentar la
     legibilidad CREA RIESGO: al alterar una aparición
     de un requisito PODEMOS OLVIDARNOS DE LAS OTRAS
     → se puede reducir usando REFERENCIAS CRUZADAS
```

**Y los cuatro tipos de inconsistencia** que identifican: **comportamiento en conflicto, términos en conflicto**, y otros dos.

> ⚠️ **Cruce con la cátedra.** La segunda parte de la definición de consistencia interna es la más olvidada: ***"se usa el mismo término para el mismo ítem en todos los requisitos"***. Eso es consistencia **terminológica**, y es la que rompe el glosario cuando no existe.
>
> Y el mecanismo del olvido está bien descrito: **repetís para que se lea mejor, cambiás una aparición, te olvidás de las otras, y ahora el documento se contradice consigo mismo.** La salida —referencias cruzadas en vez de repetir— es la misma que la tensión comprensible/no redundante de la Parte 2.

---

## 8. Modificable 🟡

> **Un conjunto es modificable si y solo si SU ESTRUCTURA Y ESTILO son tales que cualquier cambio puede hacerse FÁCIL, COMPLETA Y CONSISTENTEMENTE, MANTENIENDO esa estructura y estilo.**

**Por qué importa tanto —cuatro razones:**

```
   (i)   los requisitos CAMBIAN
   (ii)  cambian cuestiones distintas de los requisitos
         pero que LOS AFECTAN
   (iii) los requisitos EVOLUCIONAN
   (iv)  los requisitos pueden estar MAL ENUNCIADOS por
         razones inadvertidas varias
```

**Y las cinco condiciones que la facilitan:**

```
   · los requisitos están ORGANIZADOS de manera coherente
     y fácil de usar
   · la REDUNDANCIA se mantiene al mínimo
   · se usan REFERENCIAS CRUZADAS donde hace falta
   · los requisitos están ETIQUETADOS ÚNICAMENTE, para
     facilitar la trazabilidad en ambos sentidos
   · están ALMACENADOS ELECTRÓNICAMENTE
```

---

## 9. Necesario 🔴

> **Un requisito es necesario si es UNA CAPACIDAD ESENCIAL, una característica física o un factor de calidad del producto o proceso. SI SE LO REMUEVE, VA A EXISTIR UNA DEFICIENCIA que no puede cumplirse por otras capacidades.**

**Y el test que propone la literatura:**

> **Una manera común de decidir la necesidad es TRAZAR EL REQUISITO HACIA ATRÁS HASTA SU ORIGEN** — por ejemplo, trazar un caso de uso hasta una característica o una necesidad de la visión. **SI NO SE PUEDE TRAZAR, PUEDE QUE NO SEA NECESARIO.**

**La tensión con la priorización**, que ya viste en la Parte 2, se resuelve con un esquema de tres clases:

| Clase | Definición |
|---|---|
| **Esencial** | Los que **deben proveerse para que el producto final sea aceptado** → necesarios |
| **Condicional** | Los que **mejorarían el producto pero no lo volverían inaceptable si faltan** |
| **Opcional** | Los que **pueden o no valer la pena** → no necesarios |

### Las métricas de necesidad 🔴

| Métrica | Qué indica |
|---|---|
| **Secciones de casos de uso trazadas a características ÷ total de secciones** | **Un valor distinto de 1 indica flujos, requisitos especiales, pre o post-condiciones QUE NO SE REQUIEREN** |
| **Requisitos suplementarios trazados a características ÷ total** | **Un valor distinto de 1 indica requisitos no funcionales INNECESARIOS** |

> ⚠️ **Cruce con la cátedra.** Notá la diferencia con la métrica de completitud de la sección 3: **es el mismo cociente, leído al revés.**
>
> - Para **completitud** preguntabas: *¿hay características que no llegaron a ningún caso de uso?* (falta algo)
> - Para **necesidad** preguntás: *¿hay partes de casos de uso que no vienen de ninguna característica?* (sobra algo)
>
> **Un solo cruce de trazas responde las dos preguntas.** Es el ejercicio de revisión de mejor relación costo-beneficio de todo el libro.

---

## 10. Organizado 🟡

> **Un conjunto está organizado si y solo si SUS CONTENIDOS ESTÁN DISPUESTOS DE MODO QUE LOS LECTORES PUEDAN UBICAR FÁCILMENTE LA INFORMACIÓN, y las relaciones lógicas entre secciones adyacentes SEAN APARENTES.**

**Lo que aporta el proceso:**

> Recomienda organizar los requisitos funcionales **usando casos de uso. En vez de una lista tradicional de viñetas, sugiere organizarlos DE UNA MANERA QUE CUENTE LA HISTORIA de cómo alguien puede usar el producto final.**

---

## 11. Priorizado 🟡

Las tres formas de priorización, cada una con su definición:

| Forma | Qué indica el identificador asignado |
|---|---|
| **Por importancia relativa** | **Cuán esencial es incluirlo en un producto particular** |
| **Por estabilidad relativa** | **La estabilidad de ese requisito particular** |
| **Por versión** | **En qué versión del producto se va a satisfacer** |

### El problema estructural y su solución 🔴

**El problema:**

> **Tradicionalmente se sugiere establecer el ordenamiento EN LA ORGANIZACIÓN Y LA ESTRUCTURA del conjunto.** En consecuencia, **un conjunto organizado para ser modificable tendría un impacto negativo** sobre esta característica.

**La solución que adoptaron:**

> Se sugiere **EXTRAER los requisitos del conjunto HACIA UNA PLANILLA, ejecutar los ordenamientos según los atributos elegidos de antemano, y guardar la matriz EN HOJAS SEPARADAS, UNA POR CADA ORDENAMIENTO.**
>
> De esta manera el proyecto **podía mantener las organizaciones originales del modelo de casos de uso, las especificaciones suplementarias y la visión, MIENTRAS AL MISMO TIEMPO PODÍA CONSULTAR LOS ORDENAMIENTOS CUANDO HICIERA FALTA** — por ejemplo para replanificar al comienzo de una iteración.

**Y el beneficio adicional:**

> También era posible **generar COMBINACIONES DISTINTAS de ordenamientos** en tablas resumen, según el objetivo de la planificación. Por ejemplo, si se decidía desarrollar los casos de uso con beneficios críticos **y estabilizar la arquitectura**, hacía falta ver la matriz ordenada **primero por importancia relativa y después por estabilidad.**

**Los atributos que registran de cada caso de uso:**

```
   estado · beneficio · esfuerzo · riesgo técnico ·
   impacto arquitectónico · estabilidad · prioridad ·
   agendado para la iteración actual · responsable
```

> ⚠️ **Cruce con la cátedra.** La solución es simple y elegante: **separar el documento del ordenamiento.** El documento se organiza como conviene leerlo; la planilla se ordena como conviene decidir. Y como la planilla se puede reordenar, **se pueden hacer preguntas distintas sobre el mismo conjunto.**
>
> Notá además el atributo **impacto arquitectónico** en la lista: es el **valor arquitectónico** que el capítulo 13 señalaba como el tipo de valor que más se olvida, acá convertido en columna.

---

## 12. Trazabilidad 🔴

### Hacia adelante

> **Un requisito es trazable hacia adelante si y solo si está escrito de manera que FACILITE SU REFERENCIA en documentación de desarrollo o mejora FUTURA.**

**Los métodos comunes de trazabilidad explícita:**

```
   · numerar cada párrafo JERÁRQUICAMENTE
   · numerar cada requisito con un NÚMERO ÚNICO
   · usar una CONVENCIÓN para indicar un requisito
   · usar una herramienta para extraer y numerar
     únicamente todas las oraciones que cumplan
     esa convención
```

**Y una distinción importante:**

> **Además de la trazabilidad explícita, HAY CIERTA CANTIDAD DE TRAZABILIDAD IMPLÍCITA EN TODO PROCESO DE DESARROLLO.** En el caso de este proceso se logra vía:

```
   (i)   CONVENCIONES DE NOMBRES
   (ii)  la construcción de MAPEOS entre los modelos
   (iii) las RELACIONES entre los ítems de los modelos
   (iv)  la creación de PERSPECTIVAS distintas que
         ilustran cómo los elementos de un modelo
         satisfacen las demandas implícitas en otro
```

### Hacia atrás

> **Un requisito o conjunto es trazado / trazable hacia atrás si EL ORIGEN del requisito, o de cada requisito del conjunto, ES CLARO.**

### Las métricas de trazabilidad hacia atrás 🔴

Y esta es la tabla más completa de métricas del capítulo:

| Métrica | Qué indica un valor distinto de 1 |
|---|---|
| **Casos de uso trazados a características ÷ total** | Casos de uso pobremente trazados, o **sin ningún origen** |
| **Secciones de especificación trazadas ÷ total de secciones** | **Secciones —precondiciones, postcondiciones, requisitos especiales— sin origen** |
| **Requisitos suplementarios trazados ÷ total** | Requisitos suplementarios **sin origen** |
| **Diagramas de secuencia trazados a secciones de casos de uso ÷ total de diagramas de secuencia** | **Elementos de diseño sin origen.** Puede sugerir **inconsistencias entre lo que el cliente final espera y lo que se está desarrollando** |
| **Diagramas de clases trazados ÷ total de diagramas de clases** | Ídem |
| **Casos de prueba funcionales trazados a escenarios de casos de uso ÷ total** | **Casos de prueba sin origen.** Significa además que **NO SE PROBARON funcionalidades necesarias y/o SE IMPLEMENTÓ FUNCIONALIDAD EXTRA sin informar primero al equipo de requisitos** |

> ⚠️ **Cruce con la cátedra.** La última fila es la más reveladora. Un caso de prueba que no traza a ningún caso de uso significa una de dos cosas, **y las dos son problemas:**
>
> - **alguien construyó algo que nadie pidió** (funcionalidad extra), o
> - **el caso de uso existía pero nunca se documentó**
>
> Y notá que la métrica **detecta el problema desde el lado de las pruebas**, que es un lugar donde nadie lo busca. Es un buen ejemplo de que la trazabilidad no sirve solo para rastrear hacia atrás: **sirve para descubrir lo que se coló.**

---

## 13. No ambiguo 🔴🔴

> **Un requisito o conjunto es no ambiguo si LECTORES DISTINTOS CON TRASFONDOS SIMILARES pudieran extraer UNA SOLA INTERPRETACIÓN** del requisito o de cada requisito del conjunto.

### El diagnóstico sobre UML 🔴

Y acá viene una crítica que vale la pena tener:

> **Este es un proceso basado en UML. UML TIENE NOTACIÓN LIMITADA para expresar distintos tipos de requisitos. De hecho, SOLO AYUDA A VISUALIZAR LOS ACTORES Y LOS CASOS DE USO** que constituyen los requisitos funcionales de bajo nivel.
>
> **UML NO PROVEE SOPORTE PARA DETALLAR LOS CASOS DE USO.** Aunque se sugiere usar diagramas de secuencia para mostrar cómo un actor interactúa con un caso de uso, o diagramas de actividad y de estados para describir uno solo, **EL MEDIO COMÚN PARA DESCRIBIR CASOS DE USO ES EL LENGUAJE NATURAL.**
>
> Además, **los casos de uso NO son los únicos requisitos** de un producto: la Visión y las Especificaciones Suplementarias **también se crean en lenguaje natural. Y el lenguaje natural tiene ambigüedad inherente.**

**Y la crítica a los puntos de control:**

> El proceso **define un vocabulario común para disminuir la ambigüedad entre los miembros del equipo, y recomienda puntos de control durante la revisión. PERO ESOS PUNTOS DE CONTROL SON DEMASIADO GENERALES E INSUFICIENTES** para asegurar un nivel satisfactorio de no ambigüedad.

> ⚠️ **Cruce con la cátedra — esta observación es importante y muchos la pasan por alto.** Dice, con todas las letras: **UML te da los actores y los casos de uso, y ahí se termina.** Todo lo demás —los flujos, las precondiciones, los requisitos no funcionales, la visión— **es texto en lenguaje natural, con toda su ambigüedad.**
>
> La consecuencia práctica: **dibujar bien el diagrama no te protege.** El diagrama es la parte chica; el grueso del contenido —y del riesgo de ambigüedad— está en la descripción textual que lo acompaña.
>
> Es lo mismo que el capítulo 11 decía al advertir que formalizar no detecta ambigüedades, y lo que el capítulo 2 admitía sobre la imprecisión como debilidad reconocida de los casos de uso.

### Lo que sí funcionó 🔴

Los dos medios principales que adoptaron:

```
   · PARTICIPACIÓN ACTIVA de todos los tipos de interesado
     en la elicitación y la revisión
   · PREPARACIÓN DE LOS CASOS DE PRUEBA EN PARALELO
     a la preparación de los casos de uso
```

**Y la lista de frases débiles** que reconocen y buscan explícitamente:

```
   flexible · tolerante a fallas · adecuado ·
   según corresponda · maximizar · minimizar ·
   en un momento dado · hasta

   y las OPCIONES, que le dan al desarrollador libertad
   de satisfacer el requisito de más de una manera:
   puede · podría · opcionalmente
```

> **Durante las reuniones de revisión SE HACEN CHEQUEOS PARA DETECTAR EL USO DE ESTAS PALABRAS.**

### Las métricas de no ambigüedad 🔴

| Métrica | Qué indica |
|---|---|
| **Frases débiles + opciones en una especificación de caso de uso** | **Un valor distinto de CERO indica ambigüedad** |
| **Frases débiles + opciones en una especificación suplementaria** | Ídem |

> ⚠️ **Cruce con la cátedra — esta es la métrica más simple y más usable de todo el libro.** El valor deseado es **cero**, y se calcula con Ctrl+F.
>
> Es la misma técnica que el capítulo 8 describía para las herramientas automáticas de detección de ambigüedad, y el capítulo 11 recomendaba como primera estrategia. **Acá está la lista concreta**, y notá que incluye dos familias distintas:
>
> - **frases débiles** — no dicen cuánto (*adecuado, flexible, minimizar*)
> - **opciones** — no dicen si es obligatorio (*puede, podría, opcionalmente*)
>
> La segunda familia es la que más se cuela: *"el sistema podría enviar una notificación"* parece un requisito y no obliga a nada.

---

## 14. Comprensible 🔴

> **Un requisito o conjunto es comprensible si TODAS LAS CLASES DE LECTORES pueden comprender fácilmente su significado CON UN MÍNIMO DE EXPLICACIÓN.**

**Las relaciones que señalan:**

```
   · un requisito NO AMBIGUO es más claro y por lo tanto
     MÁS COMPRENSIBLE
   · PERO si la no ambigüedad se logra CON NOTACIONES
     FORMALES, la comprensibilidad POR LOS INTERESADOS
     NO TÉCNICOS DISMINUYE
   · la REDUNDANCIA aumenta la legibilidad y por lo tanto
     puede aumentar la comprensibilidad
   · ES MÁS FÁCIL COMPRENDER UN COMPORTAMIENTO VIÉNDOLO
     EN ACCIÓN que leyendo sobre él en un documento
     → la EJECUTABILIDAD mejora la comprensibilidad
   · ORGANIZAR según un estándar o plantilla la aumenta
```

**Y el hallazgo propio:**

> **Nuestras experiencias ilustraron que ORGANIZAR LOS REQUISITOS FUNCIONALES USANDO CASOS DE USO LLEVA A MAYOR COMPLETITUD Y MEJOR ENTENDIMIENTO de los requisitos.**

**Cómo lo aseguraron:**

> Como **todos los tipos de interesado** —representantes de usuarios finales, de compradores reales del sistema, arquitecto, diseñador, **y quienes hacen la instalación y el mantenimiento**— toman parte de la revisión, **los problemas de comprensión pueden revelarse y resolverse fácilmente.**

---

## 15. Conclusiones del capítulo 🔴

> Las generaciones tempranas del producto **se migraron a una plataforma basada en Java**, y la empresa **enfrentó la necesidad de cambiar su manera de trabajar para SEGUIR PROVEYENDO VALOR a sus clientes y asegurar su satisfacción DE MANERA CONTROLADA.**
>
> **En consecuencia adoptó el Proceso Unificado DE MANERA ÁGIL**, principalmente manteniendo:

```
   · participación ACTIVA Y FUERTE de interesados que
     incluyen clientes externos E INTERNOS
   · preparación de los CASOS DE PRUEBA ANTES DE CODIFICAR
   · pruebas CONTINUAS durante el desarrollo
```

> **El proceso resultante se aplicó en TRES PROYECTOS y presentó resultados satisfactorios.**

---

## Mapa de la Parte 3

```
   FACTIBLE ─────────► lo infactible SE QUEDA en la visión,
                       marcado, pero NO SE TRAZA hacia abajo
                       + escenarios de costo (peor, mejor,
                         3 óptimos)

   CLARO ────────────► ══► EL EJEMPLO ◄══
                       "debe tener tiempo de cómputo rápido"
                            ↓ se convierte en
                       "...no debe ser mayor a 6,0 ms"
                       + límites de la medición
                       + configuración exacta
                       → número (verificable) + límites
                         (no ambiguo) + configuración
                         (completo)

   COMPLETO ─────────► incluye respuestas a entradas
                       INVÁLIDAS · todos los términos
                       DEFINIDOS · nada "a determinar"
                       · NADA DE MÁS
                       métrica: casos de uso SIN ORIGEN
                       regla de los "a determinar":
                       permitidos CON DUEÑO Y FECHA;
                       alarma si no bajan en 2 iteraciones

   INDEPENDIENTE ────► TEST: ¿existe más de un diseño que
   DEL DISEÑO          lo cumpla? Si no → ya contiene
                       una decisión de diseño
                       solución: el ARQUITECTO en la revisión

   NECESARIO ────────► métrica: partes de casos de uso
                       SIN ORIGEN
                       (el MISMO cruce que completitud,
                        leído al revés)

   PRIORIZADO ───────► sacar los requisitos a una PLANILLA
                       y ordenar ahí, para no romper la
                       organización del documento

   TRAZABILIDAD ─────► métrica reveladora: casos de prueba
                       sin origen = se construyó algo que
                       nadie pidió, o el caso de uso nunca
                       se documentó

   NO AMBIGUO ───────► ⚠ UML solo da actores y casos de uso;
                       TODO LO DEMÁS es lenguaje natural
                       métrica: frases débiles + opciones
                       → el valor deseado es CERO
                       débiles: adecuado, flexible, minimizar
                       opciones: puede, podría, opcionalmente
```

---

## Preguntas para chequear que quedó

1. Definí factible. ¿Cuáles son las dos preguntas que hay que responder?
2. ¿Qué se hace con un requisito infactible que los interesados quieren conservar?
3. ¿Por qué la factibilidad se exige más en los niveles bajos que en la visión?
4. ¿Cómo se incorporan los requisitos no funcionales al cálculo de costo?
5. ¿Qué es un "enunciado de madre" y por qué es un problema?
6. Tomá el requisito "el sistema debe tener un tiempo de cómputo rápido": ¿qué preguntas no podía responder el equipo?
7. En la versión reescrita, ¿qué aporta el número, qué aportan los límites de la medición y qué aporta la configuración?
8. ¿Por qué la incompletitud lleva a requisitos poco claros?
9. Nombrá tres de los puntos de control de claridad sobre un modelo de casos de uso.
10. ¿Qué exige la condición (b) de la completitud de un conjunto? ¿Por qué un caso de uso con solo el camino feliz no la cumple?
11. ¿Por qué un conjunto con requisitos de más tampoco es completo?
12. ¿Por qué enfocarse en las tareas del usuario evita a la vez omitir e incluir de más?
13. ¿Qué efecto tuvo mostrar el sistema en un entorno que simulaba el del cliente final?
14. Explicá la regla de los "a determinar" en sus tres partes.
15. ¿Qué tres cosas comprometen la concisión?
16. ¿Por qué dejaron de atender la concisión después de dos proyectos?
17. ¿Por qué un requisito es correcto si se traza a una fuente correcta? ¿Qué riesgo trae eso?
18. ¿Cuál es el test para saber si un requisito es independiente del diseño?
19. ¿Cómo se asegura esa independencia en la práctica y por qué el analista solo no alcanza?
20. ¿Qué relación hay entre trazabilidad y consistencia externa?
21. ¿Cuál es la parte más olvidada de la definición de consistencia interna?
22. ¿Cómo la redundancia genera inconsistencia interna y cuál es la salida?
23. ¿Cuál es el test de necesidad de un requisito?
24. ¿Cómo se relacionan la métrica de completitud y la de necesidad?
25. ¿Cómo resolvieron el conflicto entre modificable y priorizado?
26. ¿Qué significa un caso de prueba que no traza a ningún caso de uso? Nombrá las dos posibilidades.
27. ¿Qué expresa UML y qué no? ¿Qué consecuencia tiene para la ambigüedad?
28. Nombrá cuatro frases débiles y tres opciones. ¿Cuál es el valor deseado de esa métrica?
29. ¿Por qué las "opciones" son especialmente peligrosas?
30. ¿Por qué es más fácil comprender un comportamiento viéndolo en acción?

---

**FIN DEL CAPÍTULO 17 — PARTE 3**

**FIN DEL CAPÍTULO 17**

*Sigue el capítulo 18: experiencia con requisitos en la práctica, estudios de seis empresas, en 2 partes.*
