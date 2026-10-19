# Calidad y features – Girón

- **Registro del proyecto:** persona
- **Archivo del tablón:** mi_tablon.csv
- **Filas totales:** 473
- **Pregunta central:** ¿Qué características están asociadas con las situaciones de desempleo en la población de Freyre?

## Claves y Llaves de Vinculación

| Código | Columna | Tres slugs reales, copiados de una fila |
| :--- | :--- | :--- |
| `codigo` | Identificador único de vivienda | 101, 102, 103 |
| `hogar_n` | Identificador de hogar dentro de la vivienda | 1, 1, 1 |

---

## Calidad y Consistencia de los Datos

### 1. Control de la Exportación y la Unión (Merge)
Al realizar la unión horizontal (`pd.merge`) de los archivos originales del censo (`persona.csv`, `hogar.csv` y `cuestionario.csv`), el principal desafío de calidad radicó en asegurar la consistencia de los tipos de datos de las llaves (`codigo` y `hogar_n`). 
- Se controló mediante una unión interna (`how='inner'`) en Pandas.
- Esto evitó la pérdida de registros o la duplicación artificial de filas, garantizando mantener el total estricto de **473 filas a nivel de registro de Persona**.

### 2. Diagnóstico y Tratamiento de Valores Vacíos (Missing Values)
La variable resultado principal `r5` (Condición de actividad) presenta **79 celdas vacías (nulos)** sobre el total de la muestra.
- **Decisión metodológica:** No se completan con "No" ni se imputan con categorías inventadas. 
- **Justificación:** Corresponden a saltos lógicos del flujo del cuestionario (por ejemplo, personas fuera del rango de respuesta o menores de edad). Forzar un dato en estas celdas introduciría un sesgo artificial severo en el cálculo de las tasas locales de desempleo.

---

## Features Propias Derivadas (Nuevas Variables)

Para enriquecer el potencial analítico del modelo sin depender de las variables precalculadas de la cátedra (`fe_`), se desarrollaron dos nuevas features en el script:

1. **`edad_actual`**
   - *Regla de origen:* Operación aritmética `2026 - r2` (Año de nacimiento). Vive en `mi_tablon.csv`.
   - *Propósito:* Permitir la segmentación de la población activa en tramos etarios específicos para evaluar el impacto del desempleo juvenil.

2. **`tiene_actividad_secundaria`**
   - *Regla de origen:* Indicador binario (1 o 0). Se activa en 1 si `r5c == "Sí"` (realizó changas) O si `r12 == "Sí"` (lidera/participa de un emprendimiento propio). Vive en `mi_tablon.csv`.
   - *Propósito:* Identificar estrategias de autoempleo o ingresos informales compensatorios dentro de la población desocupada.

---

## Frecuencias de la Variable Principal (`r5`)
Calculado de forma estricta sobre los **394 registros válidos con respuesta** (excluyendo los 79 nulos por flujo):

| Slug de Categoría | Registros | Porcentaje | Gráfico de Distribución Visual |
| :--- | :---: | :---: | :--- |
| `empleo_formal` | 178 | 45.18% | ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓ (45.2%) |
| `jubilado_o_pensionado` | 55 | 13.96% | ▓▓▓▓▓▓▓ (14.0%) |
| `estudia_y_no_trabaja` | 39 | 9.90% | ▓▓▓▓▓ (9.9%) |
| `empleo_informal` | 39 | 9.90% | ▓▓▓▓▓ (9.9%) |
| `cuentapropista` | 36 | 9.14% | ▓▓▓▓ (9.1%) |
| `tareas_del_hogar_sin_remun` | 20 | 5.08% | ▓▓ (5.1%) |
| `desocupado_busca_trabajo` | 14 | 3.55% | ▓ (3.6%) |
| `otra_situaci_n` | 13 | 3.30% | ▓ (3.3%) |
| **Total Válidos** | **394** | **100%** | |

---

## Gráficos de Cruces Estadísticos (Resultados del Tablón)

### A. Brecha de Género en el Desempleo (`r3` vs `r5`)
Visualización de la tasa de desocupación según la identidad de género declarada:

```text
Mujer   [4.76%] ▓▓▓▓▓▓▓▓▓▓▓▓BC
Varón   [2.40%] ▓▓▓▓▓▓BC
No Bin. [0.00%] 
```
*El desempleo afecta casi al doble a la población femenina de la muestra local.*

### B. Desempleo por Ciclo de Vida (Grupos de Edad)
Visualización del impacto de la desocupación según tramos etarios calculados:

```text
16 a 24 años (Jóvenes) [9.23%] ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓B
25 a 59 años (Adultos) [3.21%] ▓▓▓▓▓▓▓▓B
60 años o más (Mayores)[0.00%] 
```
*Se constata una fuerte concentración del desempleo en los segmentos de inserción juvenil en Freyre.*

---

## Qué queda afuera del Análisis
Una variable crítica que el Censo Comunitario no releva es el **Tiempo o Antigüedad de búsqueda de empleo** (meses o años acumulados en situación de desocupación). Esta ausencia limita el alcance del proyecto, impidiendo determinar si el desempleo detectado en Freyre es de carácter puramente transitorio o si responde a una problemática estructural de largo plazo.
