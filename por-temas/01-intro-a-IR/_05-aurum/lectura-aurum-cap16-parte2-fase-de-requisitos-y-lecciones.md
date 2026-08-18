# Lectura en español — Cap. 16 · Parte 2: La fase de requisitos y las lecciones del caso

> **Origen.** Capítulo 16, secciones 16.5 a 16.7, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Nigel Martin y Shirley Gregor**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1.** Se asume conocida la estructura de cinco fases y la cadena de trazabilidad vertical.

---

## Lo que hay acá

La fase de requisitos desarmada en cuatro actividades, **contrastada contra la teoría y los estándares**, y —lo más valioso— **tres ejemplos reales de requisitos elicitados**, con las palabras de los usuarios y su traducción técnica.

Esos tres ejemplos son lo más cercano que hay en todo el libro a **ver requisitos de verdad**, escritos por gente real sobre sistemas reales que se construyeron y siguen funcionando.

---

## 1. Las cuatro actividades 🔴

> **La fase de requisitos se compone de las actividades centrales de identificación, registro, revisión y priorización.**

Las tareas subordinadas pueden incluir: **identificar entradas, salidas y funciones importantes; definir necesidades de mantenimiento; registrar fechas, horarios, alcances o proveedores; verificar consistencia; y agrupar o categorizar requisitos.**

```
   1. IDENTIFICAR los requisitos de software
      (de acuerdo con los requisitos de sistema definidos)
   2. REGISTRAR los requisitos
   3. REVISAR los requisitos con los interesados
   4. PRIORIZAR los requisitos para la acción de desarrollo
```

### 1.1 Identificar 🔴

> **Los usuarios o clientes de las unidades de negocio se integran en GRUPOS FOCALES y TALLERES DE GRUPOS DE USUARIOS, dirigidos a identificar las especificaciones del usuario** — entradas, salidas, funciones.
>
> **Los modelos de CASOS DE USO y su análisis, hechos con herramientas UML, también se usan en el proceso de elicitación y comunicación.**

**Y una definición de roles que vale la pena:**

> La organización **ve a las unidades de negocio y a los gerentes de cliente COMO CLIENTES QUE PAGAN, que deben identificar y definir "QUÉ QUIEREN QUE HAGA EL SISTEMA".**
>
> **Hay una consideración explícita de que los productos de software deben representar "VALOR POR EL DINERO" para el cliente.**

> ⚠️ **Cruce con la cátedra.** Dos cosas de acá.
>
> **Los casos de uso aparecen listados como herramienta de ELICITACIÓN Y COMUNICACIÓN**, no solo de especificación. Es coherente con lo que decía el capítulo 3 —tres conceptos nomás, para que los no técnicos puedan leerlos— y con el capítulo 8, donde los casos de uso aseguraban comprensibilidad.
>
> Y la frase *"deben identificar y definir qué quieren que haga el sistema"* delimita la responsabilidad con precisión: **el cliente define el QUÉ.** No el cómo, y tampoco lo define el analista por él.

### 1.2 Registrar 🔴

> **El jefe de proyecto es responsable de registrar los requisitos en una aplicación de base de datos.**

Y los atributos que se guardan:

```
   · número de IDENTIFICACIÓN del requisito
   · CLIENTE que lo propone
   · PRIORIDAD del requisito
   · REFERENCIA CRUZADA a la especificación del sistema
```

**Y una definición importante:**

> **La base de datos de requisitos del proyecto es EL REGISTRO MAESTRO de todos los requisitos del sistema.**

> ⚠️ **Cruce con la cátedra.** Comparalo con el repositorio del capítulo 13: ahí eran dieciocho atributos, acá son cuatro. **Y los cuatro son exactamente los que hacen falta para trazar:** quién lo pidió (hacia atrás), cuánto importa (para priorizar), y a qué parte de la especificación corresponde (hacia adelante).
>
> Es un buen ejemplo de que **la trazabilidad no exige un aparato grande** — exige que cada requisito sepa de dónde viene y adónde va.

### 1.3 Revisar 🟡

> **La revisión permite que los requisitos del cliente se EXAMINEN OBJETIVAMENTE Y SE MODIFIQUEN si hace falta.**
>
> **Típicamente incluye ANÁLISIS DE COMPROMISO de negocio y financieros** por parte de los representantes de los interesados en la junta de proyecto y el panel de arquitectura.

**Y una observación empírica sobre cuándo participa realmente la gente:**

> A los usuarios **también se les ofrece la oportunidad de revisar los requisitos en la fase crítica de diseño; sin embargo, LOS CLIENTES DE NEGOCIO TIENDEN A INVOLUCRARSE MÁS ACTIVAMENTE EN LA VALIDACIÓN durante la fase de PRUEBA.**

> Ese dato es honesto y coincide con lo que decían otros capítulos: **la gente se engancha más con algo que puede probar que con un documento que tiene que leer.** Es el mismo argumento del prototipado del capítulo 8 —el cliente evalúa mejor un objeto concreto que un requisito abstracto.

### 1.4 Priorizar 🔴

> **La actividad final del flujo es la priorización, donde LOS REQUISITOS CRÍTICOS PARA EL NEGOCIO TIENEN PRECEDENCIA sobre lo que comúnmente se llama "los deseables" o requisitos opcionales.**

**Las tres categorías y qué pasa con cada una:**

| Categoría | Destino |
|---|---|
| **Crítico** | **Avanza a la fase de diseño** |
| **Estándar** | **Avanza a la fase de diseño** |
| **Opcional** | **Se retiene para revisión adicional del cliente y/o versiones futuras** |

> ⚠️ **Cruce con la cátedra.** Esas tres categorías son **exactamente las que el capítulo 4 recomendaba** para la técnica de asignación numérica: *crítico, estándar, opcional* — y las recomendaba precisamente porque **"usar términos relativos como alto, medio y bajo va a confundir a los interesados"**.
>
> Acá se ve la recomendación en uso real, con la consecuencia operativa asociada: **la frontera de la categoría es la frontera de la fase.** Crítico y estándar pasan; opcional espera. Eso vuelve la clasificación consecuente en vez de decorativa.

---

## 2. La comparación con la teoría 🟡

Los autores contrastan la práctica observada contra tres referencias: un modelo de proceso académico, las opiniones de investigadores, y los estándares internacionales.

### Contra el modelo de proceso

El modelo académico usa **un proceso interactivo de elicitación, especificación escrita, y revisión o validación** de los productos de requisitos, y **enfatiza las interacciones continuas con los usuarios.**

> **La fase observada ENCAPSULA TODAS las actividades y tareas de ese marco teórico**, incluyendo la actividad discreta de priorización.
>
> **Importantemente, tanto el marco teórico como la fase real muestran ALTA CONSIDERACIÓN POR LA PARTICIPACIÓN PROACTIVA Y CONTINUA DEL USUARIO.**

### La cita sobre quién tiene razón 🔴

Y acá aparece una afirmación que vale la pena:

> **"Cuando se están explorando aspectos del dominio de la aplicación, EL ORDEN SOCIAL DEBE INCLINARSE HACIA LAS CREENCIAS DE LOS USUARIOS, ya que su entendimiento del dominio de negocio ES MÁS VÁLIDO que el de los ingenieros de requisitos."**

> ⚠️ **Cruce con la cátedra.** Esa frase es más fuerte de lo que parece, porque **no dice que haya que escuchar al usuario por cortesía: dice que en el dominio del negocio EL USUARIO TIENE MÁS AUTORIDAD EPISTÉMICA que vos.**
>
> Y de ahí una regla práctica para una entrevista: **cuando el usuario dice algo del negocio que no cuadra con lo que vos entendías, el que está equivocado sos vos** — o el usuario está describiendo una excepción que no conocías, que es información valiosa igual. Lo que no corresponde es corregirlo.
>
> Es la contracara del capítulo 2: el analista aporta el conocimiento de qué es técnicamente factible; el usuario aporta el conocimiento del dominio. **Cada uno manda en lo suyo.**

### Sobre la priorización 🔴

Los autores recogen dos posiciones sobre por qué la priorización se volvió central:

> **"Las fuerzas competitivas redujeron el tiempo al mercado, causando que las organizaciones aceleren el desarrollo LIMITANDO DELIBERADAMENTE EL ALCANCE DE CADA VERSIÓN. Eso fuerza a los desarrolladores a distinguir entre funcionalidades DESEABLES y NECESARIAS —y de hecho, entre NIVELES de necesidad.**
>
> **Además, MODIFICAR CIERTOS REQUISITOS NO CRÍTICOS PUEDE PERMITIR que un sistema se realice usando componentes ya disponibles."**

Y la segunda:

> **"Los requisitos priorizados por los interesados impulsan a los equipos exitosos. Eso le permite al equipo DECIDIR QUÉ REQUISITOS INVESTIGAR, CUÁNDO, Y A QUÉ NIVEL DE DETALLE."**

> ⚠️ **Cruce con la cátedra.** La segunda cita agrega algo que no habías visto: **la prioridad no solo decide qué se implementa, decide CUÁNTO SE INVESTIGA.**
>
> Es un criterio muy usable para administrar el esfuerzo en un TP: **no todos los requisitos merecen el mismo nivel de análisis.** Los críticos se desarrollan en detalle; los opcionales pueden quedar enunciados. Investigar todo al mismo nivel es una manera de gastar el tiempo en lo que no importa.
>
> Y la primera cita trae de vuelta la regla de ensamblar-antes-de-construir de la Parte 1, con un giro: **aflojar un requisito no crítico puede habilitar el uso de un componente que ya existe.** El requisito rígido a veces cuesta el doble sin dar más valor.

### Y una constatación incómoda 🔴

> **El foco creciente en la priorización sugiere que, en algunos aspectos, LA ESPECIFICACIÓN DE REQUISITOS VA A PERMANECER EN UN ESTADO DE INCOMPLETITUD.**
>
> Cierto pensamiento convencional indica que **"lidiar con requisitos incompletos" ES UNA REALIDAD PARA TODOS LOS PROFESIONALES.**

### Contra los estándares 🟡

El proceso observado **es similar en alcance a los procesos del IEEE 830 y del IEEE/EIA 12207**, particularmente en la definición y el análisis de requisitos.

Y sobre el **modelo de madurez de capacidades**:

> Específico a la gestión de requisitos, **el nivel dos de la escala de madurez requiere que las organizaciones ESTABLEZCAN Y MANTENGAN UN ACUERDO CON EL CLIENTE sobre los requisitos del proyecto. Los requisitos de negocio y técnicos deben ser ATENDIDOS, DOCUMENTADOS, CONTROLADOS Y GESTIONADOS.**

**La conclusión de la comparación:**

> **La fase de requisitos observada no solo se conforma a los puntos de vista actuales de académicos y profesionales, sino que además POSEE LOS PROCESOS RIGUROSOS de marcos teóricos bien establecidos y estándares internacionales.**
>
> **El estudio sugiere que este tipo de enfoque ES VÁLIDO PARA CUALQUIER ORGANIZACIÓN, opere en el sector privado o público.**

---

## 3. Tres ejemplos reales 🔴

Esta es la parte más aprovechable del capítulo. Tres sistemas, con **los requisitos tal como los enunciaron los usuarios y los técnicos.**

### 3.1 Software de entrevista asistida por computadora 🔴

**El contexto:** en 1994 se adoptó software para conducir trabajo de encuesta en campo. **El personal de campo participó en grupos focales que identificaron qué debía hacer el software y qué beneficios debía entregar.**

**Los requisitos que enunció el personal de campo:**

| Lo que dijeron | Cómo lo detallaron |
|---|---|
| **Debe mejorar la calidad de los datos y la oportunidad** | Mediante **menos errores de transcripción (una reducción mayor al 20 %)** y **la entrada única de datos** a las bases computarizadas |
| **Debe llevar a ahorros de recursos de encuesta** | Debe **permitir eficiencias de recolección y procesamiento** |
| **Debe poder introducirse a una fuerza de entrevistadores CON POCA EXPERIENCIA INFORMÁTICA** | La mayoría del personal de campo **estaba acostumbrado a la recolección manual** y no conocía las portátiles |
| **NO DEBE CAUSAR PREOCUPACIÓN A LOS ENTREVISTADOS** | El personal temía que **el uso de portátiles pudiera ASUSTAR O INTIMIDAR a algunos proveedores de datos** |

**Y los requisitos técnicos que agregó la gerencia informática:**

```
   · para facilidad de operación, mantenimiento y
     actualización: el software debía escribirse en
     un LENGUAJE DE SINTAXIS SIMPLE Y ESTRUCTURA
     DE BLOQUES

   · las estructuras de datos debían permitir que los
     datos se PROCESEN, TRANSFIERAN Y COMPARTAN entre
     todas las herramientas de la organización

   · para soportar lo anterior: el software debía poseer
     INTERFACES DE CONVERSIÓN de datos y metadatos
     COMO CARACTERÍSTICAS ESTÁNDAR
```

**Cómo se validó:** tras una evaluación basada en diseño, se adoptó un producto y **se lo probó en julio de 1994 con una encuesta de gasto de hogares de 800 preguntas y 12.000 líneas de código**, en 450 hogares con 10 entrevistadores. **Desde ese ensayo exitoso se adoptó para otros programas de trabajo** y se integró al trabajo de encuesta telefónica.

> ⚠️ **Cruce con la cátedra — este ejemplo es oro.** Mirá el cuarto requisito de usuario: ***"no debe causar preocupación a los entrevistados"***, porque las portátiles podrían **intimidar a la gente encuestada**.
>
> Ese requisito **no lo habría producido nunca un analista pensando desde el escritorio.** Solo sale de gente que estuvo tocando timbres. Y no es funcional ni es de rendimiento — **es un requisito sobre el efecto social del sistema en personas que ni siquiera son sus usuarios.**
>
> Es exactamente lo que el capítulo 15 llamaba **incumbencia**: una preocupación sobre las consecuencias, expresada por alguien con nombre, que si no se atiende hace fracasar la adopción. Y es la mejor ilustración de por qué el capítulo 2 insistía en que **quien conoce el dominio ve cosas que el analista no ve.**
>
> Notá además que el primero viene **con número**: reducción *mayor al 20 %* de errores de transcripción. Eso es un requisito **verificable** (capítulo 8) enunciado por un usuario, no por un ingeniero.

### 3.2 Software de ajuste estacional 🟡

**El contexto:** en 1983 se adoptó un paquete de análisis y ajuste estacional, para ajustar influencias estacionales y de calendario sobre series temporales. **Antes de seleccionarlo, se sondeó a los usuarios de negocio en talleres y se les pidió definir sus requisitos más importantes.**

**Los requisitos enunciados:**

| Requisito | Tipo |
|---|---|
| **Debe ser capaz de ajustar CUALQUIER serie temporal designada** por influencias estacionales y de calendario | El primario, funcional |
| **El personal debe poder operarlo CON POCO O NINGÚN CONOCIMIENTO DETALLADO del paquete subyacente** | De operación |
| **Debe poseer una INTERFAZ INTELIGENTE** —relaciones de entrada específicas, formatos de pantalla, datos y comandos— **que GUÍE a los usuarios a través del proceso de análisis** | Técnico, acoplado al anterior |
| **Debe poseer una función para ALMACENAR Y HACER DIAGNÓSTICOS sobre análisis previamente recolectados y procesados** | Funcional |

**Y el resultado a largo plazo:**

> Desde su adopción **sufrió actualizaciones evolutivas** para mejorar el proceso de ajuste y la funcionalidad de usuario. **Después de MÁS DE VEINTE AÑOS de operación en un entorno de producción, SIGUE CUMPLIENDO CON ÉXITO LAS NECESIDADES DE LOS USUARIOS** y forma la espina dorsal analítica del proceso.

> ⚠️ **Cruce con la cátedra.** Fijate en el par de requisitos segundo y tercero: **el requisito de usuario** ("debe poder operarse sin conocer el paquete subyacente") **está acoplado explícitamente a un requisito técnico** ("debe tener interfaz inteligente que guíe al usuario").
>
> Eso es **exactamente la técnica del capítulo 6**: convertir un requisito no funcional —usabilidad— en requisitos funcionales concretos que lo materializan. El requisito de usuario dice el efecto buscado; el técnico dice el mecanismo. **Y la traza entre los dos queda registrada.**

### 3.3 Almacén de datos de entrada 🟡

**El contexto:** desarrollado desde 2001 en tres fases —un piloto de producción, un piloto, y la producción completa en junio de 2004—, para **capturar y agregar entradas estadísticas** hacia el almacén de salida.

**Los requisitos de negocio:**

```
   · debe REDUCIR LA CARGA DE TRABAJO de los proveedores
     de estadísticas: deben tener UNA SOLA estructura de
     base de datos para la recolección, reduciendo las
     cargas múltiples del pasado

   · debe INTEGRAR los almacenes de datos previamente
     separados, permitiendo integración más allá de la
     unidad estadística única, hasta las tres sub-unidades
     de definiciones, conceptos e ítems a nivel de
     registro unitario

   · debe MEJORAR LA CAPACIDAD DE SOPORTAR PRODUCTOS
     ANALÍTICOS FUTUROS — idealmente, soportar la entrega
     de productos y publicaciones actuales Y FUTUROS
```

**Los requisitos técnicos que agregó la gerencia informática:**

```
   · debe poder ACCEDER (vincular) metadatos desde el
     repositorio corporativo de metadatos
   · debe incluir las TRES FUNCIONES OBLIGATORIAS de
     actualización, consulta y coincidencia de datos
```

**El resultado:** el almacén **guarda más de 400 millones de registros** y entró en producción plena a mediados de 2004.

> ⚠️ **Cruce con la cátedra.** El tercer requisito de negocio —*mejorar la capacidad de soportar productos futuros*— es interesante porque **es un requisito sobre el valor arquitectónico**, exactamente lo que el capítulo 13 señalaba como el tipo de valor que más se olvida: *"valor para la arquitectura interna que habilita el desarrollo de funcionalidades futuras."*
>
> Y notá que está enunciado **por los usuarios de negocio**, no por los técnicos. Es raro y vale la pena: significa que el cliente entendía que parte de lo que estaba comprando era capacidad futura, no funcionalidad presente.

### El resumen de los tres 🔴

> Los tres ejemplos muestran que **es posible COMBINAR requisitos de negocio de alto nivel y requisitos de software más específicos EN UN CONJUNTO INTEGRADO** que permita dirigir los desarrollos a la resolución de problemas de negocio importantes.
>
> **Este enfoque es deliberado y duradero —más de veinte años de prácticas de calidad— y está claramente sostenido por mandatos ejecutivos y decisiones de calidad.**

**Y un factor que los autores destacan aparte:**

> **También se observó que LA CULTURA DE TRABAJO EN EQUIPO Y DE COMPARTIR VISIONES Y EXPERIENCIAS en el lugar de trabajo juega un papel importante** en gobernar la creación de sistemas orientados al negocio.

---

## 4. Las lecciones del caso 🔴

### Entender el negocio antes de construir

> **La organización cree firmemente que NO PUEDE CONSTRUIR LAS GENERACIONES FUTURAS de sistemas SIN ENTENDER PLENAMENTE SUS REQUISITOS DE NEGOCIO ACTUALES Y FUTUROS.**
>
> Los ejecutivos reconocen que **para que las aplicaciones habiliten los procesos y las salidas del negocio, LOS REQUISITOS DE NEGOCIO Y TÉCNICOS DEBEN ENTENDERSE CLARAMENTE.**

### El proceso como respuesta a la complejidad 🟡

> **El desarrollo de un proceso riguroso también apunta a lidiar con EL DINAMISMO ORGANIZACIONAL Y LA COMPLEJIDAD TÉCNICA.**

Y el contexto que lo justifica: **una tasa de publicación anual de más de 700 productos**, y la necesidad de atender clientes por canales físicos y electrónicos. Eso llevó a **concentrar los esfuerzos en desarrollar cuidadosamente sistemas que estén INTEGRADOS Y ALINEADOS con los requisitos y las funciones de entrega del negocio.**

> **En última instancia, la organización aprendió que SUS SISTEMAS INTENSIVOS EN SOFTWARE SON UN HABILITADOR CRÍTICO DE VALOR DE NEGOCIO.**

### La lección clave sobre priorización 🔴🔴

Y acá está la conclusión más citable del capítulo:

> **Una de las lecciones clave aprendidas al estudiar estas prácticas es que "LA PRIORIZACIÓN DE REQUISITOS" TIENE MUCHO QUE VER CON:**
>
> **· "EL COMPROMISO ENTRE NECESIDADES DE NEGOCIO Y TÉCNICAS"**
> **· "UN FOCO EN LA EFICIENCIA DE LOS RECURSOS"**
> **· "LA ACEPTACIÓN DE QUE UNA ESPECIFICACIÓN DE SOFTWARE PUEDE NO ESTAR NUNCA COMPLETA EN TODOS LOS ASPECTOS"**

> ⚠️ **Cruce con la cátedra.** El tercer punto es el más importante y el más difícil de aceptar: **una especificación puede no estar nunca completa en todos los aspectos, y eso no es un fracaso.**
>
> Es la misma conclusión a la que llegaban, desde ángulos distintos: el capítulo 4 (la planificación de versiones es un *problema perverso*, no hay solución óptima), el capítulo 11 (no hace falta encontrar todas las ambigüedades, solo las que se van a interpretar mal), y el capítulo 12 (buscar una decisión *satisfactoria*, no la óptima).
>
> **Cuatro capítulos, cuatro autores, la misma conclusión.** Y ojo con cómo se usa esto: **no es una excusa para entregar incompleto.** Es lo contrario — es la razón por la cual hay que priorizar bien, porque como no vas a poder con todo, importa muchísimo elegir qué sí.

### Empieza mucho antes de programar 🔴

> **En algunos casos las organizaciones NO RECONOCEN QUE CONSTRUIR SISTEMAS —particularmente los que involucran software— EMPIEZA MUCHO ANTES DE QUE SE CONTRATE A NINGÚN PROGRAMADOR O SE ESCRIBA NINGÚN CÓDIGO.**

**Y la gobernanza que lo permite:**

> La organización **exhibe un PROCESO DE GOBERNANZA BIDIRECCIONAL, que reúne las direcciones de negocio de alto nivel y las decisiones ejecutivas CON los procesos y prácticas de nivel de trabajo, MÁS BASADOS EN LO SOCIAL, que forman la piedra angular de la documentación de requisitos y del acuerdo con el usuario.**

```
   ARRIBA ──► direcciones de negocio, decisiones ejecutivas
       ↕  bidireccional
   ABAJO ───► procesos de nivel de trabajo, más SOCIALES:
              documentación de requisitos y ACUERDO
              CON EL USUARIO
```

> ⚠️ **Cruce con la cátedra.** Esa bidireccionalidad es lo que distingue este caso de una jerarquía común. **Lo estratégico baja, pero lo social sube** — y el acuerdo con el usuario se describe como *"la piedra angular"*, no como un trámite de validación al final.
>
> Y notá que se lo llama explícitamente **"más basado en lo social"**. Es el reconocimiento que atraviesa toda la serie desde el capítulo 2: **la IR es un proceso social, y las técnicas solo pueden apoyarlo.**

### Arriba y abajo a la vez 🔴

> **Al igual que esta organización, las empresas privadas de hoy van a necesitar entender las complejidades de desarrollar software usando perspectivas y procesos DE ARRIBA HACIA ABAJO Y DE ABAJO HACIA ARRIBA.**

### El cierre 🟡

> **Con un proceso de desarrollo sólido, y un enfoque de desarrollo de requisitos que lo acompañe, el software de la agencia está ayudando a dar forma y a habilitar el negocio del futuro.**
>
> **Hoy la gerencia ejecutiva entiende que la tecnología —particularmente el software— EXISTE PARA SERVIR AL NEGOCIO** y entregar las salidas y resultados requeridos.

---

## Mapa de la Parte 2

```
   LAS 4 ACTIVIDADES DE LA FASE DE REQUISITOS

   IDENTIFICAR ──► grupos focales + talleres +
                   CASOS DE USO como herramienta de
                   ELICITACIÓN Y COMUNICACIÓN
                   el cliente define EL QUÉ

   REGISTRAR ────► base de datos = REGISTRO MAESTRO
                   4 atributos: identificador · cliente
                   proponente · prioridad · referencia
                   cruzada a la especificación

   REVISAR ──────► análisis de compromiso de negocio
                   y financiero
                   (pero la gente se engancha más en
                    la fase de PRUEBA)

   PRIORIZAR ────► CRÍTICO y ESTÁNDAR → pasan a diseño
                   OPCIONAL → espera revisión o versión
                   futura

   ─────────────────────────────────────────────

   LA AUTORIDAD DEL USUARIO
   "el orden social debe inclinarse hacia las creencias
    de los usuarios: su entendimiento del dominio de
    negocio ES MÁS VÁLIDO que el de los ingenieros
    de requisitos"

   LA PRIORIDAD DECIDE TAMBIÉN CUÁNTO INVESTIGAR
   (no todo merece el mismo nivel de análisis)

   ─────────────────────────────────────────────

   LOS 3 EJEMPLOS REALES
   · entrevista asistida ─► "NO DEBE INTIMIDAR A LOS
     ENTREVISTADOS" ← requisito que solo sale de quien
     tocó timbres
     + "reducción MAYOR AL 20 %" ← verificable, dicho
     por un usuario
   · ajuste estacional ──► requisito de usuario ACOPLADO
     al requisito técnico que lo materializa
   · almacén de datos ──► requisito sobre VALOR
     ARQUITECTÓNICO, enunciado por el negocio

   ─────────────────────────────────────────────

   ══► LA LECCIÓN CLAVE ◄══
   priorizar es:
   · el COMPROMISO entre lo de negocio y lo técnico
   · un foco en la EFICIENCIA DE RECURSOS
   · "LA ACEPTACIÓN DE QUE UNA ESPECIFICACIÓN PUEDE
      NO ESTAR NUNCA COMPLETA EN TODOS LOS ASPECTOS"

   construir empieza MUCHO ANTES de contratar
   programadores
   gobernanza BIDIRECCIONAL: lo estratégico baja,
   lo social sube
```

---

## Preguntas para chequear que quedó

1. Nombrá las cuatro actividades centrales de la fase de requisitos.
2. ¿Con qué técnicas se identifican los requisitos? ¿Qué papel juegan los casos de uso?
3. ¿Qué responsabilidad se le asigna al cliente de negocio?
4. ¿Qué cuatro atributos se registran de cada requisito? ¿Para qué sirve cada uno respecto de la trazabilidad?
5. ¿Qué incluye típicamente la actividad de revisión?
6. ¿En qué fase se involucran más activamente los clientes de negocio y por qué es esperable?
7. Nombrá las tres categorías de prioridad y qué pasa con cada una.
8. ¿Por qué esas tres categorías son mejores que "alto, medio, bajo"?
9. Explicá la cita sobre por qué el orden social debe inclinarse hacia las creencias de los usuarios. ¿Qué implica para una entrevista?
10. ¿Por qué las fuerzas competitivas volvieron central a la priorización?
11. ¿Qué significa que modificar un requisito no crítico pueda permitir usar componentes ya disponibles?
12. Además de qué implementar, ¿qué otra cosa decide la priorización?
13. ¿Qué exige el nivel dos del modelo de madurez respecto de la gestión de requisitos?
14. En el ejemplo de la entrevista asistida: ¿cuáles fueron los cuatro requisitos de los usuarios de campo?
15. ¿Por qué el requisito de "no intimidar a los entrevistados" es notable? ¿Quién podía haberlo producido?
16. ¿Qué requisito de ese ejemplo es verificable y por qué?
17. En el ejemplo del ajuste estacional, ¿cómo se acopla el requisito de usuario con el técnico? ¿Con qué técnica del capítulo 6 se conecta?
18. En el almacén de datos, ¿qué tipo de valor expresa el requisito sobre productos futuros?
19. ¿Qué factor cultural destacan los autores como importante en la creación de sistemas orientados al negocio?
20. Nombrá los tres componentes de la lección clave sobre priorización.
21. ¿Por qué aceptar que una especificación puede no estar nunca completa NO es una excusa para entregar incompleto?
22. ¿Qué significa que la gobernanza sea bidireccional? ¿Qué sube y qué baja?

---

**FIN DEL CAPÍTULO 16 — PARTE 2**

**FIN DEL CAPÍTULO 16**

*Sigue el capítulo 17: requisitos de buena calidad en el Proceso Unificado, en 3 partes.*
