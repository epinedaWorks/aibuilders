# Hackaton · AI Builders GT — Resumen

Vas a tomar los datos públicos de la educación en Guatemala —millones de filas que hoy solo
un especialista puede leer— y construir, con apoyo de IA, una herramienta que los vuelva
comprensibles para cualquier persona.

| Dato | Valor |
|---|---|
| Registros | ~4.3 millones |
| Departamentos | 22 |
| Ciclo escolar | 2024 |
| Integrantes por equipo | 1 a 5 |

## Con qué vas a trabajar

El dataset **Educación Formal 2024**, publicado como dato abierto por el Instituto Nacional de
Estadística en https://datos.ine.gob.gt/dataset/educacion-formal-2024. Son **microdatos**: cada
fila es una inscripción de un estudiante durante el ciclo 2024.

Cada registro describe dónde y cómo estudia una persona —departamento, establecimiento, nivel y
grado, sector, área urbana o rural, sexo, pueblo de pertenencia, jornada— y cómo cerró el año.
No hay nombres ni identificadores: no es una encuesta, es el censo administrativo completo del
sistema educativo.

## La problemática

Los datos están publicados y son gratuitos, pero en la práctica casi nadie los aprovecha. La
barrera no es el acceso: es la interpretación. Tres razones concretas:

1. **Todo está en clave.** Los valores son códigos numéricos. El sector de una escuela aparece
   como `1`, no como "Público"; el resultado del año como `5`, no como "No promovido". Sin el
   diccionario al lado, una fila no comunica nada.
2. **El volumen abruma.** Más de cuatro millones de filas repartidas en decenas de archivos. No
   se abren cómodamente en una hoja de cálculo ni se pueden volcar completas a un modelo de IA.
3. **Nada viene calculado.** No existe una columna que se pueda sumar. Cualquier indicador
   —aprobación, deserción, repitencia— hay que construirlo a partir del conteo de registros.

El costo de esto es real: una autoridad municipal, un periodista o un docente no pueden abrir esa
tabla y sacar conclusiones sobre la educación de su territorio.

## Qué buscamos resolver

Que estos datos dejen de ser una tabla opaca y se conviertan en información que una persona sin
formación técnica pueda entender en minutos. Concretamente, que tu herramienta logre tres cosas:

- **Traducir:** que los códigos se lean como palabras y las cifras tengan contexto.
- **Explicar:** que no solo muestre gráficas, sino que diga qué significan y qué se concluye de ellas.
- **Responder:** que quien tenga una duda pueda preguntarla en lenguaje natural y obtener una
  respuesta basada en los datos reales.

Flujo: datos codificados → tu solución con IA → información comprensible.

## Cómo: los tres componentes

1. **Ingesta de datos.** Lee los archivos y los decodifica con el diccionario de variables,
   dejándolos listos para consumirse. Si esta pieza interpreta mal, todo lo demás sale mal.
2. **Dashboard con gráficas y análisis.** Visualizaciones claras acompañadas de análisis escrito,
   dirigidas a alguien sin formación estadística. Las cifras que afirmes deben cuadrar con los datos.
3. **Agente en lenguaje natural.** Responde preguntas sobre los datos y sobre el análisis que generó
   tu dashboard, sin inventar cifras y admitiendo cuando algo no se puede saber.

## Cómo se evalúa

Sobre 100 puntos. Usar IA no resta —es parte del producto y una herramienta de desarrollo válida—;
lo que más pesa es que comprendas y puedas explicar lo que construiste.

| Peso | Criterio |
|---:|---|
| 30 | Comprensión de tu solución |
| 20 | Calidad de arquitectura |
| 20 | Calidad de código |
| 15 | Cumplir el reto |
| 10 | Buenas prácticas |
| 5 | Reproducibilidad |

La evaluación incluye un **pitch**: un representante del equipo expone durante 5 minutos qué hizo
y cómo lo hizo, seguido de 5 minutos de preguntas de los jueces.

## Qué entregas

1. **Código:** un repositorio público, reproducible localmente, con instrucciones de uso y
   documentación formal de la arquitectura y las decisiones técnicas.
2. **Audiovisual:** dos videos de máximo 3 minutos cada uno, uno explicando la arquitectura del
   proyecto y otro mostrando su funcionamiento.

## Lo esencial de las reglas

- Equipos de **1 a 5 personas**; puedes participar solo.
- El proyecto se construye durante el hackatón.
- Usar IA está permitido y se espera: documenta qué usaste y para qué.
- El dataset entregado es la base; datos externos deben ser públicos y citados.
- Presentarse al pitch es obligatorio para ser evaluado.
