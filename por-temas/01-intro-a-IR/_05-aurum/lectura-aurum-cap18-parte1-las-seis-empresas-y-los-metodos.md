# Lectura en español — Cap. 18 · Parte 1: Las seis empresas y cómo se las evaluó

> **Origen.** Capítulo 18, secciones 18.1 a 18.3, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Tony Gorschek y Mikael Svahnberg**, Instituto Tecnológico de Blekinge, Suecia.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.

---

## Qué es este capítulo

Después de diecisiete capítulos de teoría y buenas prácticas, este hace **la pregunta incómoda**:

> Una pregunta que puede surgir es **si la industria realmente USA todo lo presentado.**

Los autores evaluaron **seis empresas** para averiguarlo, y el capítulo describe **qué prácticas de requisitos se implementaron y cuáles no.**

**La Parte 2 tiene los resultados** —lo que la industria hace bien y lo que no— y es la más aprovechable. Esta primera explica quiénes son las empresas y **cómo se hizo la medición**, que también tiene su interés metodológico.

---

## 1. La advertencia inicial 🔴

Los autores son cuidadosos con lo que su estudio puede y no puede decir. Vale leerlo porque **es un modelo de cómo declarar los límites de un trabajo propio.**

**Primera advertencia:**

> **Como en todo estudio de casos, LOS HALLAZGOS PUEDEN NO SER GENERALIZABLES a una muestra mayor. Sin embargo, esa no es la intención de la presentación.** La intención es dar un panorama y algunos ejemplos de qué prácticas se aplican en la industria y —más importante— **cuáles NO se aplican.**

**Segunda advertencia, y esta es la que más importa:**

> **Como los esfuerzos de evaluación presentados son parte de iniciativas de mejora de procesos, LAS EVALUACIONES NATURALMENTE TIENDEN A ENFOCARSE EN ÁREAS QUE NECESITAN CAMBIO Y MEJORA.**
>
> **Esto NO IMPLICA que los procesos de requisitos de las empresas estén totalmente dominados por deficiencias.**

> ⚠️ **Cruce con la cátedra.** Esa segunda advertencia es una lección metodológica que vale más allá del capítulo: **si mirás algo buscando problemas, vas a encontrar problemas** — y eso no significa que todo esté mal.
>
> Es un sesgo que conviene declarar en cualquier análisis propio. Si en un TP hacés un relevamiento de un negocio y encontrás quince fallas de proceso, **eso no prueba que el negocio funcione mal**: prueba que estabas buscando fallas.

**Y para qué sirve describir el estado de la práctica, según los autores:**

```
   · para el INVESTIGADOR: señala dónde hace falta más
     investigación y dónde no
   · para el EDUCADOR: señala dónde diseñar programas
     de capacitación
   · para el PROFESIONAL: señala dónde hay que tener
     cuidado para obtener un conjunto de prácticas
     que funcione · y comparte la experiencia de otros
     sobre qué funciona y qué no
```

---

## 2. Las seis empresas 🟢

Se las nombra con letras griegas por confidencialidad. Lo que importa de cada una es **su dominio y su tipo de desarrollo.**

| | Qué se estudió | Perfil |
|---|---|---|
| **Alfa** | Un proyecto de **11.000 horas-persona**: solución estandarizada parcialmente terminada para **logística y gestión de depósitos** | **Muy especializada en el dominio, Y SUS CLIENTES TAMBIÉN.** El cliente estudiado tiene conocimiento extenso del sistema, usó sistemas similares antes, **y SABE LO QUE QUIERE** |
| **Beta** | Sistema web para una agencia gubernamental, que asiste a empresas reguladas a capturar datos para mantener su certificación. **350 horas-persona en la parte de requisitos** | Experta en el dominio farmacéutico y en procesos de aprobación. **Desarrollo a medida** para clientes grandes y agencias |
| **Gamma** | Proyecto de **1.600 horas-persona**: sistema web para gestionar actividades de capacitación de una empresa de dispositivos médicos | **Dominan los proyectos a medida** |
| **Delta** | Proyecto de **18.000 horas-persona**: sistema de soporte para una agencia gubernamental, basado en un sistema anterior de computadora central, **reducido, modernizado y con interfaz gráfica agregada** | Experiencia considerable en el dominio |
| **Epsilon** | Más de **30 años** desarrollando soluciones de hardware y software para **soporte a la manufactura automatizada** | Unas 200 personas, **entorno de línea de productos.** Clientes grandes y chicos en todo el mundo |
| **Zeta** | Líder mundial en un área específica de **software de guiado y navegación** | Unos 100 empleados, de los cuales 20-25 son ingenieros de software. **Portafolio amplio dentro de su nicho.** Suele haber adaptación menor al cliente tras la instalación |

> ⚠️ **Cruce con la cátedra.** Fijate en el detalle de la empresa Alfa: **el cliente conoce el dominio tan bien como el proveedor, y "sabe lo que quiere".**
>
> Ese caso es raro y cambia todo. Es exactamente la situación que el capítulo 2 describía como la excepción: normalmente el cliente **no sabe qué quiere**, y hay una brecha cultural entre los dos lados. Cuando esa brecha no existe, **algunas prácticas de requisitos dejan de ser necesarias** — y vas a ver en la sección siguiente que el método de evaluación tuvo que contemplarlo explícitamente.

---

## 3. El método basado en modelo 🔴

### Qué mide

Es una evaluación de la **madurez del proceso de requisitos**, hecha con un modelo que los autores construyeron. Su justificación:

> Aunque existen varios métodos para evaluar procesos de desarrollo, **pocos se enfocan en la ingeniería de requisitos, y los que lo hacen hasta cierto punto SON GRANDES Y EXIGEN UNA CANTIDAD CONSIDERABLE DE RECURSOS.**
>
> Usar este modelo, en cambio, **lleva aproximadamente 40 horas-persona en total**, incluyendo el análisis de los datos recogidos.

### La estructura 🟡

```
   3 ÁREAS PRINCIPALES DE PROCESO
        · Elicitación
        · Análisis y negociación
        · Gestión
             ↓
        varias SUB-ÁREAS por cada una
        (aseguramiento de calidad, verificación y
         validación, etc.)
             ↓
        el componente más chico: las ACCIONES
```

> **Las acciones están diseñadas para establecer SI Y CÓMO se realizan ciertas actividades** durante la ingeniería de requisitos — **indicando directamente si las buenas prácticas están cubiertas y en qué medida.**

### Los cinco niveles de madurez 🟡

> **Cada acción reside en un NIVEL DE MADUREZ, del 1 al 5**, donde 1 representa un proceso rudimentario y 5 uno muy maduro.
>
> **Las acciones de cada nivel aseguran un proceso CONSISTENTE Y COHERENTE para ese nivel** — es decir, para alcanzar el nivel 1 hay que completar todas las acciones de nivel 1.

**Y para qué sirve organizar por niveles:**

> Al ubicar las acciones en niveles de madurez es posible **evaluar el potencial de una empresa para cierta madurez, Y MOSTRAR EN QUÉ ACCIONES DEBERÍA ENFOCARSE para alcanzarla** — permitiendo mejoras chicas y por pasos, **un nivel de madurez a la vez.**

### Las tres respuestas posibles 🔴🔴

La evaluación se hace con una lista de verificación que convierte cada acción en una pregunta. Y acá está lo más interesante del método: **hay tres respuestas posibles, no dos.**

```
   · COMPLETADA
   · NO COMPLETADA
   · SATISFECHA-EXPLICADA  ← la interesante
```

**Qué significa la tercera:**

> Su propósito es **tomar en cuenta LA COMPATIBILIDAD DEL MODELO. Las empresas que llevan a cabo proyectos en entornos especiales, distintos del entorno tradicional cliente-desarrollador, pueden considerar ciertas acciones innecesarias Y TENER RAZONES CONVINCENTES para esa opinión.**

**Y el ejemplo que dan es exactamente el caso de la empresa Alfa:**

> **Una empresa donde el desarrollador y el cliente son ambos especialistas en cierto dominio y por lo tanto "HABLAN EL MISMO IDIOMA". La necesidad de clarificación y validación extendida de requisitos puede no existir** — por ejemplo, **la construcción de prototipos puede omitirse.**

**Y la salvaguarda, que es lo que vuelve honesto al mecanismo:**

> **Es importante notar que una acción NO DEBERÍA considerarse satisfecha-explicada por razones como FALTA DE TIEMPO, FALTA DE DINERO, FALTA DE CONOCIMIENTO O SIMPLEMENTE "NO SE NOS OCURRIÓ"** — sino **cuando la buena práctica es INAPLICABLE al entorno industrial en el que la empresa reside.**

> ⚠️ **Cruce con la cátedra — esta categoría es una idea muy buena y transferible.** Resuelve un problema real de cualquier evaluación contra una lista de buenas prácticas: **no todas las buenas prácticas aplican a todos los contextos**, y una evaluación que no lo contemple penaliza a quien tomó una decisión correcta.
>
> Pero notá que **la salvaguarda es lo que hace que la categoría no se convierta en una excusa universal.** La distinción es entre *"no lo hicimos porque no aplica"* y *"no lo hicimos porque no llegamos"*. La primera es legítima; la segunda es una carencia disfrazada.
>
> Es un criterio útil para justificar decisiones en un TP: **si omitís algo que la teoría recomienda, la justificación válida es que no aplica a tu caso — no que no te dio el tiempo.**

### Cómo se leen los resultados 🟢

Se presentan en tablas y gráficos por nivel. En el gráfico:

```
   línea GRIS ──► total de acciones del nivel
   línea NEGRA ► completadas + satisfechas-explicadas
   línea PUNTEADA ► solo las completadas

   el área entre PUNTEADA y NEGRA = "RETARDO DEL MODELO"
        (cuánto del modelo NO APLICA a ese proyecto)
   el área entre NEGRA y GRIS = ÁREA DE MEJORA POSIBLE
```

**Y la regla de interpretación:**

> Si en el primer nivel todas las acciones están completadas o satisfechas-explicadas, **ese nivel de madurez está alcanzado.** Se repite para cada nivel. **Todos los niveles inferiores deben estar completos antes de alcanzar uno superior.**

**Con un matiz práctico que vale:** en el ejemplo que dan, **el proyecto está estrictamente en nivel 1, pero como falta UNA SOLA acción para el nivel 2, ese es el nivel al que los autores recomiendan apuntar como primer paso** de mejora.

### Las tres virtudes declaradas del método 🟡

```
   · FOCO COMPLETO en ingeniería de requisitos
   · LIVIANO Y DE BAJO COSTO
   · NO DETERMINISTA: permite la INAPLICABILIDAD entre
     las buenas prácticas del modelo y la realidad
     de los entornos industriales
```

### El riesgo de crecer 🔴

Y una advertencia que los autores se hacen a sí mismos:

> Es posible agregar áreas y acciones al modelo si hace falta. **Pero la expansión debería hacerse CON EXTREMA PRECAUCIÓN, ya que agregar sin consideración cuidadosa puede volver al modelo un COLOSO a medida que crecen su tamaño y complejidad.**
>
> Además, **agregar en un intento de establecer un modelo que sirva para todos EROSIONARÍA SU NATURALEZA LIVIANA** y crearía otro modelo de evaluación muy grande, **cuyo tamaño y cobertura NO SON UN RASGO PURAMENTE POSITIVO.**

> ⚠️ **Cruce con la cátedra.** *"Su tamaño y cobertura no son un rasgo puramente positivo"* es una frase que vale para cualquier artefacto que construyas.
>
> Es la misma tensión que atraviesa toda la serie: en el capítulo 10 (la simplicidad como elección deliberada, porque **lo simple se adopta**), en el 13 (empresas pidiendo *"herramientas simples para necesidades básicas"*), en el 15 (las metodologías demasiado prescriptivas erigen obstáculos). **Cubrir más no es gratis: se paga en adopción.**

**Cómo se aplicó:** las seis empresas se evaluaron con este método, con al menos un proyecto por empresa. Los proyectos se eligieron buscando los **"típicos"** de cada empresa; en dos casos se evaluaron tres proyectos porque **ningún tipo podía considerarse típico.**

**Las entrevistas:** con **jefes de proyecto** y **responsables de requisitos** —a veces la misma persona—, cerradas, guiadas por la lista de verificación, **de aproximadamente una hora cada una.**

---

## 4. El método inductivo 🔴

### Por qué hacía falta otro

> Mientras el modelo puede usarse para **obtener un panorama rápido e identificar la necesidad de mejoras, NO ES SUFICIENTE PARA SEÑALAR CON PRECISIÓN LAS CAUSAS RAÍZ de los problemas, ni identifica prioridades entre las sugerencias de mejora.**

**Y la diferencia de fondo entre los dos enfoques:**

```
   MODELO (prescriptivo) ──► parte de una LISTA DE BUENAS
                             PRÁCTICAS y ve qué falta

   INDUCTIVO ──────────────► parte de LAS EXPERIENCIAS
                             de los proyectos EN CURSO
                             y basa las mejoras en eso
```

> La idea es **usar las experiencias de las prácticas de los proyectos que se están ejecutando para basar las mejoras, en vez de una lista prescriptiva de (buenas) prácticas.**

### La triangulación de datos 🔴

Lo distintivo del método inductivo que usaron: **triangulación de puntos de datos** para identificar y confirmar propuestas de mejora.

**Las cuatro fuentes:**

```
                    PROYECTO              LÍNEA
                                    (el resto de la
                                     organización que
                                     apoya a los proyectos)

   ENTREVISTAS    (A) entrevistas    (C) entrevistas
                      de caso            de línea

   DOCUMENTOS     (B) documentación  (D) documentación
                      de proyecto        de línea
```

**Y para qué sirve tener cuatro:**

> **La idea NO es usar todas las fuentes solo para obtener MÁS DATOS, sino para tener una CONFIRMACIÓN (validación) de los problemas individuales identificados.**
>
> **Un problema se identifica y se especifica, y después SE CHEQUEA CONTRA LAS OTRAS FUENTES para confirmarlo.** Un beneficio adicional es que **el uso de fuentes distintas habilita varias perspectivas, disminuyendo la posibilidad de perder información crucial.**

**Y la división vertical:**

> Los datos de las entrevistas **se complementan y/o se verifican —OCASIONALMENTE SE CONTRADICEN— con los datos de la documentación.**

> ⚠️ **Cruce con la cátedra — esto es directamente aplicable a un relevamiento.** La técnica dice: **no juntes información de una sola fuente; conseguí la misma información por dos caminos distintos y compará.**
>
> Y notá el detalle de que las entrevistas y los documentos **a veces se contradicen.** Eso no es un problema del método: **es exactamente lo que el método sirve para encontrar** — la diferencia entre el proceso declarado y el proceso real, que es lo que la etnografía del capítulo 2 buscaba.
>
> Para un TP: si entrevistás a alguien y también tenés un documento del proceso, **las diferencias entre los dos son información valiosa**, no ruido a descartar.

**Cómo se aplicó:** dos empresas, **tres proyectos cada una** (seis en total). Para cada proyecto se identificaron roles clave y se entrevistó a representantes. **Además se entrevistó a personal de línea que apoya a los proyectos** —por ejemplo, probadores de sistema y gente de comercialización de fuera de los proyectos. Las entrevistas fueron **abiertas, exploratorias o confirmatorias.**

---

## 5. Por qué usaron los dos 🔴

Los autores explican por qué combinaron ambos, y el razonamiento es bueno porque **cada método corrige la debilidad del otro.**

### El riesgo del modelo

> Como se conduce como entrevista estructurada, **hay riesgo de que NO SE ENCUENTRE INFORMACIÓN VITAL si el conjunto de buenas prácticas del modelo es inapropiado.** Puede haber áreas donde el modelo no cubra completamente las actividades de las empresas estudiadas. **Es un riesgo de TODAS las evaluaciones basadas en modelo.**

**Y el riesgo más profundo:**

> Hay riesgo de que **una evaluación basada en modelo IMPONGA UN CONJUNTO ESPECÍFICO DE PRÁCTICAS que puede no ser perfectamente adecuado para la organización en cuestión.**
>
> **El riesgo es que, en vez de ENTENDER LAS NECESIDADES REALES de la organización, un enfoque basado en modelo PRESCRIBA UNA SOLUCIÓN PARTICULAR.**

### La ventaja del modelo

Pero tiene una virtud que el inductivo no:

> **Un enfoque basado en modelo PUEDE DAR INFORMACIÓN SOBRE PRÁCTICAS QUE LA EMPRESA EVALUADA NO CONOCE** — siendo beneficioso sobre los métodos inductivos, **que basan sus resultados en gran medida EN LA INFORMACIÓN Y EL CONOCIMIENTO YA PRESENTE en la empresa evaluada.**

```
   MODELO ────► te muestra lo que NO SABÍAS que existía
                pero puede imponerte algo que no te sirve

   INDUCTIVO ─► entiende TU situación real
                pero solo puede ver lo que vos ya conocés
```

**La conclusión:**

> **Para lidiar con las desventajas de ambos métodos y aprovechar los beneficios de los dos, las evaluaciones usan UNA COMBINACIÓN.**

> ⚠️ **Cruce con la cátedra.** Este par de limitaciones tiene una simetría muy clara y vale para muchas más cosas que evaluar procesos:
>
> **Una lista externa te muestra lo que no sabías que faltaba, pero puede no aplicar a tu caso.**
> **Partir de tu propia experiencia se ajusta a tu caso, pero no te puede mostrar lo que nunca viste.**
>
> Es exactamente la razón por la que en tu materia conviene tener las dos cosas: **la rúbrica colaborativa** —que se construye desde tu propia experiencia de correcciones— **y las listas de verificación de la literatura**, como las de los capítulos 8, 11 y 17. La primera se ajusta a lo que tu cátedra corrige; la segunda te muestra categorías de error que todavía no te tocaron.

---

## Mapa de la Parte 1

```
   LA PREGUNTA
   ¿la industria realmente USA todo lo que la teoría
   propone?

   LA ADVERTENCIA
   las evaluaciones eran parte de iniciativas de MEJORA
   → naturalmente BUSCAN PROBLEMAS
   → encontrar problemas NO significa que todo esté mal

   ─────────────────────────────────────────────

   LAS 6 EMPRESAS
   Alfa (logística — EL CLIENTE SABE LO QUE QUIERE) ·
   Beta (farmacéutico, a medida) · Gamma (a medida) ·
   Delta (agencia gubernamental) · Epsilon (manufactura,
   línea de productos) · Zeta (navegación, nicho)

   ─────────────────────────────────────────────

   MÉTODO 1 — BASADO EN MODELO
   3 áreas → sub-áreas → ACCIONES
   5 niveles de madurez · ~40 horas-persona

   ══► 3 RESPUESTAS, NO 2 ◄══
   completada · no completada ·
   SATISFECHA-EXPLICADA = la práctica NO APLICA
        salvaguarda: NO vale por falta de tiempo,
        dinero, conocimiento, o "no se nos ocurrió"

   riesgo declarado: agregar sin cuidado vuelve el
   modelo un COLOSO → "el tamaño no es un rasgo
   puramente positivo"

   ─────────────────────────────────────────────

   MÉTODO 2 — INDUCTIVO
   parte de las experiencias REALES, no de una lista
   TRIANGULACIÓN de 4 fuentes:
        entrevistas y documentos × proyecto y línea
   → no para tener MÁS datos: para CONFIRMAR
   → cuando entrevistas y documentos SE CONTRADICEN,
     eso ES el hallazgo

   ─────────────────────────────────────────────

   POR QUÉ LOS DOS
   MODELO: te muestra lo que NO SABÍAS · pero puede
           imponer algo que no te sirve
   INDUCTIVO: se ajusta a TU caso · pero solo ve lo
              que ya conocés
```

---

## Preguntas para chequear que quedó

1. ¿Cuál es la pregunta que motiva el capítulo?
2. ¿Por qué los hallazgos pueden no ser generalizables y por qué eso no invalida el trabajo?
3. ¿Por qué las evaluaciones tienden a enfocarse en problemas? ¿Qué sesgo introduce eso?
4. ¿Para qué sirve describir el estado de la práctica, según los tres destinatarios que enumeran?
5. ¿Qué tiene de particular la empresa Alfa respecto de su cliente? ¿Por qué eso cambia las cosas?
6. ¿Cuál es la justificación de construir un modelo propio en vez de usar los existentes?
7. Describí la estructura jerárquica del modelo.
8. ¿Qué garantizan las acciones de cada nivel de madurez? ¿Para qué sirve organizar por niveles?
9. Nombrá las tres respuestas posibles de la lista de verificación.
10. ¿Qué significa "satisfecha-explicada" y para qué se creó esa categoría?
11. ¿Por qué razones NO vale declarar una acción como satisfecha-explicada?
12. ¿Cómo aplicarías esa distinción para justificar una omisión en un trabajo propio?
13. ¿Qué es el "retardo del modelo" en el gráfico de resultados?
14. ¿Qué riesgo corre el modelo si se lo expande sin cuidado?
15. ¿Por qué "el tamaño y la cobertura no son un rasgo puramente positivo"?
16. ¿Qué no puede hacer el método basado en modelo que sí hace el inductivo?
17. ¿En qué se diferencia el punto de partida de cada método?
18. Nombrá las cuatro fuentes de la triangulación.
19. ¿Para qué se usan cuatro fuentes, si no es para tener más datos?
20. ¿Qué significa que las entrevistas y la documentación se contradigan? ¿Es un problema?
21. ¿Cuál es la ventaja del método basado en modelo sobre el inductivo?
22. ¿Cuál es el riesgo más profundo de un enfoque basado en modelo?
23. ¿Por qué conviene tener a la vez una rúbrica propia y listas de verificación externas?

---

**FIN DEL CAPÍTULO 18 — PARTE 1**

*Sigue en la Parte 2: los hallazgos — las seis áreas donde la mitad o más de las empresas tenían margen de mejora, las tres que dominaban bien, la comparación con otros relevamientos, y las conclusiones.*
