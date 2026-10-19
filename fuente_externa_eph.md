# Ficha de Fuente Externa y Decisión de Cruce – Girón

- **Registro del proyecto:** persona
- **Tema:** MVP Desempleo Freyre
- **Fuente Externa:** Encuesta Permanente de Hogares (EPH)
- **Institución Responsable:** Instituto Nacional de Estadística y Censos (INDEC)

## 1. Identificación y Propósito de la Fuente
La EPH se incorpora al proyecto con el objetivo exclusivo de actuar como un **benchmark cualitativo externo (espejo macro estadístico)**. Permitirá contrastar las distribuciones de desempleo por género, educación y edad obtenidas localmente en Freyre contra los promedios regionales de la Región Pampeana o de los aglomerados de la provincia de Córdoba.

## 2. Decisión del Cruce (Justificación de Alcance)
Se determina formalmente que **NO se realizará ningún acoplamiento o unión física (join/merge)** a nivel de registros individuales entre la base del Censo Comunitario y las microbases de la EPH por los siguientes motivos técnicos:
1. **Ausencia de llave común:** Las estructuras de datos no comparten identificadores unívocos (como códigos de barras o IDs armonizados anonimizados) que vinculen horizontalmente las filas a nivel de persona física.
2. **Asimetría Territorial:** El censo local es un barrido completo y exhaustivo sobre el territorio de Freyre, mientras que la EPH es una encuesta por muestreo continuo diseñada con representatividad exclusiva para grandes aglomerados urbanos del país.
3. **Disparidad de Criterios:** Los flujos de las preguntas laborales del formulario municipal presentan ligeras variaciones conceptuales frente a los exigentes parámetros del INDEC para categorizar la Población Económicamente Activa (PEA).

## Conclusión
Para mantener la transparencia y robustez metodológica, la base externa se procesará de forma totalmente aislada e independiente en el informe final, sirviendo solo como contexto comparativo de las magnitudes calculadas en Freyre.
