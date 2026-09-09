# 📘 APUNTE MAESTRO — Clase 04 · Entrevistas y redacción de requisitos — Parte 4

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Unidad:** `clase04` · Jueves 03/09/2026 · Presencial (Campus)
**Parte 4:** ISO/IEC 25010 — de dónde salen los atributos que un RNF puede medir.

---

## Sobre esta parte

**Qué cubre:** qué es la ISO/IEC 25010 y por qué una norma de calidad obliga a medir · el modelo de calidad del producto: las ocho características, sus subcaracterísticas, cómo se mide cada una y los errores comunes que la comprometen · lo que agregó la versión 2023 · cinco ejemplos de RNF resueltos, uno por característica, con la estructura objeto + atributo + valor + unidad · el modelo de calidad de uso, como anexo.

**Qué viene después:** Parte 5 — la defensa: escribir requerimientos y detectar lo mal escrito, con los casos trabajados en la puesta en común, la rúbrica de casos de uso y el checkpoint de la unidad.

**Marcas:** 🔴 central, evaluable · 🟡 secundario · 🟢 mencionado al pasar · 🕳️ madriguera.

## De dónde venís

De la Parte 3: el RNF como restricción medible, y la estructura objeto + atributo + valor + unidad. Esta parte responde la pregunta que quedó abierta ahí: **¿qué atributos existen para medir?** No se inventan; están catalogados.

Esta parte casi no se dictó en voz alta: la cátedra la dejó como guía escrita para que la trabajes por tu cuenta. Es material de la unidad y se evalúa como tal.

---

## 1. 🔴 Qué es la ISO/IEC 25010 y por qué obliga a medir

Cuando en la Parte 3 escribiste "el tiempo máximo de notificación es de 2 segundos", elegiste un atributo —tiempo de respuesta— casi por instinto. ¿Hay una lista de atributos posibles? Sí. Es esta norma.

La **ISO/IEC 25010** es un estándar internacional que describe el **modelo de calidad para el software y los sistemas informáticos**. Forma parte de la serie **ISO/IEC 25000**, conocida como **SQuaRE** (*Software Product Quality Requirements and Evaluation*: requisitos y evaluación de la calidad del producto de software).

Lo que hace la norma es **dividir la calidad del software en características específicas que pueden analizarse, probarse y medirse cuantitativamente**. Al categorizar los atributos de calidad —lo que llamamos requisitos no funcionales—, asegura que ningún aspecto crucial del ciclo de vida del software quede ignorado. Es un checklist de "¿pensaste en esto?".

Tiene dos modelos: el de **calidad del producto** (sección 2, el que se asocia a los RNF y el que trabaja este curso) y el de **calidad de uso** (sección 5, anexo; en este curso no se trabajan en forma directa métricas relacionadas con él).

**Es de 2011, actualizada en 2023.** Y la actualización no es cosmética: le incorporaron cuestiones que en 2011 no pesaban. Por un lado, **safety** — la seguridad en el sentido de que el producto sea seguro *para los usuarios*, no en el sentido de ciberseguridad —, a partir del surgimiento de IoT, inteligencia artificial y dispositivos que actúan sobre el mundo físico. Por otro, lo que tiene que ver con **escalabilidad y compatibilidad**, porque todo lo que era on-premise se vino a la nube y hubo que poder responder "¿cómo escalo?".

**IoT** (*Internet of Things*): dispositivos físicos —sensores, electrodomésticos, equipos médicos— conectados a internet y controlados por software.

### Por qué esto obliga a medir

Como toda norma, la ISO 25010 es una guía. Pero al ser una ISO —como la 9001 de gestión de calidad o la 27001 de seguridad de la información— **es certificable**. Puedo decir: quiero certificar qué calidad tiene mi producto respecto de esta norma. Y para certificar algo tengo que tener **medidas**.

Ahí cierra el círculo con la Parte 3: la exigencia de que los RNF sean medibles no es un capricho pedagógico. Si querés poder afirmar que tu producto cumple una característica de calidad, tenés que poder mostrar el número.

> **Para el parcial, si te preguntan:** *¿Qué es la ISO/IEC 25010 y para qué sirve en la especificación de requisitos?*
> Es el estándar internacional que define el modelo de calidad del software (serie ISO/IEC 25000, SQuaRE). Divide la calidad en características medibles y cuantificables, que sirven para identificar y clasificar los requisitos no funcionales y para asegurar que ningún aspecto de calidad quede sin considerar. Al ser certificable, exige que cada característica se pueda medir.

## 2. 🔴 El modelo de calidad del producto: ocho características

```
 ADECUACIÓN    EFICIENCIA DE   COMPATI-    USABILIDAD    FIABILIDAD    SEGURIDAD    MANTENI-     PORTABI-
 FUNCIONAL     DESEMPEÑO       BILIDAD                                              BILIDAD      LIDAD
 ├ Completitud ├ Comport.      ├ Coexis-   ├ Inteligibi- ├ Madurez     ├ Confiden-  ├ Modula-    ├ Adaptabi-
 │  funcional  │  temporal     │  tencia   │  lidad      │             │  cialidad  │  ridad     │  lidad
 ├ Corrección  ├ Utilización   └ Interope- ├ Aprendizaje ├ Disponibi-  ├ Integridad ├ Reusabi-   ├ Facilidad
 │  funcional  │  de recursos     rabilidad ├ Operabi-    │  lidad      ├ No repudio │  lidad     │  de insta-
 └ Pertinencia └ Capacidad                  │  lidad      ├ Tolerancia  ├ Autentici- ├ Analizabi- │  lación
    funcional                               ├ Protección  │  a fallos   │  dad       │  lidad     └ Capacidad
                                            │  frente a   └ Capacidad   └ Responsa-  ├ Cap. de ser   de ser
                                            │  errores       de recupe-    bilidad   │  modificado   reemplazado
                                            ├ Estética       ración                  └ Cap. de ser
                                            └ Accesibilidad                             probado
```

Ocho columnas. Cada una es una **característica**; lo que cuelga son sus **subcaracterísticas**, que son los atributos concretos que un RNF puede medir. Cuando escribís un RNF, el atributo tiene que poder ubicarse en una de estas columnas — eso es lo que garantiza que el requerimiento mide algo reconocido y no una intuición.

Para cada característica vas a ver lo mismo: qué es, sus subcaracterísticas, cómo se mide y qué errores comunes la comprometen. Los "cómo medirla" son la cantera de valores y unidades para tus RNF.

### 2.1 Adecuación funcional (idoneidad funcional)

Capacidad del producto de software para **proporcionar funciones que satisfacen las necesidades declaradas e implícitas del usuario** bajo condiciones específicas. Tres subcaracterísticas:

- **Completitud funcional:** grado en que el conjunto de funciones cubre todas las tareas y objetivos del usuario especificados.
- **Corrección funcional:** capacidad de proveer resultados correctos o precisos.
- **Pertinencia funcional:** grado en que las funciones facilitan la realización de tareas específicas del usuario.

**Cómo medirla:** porcentaje de casos de uso del negocio cubiertos por el software (escenarios); tasa de defectos lógicos por funcionalidad entregada.

**Errores comunes:** implementar *gold plating* (agregar características innecesarias: "chapado en oro" — funcionalidad que nadie pidió); no validar los flujos de negocio alternativos con los stakeholders.

Es la característica más pegada a los RF: mide si lo funcional está completo y correcto. Para el centro de entrenamiento, el porcentaje de casos de uso cubiertos es exactamente el criterio con el que vas a comparar las tres soluciones enlatadas.

### 2.2 Eficiencia de desempeño (rendimiento)

Evalúa el **desempeño del software en relación con la cantidad de recursos utilizados** bajo condiciones determinadas.

- **Comportamiento temporal:** tiempos de respuesta y procesamiento.
- **Utilización de recursos:** cantidad de CPU, RAM, red y disco consumidos.
- **Capacidad:** límites máximos del sistema (por ejemplo, usuarios concurrentes).

**Cómo medirla:** tiempo de respuesta promedio (*latency*: demora entre pedido y respuesta; *RTT*: tiempo de ida y vuelta); uso porcentual de CPU bajo carga; transacciones por segundo (*throughput*: cuánto trabajo procesa por unidad de tiempo).

**Errores comunes:** no usar índices en la base de datos; consultas SQL ineficientes dentro de bucles; ausencia de capas de caché (copia temporal de datos para no volver a calcularlos o buscarlos).

Acá vive el ejemplo canónico: "2 segundos" es comportamiento temporal. Y "100 notificaciones por minuto" es capacidad.

### 2.3 Compatibilidad

Capacidad de **dos o más sistemas o componentes para intercambiar información y/o realizar sus funciones compartiendo el mismo entorno** de hardware o software.

- **Coexistencia:** compartir un entorno común con otros programas sin afectarlos negativamente.
- **Interoperabilidad:** capacidad de interactuar con otros sistemas (mediante APIs, colas de mensajería, etc.).

**Cómo medirla:** tasa de colisiones de dependencias; porcentaje de conformidad con especificaciones estándar (por ejemplo OpenAPI/REST: convenciones estandarizadas para describir y exponer servicios web).

**Errores comunes:** acoplamiento fuerte entre sistemas; no versionar APIs; usar formatos propietarios en lugar de estándares como JSON o XML.

"La integración con el medio de pago es por medio de APIs" — el RNF que salió del caso del pago en la Parte 5 — es interoperabilidad.

### 2.4 Usabilidad (facilidad de uso)

Facilidad con la que se puede **entender, aprender y usar** el software para alcanzar objetivos específicos de forma eficaz, eficiente y satisfactoria. El grado en que el producto puede ser utilizado por usuarios específicos para lograr objetivos determinados con efectividad, eficiencia y satisfacción.

- **Inteligibilidad (reconocimiento):** capacidad de reconocer si el producto es apropiado para las necesidades que se buscan satisfacer.
- **Aprendizaje:** cuánto esfuerzo requiere aprender a usar la herramienta (el ejemplo de la cátedra: los cajeros de autoservicio de McDonald's, que nadie te enseña a usar).
- **Operabilidad:** facilidad de control y uso de la interfaz.
- **Protección frente a errores de usuario:** capacidad del sistema para prevenir fallos cometidos por la interacción del usuario.
- **Estética de la interfaz:** si la interfaz es agradable, cumpliendo patrones de diseño de UX (experiencia de usuario).
- **Accesibilidad:** uso por personas con diversidad funcional (normativas WCAG: pautas internacionales de accesibilidad web).

**Cómo medirla:** puntuación en la escala SUS (*System Usability Scale*: cuestionario estándar de diez preguntas que da un puntaje de 0 a 100); tiempo promedio para completar una tarea por primera vez.

**Errores comunes:** falta de mensajes de error descriptivos; navegación confusa; interfaces no adaptables a móviles (no *responsive*).

Para los profesores del centro, que no estudiaron administración y ya pierden tiempo con el papel, el aprendizaje y la operabilidad no son detalles: son la diferencia entre que usen el sistema o lo abandonen.

### 2.5 Fiabilidad

Grado en que un sistema **realiza sus funciones bajo condiciones especificadas durante un período de tiempo** determinado.

- **Madurez:** frecuencia con la que el sistema falla en condiciones normales.
- **Disponibilidad:** fracción del tiempo en que el sistema está operativo y accesible.
- **Tolerancia a fallos:** capacidad de operar adecuadamente a pesar de fallos de hardware o software.
- **Capacidad de recuperación (resiliencia):** habilidad para restaurar datos y estado del sistema tras una interrupción.

**Cómo medirla:** tiempo medio entre fallos (MTBF); porcentaje de *uptime* anual — los famosos "nueves", 99,9%; tiempo de recuperación (MTTR: tiempo medio hasta volver a operar después de un fallo).

**Errores comunes:** no configurar respaldos automatizados de base de datos; ausencia de balanceadores de carga (componente que reparte el tráfico entre varios servidores); carencia de mecanismos como *circuit breakers* (cortar la llamada a un componente que está fallando para no arrastrar al resto) o reintentos.

El 99,9% de la Parte 3 §3.3 vive acá, con su contingencia a cuestas.

### 2.6 Seguridad

Protección de la información y los datos de manera que **personas o sistemas no autorizados no puedan leerlos ni modificarlos**, garantizando el acceso a los autorizados.

- **Confidencialidad:** los datos solo son accesibles a quienes tienen autorización.
- **Integridad:** prevención de modificaciones no autorizadas en datos y código.
- **No repudio:** capacidad de probar que una acción o transacción ocurrió.
- **Responsabilidad:** rastreabilidad de las acciones de un usuario hacia su identidad (auditoría).
- **Autenticidad:** verificación de la identidad de usuarios y sistemas.

**Cómo medirla:** número de vulnerabilidades detectadas en análisis estáticos/dinámicos (SAST/DAST: herramientas que revisan el código sin ejecutarlo / probando la aplicación en ejecución); tiempo de detección y mitigación de brechas.

**Errores comunes:** almacenar contraseñas en texto plano; no cifrar en tránsito (HTTPS/TLS) ni en reposo (AES); omitir autenticación multifactor (MFA); no registrar logs de auditoría inmutables.

En el centro de entrenamiento, el pago de cuotas y los datos de salud (discapacidad) son lo que pide confidencialidad e integridad.

### 2.7 Mantenibilidad

Posibilidad de **modificar un producto o sistema para mejorarlo, corregirlo o adaptarlo** a los cambios del entorno y los requisitos.

- **Modularidad:** nivel de independencia de los componentes del sistema.
- **Reusabilidad:** capacidad de usar activos en otros módulos o proyectos.
- **Analizabilidad:** facilidad de diagnosticar deficiencias o causas de fallos.
- **Capacidad de ser modificado (modificabilidad):** grado en que puede alterarse de manera segura, sin introducir regresiones (romper lo que ya andaba).
- **Capacidad de ser probado (*testability*):** facilidad con la que se pueden establecer criterios de prueba y ejecutar tests.

**Cómo medirla:** complejidad ciclomática de McCabe (métrica que cuenta el número de caminos de ejecución linealmente independientes en el código: más caminos, más difícil de mantener y probar); porcentaje de cobertura de código (*code coverage*: cuánto del código fuente —líneas, funciones o caminos— se ejecuta cuando corren las pruebas automatizadas).

**Errores comunes:** código espagueti; acoplamiento severo; funciones gigantescas sin pruebas unitarias automatizadas; falta de documentación técnica de la arquitectura.

### 2.8 Portabilidad

Capacidad de un sistema, producto o componente para **ser transferido de un entorno a otro**.

- **Adaptabilidad:** capacidad de ajustarse a diferentes entornos de ejecución.
- **Facilidad de instalación:** esfuerzo necesario para instalar el sistema con éxito.
- **Capacidad de ser reemplazado (facilidad de sustitución):** habilidad para reemplazar un componente por otro similar en el mismo entorno.

**Cómo medirla:** tiempo necesario para portar la aplicación a un nuevo sistema operativo; tasa de éxito de despliegues automatizados en distintos entornos.

**Errores comunes:** uso de rutas absolutas locales; dependencias estrechamente ligadas a un sistema operativo específico.

Para una Junta que piensa abrir sucursales, la portabilidad es un criterio de selección directo: ¿la solución enlatada se instala en otra sede sin volver a empezar?

> **Para el parcial, si te preguntan:** *Enumerá las características del modelo de calidad del producto de la ISO/IEC 25010.*
> Adecuación funcional, eficiencia de desempeño, compatibilidad, usabilidad, fiabilidad, seguridad, mantenibilidad y portabilidad. Cada una se descompone en subcaracterísticas medibles (por ejemplo, fiabilidad en madurez, disponibilidad, tolerancia a fallos y capacidad de recuperación), que son los atributos que un RNF puede especificar.

## 3. 🔴 Lo que agregó la versión 2023: safety

La versión vigente, **ISO 25010:2023**, incluye la característica de **seguridad física (*safety*)**: integrada como característica del producto para evaluar **la prevención de riesgos físicos o daños materiales causados por fallos del software**. Es clave en IoT y en dispositivos médicos: un software que controla una bomba de insulina o un vehículo tiene fallos que lastiman.

No confundir con la seguridad de la sección 2.6 (*security*), que protege la información. *Safety* protege a las personas y las cosas.

> **Para el parcial, si te preguntan:** *¿Qué cambió en la ISO 25010 en su versión 2023?*
> Incorporó *safety* (seguridad física) como característica del producto, para evaluar la prevención de riesgos físicos o daños materiales causados por fallos del software, en respuesta al crecimiento de IoT, la inteligencia artificial y los dispositivos que actúan sobre el mundo físico. Es distinta de la seguridad de la información (*security*).

## 4. 🔴 Cinco ejemplos resueltos

Cada uno escrito con la estructura de la Parte 3, y ubicado en su característica y subcaracterística. Son las mejores prácticas de redacción con las que se corrige: fijate que en cada uno el atributo se puede señalar con el dedo.

**1. Eficiencia de desempeño → comportamiento temporal**
> *El tiempo máximo de notificación al usuario desde el evento que la origina es de 2 segundos.*
> - Objeto: notificación
> - Atributo: comportamiento temporal
> - Valor: 2
> - Unidad: segundos

Fijate el detalle "desde el evento que la origina": define desde dónde se mide. Sin eso, el valor es ambiguo (¿desde que se genera? ¿desde que se envía?).

**2. Fiabilidad → disponibilidad**
> *La disponibilidad del sistema es de al menos el 99,9% del tiempo durante horario laboral (5x9: lunes a viernes, de 9 a 17).*
> - Objeto: sistema
> - Atributo: disponibilidad
> - Valor: 99,9
> - Unidad: porcentaje

*Nota de la cátedra:* el equipo de Operaciones debe tener registro de las caídas del sistema para verificar este valor; ante cada fallo, hacer el análisis de causas para su resolución. Es decir: el RNF trae aparejado el mecanismo que permite medirlo.

⚠️ **Sobre este ejemplo.** En la guía escrita de la cátedra, la descomposición de este mismo ejemplo aparece como *objeto: disponibilidad · atributo: tiempo*, que invierte el esquema definido en el propio documento (el objeto es lo que se mide; el atributo, su cualidad). Lo que ves arriba es la descomposición consistente con la regla. Para el examen: aplicá la regla —objeto = sistema, atributo = disponibilidad— y, si te muestran la otra versión, saber reconocer que es la misma estructura con los rótulos cruzados.

**3. Usabilidad → aprendizaje**
> *El tiempo máximo de completitud de la inscripción del alumno es de 5 minutos en la primera ejecución sin asistencia externa, para el 80% del personal de la Secretaría de Alumnos.*
> - Objeto: inscripción
> - Atributo: aprendizaje
> - Valor: 5
> - Unidad: minutos

*Nota de la cátedra:* acá se combina con el porcentaje de usuarios que lo logran dentro de ese tiempo (80%), que es una **métrica complementaria**. Un RNF puede llevar más de un número cuando uno solo no alcanza para verificarlo.

**4. Mantenibilidad → capacidad de ser probado**
> *Al menos el 80% de las funcionalidades del sistema especificadas en el Documento de Requisitos deben poder ser testeadas con pruebas automatizadas.*
> - Objeto: funcionalidades del sistema
> - Atributo: capacidad de ser probado
> - Valor: 80
> - Unidad: porcentaje

**5. Portabilidad → facilidad de instalación**
> *El tiempo máximo de instalación del sistema en un equipo con Windows 11 es de 10 minutos, sin intervención del equipo de soporte.*
> - Objeto: sistema / ejecutable
> - Atributo: tiempo de instalación
> - Valor: 10
> - Unidad: minutos

Mirá "sin intervención del equipo de soporte" y "sin asistencia externa" en el 3: son **condiciones de medición**. Cambian completamente el valor; por eso van escritas.

Una última cosa sobre los valores. En ejemplos técnicos a veces vas a ver "0.x" como valor: es un *placeholder*, un lugar reservado para el umbral específico, que se define contractualmente con el cliente. El requerimiento final nunca queda con el placeholder.

> **Para el parcial, si te preguntan:** *Escribí un requerimiento no funcional de fiabilidad para un sistema de reservas y descomponelo.*
> "La disponibilidad del sistema de reservas es de al menos el 99,5% del tiempo, de lunes a sábado de 8 a 20." Objeto: sistema de reservas · Atributo: disponibilidad · Valor: 99,5 · Unidad: porcentaje. Verificación: registro de caídas por parte de Operaciones.

## 5. 🟡 Anexo — El modelo de calidad de uso

Es el otro modelo de la norma. La **calidad de uso** es el grado en que un producto o sistema puede ser utilizado por usuarios específicos para satisfacer sus necesidades y lograr objetivos específicos con eficacia, eficiencia, ausencia de riesgo y satisfacción, en contextos de uso específicos. Mide la experiencia del uso real, no las propiedades del producto.

En este curso **no se trabajan en forma directa** métricas relacionadas con este modelo. Está acá para que sepas que existe y no lo confundas con el de producto.

Cinco características:

1. **Eficacia:** precisión y exhaustividad con la que los usuarios alcanzan los objetivos especificados.
2. **Eficiencia:** recursos gastados en relación con la precisión y exhaustividad con la que los usuarios alcanzan los objetivos.
3. **Satisfacción:** grado de satisfacción de las necesidades del usuario en un contexto de uso determinado. Se divide en:
   - *Utilidad:* satisfacción con la percepción de haber alcanzado los objetivos pragmáticos, incluidos los resultados y las consecuencias del uso.
   - *Confianza:* grado de confianza del usuario u otra parte interesada en que el sistema se comportará como está previsto.
   - *Agrado:* grado en que el usuario obtiene agrado al satisfacer sus necesidades personales.
   - *Comodidad:* satisfacción del usuario en cuanto a su comodidad física.
4. **Ausencia de riesgo:** grado en que el producto mitiga el riesgo potencial para la situación económica, la vida humana, la salud o el medio ambiente. Consiste en:
   - *Mitigación de riesgos económicos:* para la situación financiera, el funcionamiento eficiente, la propiedad comercial, la reputación u otros recursos.
   - *Mitigación de riesgos de salud y seguridad:* para las personas en los contextos de uso previstos.
   - *Mitigación del riesgo medioambiental:* para la propiedad o el medio ambiente.
5. **Cobertura del contexto:** grado en que el producto puede usarse con eficacia, eficiencia, ausencia de riesgo y satisfacción tanto en los contextos de uso especificados como más allá de los inicialmente identificados. Incluye:
   - *Completitud de contexto:* en todos los contextos especificados — por ejemplo, que el software sea utilizable en una pantalla chica, con poco ancho de banda, por un usuario no experto, y en modo tolerante a fallos (sin conectividad).
   - *Flexibilidad:* en contextos que van más allá de los especificados inicialmente en los requisitos.

---

## Info operativa de esta parte

- Los **tipos de RNF no se desarrollan en clase**: se dejan en la guía escrita. Esta parte los cubre completos; el examen puede pedirlos.

---

## Qué viene en la Parte 5

Ya tenés el marco (Parte 3) y el catálogo (Parte 4). Ahora, la práctica: la dinámica de defensa de requerimientos, las reglas de redacción que salieron de las correcciones, los seis casos completos con su versión antes y después, la rúbrica de casos de uso que vas a llevar al parcial, y el checkpoint de toda la unidad.

**FIN DE LA PARTE 4**
