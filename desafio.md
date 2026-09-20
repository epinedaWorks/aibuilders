# Desafío

## Reto

Haz que el dataset de Educación Formal 2024 sea **entendible**. Hoy son millones de filas con
códigos numéricos que solo alguien del área puede interpretar; tu trabajo es convertirlos en
información que cualquier persona pueda leer y consultar.

Flujo: datos codificados → tu solución con IA → información comprensible.

### Los tres componentes

La solución se construye con tres piezas que se conectan entre sí. Cada una depende de la anterior.

**1. Ingesta de datos**

Un proceso que lee los archivos del dataset y los **decodifica con el diccionario de variables**,
de modo que los valores queden en palabras y no en números. Debe dejar los datos listos para que el
dashboard y el agente los consuman.

Aquí es donde se define si tu análisis va a ser correcto: si la ingesta interpreta mal los datos,
todo lo que se muestre después estará mal.

**2. Dashboard con gráficas y análisis**

Una interfaz que presente los datos mediante **gráficas claras** acompañadas de **análisis
escrito**: no basta con mostrar la visualización, hay que explicar qué significa y qué se concluye
de ella.

El público objetivo es alguien **sin formación técnica ni estadística**. Las etiquetas deben ser
legibles y las cifras que afirmes tienen que corresponder con los datos reales.

**3. Agente que explique en lenguaje natural**

Un agente conversacional al que se le pueda preguntar y que responda en **lenguaje natural**, tanto
sobre **los datos** ("cuántos estudiantes de primaria hay en Alta Verapaz") como sobre **el análisis
que generó tu dashboard** ("por qué señalas ese nivel como el más crítico").

Debe apoyarse en la información ya procesada y **no inventar cifras**. Si le preguntan algo que el
dataset no permite responder, lo correcto es que lo diga.

### Mínimo esperado

- La ingesta procesa el dataset y entrega los valores decodificados.
- El dashboard muestra al menos una vista general y una desagregación (por ejemplo, por departamento
  y por nivel), cada una con su análisis escrito.
- El agente responde consultas sobre los datos y al menos una pregunta sobre el análisis del
  dashboard.

Usar IA está permitido y se espera: es parte del producto y también una herramienta de desarrollo
válida. Lo que se evalúa es cuánto **comprendes y puedes explicar** lo que construiste.

---

## Reglas

- **Equipos de 1 a 5 personas.** Puedes participar solo si así lo prefieres.
- **El proyecto se construye durante el hackatón.** No se vale presentar algo que ya tenías hecho.
- **Usar IA está permitido y se espera.** Documenta qué usaste y para qué. Lo que se evalúa es que
  comprendas lo que entregas.
- **Puedes usar librerías, frameworks y servicios de terceros** libremente.
- **El dataset entregado es la base.** Si sumas datos externos, que sean públicos y citados.
- **No inventes datos** ni cifras en tus análisis.
- **Sin credenciales ni llaves** en el repositorio.
- **Presentarse al pitch es obligatorio** para ser evaluado.
- **Respeto entre participantes** y con el equipo organizador.
- **Las decisiones del jurado son finales.**

Si tienes duda sobre si algo está permitido, pregunta a los organizadores antes de asumir.

---

## Sugerencias: desarrollo asistido con IA

Vas a usar IA para construir esto, y está bien. La diferencia entre un proyecto que sostienes y uno
que se te va de las manos está en **cómo** la usas: como asistente que ejecuta y valida lo que tú
diseñaste, no como alguien a quien le delegas el proyecto completo.

### Quién hace qué

La regla práctica: **el criterio es tuyo, la ejecución puede ser compartida.**

**Tú decides**

- Entender el problema y qué se quiere lograr.
- El análisis: qué preguntas responderán los datos.
- El diseño: qué componentes hay y cómo se conectan.
- Las decisiones técnicas y por qué se tomaron.
- Qué código entra al proyecto y qué se descarta.

**La IA asiste**

- Implementar lo que ya definiste.
- Explicarte lo que no entiendes de un lenguaje o librería.
- Revisar tu diseño y señalar huecos o riesgos.
- Validar resultados y ayudarte a encontrar errores.
- Proponer alternativas para que tú elijas.

### Un ciclo de trabajo que funciona

1. **Piensa antes de pedir.** Antes de escribir un solo prompt, ten claro qué vas a construir y por
   qué. Si le pides a la IA que resuelva algo que tú no has entendido, no vas a poder juzgar si lo
   hizo bien.
2. **Diseña tú, y deja que la IA critique.** Plantea tu diseño y pídele que lo cuestione: qué se te
   escapó, qué se puede simplificar, qué va a fallar cuando crezca. Usarla como revisor es mucho más
   valioso que usarla como generadora de arquitecturas que no elegiste.
3. **Pide en pedazos pequeños.** Una función, un módulo, un paso. "Hazme todo el proyecto" produce
   código que nadie revisó y que nadie puede explicar.
4. **Lee y entiende antes de integrar.** Si te entrega algo que no comprendes, pídele que te lo
   explique antes de pegarlo. Si sigue sin quedar claro, pide una versión más simple. Código que no
   entiendes es deuda que vas a pagar en la ronda de preguntas.
5. **Verifica contra la realidad.** La IA puede producir cifras convincentes y equivocadas. Contrasta
   lo que salga con los datos: usa las cifras de referencia de la sección Contenido como control.
6. **Documenta mientras avanzas.** Anota por qué tomaste cada decisión, en tus palabras. Es lo que te
   va a permitir explicar el proyecto después.

### Señales de que perdiste el control

- Hay archivos en tu proyecto que no sabes qué hacen.
- No puedes explicar por qué el código está organizado así.
- Tienes dependencias instaladas que no recuerdas haber elegido.
- Cuando algo falla, tu única estrategia es volver a pedirle a la IA que lo arregle.
- El proyecto funciona, pero no sabrías por dónde empezar a modificarlo.

**Cómo recuperarlo:** deja de agregar cosas. Recorre lo que ya tienes y pídele a la IA que te
explique cada parte hasta que puedas explicarla tú. Borra lo que no aporta. Un proyecto más pequeño
que dominas vale más que uno grande que no.

### Cambia la forma de pedir

| En vez de | Pide |
|---|---|
| "Hazme el dashboard" | "Necesito una gráfica de X por Y. Propón dos formas y dime ventajas de cada una" |
| "Arréglalo" | "Explícame por qué falla antes de proponer el arreglo" |
| "Dame el código" | "Dame el código y explícame qué hace cada parte y por qué así" |
| "¿Está bien mi proyecto?" | "Este es mi diseño: ¿qué problemas le ves y qué estoy asumiendo sin querer?" |

Nada de esto es para que uses menos IA, sino para que llegues al final **con el dominio de tu
proyecto**. Es exactamente lo que se evalúa con mayor peso.
