# Minuta de reunión — Negociación de cambios en los requerimientos

Proyecto: sistema para el centro de entrenamiento **Vida Sana**

| Dato | Detalle |
|---|---|
| Fecha | Jueves 10/09/2026 |
| Modalidad | Virtual (Zoom) |
| Participantes | Junta Directiva · Profesores · Analistas mediadores (Equipo 3) · Analistas documentadores (Equipos 5 y 6) |
| Motivo | Profesores y Junta Directiva plantearon pedidos contrapuestos después de las entrevistas. Se convoca a ambas partes para mediar y acordar los requerimientos. |
| Objetivo | Llegar a una definición de requerimientos que permita avanzar a la etapa siguiente: preselección de posibles soluciones enlatadas. |
| Elaborada por | Analistas documentadores — Equipos 5 y 6 |

---

## 1. Exposición de posiciones

### 1.1 Junta Directiva

- Registra una **pérdida del 5%** respecto del mes anterior, atribuida a pagos de planes de socios que no se registran.
- Duda de que todas las clases se dicten como corresponde y propone **instalar cámaras** para verificarlo.
- Espera que las cámaras **cuenten las personas presentes** y se integren con la aplicación.
- Sostiene que los profesores aceptaron tareas administrativas al firmar su contrato, pero su objetivo es que la aplicación les quite esa tarea: **el cobro debe hacerse por la aplicación**.
- Plantea las cámaras como **control forense**: cruzar la cantidad de pagos con la cantidad de asistentes de cada clase.
- Considera que la inversión en cámaras se recupera en pocos meses si se frena la pérdida.
- Confirmó su participación en una **feria de fitness en 45 días** y necesita el **acceso por QR** operativo para demostrarlo ante potenciales socios. Acepta arrancar con un MVP.
- El presidente viaja seguido y necesita ver **desde el celular**: clases dictadas en el día, asistentes por clase, socios deudores y recaudación mensual. Con esos datos decidiría abrir más clases o sumar profesores. Se agregarán indicadores más adelante.
- Hoy tiene **una sucursal** y busca expandirse.
- No considera su responsabilidad proveer celulares a los profesores.
- Pide una respuesta con plazos en el corto plazo.

### 1.2 Profesores

- **No quieren realizar cobros ni registros administrativos**: no pueden interrumpir una clase para cobrar. Piden personal administrativo o un sistema que lo resuelva.
- Consultan por las cámaras: quién las controla, dónde se guardan las grabaciones (infraestructura propia o de terceros) y si se instalan en administración o en las salas.
- Les preocupa la **privacidad de los socios**: los socios actuales no fueron avisados y podrían darse de baja. Aclaran que es una preocupación propia, no un reclamo recibido de socios.
- Aceptan las cámaras si se garantiza que no afectan la retención de socios. Les sirven para demostrar cuándo una clase se cancela por falta de alumnos.
- Entienden que con las cámaras dejarían de contar asistentes y de controlar ingresos manualmente.
- Preguntan quién controlará a los socios con deuda.
- El encargado de rutinas necesita **cargar rutinas personalizadas y asignarlas a cada socio**, también cuando está de vacaciones. Hoy se envían en PDF por WhatsApp; piden un lugar centralizado, visible en la aplicación o enviado por WhatsApp. La generación con IA según perfil y progreso sería un plus.
- Algunos profesores **no tienen smartphone** y no podrían recibir notificaciones. Piden que se les provea un dispositivo.

### 1.3 Aportes de los analistas durante la reunión

- La implementación de las cámaras no será completa desde el primer día: habrá una etapa de ajuste que requiere personal de respaldo.
- Si las cámaras solo reconocen personas y no habilitan el ingreso, hace falta un molinete o una persona que controle el acceso.

---

## 2. Negociación punto por punto

**NN:** no negociable. **C:** cedido desde una posición previa.

### 2.1 Junta Directiva

- **C:** acepta que el cobro se realice por la aplicación, quitando esa tarea a los profesores.
- **C:** acepta arrancar con un MVP (acceso por QR y cámaras) y dejar el molinete para una segunda instancia.
- **C:** acepta evaluar la funcionalidad de rutinas, sujeta a su impacto en el presupuesto.
- **NN:** instalación de cámaras.
- **NN:** acceso por QR operativo para la feria de fitness (45 días).
- **NN:** no provee celulares a los profesores.

### 2.2 Profesores

- **C:** aceptan la instalación de cámaras, con la condición de que no afecte la retención de socios.
- **NN:** no realizar cobros ni registros administrativos.
- **Sin acuerdo:** provisión de dispositivos para quienes no tienen smartphone.

---

## 3. Acuerdo final

### 3.1 Requerimientos funcionales

| ID | Requerimiento | Resultado esperado |
|---|---|---|
| RF-01 | El socio podrá registrar el pago de su plan desde la aplicación, indicando el plan y el período que abona. | El pago queda registrado y asociado al socio, sin intervención de los profesores. |
| RF-02 | El socio podrá registrar su ingreso a la sede presentando su código QR personal. | El sistema registra socio, fecha y hora del ingreso, e indica si su plan está vigente. |
| RF-03 | El sistema registrará la cantidad de personas presentes en cada clase a partir de las imágenes de las cámaras. | Cada clase queda registrada con su cantidad de asistentes, fecha y hora. |
| RF-04 | La Junta Directiva podrá consultar, por clase, la cantidad de pagos registrados y la cantidad de asistentes registrados por las cámaras. | Se muestran ambos valores por clase, lo que permite detectar asistentes sin pago registrado. |
| RF-05 | El presidente de la Junta Directiva podrá consultar los indicadores del negocio: cantidad de clases dictadas en el día, cantidad de asistentes por clase, cantidad de socios deudores y recaudación mensual. | Se muestran los cuatro indicadores con los datos registrados hasta el momento de la consulta. |

### 3.2 Requerimientos no funcionales

| ID | Tipo (ISO 25010) | Requerimiento |
|---|---|---|
| RNF-01 | Eficiencia de desempeño — comportamiento temporal | Los indicadores del RF-05 deberán reflejar los registros con una demora máxima de [N] minutos. (Valor a confirmar con la Junta Directiva: se pidió "tiempo real".) |
| RNF-02 | Portabilidad | La consulta del RF-05 deberá poder realizarse desde un teléfono celular con conexión a internet, fuera de la sede. |

### 3.3 Acuerdos sobre la gestión del proyecto

- El sistema se entrega por etapas: un **MVP** con el acceso por QR y la integración de cámaras, y ciclos posteriores para el resto.
- El molinete queda para una segunda instancia.
- Los analistas enviarán **dentro de las 72 horas** (fin de semana incluido) esta minuta y una estimación de plazos. La fecha se fija recién cuando la Junta confirme los requerimientos.

### 3.4 Puntos sin resolver

| Tema | Situación | Próximo paso |
|---|---|---|
| Plazo de 45 días para el acceso por QR | NN de la Junta (feria de fitness). Los analistas no comprometen fecha sin requerimientos definidos. | Estimación en la respuesta de 72 h. |
| Personal administrativo durante la implementación | Propuesta de los analistas: 1 o 2 personas (o profesores capacitados) como respaldo mientras se ajusta el sistema. Los profesores no aceptan sumar tareas. | Los analistas presentan la propuesta; Junta y profesores la aceptan o no. |
| Cámaras: ubicación, visualización y almacenamiento | Sin definir dónde se instalan, quién ve las imágenes, dónde y por cuánto tiempo se guardan (propio o de terceros), ni su costo. | Relevamiento técnico y de costos. |
| Aviso a los socios sobre las cámaras | Preocupación de los profesores por la privacidad y posibles bajas. No hay reclamos de socios registrados. | Relevar la opinión de los socios en el cuestionario. |
| Control de ingreso ante fallas | Sin molinete, el QR y las cámaras no impiden el ingreso. Si fallan, hace falta una persona que atienda. | Definir junto con el personal administrativo. |
| Dispositivos para profesores sin smartphone | NN de la Junta: no los provee. Los profesores los piden para recibir notificaciones. | Tratar en una próxima reunión. |
| Rutinas de entrenamiento | Se requiere cargar rutinas personalizadas mensuales y asignarlas a cada socio (manual; IA como opción). Falta definir el canal (aplicación o WhatsApp) y el costo. | La Junta evalúa el impacto en el presupuesto. |
| Magnitud del negocio | Hoy una sucursal, con intención de expandirse. Faltan cantidad de socios, profesores y sucursales previstas. | Cuestionario complementario a la Junta. |
