# Lectura en español — Cap. 18 · Parte 2: Qué encontraron

> **Origen.** Capítulo 18, secciones 18.4 a 18.7, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Tony Gorschek y Mikael Svahnberg**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1.** Se asumen conocidas las seis empresas y los dos métodos de evaluación.

---

## Lo que hay acá

Los resultados. Y son útiles por una razón simple: **muestran qué prácticas de la teoría la industria efectivamente no hace** — y como las seis empresas son competentes en lo suyo, **lo que fallan sistemáticamente probablemente sea difícil, no descuidado.**

Vale leerlo mirando tu propio trabajo: **las seis carencias que encontraron son exactamente las que se te van a colar a vos.**

---

## 1. Las seis carencias 🔴🔴

Estas son las áreas donde **la mitad o más de las empresas tenían margen de mejora.**

### 1.1 Especificación y descripción de requisitos

> **Los requisitos resultaron especificados HETEROGÉNEAMENTE dentro de cada especificación y entre especificaciones distintas, ya que NO SE USABA NINGUNA PLANTILLA ESTANDARIZADA ni un conjunto mínimo de atributos.**

**Presente en:** Beta, Gamma, Delta, Epsilon, Zeta — **cinco de seis.**

### 1.2 Cuantificación de requisitos 🔴

> **Los requisitos de calidad (no funcionales) RARA VEZ SE EXPRESABAN EN FORMA VERIFICABLE** — por ejemplo, con un criterio de ajuste cuantificado.

**Presente en:** Alfa, Beta, Gamma, Epsilon, Zeta — **cinco de seis.**

> ⚠️ **Cruce con la cátedra.** Esta es la que más te conviene retener: **cinco de seis empresas competentes escribían requisitos no funcionales sin número.**
>
> No es descuido. Es que **poner el número es difícil** — hay que saber cuánto es suficiente, y eso exige conocimiento del dominio que a veces no está en la sala. Es exactamente el caso del capítulo 17: *"debe tener un tiempo de cómputo rápido"* necesitó tres rondas de preguntas para convertirse en *"no debe ser mayor a 6,0 ms"*.
>
> **Si en tu TP los requisitos no funcionales no tienen número, estás en compañía de cinco de seis empresas.** Lo cual no los hace correctos — pero sí explica por qué la cátedra insiste tanto.

### 1.3 Justificación de requisitos y decisiones 🔴

> **La justificación detrás de los requisitos —que responde por qué un requisito es relevante— RARA VEZ SE ESPECIFICABA.**
>
> Además, **las decisiones tomadas por ingenieros y gerencia respecto de los requisitos RARA VEZ SE DOCUMENTABAN y se difundían** a todas las partes del grupo de desarrollo.
>
> **Un ejemplo: el motivo para RECHAZAR un requisito no se documentaba.**

**Presente en:** Delta, Epsilon, Zeta — **tres de seis.**

> ⚠️ **Cruce con la cátedra.** El ejemplo del rechazo no documentado es el más concreto: **si no se registra por qué se rechazó algo, ese algo va a volver a proponerse.** Y de hecho eso es exactamente lo que encontraron en la evaluación en profundidad, como vas a ver más abajo.

### 1.4 Trazabilidad 🔴

> **Las políticas y estructuras para trazar requisitos a menudo faltaban** — por ejemplo, trazar requisitos a componentes de diseño, o componentes de diseño a requisitos.
>
> Además, **el versionado y la trazabilidad de versiones estaban EN EL MEJOR DE LOS CASOS A NIVEL DE DOCUMENTO** (teniendo versiones de la especificación). **El versionado DE LOS REQUISITOS MISMOS era raro.**

**Presente en:** Alfa, Gamma, Epsilon, Zeta — **cuatro de seis.**

> ⚠️ **Cruce con la cátedra.** La distinción entre **versionar el documento** y **versionar los requisitos** es fina y práctica. Tener "especificación v3" no te dice qué requisito cambió entre la v2 y la v3 — para saberlo hay que abrir las dos y comparar.
>
> Es la misma carencia que causaba el problema del capítulo 10 en el caso de los operadores de telefonía: **historial de revisiones no confiable → hay que revisar todo de nuevo desde cero.**

### 1.5 Evaluación de riesgos y requisitos volátiles 🟡

> **La evaluación de riesgos basada en requisitos no se privilegiaba. Como resultado, NO HABÍA ESFUERZO ACTIVO POR IDENTIFICAR Y MONITOREAR LOS REQUISITOS VOLÁTILES** — por ejemplo, los propensos a mucho cambio, o los que exigen implementar tecnología nueva o desconocida.

**Presente en:** Alfa, Beta, Gamma, Zeta — **cuatro de seis.**

### 1.6 Revisión de requisitos 🔴

> **Después de la especificación inicial, LAS REVISIONES DE REQUISITOS NO ERAN PRÁCTICA COMÚN. Esto era cierto para TODOS los tipos de revisión**, desde las informales hasta las formales.

**Presente en:** Alfa, Beta, Gamma, Epsilon, Zeta — **cinco de seis.**

**Y en la evaluación en profundidad encontraron por qué:**

> No eran práctica común **principalmente POR RESTRICCIONES DE COSTO Y TIEMPO durante el desarrollo.** Además había **insuficiencias en la "infraestructura de revisión"**: falta de gente entrenada para planificar y conducir revisiones, y falta de materiales como listas de verificación.

> ⚠️ **Cruce con la cátedra.** Este hallazgo es importante porque **el capítulo 8 mostraba que las inspecciones son de los enfoques más costo-efectivos que existen** — y sin embargo cinco de seis empresas no las hacen.
>
> La razón que dan es reveladora: **no es que no crean que sirven; es que no tienen la infraestructura.** Nadie entrenado para moderarlas, ninguna lista de verificación preparada. **La práctica más rentable del libro no se adopta porque falta el andamiaje para hacerla.**
>
> Y eso da valor a algo que tu materia sí tiene: **la rúbrica colaborativa es exactamente ese andamiaje faltante.** Es la lista de verificación que estas empresas no tenían.

---

## 2. Las tres cosas que sí hacían bien 🔴

Y acá está el contrapeso, que los autores destacan porque **contradice a varios relevamientos previos.**

### 2.1 Consideración del dominio 🔴

> A medida que los requisitos se elicitan y especifican, **se toman en cuenta las cuestiones del dominio objetivo del sistema.** Esto incluye: **aspectos técnicos del entorno operativo futuro, interacciones con otros sistemas y personal, y restricciones impuestas por factores como el entorno, las leyes y las regulaciones.**

### 2.2 Priorización de requisitos 🔴

> **TODAS las empresas priorizaban los requisitos.**

**Pero con un matiz honesto:**

> Esto **no quiere decir que se adoptara ningún método formal de priorización**, sino más bien que **la priorización tenía lugar, dándole a los requisitos algún tipo de atributo que denotara su importancia.**
>
> **Los métodos usados y la regularidad variaban muchísimo:** desde tener **un grupo formal de control con participación de clientes**, hasta **prácticas improvisadas donde un gerente tomaba las decisiones finales.**

### 2.3 Validación mediante modelos 🟡

> **El uso de modelos para elicitar y validar requisitos era bastante común, aunque principalmente DESDE UNA PERSPECTIVA TÉCNICA** — por ejemplo, usando modelos arquitectónicos para ver el sistema entero, sus subsistemas, y los vínculos entre ellos.

---

## 3. Los ocho hallazgos de la evaluación profunda 🔴

En las dos empresas donde se hizo la evaluación inductiva, aparecieron ocho hallazgos. **Cinco confirman lo anterior; tres son nuevos.**

### Los que confirman

**Nivel de abstracción y contenido de los requisitos.**

> **El nivel de abstracción, contenido y detalle VARIABA ENTRE DOCUMENTOS DEL MISMO TIPO, E INCLUSO DENTRO DEL MISMO DOCUMENTO.**

**Contexto, beneficio y justificación del requisito.**

> Especificar este atributo **se sintió como un paso lógico al preguntar "POR QUÉ" debería especificarse un requisito — algo que a menudo faltaba.** Al enunciar el contexto y el porqué, **y especificar los BENEFICIOS NO OBVIOS para los interesados, puede ofrecerse un entendimiento más completo a todos los que lean los requisitos después.**

**Trazabilidad.** Considerada deficiente en ambas empresas.

**Revisiones y su soporte.**

> **Ambas empresas SE DABAN CUENTA de que arreglar defectos temprano ahorra tiempo y esfuerzo más adelante; sin embargo FALTABAN LAS RUTINAS Y LA ESTRUCTURA.** Se identificó que hacía falta **construir y poner a disposición el soporte: entrenamiento de revisores y moderadores, listas de verificación formales, y métodos sobre cómo y cuándo conducir cada tipo de revisión.**

**Verificación y validación contra los requisitos.**

> **Las pruebas no siempre se conducían basándose en los requisitos relevantes**, sino a veces de manera improvisada, y a veces **basándose en especificaciones funcionales suministradas por los desarrolladores.**
>
> Se identificó como crucial que **el sistema se pruebe CONTRA LOS REQUISITOS —los cuales a su vez tienen que mantenerse actualizados—** y que **los requisitos estén disponibles para los probadores ANTES de entrar en la fase de pruebas**, para que puedan desarrollarse los planes y casos de prueba.

> ⚠️ **Cruce con la cátedra.** Esa práctica de probar contra **especificaciones funcionales escritas por los desarrolladores** es un círculo cerrado: **el que construyó define contra qué se prueba lo que construyó.** Cualquier malentendido de requisitos queda invisible, porque la prueba hereda el mismo malentendido.
>
> Es el mismo problema que el capítulo 10 señalaba sobre verificación contra validación: **se verifica que el sistema hace lo que el desarrollador entendió, no lo que el usuario quería.**

### Los tres hallazgos nuevos 🔴

**Roles y responsabilidades en el proceso.**

> **En la mayoría de las evaluaciones había ALGUNAS descripciones de roles e incluso de responsabilidades. Esos roles, sin embargo, RARA VEZ SE USABAN O ERAN CONOCIDOS por toda la organización.**
>
> **La confusión sobre responsabilidades y sobre A QUIÉN ELICITARLE INFORMACIÓN, así como la incertidumbre sobre QUIÉN TIENE PODER EJECUTIVO SOBRE LOS REQUISITOS, generaba confusión y PÉRDIDA DE IMPULSO durante el desarrollo.**

> ⚠️ **Cruce con la cátedra.** Notá que el problema **no es que los roles no existan: es que existen en un documento y nadie los conoce.** Y las dos preguntas que quedan sin respuesta son muy concretas: *¿a quién le pregunto?* y *¿quién decide?*
>
> Es exactamente lo que el capítulo 7 llamaba **interesados críticos para el éxito**: los que pueden acordar Y sostener el acuerdo. Sin eso claro, se negocia con quien no puede decidir.

**Mantener el historial de requisitos y decisiones.**

> Como muchos requisitos **se manejaban en múltiples proyectos y abarcaban múltiples productos, las decisiones tomadas sobre ellos NO SE DOCUMENTABAN sistemática ni regularmente** ni se vinculaban explícitamente al requisito relevante.
>
> **La implicancia: ALGUNOS REQUISITOS SE ESCUDRIÑABAN VARIAS VECES — por ejemplo, TENÍAN QUE DESCARTARSE MÁS DE UNA VEZ.** Otra implicancia: la información sobre el análisis y las decisiones **no era fácilmente accesible por los desarrolladores.**

> ⚠️ **Cruce con la cátedra — este hallazgo es muy concreto y muy citable.** *"Tenían que descartarse más de una vez"* es el costo exacto de no documentar los rechazos, medido en trabajo repetido.
>
> Es el mismo mecanismo que el capítulo 5 describía como **pérdida de conocimiento**, pero con una manifestación más tonta: no se pierde porque alguien se fue, **se pierde porque nadie lo anotó, y el mismo grupo vuelve a discutir lo mismo.**

**Mantenimiento de los requisitos durante y después del proyecto.**

> **Frecuentemente, a medida que los requisitos reales cambiaban durante el ciclo de vida, LAS ESPECIFICACIONES NO SE CAMBIABAN para reflejarlo. Los cambios de diseño no llevaban a actualizaciones de la especificación**, causando eventualmente que **la especificación NO REFLEJARA EL ESTADO ACTUAL DEL SISTEMA.**
>
> **En los proyectos y empresas estudiadas, los requisitos desactualizados que reflejaban pobremente el estado del sistema eran, desafortunadamente, FRECUENTES.**

**Por qué eso importa —tres razones que dan:**

```
   · es PRERREQUISITO para poder hacer pruebas basadas
     en los requisitos
   · hace falta para lograr cualquier REUTILIZACIÓN
   · hace falta para poder RE-PRIORIZAR
```

> ⚠️ **Cruce con la cátedra.** Acá se cierra un círculo con el capítulo 6: allí los desarrolladores decían *"el código, en cambio, siempre está actualizado"* como razón para desconfiar de los modelos. **Este capítulo muestra que tenían razón** — la especificación efectivamente se desactualiza, y el cambio entra por el diseño sin subir nunca a los requisitos.
>
> Es exactamente lo que el capítulo 6 llamaba **no gestionar jerárquicamente**: el cambio entra por abajo y la especificación queda mintiendo.

---

## 4. La comparación con otros relevamientos 🟡

Los autores cruzan sus hallazgos contra cinco relevamientos independientes. Lo interesante es que **no todo coincide.**

### Lo que se confirma

| Hallazgo | Confirmado por |
|---|---|
| **Insuficiencia en documentar requisitos, supuestos y justificación** | Varios relevamientos |
| **Requisitos volátiles y necesidad de gestionar la incertidumbre** | Tres relevamientos |
| **Falta de trazabilidad** | Dos relevamientos |
| **Necesidad de completitud, plantillas y listas de verificación** | Un relevamiento de doce empresas |
| **Rupturas de comunicación** | Varios |

### Lo que se contradice 🔴

Y acá está lo más interesante:

> **Contradiciendo uno de los estudios, las empresas de nuestras evaluaciones TIENEN UN BUEN MANEJO DE SUS CLIENTES Y DE LOS REQUISITOS DE SU DOMINIO, REALIZAN PRIORIZACIÓN de requisitos, NO USAN CONSISTENTEMENTE NINGUNA PLANTILLA, y CARECEN de rutinas y soporte adecuados para revisiones.**

Y contra otro relevamiento:

> **Los requisitos rápidamente cambiantes y la falta de trazabilidad se reconocen en ambos estudios. Por otro lado, los esfuerzos de verificación y validación NO estaban difundidos en nuestras evaluaciones. Y la priorización SÍ se realizaba, contradiciendo** al otro estudio.

**Y una observación sobre las herramientas:**

> La mayoría de las organizaciones **usa herramientas como PROCESADORES DE TEXTO para especificar requisitos.** Para proyectos grandes **con más de 1.000 requisitos eso causa problemas**, y las organizaciones que sí usan herramientas de requisitos **en general trabajan con aplicaciones más grandes.**

**Y una preferencia declarada por parte de las empresas:**

> **Los métodos inductivos parecen ser preferibles a las actividades de mejora prescriptivas basadas en modelo**, como indica la disposición a mejorar **pero prefiriendo SOLUCIONES ADAPTADAS por sobre prácticas prescriptivas.**

---

## 5. Los cinco temas que atraviesan todo 🔴

En la discusión, los autores destilan los hallazgos en temas. Estos son los más desarrollados.

### 5.1 Especificación y nivel de abstracción 🔴🔴

Este es el más elaborado del capítulo y el más aplicable.

**Qué es el problema:**

> Consiste en varios aspectos de cómo se especifican los requisitos: **los atributos usados** (nombre, descripción, identificador) y **el nivel de detalle de cada uno.**
>
> Estrechamente relacionado está **el NIVEL DE ABSTRACCIÓN.** Por ejemplo, *"soporte para múltiples idiomas en la interfaz"* **es más abstracto que** *"soporte para idiomas europeos"*.

**Y los dos están ligados:**

> **Un requisito muy abstracto probablemente NO tendría una descripción técnica detallada, mientras que uno de nivel más bajo PODRÍA describirse con más detalle.**

**De qué depende el nivel correcto:**

```
   · de las NECESIDADES DE LOS USUARIOS de los requisitos
   · del USO PRETENDIDO de los requisitos
   · de la DESCRIPCIÓN ORIGINAL cuando se lo planteó
     por primera vez
```

**Y la regla que se desprende, que es lo importante:**

> Como saben los profesionales, **los requisitos vienen "de todas las formas y tamaños" según su fuente. LO IMPORTANTE ES QUE LOS REQUISITOS PARA UN PROPÓSITO DADO** —por ejemplo, una especificación que va a usarse como base de diseño— **SEAN HOMOGÉNEOS Y ESTÉN EN UN NIVEL DE ABSTRACCIÓN APROPIADO PARA ESE USO.**

**Y por qué eso importa, con un ejemplo concreto:**

> Un ejemplo es la práctica de priorizar. **Si una especificación consiste en requisitos HETEROGÉNEOS —por ejemplo, en múltiples niveles de abstracción— ES DIFÍCIL COMPARARLOS Y DECIDIR que uno debe priorizarse sobre otro.**

**Y la conclusión sobre qué exigir:**

> **Exactamente qué atributos usar y con qué nivel de detalle describir los requisitos ES DECISIÓN DE CADA ORGANIZACIÓN — MIENTRAS LAS ELECCIONES SEAN EXPLÍCITAS y los requisitos se especifiquen en consecuencia.**

**Y lo que encontraron en la realidad:**

> **Una mezcla de requisitos muy abstractos y muy técnicos en la mayoría de las especificaciones, SIN IMPORTAR el uso pretendido.** Además, **los requisitos a menudo se especificaban incompletamente, resultando en requisitos inadecuados.**

> ⚠️ **Cruce con la cátedra — esta es la parte que más te sirve del capítulo.** Tiene dos ideas que valen por separado:
>
> **1. El problema no es el nivel de abstracción: es la MEZCLA de niveles.** Un documento todo abstracto sirve para discutir con el negocio; uno todo detallado sirve para diseñar. **Uno mezclado no sirve para ninguna de las dos cosas.**
>
> **2. Y el ejemplo de la priorización muestra por qué:** si un ítem de tu lista es *"el sistema debe gestionar reservas"* y otro es *"el campo de fecha debe validar formato dd/mm/aaaa"*, **no los podés comparar** — no están en la misma escala. Cualquier priorización sobre esa lista es arbitraria.
>
> Es un chequeo rápido y muy productivo para un entregable: **leé tu lista de requisitos y preguntate si todos están al mismo nivel.** Los que desentonan hay que subirlos o bajarlos.

### 5.2 Contexto y justificación 🔴

> **La justificación ANCLA EL REQUISITO A LA REALIDAD** — contiene información sobre **por qué se especificó en primer lugar** y ayuda a quien lo usa **a entender la motivación subyacente.**

**Y una regla práctica sobre cuándo hace falta:**

> **PUEDE NO SER NECESARIO PROVEER UNA JUSTIFICACIÓN PARA TODOS LOS REQUISITOS**, pero debería proveerse **al menos para aquellos QUE PUEDEN DAR LUGAR A MALENTENDIDOS, o donde la justificación PUEDA FACILITAR UN ENTENDIMIENTO AUMENTADO** del sistema que se está construyendo.

> ⚠️ **Cruce con la cátedra.** Esa regla es realista y usable: **no justifiques todo — justificá lo que puede malinterpretarse.** Es el mismo criterio de economía que el capítulo 5 aplicaba a la trazabilidad (no toda relación vale su costo) y el capítulo 11 a la ambigüedad (no hace falta encontrarlas todas, solo las que se van a interpretar mal).

### 5.3 Documentar decisiones y su historia 🔴

> **Al documentar explícitamente la información de decisión y VINCULARLA a los requisitos relevantes, SE FACILITA ENCONTRAR información potencialmente importante.** Eso permite que **la justificación de una decisión SOBREVIVA INDEFINIDAMENTE después de la reunión donde se la tomó.**

**Los tres beneficios obvios:**

```
   · los errores previos NO SE REPITEN
   · se evita HACER EL MISMO TRABAJO DE NUEVO
   · los desarrolladores pueden VER POR QUÉ se hizo un
     cambio a un requisito SIN NECESIDAD DE ENCONTRAR
     A PERSONAS que pueden ser difíciles de ubicar
     o de acceder
```

### 5.4 Trazabilidad: las tres áreas 🔴

Y acá los autores hacen una aclaración muy sensata:

> **Durante las evaluaciones NUNCA SE PROPUSO que fuera necesaria —ni siquiera deseable— ninguna clase de trazabilidad "PERFECTA" O "TOTAL"**, sino más bien que **deberían satisfacerse TRES ÁREAS PRINCIPALES.**

| Área | Qué es | Para qué sirve |
|---|---|---|
| **Trazabilidad hacia atrás** | Un vínculo **desde el requisito hacia su fuente** en otros documentos o personas | **Provee información de DE DÓNDE VIENE.** Ejemplo: si viene de un estudio previo, saberlo permite **volver al estudio entero en vez de trabajar solo con el requisito extraído** |
| **Trazabilidad hacia adelante** | Un vínculo **desde los requisitos hacia el diseño** e indirectamente hacia los componentes implementados | Principalmente para **verificación y validación**: las fallas encontradas al ejecutar casos de prueba **pueden trazarse al área causante MÁS RÁPIDO** |
| **Control de versiones de los requisitos** | No solo del documento, **sino de los requisitos mismos** | **Mayor control sobre el cambio** y **trazabilidad de versiones** |

> ⚠️ **Cruce con la cátedra.** El ejemplo de la trazabilidad hacia atrás es el más útil: **el requisito extraído pierde su contexto, y el vínculo a la fuente te devuelve el acceso a él.** No alcanza con saber *quién* lo dijo — sirve saber *de qué documento salió* para poder leer lo que lo rodeaba.
>
> Y notá la moderación: **nadie pidió trazabilidad total.** Tres áreas alcanzan. Es la misma economía del capítulo 5.

### 5.5 Revisiones 🔴

Y acá viene el argumento más fuerte del capítulo:

> **El beneficio más significativo de las inspecciones es que ENTRE EL 50 Y EL 90 % DE LOS DEFECTOS PUEDEN ATRAPARSE — y, igualmente importante, PUEDEN ATRAPARSE EN LAS ETAPAS TEMPRANAS**, reduciendo así el costo del retrabajo.
>
> **Esa es la razón principal por la cual hay consenso general** en los informes de experiencia y en la investigación **de que la inspección de requisitos es MUY BENEFICIOSA.**

**Y la recomendación concreta:**

> **La recomendación para organizaciones con recursos limitados para revisiones e inspecciones es PRIORIZAR LAS INSPECCIONES DE REQUISITOS POR SOBRE, por ejemplo, LAS DE DISEÑO Y CÓDIGO** — principalmente **por el efecto de filtración hacia abajo de los defectos de requisitos.**
>
> Dicho de otro modo: **cuanto antes puedan atraparse problemas como incompletitud, ambigüedad, errores y conflictos, MENOS ESFUERZO CUESTA ARREGLARLOS y rehacer las partes influidas.**

> ⚠️ **Cruce con la cátedra — esta recomendación es muy citable.** Si tenés tiempo para revisar **una sola cosa**, revisá los requisitos, no el código. Porque un defecto de requisitos **se filtra hacia abajo** y contamina todo lo que se construyó encima.
>
> Y el número —del 50 al 90 % de los defectos— explica por qué es tan rentable. Compará con el hallazgo del capítulo 17: **el 56 % de los errores encontrados en pruebas se rastrean a errores de requisitos.** Son las dos caras del mismo dato.

---

## 6. Conclusiones 🔴

### Lo positivo, que los autores destacan

> Como las evaluaciones se hicieron como parte de una iniciativa de mejora, **están intencionalmente enfocadas en encontrar problemas. No obstante, TAMBIÉN SE OBSERVAN ASPECTOS POSITIVOS.**
>
> **El más prominente es EL CONOCIMIENTO EXTENSO DEL DOMINIO presente en las empresas evaluadas**, así como el hecho de que **las empresas HACEN GRANDES ESFUERZOS POR TOMAR EN CUENTA LAS CUESTIONES DEL DOMINIO** —de tipo técnico, de aplicación, POLÍTICO (humano) y organizacional— durante la especificación e implementación.

**Y por qué eso contrasta con otros estudios:**

> Esto es así **A PESAR DE que otros relevamientos mencionan esas cuestiones COMO PROBLEMÁTICAS para las empresas. Una explicación podría ser que muchas de las empresas evaluadas SE HAN ESPECIALIZADO EN UN DOMINIO ESPECÍFICO Y ESTRECHO, volviéndoles posible SER EXPERTAS.**

> ⚠️ **Cruce con la cátedra.** Esa explicación es interesante y tiene una consecuencia: **el conocimiento del dominio no es una virtud individual sino una consecuencia de la especialización.** Las empresas que hacen siempre lo mismo terminan sabiendo mucho de eso.
>
> Y el corolario incómodo: **si tu empresa hace de todo, probablemente no sepa bien de nada** — y ahí la elicitación tiene que trabajar mucho más.

### El balance final

> **Las evaluaciones revelan aspectos positivos del estado de la práctica —áreas que las empresas dominan— así como varios aspectos negativos donde hacen falta más investigación y capacitación**, y donde las empresas estudiadas tienen margen de mejora.

---

## Mapa de la Parte 2

```
   ══► LAS 6 CARENCIAS ◄══
   (mitad o más de las empresas)

   especificación heterogénea, sin plantilla ....... 5/6
   NO FUNCIONALES SIN NÚMERO ....................... 5/6
   sin justificación de requisitos ni decisiones ... 3/6
     (ni siquiera se documenta POR QUÉ SE RECHAZÓ algo)
   trazabilidad: versionado a nivel de DOCUMENTO,
     no de requisito ............................... 4/6
   sin análisis de riesgo ni requisitos volátiles .. 4/6
   SIN REVISIONES de requisitos .................... 5/6
     causa: falta de tiempo Y DE INFRAESTRUCTURA
     (gente entrenada, listas de verificación)

   ─────────────────────────────────────────────

   LAS 3 QUE SÍ HACÍAN BIEN
   · consideración del DOMINIO
   · PRIORIZACIÓN (todas — aunque de manera informal)
   · validación con MODELOS (sobre todo técnicos)

   ─────────────────────────────────────────────

   LOS 3 HALLAZGOS NUEVOS DE LA EVALUACIÓN PROFUNDA
   · roles definidos PERO QUE NADIE CONOCE
     → ¿a quién le pregunto? ¿quién decide?
   · no documentar decisiones → REQUISITOS QUE HAY QUE
     DESCARTAR MÁS DE UNA VEZ
   · especificaciones DESACTUALIZADAS: el cambio entra
     por el diseño y no sube nunca a los requisitos

   ─────────────────────────────────────────────

   ══► EL TEMA MÁS APLICABLE ◄══
   NO ES el nivel de abstracción: ES LA MEZCLA
   "soporte para múltiples idiomas" ≠ "soporte para
    idiomas europeos"
   → si la lista es heterogénea, NO SE PUEDE PRIORIZAR
     (no hay escala común para comparar)
   → la elección es de cada uno, PERO DEBE SER EXPLÍCITA

   ─────────────────────────────────────────────

   LA RECOMENDACIÓN MÁS FUERTE
   las inspecciones atrapan del 50 al 90 % de los defectos
   → si tenés recursos para revisar UNA SOLA COSA,
     REVISÁ LOS REQUISITOS, no el código
     (por el efecto de filtración hacia abajo)
```

---

## Preguntas para chequear que quedó

1. Nombrá las seis áreas donde la mitad o más de las empresas tenían margen de mejora.
2. ¿Qué significa que los requisitos estén "especificados heterogéneamente"?
3. ¿Cuántas empresas no expresaban los requisitos no funcionales en forma verificable? ¿Por qué eso es difícil y no solo descuido?
4. ¿Qué ejemplo dan de decisión no documentada y qué consecuencia tiene?
5. Diferenciá versionar el documento de versionar los requisitos. ¿Por qué importa?
6. ¿Por qué no se hacían revisiones de requisitos? Nombrá las dos causas.
7. ¿Qué relación tiene esa segunda causa con la rúbrica colaborativa de tu materia?
8. Nombrá las tres prácticas que las empresas sí dominaban.
9. ¿Cómo priorizaban las empresas? ¿Usaban métodos formales?
10. ¿Qué encontró la evaluación profunda sobre el nivel de abstracción dentro de un mismo documento?
11. ¿Qué problema hay en probar contra especificaciones funcionales escritas por los desarrolladores?
12. ¿Cuál era el problema con los roles y responsabilidades? ¿Qué dos preguntas quedaban sin respuesta?
13. ¿Qué consecuencia concreta tenía no documentar las decisiones sobre requisitos?
14. ¿Por qué las especificaciones quedaban desactualizadas? Nombrá las tres razones por las que eso importa.
15. ¿Qué contradicciones aparecieron al comparar con otros relevamientos?
16. ¿Qué herramientas usa la mayoría para especificar requisitos y a partir de qué tamaño causan problemas?
17. Explicá con el ejemplo de los idiomas la diferencia de nivel de abstracción.
18. ¿Por qué una lista heterogénea no se puede priorizar?
19. ¿Qué se exige respecto de los atributos y el nivel de detalle: uniformidad universal o algo más modesto?
20. ¿Para qué requisitos hace falta justificación, según la regla práctica que dan?
21. Nombrá las tres áreas de trazabilidad que consideraron suficientes. ¿Qué aporta cada una?
22. ¿Por qué el ejemplo del estudio previo ilustra bien la trazabilidad hacia atrás?
23. ¿Qué porcentaje de defectos atrapan las inspecciones? ¿Qué se recomienda inspeccionar primero y por qué?
24. ¿Cuál es el aspecto positivo más prominente que encontraron y cuál es su explicación?

---

**FIN DEL CAPÍTULO 18 — PARTE 2**

**FIN DEL CAPÍTULO 18**

*Sigue el capítulo 19: análisis de un relevamiento empírico sobre ingeniería de requisitos, en 2 partes.*
