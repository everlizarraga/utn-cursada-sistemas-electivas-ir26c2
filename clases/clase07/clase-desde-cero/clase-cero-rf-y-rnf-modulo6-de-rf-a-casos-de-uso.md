# Clase desde cero — RF y RNF — Módulo 6: De los RF a los casos de uso

**Materia:** Ingeniería de Requisitos (IR) · UTN FRBA · 2C 2026
**Eje:** Centro de Entrenamiento Vida Sana
**Marcas:** 🔴 central · 🟡 secundario · 🟢 al pasar · 🕳️ madriguera · ✏️ tu turno

---

## Sobre este documento

**Qué cubre:** la relación entre los tres tipos de sentencia y el diagrama de casos de uso: el RF de nivel alto es el nombre del caso de uso · el RNF no se dibuja pero restringe el escenario (y a veces genera casos de uso derivados) · la regla de negocio es precondición o condición de un flujo · cómo se agrupan los RF detallados en casos de uso (café con leche) · las relaciones (inclusión, extensión, generalización) aplicadas al gimnasio · la herencia entre actores · el diagrama completo de Vida Sana, con cada decisión justificada.

**Qué NO cubre:** la notación UML desde cero ni la plantilla de escenario. Eso se asume de las primeras clases de la materia.

## De dónde venís

De la consolidación del M5: 29 RF, 19 reglas, 15 RNF, 27 preguntas. Y de las primeras clases: qué es un caso de uso, actores primarios y secundarios, inclusión, extensión, generalización, el actor Tiempo, y que un caso de uso no es un proceso.

---

## 1. 🔴 El puente: qué se dibuja y qué no

Tenés tres listas. Solo una se dibuja.

```
   RF (nivel alto: verbo infinitivo + objeto)  ──→  NOMBRE del caso de uso   ✅ se dibuja
   RF (nivel detallado: rol + verbo + objeto)  ──→  ACTOR + escenario        ✅ actor se dibuja,
                                                                                 escenario se escribe
   RNF                                         ──→  restricción del escenario ❌ no se dibuja
                                                    (a veces genera CU derivados)
   Regla de negocio                            ──→  precondición / condición  ❌ no se dibuja
                                                    de un flujo
```

### 1.1 El RF de nivel alto es el caso de uso

En M2 §3 viste que "Registrar socio" (verbo en infinitivo + objeto) era el nivel alto de "El profesor registra un socio con su DNI…". Ese nivel alto **es el nombre del caso de uso**. Y el nivel detallado te da lo demás: el **rol** es el actor que se conecta con la elipse, y el verbo + objeto + datos son el escenario.

```
   RF-04  El socio se anota en una clase.
           │                │
           ▼                ▼
        [Socio] ────── ( Anotarse en clase )
        actor           caso de uso
```

Por eso importaba tanto el actor como sujeto: **sin actor en el RF no sabés a quién conectar la elipse**. "El sistema debe controlar la capacidad" no dibuja nada.

### 1.2 El RNF no se dibuja, restringe

El RNF no es una función: es una condición sobre cómo se ejecuta una función. Cuando escribas el escenario de "Anotarse en clase", ahí adentro vas a tener que asegurarte de que la confirmación tarde menos de 2 segundos (si existe ese RNF). El diagrama no lo muestra; el escenario lo cumple.

**Con una excepción que ya conocés de las primeras clases:** un RNF puede **generar** casos de uso derivados cuando, para que la condición sea verificable, el sistema necesita funciones que nadie pidió. En el gimnasio, RNF-13 (cada registro conserva usuario, fecha y hora) necesita que el sistema tome la fecha y hora: eso es un caso de uso con el actor Tiempo, incluido en cada registro. Se dibujan las funciones derivadas, nunca la condición.

### 1.3 La regla de negocio es precondición o condición

RN-14 (el plan vence al mes) no se dibuja. Aparece como **precondición** de "Anotarse en clase": *el socio tiene un plan vigente con clases disponibles*. RN-12 (menos de tres, no se dicta) aparece como **condición** que dispara "Cancelar clase" o la extensión de ofrecer otro turno. Y recordá la frontera: lo previo y separado es precondición, no relación de inclusión.

> **Para el parcial, si te preguntan:** *¿Cómo se relacionan los RF, los RNF y las reglas de negocio con el diagrama de casos de uso?*
> El RF a nivel alto (verbo en infinitivo + objeto) es el nombre del caso de uso, y el rol del RF detallado es el actor que se conecta con él. El RNF no se modela como caso de uso porque es una restricción, no una función; se cumple dentro del escenario, aunque puede generar casos de uso derivados cuando la condición necesita funciones para ser verificable. La regla de negocio tampoco se dibuja: aparece como precondición o como condición de un flujo del escenario.

## 2. 🔴 Agrupar: de 29 RF a los casos de uso

Veintinueve RF detallados no son veintinueve casos de uso. Varios comparten el mismo nivel alto, y otros son variantes de una misma función. La regla para agrupar es la del café con leche: **arrancás granular, con un caso de uso por RF, y unís después** lo que resulte ser la misma función. Nunca al revés: si arrancás con "Gestionar clases" como un caso de uso gigante, no lo vas a poder partir bien.

Agrupamos:

| RF | Nivel alto (caso de uso) | Actor | Decisión |
|---|---|---|---|
| RF-27 | Registrar socio | Socio (o Profesor, según P-17) | Uno solo; el rol se decide con el cliente |
| RF-11, RF-12 | Contratar plan | Socio | El pago **siempre** forma parte de contratar (RN-15): "Pagar plan" se incluye |
| RF-13, RF-23 | Consultar plan | Socio | Plan y presentes eran la misma ficha: una consulta |
| RF-28 | Consultar clases disponibles | Socio | Derivado; previo a anotarse, pero **separado**: no es inclusión, es lo que hacés antes |
| RF-04 | Anotarse en clase | Socio | |
| RF-06 | Anotarse en lista de espera | Socio | Sale de anotarse cuando la clase está completa: **extensión** de Anotarse en clase, bajo condición |
| RF-05 | Darse de baja de clase | Socio | |
| RF-14 | Informar ausencia | Socio | Distinto de darse de baja (M4 §1): otro caso de uso |
| RF-15 | Recuperar clase | Socio | |
| RF-07, RF-08, RF-25 | Tomar lugar liberado | Socio | Recibir el ofrecimiento, aceptarlo o solicitarlo por iniciativa propia: distintas formas de lograr lo mismo → candidato a **generalización**, ver §3.3 |
| RF-17 | Recibir aviso de cancelación | Socio | El complemento de Cancelar clase: el anotado se entera |
| RF-09 | Ofrecer otro turno | Socio | Sale de Cancelar clase cuando hay anotados (RN-12): **extensión**, ver §3.2; no es generalización con el aviso de cancelación, ver §3.3 |
| RF-01 | Reservar turno en sector | Socio | |
| RF-02, RF-03 | Registrar uso de sector | Socio | Ingreso y salida como un caso de uso con dos momentos, o dos casos; ver §3.4 |
| RF-18, RF-19 | Registrar asistencia a clase | Profesor o Socio (P-17) | Un caso de uso; el actor lo decide el cliente |
| RF-10, RF-24 | Consultar clase | Profesor | Inscriptos, lista de espera y planilla: una consulta con distintas vistas |
| RF-16 | Cancelar clase | Profesor | |
| RF-20, RF-21 | Consultar ficha de socio | Profesor, Junta | Dos actores, un caso de uso |
| RF-22 | Consultar caja diaria | Junta | |
| RF-26 | Consultar cupo completo por profesor | Junta | |
| RF-29 | Registrar clase | Junta | |

De 29 RF quedaron **20 casos de uso** (más los derivados de las relaciones: Pagar plan, Tomar fecha y hora y las dos especializaciones de Tomar lugar liberado). Ninguno se llama "gestionar", ninguno tiene "el sistema", ninguno mezcla dos verbos.

## 3. 🔴 Las relaciones, aplicadas

Tres relaciones y dos fronteras. Acá van las que el gimnasio justifica; el resto, no se fuerza.

### 3.1 Inclusión: lo que se hace siempre, adentro

**Pagar plan** dentro de **Contratar plan**: por RN-15, no se contrata sin pagar seña o totalidad. Siempre. Es inclusión.

**Tomar fecha y hora** (actor Tiempo) dentro de **Registrar asistencia a clase** y **Registrar uso de sector**: por RNF-13, todo registro conserva fecha y hora. Siempre. Es inclusión, y es el caso de uso derivado de un RNF de §1.2.

```
   ( Contratar plan ) ─── inc ──▶ ( Pagar plan )
   ( Registrar asistencia a clase ) ─── inc ──▶ ( Tomar fecha y hora ) ─── [Tiempo]
   ( Registrar uso de sector )      ─── inc ──▶ ( Tomar fecha y hora )
```

Lo que **no** es inclusión: Consultar clases disponibles antes de Anotarse. Es previo y separado: el socio puede consultar y no anotarse, o anotarse sabiendo ya la clase. Precondición, no relación.

### 3.2 Extensión: lo excepcional, bajo condición

**Anotarse en lista de espera** extiende **Anotarse en clase** bajo la condición "la clase está completa" (RN-10). No siempre pasa; solo cuando el cupo (RN-01 a RN-04) está lleno.

**Ofrecer otro turno** extiende **Cancelar clase** bajo la condición "hay socios anotados" (RN-12: a los anotados se les ofrece otro turno).

```
   ( Anotarse en lista de espera ) ─── ext ──▶ ( Anotarse en clase )
                                     [clase completa]
   ( Ofrecer otro turno ) ─── ext ──▶ ( Cancelar clase )
                             [hay socios anotados]
```

Y una que es tentadora y **no** va: "Verificar plan vigente" como extensión de Anotarse. Que el socio tenga plan vigente (RN-14) es **precondición**: si no la tiene, el caso de uso no arranca. La extensión es para lo que pasa **durante** el flujo, bajo condición; la precondición es lo que tiene que ser cierto **antes**.

### 3.3 Generalización: distintas formas de lograr lo mismo

**Tomar lugar liberado** tiene dos formas: el socio lo acepta cuando le llega el ofrecimiento (RF-07 + RF-08), o lo solicita por iniciativa propia al ver el lugar libre (RF-25). Mismo objetivo, distinta forma de llegar, excluyentes en cada ejecución. Es generalización: el general es abstracto (no tiene escenario propio), y los dos especializados sí.

```
                 ( Tomar lugar liberado )   ← abstracto
                     ▲            ▲
                     │            │
   ( Aceptar ofrecimiento )   ( Solicitar lugar libre )
```

**Ojo:** esto depende de P-25 (si conviven las dos formas, o si la Junta elige una). Si elige una, no hay generalización: un solo caso de uso. La relación **se justifica con el negocio**, no con la ganas de dibujar un triángulo.

Lo que **no** es generalización: "Recibir aviso de cancelación" (RF-17) y "Ofrecer otro turno" (RF-09). Los dos le llegan al socio por la misma causa (una clase que no se dicta), pero no son dos formas de lograr **lo mismo**: uno informa, el otro ofrece una alternativa que el socio acepta o no. Van como dos casos de uso distintos, y el segundo como extensión de Cancelar clase (§3.2). Si en el escenario el tratamiento fuera idéntico y solo cambiara el texto, podrían unirse en uno; lo que no es defendible es dibujarlos como generalización.

### 3.4 Un caso de uso no es un proceso

Ingreso y salida de un sector (RF-02, RF-03): ¿un caso de uso o dos? Si el socio se identifica al entrar y al salir con el mismo gesto (pasa la credencial), es un solo caso de uso, "Registrar uso de sector", con dos momentos en el escenario. Si son dos acciones con distinto disparo y distinto resultado, son dos. Lo que no podés hacer es dibujar "Ingresar → Usar → Salir" encadenados con flechas: eso es un proceso, y el diagrama de casos de uso no muestra secuencia.

## 4. 🔴 Actores: primarios, secundarios y herencia

**Primarios** (a la izquierda, trazo lleno): Socio, Profesor, Junta Directiva. Los tres tienen objetivos propios.

**Secundarios** (a la derecha, punteado): **Tiempo**, que entrega fecha y hora cuando el sistema la consulta (Tomar fecha y hora). Y, si el pago es en línea con plataforma externa (RNF-05), la **Plataforma de pago** como sistema externo, conectada a Pagar plan.

**¿Herencia entre actores?** Se usa cuando dos actores comparten exactamente las mismas interacciones con algún caso de uso. En el gimnasio, Profesor y Junta comparten **Consultar ficha de socio**. ¿Justifica un actor general? Solo si existe un concepto del negocio que los agrupe: no lo hay ("personal del centro" no aparece en el enunciado, y la Junta no es personal). Con un solo caso de uso compartido, la solución simple es conectar los dos actores a la misma elipse. Si en la entrevista apareciera "Iniciar sesión" para los tres, ahí sí conviene un actor general **Usuario** del que heredan Socio, Profesor y Junta, porque ese sí es un concepto real (todos son usuarios del sistema).

**Lo que nunca va:** inclusión o extensión **entre actores**. Un actor no incluye a otro. Esas dos relaciones son entre casos de uso; entre actores solo existe la herencia. Es uno de los errores más frecuentes de parcial.

> **Para el parcial, si te preguntan:** *Alumno y docente comparten las interacciones definidas para Usuario. ¿Cómo se modela?*
> Alumno y docente heredan de Usuario: se dibuja la generalización entre actores, con Usuario conectado al caso de uso compartido (por ejemplo, Iniciar sesión). Inclusión y extensión no aplican: son relaciones entre casos de uso, nunca entre actores.

## 5. 🔴 El diagrama de Vida Sana

En texto, con la misma información que llevaría el dibujo. Actores a la izquierda (primarios) y a la derecha (secundarios); el sistema es el rectángulo.

```
                    ┌──────────────────── Sistema Vida Sana ────────────────────┐
                    │                                                            │
   [Socio] ─────────┼─ ( Registrar socio )                                       │
          ─────────┼─ ( Contratar plan ) ── inc ─▶ ( Pagar plan ) ──────────────┼──· · · [Plataforma
          ─────────┼─ ( Consultar plan )                                         │          de pago]
          ─────────┼─ ( Consultar clases disponibles )                           │
          ─────────┼─ ( Anotarse en clase ) ◀── ext ── ( Anotarse en lista       │
          ─────────┼─ ( Darse de baja de clase )        de espera )              │
          ─────────┼─ ( Informar ausencia )             [clase completa]         │
          ─────────┼─ ( Recuperar clase )                                        │
          ─────────┼─ ( Tomar lugar liberado )  ← abstracto                      │
          ─────────┼─      ▲ ( Aceptar ofrecimiento )                            │
          ─────────┼─      ▲ ( Solicitar lugar libre )                           │
          ─────────┼─ ( Recibir aviso de cancelación )                           │
          ─────────┼─ ( Reservar turno en sector )                               │
          ─────────┼─ ( Registrar uso de sector ) ── inc ─▶ ( Tomar fecha        │
                    │                                          y hora ) ──────────┼──· · · [Tiempo]
   [Profesor] ──────┼─ ( Registrar asistencia a clase ) ── inc ─▶ (Tomar fecha y hora)
             ──────┼─ ( Consultar clase )                                        │
             ──────┼─ ( Cancelar clase ) ◀── ext ── ( Ofrecer otro turno )       │
             ──────┼─ ( Consultar ficha de socio ) ◀─────┐   [hay anotados]      │
                    │                                    │                        │
   [Junta        ───┼─────────────────────────────────────┘                       │
    Directiva]   ───┼─ ( Consultar caja diaria )                                  │
                 ───┼─ ( Consultar cupo completo por profesor )                   │
                 ───┼─ ( Registrar clase )                                        │
                    └────────────────────────────────────────────────────────────┘
```

**Decisiones que hay que poder justificar cuando te pregunten** (todas salen de M5):

1. *Registrar socio* y *Registrar asistencia a clase* tienen el actor a confirmar (P-17, P-22). En el diagrama de entrega se elige uno y se aclara la decisión.
2. *Pagar plan* incluido en *Contratar plan* por RN-15. Si además el socio pudiera pagar un saldo fuera de la contratación (RN-18: "saldo"), Pagar plan también se conecta directo con el Socio. Es P-09 / P-11.
3. *Anotarse en lista de espera* como extensión, no como caso de uso suelto, porque solo existe cuando la clase está completa (RN-10).
4. *Tomar lugar liberado* generalizado, condicionado a P-25.
5. *Consultar clases disponibles* separado de *Anotarse*, no incluido: es previo y opcional.
6. *Tomar fecha y hora* con el actor Tiempo, derivado de RNF-13. Se relaciona solo con los casos de uso que efectivamente lo consultan (los dos registros), no con "todo lo que tenga que ver con tiempo".
7. No hay actor "Sistema", ni "Lector de credencial", ni "App": son componentes (M1 §3.3).
8. El vencimiento del plan **no está dibujado**: no está en el enunciado. Si se agrega el aviso de vencimiento, va como caso de uso "Avisar vencimiento de plan" con el actor Tiempo (o un subsistema notificador, que es la otra forma aceptada de modelar un disparo sin humano; las dos son válidas si están justificadas).

⚠️ **Sobre la notación:** el dibujo de arriba es esquemático. En la entrega y en el parcial, la notación UML se corrige estrictamente: elipses para los casos de uso, monigote para los actores humanos, rectángulo del sistema con nombre, línea llena para asociación, punteada con «include» / «extend» y la punta hacia el incluido / hacia el base, triángulo hueco para la generalización. Una inclusión dibujada al revés es un error de parcial aunque el análisis esté bien.

## 6. 🟡 Lo que el diagrama no puede mostrar

Tres cosas quedan **fuera del dibujo y adentro de la entrega**:

- **Los RNF**, en su lista, cada uno trazado al RF que restringe (M5 C.1). Son criterios de aceptación de los escenarios.
- **Las reglas de negocio**, en su lista, y referenciadas como precondiciones y condiciones en la plantilla de cada escenario.
- **Las preguntas abiertas** (P-01 a P-27) y **el conflicto** (RN-16 vs. RN-16'): un diagrama que elige por su cuenta es un diagrama que se va a rehacer.

Un diagrama de casos de uso sin esas tres listas al lado está incompleto, aunque esté perfecto.

---

## ✏️ Tu turno

1. Escribí la plantilla mínima (actor, precondición, poscondición, flujo principal en 4-6 pasos) del caso de uso **Anotarse en clase**, indicando en qué paso se aplica cada regla (RN-01 a RN-04, RN-10, RN-14) y qué RNF restringe el flujo.
2. Decidí P-17 vos (quién registra la asistencia a clase) y redibujá solo esa parte del diagrama con tu decisión, con una línea de justificación.
3. Encontrá en el diagrama un caso de uso que **no tenga ningún RNF asociado** en la lista de M5 y escribile uno.

## ✅ Checkpoint

1. ¿Qué parte del RF se convierte en el nombre del caso de uso, y qué parte en el actor?
2. ¿Por qué un RNF no se dibuja? ¿Cuándo, igual, genera casos de uso?
3. ¿Dónde aparece una regla de negocio en el modelo de casos de uso?
4. ¿Qué es la regla del café con leche aplicada a agrupar RF en casos de uso?
5. ¿Por qué "Consultar clases disponibles" no está incluido en "Anotarse en clase"?
6. ¿Por qué "Anotarse en lista de espera" es una extensión y no un caso de uso independiente?
7. ¿Por qué "Verificar plan vigente" no es una extensión de Anotarse?
8. ¿Cuándo dos casos de uso con el mismo verbo son generalización y cuándo no?
9. ¿Puede un actor incluir a otro actor? ¿Qué relación sí existe entre actores y cuándo se usa?
10. ¿Qué tres cosas acompañan al diagrama en una entrega, y por qué no puede ir solo?

## Qué viene después

Se terminó la clase desde cero. Lo que sigue es tu prueba de fuego: el apunte maestro de la clase 07 y la profundización sobre ParkingDog, un negocio nuevo, con el mismo método de M5 aplicado desde el primer párrafo. Si al leer esos archivos cada decisión te parece obvia, la clase cumplió su objetivo.

**FIN DEL MÓDULO 6**
