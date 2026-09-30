# 📗 COMPLEMENTO — Clase 07 · Repaso de RF y RNF, simulacro y quiz

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Unidad:** `clase07` · Complementa a `apunte-maestro-clase07-repaso-rf-rnf-y-simulacro-parte1` y `-parte2`
**Contenido:** respuestas de los checkpoints de las dos partes, en formato de examen. No hubo dudas de sesión que destilar.

---

## Parte B — Respuestas del checkpoint de la Parte 1

**1. ¿Qué es lo que se corrige en las entregas de RF y RNF, si no es la identificación?**
La redacción. Lo que se identifica como requisito sí lo es; lo que se optimiza es la forma, para que el requisito sea medible y tenga una sola interpretación.

**2. ¿Qué tres cosas hay que identificar en la sintaxis de un RNF para poder medirlo?**
El valor, el atributo al que pertenece ese valor, y el objeto al que pertenece ese atributo. Con eso se puede definir cómo medir y determinar si la restricción se cumplió.

**3. ¿Por qué "el sistema debe estar disponible" no se puede verificar, y cómo verifica el equipo de operaciones una disponibilidad del 99,9%?**
Porque no dice qué se mide: queda tácito, y admite distintas interpretaciones sobre cómo validarlo. Con "99,9% del tiempo en horario laboral", operaciones verifica el valor con el registro de caídas del sistema, y ante cada caída hace un análisis de causa y efecto.

**4. ¿Qué dos problemas de redacción tenía "cantidad de copias garantizadas por impresora" y cuál fue la consecuencia?**
El verbo "garantizar" en voz pasiva, sin decir quién garantiza (¿la impresora o el comprador?), y un cambio de preposición ("por" / "para") en el mismo pliego que habilitaba las dos lecturas. El requisito quedó incompleto y ambiguo, cada parte lo interpretó distinto, y hubo que reescribir todo lo que se basó en ese supuesto.

**5. ¿Por qué el tiempo de aprendizaje se define para el 80% del personal y no para todos?**
Porque siempre puede haber usuarios a los que les cueste más aprender, y un requisito que exige que todos lo logren no es realista. El 80% es la métrica mínima; si no se alcanza, hay que revisar pantallas, tipografía, interfaz o capacitación.

**6. ¿Qué diferencia hay entre un RNF transversal y un RNF de una función? Dá un ejemplo de cada uno.**
El transversal restringe a todo el sistema sin importar qué función se ejecute (compatibilidad con el sistema operativo, normativa de datos personales, doble factor de autenticación). El de una función restringe un caso de uso concreto y se cumple dentro de su escenario (el tiempo máximo de confirmación del registro de asistencia es de 2 segundos).

**7. ¿Por qué "interactuar" no es una función? ¿Cómo se reescribe el requisito de las formas de interacción?**
Porque no tiene un objetivo ni un escenario definible: interactuar es cómo se logra el cometido (comprar un pasaje, cargar una tarjeta), no el cometido. Se reescribe como RNF sobre los componentes, sin el actor como sujeto: "Los dispositivos de interfaz de la máquina con el pasajero son un teclado táctil y una interfaz interactiva de voz".

**8. En el requisito de la pantalla de 42 pulgadas, ¿qué se mide, qué sobra, y qué otro parámetro se estaba mezclando?**
Se miden las 42 pulgadas (eventualmente como rango o como área visible). Sobra el "para mejorar la experiencia de usuarios con movilidad reducida", que es justificación. Se mezclaba la altura de montaje de la pantalla, que es el parámetro que sí afecta a la movilidad reducida y es otro RNF.

**9. ¿Por qué "cuando el pasajero activa el comando de desplazamiento" no va en el RNF?**
Porque es una acción del actor que dispara algo, y eso pertenece al escenario del RF "Ajustar altura de pantalla". En el RNF el actor desaparece y solo va lo que se mide: "Los controles y botones se ubican en la mitad inferior de la pantalla, en modo de baja altura".

**10. ¿Cómo se redacta que el sistema tenga una cámara?**
Como un componente con una característica de calidad verificable, no como función: "La definición mínima de la cámara es de N megapíxeles". En contexto académico el valor se puede inventar; en uno laboral se releva.

## Parte B — Respuestas del checkpoint de la Parte 2

**1. ¿Por qué la mascota no es actor del ParkingDog? ¿Y por qué la cucha tampoco?**
La mascota parece interactuar (come, toma agua) pero no tiene ningún objetivo frente al sistema: el objetivo es del dueño que la deja. La cucha es parte del sistema: un sistema es un conjunto de elementos interrelacionados con un objetivo común, y el PD es uno de esos elementos, con sus componentes adentro.

**2. ¿Cuáles son los dos actores identificados en el simulacro?**
El dueño de la mascota y, eventualmente, el técnico de mantenimiento, que aparece más adelante en la descripción con su tarjeta de mantenimiento.

**3. "Tener un sensor de comida" no es un RF. ¿Cuál es la función del dueño, y qué lugar ocupa el sensor?**
La función del dueño es saber si la mascota tiene comida y agua y cuánto consumió, dispensarle más, o conocer su estado. El sensor (o la balanza) es el cómo se logra: es el elemento del sistema que se especifica como RNF.

**4. ¿Qué tiene un sistema de tiempo real que no tiene una consulta en línea? Dá el ejemplo del termostato y el de la cámara.**
Tiene un sensor que mide, un actuador que actúa en función de lo medido, y criticidad. El termostato mide la temperatura y calienta o enfría para mantener el rango de 22 a 25 grados: tiempo real. Ver a la mascota por la cámara es entrar y mirar, sin que nada actúe porque la mascota se movió: en línea.

**5. ¿Por qué "el dueño monitorea a la mascota en tiempo real" está mal escrito?**
Porque no es tiempo real: nada reacciona a lo que hace la mascota; el dueño entra a la app y ve la cámara en línea. Además "tiempo real" no se puede verificar; lo que corresponde es un tiempo máximo de retardo con unidad.

**6. Alumno y docente comparten las interacciones de usuario: ¿qué relación se usa y cuáles no aplican entre actores?**
Herencia: alumno y docente heredan de usuario, que es quien tiene el caso de uso compartido. Inclusión y extensión no aplican porque son relaciones entre casos de uso, nunca entre actores.

**7. ¿Qué hace el ingeniero de requisitos ante dos stakeholders con pedidos incompatibles, y quién decide?**
Detecta y documenta el conflicto, entiende la justificación de cada pedido, y media o negocia para llegar a un acuerdo, por ejemplo con valores intermedios. Decide quien paga la solución: el cliente puede imponer su requisito o admitir negociar otros valores.

**8. ¿Por qué "se acordó" en una minuta es un problema? ¿Cómo se escribe?**
Porque el "se" impersonal oculta quién avaló la decisión, y después no se sabe a quién reclamarle si el acuerdo no se cumple. Se escribe con el responsable explícito: "La junta directiva acordó que los profesores no toman más asistencia".

**9. ¿Un requisito verificable es necesariamente completo? Dá el contraejemplo.**
No: son propiedades independientes. "El inicio de sesión es con credenciales" se puede probar, pero no dice qué credenciales ni quién las crea; es verificable e incompleto a la vez.

**10. "Comprar producto" incluye "Aplicar descuento", solo para algunos clientes. ¿Qué está mal?**
La relación. La inclusión es comportamiento que se ejecuta siempre dentro del flujo; un comportamiento que ocurre solo bajo condición (tener descuento) se modela con extensión: "Aplicar descuento" extiende a "Comprar producto".

**11. ¿Cómo es el parcial del 01/10, qué se evalúa, y qué sale al final?**
Es un role-playing de entrevista, grupal, presencial en Campus a las 19:00, con un enunciado de contexto y una mini rúbrica entregados una semana antes; puede tocar el rol de entrevistador o de cliente. Se evalúan las habilidades del entorno de la entrevista: escuchar, adaptar la entrevista sobre la marcha, chequear cada requisito, manejar el tiempo. Al final sale la minuta.

---

**FIN DEL COMPLEMENTO — Clase 07**
