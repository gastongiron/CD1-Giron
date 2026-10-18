# Limitaciones de la Integración de Datos – Censo Freyre

Este documento detalla los motivos técnicos y metodológicos por los cuales se decidió mantener la Encuesta Permanente de Hogares (EPH - INDEC) únicamente como un benchmark cualitativo, descartando una integración física (join) de bases de datos.

## 1. Ausencia de Clave Común (Llave de Cruce)
No existen identificadores unívocos (como DNI anonimizados o códigos armonizados de registro) que vinculen a los ciudadanos encuestados en el Censo Comunitario de Freyre con las personas relevadas por el INDEC de forma horizontal.

## 2. Asimetría Territorial y Representatividad
- **Censo Comunitario:** Es un operativo exhaustivo de escala local y cobertura total sobre el territorio específico de la localidad de Freyre, Córdoba.
- **EPH (INDEC):** Es una encuesta por muestreo continuo diseñada con representatividad estadística para grandes aglomerados urbanos del país. No captura la realidad de comunas rurales o pequeñas localidades del interior de forma directa.

## 3. Disparidad en los Criterios de Flujo
Las categorías de la variable principal de condición de actividad (`r5`) responden a un autorreporte municipal que puede diferir sutilmente de las estrictas definiciones operativas que utiliza el INDEC para medir la Población Económicamente Activa (PEA).

## Conclusión de Alcance
Para evitar sesgos y deformaciones estadísticas en la muestra, la base de datos de la EPH se utilizará de forma totalmente aislada e independiente en el reporte estadístico final, funcionando como un espejo de comparación macro (benchmark) contra las tasas calculadas localmente en Freyre.
