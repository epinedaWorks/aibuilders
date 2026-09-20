# Contenido — Dataset Educación Formal 2024

## Información

Vas a trabajar con el dataset **Educación Formal 2024**: el registro de todas las inscripciones
del sistema educativo guatemalteco durante ese ciclo escolar.

- Registros: ~4.3 millones
- Departamentos: 22
- Columnas: 15
- Ciclo escolar: 2024

### De dónde vienen

Los datos provienen de los **registros administrativos del sistema educativo**: cada año, los
establecimientos del país reportan al Ministerio de Educación quién se inscribió, en qué nivel y
grado, y cómo terminó el ciclo. Esa información se consolida y se publica como dato abierto.

Fuente oficial: portal de datos abiertos del **Instituto Nacional de Estadística (INE)**,
https://datos.ine.gob.gt/dataset/educacion-formal-2024

### Qué son exactamente

Son **microdatos**: en lugar de entregar totales ya calculados, se entrega el detalle fila por
fila. **Cada fila representa una inscripción**, es decir, un estudiante matriculado en un
establecimiento durante 2024.

Cada fila no dice quién es la persona —no hay nombres ni identificadores— sino **cómo y dónde
estudia**: el departamento, el establecimiento, el nivel educativo y grado, si la escuela es
pública o privada, si está en área urbana o rural, el sexo, el pueblo de pertenencia, la jornada,
el plan de estudios, y cómo cerró el año (aprobado, no aprobado o retirado), además de si repite
grado o se está graduando.

No es una encuesta ni una muestra estadística: es un **censo administrativo**, o sea la totalidad
de los registros del sistema. Por eso son más de cuatro millones de filas.

### Para qué se usan

- **Planificar y asignar recursos:** saber dónde hay más estudiantes, qué niveles están saturados
  y en qué municipios crece o cae la matrícula.
- **Medir resultados:** calcular qué porcentaje aprueba, no aprueba o abandona el año, y comparar
  entre departamentos, niveles o sectores.
- **Detectar brechas:** contrastar lo urbano contra lo rural, lo público contra lo privado, o cómo
  varían los resultados según sexo y pueblo de pertenencia.
- **Investigación y periodismo de datos:** sustentar reportajes, tesis y estudios con evidencia.

Preguntas como "¿en qué departamento se aprueba menos el nivel básico?" o "¿se abandona más la
escuela en el área rural?" se pueden responder con este dataset, pero solo después de procesarlo,
porque tal como viene no es legible.

### Qué no contienen

- Solo abarca el ciclo **2024**: no hay manera de comparar contra otros años.
- No hay identificador de estudiante, así que **no se puede seguir a una persona** en el tiempo ni
  reconstruir su trayectoria.
- No incluye calificaciones, edad, discapacidad, datos socioeconómicos, ni información sobre
  docentes o infraestructura de los establecimientos.

---

## Estructura

### Formato de entrega

- **23 archivos** en formato `.xlsx` (Excel): **22 de datos**, uno por departamento, más
  **1 diccionario de variables**.
- Cada archivo de datos tiene una **hoja con los registros**. La primera fila son los encabezados;
  de la segunda en adelante, los datos.
- **Grano:** una fila es una inscripción. Todos los archivos comparten exactamente el mismo esquema
  de 15 columnas, así que se pueden concatenar.
- **Sin celdas vacías:** cuando un dato no se registró, viene el código `9` (Ignorado), que es un
  valor real y no un faltante.

Casi todos los valores son **códigos numéricos**, no texto. El diccionario de variables es el que
traduce cada código a su etiqueta; sin él los datos no se interpretan.

### Las 15 columnas

| Columna | Tipo | Qué contiene |
|---|---|---|
| `Año` | Entero | Ciclo escolar. Siempre `2024`. |
| `CodEstablecimiento` | Texto | Código del establecimiento, formato `DD-MM-NNNN-SS`. |
| `Departamento_F` | Entero | Departamento, del `1` al `22`. |
| `Depto_mupio` | Entero | Campo de departamento y municipio. Ver notas. |
| `Sector` | Código | Quién administra el establecimiento. |
| `Área` | Código | Ubicación urbana o rural. |
| `Sexo` | Código | Sexo del estudiante. |
| `Grado` | Entero | Grado que cursa. Su significado depende de `Nivel`. |
| `Nivel` | Código | Nivel educativo. |
| `Pueblo_Per` | Código | Pueblo de pertenencia. |
| `Plan_Est` | Código | Plan de estudios (modalidad de asistencia). |
| `Jornada_Est` | Código | Jornada en que estudia. |
| `Resultado_F` | Código | Cómo cerró el ciclo escolar. |
| `Repitente` | Código | Si está repitiendo el grado. |
| `Graduando` | Código | Si se gradúa en ese ciclo. |

### Catálogo de códigos

- **Sector:** `1` Público · `2` Privado · `3` Municipal · `4` Cooperativa
- **Área:** `1` Urbana · `2` Rural · `9` Ignorado
- **Sexo:** `1` Hombre · `2` Mujer · `9` Ignorado
- **Nivel:** `1` Preprimaria · `2` Primaria · `3` Básico · `4` Diversificado ·
  `5` Primaria de adultos · `9` Ignorado
- **Pueblo de pertenencia:** `1` Maya · `2` Garífuna · `3` Xinka ·
  `4` Afrodescendiente/Creole/Afromestizo · `5` Ladino/Mestizo · `6` Extranjero · `9` Ignorado
- **Plan de estudios:** `1` Diario · `2` Fin de semana · `3` Virtual a distancia ·
  `4` Semipresencial · `5` Mixto
- **Jornada:** `1` Matutina · `2` Vespertina · `3` Nocturna · `4` Doble · `5` Intermedia ·
  `9` Ignorado
- **Resultado final:** `1` Promovido · `2` Vigente · `3` Retirado · `4` Retirado definitivo ·
  `5` No promovido · `9` Ignorado
- **Repitente:** `1` Sí · `2` No · `9` Ignorado
- **Graduando:** `1` Sí es graduando · `2` No es graduando · `9` Ignorado

### Catálogo de departamentos

`1` Guatemala · `2` El Progreso · `3` Sacatepéquez · `4` Chimaltenango · `5` Escuintla ·
`6` Santa Rosa · `7` Sololá · `8` Totonicapán · `9` Quetzaltenango · `10` Suchitepéquez ·
`11` Retalhuleu · `12` San Marcos · `13` Huehuetenango · `14` Quiché · `15` Baja Verapaz ·
`16` Alta Verapaz · `17` Petén · `18` Izabal · `19` Zacapa · `20` Chiquimula · `21` Jalapa ·
`22` Jutiapa

El diccionario incluye además el catálogo completo de **municipios**, con un código de cuatro
dígitos donde los dos primeros son el departamento (por ejemplo, `0101` es el municipio de
Guatemala).

### El código de establecimiento

`CodEstablecimiento` no es un identificador plano: codifica una jerarquía en cuatro segmentos
separados por guiones, como `19-01-0001-42`.

| Segmento | Ejemplo | Qué es |
|---|---|---|
| 1.º | `19` | Departamento |
| 2.º | `01` | Municipio dentro del departamento |
| 3.º | `0001` | Número del establecimiento |
| 4.º | `42` | Nivel educativo que ofrece |

Valores del cuarto segmento: `40`, `41` y `42` preprimaria · `43` primaria ·
`44` primaria de adultos · `45` básico · `46` diversificado.

Como el nivel va dentro del código, **un mismo establecimiento que atiende varios niveles aparece
con varios códigos distintos**. Contar códigos únicos no equivale a contar escuelas.

### Notas para interpretar correctamente

- **El municipio se deriva del código del establecimiento**, no de la columna `Depto_mupio`: esa
  columna trae un valor constante dentro de cada archivo y no sirve para desagregar.
- **`Grado` siempre se lee junto a `Nivel`.** Rangos: preprimaria `0`–`6`, primaria `1`–`6`,
  básico `1`–`3`, diversificado `4`–`7`, primaria de adultos `1`–`4`. Un `1` de primaria no es lo
  mismo que un `1` de básico.
- **El diccionario menciona una variable `Modalidad`** (bilingüe / monolingüe) que **no existe** en
  los archivos de datos. No la asumas.
- **El código `9` (Ignorado) es un dato real.** Decide si lo excluyes o lo reportas aparte, pero sé
  consistente y documenta la decisión.

### Inconsistencias conocidas

Particularidades reales de los archivos, verificadas sobre los datos. Si no las tomas en cuenta,
tus resultados van a salir mal.

| Qué pasa | Dónde | Cómo manejarlo |
|---|---|---|
| **Prefijo `00-` en el código.** Cerca del 36% de los registros del departamento de Guatemala usan `00-` como primer segmento en lugar de `01-`. Corresponden a establecimientos de la capital. | Solo en `guatemala.xlsx`. Ningún otro departamento lo presenta. | Normaliza el prefijo antes de derivar el municipio. Si no lo haces, a Guatemala le saldrán cerca de 39 municipios en lugar de los **17** reales, y unos 310 mil registros quedarán mal atribuidos. |
| **`Depto_mupio` no varía.** Su valor es constante dentro de cada archivo. | En los 22 archivos de datos. | Ignora esa columna para desagregar por municipio; usa el segundo segmento de `CodEstablecimiento`. |
| **`Modalidad` documentada pero ausente.** | Diccionario de variables. | No la asumas ni intentes derivarla. |
| **`Resultado_F = 4` casi no aparece.** El retiro se concentra en el código `3`. | En todos los archivos. | Decide cómo tratas el retiro y documéntalo. |
| **Hojas adicionales vacías.** | `solola.xlsx` | Lee la hoja que contiene los datos, no la primera por posición a ciegas. |
| **Conteo de municipios inflado.** | Efecto del caso `00-`. | El total nacional de municipios con datos debe quedar alrededor de **340**, no cerca de 384. |

Atajo de verificación: si tu proceso reporta **17 municipios para Guatemala** y un total cercano a
**4,298,887 registros**, vas bien. Si Guatemala te da 39, no normalizaste el prefijo `00-`.

### Cifras para validar tu lectura

| Indicador | Valor esperado |
|---|---|
| Total de registros | 4,298,887 |
| Sector: Público / Privado / Cooperativa / Municipal | 74.7% / 20.9% / 4.0% / 0.3% |
| Área: Rural / Urbana | 61.4% / 38.6% |
| Sexo: Hombre / Mujer | 50.7% / 49.3% |
| Nivel: Primaria / Básico / Preprimaria / Diversificado | 56.4% / 17.8% / 17.1% / 8.5% |
| Resultado: Promovido / No promovido / Retirado | 85.2% / 9.2% / 5.5% |
| Municipios en el departamento de Guatemala | 17 |

---

## Archivos

El dataset se entrega en 23 archivos `.xlsx`: uno por departamento más el diccionario de variables.

### Diccionario de variables

Empieza por aquí: es el archivo que traduce todos los códigos.

| Archivo | Tamaño | Descarga |
|---|---|---|
| `diccionario_de_variables.xlsx` | 25 KB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/diccionario_de_variables.xlsx |

### Datos por departamento

| Departamento | Archivo | Registros | Tamaño | Descarga |
|---|---|---:|---:|---|
| Alta Verapaz | `alta_verapaz.xlsx` | 391,085 | 20.3 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/alta_verapaz.xlsx |
| Baja Verapaz | `baja_verapaz.xlsx` | 81,736 | 4.2 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/baja_verapaz.xlsx |
| Chimaltenango | `chimaltenango.xlsx` | 166,965 | 8.6 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/chimaltenango.xlsx |
| Chiquimula | `chiquimula.xlsx` | 127,409 | 6.6 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/chiquimula.xlsx |
| El Progreso | `el_progreso.xlsx` | 49,803 | 2.5 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/el_progreso.xlsx |
| Escuintla | `escuintla.xlsx` | 207,618 | 10.7 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/escuintla.xlsx |
| Guatemala | `guatemala.xlsx` | 863,879 | 42.5 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/guatemala.xlsx |
| Huehuetenango | `huehuetenango.xlsx` | 316,771 | 16.5 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/huehuetenango.xlsx |
| Izabal | `izabal.xlsx` | 120,326 | 6.2 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/izabal.xlsx |
| Jalapa | `jalapa.xlsx` | 99,625 | 5.1 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/jalapa.xlsx |
| Jutiapa | `jutiapa.xlsx` | 134,571 | 6.9 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/jutiapa.xlsx |
| Petén | `peten.xlsx` | 169,629 | 8.8 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/peten.xlsx |
| Quetzaltenango | `quetzaltenango.xlsx` | 232,627 | 12.0 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/quetzaltenango.xlsx |
| Quiché | `quiche.xlsx` | 268,998 | 14.0 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/quiche.xlsx |
| Retalhuleu | `retalhuleu.xlsx` | 98,128 | 5.1 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/retalhuleu.xlsx |
| Sacatepéquez | `sacatepequez.xlsx` | 91,552 | 4.7 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/sacatepequez.xlsx |
| San Marcos | `san_marcos.xlsx` | 303,565 | 15.8 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/san_marcos.xlsx |
| Santa Rosa | `santa_rosa.xlsx` | 108,264 | 5.6 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/santa_rosa.xlsx |
| Sololá | `solola.xlsx` | 122,831 | 6.3 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/solola.xlsx |
| Suchitepéquez | `suchitepequez.xlsx` | 159,287 | 8.3 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/suchitepequez.xlsx |
| Totonicapán | `totonicapan.xlsx` | 113,139 | 5.8 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/totonicapan.xlsx |
| Zacapa | `zacapa.xlsx` | 71,079 | 3.7 MB | https://hackaton-aibuildersgt-datos.s3.us-east-1.amazonaws.com/zacapa.xlsx |

**Total:** 4,298,887 registros.
