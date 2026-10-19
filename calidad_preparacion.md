# Calidad y features – Girón

- **Registro del proyecto:** persona
- **Archivo del tablón:** mi_tablon.csv
- **Filas:** 473
- **Pregunta:** ¿Qué características están asociadas con las situaciones de desempleo en la población de Freyre?

## Claves

| Código | Columna | Tres slugs reales, copiados de una fila |
| :--- | :--- | :--- |
| `codigo` | Identificador de vivienda | 101, 102, 103 |
| `hogar_n` | Identificador de hogar dentro de la vivienda | 1, 1, 1 |

## Calidad
- **Un problema de la exportación que toca a mis claves:** Al realizar la unión (`merge`), si existieran códigos con formatos inconsistentes (por ejemplo, números leídos como texto), se podrían perder filas de personas. Se controló usando una unión interna (`how='inner'`) asegurando mantener el total estricto de 473 registros mapeados en el notebook.
- **Qué celda vacía no completo, y por qué:** La columna `r5` presenta 79 celdas vacías sobre los 473 registros totales. No las completo con "no" ni con categorías inventadas porque corresponden a saltos lógicos del cuestionario o respuestas no dadas; forzar un dato ahí sesgaría la tasa real de desempleo.

## Features
1. **Nombre:** `edad_actual`
   - *Regla:* Calculada numéricamente restando el año del censo menos el año de nacimiento: `2026 - r2`. Vive en `mi_tablon.csv`.
2. **Nombre:** `tiene_actividad_secundaria`
   - *Regla:* Indicador binario (1 o 0). Se activa en 1 si `r5c` es igual a "Sí" o si `r12` es diferente de "No". Vive en `mi_tablon.csv`.

## Frecuencias de la variable principal (`r5`)

| Slug | Registros | Porcentaje |
| :--- | :---: | :---: |
| `empleo_formal` | 178 | 45.18% |
| `jubilado_o_pensionado` | 55 | 13.96% |
| `estudia_y_no_trabaja` | 39 | 9.90% |
| `empleo_informal` | 39 | 9.90% |
| `cuentapropista` | 36 | 9.14% |
| `tareas_del_hogar_o_cuidado_sin_remun` | 20 | 5.08% |
| `desocupado_busca_trabajo` | 14 | 3.55% |
| `otra_situaci_n` | 13 | 3.30% |

## Qué queda afuera
Una variable que yo quería y que esta base no tiene es el **Tiempo de búsqueda de empleo** (antigüedad de la desocupación), lo que me impide analizar si el desempleo en Freyre es de carácter estructural o puramente transitorio.
