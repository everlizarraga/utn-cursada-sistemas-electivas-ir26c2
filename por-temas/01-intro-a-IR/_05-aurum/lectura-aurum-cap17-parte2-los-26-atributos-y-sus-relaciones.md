# Lectura en español — Cap. 17 · Parte 2: Los veintiséis atributos y sus relaciones

> **Origen.** Capítulo 17, sección 17.4 (introducción y tablas), de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Nur Yilmaztürk**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1.** Se asume conocido el proceso de doce pasos.

---

## Lo que hay acá

Este capítulo hizo algo que ningún otro del libro hizo: **juntó todos los atributos de calidad de requisitos que la literatura menciona y los cruzó entre sí.**

El resultado son **veintiséis atributos** —contra los diez del capítulo 8— y, más importante, **un mapa de cómo se afectan mutuamente**, incluyendo los casos en que **mejorar uno empeora otro.**

Esa segunda parte es lo que más vale. Es fácil aceptar que un requisito debe ser no ambiguo, completo, conciso y comprensible. **Es más difícil aceptar que algunas de esas cosas se pelean entre sí** — y este capítulo dice exactamente cuáles.

---

## 1. Los veintiséis atributos 🔴

La lista completa que compilaron. Los que ya conocés del capítulo 8 están marcados con ✓.

### Sobre el contenido del requisito

| Atributo | ✓ cap. 8 |
|---|---|
| **Alcanzable / factible / realizable** | ✓ (factibilidad) |
| **Correcto** | ✓ |
| **Necesario** | |
| **Completo** | ✓ |
| **En el nivel de detalle correcto** | ✓ |
| **Independiente del diseño** | |
| **Independiente de la implementación** | |

### Sobre cómo está escrito

| Atributo | ✓ cap. 8 |
|---|---|
| **No ambiguo** | ✓ |
| **Claro / preciso / significativo** | |
| **Comprensible** | ✓ |
| **Conciso** | |
| **No redundante** | |

### Sobre el conjunto

| Atributo | ✓ cap. 8 |
|---|---|
| **Internamente consistente** | ✓ (consistencia) |
| **Externamente consistente** | ✓ (consistencia) |
| **Organizado** | |
| **Modificable** | ✓ (modificabilidad) |
| **Reutilizable** | |

### Sobre las relaciones y la gestión

| Atributo | ✓ cap. 8 |
|---|---|
| **Trazable hacia adelante** | ✓ (trazabilidad) |
| **Trazado / trazable hacia atrás** | ✓ (trazabilidad) |
| **Referenciado cruzadamente** | |
| **Priorizado por importancia relativa** | ✓ |
| **Priorizado por estabilidad relativa** | ✓ |
| **Priorizado por versión** | |

### Sobre el soporte

| Atributo | ✓ cap. 8 |
|---|---|
| **Verificable** | ✓ |
| **Almacenado electrónicamente** | |
| **Ejecutable / interpretable** | |

> ⚠️ **Cruce con la cátedra.** Los diez del capítulo 8 están todos acá. Lo que agrega este capítulo son **atributos que no son sobre el requisito en sí, sino sobre cómo se lo maneja**: almacenado electrónicamente, referenciado cruzadamente, priorizado por versión.
>
> Y dos que sí son de contenido y valen: **necesario** (¿tiene que estar?) y **no redundante** (¿no está dicho ya en otro lado?). Son criterios de revisión distintos de los del capítulo 8 y fáciles de correr sobre un entregable.

---

## 2. Los tres problemas al comparar fuentes 🔴

Antes de las relaciones, los autores documentan las inconsistencias que encontraron al juntar la literatura. **Vale leerlo porque explica por qué el vocabulario de calidad es tan resbaladizo.**

### Problema 1 — La misma cosa con nombres distintos

> **Distintas referencias pueden usar términos distintos para el mismo atributo.** Por ejemplo, el primero de la tabla se llama **"alcanzable"** en una fuente, **"factible"** en otra, y **"realizable"** en una tercera.

**Cómo lo resolvieron:** incluir todos los términos encontrados, o **referirse a todos usando el más común.**

### Problema 2 — El mismo nombre con contenidos distintos 🔴

Este es peor:

> **El contenido de un atributo puede diferir de referencia a referencia.** Dos fuentes **definen "correcto" como lo que una tercera llama "necesario"** — y esa tercera **presenta además "correcto" como atributo separado, pero con una definición distinta.**

**Cómo lo resolvieron:** **mantener ambos atributos y asumir una relación positiva entre los dos.**

> ⚠️ **Cruce con la cátedra.** Esto es una ilustración perfecta —y algo irónica— de lo que el capítulo 11 llamaba **ambigüedad léxica**: la misma palabra usada por comunidades distintas con significados distintos, sin que nadie lo note.
>
> **Y pasa dentro de la propia literatura de calidad de requisitos.** Si a los que escriben sobre no ambigüedad les pasa esto, vale la pena tener presente que **cuando alguien dice "el requisito tiene que ser correcto", conviene preguntar qué entiende por correcto.**

### Problema 3 — ¿Aplica al requisito o al conjunto? 🔴

> **No hay distinción clara entre atributos de calidad aplicables SOLO A REQUISITOS INDIVIDUALES y aplicables SOLO AL CONJUNTO.**

Y el ejemplo que dan:

```
   "COMPLETITUD"
   · una fuente dice que es atributo DEL CONJUNTO
   · otra dice que aplica al REQUISITO INDIVIDUAL
   · otra dice que aplica A LOS DOS
```

**Cómo lo resolvieron:** **desatender esa distinción y usar el atributo para medir ambos**, salvo cuando hay consenso común sobre su aplicabilidad.

Y una observación de fondo:

> **En la mayoría de los casos, la definición de un atributo presentado como propiedad de un conjunto IMPLICA DEPENDENCIA de que los requisitos individuales de ese conjunto tengan la misma calidad.**

> ⚠️ **Cruce con la cátedra.** La distinción individual/conjunto es más útil de lo que parece, aunque estos autores la desatiendan. **Hay cosas que solo pueden fallar en el conjunto:** la consistencia interna, por ejemplo, no es una propiedad que un requisito pueda tener solo — **hacen falta al menos dos para contradecirse.** Es lo que viste en el capítulo 5 con el ejemplo del personal y los clientes militares: cada requisito era impecable, el conflicto solo aparecía al leerlos juntos.

---

## 3. Los tres tipos de relación 🔴🔴

Y acá está lo importante. Los atributos **no son independientes**, y se afectan de tres maneras distintas.

### Tipo 1 — Uno hace falta para el otro 🔴

> **No es posible lograr cierta calidad a menos que otra exista.**
>
> **Por ejemplo: SI UN REQUISITO NO ES NO AMBIGUO, NO PUEDE SER VERIFICABLE. Naturalmente, no hay manera de verificar un requisito si existen múltiples interpretaciones de él.**

```
   NO AMBIGUO ──es prerrequisito de──► VERIFICABLE
```

> ⚠️ **Cruce con la cátedra.** Esa dependencia es la más importante de todas y vale entenderla bien: **la verificabilidad DEPENDE de la no ambigüedad, no al revés.**
>
> Si un requisito admite dos lecturas, **no hay un caso de prueba que lo verifique** — habría dos casos de prueba distintos, y no sabés cuál corresponde. Por eso el orden de trabajo importa: **primero desambiguar, después verificar.** Intentar hacer verificable un requisito ambiguo es trabajo perdido.

### Tipo 2 — Depende de CÓMO lo logres 🔴🔴

Este es el tipo más interesante, y el ejemplo que dan es excelente:

> **Un atributo puede afectar el logro de otro DEPENDIENDO DE LA MANERA en que se logre el primero.**
>
> **Por ejemplo: si tratamos de hacer un requisito más NO AMBIGUO, más VERIFICABLE, COMPLETO y CONSISTENTE USANDO NOTACIONES EXTREMADAMENTE FORMALES, definitivamente DISMINUIMOS EL NIVEL DE COMPRENSIBILIDAD** — especialmente por parte de los interesados que no son especialistas en informática.

**Pero la conclusión NO es que esos atributos se peleen:**

> **De ninguna manera los requisitos no ambiguos, verificables, completos y consistentes son INcomprensibles. Al contrario: la no ambigüedad, la completitud y la consistencia MEJORAN LA COMPRENSIBILIDAD cuando se logran por medios MENOS FORMALES** — como usar lenguaje natural aumentado con modelos más formales.

```
   no ambiguo + verificable + completo + consistente

        logrados con NOTACIÓN EXTREMADAMENTE FORMAL
             ↓
        BAJA la comprensibilidad

        logrados con LENGUAJE NATURAL + MODELOS
             ↓
        SUBE la comprensibilidad
```

> ⚠️ **Cruce con la cátedra — esta es la observación más valiosa del capítulo.** Dice algo que no es obvio: **el conflicto entre precisión y comprensibilidad NO ES INHERENTE — es consecuencia del medio que elegís.**
>
> Y le da fundamento a por qué tu materia trabaja como trabaja: **lenguaje natural aumentado con modelos** es exactamente la receta que este capítulo señala como la que mejora las dos cosas a la vez. Los casos de uso son eso: texto en el idioma del cliente, más un diagrama que le da estructura.
>
> Conecta con el capítulo 10 (los cinco motivos por los que se usa lenguaje natural) y con el capítulo 8 (los métodos formales son difíciles de entender para quien no tiene el trasfondo, y el cliente a menudo no está interesado en aprenderlos).

### Tipo 3 — Uno impide al otro 🔴

> **La existencia de un atributo PONE EN PELIGRO el logro de otro.**
>
> **Por ejemplo: si TODOS los casos de uso incluidos en un modelo fueran NECESARIOS, ¿POR QUÉ NECESITARÍAMOS CLASIFICAR alguno de ellos COMO OPCIONAL por importancia relativa?**

```
   NECESARIO ──se pelea con──► PRIORIZADO POR IMPORTANCIA

   si todo es necesario, no hay nada que priorizar
   si hay opcionales, no todo era necesario
```

> ⚠️ **Cruce con la cátedra.** Es una tensión lógica real y vale tenerla presente. Se resuelve reconociendo que **"necesario" y "opcional" no están en la misma escala**: necesario es respecto del producto final; opcional es respecto de *esta versión*.
>
> Pero el señalamiento sirve como control: **si en tu lista de requisitos hay muchos "opcionales", vale preguntarse si eran realmente requisitos** — o eran deseos que se colaron. Es la misma sospecha que el capítulo 13 planteaba con los requisitos "beta".

---

## 4. El mapa de relaciones 🟡

El capítulo produce dos tablas cruzando los veintiséis atributos entre sí. Estas son las relaciones que declaran, con la notación:

```
   +   fortalece el atributo relacionado
   −   debilita el atributo relacionado
   +?  PUEDE debilitar
   −?  PUEDE fortalecer
```

### Las relaciones de fortalecimiento 🔴

Las más relevantes:

| Este atributo… | …fortalece a |
|---|---|
| **Claro / preciso** | Completo (posiblemente) · Ejecutable |
| **Completo** | Ejecutable · Necesario · Organizado · Trazable hacia atrás |
| **Conciso** | En el nivel de detalle correcto · Independiente del diseño · Independiente de la implementación · No redundante |
| **Correcto** | Ejecutable · Externamente consistente · Internamente consistente · Necesario · Trazable hacia atrás |
| **Referenciado cruzadamente** | Almacenado electrónicamente |
| **Externamente consistente** | Trazable hacia adelante |
| **Modificable** | Referenciado cruzadamente · Almacenado electrónicamente · Trazable hacia adelante · Organizado · Trazable hacia atrás |
| **No ambiguo** | Claro / preciso · Verificable |
| **Comprensible** | Claro / preciso · Ejecutable · Organizado |
| **Verificable** | Alcanzable · Claro / preciso · No ambiguo |

### Las relaciones problemáticas 🔴

Y estas son las que conviene tener presentes:

| Este atributo… | …puede debilitar a | Por qué |
|---|---|---|
| **Conciso** | **Completo** | Ser breve puede costar dejar cosas afuera |
| **Modificable** | **Priorizado por importancia, por estabilidad y por versión** | Si el conjunto se organiza para poder modificarse fácil, no puede a la vez estar ordenado por prioridad |
| **Priorizado por importancia** | **Necesario** · las otras dos formas de priorización | La tensión lógica del tipo 3 |
| **Comprensible** | **No redundante** | Repetir mejora la lectura pero introduce redundancia |
| **No ambiguo** | **Almacenado electrónicamente · Ejecutable** (posiblemente) | — |

> ⚠️ **Cruce con la cátedra.** Dos de estas son directamente aplicables a un entregable:
>
> **Conciso contra completo.** Es el compromiso más común y el más fácil de errar en las dos direcciones. Un documento que se hace corto por prolijidad deja huecos; uno que se hace exhaustivo se vuelve ilegible. **El criterio no es cuál gana: es cuál de los dos está en riesgo en TU caso.**
>
> **Comprensible contra no redundante.** Esta es contraintuitiva y útil: **repetir información mejora la comprensión pero rompe la no redundancia** — y peor, crea riesgo de inconsistencia interna, porque al cambiar una aparición te podés olvidar de las otras. La salida que propone el propio capítulo es **usar referencias cruzadas en vez de repetir.**

---

## 5. La honestidad sobre la medición 🔴

Y una advertencia que conviene tener:

> **Finalmente, LA MAYORÍA DE LOS ATRIBUTOS SON SUBJETIVOS. En esos casos puede ser difícil medir una calidad objetivamente mediante métricas; puede requerir REVISIONES POR EXPERTOS para la evaluación última.**
>
> **Aun así, es posible ASOCIAR ESAS CARACTERÍSTICAS CON INDICADORES que apunten a la existencia o ausencia de la calidad en cuestión.**

> ⚠️ **Cruce con la cátedra.** Esa distinción entre **medir** y **tener un indicador** es la salida práctica al problema. No podés medir cuán comprensible es un documento; **sí podés contar cuántas frases débiles tiene**, y eso indica algo.
>
> Es lo que hace la Parte 3 de este capítulo: para cada atributo, en vez de una medida directa, **una métrica indirecta que apunta al problema.**

---

## 6. La tesis del capítulo 🔴

Antes de entrar a los atributos uno por uno, los autores enuncian su conclusión general:

> **Nuestras experiencias han probado que EL NIVEL DE CALIDAD LOGRADO EN LOS REQUISITOS DEPENDE ALTAMENTE DEL PROCESO ADOPTADO.**

Y desarman cómo un proceso puede influir sobre una calidad — **son cuatro casos, no dos:**

```
   1. llevando a una MEJORA de esa calidad
   2. DETRAYENDO de esa calidad
   3. HACIENDO LAS DOS COSAS → una situación de COMPROMISO
   4. NO ABORDANDO EN ABSOLUTO esa calidad
```

**Y el diagnóstico sobre el Proceso Unificado:**

> **Un requisito o un conjunto creado mediante este proceso PUNTUARÍA MUY BIEN en la mayoría de los atributos de calidad, y MÁS BIEN INSUFICIENTEMENTE EN OTROS.**
>
> **ADAPTAR las prácticas estándar para ajustarse a las necesidades de un proyecto específico AYUDA A MEJORAR la calidad pobre — pero principalmente EN AQUELLOS ATRIBUTOS QUE MÁS IMPORTAN AL PROYECTO.**

> ⚠️ **Cruce con la cátedra.** Los cuatro casos son un marco de análisis muy usable, y el cuarto es el que más se pasa por alto: **un proceso puede simplemente no decir nada sobre un atributo de calidad.** No lo mejora ni lo empeora — lo deja librado a lo que cada uno haga.
>
> Y eso es lo peligroso, porque **no se nota.** Un proceso que empeora algo genera quejas; uno que no lo aborda no genera nada, y el problema aparece recién en producción.
>
> La conclusión práctica: **al adoptar cualquier proceso, la pregunta útil no es "¿qué hace bien?" sino "¿qué no cubre?"** — y después decidir si eso que no cubre importa en tu caso.

---

## Mapa de la Parte 2

```
   26 ATRIBUTOS (contra los 10 del cap. 8)
   agrega: necesario · no redundante · conciso ·
   independiente del diseño y de la implementación ·
   organizado · reutilizable · referenciado cruzadamente
   · almacenado electrónicamente · ejecutable

   ─────────────────────────────────────────────

   LOS 3 PROBLEMAS AL COMPARAR FUENTES
   1. la misma cosa con NOMBRES DISTINTOS
      (alcanzable = factible = realizable)
   2. el mismo NOMBRE con contenidos distintos
      ("correcto" significa cosas distintas según quién)
   3. no se sabe si aplica al REQUISITO o al CONJUNTO

   ─────────────────────────────────────────────

   ══► LOS 3 TIPOS DE RELACIÓN ◄══

   1. UNO HACE FALTA PARA EL OTRO
      NO AMBIGUO es prerrequisito de VERIFICABLE
      → primero desambiguar, DESPUÉS verificar

   2. DEPENDE DE CÓMO LO LOGRES  ← la clave
      no ambiguo + completo + consistente
         con NOTACIÓN FORMAL → BAJA la comprensibilidad
         con LENGUAJE NATURAL + MODELOS → LA SUBE
      → el conflicto NO es inherente: es del medio

   3. UNO IMPIDE AL OTRO
      si todo es NECESARIO, ¿qué hay para PRIORIZAR?

   ─────────────────────────────────────────────

   LAS TENSIONES PRÁCTICAS
   conciso ↔ completo
   comprensible ↔ no redundante
     (salida: referencias cruzadas, no repetir)
   modificable ↔ priorizado

   ─────────────────────────────────────────────

   UN PROCESO PUEDE, RESPECTO DE UNA CALIDAD:
   mejorarla · detraerla · ambas (compromiso)
   · O NO ABORDARLA EN ABSOLUTO ← lo peligroso,
     porque no se nota
```

---

## Preguntas para chequear que quedó

1. ¿Cuántos atributos de calidad compilaron y cuántos tenía el capítulo 8?
2. Nombrá cuatro atributos que este capítulo agrega y que no estaban en el capítulo 8.
3. Explicá el primer problema al comparar fuentes con su ejemplo.
4. ¿Por qué el segundo problema es peor? ¿Con qué tipo de ambigüedad del capítulo 11 se conecta?
5. ¿Qué hicieron cuando dos fuentes usaban el mismo nombre para cosas distintas?
6. ¿Por qué es difícil saber si un atributo aplica al requisito individual o al conjunto? Dé el ejemplo.
7. ¿Qué atributo solo puede fallar en el conjunto y por qué?
8. Explicá el primer tipo de relación con el ejemplo de no ambiguo y verificable.
9. ¿Cuál es la consecuencia práctica de esa dependencia para el orden de trabajo?
10. Explicá el segundo tipo de relación. ¿Qué pasa si lográs la no ambigüedad con notación formal? ¿Y con lenguaje natural más modelos?
11. ¿Por qué el conflicto entre precisión y comprensibilidad no es inherente?
12. Explicá el tercer tipo de relación con el ejemplo de necesario y priorizado.
13. ¿Cómo se resuelve esa tensión lógica?
14. ¿Qué atributos fortalece la modificabilidad?
15. Explicá la tensión entre conciso y completo. ¿Cuál es el criterio para resolverla?
16. ¿Por qué la comprensibilidad puede debilitar la no redundancia? ¿Qué salida propone el capítulo?
17. ¿Por qué la mayoría de los atributos son difíciles de medir objetivamente? ¿Qué se usa en su lugar?
18. ¿Cuáles son los cuatro casos en que un proceso puede influir sobre una calidad?
19. ¿Cuál de los cuatro es el más peligroso y por qué?
20. ¿Qué pregunta conviene hacerse al adoptar un proceso?

---

**FIN DEL CAPÍTULO 17 — PARTE 2**

*Sigue en la Parte 3: la evaluación atributo por atributo — cómo se logró cada calidad en la práctica, qué aportó el proceso y qué no, y las métricas concretas que se usaron para medirlas.*
