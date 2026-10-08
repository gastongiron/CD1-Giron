# Diccionario de Datos - Proyecto Desempleo Freyre

Este documento detalla las variables seleccionadas del Censo Comunitario de Freyre para el análisis del MVP de Desempleo.

## Universo del MVP
- **Filtro de Edad:** Personas de 16 años o más (Derivado de `r2` / Año de nacimiento).

## Detalle de Variables Seleccionadas

### 1. Condición de Actividad (`r5`)
- **Tipo:** Nominal / Categórica.
- **Descripción:** Identifica la situación laboral principal declarada por el ciudadano en los últimos 7 días.
- **Categoría Clave para el MVP:** "Desocupado (busca trabajo)".

### 2. Año de Nacimiento (`r2`)
- **Tipo:** Numérica / Entera.
- **Descripción:** Año en que nació el encuestado. Se utiliza para calcular la edad actual (`2026 - r2`) y segmentar en grupos etarios (ej. de 16 a 24 años, de 25 a 59 años, etc.).

### 3. Nivel Educativo (`r4`)
- **Tipo:** Ordinal.
- **Descripción:** Máximo nivel de instrucción alcanzado por la persona (ej. Primario incompleto/completo, Secundario incompleto/completo, Terciario/Universitario). Se usará para analizar si a menor nivel educativo se incrementa la tasa de desocupación.

### 4. Sexo o Género (`r3`)
- **Tipo:** Nominal.
- **Descripción:** Registro biológico o de identidad de la persona. Se usará como variable de cruce para evaluar brechas de género en el desempleo local.

### 5. Realización de Changas (`r5c`)
- **Tipo:** Binaria (Sí / No).
- **Descripción:** Pregunta condicional para registrar si la persona, a pesar de no tener empleo fijo o declararse desocupada, realizó alguna actividad paga menor en la última semana.

### 6. Participación en Emprendimientos (`r12`)
- **Tipo:** Nominal / Categórica.
- **Descripción:** Evalúa si la persona de 16 años o más lidera o participa de un proyecto productivo o comercial independiente.
