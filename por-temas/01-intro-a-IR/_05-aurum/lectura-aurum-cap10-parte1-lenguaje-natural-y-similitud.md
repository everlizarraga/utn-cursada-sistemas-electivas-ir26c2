# Lectura en español — Cap. 10 · Parte 1: El lenguaje natural y la similitud de requisitos

> **Origen.** Capítulo 10, secciones 10.1 a 10.4, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Johan Natt och Dag** (Universidad de Lund, Suecia) y **Vincenzo Gervasi** (Universidad de Pisa, Italia).
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.

---

## Por qué este capítulo te sirve más de lo que su título sugiere

Se llama "gestión de grandes repositorios de requisitos en lenguaje natural" y suena a problema de empresa grande. Pero contiene **dos secciones que valen mucho para tu cursada**:

1. **La justificación de por qué los requisitos se escriben en lenguaje natural** y no en lenguajes formales — cinco razones, y una de ellas es la mejor distinción entre verificación y validación de todo el libro.
2. **El tratamiento de las abstracciones de dominio**: cómo los conceptos de un dominio se representan mediante **conjuntos de términos**, y por qué identificarlos es un factor de éxito. Es la base conceptual de lo que vas a hacer en la segunda mitad de la materia.

El resto es procesamiento de lenguaje natural aplicado a detectar requisitos duplicados. Interesante, no evaluable.

---

## 1. El problema 🟡

> **Las empresas dirigidas por el mercado y la tecnología que desarrollan productos de software cada vez más complejos terminan enfrentando el desafío de lidiar con flujos enormes de información que pueden desbordar sus capacidades de gestión y análisis.**
>
> **Los requisitos son particularmente difíciles de gestionar efectivamente por su naturaleza no estructurada.**

Cuando el volumen y el ritmo de llegada crecen, aparecen dos problemas específicos:

```
   · DETERIORO del repositorio de requisitos
   · DIFICULTAD CRECIENTE para identificar y mantener
     las interrelaciones entre requisitos
```

**Y la razón de fondo:**

> **Una razón mayor de estos problemas es que los requisitos se comunican en lenguaje natural, lo que induce varios problemas —imprecisión, ambigüedad, incompletitud, conflicto e inconsistencia— que llevan tiempo resolver.**

### La encrucijada 🟡

Las empresas que enfrentan esto llegan a un cruce de caminos donde la elección es **reducir el flujo de requisitos entrantes** o **asignar más recursos para manejarlos**. Y ninguna de las dos sirve:

| Opción | Por qué no funciona |
|---|---|
| **Cortar la elicitación** y la invención de requisitos nuevos | **Aumenta el riesgo de perder oportunidades de negocio** potenciales |
| **Agregar más gente** al trabajo | **Se demostró que es demasiado caro y a veces contraproducente** |

**La propuesta del capítulo:** un enfoque de ingeniería lingüística basado en técnicas de recuperación de información, donde **se calculan similitudes entre requisitos para indicar el solapamiento semántico**.

---

## 2. Por qué los requisitos se escriben en lenguaje natural 🔴🔴

Esta sección es la más aprovechable del capítulo. Arranca con una constatación:

> Un relevamiento reciente confirma que **los requisitos se escriben y se comunican, en muy gran medida, en lenguaje natural.** Y aun así, después de años de investigación fructífera sobre cómo especificarlos y formularlos mejor, **el estado de la práctica es, en general, que las guías de calidad de requisitos rara vez se aplican.**
>
> **Hay una gran brecha entre los modelos formales que muchos investigadores promueven y la informalidad que domina en la industria.**

Y después dan **cinco razones** de por qué los requisitos se especifican inicialmente en lenguaje natural y en muchos casos se mantienen así todo el desarrollo.

### Razón 1 — Es el idioma compartido 🔴

> **El lenguaje natural es el idioma primario de comunicación, compartido por todos los interesados y participantes del proceso de desarrollo.**
>
> **Los lenguajes formales requieren entrenamiento específico, que es poco realista esperar de todo interesado, y en particular de los clientes o usuarios finales.**

### Razón 2 — Es universal 🔴

> La IR es **un proceso social y evolutivo**, donde los requisitos se elicitan y especifican **a distintos niveles de abstracción en distintos momentos** del desarrollo.
>
> **El lenguaje natural es universal**: puede usarse para hablar de **dominios arbitrarios y a niveles de abstracción arbitrarios. Muchos lenguajes formales no tienen esa fortaleza.**

### Razón 3 — Formalizar lo que se va a descartar no rinde 🟡

> **En desarrollo a gran escala, comparativamente pocos de los requisitos propuestos se seleccionan realmente para implementación.** Como no se espera implementarlos todos, **hay poca motivación para gastar tiempo formalizándolos.**

Y agregan de su experiencia: **las empresas que valoran la interacción cercana con sus clientes y la reacción rápida a las condiciones cambiantes del mercado no encuentran costo-beneficioso traducir todos los requisitos a especificaciones formales.**

### Razón 4 — Lo formal no tolera lo incompleto 🔴

> **Muchos métodos formales no ofrecen ningún soporte para la gestión y el análisis de requisitos erróneos, incompletos o parcialmente especificados.**
>
> **En contraste, las técnicas de lenguaje natural se adaptan naturalmente a esas situaciones, que en la práctica constituyen una gran parte del ciclo de vida de un requisito.**

> Esta razón es más profunda de lo que parece. Un requisito **empieza siendo incompleto y ambiguo** — es su estado natural en las primeras semanas. Un lenguaje que solo admite enunciados bien formados **no puede usarse hasta que ya no lo necesitás**.

### Razón 5 — Verificación contra validación 🔴🔴

Y esta es la mejor de las cinco, porque contiene la distinción más precisa de todo el libro entre dos palabras que se confunden:

> **Si bien los lenguajes formales pueden mejorar nuestra capacidad de chequear la consistencia interna y la completitud de los requisitos** —proceso al que se llama a menudo **verificación**— **no pueden capturar las propiedades externas de los requisitos**, por ejemplo **la correspondencia entre los requisitos y las intenciones reales del usuario.**
>
> **Verificar esas propiedades —la validación— requiere buena comunicación e interacción con los interesados. Y para ese fin, el lenguaje natural es un idioma más adecuado.**

```
   VERIFICACIÓN
   ¿es el documento consistente consigo mismo y completo?
   → pregunta INTERNA
   → los lenguajes formales ayudan mucho

   VALIDACIÓN
   ¿se corresponde con lo que el usuario realmente quiere?
   → pregunta EXTERNA
   → solo se responde HABLANDO CON GENTE
   → el lenguaje natural es mejor herramienta
```

> ⚠️ **Cruce con la cátedra — retené esta distinción.** Es la formulación más limpia de verificación vs. validación que vas a encontrar, y explica **por qué la materia trabaja con lenguaje natural y UML y no con lógica formal**.
>
> Un documento puede estar **perfectamente verificado** —sin contradicciones internas, completo respecto de su propia estructura— **y estar completamente mal validado**, porque describe un sistema que nadie quería. La consistencia interna no garantiza nada sobre el mundo.
>
> Conecta además con el capítulo 8: allí los **enfoques analíticos** enfrentaban el problema de que "no hay un documento de referencia contra el cual comparar los requisitos". Acá está la razón: **la referencia son las personas**, y a las personas se les habla en lenguaje natural.

### La conclusión de la sección 🔴

> **Así, pese a sus deficiencias reconocidas y afamadas, hay pocos incentivos para evitar el lenguaje natural. Deberíamos entonces esperar que su uso no pueda escaparse.**

Y citan a Michael Jackson con una frase que resume el campo:

> **La ingeniería de requisitos es donde lo informal se encuentra con lo formal.**

**La consecuencia práctica:** la brecha entre las necesidades de los usuarios y una versión nueva del sistema **debe salvarse usando métodos y técnicas que reconozcan, de alguna forma, la comunicación en lenguaje natural.**

---

## 3. Qué se investigó y qué se puede esperar 🟡

### La advertencia sobre las expectativas 🔴

Antes de repasar la investigación, los autores traen una advertencia importante:

> **Hubo muchas expectativas poco realistas sobre las técnicas de procesamiento de lenguaje natural**, dado el deseo de un sistema que pudiera sostener las actividades actualmente caras de la IR.
>
> **Esas expectativas se basan típicamente en concepciones erróneas sobre cuál es realmente el problema de comunicación en la IR industrial**, y sobre **hasta qué punto los requisitos de un sistema están disponibles en forma textual.**

Y la conclusión que recogen, que vale la pena:

> **La IR es un proceso social, y las técnicas lingüísticas pueden tener éxito solo en un papel de APOYO a ese proceso — no intentando reemplazarlo.**

La investigación se agrupa en **tres actividades**: entendimiento del dominio y de los requisitos · verificación y validación · gestión de requisitos.

### 3.1 Entendimiento del dominio: las abstracciones 🔴🔴

Esta subsección es la que más te sirve de todo el capítulo.

> **Una tarea central en el entendimiento del dominio y de los requisitos es identificar y entender los CONCEPTOS DEL DOMINIO, también llamados ABSTRACCIONES DEL DOMINIO.**
>
> **Las abstracciones del dominio son conceptos generales que se forman para representar características comunes de instancias específicas del dominio.**

Y lo que sigue es la parte clave:

> **Las abstracciones del dominio vuelven más eficiente la comunicación dentro del dominio. Pero los desarrolladores deben tener en cuenta no solo el concepto general, sino también las instancias específicas, para entender plenamente las abstracciones.**
>
> **Las abstracciones del dominio se representan típicamente en lenguaje natural mediante CONJUNTOS DE TÉRMINOS — a menudo sustantivos y frases nominales.**

Por eso los investigadores estudiaron técnicas para **extraer esos términos** —que representan las abstracciones— **del discurso generado a partir de transcripciones de entrevistas y de deseos de clientes expresados en lenguaje natural.**

> ⚠️ **Cruce con la cátedra — el más importante del capítulo.** Leé de nuevo ese bloque y compará con lo que vas a hacer en las clases 10 a 14.
>
> **La afirmación de que las abstracciones del dominio se representan mediante conjuntos de términos, y que hay que capturar tanto el concepto general como sus instancias específicas, es exactamente el fundamento conceptual de un léxico del dominio.** Este capítulo no describe el artefacto que vas a construir —eso es tradición de Leite y Doorn, y no está en el libro— pero **sí describe el problema que ese artefacto resuelve** y por qué se resuelve con términos y no con otra cosa.
>
> Y notá el detalle de que **son sobre todo sustantivos y frases nominales**. Los verbos vienen después, cuando se describe qué se hace con esas entidades. La entrada al dominio son los nombres de las cosas.
>
> También conecta hacia atrás: en el capítulo 6, el **factor de impacto M3** decía que *cambiar el vocabulario del dominio genera cambios grandes en la arquitectura*. Acá está el otro lado: **ese vocabulario es lo primero que hay que identificar.**

**Qué se investigó concretamente:** herramientas que sugieren abstracciones al elicitador humano comparando oraciones y extrayendo fragmentos coincidentes; etiquetadores gramaticales y semánticos que ayudan a identificar y analizar abstracciones; y **análisis de colocaciones** para producir mapas de las entidades clave.

### 3.2 Verificación y validación 🔴

> **Se reconoce generalmente que gastar más tiempo en las etapas de verificación y validación, y encontrar errores temprano, es más redituable que proceder demasiado pronto a la codificación.**

Y una observación de método:

> **Las dos actividades no se llevan a cabo por separado.** Chequear un conjunto de requisitos puede revelar **inconsistencias internas que pueden ser también externas**, y que deben resolverse con un interesado.

**Los indicadores de calidad.** Se derivaron **siete indicadores de calidad** para medir la calidad de las especificaciones de requisitos, que se usaron para desarrollar una herramienta empleada por la NASA. Otros grupos propusieron modelos de calidad similares con herramientas propias.

**Y el hallazgo que importa:** un grupo aplicó dos de esas herramientas para evaluar la calidad de **100 casos de uso**. Su conclusión:

> **Aunque las técnicas pueden apoyar la evaluación de calidad, NO SON SUFICIENTES para abordar completamente la corrección y la consistencia.**

**Los lenguajes restringidos.** Varios investigadores propusieron **restringir explícitamente el lenguaje usado en los requisitos**. La ventaja sugerida:

> **Puede ser usado por especialistas del dominio que quieren los beneficios de los lenguajes formales pero carecen del entrenamiento requerido.**

Las variantes van escalando: usar **un subconjunto del inglés que prohíbe expresar oraciones ambiguas** · definir **una sintaxis y gramática de inglés restringido** · y una que va un paso más allá y **restringe el lenguaje y la semántica a un estilo de escenario**, más entendible por el usuario que una especificación formal.

> ⚠️ **Cruce con la cátedra.** El "estilo de escenario" como forma de restringir el lenguaje manteniéndolo legible es exactamente la lógica de los artefactos estructurados que usa tu materia. **Una plantilla no es burocracia: es un lenguaje restringido que reduce la ambigüedad sin pedirle al cliente que aprenda lógica.**

**Los intentos de transformación automática.** Varios trabajos intentaron **transformar requisitos en lenguaje natural en modelos de objetos**. Y los autores señalan que **todos sufren los mismos problemas comunes**:

```
   · limitaciones del analizador sintáctico
   · ambigüedad
   · incompletitud
   · conocimiento del dominio y reglas de transformación
     insuficientes
```

### 3.3 Gestión de requisitos 🟡

> **Los requisitos se elicitan y llegan de muchas fuentes distintas y cambian constantemente. Cuando llegan numerosos requisitos cada mes —sea en ráfagas de miles o continuamente 3 a 5 por día— la importancia de actividades apropiadas de gestión se vuelve muy evidente.**

**Qué ofrecen las herramientas actuales:** almacenar y recuperar requisitos, anotarlos con metadatos, y gestionar relaciones entre requisitos. Indexado, búsqueda por palabras clave y búsqueda sobre metadatos.

**Y su limitación:**

> **Desafortunadamente, la gestión de relaciones se limita casi siempre a establecer manualmente vínculos entre pares de requisitos.** Algunos tipos de vínculo pueden declararse como **frágiles**: cualquier cambio en uno de los requisitos vinculados **marca el vínculo como roto hasta que el usuario lo verifica y lo restablece manualmente.**

**Las cuatro actividades que quedan sin soporte:**

```
   · EMPAREJAR requisitos entrantes con los ya elicitados,
     planificados e implementados
   · MANTENER LA SEPARACIÓN y encontrar relaciones entre
     pedidos de clientes y requisitos inventados dentro
     de la organización
   · IDENTIFICAR DEPENDENCIAS e interrelaciones
   · EXTRAER del repositorio los requisitos que encajan
     en áreas estratégicas
```

---

## 4. La similitud entre requisitos 🟡

### La idea

> **Una cantidad de problemas en la gestión de grandes volúmenes de requisitos pueden resolverse, o al menos aliviarse, usando una medida de cuán similares son dos requisitos.**

En la mayoría de los problemas lo que hace falta es **similitud semántica**: una medida de **si dos requisitos transmiten el mismo significado, y en qué medida**. Pero se pueden usar otras nociones:

| Medida de similitud | En qué se parecen |
|---|---|
| **Semántica** | En el **significado** |
| **Sintáctica** | En la **estructura gramatical** |
| **Léxica** | En **las palabras usadas** |
| **Estructural** | En la **estructura de secciones** |
| **Extensional** | En el **tamaño** |
| **Argumentativa** | En la **justificación** |
| **De meta** | En el **objetivo** |
| **De fuente** | En **quién la propuso** |
| **De función** | En la **función que atienden** |
| **De objeto** | En las **partes del sistema afectadas** |
| **Temporal** | En el **momento de origen** |

### La restricción que decide todo 🟡

> Cualquiera sea la medida elegida, para ser aplicable debe poseer una propiedad fundamental: **tiene que ser computable de manera relativamente barata.**
>
> **Cualquier medida que requiera intervención humana significativa va a ser demasiado costosa** para usarse en repositorios grandes. Estamos forzados, entonces, **a enfocarnos en medidas que puedan computarse de manera totalmente automática.**

**Y el compromiso que eso obliga:**

> Dado el estado del arte actual, **no es factible extraer el significado de manera confiable de texto en lenguaje natural totalmente irrestricto**, como el que se encuentra en la mayoría de los requisitos. **Nos enfocamos por lo tanto en la SIMILITUD LÉXICA como una manera de APROXIMAR la similitud semántica.**

> Es un compromiso explícito y honesto: **no pueden medir el significado, así que miden las palabras** y aceptan que es una aproximación. La pregunta de todo el capítulo es cuán buena resulta esa aproximación en la práctica.

### El procesamiento del texto 🟢

Los pasos que aplican:

**1. Segmentación en unidades** (*tokenización*). Separar los constituyentes léxicos del requisito. Cada palabra en sentido amplio se llama **unidad léxica**. En los casos que presentan, **una unidad es una secuencia de letras y/o dígitos; cualquier otro carácter se considera delimitador y se descarta.**

**2. Reducción a la raíz** (*stemming*). Reducir las unidades a su forma base, **quitando las flexiones morfológicas** — reducir plurales a singular, o quitar persona, modo y aspecto de los verbos. Se hace con **reglas morfológicas generales más un diccionario de excepciones**.

**3. Eliminación de palabras vacías.** Descartar **todas las palabras que tienen un papel puramente gramatical**. La información gramatical que transmiten puede guardarse en otra forma antes de eliminarlas. **En la mayoría de los casos, las palabras vacías coinciden con las llamadas palabras de clase cerrada**: artículos y preposiciones. Usaron una lista de **425 palabras**.

**4. Representación como vector.** Si no se considera importante el orden, un requisito puede representarse como **un vector de pesos**, donde cada peso denota **la importancia relativa de cada unidad léxica en ese requisito**.

Sobre los pesos, una decisión razonada:

> **Como los requisitos expresados en estilo de característica están más enfocados que un texto literario, asumimos que las unidades que quedan después del preprocesamiento son todas igualmente valiosas.**

En el caso más simple **el peso coincide con la frecuencia**. Pero como se considera que **la importancia de una unidad no es linealmente proporcional a la cantidad de veces que aparece**, en los casos posteriores usan una fórmula logarítmica.

**5. La medida del coseno.** Una vez representados como vectores, se aplican medidas estándar. Compararon tres, y eligieron **la del coseno**, que **calcula el coseno del ángulo entre los vectores** que representan los requisitos.

Y una limitación que declaran explícitamente:

> La definición asume un espacio vectorial con **distancia uniforme en todas las dimensiones**. Eso es, por supuesto, **una simplificación grosera**: en la práctica, **la presencia o ausencia de ciertos términos puede ser mucho más importante y reveladora de la verdadera similitud semántica que la de otros.**
>
> Sin embargo, como nos interesan técnicas que funcionen **independientemente del dominio y del idioma exactos**, aceptamos esa simplificación, teniendo en cuenta que pueden emplearse técnicas más refinadas en dominios específicos.

---

## Mapa de la Parte 1

```
   EL PROBLEMA
   volumen + ritmo de llegada → deterioro del repositorio
   las dos salidas obvias no sirven:
     cortar el flujo → se pierden oportunidades
     poner más gente → caro y contraproducente

   ─────────────────────────────────────────────

   ══► POR QUÉ LENGUAJE NATURAL ◄══

   1. es el IDIOMA COMPARTIDO por todos los interesados
   2. es UNIVERSAL: cualquier dominio, cualquier nivel
      de abstracción
   3. formalizar lo que se va a descartar no rinde
   4. lo formal NO TOLERA lo incompleto — y los
      requisitos nacen incompletos
   5. VERIFICACIÓN ≠ VALIDACIÓN
      verificar = consistencia INTERNA → lo formal ayuda
      validar = corresponde con lo que el usuario quiere
                → solo hablando con gente

   "la IR es donde lo informal se encuentra con lo formal"

   ─────────────────────────────────────────────

   ══► ABSTRACCIONES DEL DOMINIO ◄══
   conceptos generales que representan características
   comunes de instancias específicas
   → se representan mediante CONJUNTOS DE TÉRMINOS
     (sobre todo sustantivos y frases nominales)
   → hay que capturar el concepto general Y las
     instancias específicas

   ─────────────────────────────────────────────

   SIMILITUD
   11 medidas posibles · la que hace falta es la
   SEMÁNTICA · pero solo se puede computar barato
   la LÉXICA → se la usa como aproximación
   pasos: tokenizar · reducir a raíz · quitar palabras
   vacías · vectorizar · medida del coseno
```

---

## Preguntas para chequear que quedó

1. ¿Qué dos problemas específicos aparecen cuando crecen el volumen y el ritmo de llegada de requisitos?
2. ¿Cuáles son las dos salidas obvias al problema y por qué ninguna funciona?
3. Nombrá las cinco razones por las que los requisitos se escriben en lenguaje natural.
4. ¿Por qué el lenguaje natural es "universal" en un sentido que los lenguajes formales no?
5. ¿Por qué los métodos formales no sirven para requisitos incompletos o parcialmente especificados?
6. Diferenciá verificación de validación. ¿Cuál puede sostener un lenguaje formal y cuál no? ¿Por qué?
7. ¿Puede un documento estar bien verificado y mal validado? Explicá.
8. ¿Qué quiere decir Jackson con que "la IR es donde lo informal se encuentra con lo formal"?
9. ¿Qué son las abstracciones del dominio y cómo se representan en lenguaje natural?
10. ¿Por qué no alcanza con tener el concepto general de una abstracción?
11. ¿Qué tipo de palabras representan típicamente las abstracciones del dominio?
12. ¿Cuál es el papel que las técnicas lingüísticas pueden cumplir en la IR, y cuál no?
13. ¿Qué concluyó el estudio que evaluó 100 casos de uso con herramientas automáticas de calidad?
14. ¿Cuál es la ventaja sugerida de usar un lenguaje restringido?
15. Nombrá los cuatro problemas comunes de los intentos de transformar lenguaje natural en modelos de objetos.
16. ¿Qué es un vínculo "frágil" en una herramienta de gestión de requisitos?
17. Nombrá cinco medidas de similitud distintas de la semántica.
18. ¿Qué propiedad fundamental debe tener una medida de similitud para servir en repositorios grandes?
19. ¿Por qué usan similitud léxica si lo que necesitan es similitud semántica?
20. Describí los tres pasos de preprocesamiento del texto.
21. ¿Qué simplificación admiten los autores en su medida, y por qué la aceptan igual?

---

**FIN DEL CAPÍTULO 10 — PARTE 1**

*Sigue en la Parte 2: los tres casos de estudio industriales —detectar duplicados en un repositorio, vincular deseos de clientes con requisitos de producto, y manejar pedidos redundantes de operadores de telefonía— con sus resultados medidos, más las conclusiones del capítulo.*
