# Introducción / Conceptos de Ing. De Requisitos

> Conversión fiel a Markdown de Introduccion_ConceptosIR.pdf (18 slides).

**Notas de conversión:**
- Slide 7: "managment" y "tecnicas" figuran así (sin corregir) en el original.
- Slide 10: "los req. Que verdaderamente reflejen..." — la mayúscula tras el punto de abreviatura está así en el original.
- Slide 12: el encabezado de la tabla dice "Dificultad escencial" (sic) en el original; en las slides 10 y 11 dice "esencial".
- Slides 13, 14 y 17 incluyen recortes de texto en inglés (imagen de un libro/estándar, tipografía serif); se transcriben tal cual, con guiones de corte de línea eliminados por legibilidad.
- Se buscaron hipervínculos en las anotaciones del PDF: no hay.

---

## Slide 1 — Introducción / Conceptos de Ing. De Requisitos

Ing. Laura Varela

## Slide 2 — Agenda

Conceptos de Ingeniería de Requisitos

Roles en el proceso de requisitos

Ejercitación grupal

Req. funcionales y no funcionales, definición y diferencias.

Ejercitación grupal

## Slide 3 — Roles - Usuarios/Stakeholders/Clientes

- **Usuarios**:
  - son aquellos que van a operar el sistema (interactuar directamente con el)

*(La slide incluye dos fotografías de usuarios operando computadoras — una mujer mayor frente a una PC de escritorio y dos niños en computadoras de un aula — y un ícono de dos personas. El mensaje visual: usuarios pueden ser personas de cualquier edad y contexto.)*

Diagrama (esquema de permisos):

```
                    ┌─ Grupo de usuarios ──► Perfil de acceso ──► Grupo de permisos
                    │                                        └──► Grupo de permisos
USUARIO ────────────┼─ Grupo de usuarios ──► Perfil de acceso ──► Grupo de permisos
                    │                                        
                    └─ Grupo de usuarios ──► Perfil de acceso ──► Grupo de permisos
```

*(Descripción del diagrama: a la izquierda, un único "USUARIO"; de él salen flechas hacia tres "Grupo de usuarios"; cada grupo de usuarios apunta a un "Perfil de acceso"; los perfiles de acceso apuntan —con flechas que se cruzan, algunas a más de un destino— a cuatro "Grupo de permisos" representados con candados. Ilustra cómo un usuario se relaciona con permisos a través de grupos y perfiles de acceso.)*

## Slide 4 — Roles - Usuarios/Stakeholders/Clientes

- **Cliente**: son aquellos que representan el mercado al que apunta el software. También son aquellos que aportan fondos para pagar el desarrollo y su posterior mantenimiento
- **Stakeholder**: son aquellos que tienen algún interés en el desarrollo e implementación de la solución de software propuesta.
  - Ejemplos:
    - Entes reguladores
    - Áreas de la empresa que no están involucradas directamente en el desarrollo
    - Clientes
    - Aquellos usuarios que tienen injerencia en la toma de decisiones

## Slide 5 — Contexto de los Usuarios/Stakeholders/Clientes

- **Negocio**: es el objetivo de una organización, la razón por la cual la misma existe.
  - El negocio puede pertenecer al ámbito público o privado; puede tener o no fines de lucro.
- **Proceso de negocio**: es el conjunto de procesos que realiza la organización para llevar a cabo su objetivo de negocio, de acuerdo a su misión, visión y valores

*(La slide incluye una ilustración decorativa de figuras humanas azules sobre engranajes.)*

## Slide 6 — Roles del Ingeniero de Requisitos

**Facilitador**
- Asistir a los stakeholders y usuarios en el proceso
- Permitir que se sientan seguros y participativos en el proceso

**Mediador**
- Facilitar la resolución de conflictos de intereses (entre REQ)
- Facilitar la priorización de REQ

**Desarrollador**
- Documenta y define para el posterior trabajo del equipo de desarrollo
- Eventualmente, debe conocer las limitaciones de la arquitectura/infraestructura/estado del arte

*(Cada rol aparece como una banda naranja con una ilustración: dos figuras dialogando en sillones (Facilitador); una figura roja al centro de varios grupos (Mediador); figuras armando piezas de rompecabezas (Desarrollador).)*

## Slide 7 — Responsabilidades del Ing. Requisitos

**Liderar el proceso de elicitación**
- Aplicar aspectos de project managment
- Comunicar efectivamente a stakeholders/usuarios

**Documentar**
- La documentación de los req. es la base de las próximas fases del proyecto
- Aplicar diferentes tecnicas (UML, escenarios, user stories, etc.)

**Validar los requerimientos**
- Con los usuarios, para poder avanzar sobre una base cierta de elicitación

*(Mismo formato de bandas naranjas con ilustraciones: figura azul destacada frente a un grupo (Liderar); hilera de libros en dominó de colores (Documentar); figura junto a un tilde verde grande (Validar).)*

## Slide 8 — Elicitación de Requisitos

- Antes de planificar un proyecto de software, se deberían establecer sus **objetivos y su ámbito de aplicación,** considerando soluciones alternativas e identificando tanto dificultades técnicas como de gestión. El desarrollador de software y el cliente deben reunirse para definir los **objetivos del proyecto y su ámbito.**
- Los objetivos identifican las metas generales del proyecto sin considerar cómo se conseguirán. Una vez que se han comprendido los objetivos y el ámbito del proyecto, se consideran las soluciones alternativas.
- Además, los objetivos establecidos permiten posteriormente formular los requerimientos del Sistema de Software

*(Ilustraciones decorativas: tres figuras azules reunidas alrededor de una mesa con notebook; figura pensativa junto a casillas con un tilde azul.)*

## Slide 9 — Dificultades del Proceso de IR

- Un estudio entre 372 organizaciones, demostró que para 179 de ellas, el soporte de las aplicaciones de software no eran consistentes, o lo eran muy poco, con los procesos de negocio [Wolf and Harmon 2012].
- Se detectaron dificultades "esenciales" y otras "accidentales"
- **Esenciales**: son inherentes lo que el producto intenta lograr como objetivo
- **Accidentales**: se llega a ellas a través de prácticas inadecuadas.

## Slide 10 — Dificultades del Proceso de IR

| Dificultad esencial | Dificultad accidental | Desafíos |
|---|---|---|
| Entender lo que el cliente necesita=> los clientes no saben realmente lo que necesitan o tienen muy poca idea de sus requerimientos | Utilizar prácticas inadecuadas de elicitación=> los clientes no pueden articular los req. Que verdaderamente reflejen sus necesidades de negocios. | Los analistas de sistemas deben anticipar o seleccionar la elicitación de req. y entender a la organiz. en profundidad. Los modelos de procesos de negocio deben conducir la elicitación de req. |

## Slide 11 — Dificultades del Proceso de IR

| Dificultad esencial | Dificultad accidental | Desafíos |
|---|---|---|
| Comunicación efectiva con los stakeholder a partir del "gap" entre los dominios de negocio y de sistemas=> la SRS tiene muchos "lectores" con diferentes puntos de vista y conocimientos | Re-trabajo y errores comunicacionales por los diferentes tipos de notación=> ej. BPMN 72% de uso en profesionales de negocios; UML 18%. | Utilizar la misma notación a lo largo del proceso y que los stakeholders usen los mismos productos de trabajo |

## Slide 12 — Dificultades del Proceso de IR

| Dificultad escencial | Dificultad accidental | Desafíos |
|---|---|---|
| Cambios habituales y arbitrarios en los req.=> el proceso de negocio cambia por diversos factores, los req. pueden necesitar adaptarse a procesos de negocio evolutivos | Deficiencias en la trazabilidad "hacia atrás" dificultan la consistencia entre la documentación y el sistema: el proceso de negocio no está alineado con los req. del sistema | La documentación debe "linkear" los proceso de negocio a los artefactos de análisis, diseño e implementación de forma explícita y trazable. |

## Slide 13 — Requerimientos/Definición

*(Recorte en inglés de un libro/estándar, tipografía serif:)*

> **1.1. Definition of a Software Requirement**
>
> At its most basic, a software requirement is a property that must be exhibited by something in order to solve some problem in the real world. It may aim to automate part of a task for someone to support the business processes of an organization, to correct shortcomings of existing software, or to control a device—to name just a few of the many problems for which software solutions are possible.

*(Ilustración decorativa de una lamparita encendida.)*

## Slide 14 — Requerimientos funcionales

*(Recorte en inglés, tipografía serif:)*

> *Functional* requirements describe the functions that the software is to execute; for example, formatting some text or modulating a signal. They are sometimes known as capabilities or features. A functional requirement can also be described as one for which a finite set of test steps can be written to validate its behavior.

**Testeables con una cantidad finita de pasos.**

Fórmulas (a la izquierda, con una flecha hacia el texto de la derecha):

```
ax² + bx + c = 0

x = (−b ± √(b² − 4ac)) / 2a
```

*(Descripción: la ecuación cuadrática general y su fórmula resolvente, usadas como analogía visual de una función con entradas y resultado.)*

**Funciones que el usuario necesita resolver con el sistema, para las que brindará distintos valores de entrada (variables o parámetros).**

## Slide 15 — Requerimientos funcionales f(x)=y

Cómo los escribimos?

En un **nivel alto**: Verbo en infinitivo + objeto sobre el que se actúa

Ej.

> Registrar alumno.

*(El ejemplo aparece flanqueado por dos etiquetas en forma de flecha: "VERBO" apuntando a "Registrar" y "OBJETO" apuntando a "alumno".)*

Resultado: el registro persistente y consistente de un alumno en la base de datos del sistema (sea cual fuere su formato) *(texto resaltado en amarillo y subrayado en el original)*

## Slide 16 — Requerimientos funcionales f(x)=y

Cómo los escribimos?

En un nivel más detallado, se pueden detallar los parámetros de entrada, y el rol que lo requiere

Ej.

> "La *secretaría de alumnos* *registrará/podrá registrar* *un alumno con su DNI, apellido, nombre, tel, email, fecha de ingreso y carrera.*"

*(Sobre la frase hay tres llaves con etiquetas: "ROL" sobre "secretaría de alumnos", "VERBO" sobre "registrará/podrá registrar" y "OBJETO" sobre "un alumno con su DNI, apellido, nombre, tel, email, fecha de ingreso y carrera". Una llave inferior abarca la frase completa y baja hacia "Variable (x)".)*

**Variable (x):** datos del alumno

**Resultado esperado (y)**: registro consistente y persistente del alumno en la base de datos.->testeable *("testeable" resaltado en amarillo en el original)*

## Slide 17 — Requerimientos No Funcionales

*(Recorte en inglés, tipografía serif:)*

> *Nonfunctional* requirements are the ones that act to constrain the solution. Nonfunctional requirements are sometimes known as constraints or quality requirements. They can be further classified according to whether they are performance requirements, maintainability requirements, safety requirements, reliability requirements, security requirements, interoperability requirements or one of many other types of software requirements (see Models and Quality Characteristics in the Software Quality KA).

**MEDIBLES!**

**Restringen el diseño de la solución al requerimiento funcional**

*(Ilustraciones decorativas: figura midiendo con lápiz y regla; figura junto a una señal de prohibido.)*

## Slide 18 — Requerimientos no funcionales

Ej.

- Los alumnos se identifican por el número de legajo asignado por el sistema en el momento de la registración.
- El número de legajo es único y tiene un dígito verificador que se calcula con la sig. fórmula ……
- El sistema deberá verificar que el número de DNI no esté duplicado en la base de datos.
- Todos los campos estarán disponibles para su ingreso en una única pantalla.
- El registro se debe generar en la base de datos en menos de 0.x segundos.

etc.

---

**FIN DEL ARCHIVO FUENTE — Introducción / Conceptos de Ing. De Requisitos**
