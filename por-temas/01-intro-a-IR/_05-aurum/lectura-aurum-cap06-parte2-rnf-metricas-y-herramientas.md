# Lectura en español — Cap. 6 · Parte 2: Requisitos no funcionales, métricas y herramientas

> **Origen.** Capítulo 6, secciones 6.3 a 6.7, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Per Jönsson y Mikael Lindvall**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1.** Se asumen conocidos los conceptos de SLO, los cuatro conjuntos de impacto, y las estrategias automatizables y manuales.

---

## 1. Análisis de impacto y requisitos no funcionales 🔴

Esta sección es la más aprovechable del capítulo para tu cursada.

### La definición que usan

> **Requisitos no funcionales, o requisitos de calidad: aquellos requisitos "que no se ocupan específicamente de la funcionalidad del sistema".**

Y el problema que traen:

> **Los requisitos no funcionales son a menudo más difíciles de tratar que los funcionales, porque su impacto generalmente no está localizado en una parte del sistema, sino que atraviesa el sistema entero.**

### El ejemplo de la seguridad 🔴

Un requisito no funcional que pide **alta seguridad** requiere a menudo **soporte fundamental en la arquitectura**, porque puede restringir:

- el acceso a los datos,
- la gestión de archivos,
- las vistas de base de datos,
- la funcionalidad disponible.

**Y el camino inverso también existe.** Los cambios a requisitos *funcionales* pueden afectar a los *no funcionales*: si un cambio implica reemplazar un protocolo de transferencia de datos por uno más intensivo en datos, **el rendimiento general del sistema puede degradarse**.

### Convertir requisitos no funcionales en funcionales 🔴

Uno de los enfoques para tratarlos es **convertirlos en uno o más requisitos funcionales**. El ejemplo del capítulo es muy claro:

```
   REQUISITO NO FUNCIONAL
   "ninguna persona no autorizada debería tener
    permitido el acceso a los datos"
                  │
                  ▼  se descompone en
   REQUISITOS FUNCIONALES, MÁS TANGIBLES
   "un usuario debe iniciar sesión en el sistema
    usando una contraseña"
   "la identidad del usuario debe verificarse contra
    el subsistema de inicio de sesión al acceder
    a los datos"
```

**Pero la advertencia importante:**

> **No todos los requisitos no funcionales pueden convertirse de esta manera**, lo que significa que **los cambios a ellos siguen teniendo impacto sobre todo el sistema**. Y desafortunadamente, **la mayoría de las técnicas de análisis de impacto tratan exclusivamente con cambios que pueden ubicarse inicialmente en un componente o clase específicos.**

> ⚠️ **Cruce con la cátedra — importante para las clases 06 y 07.** Esta técnica de descomposición te sirve directamente en un TP: **un RNF vago se vuelve manejable descomponiéndolo en los RF que lo materializan.** Es la contracara operativa de lo que viste en el capítulo 1: la seguridad como cualidad es no funcional, pero el mecanismo de autorización que la realiza es funcional.
>
> Y ojo con el límite: **no todos se pueden convertir.** Rendimiento, mantenibilidad o usabilidad no se descomponen en funciones sin perder algo. Saber cuáles sí y cuáles no es criterio, y ese criterio es exactamente lo que una corrección fundamentada valora.

### Otros enfoques 🟡

**La distinción de Lam y Shankararaman.** Insisten en separar **análisis de impacto funcional** de **análisis de impacto de calidad** — uno para cada tipo de requisito. Sugieren usar el **Despliegue de la Función de Calidad (QFD)**, donde se construye una **matriz que conecta requisitos del cliente con características de diseño**; un cambio a un requisito se mapea a características de diseño a través de esa matriz.

**Trazabilidad basada en eventos.** Un enfoque donde **los requisitos se interconectan como publicadores de eventos hacia modelos de rendimiento suscritos**. Cuando se propone un cambio a un requisito, **los modelos de rendimiento relevantes se recalculan**, y el análisis de impacto resultante se compara contra las restricciones de la especificación. Si varios requisitos están vinculados al mismo modelo, **todos se verifican contra ese análisis**.

### La evaluación de arquitectura basada en escenarios 🟡

El impacto de los requisitos no funcionales se trata comúnmente en la **evaluación de arquitectura de software**. Bosch creó un método de diseño arquitectónico con foco fuerte en ellos: **una arquitectura inicialmente funcional se transforma progresivamente hasta ser capaz de cumplir todos los requisitos no funcionales** planteados sobre el sistema.

Cómo funciona la parte que sirve para análisis de impacto:

```
   1. Para cada atributo no funcional operacional
      (rendimiento, confiabilidad...) se crea un PERFIL
      de escenarios de uso que describen usos típicos
      del sistema a construir

   2. A los escenarios del perfil se les asignan PESOS
      RELATIVOS, según su frecuencia u ocurrencia probable

   3. Se evalúa el IMPACTO ARQUITECTÓNICO de cada escenario
      (para rendimiento, por ejemplo, expresado como
       tiempo de ejecución)

   4. Con el impacto y los pesos se calculan valores
      globales del atributo de calidad evaluado
      (rendimiento total, tiempo de ejecución)

   5. Esos valores se comparan contra los requisitos
      no funcionales correspondientes → ¿se cumplen o no?
```

**Dos usos del resultado:**

1. Los valores **funcionan como restricciones sobre cuánto pueden cambiar los requisitos no funcionales antes de que haga falta una reorganización arquitectónica.**
2. Si **cambia un requisito funcional**, es posible incorporar el cambio en una arquitectura especulativa, **recalcular el impacto de los escenarios del perfil, y ver si los requisitos no funcionales se siguen cumpliendo o no.**

> Ese segundo uso es elegante: permite responder "¿este cambio funcional rompe algo de calidad?" **antes** de implementarlo.

---

## 2. Las métricas 🟡

Las métricas sirven en análisis de impacto por dos motivos distintos:

| Momento | Para qué |
|---|---|
| **Al hacer el análisis** (fin de la fase de requisitos) | **Medir y cuantificar el cambio** causado por un requisito nuevo o cambiado — captura el **impacto predicho** |
| **Una vez implementados los cambios** (fin de las pruebas) | **Evaluar el propio proceso de análisis de impacto** — captura el **impacto real** |

```
   REQUISITOS ──┬──► DISEÑO ──► CÓDIGO ──► PRUEBAS ──┬──►
                │                                     │
          punto de medida 1                    punto de medida 2
          IMPACTO PREDICHO                     IMPACTO REAL
                └──────────── se comparan ────────────┘
                     ciclo de aprendizaje
```

> **Este tipo de medición es crucial para poder analizar y aprender de la experiencia, y así mejorar continuamente la capacidad de análisis de impacto.**

Los autores aclaran que el esquema es una simplificación en forma de cascada: **los puntos de medida se aplican cada vez que se hace una predicción y cada vez que se completa una implementación.**

### 2.1 Métricas para cuantificar el impacto 🟡

Se basan en **los SLO que se predice que van a cambiar**, más **indicadores de cuán severo es el cambio**. Sirven para **estimar el costo** de un cambio propuesto:

> **Cuantos más requisitos y otros SLO se vean afectados, más dispersos estén, y más complejo sea el cambio propuesto, más caro va a resultar el requisito nuevo o cambiado.**

**Y para qué sirve saberlo:** los requisitos que son costosos en ese sentido **pero aportan poco valor pueden filtrarse**, en beneficio de los que aportan más valor a menor costo.

**Qué se puede medir, por tipo de SLO:**

| SLO | Métricas |
|---|---|
| **Requisitos** | **Cantidad de requisitos afectados.** Su complejidad, que suele determinar cuán severo es el cambio: **tamaño de cada requisito** (en puntos de función) y **cantidad de dependencias** de cada requisito con otros |
| **Arquitectura y diseño** | Cantidad de **componentes** afectados · de **clases o módulos** · de **métodos o funciones** |
| **Código fuente** | **Líneas de código** afectadas · nivel de **complejidad** de componentes, clases y métodos (complejidad ciclomática y métricas orientadas a objetos estándar) |

### 2.2 El factor de impacto 🔴

Para determinar cuán severo o costoso es un cambio, es útil definir el **factor de impacto**. Está basado en un hallazgo empírico: **los cambios a distintos tipos de SLO pueden usarse como indicador de la extensión del cambio.**

> **Cuanto más alto el factor de impacto, más severo el cambio.**

| Factor | Impacto | Descripción |
|---|---|---|
| **M1** | Cambio del **modelo de objetos de diseño** | Regarda la descripción **real o física** del sistema. Puede generar en la arquitectura **un cambio del tamaño del cambio en el modelo** |
| **M2** | Cambio del **modelo de objetos de análisis** | Regarda la descripción **ideal o lógica**. **Un cambio chico acá puede generar en la arquitectura un cambio mayor que el del modelo** |
| **M3** | Cambio del **modelo de objetos del dominio** | Regarda **el vocabulario necesario en el sistema**. **Un cambio chico acá puede generar un cambio grande en la arquitectura** |
| **M4** | Cambio del **modelo de casos de uso** | Requiere agregados y borrados al modelo de casos de uso. **Cambios chicos acá pueden requerir un cambio grande en la arquitectura** |

**La lógica detrás de la escala:**

```
   M1  cambios que NO afectan otro tipo de SLO que el modelo
       de diseño → alcance relativamente LIMITADO
                        │
                        ▼  severidad creciente
   M4  cambios al modelo de casos de uso → probablemente
       requieran cambios relacionados con los FUNDAMENTOS
       del sistema, y además probablemente involucren
       cambios en TODOS los otros SLO
```

> ⚠️ **Cruce con la cátedra — el punto más aprovechable de esta parte.** Mirá **M3** y **M4** juntos.
>
> **M3 dice que cambiar el vocabulario del dominio genera cambios grandes en la arquitectura.** Eso es evidencia empírica de por qué la segunda mitad de tu materia se dedica a construir un léxico del dominio: **el vocabulario no es preámbulo del sistema, es infraestructura del sistema.** Cambiarlo tarde sale carísimo.
>
> **Y M4 dice que el modelo de casos de uso es el SLO más caro de tocar de los cuatro** — cambiarlo mueve todo lo demás. Eso explica por qué la cátedra invierte tantas clases y tantos TP en que los casos de uso salgan bien desde el principio: **es el artefacto donde equivocarse cuesta más.**

### 2.3 Métricas para evaluar el propio análisis 🟢

Bohner y Arnold proponen métricas basadas en **relaciones entre los tamaños de los conjuntos de impacto** — indicadores de la efectividad del método empleado:

| Métrica | Qué mide | Valor deseado |
|---|---|---|
| **SIS / EIS** | Cuántos SLO se creyó afectados **sobre** cuántos se estimó afectados | **Cerca de 1.** Un valor mucho menor indica que muchos SLO quedaron marcados por impacto indirecto, **lo que hará lento verificarlos** |
| **EIS / Sistema** | Cuántos SLO se estimó afectados **sobre** el total del sistema | **Mucho menor a 1**, indicando que los cambios se limitan a una parte chica. **Cerca de 1 indicaría o un método defectuoso o un sistema con efectos de propagación extremos** |
| **EIS / AIS** | Cuántos SLO se estimó afectados **sobre** cuántos resultaron afectados | **1** — estimación perfecta. En la realidad suele ser **menor a 1**, indicando que el método **no logró estimar todos los impactos** |

**Dos casos especiales del tercero:** que AIS y EIS **se superpongan solo parcialmente**, o que **no se superpongan en absoluto**. Ambos indican un fracaso del método.

#### El árbol de Fasolino y Visaggio 🟢

Otros autores atan las métricas a propiedades del método:

```
   ADECUACIÓN ──────► capacidad de estimar el conjunto
     medida por        de impacto
     INCLUSIVIDAD      (binaria: 1 si todo el AIS está
                        dentro del EIS, 0 si no)

   EFECTIVIDAD ─────► capacidad de dar resultados útiles
     ├─ SENSIBILIDAD A LA PROPAGACIÓN
     │    capacidad de identificar efectos de propagación
     │    medida por AMPLIFICACIÓN = (EIS − SIS) / SIS
     │    → no debería ser mucho mayor a 1, lo que indicaría
     │      mucho más impacto indirecto que directo
     ├─ AGUDEZA
     │    capacidad de NO sobreestimar el impacto
     │    medida por TASA DE CAMBIO = EIS / Sistema
     └─ ADHERENCIA
          capacidad de estimar el impacto correcto
          medida por S-Ratio = AIS / EIS
```

#### Métricas sueltas de Lam y Shankararaman 🟢

Menos definidas y sin valores recomendados:

- **Desviación de calidad** — la diferencia en algún atributo de calidad (rendimiento, por ejemplo) **antes y después** de implementar los cambios, o entre valores reales y simulados. **Una diferencia mayor a la esperada podría indicar que el método no identificó todo el impacto.**
- **Conteo de defectos** — la cantidad de defectos que aparecen después de implementar los cambios. **Un número grande podría indicar que algún impacto se pasó por alto.**
- **Conteo de dependencias** — la cantidad de requisitos que dependen de un requisito particular. **Los requisitos con conteo alto deberían examinarse cuidadosamente cuando se los somete a cambio.**

---

## 3. El estudio de campo en Ericsson 🔴

Esta es la parte más contundente del capítulo: qué pasó cuando se midió un análisis de impacto real contra la realidad.

### El contexto

Lindvall definió y usó métricas en un estudio en **Ericsson AB**, la empresa sueca de telecomunicaciones, sobre un análisis de impacto **hecho en un proyecto comercial real, por los propios desarrolladores del proyecto, como parte del trabajo regular**.

El análisis se hizo **en la fase de requisitos** — de ahí el término **análisis de impacto dirigido por requisitos**. Los resultados se usaron para **estimar el costo de implementación y seleccionar requisitos** según costo estimado contra beneficio percibido.

**Las preguntas del estudio:**

- ¿Qué tan buena fue la predicción del cambio, en términos de **cuántas clases C++** iban a cambiar?
- ¿Y en términos de **cuáles clases** iban a cambiar? Desglosada en: *¿se predijeron las clases que cambiaron?* y *¿cambiaron las clases predichas?*

### Los números 🔴

```
   Total de clases C++ en el sistema ......... 136
   Clases PREDICHAS para cambiar .............  30
   Clases que EFECTIVAMENTE cambiaron ........  94

   Solo el 31,0 % de las clases que cambiaron
   habían sido predichas
```

La tabla cruzada completa:

| | | **Predichas: sin cambio** | **Predichas: con cambio** | |
|---|---|---|---|---|
| **Reales** | **Sin cambio** | **A: 42** (30,9 %) | **B: 0** (0,0 %) | 42 |
| | **Con cambio** | **C: 64** (47,1 %) | **D: 30** (22,1 %) | 94 |
| | | 106 | 30 | **136** |

**Qué significa cada celda:**

- **A (42)** — no se predijo que cambiaran y no cambiaron. **Predicción correcta**, aunque *implícita*: resultaron como efecto colateral de predecir las que sí cambiaban.
- **B (0)** — se predijo que cambiaran y **no cambiaron**. Un número grande acá indicaría gran desviación. **Fue cero.**
- **C (64)** — **no se predijo que cambiaran, pero cambiaron.** Un número grande acá también indica gran desviación. **Fue la celda más grande de todas.**
- **D (30)** — se predijo que cambiaran y cambiaron. **Predicción correcta.**

### Las tres maneras de evaluar el resultado 🔴

**1. Porcentaje de predicciones correctas:** (42 + 30) / 136 = **52,9 %**. La predicción fue correcta **en aproximadamente la mitad de los casos**.

**2. El valor Kappa de Cohen**, que mide el acuerdo entre dos grupos y va de −1,0 a 1,0:

```
   −1,0  incumplimiento total entre los dos grupos
    0,0  el resultado NO ES MEJOR QUE EL PURO AZAR
    1,0  cumplimiento total
```

**El valor en este caso fue 0,22**, que indica **una predicción apenas aceptable**.

**3. Comparar cantidades:** la cantidad de clases predichas resultó **subpredicha en gran medida, por un factor de 3**. Solo alrededor de **un tercio** del conjunto de clases que cambiaron fue identificado.

**Pero un matiz que vale:** **todas las clases que se predijo que iban a cambiar, efectivamente cambiaron** (la celda B fue cero). Lo que falló no fue la precisión de lo que se señaló — fue **todo lo que no se señaló**.

### El análisis por requisito 🟡

El estudio después miró requisito por requisito. Los resultados:

> **En casi todos los casos hubo subpredicción** en cantidad de clases. La cantidad de clases cambiadas dividida por la cantidad de clases predichas **fue de 1,0 a 7,0. Es decir: hasta 7 veces más clases de las predichas cambiaron realmente.**

**Por qué importa eso concretamente.** La estimación de costo para seleccionar requisitos se basa en la predicción: los requisitos que se predice que causan cambio en pocas entidades **se consideran menos caros**, y los que causan cambio en muchas, más caros. Eso hace que **el orden de selección de requisitos equivalga a la lista de requisitos ordenada por cantidad de ítems predichos**.

Comparando el orden relativo basado en clases predichas contra el basado en clases realmente cambiadas, se pudo juzgar la calidad de la predicción desde otro ángulo. **El resultado: la mayoría de los requisitos estaba subpredicha.**

### El hallazgo lateral 🟡

Un dato curioso que salió del análisis:

> **Las clases grandes cambiaron, mientras que las chicas quedaron sin cambios. Y las clases grandes eran las que se había predicho que cambiarían.**

De ahí la conclusión: **el tamaño de la clase puede ser uno de los ingredientes que usan los desarrolladores —quizás inconscientemente— cuando buscan candidatos** afectados por un requisito nuevo o cambiado.

> ⚠️ **Cruce con la cátedra.** El estudio de Ericsson es el mejor argumento empírico del libro sobre por qué la trazabilidad y las dependencias importan. **Profesionales con experiencia, en un proyecto real, sobre su propio sistema, acertaron a nivel del azar mejorado.** No fue por falta de talento — fue porque estimaban de memoria, sin información de dependencias registrada. Si alguna vez necesitás justificar por qué vale la pena documentar relaciones entre requisitos, este es el número: **subpredicción por factor de 3, hasta 7 en casos individuales.**

---

## 4. Herramientas de soporte 🟢

> **La complejidad del proceso de gestión del cambio hace necesario usar algún tipo de soporte de herramientas.**

**Qué debería hacer una herramienta de gestión del cambio:** gestionar requisitos y otros SLO, gestionar pedidos de cambio, vincular pedidos con requisitos y SLO, y monitorear el progreso del análisis de impacto.

**El mínimo posible:** una base de datos simple o una planilla de cálculo. Pero **requiere una cantidad considerable de trabajo manual**, lo que eventualmente puede llevar a **inconsistencias en los datos**.

Y una advertencia de proceso:

> **Si el soporte de herramientas no es parte integral del proceso de gestión del cambio, siempre existe el riesgo de que no se use apropiadamente. Un sistema que no se usa en toda su extensión no puede dar soporte apropiado al proceso.**

### El problema principal 🟡

> **Muchas herramientas de gestión del cambio están restringidas a trabajar con cambio y análisis de impacto al nivel de requisitos.** Idealmente, una herramienta soportaría análisis de impacto sobre **requisitos, diseño, código fuente, casos de prueba** y demás. Pero eso requeriría **integrar herramientas de gestión de requisitos, herramientas de diseño y entornos de desarrollo en un solo conjunto.**

**El dato del relevamiento propio de los autores:** de **29 herramientas de gestión de requisitos** que soportan trazabilidad, **solo en nueve** estaba explícitamente declarado en sus sitios web que soportaban trazabilidad entre requisitos **y otros SLO** como elementos de diseño, casos de prueba y código.

Eso indica que **en muchos casos es necesario usar varias herramientas distintas** para gestionar trazabilidad y hacer análisis de impacto — lo que **puede ser problemático según el grado de integración entre ellas**.

### Extraer dependencias automáticamente 🟢

Existen herramientas que extraen información de dependencias de las representaciones existentes —código fuente, modelos de objetos— **pero la tarea es difícil y a menudo requiere trabajo manual**:

- **Las representaciones de nivel más alto pueden ser demasiado gruesas.**
- **El código fuente puede tener dependencias ocultas**, por ejemplo por ligadura tardía.

**Un enfoque interesante** que menciona el capítulo toma como entrada **un conjunto de escenarios de prueba y algunas trazas hipotéticas** que vinculan SLO con escenarios. Después calcula **las huellas de los escenarios** —las líneas de código que cubren— y, con las huellas y las trazas hipotéticas, **genera las trazas restantes**. Puede usarse **incluso cuando no existe código**, simulando el sistema o formulando hipótesis sobre las huellas.

**Y una limitación general:** las herramientas que trabajan con código fuente **se usan mayormente en contextos de mantenimiento**, y son obviamente **de utilidad limitada dentro del proyecto de desarrollo**.

**El diagnóstico final sobre herramientas:**

> Muchas herramientas de análisis de impacto son **herramientas de prueba de concepto**, construidas para mostrar o sostener un algoritmo o metodología particular. **Lo que falta es la integración a las herramientas de gestión del cambio de uso corriente.**

---

## 5. El futuro del análisis de impacto 🟢

Los autores enumeran las líneas pendientes:

**1. Requisitos no funcionales.** **La mayoría de las estrategias trabaja bajo el supuesto de que los cambios solo afectan a la funcionalidad.** Por eso es más difícil evaluar el impacto de cambios a requisitos no funcionales, o de cambios donde los no funcionales se ven afectados indirectamente. **Hace falta un foco más fuerte** en esto.

**2. La perspectiva de requisitos.** El análisis de impacto se menciona mayormente en contextos de mantenimiento. Hace falta **más investigación enfocada en los aspectos de ingeniería de requisitos**: cómo relacionar requisitos con otros SLO y cómo propagar el cambio en ese contexto.

**3. Trabajar con información parcial** — y este es el punto más realista:

> **La mayoría de las estrategias automatizables asume modelos completos e información de trazabilidad total. Como en la industria es común encontrar modelos desactualizados e información de trazabilidad solo parcial, hacen falta estrategias más robustas que puedan trabajar con información parcial.**

**4. Herramientas integradas.** El análisis de impacto a escala completa **debe ser parte integral de las herramientas de gestión de requisitos** para que el cambio se maneje apropiadamente.

**5. Tipos de sistema nuevos.** Hay que adaptarlo a **aplicaciones web y software COTS**. Las aplicaciones web, por ejemplo, consisten a menudo en **componentes autónomos que se conectan a un repositorio central**, como una base de datos. Por lo tanto **hay pocas dependencias de control entre componentes, y en cambio ricas redes de dependencias de datos** hacia y dentro del repositorio central. Y como esos repositorios **pueden compartirse entre varios sistemas distintos**, aparecen **dependencias de interoperabilidad** que las estrategias actuales no atienden.

---

## 6. Resumen del capítulo 🔴

Los autores recapitulan:

**El análisis de impacto es parte importante de la IR**, porque los cambios al software se inician a menudo por cambios en los requisitos. Y a medida que el proceso de desarrollo se vuelve **menos parecido a una cascada** y **más requisitos nuevos y cambiados pueden esperarse a lo largo del proceso**, el análisis de impacto **se vuelve parte integral de cada fase**.

**Los métodos clásicos** son: análisis de dependencias, análisis de trazabilidad y rebanado. El trabajo temprano los aplicaba **sobre el código fuente**. La maduración de la ingeniería de software llevó a la necesidad de entender **cómo los pedidos de cambio afectan a otros SLO además del código**, incluyendo los requisitos, y los mismos métodos se aplicaron ahí.

**Los métodos típicos de hoy:** analizar información de trazabilidad o dependencias, usar técnicas de rebanado, consultar especificaciones de diseño y documentación, **y entrevistar a desarrolladores con conocimiento — que es probablemente la manera más común**.

**Las métricas son útiles e importantes** para medir y cuantificar el cambio causado por un requisito, y para **evaluar el propio proceso** una vez implementados los cambios. Y el **factor de impacto** es útil para determinar la severidad, **porque indica la extensión probable de un cambio a cierto tipo de SLO**.

Y el cierre:

> **El análisis de impacto es una actividad crucial que sostiene a la ingeniería de requisitos. Sus resultados alimentan muchas actividades, incluyendo la estimación del costo de los requisitos y su priorización. Esas actividades alimentan directamente la planificación del proyecto, lo que convierte al análisis de impacto en una actividad central de un proyecto exitoso.**

---

## Mapa de la Parte 2

```
   REQUISITOS NO FUNCIONALES
   su impacto NO está localizado: atraviesa el sistema
   → técnica: DESCOMPONERLOS en requisitos funcionales
     "nadie no autorizado accede a los datos"
       → "el usuario debe iniciar sesión con contraseña"
       → "la identidad se verifica al acceder"
   → PERO no todos se pueden convertir así

   ─────────────────────────────────────────────

   FACTOR DE IMPACTO — severidad creciente
   M1  modelo de objetos de DISEÑO ...... alcance limitado
   M2  modelo de objetos de ANÁLISIS .... cambio chico →
                                          cambio mayor
   M3  modelo del DOMINIO (vocabulario) . cambio chico →
                                          cambio GRANDE
   M4  modelo de CASOS DE USO ........... toca los
                                          FUNDAMENTOS
                                          + todos los SLO

   ─────────────────────────────────────────────

   EL ESTUDIO DE ERICSSON
   136 clases · 30 predichas · 94 cambiaron
   → solo el 31 % de las que cambiaron fue predicho
   → predicción correcta en el 52,9 % de los casos
   → Kappa 0,22 (apenas mejor que el azar)
   → SUBPREDICCIÓN por factor de 3
     (hasta 7 en requisitos individuales)
   → pero: TODAS las predichas cambiaron (0 falsos positivos)

   ─────────────────────────────────────────────

   PENDIENTE EN EL CAMPO
   · los RNF (casi todo asume que el cambio es funcional)
   · trabajar con información PARCIAL
     (los modelos reales están desactualizados)
   · integración a herramientas de uso corriente
```

---

## Preguntas para chequear que quedó

1. ¿Por qué los requisitos no funcionales son más difíciles de tratar en análisis de impacto?
2. Dé el ejemplo de la seguridad en las dos direcciones: cómo un RNF afecta la arquitectura y cómo un cambio funcional puede degradar un RNF.
3. Explicá la técnica de convertir un RNF en requisitos funcionales, con el ejemplo del capítulo. ¿Cuál es su límite?
4. ¿Qué distinguen Lam y Shankararaman, y qué herramienta proponen?
5. Describí los cinco pasos de la evaluación de arquitectura basada en escenarios.
6. ¿Cuáles son los dos usos del resultado de esa evaluación?
7. ¿Cuáles son los dos momentos de medición y qué captura cada uno?
8. ¿Qué hace que un requisito nuevo resulte caro, según las métricas de cuantificación?
9. Nombrá los cuatro factores de impacto en orden de severidad creciente.
10. ¿Por qué un cambio chico al modelo del dominio genera un cambio grande en la arquitectura?
11. ¿Por qué M4 (casos de uso) es el factor más severo?
12. Explicá las tres métricas de Bohner y Arnold y su valor deseado.
13. ¿Qué mide la amplificación y cuál es su valor problemático?
14. ¿Qué indicaría un conteo de defectos alto después de implementar los cambios?
15. En el estudio de Ericsson: ¿cuántas clases había, cuántas se predijeron y cuántas cambiaron?
16. ¿Qué significa que la celda B haya sido cero? ¿Y que la celda C haya sido la más grande?
17. ¿Qué es el valor Kappa y qué indicó 0,22 en este caso?
18. ¿Por qué la subpredicción distorsiona la selección de requisitos?
19. ¿Qué hallazgo lateral sobre el tamaño de las clases salió del estudio?
20. ¿Por qué de 29 herramientas relevadas solo nueve servían realmente?
21. ¿Cuál es el supuesto poco realista que hacen la mayoría de las estrategias automatizables?
22. ¿Por qué las aplicaciones web plantean un problema distinto para el análisis de impacto?

---

**FIN DEL CAPÍTULO 6 — PARTE 2**

**FIN DEL CAPÍTULO 6**

*Sigue el capítulo 7: negociación de requisitos, en 2 partes.*
