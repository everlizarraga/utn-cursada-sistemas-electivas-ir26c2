# E6

> Conversión fiel a Markdown de E6.pdf (6 páginas).

**Avanzamos con la generación de documentación en base a la entrevista realizada.**

## 1er parte:

Realizar el CU en base a los requerimientos funcionales y no funcionales relevados en la entrevista con Junta Directiva y Profesores.

Utilizar Lucidchart para resolver el CU

| ID | Requerimiento | Tipo |
|---|---|---|
| **RF-01** | El profesor debe registrar cuando un cliente/socio presente algún tipo de limitación física durante o previo a un entrenamiento. | Funcional |
| **RF-02** | El sistema debe permitir al gerente visualizar, para cada profesor, el porcentaje de clases dictadas con cupo completo en el mes, a fin de identificar quiénes alcanzan el porcentaje base definido y corresponden al pago del bono. | Funcional |
| **RF-03** | El socio podrá registrar sus asistencias al momento de ingresar al establecimiento | Funcional |
| **RF-04** | El socio podrá darse de baja de una clase desde el sistema. | Funcional |
| **RF-05** | El sistema debe notificar la baja de asistencia a una clase mediante WhatsApp al profesor/es asignado/s a esa clase. | Funcional |
| **RF-06** | Los profesores deben poder emitir comunicaciones (avisos, cupos, plantillas) por WhatsApp a los socios desde el sistema. | Funcional |
| **RF-07** | El sistema debe organizar el uso de las instalaciones diferenciando entre clases con profesor asignadas a un turno fijo, y sectores de uso libre (cardio y musculación). | Funcional |
| **RF-08** | Los profesores deben ser alertados cuando se excede el tiempo limite de uso de las instalaciones. | Funcional |
| **RF-09** | El sistema debe controlar la capacidad máxima de cada clase/sector según el tipo (8 pilates, 7 cardio, 5 musculación, 8 yoga/funcional/stretching). | Funcional |
| **RF-10** | El sistema debe gestionar automáticamente la lista de espera de una clase completa, ofreciendo el lugar por orden de inscripción cuando un socio se da de baja. | Funcional |
| **RF-11** | El sistema debe alertar a los profesores cuando una clase tenga menos de 3 socios anotados, para ofrecerles cambiar de turno. | Funcional |
| **RF-12** | El sistema debe gestionar los planes mensuales de los socios (4, 6, 8 o 12 clases), controlando su vigencia desde la primera clase hasta la misma fecha del mes siguiente. | Funcional |
| **RF-13** | El sistema debe registrar avisos de ausencia de los socios y habilitar la recuperación de clase solo a quienes avisaron con una anticipación de 1 día. | Funcional |
| **RF-14** | El sistema debe notificar a los socios en lista de espera cuando se libere un cupo por ausencia avisada. | Funcional |
| **RF-15** | El sistema debe controlar el tiempo mínimo (30 min) y máximo (120 min) de uso en los sectores sin profesor, dentro del horario de 8 a 20 hs de lunes a sábados. | Funcional |

|  |  |  |
|---|---|---|
| **RNF-01** | El sistema debe confirmar un registro de asistencia en un tiempo no mayor a 2 segundos. | No Funcional (Rendimiento) |
| **RNF-02** | El sistema debe procesar la actualización de una lista de espera (baja de un socio y oferta del cupo al siguiente inscripto) en un tiempo no mayor a 5 segundos. | No Funcional (Rendimiento) |
| **RNF-03** | El sistema debe permitir que el 80% de los profesores puedan registrarse en el sistema en menos de 30 segundos | No Funcional (Usabilidad) |
| **RNF-04** | El sistema debe garantizar la exactitud de los registros de horario, con una tasa de error del 0.1% en la asignación de turnos, evitando inconsistencias que afecten la confiabilidad de los datos de asistencia. | No Funcional (Confiabilidad) |
| **RNF-05** | El inicio de sesión de los clientes debe realizarse en menos de 3 clicks.. | No Funcional (Usabilidad) |
| **RNF-06** | El presente de las clases debe estar disponible en todo el horario de apertura del gimnasio | No Funcional (Confiabilidad) |
| **RNF-07** | Las notificaciones de cancelación de clase deberán ser enviadas por whatsapp a los clientes en menos de 2 minutos desde la cancelación de la misma | No Funcional (Rendimiento) |
| **RNF-08** | El presente de las clases debe ser testeado mediante pruebas E2E para verificar la correcta implementación | No Funcional (Mantenibilidad) |
| **RNF-09** | La cantidad de interacciones para acceder a la ficha del socio, planillas de clases, debe ser menor a 5 | No Funcional (Usabilidad) |

Responder:

¿Pudieron identificar los actores de cada CU o los asumieron en función del requerimiento?

¿Pudieron identificar los CU, y sus relaciones de inclusión, extensión y con el o los actores?

## 2da parte:

a. Indicar para cada requerimiento si cumple con las condiciones de calidad, justificando cada caso.

| Característica | Pregunta guía |
|---|---|
| No ambiguo | ¿Existe una única interpretación posible? |
| Consistente | ¿Se contradice consigo mismo o con otros requisitos? |
| Completo | ¿Contiene todos los elementos necesarios para comprenderlo y desarrollarlo? |
| Verificable | ¿Puedo comprobar su cumplimiento? ¿Existe un procedimiento? |

| ID | Requerimiento | No ambiguo | Consistente | Completo | Realista | Rastreable | Verificable |
|---|---|---|---|---|---|---|---|
| **RF-01** | El profesor debe registrar cuando un cliente/socio presente algún tipo de limitación física durante o previo a un entrenamiento. |  |  |  |  |  |  |
| **RF-02** | El sistema debe permitir al gerente visualizar, para cada profesor, el porcentaje de clases dictadas con cupo completo en el mes, a fin de identificar quiénes alcanzan el porcentaje base definido y corresponden al pago del bono. |  |  |  |  |  |  |
| **RF-03** | El socio podrá registrar sus asistencias al momento de ingresar al establecimiento |  |  |  |  |  |  |
| **RF-04** | El socio podrá darse de baja de una clase desde el sistema. |  |  |  |  |  |  |
| **RF-05** | El sistema debe notificar la baja de asistencia a una clase mediante WhatsApp al profesor/es asignado/s a esa clase. |  |  |  |  |  |  |
| **RF-06** | Los profesores deben poder emitir comunicaciones (avisos, cupos, plantillas) por WhatsApp a los socios desde el sistema. |  |  |  |  |  |  |
| **RF-07** | El sistema debe organizar el uso de las instalaciones diferenciando entre clases con profesor asignadas a un turno fijo, y sectores de uso libre (cardio y musculación). |  |  |  |  |  |  |
| **RF-08** | Los profesores deben ser alertados cuando se excede el tiempo limite de uso de las instalaciones. |  |  |  |  |  |  |
| **RF-09** | El sistema debe controlar la capacidad máxima de cada clase/sector según el tipo (8 pilates, 7 cardio, 5 musculación, 8 yoga/funcional/stretching). |  |  |  |  |  |  |
| **RF-10** | El sistema debe gestionar automáticamente la lista de espera de una clase completa, ofreciendo el lugar por orden de inscripción cuando un socio se da de baja. |  |  |  |  |  |  |
| **RF-11** | El sistema debe alertar a los profesores cuando una clase tenga menos de 3 socios anotados, para ofrecerles cambiar de turno. |  |  |  |  |  |  |
| **RF-12** | El sistema debe gestionar los planes mensuales de los socios (4, 6, 8 o 12 clases), controlando su vigencia desde la primera clase hasta la misma fecha del mes siguiente. |  |  |  |  |  |  |
| **RF-13** | El sistema debe registrar avisos de ausencia de los socios y habilitar la recuperación de clase solo a quienes avisaron con una anticipación de 1 día. |  |  |  |  |  |  |
| **RF-14** | El sistema debe notificar a los socios en lista de espera cuando se libere un cupo por ausencia avisada. |  |  |  |  |  |  |
| **RF-15** | El sistema debe controlar el tiempo mínimo (30 min) y máximo (120 min) de uso en los sectores sin profesor, dentro del horario de 8 a 20 hs de lunes a sábados. |  |  |  |  |  |  |

|  |  | No ambiguo | Consistente | Completo | Realista | Rastreable | Verificable |
|---|---|---|---|---|---|---|---|
| **RNF 01** | El sistema debe confirmar un registro de asistencia en un tiempo no mayor a 2 segundos. |  |  |  |  |  |  |
| **RNF 02** | El sistema debe procesar la actualización de una lista de espera (baja de un socio y oferta del cupo al siguiente inscripto) en un tiempo no mayor a 5 segundos. |  |  |  |  |  |  |
| **RNF 03** | El sistema debe permitir que el 80% de los profesores puedan registrarse en el sistema en menos de 30 segundos |  |  |  |  |  |  |
| **RNF 04** | El sistema debe garantizar la exactitud de los registros de horario, con una tasa de error del 0.1% en la asignación de turnos, evitando inconsistencias que afecten la confiabilidad de los datos de asistencia. |  |  |  |  |  |  |
| **RNF 05** | El inicio de sesión de los clientes debe realizarse en menos de 3 clicks.. |  |  |  |  |  |  |
| **RNF 06** | El presente de las clases debe estar disponible en todo el horario de apertura del gimnasio |  |  |  |  |  |  |
| **RNF 07** | Las notificaciones de cancelación de clase deberán ser enviadas por whatsapp a los clientes en menos de 2 minutos desde la cancelación de la misma |  |  |  |  |  |  |
| **RNF 08** | El presente de las clases debe ser testeado mediante pruebas E2E para verificar la correcta implementación |  |  |  |  |  |  |
| **RNF 09** | La cantidad de interacciones para acceder a la ficha del socio, planillas de clases, debe ser menor a 5 |  |  |  |  |  |  |

b. Para cada uno, reescribirlo correctamente, en caso de corresponder.

---

## Notas de conversión

- **Orden del documento (verificado visualmente):** el bloque "Responder:" con las dos preguntas está al pie de la página 2, después de la tabla de RNF, cerrando la 1er parte; el ítem "b." está al final de la página 6, después de la tabla de calidad de los RNF. Las extracciones automáticas de texto reubican ambos bloques.
- **Tablas que cruzan páginas:** las cuatro tablas del original se cortan por salto de página (RF: páginas 1–2 y 3–5; RNF: páginas 2 y 5–6). Acá se transcriben enteras, sin repetir encabezados, para no partir la estructura.
- **Encabezados faltantes en el original:** la tabla de RNF de la 1er parte no tiene fila de encabezado (arranca directo en RNF-01); la tabla de calidad de los RNF tiene las dos primeras celdas de encabezado vacías (sin "ID" ni "Requerimiento"). Se replican como filas de encabezado vacías, ya que Markdown exige la fila.
- **IDs de RNF inconsistentes entre partes:** en la 1er parte van con guion (`RNF-01`), en la 2da parte van sin guion (`RNF 01`). Transcripto tal cual en cada caso.
- **Criterios de calidad desalineados:** la tabla "Característica / Pregunta guía" define 4 características (No ambiguo, Consistente, Completo, Verificable), pero las tablas de evaluación tienen 6 columnas: agregan "Realista" y "Rastreable", que no tienen pregunta guía asociada.
- **Celdas de evaluación vacías:** todas las columnas de calidad de la 2da parte están en blanco en el original (son para completar). Se transcriben vacías.
- **Errores del original, transcriptos sin corregir:** "tiempo limite" sin tilde (RF-08); "clicks.." con doble punto (RNF-05); "whatsapp" en minúscula en RNF-07 frente a "WhatsApp" en RF-05 y RF-06.
- **Cortes de palabra por ancho de celda reunidos:** "Mantenibilida / d" → "Mantenibilidad"; "Consis / tente" → "Consistente"; ídem el resto de los encabezados de columna. Son quiebres de línea del renderizado, no del texto.
- **Sin hipervínculos:** se revisaron las anotaciones URI del PDF; no hay ninguna (Lucidchart se menciona solo como texto).
- **Sin elementos visuales:** el documento no tiene diagramas, imágenes ni código; es texto y tablas.

---

**FIN DEL ARCHIVO FUENTE — E6**
