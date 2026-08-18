# SWEBOK Guide V3.0 — Capítulo 1: Requisitos de Software (Parte 4 de 4)

> Traducción al español, fiel y completa, de `04-SWEBOOK_v3_Chap1.pdf` (18 páginas). Esta parte cubre las páginas 1-15 a 1-18: matriz de tópicos contra material de referencia, lecturas recomendadas y referencias. Cierra el capítulo.

**Notas de conversión**

- **Es una traducción, no una transcripción.** Ante cualquier duda, prevalece el PDF original.
- **Títulos de obras sin traducir.** Los títulos de libros, papers y publicaciones de las secciones de Lecturas recomendadas y Referencias se transcriben tal cual, en su idioma original, porque son la referencia con la que se busca y cita cada obra. Los comentarios sobre cada lectura sí están traducidos.
- **La matriz fue verificada visualmente**, celda por celda, sobre las páginas 1-15 y 1-16 rasterizadas a 200 dpi. La extracción de texto la desordenaba por completo: los encabezados de columna están escritos en vertical y las celdas vacías no dejan rastro. Las celdas que aparecen vacías en esta tabla están vacías en el original.
- **Cómo leer los códigos de la matriz** (el documento no lo explica, se aclara acá): `c4` significa capítulo 4; `c4s1` significa capítulo 4, sección 1; `c12s2–5` significa capítulo 12, secciones 2 a 5. `[1*]` remite a Sommerville y `[2*]` a Wiegers, las dos obras de referencia de todo el capítulo.
- **Inconsistencias del original en los nombres de autores, conservadas.** El capítulo escribe el mismo apellido de dos formas distintas según la sección: *Beus-Dukic* en Lecturas recomendadas y *Beus-Deukic* en la referencia [5]; *A. Antón* y *A.I. Antón*; *A. Finkelstein* y *C.W. Finkelstein*; *N. Maiden* y *N.A. Maiden*. Se transcriben tal cual; **no se unificaron**.
- **Inconsistencia adicional que afecta a la Parte 1.** La sigla INCOSE se expande de dos maneras distintas en el capítulo: en la tabla de acrónimos y en la referencia [3] figura como *International Council on Systems Engineering*, mientras que en la sección 1.6 el texto la expande como *International Council on Software and Systems Engineering*. Ambas formas se conservaron en su lugar. La denominación oficial de la organización es la primera.
- Esta parte no contiene figuras ni diagramas.
- El documento no contiene hipervínculos: se revisaron las anotaciones del PDF y no hay ninguno.

---

## MATRIZ DE TÓPICOS CONTRA MATERIAL DE REFERENCIA

| Tópico | Sommerville 2011 `[1*]` | Wiegers 2003 `[2*]` |
|---|---|---|
| **1. Fundamentos de los requisitos de software** | | |
| 1.1. Definición de un requisito de software | c4 | c1 |
| 1.2. Requisitos de producto y requisitos de proceso | c4s1 | c1, c6 |
| 1.3. Requisitos funcionales y no funcionales | c4s1 | c12 |
| 1.4. Propiedades emergentes | c10s1 | |
| 1.5. Requisitos cuantificables | | c1 |
| 1.6. Requisitos de sistema y requisitos de software | c10s4 | c1 |
| **2. Proceso de requisitos** | | |
| 2.1. Modelos de proceso | c4s4 | c3 |
| 2.2. Actores del proceso | | c1, c2, c4, c6 |
| 2.3. Soporte y gestión del proceso | | c3 |
| 2.4. Calidad y mejora del proceso | | c22, c23 |
| **3. Elicitación de requisitos** | | |
| 3.1. Fuentes de requisitos | c4s5 | c5, c6, c9 |
| 3.2. Técnicas de elicitación | c4s5 | c6 |
| **4. Análisis de requisitos** | | |
| 4.1. Clasificación de requisitos | c4s1 | c12 |
| 4.2. Modelado conceptual | c4s5 | c11 |
| 4.3. Diseño arquitectónico y asignación de requisitos | c10s4 | c17 |
| 4.4. Negociación de requisitos | c4s5 | c7 |
| 4.5. Análisis formal | c12s5 | |
| **5. Especificación de requisitos** | | |
| 5.1. Documento de definición del sistema | c4s2 | c10 |
| 5.2. Especificación de requisitos del sistema | c4s2, c12s2, c12s3, c12s4, c12s5 | c10 |
| 5.3. Especificación de requisitos de software | c4s3 | c10 |
| **6. Validación de requisitos** | | |
| 6.1. Revisiones de requisitos | c4s6 | c15 |
| 6.2. Prototipado | c4s6 | c13 |
| 6.3. Validación de modelos | c4s6 | c15 |
| 6.4. Pruebas de aceptación | c4s6 | c15 |
| **7. Consideraciones prácticas** | | |
| 7.1. Naturaleza iterativa del proceso de requisitos | c4s4 | c3, c16 |
| 7.2. Gestión de cambios | c4s7 | c18, c19 |
| 7.3. Atributos de requisitos | c4s1 | c12, c14 |
| 7.4. Trazabilidad de requisitos | | c20 |
| 7.5. Medición de requisitos | c4s6 | c18 |
| **8. Herramientas de requisitos de software** | | c21 |

---

## LECTURAS RECOMENDADAS

**I. Alexander y L. Beus-Dukic, *Discovering Requirements* [5].**

Un libro sobre requisitos de software fácil de digerir y de orientación práctica; es quizás el mejor de los libros de texto actuales sobre cómo encajan entre sí los diversos elementos de los requisitos de software. Está lleno de consejos prácticos sobre (por ejemplo) cómo identificar a los distintos stakeholders del sistema y cómo evaluar soluciones alternativas. Su cobertura es ejemplar y sirve como referencia útil para técnicas clave, como el modelado de casos de uso y la priorización de requisitos.

**C. Potts, K. Takahashi y A. Antón, "Inquiry-Based Requirements Analysis" [6].**

Este paper es un relato fácil de digerir de un trabajo que ha demostrado ser muy influyente en el desarrollo del tratamiento de requisitos. Describe cómo y por qué la elaboración de requisitos no puede ser un proceso lineal por el cual el analista simplemente transcribe y reformula los requisitos elicitados del cliente. El rol de los escenarios se describe de una manera que ayuda a definir su uso en el descubrimiento y la descripción de requisitos.

**A. van Lamsweerde, *Requirements Engineering: From System Goals to UML Models to Software Specifications* [7].**

Sirve como buena introducción a la ingeniería de requisitos, pero su valor único es como libro de referencia del lenguaje de modelado de requisitos orientado a objetivos KAOS. Explica por qué el modelado de objetivos es útil y muestra cómo puede integrarse con técnicas de modelado mainstream usando UML.

**O. Gotel y A. Finkelstein, "An Analysis of the Requirements Traceability Problem" [8].**

Este paper es un trabajo de referencia clásico sobre un elemento clave de la gestión de requisitos. Basado en estudios empíricos, expone las razones de la trazabilidad efectiva de requisitos y las barreras que la impiden. Es lectura esencial para comprender por qué la trazabilidad de requisitos es un elemento esencial de un proceso de software efectivo.

**N. Maiden y C. Ncube, "Acquiring COTS Software Selection Requirements" [9].**

Este paper es significativo porque reconoce explícitamente que los productos de software a menudo integran componentes de terceros. Ofrece perspectivas sobre los problemas de seleccionar software preexistente para satisfacer requisitos: usualmente hay un desajuste. Esto desafía algunos de los supuestos que sustentan buena parte del tratamiento tradicional de requisitos, que tiende a asumir software a medida.

---

## REFERENCIAS

**[1\*]** I. Sommerville, *Software Engineering*, 9th ed., Addison-Wesley, 2011.

**[2\*]** K.E. Wiegers, *Software Requirements*, 2nd ed., Microsoft Press, 2003.

**[3]** INCOSE, *Systems Engineering Handbook: A Guide for System Life Cycle Processes and Activities*, version 3.2.2, International Council on Systems Engineering, 2012.

**[4]** S. Friedenthal, A. Moore, y R. Steiner, *A Practical Guide to SysML: The Systems Modeling Language*, 2nd ed., Morgan Kaufmann, 2012.

**[5]** I. Alexander y L. Beus-Deukic, *Discovering Requirements: How to Specify Products and Services*, Wiley, 2009.

**[6]** C. Potts, K. Takahashi y A.I. Antón, "Inquiry-Based Requirements Analysis", *IEEE Software*, vol. 11, no. 2, Mar. 1994, pp. 21–32.

**[7]** A. van Lamsweerde, *Requirements Engineering: From System Goals to UML Models to Software Specifications*, Wiley, 2009.

**[8]** O. Gotel y C.W. Finkelstein, "An Analysis of the Requirements Traceability Problem", *Proc. 1st Int'l Conf. Requirements Eng.*, IEEE, 1994.

**[9]** N.A. Maiden y C. Ncube, "Acquiring COTS Software Selection Requirements", *IEEE Software*, vol. 15, no. 2, Mar.–Apr. 1998, pp. 46–56.

---

**FIN DEL ARCHIVO FUENTE — SWEBOK Guide V3.0, Capítulo 1: Requisitos de Software (Parte 4 de 4)**
