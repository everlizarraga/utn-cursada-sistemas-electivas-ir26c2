# Lectura en español — Cap. 10 · Parte 2: Los tres casos de estudio

> **Origen.** Capítulo 10, secciones 10.5 a 10.8, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Johan Natt och Dag y Vincenzo Gervasi**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1.** Se asume conocida la idea de aproximar la similitud semántica mediante similitud léxica.

---

## Qué hay acá

Tres casos industriales reales, con datos medidos. Son 🟢 en su mayor parte —no tocan tu cronograma— pero **el primero contiene un hallazgo que sí vale**: cuando se comparó la detección automática de requisitos duplicados contra el trabajo de los expertos humanos, **resultó que los expertos se habían perdido el 37 % de los duplicados**.

Es otro dato en la misma línea que el estudio de Ericsson del capítulo 6: **profesionales experimentados, trabajando sobre su propio material, con desempeño bastante peor de lo que uno supondría.**

---

## 1. Caso 1 — Mantener el repositorio en forma 🟡

### El contexto

**Telelogic AB** desarrolla un entorno de desarrollo de software para sistemas de tiempo real, comercializado globalmente. **Los requisitos se recolectan continuamente de varias fuentes**: marketing, soporte, desarrollo, pruebas, evaluaciones de usabilidad, prospectiva tecnológica.

Los requisitos entran al repositorio con estado **"Nuevo"** y después pasan por una serie de evaluaciones y refinamientos: chequeo del nivel de detalle apropiado, asignación de costo, impacto y prioridad. **Cada requisito tiene un ciclo de vida** que progresa por estados; cuando se implementó y verificó, queda como **"Aplicado"**. **Todos los requisitos se conservan en el repositorio, que crece continuamente.**

### El chequeo inicial 🔴

En su estado inicial, cada requisito se chequea por **tres propiedades relacionadas**:

```
   1. ¿es un DUPLICADO de otro requisito ya en el repositorio?
   2. ¿es posible FUSIONARLO con otro requisito?
   3. ¿debería DIVIDIRSE en dos o más requisitos antes
      de seguir analizándolo?
```

Si tiene alguna de esas propiedades, se le asigna el estado "Duplicado" y se toma la acción correspondiente:

- **Al fusionar**, toda la información se agrega al requisito con el que se fusiona.
- **Al dividir**, la información se distribuye en dos o más requisitos nuevos.
- **Si es un duplicado puro**, no se toma ninguna acción adicional.

**El problema:** los requisitos llegan **a un ritmo promedio de tres por día**, y el repositorio crece sin fin. **Esas actividades están causando congestión en el proceso.**

### Los datos

Una foto del repositorio hacia el año 2000:

| Nuevos | Asignados | Clasificados | Implementados | Rechazados | Duplicados | **Total** |
|---:|---:|---:|---:|---:|---:|---:|
| 406 | 428 | 601 | 252 | 103 | 130 | **1.920** |

De los 130 marcados como duplicados, **se consideran para la evaluación solo los 101 que eran duplicados reales** — las fusiones y las divisiones coincidirían solo parcialmente y sesgarían los resultados.

### Las tres medidas de evaluación 🟡

Vale la pena entenderlas porque son estándar y aparecen en cualquier evaluación de este tipo. Se fija un **umbral** de similitud: si dos requisitos lo superan, se los considera **sospechosos de ser duplicados**.

| Medida | Qué calcula |
|---|---|
| **Exhaustividad** (*recall*) | **El porcentaje de los pares que realmente eran duplicados que caen por encima del umbral** — o sea, cuántos de los que había, encontró |
| **Precisión** | **El porcentaje de duplicados reales por encima del umbral, en relación con TODOS los pares por encima del umbral** — o sea, de lo que señaló, cuánto era verdadero |
| **Exactitud** (*accuracy*) | **El porcentaje de todos los pares que caen del lado correcto del umbral** — duplicados correctamente sugeridos más no-duplicados correctamente descartados |

```
   EXHAUSTIVIDAD alta = no se me escapa casi nada
   PRECISIÓN alta     = casi nada de lo que señalo es basura
   → hay un compromiso entre las dos
```

### Los resultados 🟢

La exhaustividad **baja de alrededor del 80 % en el umbral mínimo a poco menos del 20 % en el umbral máximo**. Las tres medidas de similitud comparadas se comportan igual en los dos extremos, pero difieren en el medio: **una da peor exhaustividad y se descarta; entre las otras dos la elección no es obvia** — una da mayor exhaustividad y menor precisión que la otra, **así que la elección depende de la aplicación.**

### Los grupos 🟢

Una observación de método interesante. Si el analizador asigna similitud a los pares (A, F) y (C, F) pero no al par (A, C), **igual sería interesante mirar los tres requisitos juntos**. A esos agrupamientos los llaman **n-grupos**, donde n es la cantidad de requisitos del grupo. En el ejemplo, los dos pares forman un 3-grupo.

**Por qué importa en la práctica:** con umbral bajo puede aparecer **un grupo muy grande de 42 requisitos**. Ese es entonces **el número máximo de requisitos que el analista tendría que manejar simultáneamente** — y los autores sugieren que **grupos tan grandes probablemente puedan ignorarse por irrelevantes.**

Además notan algo práctico: **como los requisitos llegan continuamente, de a pocos, el análisis puede hacerse incrementalmente sobre un conjunto chico**, evitando tener que interpretar el resultado de todo el repositorio de una vez.

### El hallazgo 🔴

Y acá viene lo mejor del caso. Se preguntaron **si el analizador automático revelaba duplicados que los expertos se habían perdido**. Para averiguarlo, le pidieron a un experto que analizara **75 requisitos que el sistema había sugerido como duplicados con umbral alto, pero que los expertos NO habían marcado como tales.**

**El resultado del reanálisis:**

| Relación real | Cantidad |
|---|---:|
| **Duplicados** | **28** |
| **Similares** | 13 |
| **Relacionados** | 8 |
| **Parte de** | 5 |
| **No relacionados** | 21 |

> **Resultó que el 37 % de los pares duplicados sugeridos habían sido efectivamente pasados por alto por los expertos.**

Con ese umbral, corregidos los números: **la exhaustividad subiría del 25 % al 40 %, la precisión del 30 % al 56 %**, y la exactitud —ya alta— sería aún mayor.

**El criterio que usaba el analista** para no considerar duplicados dos requisitos: **si iban a implementarse en partes distintas del software.**

Y notá la tabla completa: **solo 21 de los 75 pares identificados estaban completamente equivocados.** Los otros 54 tenían **alguna relación real** — duplicado, similar, relacionado o "parte de".

### La regla que se desprende 🔴

> **Esos 21 pares erróneamente identificados deben ponerse en relación con los varios miles de sugerencias potenciales. En un escenario industrial es mejor tener unas pocas sugerencias extra que pueden descartarse, que perderse duplicados reales.**
>
> **Dicho de otra manera: es, hasta cierto punto, de mayor interés aumentar la exhaustividad a expensas de la precisión.**

> ⚠️ **Cruce con la cátedra.** Dos cosas para llevarse:
>
> **1. El dato del 37 %** es otra pieza de la misma evidencia que el estudio de Ericsson del capítulo 6: **la revisión humana de conjuntos grandes de requisitos falla sistemáticamente**, no por incompetencia sino porque nadie puede sostener 1.900 requisitos en la cabeza al mismo tiempo. Es un argumento a favor de cualquier ayuda mecánica, por tosca que sea.
>
> **2. La regla de preferir exhaustividad sobre precisión** es transferible a cualquier revisión que hagas. Al revisar un entregable propio, **conviene marcar de más y después descartar**, no marcar solo lo que estás seguro. Un falso positivo cuesta treinta segundos; un falso negativo llega al parcial.

---

## 2. Caso 2 — Vincular deseos de clientes con requisitos de producto 🟢

### El contexto

**Baan** desarrolla aplicaciones grandes y complejas para planificación de recursos empresariales, gestión de la relación con clientes, cadena de suministro y otras áreas. Manejan **dos tipos de requisito**:

| Tipo | Qué es |
|---|---|
| **Requisitos de mercado** | **Deseos nuevos de clientes**, que se copian a la base **tal cual, sin alterar el texto original especificado por el cliente** |
| **Requisitos de negocio** | **Requisitos de producto**, creados dentro de la organización |

Periódicamente la dirección decide arrancar un proyecto de versión nueva, y **se seleccionan requisitos de negocio para implementar — preferentemente de manera de maximizar la cantidad de requisitos de mercado satisfechos**, compatiblemente con las restricciones de tiempo y presupuesto.

**Por qué importa vincularlos bien:**

> **Los clientes reciben mensajes informativos cuando su requisito de mercado se acepta y cuando se satisface en una versión próxima. Así, establecer vínculos completos y correctos es primordial para mantener buenas relaciones con los clientes.**

**La relación es de muchos a muchos:** un requisito de mercado puede abarcar varios de negocio (por ejemplo, para dividir un paquete de trabajo grande en piezas manejables), y uno de negocio puede satisfacer varios de mercado (cuando varios clientes piden la misma funcionalidad).

### El problema concreto 🟡

Vincular en las dos direcciones es rutina diaria de los jefes de producto, **y es muy demandante de tiempo, porque la herramienta actual solo permite búsqueda de texto en la descripción del requisito.**

Y el ejemplo que dan es elocuente:

```
   Se busca el término "contenedor" entre los requisitos
   de mercado:
     → 37 resultados buscando solo en el campo etiqueta
     → 318 resultados buscando en el campo descripción

   Los expertos deben revisar todos.

   Pero históricamente, SOLO 5 requisitos de mercado
   fueron efectivamente vinculados.

   De esos 5, cuatro se encontraban buscando "contenedor".
   El quinto NO aparecía, y requería una búsqueda nueva
   (por ejemplo "estadísticas", que agrega otros 40 y 99
   resultados al conjunto ya abrumador de candidatos).
```

### Los datos

Entre 1996 y 2002 se elicitaron y vincularon manualmente:

| | Elicitados | Vinculados |
|---|---:|---:|
| **Requisitos de negocio** | 3.779 | 1.094 |
| **Requisitos de mercado** | 8.302 | 2.400 |

El corpus analizado contenía **casi un millón de palabras**, con los requisitos de mercado aportando **aproximadamente dos tercios** del total.

### La calidad lingüística del texto 🟡

Un obstáculo potencial que investigaron: **la calidad lingüística variable del texto**. Como en el caso 1, los requisitos **se escriben a menudo con apuro, y pueden contener siglas, errores ortográficos, fragmentos de código, lenguaje coloquial.**

**Qué encontraron al medirlo:** las entidades que no son palabras representan **alrededor del 2 a 3 % del corpus**, y **los errores ortográficos —la única amenaza real para el emparejamiento léxico— solo el 0,3 a 0,4 %.**

**Conclusión:** el cálculo de similitud léxica **no va a verse significativamente afectado por errores de tipeo ocasionales.**

Además, un análisis estadístico de las dos listas de términos mostró **una correlación alta y significativa**, lo que **da buena indicación de que se está usando un léxico compartido en los dos tipos de requisito** — cosa no sorprendente, dado que ambos discuten cuestiones de un dominio restringido. **Eso respalda el supuesto de que en este contexto la similitud léxica puede ser una buena aproximación de la semántica.**

> ⚠️ **Cruce con la cátedra.** Reparen en el razonamiento: **la técnica funciona porque el dominio es restringido y hay un léxico compartido.** Es la misma condición que hacía funcionar los cuestionarios en el capítulo 2 ("los términos, conceptos y límites del dominio deben estar bien establecidos"). **El vocabulario compartido no es un lujo: es la precondición de que las cosas se puedan comparar entre sí.**

### Cómo se usaría 🟢

La interacción esperada:

```
   1. Se envía un requisito nuevo a la base
   2. La herramienta computa la similitud contra los
      preexistentes del tipo OPUESTO y los ordena
   3. Se le presentan al usuario los n mejores
   4. Opcionalmente el usuario "baja" y ve la página
      siguiente
```

**El tamaño de la lista funciona como umbral.** Y proponen un tamaño concreto con fundamento: **entre 5 y 9 elementos sería un buen compromiso**, ya que ese tamaño **permite detectar rápidamente uno o más requisitos correctamente relacionados**, teniendo en cuenta que **de todos modos no se puede alcanzar el 100 %** de exhaustividad ni de precisión.

### Los resultados 🟢

**El techo:** solo alcanzan una exhaustividad máxima de **aproximadamente 94 %** —y con una lista irrazonable de 3.000 requisitos. La razón: **204 requisitos que fueron vinculados manualmente pero NO TIENEN NINGÚN TÉRMINO EN COMÚN.**

Esos 204 casos son los más interesantes, porque **representan los casos donde el supuesto de la similitud léxica como aproximación de la semántica no se sostiene.** Al examinarlos encontraron:

```
   · la mayoría estaban DESCRITOS ESCUETAMENTE, con una
     sola línea de texto. En algunos casos SIN DESCRIPCIÓN
   · algunos estaban escritos COMPLETAMENTE EN OTRO IDIOMA
     mientras los requisitos con los que estaban vinculados
     estaban en inglés
   · algunos parecían describir cosas COMPLETAMENTE
     DISTINTAS: podrían estar mal vinculados, o
     relacionados de una manera que se les escapó
```

**Lo positivo:** **con un tamaño de lista muy razonable de 10, alcanzan una exhaustividad del 51 %.**

### La estimación de ahorro 🟢

Hicieron una cuenta gruesa:

```
   Para 690 requisitos de negocio, una lista de 10
   daría exhaustividad del 100 %

   Caso manual:    revisar ~30 requisitos por búsqueda
   Con la ayuda:   revisar 10 en el peor caso
   → hasta 66 % de esfuerzo ahorrado

   A 15 segundos por requisito leído y decidido,
   la ganancia total es de ~57,5 horas
```

Y una honestidad metodológica que vale destacar:

> **El lector crítico podría observar que en un escenario real no es posible saber cuándo dejar de recorrer la lista**, ya que podrían encontrarse más vínculos relevantes siguiendo. **Lo mismo aplica al caso manual:** buscar más palabras clave podría dar más vínculos.
>
> Con todo, los datos muestran que **un nivel similar de cobertura puede alcanzarse con menos esfuerzo.** Si se desea, **el tiempo ahorrado puede gastarse en aumentar la cobertura, examinando más candidatos** — o dedicarse a otras actividades si la cobertura alcanzada se considera aceptable.

---

## 3. Caso 3 — Pedidos redundantes de operadores 🟢

### El contexto

**Sony Ericsson** desarrolla teléfonos móviles para un mercado global. **Sus clientes primarios son los operadores de telefonía móvil**, que venden los teléfonos al usuario final.

Para conocer las capacidades técnicas de los teléfonos, los operadores envían **Pedidos de Información**. Hay dos clases: pedidos generales, y **pedidos de declaración de cumplimiento**, que son los más comunes: **contienen requisitos específicos y se responden con declaraciones estandarizadas simples sobre si un producto cumple o no cada requisito enunciado.**

### El proceso 🟢

```
   OPERADORES ──► Gerente de Cuenta Clave
                       │
                       ▼
                  Especialista de Soporte a Ofertas
                  (revisa desde el punto de vista de mercado
                   y decide qué productos considerar)
                       │
                       ▼
                  Coordinador
                  (analiza y distribuye las partes relevantes)
                       │
                       ▼
                  ÁREAS DE PERICIA
                  · Grupo de Función (implementación y pruebas)
                  · Grupo de Trabajo Técnico (hojas de ruta,
                    funciones futuras)
                       │
                       ▼ (respuestas)
                  vuelta por el mismo camino, con revisión
                  en cada paso, hasta el operador
```

**Por qué importa:** los pedidos **juegan un papel importante en la planificación estratégica del operador**, y le dan a la empresa **información vital de inteligencia de negocio**, ya que las funcionalidades priorizadas por los operadores **sirven de guía para desarrollar teléfonos futuros**. Los operadores tienen entonces **gran influencia sobre los requisitos finales del producto**.

### El problema 🔴

> **La eficiencia del proceso está severamente impedida.** Las áreas de pericia **están ocupadas con su asignación primaria en desarrollo y pruebas y tienen problemas para encontrar el tiempo** de analizar los pedidos.
>
> **Y se frustran particularmente porque tienen que declarar el cumplimiento de los mismos requisitos, o de requisitos muy similares, una y otra vez.**

Las causas concretas:

```
   · GRANDES PARTES de las versiones nuevas de pedidos que
     llegan del MISMO operador son típicamente IGUALES
     a las versiones previas
   · el HISTORIAL DE REVISIONES del operador NO ES CONFIABLE:
     hubo casos donde se REUTILIZARON identificadores y
     donde se CAMBIARON requisitos SIN INDICARLO
   · a menudo los mismos requisitos, o muy similares,
     aparecen en pedidos de OPERADORES DISTINTOS
```

> ⚠️ **Cruce con la cátedra.** El segundo punto es una lección de trazabilidad por la vía del dolor: **reutilizar identificadores y cambiar contenido sin marcar la versión rompe toda posibilidad de comparar.** Es exactamente lo que el capítulo 5 llamaba `cambia_a` — la relación que registra la historia de un requisito. Cuando esa relación no se mantiene, **no se puede saber qué cambió, y hay que revisar todo de nuevo desde cero.**

### La solución propuesta 🟢

Cuando llegan los pedidos, **se convierten a un formato estandarizado** donde los requisitos atómicos pueden identificarse con identificadores únicos. El pedido estandarizado **se compara contra una base de pedidos previos ya analizados**, y para cada requisito se proveen coincidencias basadas en similitud.

Los gestores pueden entonces **marcar los requisitos nuevos como duplicados, similares, o ninguno de los dos**. Los pedidos pasan después a las áreas de pericia como siempre, **pero esta vez solo tienen que chequear los marcados como similares o no marcados.**

**La hipótesis de fondo:**

> **Es más rápido juzgar cuán similares son dos requisitos que reanalizar cada uno para determinar el cumplimiento.**

**Beneficios adicionales** que aparecen automáticamente:

```
   · toda la inteligencia de negocio se reúne EN UN LUGAR
   · se pueden identificar y mantener SIMILITUDES entre
     los requisitos de operadores distintos
   · se pueden identificar más fácilmente las
     CONTRADICCIONES entre requisitos de operadores
     distintos
```

### La evaluación 🟢

**Corrida 1.** Dos revisiones del mismo operador. La revisión 1 tenía 242 requisitos ya chequeados; la revisión 2 tenía 434 y se mandó a un área de pericia para chequeo completo — **porque el historial de revisiones no era confiable**.

En paralelo, **una persona NO experta usó el enfoque semiautomático** y en 8 horas pudo identificar que, comparado con la revisión 1, **209 requisitos eran nuevos, 50 estaban cambiados y 175 eran idénticos.** Solo 259 habrían requerido atención del área de pericia.

**El cálculo de ahorro:** contra las 20 horas del chequeo experto completo, el enfoque asistido habría ahorrado **unas 5 horas**.

**Corrida 2.** Dos revisiones de **operadores distintos**, elegidas para ver cómo se comporta el enfoque **sobre requisitos de fuentes distintas, que se espera estén enunciados de manera diferente**. Un experto hizo la comparación completamente manual y también la asistida.

**El resultado sugiere un aumento del 33 % en desempeño** — aunque los autores aclaran que **se espera un efecto de aprendizaje y la cifra exacta no debería tomarse muy en serio.** Pero la conversación con el experto reveló que **el enfoque semiautomático sí dio apoyo relevante para ser valioso en el proceso.**

**Y un obstáculo identificado:**

> **La falta de una herramienta de soporte fluida y amigable se identificó como un asesino del desempeño** al usar el enfoque semiautomático.

Se estimó que **puede ahorrarse el 20 % del tiempo** dedicado a chequear el cumplimiento.

---

## 4. Conclusiones del capítulo 🔴

### El diagnóstico

> **Un número creciente de empresas dirigidas por el mercado y la tecnología se da cuenta de que los requisitos se gestionan mejor de manera continua**, y por lo tanto conviene almacenarlos en repositorios más grandes.
>
> Desafortunadamente, como indica la lucha de esas mismas empresas con sus repositorios, **parece que los desafíos puros de gestión de información se están volviendo cada vez más evidentes en la gestión de requisitos a gran escala. Eso puede ser indicación de que las herramientas disponibles no satisfacen la demanda.**

### La evaluación del enfoque

> **El enfoque presentado da una exactitud razonablemente alta, considerando su simplicidad.** Y lo más importante: **provee apoyo adicional a la gestión de grandes repositorios.**
>
> **El apoyo no apunta a reemplazar la manera actual de trabajar, sino a complementarla para ahorrar tiempo.**

Y una justificación de diseño que vale la pena:

> **La simplicidad de la técnica es una elección deliberada. Al ser simple, es robusta y requiere poco o ningún mantenimiento ni atención — lo cual es importante para su aceptación en la industria.**

> ⚠️ **Cruce con la cátedra.** "La simplicidad es una elección deliberada, porque lo simple es robusto y se adopta" es un principio de diseño que atraviesa toda la serie. Lo viste en el capítulo 3 (los casos de uso tienen solo tres conceptos, **y eso es su virtud**), en el capítulo 4 (usar la técnica de priorización más simple que sirva) y en el capítulo 8 (empezar con una práctica y agregar sofisticación después). **Lo sofisticado que nadie usa vale menos que lo tosco que se usa todos los días.**

**Y el obstáculo real que identificaron:**

> Nuestra experiencia de los tres casos es que **el obstáculo mayor está en el nivel de implementación, ya que no hay soluciones listas.** Hasta que haya soluciones comerciales, **el costo de adoptar la técnica correspondería a un proyecto de desarrollo interno.**

### Otras actividades que podrían apoyarse 🟡

Además de lo presentado en los casos, la misma técnica podría dar soporte a:

| Actividad | Cómo |
|---|---|
| **Trazado de requisitos** | Usar medidas de similitud para el trazado **"después de los hechos"**, cuando la matriz de trazabilidad no se mantuvo desde el principio |
| **Seguimiento de defectos** | Cuando se reportan defectos nuevos, **un chequeo de similitud ayuda a identificar si defectos parecidos ya fueron reportados**, y evita gastar tiempo en reportes de error duplicados |
| **Casos de soporte** | El personal de centros de atención **recorre casos de soporte a diario** y podría apoyarse en las mismas técnicas |

### El cierre

> **Las técnicas de ingeniería lingüística se usan ampliamente en sistemas de apoyo intensivos en información** — por alguna razón, la mayoría de las herramientas de ingeniería de software asistida quedan excluidas. **Las técnicas están disponibles y pueden adaptarse y explotarse con éxito.**
>
> **Con el aumento de la cantidad de información escrita en lenguaje natural que las grandes empresas de desarrollo necesitan gestionar, aprovechar estas técnicas vale definitivamente la pena.**

---

## Mapa de la Parte 2

```
   CASO 1 — TELELOGIC: detectar duplicados
   1.920 requisitos, llegan 3 por día
   al entrar se chequea: ¿duplicado? ¿fusionar? ¿dividir?

   ══► EL HALLAZGO ◄══
   de 75 pares que el sistema marcó y los expertos NO,
   el 37 % eran duplicados REALES que se les habían
   pasado por alto
   → solo 21 de 75 estaban completamente equivocados

   REGLA: en la práctica conviene AUMENTAR LA
   EXHAUSTIVIDAD A COSTA DE LA PRECISIÓN
   (mejor sugerencias de más que perderse duplicados)

   ─────────────────────────────────────────────

   CASO 2 — BAAN: vincular deseos con requisitos
   3.779 de negocio + 8.302 de mercado, ~1 millón
   de palabras
   búsqueda manual: 318 resultados para revisar,
   de los cuales solo 5 servían

   funciona porque el DOMINIO ES RESTRINGIDO y hay
   LÉXICO COMPARTIDO

   con lista de 10: 51 % de exhaustividad, ~57,5 horas
   ahorradas

   falla donde: descripciones de una línea · otro idioma
   · vínculos que nadie entiende

   ─────────────────────────────────────────────

   CASO 3 — SONY ERICSSON: pedidos redundantes
   los operadores mandan lo mismo una y otra vez
   y el historial de revisiones NO ES CONFIABLE
   (identificadores reutilizados, cambios sin marcar)
   → hay que revisar todo de nuevo desde cero

   hipótesis: es más rápido juzgar si dos requisitos
   son similares que reanalizar cada uno

   ─────────────────────────────────────────────

   LA LECCIÓN DE DISEÑO
   la simplicidad es una ELECCIÓN DELIBERADA:
   lo simple es robusto y se adopta
```

---

## Preguntas para chequear que quedó

1. ¿Qué tres propiedades se chequean cuando entra un requisito nuevo al repositorio de Telelogic?
2. ¿Qué pasa con la información cuando se fusiona un requisito? ¿Y cuando se divide?
3. Definí exhaustividad, precisión y exactitud. ¿Qué compromiso hay entre las dos primeras?
4. ¿Qué es un n-grupo y por qué es útil mirarlos?
5. ¿Por qué un grupo de 42 requisitos probablemente pueda ignorarse?
6. ¿Qué porcentaje de duplicados se habían pasado por alto los expertos? ¿Cuántos de los 75 pares estaban completamente mal?
7. ¿Cuál era el criterio del analista para no considerar duplicados dos requisitos?
8. ¿Por qué en un contexto industrial conviene aumentar la exhaustividad a costa de la precisión?
9. Diferenciá requisitos de mercado de requisitos de negocio en el caso Baan. ¿Cuál se copia sin modificar y por qué?
10. ¿Por qué es primordial establecer vínculos completos y correctos entre ambos?
11. En el ejemplo de la búsqueda por "contenedor": ¿cuántos resultados devuelve, cuántos servían realmente, y qué pasa con el que no aparece?
12. ¿Qué porcentaje del corpus son errores ortográficos y por qué eso importa?
13. ¿Por qué la técnica funciona en este contexto? ¿Qué condición del dominio la hace viable?
14. ¿Por qué proponen un tamaño de lista de entre 5 y 9?
15. ¿Qué impide alcanzar el 100 % de exhaustividad? Nombrá las tres causas encontradas.
16. ¿Qué objeción metodológica se hacen a sí mismos los autores sobre la estimación de ahorro?
17. En el caso Sony Ericsson, ¿por qué las áreas de pericia se frustran?
18. ¿Por qué el historial de revisiones de los operadores no es confiable, y qué consecuencia tiene?
19. ¿Cuál es la hipótesis de fondo de la solución propuesta?
20. Nombrá los tres beneficios adicionales que aparecen automáticamente.
21. ¿Qué se identificó como "asesino del desempeño" en la evaluación?
22. ¿Por qué la simplicidad de la técnica es una elección deliberada?
23. Nombrá las tres actividades adicionales que la misma técnica podría apoyar.

---

**FIN DEL CAPÍTULO 10 — PARTE 2**

**FIN DEL CAPÍTULO 10**

*Sigue el capítulo 11: entender la ambigüedad en la ingeniería de requisitos, en 2 partes.*
