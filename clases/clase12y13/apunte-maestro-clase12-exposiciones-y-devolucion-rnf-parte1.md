# Apunte maestro — Clase 12 · Parte 1
## Dos fracasos célebres de la IR: LASCAD y el Virtual Case File del FBI

> **Sobre esta parte.** La clase 12 tuvo tres bloques. Esta parte cubre el primero: **los casos** que se analizaron en el TP de investigación. Hay dos fracasos reales de sistemas de información, contados de punta a punta y leídos con los lentes de la Ingeniería de Requisitos.
> La **Parte 2** reúne qué se valoró y qué se corrigió en la forma de exponer.
> La **Parte 3** es la devolución de los RNF del primer parcial, que es lo más evaluable de la clase.
>
> **De dónde venís.** Se asume lo visto hasta la clase 11: stakeholders, usuarios y clientes; RF, RNF y reglas de negocio; técnicas de elicitación; entrevistas, cuestionarios y negociación; casos de uso; escenarios.

---

## 0. 🟡 Qué es un caso de investigación y cómo leerlo

El TP de investigación pide tomar un **fracaso célebre** de un sistema de información, reconstruir qué pasó y explicar **por qué** pasó desde la Ingeniería de Requisitos. Los casos asignados este cuatrimestre fueron tres:

- **LASCAD:** el despacho de ambulancias de Londres, 1992.
- **Virtual Case File:** el sistema de expedientes del FBI, 2000-2005.
- **El aeropuerto de Denver.**

En esta clase se expusieron los dos primeros (LASCAD por dos equipos distintos). Denver queda para la clase siguiente.

Para leer los dos casos de esta parte conviene usar las mismas cinco preguntas:

1. **¿Qué dolor quería resolver la organización?** Nadie encara un proyecto así por capricho: había un problema real.
2. **¿Qué pasó?** Línea de tiempo y hechos.
3. **¿Por qué falló?** Casi nunca hay una sola causa, pero suele haber un origen común.
4. **¿Quién tenía responsabilidad y qué se debió haber hecho distinto?**
5. **¿Qué cambió hoy y qué sigue igual?**

---

# 🔴 CASO 1 — LASCAD (Londres, 1992)

> **LASCAD** = *London Ambulance Service Computer-Aided Despatch*. Es el sistema de **despacho asistido por computadora** del servicio de ambulancias de Londres. "Despacho" es la operación de decidir qué ambulancia sale hacia qué emergencia.

## 1. 🟡 El dolor: despachar ambulancias con papel y radio

Antes de 1992 el despacho era **manual**. Así funcionaba:

- Alguien llama a emergencias.
- Un operador anota el incidente en papel.
- Otro ubica la ambulancia disponible más cercana, por radio y por experiencia propia, y se la asigna.

Todo dependía de la coordinación y del oficio de la gente de la sala de control.

El **objetivo** del sistema nuevo era automatizar gran parte de ese proceso: registrar las llamadas, localizar el incidente, saber qué ambulancias estaban libres y dónde, y **decidir automáticamente** cuál mandar. La idea de fondo era razonable: bajar los tiempos de respuesta y aprovechar mejor los vehículos.

El sistema descansaba sobre un **supuesto clave**, que es donde empieza el problema:

> La asignación automática solo funciona si el sistema recibe **datos oportunos y precisos** sobre la ubicación y el estado de cada ambulancia.

```
  ANTES                      OBJETIVO                       SUPUESTO CLAVE
  papel + radio +   ───►     registrar, localizar   ───►    datos de ubicación y
  coordinación manual        y asignar más rápido           disponibilidad siempre
                             (automáticamente)              correctos y a tiempo
```

## 2. 🟡 La línea de tiempo: cómo se llegó al 26 de octubre

| Fecha | Qué pasó | Por qué importa |
|---|---|---|
| **1989-90** | Conflicto gremial entre la gerencia y los trabajadores, con huelga incluida. | Desconfianza profunda entre los dos actores principales del sistema. |
| **1990** | Se abandona un **intento anterior** de sistema porque no superó las **pruebas de carga**. | Primera advertencia: el problema de la carga ya se conocía. |
| **1991** | Se escribe una **especificación nueva, más ambiciosa**, que además cambia la forma de trabajar. La escribe la **gerencia**. Las tripulaciones casi no participan y la especificación **nunca se firma formalmente**. | Los usuarios reales quedan afuera de la definición. |
| **1991** | Gana la **oferta más barata**: el software se cotiza en **£35.000**. Nadie pregunta cómo puede costar tan poco. Otros oferentes advierten los riesgos. | Se elige por precio un sistema crítico. |
| **1992** | Nadie calcula cómo va a impactar el sistema sobre la **red de radio**. Queda "para después". | El sistema depende de la radio para saber dónde está cada ambulancia. |
| **26/10/1992, 07:00** | **Puesta en marcha**: en toda Londres, en una sola etapa, abandonando el respaldo manual. | No hay vuelta atrás si algo sale mal. |
| **26-27/10/1992** | **Colapso operativo.** | — |
| **04/11/1992** | **Caída definitiva**: el sistema se bloquea por **pérdida de memoria**, falla la **conmutación al servidor de respaldo** (que nunca se había probado) y se **vuelve al papel**. | — |

> **Prueba de carga:** someter al sistema a un volumen de trabajo como el real (o mayor) para ver si lo soporta.
> **Conmutación al respaldo:** pasar automáticamente a un servidor de repuesto cuando el principal falla.
> **Pérdida de memoria** (*memory leak*): un programa que va reservando memoria y no la libera, hasta que se queda sin memoria y se cae.

**Pregunta que deja la línea de tiempo:** ¿en qué momento todavía se podía frenar o reducir el impacto?

Hay dos lecturas, y ninguna es "esperar al final":

- **1991.** Ahí se escribió una especificación nueva sobre la base de un intento que ya había fallado, y sin los usuarios. Es el punto más temprano donde se podía corregir el rumbo.
- **Antes de la puesta en marcha.** Con pruebas reales y un margen de tiempo, todavía se podía postergar.

## 3. 🔴 El día del lanzamiento: un sistema que generó su propia carga

Lo más instructivo del caso es **cómo** colapsó. La reconstrucción de abajo es ilustrativa: sigue el mecanismo documentado, no los minutos exactos.

| Hora (aprox.) | Qué pasa |
|---|---|
| 07:00 | Arranca el turno. Datos perfectos, todo funciona: es el **camino feliz**. |
| ~08:30 | Se empiezan a **perder mensajes de radio**. El sistema deja de saber dónde está cada ambulancia. |
| Mañana | Una tripulación sale en una ambulancia distinta de la asignada, que es una práctica común del trabajo diario. El sistema lo registra como **error**. |
| ~11:00 | Las ambulancias no llegan. La gente desesperada **vuelve a llamar**, y el sistema registra cada llamada repetida como un **incidente nuevo**: la misma emergencia termina con una, dos o tres ambulancias asignadas. |
| Mediodía | Las **excepciones sin atender generan nuevas excepciones**. La cola de mensajes crece y las pantallas de los operadores se vuelven ilegibles. |
| Tarde | Cada asignación tarda más y manda ambulancias **cada vez más lejos**. |
| ~17:30 | Sistema saturado: la cola de excepciones lo vuelve inmanejable. (La vuelta definitiva al papel llega recién el 04/11.) |

> **Camino feliz:** el recorrido de un proceso cuando todo sale como se espera, sin errores ni excepciones.
> **Excepción** (en este contexto): una situación que el sistema no sabe resolver solo y que deja pendiente para que la atienda un operador.

En el colapso, las llamadas llegaron a esperar cerca de **10 minutos** para ser atendidas.

Ahora el dato que da vuelta el caso. **La demanda de ese día fue apenas un 6 % mayor que el promedio**, sin contar las llamadas repetidas. Es un valor normal, dentro de lo esperable para 95 de cada 100 días. Ese día incluso se trasladaron menos pacientes que el promedio del mes.

**No colapsó por la demanda: generó su propia carga.** El mecanismo es un círculo vicioso:

```
            se pierde la señal de radio
                        │
                        ▼
      el sistema no sabe dónde están las ambulancias
                        │
                        ▼
     asigna mal / lejos ──► la ambulancia no llega
                        │
                        ▼
     la gente vuelve a llamar ──► incidente "nuevo" duplicado
                        │
                        ▼
     más excepciones sin atender ──► generan más excepciones
                        │
                        ▼
        más carga ──► más demora ──► (vuelve arriba)
```

La carga real del día casi no se movió. La carga **del sistema** se multiplicó porque cada falla producía trabajo nuevo.

## 4. 🔴 La causa raíz: requisitos para un mundo ideal

### 4.1 Lo que se diseñó vs. lo que el trabajo exigía

| Lo que se diseñó | ≠ | Lo que el trabajo real exigía |
|---|---|---|
| Un sistema que asigna ambulancias automáticamente a partir de información **precisa y actualizada**. | | Manejar **datos imperfectos**, excepciones, demoras de comunicación y **decisiones humanas bajo presión**. |

El diseño era impecable "en un mundo ideal", pero necesitaba una precisión de datos **casi del 100 %**. La gerencia definió el sistema que quería tener y **no lo validó con quienes hacían el trabajo**. Los operadores y las tripulaciones sabían cosas que el sistema nunca contempló. La salida de una ambulancia distinta de la asignada es el ejemplo más claro: en la sala de control era rutina, y para el sistema era un error.

### 4.2 No hubo una sola causa, pero sí un origen común

La lectura más aceptada del caso es que **ninguna falla, por sí sola, habría colapsado el sistema**. Las fallas se encadenaron:

```
 ┌───────────────┐   ┌───────────────┐   ┌───────────────┐   ┌───────────────┐   ┌───────────────┐
 │ Stakeholders  │──►│ Requisitos    │──►│ Solo el       │──►│ Especificación│──►│ Plazo, presu- │──► COLAPSO
 │ desalineados  │   │ desde la      │   │ "camino feliz"│   │ aceptada al   │   │ puesto y      │    26/10/1992
 │               │   │ gerencia      │   │               │   │ pie de la     │   │ alcance       │
 │               │   │               │   │               │   │ letra         │   │ inadecuados   │
 └───────────────┘   └───────────────┘   └───────────────┘   └───────────────┘   └───────────────┘
 └──────────────────────────────── ORIGEN COMÚN ──────────────────────────────────────┘
   una falla de conducción y validación del cambio, que se expresó en la INGENIERÍA DE REQUISITOS
```

1. **Stakeholders desalineados:** intereses en conflicto que nunca se alinearon. Se esperaba que el software resolviera un problema que era **organizacional**.
2. **Requisitos desde la gerencia**, no desde quienes iban a usar el sistema todos los días.
3. **El camino feliz:** una especificación pensada para la operación habitual en un mundo ideal.
4. **Aceptada al pie de la letra:** el proveedor no la cuestionó.
5. **Plazo, presupuesto y alcance inadecuados**, y un pase a producción con problemas conocidos.

### 4.3 Las preguntas que nadie hizo

¿Qué pasa si…

- …faltan datos?
- …la gente vuelve a llamar?
- …se pierde la señal de radio?
- …las fallas generan más carga?

Los problemas organizacionales (apuro, conflicto gremial, presupuesto) **explican** por qué nadie hizo esas preguntas. **No reemplazan la responsabilidad de hacerlas.** En ningún sistema puede pasar que nadie las haga, y menos en uno crítico.

### 4.4 La lección: validar no es transcribir

El título que mejor resume el caso: *el sistema hizo exactamente lo que le pidieron*. **Ese fue el problema.**

> **Validar requisitos no es anotar lo que dice el cliente y hacerlo tal cual: es cuestionarlo.** Es preguntarse "¿y si falla esto?", "¿y si pasa esto otro?". Validar incluye comprobar si el cambio **puede sostenerse en el trabajo cotidiano**.

> **Para el parcial, si te preguntan:** *¿Por qué fracasó LASCAD desde la Ingeniería de Requisitos?*
> Porque los requisitos se definieron para el proceso ideal que imaginaba la gerencia y no para el trabajo real de la sala de control: sin participación de operadores y tripulaciones, solo con el camino feliz y sin validar el comportamiento ante datos imperfectos. El proveedor aceptó la especificación sin cuestionarla, y el sistema se lanzó en una sola etapa, sin pruebas de carga reales ni plan de contingencia.

## 5. 🟡 ¿Falló "en un sentido técnico"? Fracaso sociotécnico

El informe oficial de la investigación (1993) concluyó que **el sistema no falló en un sentido técnico**. Hay buenos motivos para discutirlo:

- **La objeción:** si un sistema cumple su especificación y colapsa en un día de demanda normal, **la especificación es parte de la falla técnica**. La frase del informe separa artificialmente el software de sus requisitos.
- **El matiz que da la cátedra:** el informe se refiere a que el código hacía lo que se había definido. Si se lo testeaba contra la funcionalidad definida, funcionaba. **Lo que falló fue lo que se definió como solución.** A eso se sumó la falta de capacitación de los usuarios.
- **Y además hubo una falla técnica pura:** la caída final fue por pérdida de memoria y por un respaldo que nunca se había probado.

La síntesis que cierra la discusión: fue un **fracaso sociotécnico**.

> **Sociotécnico:** que combina causas sociales y organizacionales (gestión, capacitación, conflicto, decisiones gerenciales) con causas técnicas (software, infraestructura). No es solo un error de programación ni solo un error de gestión.

## 6. 🟡 ¿Quién tuvo la responsabilidad?

En clase se votó entre cuatro opciones: desarrolladores, gerencia, trabajadores (resistencia al cambio) o responsabilidad compartida. La mayoría eligió **la gerencia**, 7 personas eligieron **responsabilidad compartida** y 1 eligió a los desarrolladores. No hay respuesta única. Uno de los equipos cargó el peso principal sobre la gerencia; el otro propuso, apoyado en el informe, una lectura más fina: **la responsabilidad no se reparte en partes iguales, pero la tienen los dos lados.**

**La mayor responsabilidad es de la dirección del servicio:**

- Impuso un plazo que ya le habían advertido que era inviable.
- Decidió pasar a producción con problemas conocidos.
- Hizo el despliegue completo en una sola etapa (lo que se llama un lanzamiento *Big Bang*).
- No tenía plan de contingencia.
- Ya había fallado un intento previo y hubo advertencias en el camino que no se tomaron en cuenta.

> **Lanzamiento Big Bang:** poner en producción todo el sistema, para todos los usuarios, de una sola vez. Lo opuesto es el **despliegue escalonado** o por etapas.

**El proveedor también decidió:**

- Aceptó un contrato que no podía cumplir.
- Lo aceptó en un sistema donde había vidas en juego.
- Lo aceptó cuando otros oferentes ya habían advertido los riesgos.

**Aceptar un contrato imposible, con vidas en juego, también es una decisión con consecuencias éticas.** De ahí sale una pregunta incómoda que vale para cualquiera que desarrolle: si te dan requisitos mal hechos y un plazo imposible, y los programás sin decir nada, ¿sos parte del problema?

**El Estado y los entes reguladores.** En un servicio de emergencias, el Estado debería revisar que el sistema funcione antes de que opere sobre la población: no es lo mismo que un sistema de una empresa de juguetes. Los **entes reguladores son stakeholders** del sistema. Lo mismo vale para las consecuencias: al sistema se le atribuyeron muertes que después no se pudieron probar, y el director del servicio renunció tras las denuncias. Eso también incumbe a quien diseña el sistema.

**Sobre quién podía frenar el lanzamiento:** siempre hay alguien con poder de decisión. El punto es **qué evaluaciones hace esa persona al momento de decidir**. Un dicho viejo lo resume con ironía: *"el que sabe, sabe; y el que no, jefe"*. Lo que el jefe sí tiene que saber hacer es **analizar, escuchar y decidir** en función de las cuestiones críticas. Cuando la decisión se toma por presión externa, todo se complica.

### 6.1 Culpar al usuario

Cuando el sistema colapsó, la gerencia atribuyó la falla a un **"mal uso deliberado"** de las tripulaciones. La investigación no encontró pruebas de eso. Lo que probablemente veían como mal uso era la práctica habitual de salir en otra ambulancia, que el sistema registraba como error.

Hay un caso paralelo en el Reino Unido: **Horizon**, el sistema contable de las sucursales del correo británico. Durante años el correo dio por cierto lo que decía el sistema cuando marcaba faltantes de dinero, y culpó a los encargados. Hubo consecuencias judiciales para cientos de personas, incluso prisión. Después se probó que el sistema tenía errores.

> **En los dos casos se confió más en el sistema que en la gente que lo operaba.**

En LASCAD hubo además un componente político. Después del conflicto de 1989-90, la gerencia quiso usar el sistema para **disciplinar a los trabajadores**: el informe lo describe como un **"chaleco de fuerza"**. Un sistema pensado para imponer una forma de trabajo difícilmente contemple que la gente trabaja de otra manera, y difícilmente sea adoptado.

## 7. 🔴 Qué se debería haber hecho distinto

Las mejoras atacan las dos cosas: **cómo se define** el sistema y **cómo se introduce**.

| Acción | Qué implica |
|---|---|
| **1. Involucrar** | Entrevistar y **observar** a operadores y tripulaciones desde la elicitación, y validar con ellos los **escenarios excepcionales**, no solo el camino feliz. |
| **2. Verificar** | Pruebas de **carga**, de **duración** (períodos largos), de **integración**, de **recuperación** y con **datos imperfectos**, lo más parecido a la realidad, llevando el sistema a situaciones extremas. |
| **3. Transición gradual** | **Pilotos**, despliegue por etapas o por zonas y procedimientos manuales de **contingencia** ya practicados. |

### 7.1 Evidencia de que funciona, no ausencia de evidencia de que falla

Una frase clave del informe de 1993:

> En un sistema crítico **no basta con que no haya evidencia de que vaya a fallar**: hace falta **evidencia positiva de que va a funcionar**.

Parecen frases iguales y no lo son. "No tenemos pruebas de que vaya a fallar" puede significar simplemente que no se probó. "Tenemos pruebas de que funciona" significa que se recorrieron los caminos posibles, **incluidos los no felices**, y que el sistema se comportó bien en todos.

De ahí sale una propuesta concreta: definir **de antemano las condiciones de lanzamiento**, es decir, qué evidencia permite avanzar y qué obliga a postergar.

> **Para el parcial, si te preguntan:** *¿Qué diferencia hay entre "no hay evidencia de que vaya a fallar" y "hay evidencia de que va a funcionar"?*
> La primera es ausencia de pruebas y puede significar que no se probó nada. La segunda exige haber verificado el comportamiento del sistema en todos los caminos, incluidas las excepciones y los datos imperfectos. En un sistema crítico solo la segunda habilita el pase a producción.

### 7.2 Los RNF de un sistema crítico

El caso se conecta con la materia sobre todo por los **requisitos no funcionales**. Uno de los equipos propuso cuatro características que en un sistema crítico **no se negocian**:

| Característica | Qué significa |
|---|---|
| **Disponibilidad** | El sistema está disponible cuando se lo necesita. |
| **Tolerancia a fallos** | Si algo se rompe, el sistema sigue andando. |
| **Degradación elegante** | Si no puede con todo, hace al menos lo básico, y bien, en lugar de caerse entero. |
| **Seguridad operativa** | No pone en riesgo a nadie. |

La idea de fondo de esa propuesta: en sistemas críticos, los RNF son **condiciones de bloqueo**, no variables de ajuste frente a plazos o presiones comerciales. Si no se cumplen, el sistema no sale a producción: **se mueve la fecha, no el requisito**.

Cuando en clase se preguntó qué RNF habría que establecer para este sistema, salieron ideas como estas:

- pautas de tiempo de respuesta;
- disponibilidad las 24 horas;
- disponibilidad del 99 % soportando altas cargas, con la aclaración inmediata de que **habría que definir qué es "alta carga"**: un adjetivo sin valor no se puede medir;
- tiempo máximo de recuperación tras una falla;
- tiempo máximo de atención de una llamada.

Pasadas a la forma que la materia exige (objeto, atributo, valor y unidad, con el verbo **ser**), quedarían así. Los valores son de ejemplo.

```
El tiempo máximo de recuperación del sistema tras una falla es de 1 hora.
El tiempo máximo de atención de una llamada de emergencia es de 5 minutos.
La disponibilidad mínima del sistema es del 99 % del tiempo.
```

**Ojo con la redacción:** no mezclar *"máximo"* con *"al menos"*. "El tiempo **máximo** de recuperación es de **al menos** una hora" dice dos cosas opuestas: un techo y un piso. Si es un límite superior, va "máximo… es de X". Si es un mínimo, va "mínimo… es de X". Nunca las dos juntas.

> **Para el parcial, si te preguntan:** *Escribí un RNF para un sistema crítico como el despacho de ambulancias.*
> Por ejemplo, de disponibilidad: "La disponibilidad mínima del sistema es del 99 % del tiempo." Tiene objeto (sistema), atributo (disponibilidad mínima), valor (99) y unidad (% del tiempo), y restringe la funcionalidad de despachar ambulancias. En un sistema crítico, además, conviene tratarlo como condición para pasar a producción.

## 8. 🟢 Si pasara hoy

**La tecnología cambió; los riesgos de fondo, no.**

| Qué cambió | Qué no cambió |
|---|---|
| **GPS y conectividad móvil:** las ambulancias ya no necesitan informar su ubicación por radio. | La presión por los plazos y los costos. |
| **Despliegues graduales** en lugar de todo a la vez. | Las compras que priorizan el precio. |
| **Pruebas de carga automatizadas:** el volumen real se simula antes de salir. | La tentación de saltear pruebas. |
| **Ingeniería del caos:** inyectar fallas a propósito para ver cómo responde el sistema. | La creencia de que "el cliente sabe lo que necesita". |
| **ISO/IEC 25010:** la capacidad y la tolerancia a fallos son características que se especifican. | Las decisiones gerenciales y la necesidad de que participen los usuarios. |
| **Mayor visibilidad pública:** las redes sociales viralizan las fallas y presionan para corregirlas. | La incertidumbre de los datos del mundo real. |

> **ISO/IEC 25010:** norma internacional que define un modelo de características de calidad del software (por ejemplo, fiabilidad, eficiencia de desempeño, seguridad), útil como lista de qué atributos especificar.

**Hoy probablemente no colapsaría exactamente igual, pero fallaría por las mismas razones** si se ignoraran las personas y la gestión del riesgo.

Un caso reciente lo muestra. El 19/07/2024, la empresa de ciberseguridad **CrowdStrike** distribuyó una actualización defectuosa **a todos sus clientes a la vez**. Millones de equipos quedaron fuera de servicio, incluidos los de hospitales y servicios de emergencia. Su compromiso posterior fue hacer **despliegues escalonados**, que es lo mismo que en 1993 recomendaba el informe de LASCAD: introducir el sistema por etapas y consultando al personal.

**El mismo patrón aparece con los agentes de IA**, que se lanzan a producción por presión del mercado y de los costos, sin guardarraíles suficientes.

> **Agente de IA:** programa basado en IA que toma decisiones y ejecuta acciones por sí mismo, no solo responde preguntas.
> **Guardarraíles:** controles que limitan lo que un sistema automático puede hacer y frenan sus errores antes de que causen daño.

La cátedra trajo además un paralelo con un hecho reciente: un caso en que, tras fallar un sistema, falló también la respuesta humana, con víctimas. Ahí es donde los RNF (disponibilidad, criticidad, interfaces) muestran su función: **dar apoyo a la operación humana**. Para cualquier sistema crítico se propone este esquema:

```
  Tecnología  ───►  Persona  ───►  Acción
  apoya la          decide e        con contingencia
  decisión          interviene
      ▲                │
      └── puede frenar ┘
          al sistema
```

**Ningún sistema crítico debería operar de forma totalmente autónoma.** La tecnología apoya, la persona decide y puede frenarlo. Por eso, a la pregunta "¿confiarías hoy en un sistema que asigne ambulancias automáticamente?", hay que tener en cuenta que hoy **ni siquiera un viaje de Uber se asigna automáticamente de esa forma**, y un servicio de emergencias es muchísimo más crítico.

Estas medidas tienen **límites**. Requieren tiempo, recursos y responsables con autoridad, y sirven de poco si sus resultados no influyen en las decisiones.

## 9. 🟢 Hasta las fuentes hay que cuestionarlas

Uno de los estudios más usados sobre el caso (Greenwood y otros, 2010) compara el fracaso de 1992 con el sistema que sí funcionó después. Informa que **23 de 24 riesgos** se mitigaron total o parcialmente, **pero su conclusión habla de todos**. Además, es un análisis hecho "con el diario del lunes": en la recuperación cambiaron muchas cosas a la vez (participación de usuarios, prototipos, implementación por etapas). Por eso no se puede atribuir el éxito a una sola medida ni demostrar que aplicar un método habría garantizado otro resultado.

**La lección es coherente con todo el caso:** si se le critica al proveedor no haber cuestionado los requisitos del cliente, no se puede aceptar sin cuestionar un paper, ni siquiera el que da la razón.

---

# 🟡 CASO 2 — Virtual Case File del FBI (2000-2005)

## 10. 🟡 El dolor: información dispersa y agentes que no confiaban en el sistema

En los años 90, un agente del FBI investigó un caso enorme de desvío de millones de dólares que involucraba a la mafia rusa y a la mafia italiana. Juntó transacciones, entrevistas y una masa de datos que **el FBI no tenía dónde centralizar ni organizar**.

Lo que había era **ACS**, el sistema de expedientes de ese momento. En realidad eran varias aplicaciones integradas entre sí, **cada una con su propia base de datos**, y había **discrepancias** entre ellas. Encima, muchos agentes **ni siquiera cargaban** la información: preferían el expediente en papel porque lo creían más confidencial, para no exponer a sus testigos.

El proyecto **Trilogy** se pensó en tres etapas:

1. **Reemplazar las computadoras** de los agentes, que tenían sistemas operativos obsoletos. ✅ Salió bien.
2. **Mejorar las redes**, que eran muy lentas. ✅ Salió bien.
3. **El software: el Virtual Case File (VCF)**, que debía centralizar toda la información. ❌ Fracasó.

Para el VCF, el FBI contrató a la empresa **SAIC** (hoy se llama Leidos).

**El dolor era real y se entendía bien:** información dispersa, inconsistente y en parte fuera del sistema. No fue "contratemos a una empresa para que nos arregle la vida": venía de charlas previas sobre algo que no funcionaba. La organización tenía la esperanza legítima de resolver un problema concreto.

## 11. 🟡 Las cuatro causas

```
  CONTEXTO TECNOLÓGICO     ELICITACIÓN DE       PRESIONES          GESTIÓN Y
  Y EMPRESARIAL        ──► REQUISITOS      ──►  EXTERNAS      ──►  PLANIFICACIÓN
```

**1. Contexto tecnológico y empresarial.** Lo tecnológico estaba resuelto: las dos primeras etapas de Trilogy salieron bien. El problema era empresarial. El FBI **no tenía un proceso claro** de cómo los agentes obtenían y guardaban la información, y **cada agente trabajaba distinto**: unos con papel, otros con el sistema. No se les dio **confianza en la seguridad** del sistema nuevo ni se estableció un proceso concreto que después se pudiera llevar a tecnología y mejorar.

**2. Elicitación de requisitos.** Es el centro del caso y tiene sección propia (la 12).

**3. Presiones externas.** El proyecto arrancó en 2000. En 2001 ocurrió el atentado a las Torres Gemelas, y el gobierno y el Congreso quisieron el sistema operativo **ya**. En 2002, además de los ~170 millones de dólares iniciales, el Congreso aprobó **78 millones más para adelantar la entrega casi un año**, de 2004 a 2003, **con los mismos requisitos**.

**4. Gestión y planificación.** No hubo planificación de tiempos ni **hitos** con funcionalidades concretas. Por la conducción del proyecto del lado del FBI pasaron **tres responsables distintos** (el equipo lo ubicó en 2002). El primer responsable, que impulsó el VCF, tenía algunos conocimientos de IT (tecnología de la información), pero no le alcanzaron para sostener la comunicación con el proveedor.

## 12. 🔴 El documento de 800 páginas: cuando muchos requisitos no son buenos requisitos

Los ingenieros juntaron en muchas reuniones un **documento de requisitos de unas 800 páginas**. El problema no era la cantidad en sí. Era **qué contenía y cómo estaba gestionado**:

- **Mucho diseño e interfaz, poca funcionalidad.** El documento ponía **al mismo nivel** un requisito funcional y uno de diseño o de interfaz. Cuando los agentes empezaron a usar el sistema, descubrieron que **muchas funcionalidades esenciales de su trabajo diario no estaban**, o daban error. Primero hay que asegurar que el sistema haga lo que tiene que hacer (que busque como tiene que buscar); la interfaz viene después.
- **Riesgo de inconsistencia.** Con un volumen así, se pierde **consistencia y coherencia**. Si los requisitos no se vuelcan a una herramienta de **gestión de requerimientos**, es muy difícil evitar requisitos que se contradigan entre sí, aunque sean de interfaz o de disponibilidad. Eso probablemente también afectó la coordinación entre los equipos de desarrollo.
- **Más de 400 modificaciones sobre la marcha**, sin ninguna gestión del tipo "¿lo implementamos o no? ¿qué consecuencias trae?".

**El volumen solo no dice nada.** Los requisitos de un ERP para una línea aérea pueden llegar a 1.400 páginas, y está justificado porque incluye todos los procesos de la aerolínea, desde el despacho hasta el manejo de tripulaciones, que son muy complejos. El problema del VCF eran 800 páginas **sin foco en lo funcional y sin gestión**.

> **ERP** (*Enterprise Resource Planning*): sistema integrado que cubre los procesos centrales de una organización (compras, ventas, personal, operaciones).
> **Gestión de requerimientos** (o de cambios): proceso que registra cada requisito y cada pedido de cambio, evalúa su impacto y decide si se acepta.

**El dato que lo confirma:** en 2002, un integrante del equipo leyó el documento de requisitos, **sin haber escrito una sola línea de código**, y avisó a un superior que eso no llevaba a ningún lado. Nadie le hizo caso. El proyecto se canceló unos tres años después. **Un análisis crítico de los requisitos alcanzaba para anticipar la catástrofe.**

> **Para el parcial, si te preguntan:** *¿Qué falló en la elicitación del Virtual Case File?*
> Se produjo un documento enorme que mezclaba al mismo nivel requisitos funcionales con requisitos de diseño e interfaz, sin gestionar su consistencia ni los más de 400 cambios que entraron sobre la marcha. Por eso faltaron funcionalidades esenciales para el trabajo de los agentes, y además no se definió primero el proceso real de trabajo que el sistema debía soportar.

## 13. 🟡 Presión, contratos y equipos

**Adelantar la fecha no acelera el trabajo.** Un dicho que circula entre docentes: *una mujer hace un bebé en nueve meses, pero nueve mujeres no hacen un bebé en un mes.* Sumar dinero o gente para adelantar la entrega no reemplaza una planificación correcta.

**Equipos sin comunicación.** SAIC repartió el desarrollo en **ocho grupos de programadores** que casi no se comunicaban. Al momento de integrar, las partes no encajaban.

**Pago por hora, no por entrega.** El FBI le pagaba al proveedor **por hora de código**, no por funcionalidad entregada. Así se vuelve muy difícil medir si las horas aportan valor real al producto.

**El reparto de la culpa.** El análisis expuesto estimó así el peso de cada causa:

| Causa | Peso estimado |
|---|---|
| Establecer los requisitos | 40 % |
| Asesoramiento del proveedor (SAIC) | 25 % |
| Organización del FBI | 25 % |
| Condiciones de desarrollo e implementación | 10 % |

Lo del **asesoramiento** se conecta con la cursada. En la práctica por Zoom de negociación, quienes tenían que documentar y no sabían qué escribir **empezaban a preguntar e indagar**. Ese es el rol del proveedor: analizar, buscar ambigüedades y aclarar lo que no se entiende **antes** de pasárselo a los desarrolladores.

## 14. 🟡 Qué se haría distinto, y lo que efectivamente se hizo: Sentinel

**Como ingenieros de requisitos, la propuesta es:**

- **Reuniones de elicitación exhaustivas**, que aprovechen cada minuto de comunicación entre proveedor y cliente, usando **distintas técnicas** (incluidos cuestionarios y la participación de los agentes, que son quienes iban a usar el sistema).
- **Un modelo de desarrollo ágil**:
  - **Testeos por entrega**: el usuario prueba y aprende a usar el sistema en cada entrega.
  - **Gestión de nuevas funcionalidades**: un mecanismo para decidir si un cambio entra o no.
  - **Cobro por entrega**, no por hora.

> **Desarrollo en cascada:** se especifica todo primero, después se diseña, después se programa y al final se prueba, en etapas secuenciales.
> **Desarrollo ágil:** se construye en ciclos cortos, con entregas parciales que el usuario prueba y que permiten incorporar cambios de forma controlada.

**Lo que pasó en la realidad:** el VCF se canceló y el FBI encaró un proyecto nuevo, **Sentinel**, que arrancó en 2006 y se inauguró en 2012. Corrigió lo que Trilogy hizo mal:

| Trilogy (VCF) | Sentinel |
|---|---|
| Documentos extensos y poco consistentes. | Mayor atención a la **gestión de requisitos**, con personal a cargo de las reuniones de relevamiento. |
| Desarrollo en cascada, desbordado por las modificaciones. | Metodología ágil por fases, con **seguimiento de entregables**. |
| Plazos de alta exigencia impuestos desde afuera. | Plazos sujetos a cada etapa de desarrollo. |

Algunos datos de contexto:

- **Las ideas ágiles** se empiezan a concebir a mediados de los 90, y el **Manifiesto Ágil** es de 2001. Para un proyecto que arrancó en 2000, lo ágil era una idea incipiente, igual que el testing unitario. Hoy hay una madurez en ese tipo de prácticas que en esa época no existía.
- **En proyectos grandes y ambiciosos**, lo ágil se puede combinar con una estructura más amplia: se arman **módulos** que avanzan en etapas (en "cascadita" o en espiral), y cada módulo se desarrolla con metodología ágil adentro.

> **Manifiesto Ágil:** declaración de 2001 que fijó los valores y principios del desarrollo ágil.
> **Modelo en espiral:** desarrollo en vueltas sucesivas, cada una con su análisis de riesgo antes de avanzar.

## 15. 🟢 Datos que dimensionan el desastre

- Del VCF quedaron **unas 700.000 líneas de código**, de las que **solo un 10 % era reutilizable**. No sirvió ni como esqueleto para otro sistema.
- Sentinel funciona y sigue en uso. Según lo que encontró el equipo, en 2025 los documentos del caso **Epstein** salieron de Sentinel; la cátedra lo destacó como muestra de su valor en un caso muy grave.

**La conclusión del caso:** se puede tener todo el presupuesto, contratar especialistas y que lidere el proyecto un organismo como el FBI. Nada de eso **garantiza** el éxito. Una buena gestión, requisitos bien definidos y una metodología adecuada tampoco lo garantizan, pero hacen que la conducción sea manejable y que se cumplan los objetivos.

---

## 16. 🔴 Lo que los dos casos enseñan a la Ingeniería de Requisitos

| Lección | En LASCAD | En el VCF |
|---|---|---|
| **Modelar el trabajo real, no el ideal** | Se diseñó para datos perfectos y el camino feliz. | No se definió el proceso real de los agentes antes de pedir el sistema. |
| **Los usuarios clave participan desde la elicitación** | Las tripulaciones casi no participaron; la especificación la escribió la gerencia. | No queda claro que se haya consultado a los agentes. |
| **Los requisitos se cuestionan, no se transcriben** | El proveedor aceptó la especificación al pie de la letra. | 800 páginas sin foco funcional que nadie depuró; la advertencia de 2002 se ignoró. |
| **Calidad verificable (RNF con valor)** | No hubo pruebas de carga reales ni respaldo probado. | Faltaron funcionalidades esenciales y hubo errores al usarlo. |
| **Gestionar los cambios** | Especificación nunca firmada formalmente. | Más de 400 cambios sin gestión. |
| **Implementación gradual** | Big Bang, sin contingencia. | Desarrollo en cascada, sin entregas parciales probadas por los usuarios. |
| **Las presiones externas explican, no justifican** | Conflicto gremial, presupuesto mínimo. | Atentado de 2001, Congreso, fechas adelantadas. |

> **Para el parcial, si te preguntan:** *¿Qué tienen en común los fracasos de LASCAD y del Virtual Case File desde la Ingeniería de Requisitos?*
> En los dos casos los requisitos no representaban el trabajo real de los usuarios: en LASCAD por haberlos escrito la gerencia pensando en el camino feliz, y en el VCF por un documento enorme centrado en diseño e interfaz y sin gestión de cambios. A eso se sumaron presiones de plazo y una implementación sin etapas validadas con los usuarios: de una sola vez en LASCAD, en cascada en el VCF.

---

### Qué viene en la Parte 2

Cómo se expone un caso de investigación: qué se valoró, qué se corrigió y qué conviene preparar antes de exponer, con la logística de la próxima clase.

**FIN DE LA PARTE 1**
