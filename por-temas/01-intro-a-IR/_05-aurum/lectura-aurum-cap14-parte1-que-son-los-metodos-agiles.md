# Lectura en español — Cap. 14 · Parte 1: Qué son los métodos ágiles y hasta dónde llegan

> **Origen.** Capítulo 14, secciones 14.1 a 14.3, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Alberto Sillitti y Giancarlo Succi**, Universidad Libre de Bozen-Bolzano, Italia.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.

---

## Aviso sobre este capítulo

No está en tu cronograma. Pero tiene una cosa que sí vale, y es **el marco conceptual que explica por qué lo ágil hace lo que hace**: todo el enfoque se deriva de un solo principio —**eliminar el desperdicio**— y de ahí salen la documentación mínima, las iteraciones cortas y el cliente presente. Sin ese marco, las prácticas ágiles parecen una lista arbitraria de costumbres.

Y trae algo poco frecuente en la literatura ágil: **una discusión honesta de sus límites.** Los propios autores dicen dónde no funciona.

---

## 1. De dónde viene lo ágil 🔴

### La producción esbelta

> **Los métodos ágiles son una familia de procesos de desarrollo** cuyo objetivo es **entregar productos más rápido, con alta calidad, y satisfacer las necesidades del cliente, mediante la aplicación de los principios de la PRODUCCIÓN ESBELTA al desarrollo de software.**

La producción esbelta **se concibió en los años 50 en Toyota**, e involucra prácticas que hoy son parte de la mayoría de los procesos de manufactura: producción justo a tiempo, gestión de calidad total, mejora continua del proceso.

**Y su principio, que es uno solo:**

> **La identificación y remoción constante del DESPERDICIO** (*muda* en japonés): **cualquier cosa que no agregue valor para el cliente al producto final.**

De ahí, los métodos ágiles se enfocan en dos cosas:

```
   1. ENTREGAR VALOR para el cliente
   2. ASEGURAR que el cliente ENTIENDA ese valor
      y quede satisfecho con el proyecto
```

### Por qué agregar algo de más es un error 🔴

Este razonamiento es el corazón del capítulo:

> Entregar valor implica que el equipo **debe producir SOLO lo que provee valor** y remover —o al menos reducir al mínimo— todo lo demás. **Producir cualquier cosa que no se requiera se considera un error.**
>
> **Agregar una funcionalidad que no hace falta no solo consume esfuerzo sin agregar valor, sino que además CREA CÓDIGO EXTRA**, que puede contener errores y **vuelve el código más largo y más complejo de mantener, corregir y mejorar.**

Y el desperdicio incluye cosas que normalmente se consideran virtudes:

> **Ese desperdicio incluye ARQUITECTURAS GENERALES que se usan solo parcialmente, o COMPONENTES REUTILIZABLES con funcionalidades que probablemente nunca se usen.**

> ⚠️ **Cruce con la cátedra.** Esa última frase es la más provocadora del capítulo, y vale entenderla bien porque contradice una intuición muy común: **la generalidad no es gratis.** Una arquitectura preparada para casos que nunca llegan cuesta el doble —una vez al construirla y otra vez cada vez que hay que mantenerla— y no dio nada a cambio.
>
> Conecta con lo que viste en el capítulo 13 sobre el modelo alfa/beta: **un requisito que no aporta valor no es neutro, es negativo**, porque consume presupuesto que podría haber ido a uno que sí.

### Las dos declaraciones de posición 🟡

Para lograr esa eliminación de desperdicio, los métodos ágiles se declaran:

```
   · ADAPTATIVOS en vez de PREDICTIVOS
   · ORIENTADOS A LAS PERSONAS en vez de
     ORIENTADOS AL PROCESO
```

Y para asegurar la satisfacción del cliente **se busca una colaboración estrecha entre el equipo y el cliente**, de modo que:

- **los requisitos se identifiquen plenamente y se entiendan correctamente**;
- **el producto final refleje lo que el cliente necesita, NI MÁS NI MENOS.**

---

## 2. El manifiesto ágil 🔴

### Por qué existe

> Los promotores se dieron cuenta de que **la amplia variedad de estos métodos podía disuadir a potenciales adoptantes**, que no podían determinar qué aplicar en sus propias operaciones.

Como resultado, **analizaron la raíz de la gestión esbelta y definieron un documento con un conjunto de valores básicos comunes a todos los métodos.**

### Los cuatro valores 🔴

| Valor | Qué significa |
|---|---|
| **Individuos e interacciones por encima de procesos y herramientas** | Enfatiza **la importancia de las personas y sus interacciones**, en vez de enfocarse en procesos estructurados y herramientas |
| **Colaboración con el cliente por encima de contratos** | La relación **se regula mediante la participación del cliente en el proceso**, en vez de mediante contratos detallados y fijos. *(Usualmente los contratos ágiles son de **precio variable y alcance variable**, no de precio fijo y alcance fijo.)* |
| **Software funcionando por encima de documentación** | La meta es **entregar código que funcione**, que es el artefacto que provee valor. **El código bien escrito se autodocumenta y la documentación formal se reduce al mínimo** |
| **Responder al cambio por encima de planificar** | El equipo **debe reaccionar rápido a la variabilidad de los requisitos. Las decisiones vinculantes se demoran lo más posible** y el tiempo de planificación se limita a lo que el cliente necesita. **Cualquier intento de pronosticar necesidades futuras está prohibido** |

> ⚠️ **Cruce con la cátedra — leelo con cuidado.** Es fácil malinterpretar los valores como si dijeran *"la documentación no importa"* o *"planificar está mal"*. **No dicen eso.** Dicen que cuando hay que elegir entre dos cosas valiosas, se prefiere una — y **el marco de la producción esbelta explica por qué**: la documentación y la planificación son valiosas **hasta el punto en que dejan de agregar valor para el cliente**, y a partir de ahí son desperdicio.
>
> Notá además que el tercer valor **descansa sobre un supuesto muy fuerte**: *"el código bien escrito se autodocumenta"*. Eso es cierto para el CÓMO —qué hace este método— y **falso para el POR QUÉ.** El código nunca documenta por qué el negocio funciona así. Es exactamente lo que el capítulo 5 llamaba **pérdida de conocimiento cuando alguien deja el proyecto**.

### Las cinco prácticas comunes 🔴

De esos valores salen prácticas y comportamientos. Y una aclaración de origen que vale:

> **La afirmación subyacente es que NO son invenciones de la comunidad ágil, sino el resultado de RACIONALIZAR LA EXPERIENCIA de éxitos y fracasos en desarrollo de software.**

**1. Adaptabilidad.** *"Las prácticas tienen que adaptarse a las necesidades específicas tanto del equipo como del cliente.* **No hay una solución que sirva para todos."**

**2. Desarrollo incremental.** Las distintas fases —análisis, diseño, código y pruebas— **se comprimen en iteraciones muy cortas, de dos semanas a dos meses**, para enfocarse en unos pocos problemas bien definidos que **provean valor real al cliente**.

**3. Versiones frecuentes.** Al final de cada iteración **la aplicación se entrega al cliente**, que la prueba y da retroalimentación. Tres beneficios:

```
   1. el cliente puede USAR la aplicación muy temprano,
      permitiendo identificar problemas potenciales A
      TIEMPO para mejorar el producto limitando el efecto
      sobre el cronograma
   2. el cliente SE SIENTE EN CONTROL del proceso, ya
      que los progresos son siempre visibles
   3. LA CONFIANZA entre cliente y equipo AUMENTA, porque
      el equipo se considera confiable al poder entregar
      versiones que funcionan, temprano
```

**4. Priorización antes de cada iteración.** Antes de cada iteración, cliente y equipo **identifican requisitos nuevos y REASIGNAN PRIORIDADES a los viejos** según las necesidades reales del cliente en ese momento.

**5. Alta participación del cliente.** Mediante **pedido continuo de retroalimentación** para identificar problemas temprano. En algunos casos **el cliente es incluso miembro del equipo** —la práctica del cliente en el sitio— y **está siempre disponible** para clarificar cuestiones de requisitos.

### Qué significa ser "más ágil" 🟡

Una definición precisa y útil:

> **Una metodología de desarrollo es MÁS ÁGIL que otra si requiere MENOS SOBRECARGA — que es todo aquello que no produce valor para el cliente.**

Y una aclaración importante:

> **No hay una solución única para todos los contextos. Los métodos ágiles proveen SOLO GUÍAS y un trasfondo básico de prácticas y comportamientos que TIENEN QUE ADAPTARSE al problema específico.**

---

## 3. Los límites: el tamaño del equipo 🔴

Acá arranca la parte honesta del capítulo.

> **La mayoría de los métodos ágiles apunta específicamente a EQUIPOS CHICOS, de hasta 16 desarrolladores.** Hay métodos que soportan un rango más amplio, **pero hay muchos problemas bajo investigación**, incluyendo su uso en un entorno distribuido.

### Por qué el tamaño limita la agilidad 🔴

El argumento es mecánico y convincente:

> **El nivel de agilidad está a menudo relacionado con el tamaño del equipo. La comunicación directa y la documentación limitada son posibles SOLO EN EQUIPOS CHICOS.**
>
> **Cuando el equipo crece, el nivel de sobrecarga crece también.** Esa sobrecarga incluye: **(1) documentación y (2) comunicación mediada.**
>
> **Hace falta más documentación para compartir conocimiento y rastrear el estado del proyecto, PORQUE LA INTERACCIÓN DIRECTA DE TODOS CON TODOS YA NO ES POSIBLE.** Por lo tanto, **la importancia de la documentación aumenta y se vuelve una manera de mejorar el compartir conocimiento. En ese caso EL CÓDIGO EN SÍ NO ALCANZA**, y la comunicación directa entre el equipo y el cliente no es posible con un equipo grande.

**Una familia de métodos que hace explícita esta escala:**

| Método | Cantidad de personas |
|---|---|
| El más liviano | 2 a 6 |
| El siguiente | 6 a 20 |
| El siguiente | 20 a 40 |
| El más pesado | 40 a 80 |

> **Los distintos niveles se enfocan en prácticas distintas para gestionar la escalabilidad. Una escalabilidad limitada se logra REDUCIENDO EL NIVEL DE AGILIDAD.**

Y la conclusión, dicha sin vueltas:

> **Desarrollar sistemas grandes usando métodos ágiles es difícil o incluso imposible.** Actualmente el esfuerzo de investigación se enfoca en proyectos chicos y medianos, ya que **incluso en esa área su efectividad sigue bajo investigación. Muchas prácticas ágiles simplemente no escalan; otras sí.**

> ⚠️ **Cruce con la cátedra.** El argumento sobre por qué crece la documentación cuando crece el equipo **es transferible a tu trabajo grupal.** En un equipo de tres o cuatro, mucho se resuelve hablando. Pero notá la condición que lo hace funcionar: **interacción directa de todos con todos.** Si el equipo trabaja en subgrupos, o si alguien falta a una reunión, **ya no se cumple** — y ahí la documentación deja de ser burocracia y pasa a ser lo único que mantiene al grupo alineado.
>
> Es la misma lógica que el capítulo 13 señalaba sobre el riesgo de perder gente clave, y el capítulo 5 sobre la pérdida de conocimiento.

---

## 4. Los otros dos límites 🟡

### La gente

> Los métodos ágiles **se enfocan en el valor de las personas para resolver problemas y compartir información**, no en el proceso ni en una cantidad masiva de documentación.
>
> **Sin embargo, la orientación a las personas puede representar una debilidad principal, ya que las habilidades requeridas para construir buenos equipos ágiles NO SON COMUNES.**

Qué se le pide a un miembro de equipo:

```
   ser un desarrollador EXCELENTE
   + poder trabajar en equipo
   + comunicarse e interactuar con colegas Y CLIENTES
```

**Y la razón de por qué hace falta todo eso:**

> **El equipo es AUTO-ORGANIZADO y no puede recurrir a un proceso predefinido y detallado** para resolver problemas y compartir conocimiento.

> Es un compromiso que se declara poco: **quitar el proceso no elimina la necesidad de coordinarse — la traslada a las personas.** Si el equipo no tiene esas habilidades, no hay proceso de respaldo que lo sostenga.

### El dominio de aplicación 🟡

> **En general, parece que los métodos ágiles son valiosos para construir aplicaciones que NO SON CRÍTICAS PARA LA MISIÓN y de tamaño limitado.**

Se estudian otras áreas —como sistemas embebidos, donde **el rendimiento, el comportamiento en tiempo real y las restricciones de memoria son problemas comunes.**

**Y sobre la reutilización, una precisión que corrige un malentendido:**

> Enfocarse en producir solo lo que da valor **no significa que construir artefactos reutilizables esté prohibido. SI LA META DEL PROYECTO ES desarrollar un artefacto reutilizable, el equipo se enfoca en ese problema** y usa métodos ágiles para abordarlo.
>
> **Lo que NO se hace es desarrollar artefactos reutilizables en proyectos con OTRO objetivo**, porque eso obligaría a incluir funcionalidades que no son útiles para el proyecto en curso.

**El veredicto final:**

> **Los métodos ágiles NO son la solución para desarrollar todo producto. Su aplicación es extremadamente difícil o incluso imposible en muchas áreas, como las aplicaciones críticas de seguridad o las muy grandes y complejas.**

Y una autocrítica del campo:

> **Varias áreas que se analizaron en profundidad en entornos tradicionales NO SE ENTIENDEN BIEN en los métodos ágiles. A menudo hay una falta de esfuerzo de investigación, ESPECIALMENTE EN EL ÁREA DE INGENIERÍA DE REQUISITOS.**

---

## 5. Por qué fracasan los proyectos 🔴

El capítulo trae los datos del informe Standish, y el hallazgo es notable:

> **Cinco de los ocho factores principales de fracaso de proyectos tienen que ver con REQUISITOS.**

| Problema | % |
|---|---:|
| **Requisitos incompletos** | **13,1** |
| **Baja participación del cliente** | **12,4** |
| Falta de recursos | 10,6 |
| **Expectativas poco realistas** | **9,9** |
| Falta de apoyo de la gerencia | 9,3 |
| **Cambios en los requisitos** | **8,7** |
| Falta de planificación | 8,1 |
| **Requisitos inútiles** | **7,5** |

Los cinco marcados suman **51,6 %** de los factores de fracaso.

> ⚠️ **Cruce con la cátedra.** Esta tabla es la mejor versión resumida del argumento que abre todo el libro. Y notá que **los cinco factores de requisitos son de naturaleza distinta:**
>
> - **incompletos** → falta algo
> - **baja participación del cliente** → falta con quién chequear
> - **expectativas poco realistas** → falta factibilidad (capítulo 8)
> - **cambios** → volatilidad (capítulos 4 y 6)
> - **inútiles** → los requisitos "beta" del capítulo 13
>
> Cada uno tiene una contramedida distinta. **No hay un solo problema de requisitos: hay cinco.**

### Los estándares que lo ágil no usa 🟡

El capítulo lista los estándares tradicionales:

```
   IEEE 830  — práctica recomendada para especificaciones
               de requisitos de software
   IEEE 1233 — guía para desarrollar especificaciones de
               requisitos de sistema
   IEEE 1362 — guía para el documento de concepto de
               operaciones
```

Y la posición ágil respecto de ellos:

> **Los métodos ágiles no se apoyan en estos estándares para la elicitación y gestión de requisitos, PERO HAN ADAPTADO MUCHAS DE LAS IDEAS BÁSICAS al entorno nuevo.**

Con una diferencia concreta:

> **En los métodos ágiles TODO EL EQUIPO DE DESARROLLO participa de la elicitación y gestión de requisitos, mientras que en los enfoques tradicionales a menudo participa solo un subconjunto del equipo.**
>
> **Este enfoque es factible SOLO SI EL TAMAÑO DEL PROBLEMA ES LIMITADO.**

---

## 6. El argumento contra pronosticar 🔴

Esta sección merece atención porque es un razonamiento contraintuitivo bien construido.

**La posición ágil:** no tratar de pronosticar cambios ni necesidades futuras, **enfocarse solo en las funcionalidades por las que el cliente está pagando.** Eso evita desarrollar una arquitectura demasiado general que exige esfuerzo adicional.

**La objeción natural** sería: *pero una arquitectura más comprensiva maneja mejor la variabilidad que se puede prever.* Y acá viene la respuesta:

> **Una arquitectura más compleja cuesta más, no solo para el desarrollo sino también para el MANTENIMIENTO y la CORRECCIÓN DE ERRORES.**
>
> **Por lo tanto, esa arquitectura más grande puede terminar siendo UN INHIBIDOR para manejar la variabilidad que NO se pudo prever de antemano.**

Y el remate:

> **Sin mencionar que usualmente es difícil hacer predicciones correctas.** Por eso **muchas funcionalidades incluidas en las etapas tempranas no se usan en el producto final, y se requieren nuevas que no se habían identificado al principio.**
>
> Ese enfoque **genera funcionalidades inútiles, que son desperdicio Y GENERAN DESPERDICIO ADICIONAL** por la mayor complejidad del código y el esfuerzo extra de mantenimiento.

```
   arquitectura general "por las dudas"
        ↓
   más compleja de mantener y corregir
        ↓
   MENOS capaz de absorber el cambio que SÍ llegó
   (el que no se había previsto)
        ↓
   → lo que se construyó para absorber cambios
     TERMINA IMPIDIÉNDOLOS
```

> ⚠️ **Cruce con la cátedra.** Este argumento es una respuesta directa a lo que el capítulo 4 llamaba **volatilidad**: allí se decía que *el proyecto puede encarecerse porque los desarrolladores tienen que elegir una arquitectura apta para el cambio.* **Este capítulo discute esa jugada** — sostiene que la arquitectura apta para el cambio previsto puede volverte más rígido ante el cambio imprevisto.
>
> No hay que tomar partido; lo aprovechable es **tener las dos posiciones**, porque juntas son un buen ejemplo de un compromiso real que se argumenta de los dos lados.

---

## Mapa de la Parte 1

```
   EL ORIGEN: producción esbelta (Toyota, años 50)
   principio único: eliminar el DESPERDICIO = todo lo
   que no agrega valor para el cliente

   → agregar una funcionalidad que no hace falta
     NO ES NEUTRO: consume esfuerzo Y crea código
     que hay que mantener
   → el desperdicio incluye ARQUITECTURAS GENERALES
     usadas a medias y COMPONENTES REUTILIZABLES
     que no se reutilizan

   ─────────────────────────────────────────────

   LOS 4 VALORES
   individuos > procesos · colaboración > contratos
   · software funcionando > documentación
   · responder al cambio > planificar

   LAS 5 PRÁCTICAS
   adaptabilidad · desarrollo incremental (2 semanas
   a 2 meses) · versiones frecuentes · priorización
   antes de CADA iteración · alta participación
   del cliente

   "más ágil" = MENOS SOBRECARGA

   ─────────────────────────────────────────────

   ══► LOS LÍMITES (dichos por los propios autores) ◄══

   TAMAÑO ──► hasta ~16 desarrolladores
              al crecer, la interacción de todos con
              todos deja de ser posible → hace falta
              documentación → CAE LA AGILIDAD
              "desarrollar sistemas grandes es difícil
               o incluso imposible"

   GENTE ───► las habilidades requeridas NO SON COMUNES
              el equipo es auto-organizado: no hay
              proceso de respaldo

   DOMINIO ─► no sirve para crítico de seguridad ni
              muy grande y complejo

   ─────────────────────────────────────────────

   5 DE LOS 8 FACTORES DE FRACASO SON DE REQUISITOS
   incompletos · baja participación del cliente ·
   expectativas irreales · cambios · inútiles
   = 51,6 %
```

---

## Preguntas para chequear que quedó

1. ¿De dónde viene el enfoque ágil y cuál es su principio único?
2. ¿Qué es el desperdicio y por qué agregar una funcionalidad innecesaria no es neutro?
3. ¿Por qué una arquitectura general usada a medias cuenta como desperdicio?
4. Nombrá los cuatro valores del manifiesto ágil.
5. ¿Por qué los valores no dicen que la documentación no importe? ¿Qué los explica?
6. ¿Qué supuesto fuerte hay detrás de "el código bien escrito se autodocumenta"? ¿Dónde falla?
7. Nombrá las cinco prácticas comunes.
8. ¿Cuáles son los tres beneficios de las versiones frecuentes?
9. ¿Qué significa exactamente que una metodología sea "más ágil" que otra?
10. ¿Hasta qué tamaño de equipo apuntan la mayoría de los métodos ágiles?
11. Explicá el mecanismo por el cual crecer el equipo reduce la agilidad.
12. ¿Cómo se logra escalabilidad limitada en la familia de métodos que la hace explícita?
13. ¿Por qué la orientación a las personas es a la vez fortaleza y debilidad?
14. ¿Qué habilidades se le piden a un miembro de un equipo ágil y por qué?
15. ¿En qué dominios es difícil o imposible aplicar métodos ágiles?
16. ¿Está prohibido construir componentes reutilizables? Explicá la distinción exacta.
17. Nombrá los cinco factores de fracaso relacionados con requisitos y qué contramedida tiene cada uno.
18. ¿Qué diferencia hay entre lo ágil y lo tradicional respecto de quién participa de la elicitación? ¿Bajo qué condición es factible?
19. Explicá el argumento de por qué una arquitectura más general puede volverse un inhibidor del cambio.
20. ¿Con qué afirmación del capítulo 4 discute ese argumento?

---

**FIN DEL CAPÍTULO 14 — PARTE 1**

*Sigue en la Parte 2: el enfoque ágil concreto a los requisitos — el cliente único, el desperdicio en requisitos, la evolución de los requisitos, los requisitos no funcionales—, los roles de cliente, desarrolladores y gerentes, y las herramientas.*
