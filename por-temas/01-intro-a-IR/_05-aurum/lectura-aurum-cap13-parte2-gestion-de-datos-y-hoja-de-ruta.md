# Lectura en español — Cap. 13 · Parte 2: Gestión de datos, elicitación y hoja de ruta

> **Origen.** Capítulo 13, secciones 13.4 a 13.7, de *Engineering and Managing Software Requirements* (Aurum, A. y Wohlin, C., eds., Springer, 2005). Capítulo de **Björn Regnell y Sjaak Brinkkemper**.
>
> Cobertura fiel, redacción propia. Las notas ⚠️ marcan cruces con tu cursada y son mías, no del libro. **Ante cualquier diferencia, en el parcial manda la cátedra.**
>
> **Marcas** 🔴🟡🟢 = relevancia para tu materia, no señales de la cátedra.
>
> **Viene de la Parte 1.** Se asumen conocidas las diferencias entre desarrollo dirigido por el mercado y a medida, y el modelo alfa/beta.

---

## 1. El modelo de estados de un requisito 🔴

### Por qué hace falta

> **En la concepción de un requisito es muy incierto si finalmente va a realizarse en una versión del producto.** Los recursos disponibles y el tiempo hasta la fecha planificada **limitan la realización de cualquier deseo.**
>
> **Para llevar la cuenta de grandes volúmenes de requisitos a través de las etapas del desarrollo, un modelo de estados es indispensable.**

Los autores le ponen un nombre que explica bien la idea:

> Llamamos a este modelo de estados **"la escalera de salmones"**, refiriéndonos a **la incertidumbre de un salmón sobre lograr remontar la corriente hasta las aguas de desove.**

### Los dos modos 🔴

Antes de los estados, una distinción de fondo:

> **Los requisitos se reciben EN CUALQUIER MOMENTO, pero el desarrollo de un producto se hace EN VERSIONES, producidas en momentos DISCRETOS.** Distinguimos, entonces, dos modos:

| Modo | Qué pasa |
|---|---|
| **Modo continuo** | **Se reciben y registran requisitos** de toda clase de proponentes, internos o externos: clientes, representantes de ventas, equipos de desarrollo |
| **Modo de versión** | **Se inicia en tiempos designados según la hoja de ruta.** El jefe de producto está en contacto con los otros roles: jefe de proyecto, ingenieros, probadores, autores técnicos, traductores. **El contenido de la próxima versión —el alcance— se CONGELA** para poder gestionar el proyecto apropiadamente. Los cambios al alcance **se deciden mediante un procedimiento de cambio de alcance** |

> ⚠️ **Cruce con la cátedra.** Esa tensión entre **un flujo que no para** y **entregas que ocurren en fechas fijas** es estructural, y el mecanismo para resolverla es **congelar el alcance y tener un procedimiento explícito para descongelarlo.**
>
> Es la misma lógica de la **línea base de requisitos** del capítulo 6 —crear una instantánea contra la cual comparar los cambios posteriores— y del **canal único** que examina cada cambio antes de dejarlo entrar.

### Los ocho estados 🔴

```
                                          Publicado
                                    Verificado
                              Desarrollado
                        Planificado      ← modo de VERSIÓN
              Especificado               ← modo CONTINUO
       Aprobado
              Descartado
   Candidato
```

**Candidato.** Todo requisito recibido obtiene este estado.

> **Se prefiere que la descripción del requisito siga la redacción del proponente lo más precisamente posible, PARA MANTENER EL COMPROMISO de la parte que lo propuso.**

**Aprobado.** A intervalos regulares, los candidatos **se revisan para su posible inclusión** en versiones futuras. Y el capítulo describe lo difícil que es ese juicio:

> **Este proceso de juicio es una tarea muy difícil y de mucha responsabilidad.** Primero, **hace falta una visión de largo plazo del producto**, usualmente expresada en la hoja de ruta. Después, **hace falta un entendimiento funcional y técnico profundo del producto** para determinar el significado y las consecuencias de los requisitos, a menudo muy detallados, de la base de clientes existente.
>
> **Finalmente, los jefes de producto deberían poder lidiar con las cuestiones POLÍTICAS Y ESTRATÉGICAS que traen los contratos nuevos posibles, los clientes importantes y los vendedores insistentes.**

**Especificado.** Como la descripción original **probablemente no sea muy adecuada para planificar y desarrollar**, normalmente **se crea una especificación más elaborada y se la vincula al requisito.** El tipo de documentación varía:

> **En algunas organizaciones se crea un texto que explica el requisito con más profundidad; en otras se hace un documento de diseño completo con CASOS DE USO Y DIAGRAMAS DE CLASES.**

**Descartado.** Los requisitos rechazados obtienen este estado. Dos detalles importantes:

```
   · se envía al proponente una NOTIFICACIÓN CON LA
     MOTIVACIÓN del rechazo
   · los requisitos descartados NO SE BORRAN de la base,
     para habilitar consultas y análisis futuros
```

**Planificado.** La fecha planificada y los recursos de personal **determinan la cantidad de días-persona disponibles.** La planificación **puede acomodar un número máximo de requisitos**, basándose en las estimaciones de esfuerzo y en una priorización.

Y un detalle realista:

> **Como las estimaciones son usualmente demasiado optimistas, algunos requisitos planificados llevan una indicación de prioridad más baja y pueden ser candidatos a salir del plan en caso de escasez de tiempo.**

**Desarrollado.** El desarrollo implica **diseño técnico, codificación, pruebas unitarias, y producción de materiales colaterales** —folletos, campaña de comercialización, material de capacitación.

Y una advertencia:

> **Notar que sacar un requisito del plan puede ocurrir EN CUALQUIER MOMENTO, incluso cuando el desarrollo está sustancialmente en marcha.** En ese caso **el código tiene que volverse a un estado donde el requisito estaba incluido.** Suele pasar **si se acaba el tiempo, o por cambio de prioridades.**

**Verificado.** Los tipos típicos de prueba:

```
   · pruebas UNITARIAS funcionales, hechas por un probador
     que NO es parte del equipo de desarrollo
   · prueba de INTEGRACIÓN, enfocada en las dependencias
     entre módulos
   · prueba de SISTEMA, para el sistema completo
   · prueba de ACEPTACIÓN, para el producto completo
     (software y colaterales)
   · prueba final de los archivos de instalación
```

**Publicado.** El requisito llegó a una versión oficial del producto.

> ⚠️ **Cruce con la cátedra.** Tres cosas de esta sección son transferibles a cualquier trabajo con requisitos:
>
> **1. Conservar la redacción del proponente** en el estado candidato, **para mantener su compromiso.** Es una razón que rara vez se explicita: si le reescribís el requisito a alguien apenas lo dice, **deja de sentirlo suyo.** La reescritura viene después, en el estado especificado.
>
> **2. Notificar el rechazo con su motivación.** Rechazar en silencio es lo que hace que la gente deje de proponer.
>
> **3. No borrar lo descartado.** Es lo mismo que pedía el capítulo 4 sobre priorización — **conservar información de los requisitos descartados** para poder analizar después si se decidió bien.

---

## 2. El repositorio 🟡

> Para desarrollos chicos **una simple planilla de cálculo puede alcanzar.** Un desarrollo a mayor escala **es improbable que se ejecute con éxito sin una herramienta de gestión de requisitos**, por el volumen.

Y una crítica al documento monolítico:

> **Los documentos monolíticos de especificación también se consideran problemáticos, porque la estructura del documento OBSTACULIZA LA ELABORACIÓN CONCURRENTE de requisitos distintos por equipos distintos.**

### Los atributos típicos 🔴

Este esquema es útil porque **muestra en qué estado se asigna cada atributo** — o sea, qué información existe en cada momento y cuál todavía no:

| Atributo | Valor | Se asigna en el estado |
|---|---|---|
| **Estado** | El estado actual en la escalera | — |
| **Identificador** | Identidad única | Candidato |
| **Proponente** | **¿Quién lo propuso?** | Candidato |
| **Empresa** | La empresa del proponente | Candidato |
| **Dominio** | Dominio funcional | Candidato |
| **Etiqueta** | **Un buen nombre descriptivo** | Candidato |
| **Descripción** | Descripción textual breve | Candidato |
| **Contrato** | **Vínculo al contrato de venta que impone el requisito** | Candidato |
| **Prioridad** | Categoría de importancia (1, 2, 3) | Aprobado |
| **Motivación** | **Justificación: ¿por qué es importante?** | Aprobado |
| **Línea de negocio** | Segmento de mercado para el que importa | Aprobado |
| **Especificación** | **Vínculos al caso de uso, a la especificación textual** | Especificado |
| **Descomposición** | **Vínculos padre-de / hijo-de** hacia otros requisitos | Especificado |
| **Estimación** | Estimación de esfuerzo en horas | Especificado |
| **Cronograma** | Versión para la que está planificado | Planificado |
| **Diseño** | Vínculos a documentos de diseño | Desarrollado |
| **Prueba** | Vínculos a documentos de prueba | Verificado |
| **Versión** | Nombre oficial de la versión | Publicado |

> ⚠️ **Cruce con la cátedra.** Mirá los tres atributos que se asignan al entrar: **proponente, etiqueta y descripción.** Son exactamente **los tres metadatos mínimos** que el capítulo 2 pedía guardar de cada requisito (fuente, prioridad, justificación) — con la prioridad y la justificación llegando un paso después, cuando ya se lo aprobó.
>
> Y notá que **la trazabilidad no se agrega al final: se construye en capas**, un vínculo por estado. Especificación en un estado, descomposición en otro, diseño y prueba después. **Nadie llena una matriz de trazabilidad de una vez; se va poblando.**

**Atributos adicionales según el mercado:**

- **Datos de país**, para productos vendidos internacionalmente: **varios países tienen reglas legales o financieras exigidas por ley.**
- **Plataforma técnica**: sistemas operativos, bases de datos, interfaces multimodales. **Algunas plataformas proveen facilidades que pueden incorporarse; para otras hay que desarrollarlas completamente.**
- **Dominio funcional**, para productos de líneas o mercados distintos — importante donde **la seguridad es una cuestión central**, como salud o aviónica.

**Y un problema declarado sobre trazabilidad:**

> **Mientras las herramientas de gestión de requisitos y de desarrollo carezcan de medios apropiados de interoperación, el rastreo y seguimiento está condenado a ser una tarea manual, intensiva en trabajo y propensa a error.**
>
> Dado que **los desarrolladores trabajan a menudo sobre un requisito a la vez**, rastrear los cambios hechos en los distintos productos de trabajo **daría automáticamente visión sobre el proceso de trazado.**

---

## 3. Análisis de mercado y elicitación 🔴

Las fuentes de requisitos son numerosas.

### La colaboración con clientes clave 🔴

> **Una manera eficiente de recolectar requisitos de manera estructurada es mediante la colaboración con CLIENTES CLAVE.** A cambio de transferencia temprana de conocimiento, **el cliente clave asiste en la especificación de requisitos y en las pruebas en sitio.**

**Y la advertencia que viene con eso:**

> **Hay que tener cuidado de que el foco del producto siga siendo el ANCHO COMPLETO DEL MERCADO, y no se deteriore hacia una visión estrecha de esos clientes clave.**

> Es un riesgo fino: el cliente que más colabora **es también el que más te sesga.** Lo que te dice es información valiosa y no representativa a la vez.

### Los informes de analistas 🟡

Para mercados de aplicaciones empresariales grandes, **las empresas analistas proveen panoramas funcionales y técnicos de los dominios subyacentes.**

Y un efecto lateral que vale destacar:

> **Un efecto secundario de los informes de analistas es LA UNIFICACIÓN DE LA TERMINOLOGÍA en un dominio.**
>
> **Posicionar la versión actual del producto sobre el panorama completo del dominio es una buena fuente de requisitos adicionales.**

### Los talleres facilitados 🔴

Una técnica propuesta recientemente:

> **Un grupo de expertos del dominio se reúne en un entorno de trabajo intensivo para especificar los requisitos, gestionado por un facilitador.**

Y acá viene un dato empírico interesante. Se comparó **taller facilitado contra entrevista tradicional uno a uno**, analizando **unos 50 proyectos de cada categoría** en una empresa financiera grande:

| Resultado | |
|---|---|
| **Proyectos chicos** | El taller facilitado es **MENOS efectivo** |
| **Proyectos grandes** | El taller facilitado es **MÁS efectivo** |
| **Satisfacción de los clientes con la calidad de los requisitos resultantes** | **Sorprendentemente, MENOR** con los talleres |

**La explicación tentativa que dan:**

> **El tiempo y la presión grupal del taller facilitado podrían ser las razones.**

> ⚠️ **Cruce con la cátedra.** Este resultado es un buen antídoto contra la idea de que una técnica más elaborada es siempre mejor. **El taller facilitado gana en eficiencia para proyectos grandes, y pierde en satisfacción percibida.** Es exactamente el tipo de compromiso que el capítulo 2 pedía tener en cuenta al justificar la elección de una técnica: **no hay una que gane en todas las dimensiones.**
>
> Y la explicación —presión de tiempo y de grupo— rima con lo que el capítulo 2 advertía sobre el trabajo grupal: hay que asegurar que **todos tengan oportunidad suficiente de contribuir** y se sientan cómodos para hablar.

### Los grupos de trabajo de clientes 🟡

> **La participación del cliente en la especificación debe realizarse con cuidado. Hay que gestionar las expectativas, ya que el desarrollo de los requisitos puede repartirse a lo largo de varias versiones y años.**

Algunas empresas organizan **grupos de trabajo de clientes**:

> Un equipo de **representantes de clientes junto con jefes de producto**, que **desarrolla un documento de especificación para toda un área funcional nueva.** Los representantes **son expertos en el dominio y pueden juzgar muy bien las prioridades entre los requisitos imprescindibles y los deseables.**

**Y el riesgo que trae:**

> **Establecer un grupo de trabajo en un área también CREA EXPECTATIVAS sobre la disponibilidad futura en las versiones.** Cambios estratégicos de la hoja de ruta **que excluyan el tema del grupo pueden poner presión sobre la relación entre proveedor y cliente.**

---

## 4. La hoja de ruta 🟡

### Qué es

> **Una hoja de ruta es un documento que provee la disposición de las versiones del producto por venir, en un marco temporal de tres a cinco años.**

**Por qué la quieren los clientes:**

> **Los clientes quieren estar seguros de que el futuro del producto de software del que dependen está en línea con sus propios planes futuros.** Especialmente **en mercados donde los costos y consecuencias de cambiar de proveedor son grandes**, el cliente quiere tener parte en la decisión.

### Los tres usos 🟡

**Una hoja de ruta tecnológica identifica** los temas críticos de requisitos del sistema, los objetivos de desempeño de producto y proceso, y las alternativas tecnológicas e hitos para alcanzarlos. Sus tres usos mayores:

```
   1. DESARROLLAR CONSENSO sobre un conjunto de
      necesidades y las tecnologías requeridas para
      satisfacerlas

   2. PROVEER UN MECANISMO que ayude a los expertos a
      pronosticar desarrollos tecnológicos en las áreas
      objetivo

   3. UN MARCO para planificar y coordinar desarrollos,
      dentro de una organización o en toda una industria
```

### El ciclo de inversión 🟡

La hoja de ruta **no puede verse independiente de la estrategia general de la empresa.** Una estructura cíclica de cuatro capas:

```
   ESTRATEGIA        plan de inversión ──────► ingresos
   CORPORATIVA
        │
        ▼
   ESTRATEGIA        HOJA DE RUTA ───────────► ventas y
   DE PRODUCTO       DEL PRODUCTO              servicios
        │
        ▼
   PROCESO DE        requisitos del ─────────► versión
   VERSIÓN           producto                  del producto
        │
        ▼
   PROCESO DE        diseño ─────────────────► construcción
   DESARROLLO                                  del software
```

**Anualmente se elabora el plan de inversión** basándose en ingresos y pronósticos de las líneas actuales: **extender una línea con una versión nueva, arrancar una línea nueva, o terminar una línea.** Incluye niveles de inversión en dinero o cantidad de personal.

**Ese plan alimenta a la gestión** para crear o actualizar las hojas de ruta, **tomando en cuenta las visiones de las unidades de ventas y consultoría** — porque **esas unidades son las que mejor saben cuáles son las fortalezas y debilidades de los productos actuales**, y qué tendencias y funcionalidades aprecian los clientes actuales y prospectivos.

**Los jefes de producto** elaboran la hoja de ruta en un conjunto de requisitos para las distintas versiones: **o seleccionan los adecuados entre los candidatos de la base, o buscan requisitos adicionales** en distintas fuentes del dominio — especialmente cuando se inician líneas nuevas o se expande una existente con un área funcional nueva.

---

## 5. Un ejemplo industrial: el proceso en cuatro fases 🟡

El capítulo describe el proceso de una empresa real, rediseñado y evaluado.

```
   FASE 1 — INICIACIÓN
     1. formar el equipo de la hoja de ruta
     2. determinar la estrategia
     3. determinar las precondiciones
     4. fijar el contexto

   FASE 2 — PREPARACIÓN
     1. priorizar los temas
     2. seleccionar los temas
     3. determinar el cronograma
     4. crear la hoja de ruta

   FASE 3 — FINALIZACIÓN
     1. validar la hoja de ruta
     2. comunicar internamente
     3. comunicar externamente

   FASE 4 — SEGUIMIENTO
     1. revisar y actualizar periódicamente
```

**Fase 1.** Se forma el equipo con **empleados veteranos con conocimiento profundo del producto y acceso a las personas clave.** La estrategia y las precondiciones **las fija la gerencia corporativa**: línea de tiempo (tres o cinco años), productos en alcance, rango de inversión, frecuencia de versiones.

**Fase 2.** Se identifican y priorizan los **temas** de extensión funcional y técnica.

> **Los temas pueden verse como REQUISITOS DE ALTO NIVEL, usualmente cuestiones genéricas bien conocidas del dominio del producto.** Se elaboran en un conjunto de requisitos coherentes a planificar en una o varias versiones.

Ejemplos de tema: *"habilitación para flujo de trabajo"*, *"portar a la plataforma Linux"*, *"extensiones para un mercado nuevo"*.

**Y un criterio de calidad para los temas que vale la pena:**

> **Los temas deberían estar tan bien definidos y ser tan atractivos que sean candidatos a figurar como las extensiones funcionales listadas EN LOS FOLLETOS que cubren los productos de la versión.**

**Sobre los cronogramas:** se expresan a menudo **en trimestres**. Y **la frecuencia de versiones depende del tamaño del producto**:

```
   sistemas de planificación de recursos empresariales:
     ~1,5 años (el mercado NO ES RECEPTIVO a demasiadas
     actualizaciones disruptivas)

   software de contabilidad: una vez al año
     (los cambios de legislación exigen que los procesos
      financieros estén al día)
```

**Fase 3.** Una vez borrada la hoja de ruta, **requiere validarse con los distintos grupos de interesados**: gerencia general, clientes grandes, equipos de ventas y consultoría, equipos de desarrollo. **Se integran comentarios y devoluciones**, y la hoja de ruta **se entrega a la gerencia general, que es su dueña y comunicadora.** La comunicación formal **se lanza a menudo en algún evento grande donde se reúnen muchos clientes.**

**Fase 4.** El equipo se agradece y se disuelve. **Algunos jefes de producto siguen responsables del mantenimiento de la documentación y de su actualización con temas nuevos. Después de unos tres años se forma un equipo nuevo y el ciclo se repite.**

> ⚠️ **Cruce con la cátedra.** El criterio de calidad de los temas —*que sean tan buenos que puedan ir en el folleto*— es un test simple y potente. **Si un tema no se puede enunciar de manera que le interese a alguien de afuera, probablemente no esté bien definido.** Es una versión comercial del mismo principio que atraviesa la serie: un requisito que no se puede comunicar claramente probablemente no esté claro.

---

## 6. Conclusión del capítulo 🔴

> **Cuando el proceso de IR se ejecuta en un contexto dirigido por el mercado, la organización enfrenta desafíos especiales. Los candidatos que llegan continuamente proveen la entrada a una toma de decisiones que debería resultar en una hoja de ruta estratégica y un plan de versiones priorizado.**
>
> **Un desafío mayor es lidiar con la cantidad potencialmente enorme de información y representarla y organizarla de manera eficiente**, para que provea una buena base de decisión — **que a su vez provee la base de un negocio de software rentable.**

**Los cuatro elementos que el capítulo aporta:**

```
   · un MODELO DE CALIDAD DEL PROCESO para evaluar
     la bondad de la selección de requisitos
   · un MODELO DE ESTADOS típico para el seguimiento
     del progreso
   · un REPOSITORIO típico para la gestión de datos
   · un EJEMPLO INDUSTRIAL de proceso de gestión
     de versiones
```

**Y el cierre:**

> **El proceso tiene que adaptarse a su contexto específico. La madurez de la organización y de sus productos, así como la del mercado y sus clientes, son parámetros críticos que hay que considerar** al formular y establecer un proceso bien balanceado.
>
> **También es importante que haya un MECANISMO INCORPORADO PARA APRENDER Y MEJORAR, para mantenerse por delante incluso a medida que la competencia se vuelve más inteligente.**

---

## Mapa de la Parte 2

```
   LA ESCALERA DE SALMONES

   MODO CONTINUO          MODO DE VERSIÓN
   entran requisitos      el alcance se CONGELA
   en cualquier momento   y se descongela por
                          procedimiento explícito

   candidato ─► aprobado ─► especificado ─► planificado
   ─► desarrollado ─► verificado ─► publicado
        └─► descartado (con MOTIVO, y NO se borra)

   · conservar la redacción del PROPONENTE (compromiso)
   · notificar el rechazo CON SU MOTIVACIÓN
   · sacar del plan puede pasar EN CUALQUIER MOMENTO

   ─────────────────────────────────────────────

   EL REPOSITORIO
   cada atributo se asigna EN UN ESTADO DISTINTO
   → la trazabilidad NO se agrega al final:
     SE CONSTRUYE EN CAPAS

   ─────────────────────────────────────────────

   ELICITACIÓN DE MERCADO
   · clientes clave ──► valiosos Y SESGADOS
   · informes de analistas ──► unifican la TERMINOLOGÍA
   · talleres facilitados ──► mejores en proyectos
     grandes, PERO menor satisfacción percibida
   · grupos de trabajo de clientes ──► crean expectativas

   ─────────────────────────────────────────────

   HOJA DE RUTA — 3 a 5 años
   4 fases: iniciación · preparación · finalización
   · seguimiento
   TEMAS = requisitos de alto nivel
   test: ¿podría ir en el FOLLETO?
```

---

## Preguntas para chequear que quedó

1. ¿Por qué el modelo de estados se llama "escalera de salmones"?
2. Diferenciá el modo continuo del modo de versión. ¿Qué pasa con el alcance en cada uno?
3. Nombrá los ocho estados del modelo.
4. ¿Por qué conviene conservar la redacción del proponente en el estado candidato?
5. ¿Qué tres cosas hacen difícil el juicio para pasar un requisito a "aprobado"?
6. ¿Qué se hace con un requisito descartado y por qué no se borra?
7. ¿Por qué algunos requisitos planificados llevan indicación de prioridad más baja?
8. ¿Qué pasa si hay que sacar un requisito del plan cuando el desarrollo ya está en marcha?
9. Nombrá los cinco tipos de prueba del estado "verificado".
10. ¿Por qué un documento monolítico de especificación es problemático?
11. Nombrá los atributos que se asignan en el estado candidato. ¿Y en aprobado?
12. ¿Qué muestra el hecho de que cada atributo se asigne en un estado distinto?
13. ¿Cuál es el beneficio y cuál el riesgo de colaborar con clientes clave?
14. ¿Qué efecto secundario tienen los informes de analistas de mercado?
15. ¿Qué resultado dio la comparación entre talleres facilitados y entrevistas uno a uno? ¿Cuál fue el resultado sorprendente y cómo se lo explica?
16. ¿Qué es un grupo de trabajo de clientes y qué riesgo trae establecerlo?
17. ¿Qué es una hoja de ruta y por qué la quieren los clientes?
18. Nombrá los tres usos mayores de una hoja de ruta.
19. Nombrá las cuatro fases del proceso de hoja de ruta.
20. ¿Qué es un "tema" y cuál es el test de calidad para saber si está bien definido?
21. ¿Por qué la frecuencia de versiones difiere entre un sistema empresarial y un software de contabilidad?
22. ¿Cuáles son los cuatro elementos que aporta el capítulo?

---

**FIN DEL CAPÍTULO 13 — PARTE 2**

**FIN DEL CAPÍTULO 13**

*Sigue el capítulo 14: ingeniería de requisitos para métodos ágiles, en 2 partes.*
