# Project Charter

## 1. Identificación del proyecto
- **Nombre del proyecto:** CD1-Gaston Giron-Desempleo
- **Equipo:** Gastón Girón (Individual)
- **Integrantes:** Gastón Girón
- **Fecha de elaboración:** 08 de Octubre de 2026
- **Versión del documento:** v1.0

## 2. Descripción general
El proyecto consiste en realizar un estudio estadístico sobre el desempleo en la localidad de Freyre, Córdoba, utilizando los datos recolectados en el Censo Comunitario local. Se busca entender el perfil de las personas desocupadas.

## 3. Problema
En Freyre existen personas desocupadas que buscan trabajo activamente. El problema radica en que no se conocen con precisión cuáles son las características sociodemográficas y educativas comunes de esta población, lo que dificulta el diseño de políticas públicas eficientes. No asumimos de antemano las causas del empleo informal o la falta de estudios.

## 4. Justificación
Este problema afecta directamente a los ciudadanos desocupados de Freyre y a la economía local. Es relevante porque permitirá a la Municipalidad tomar decisiones informadas sobre dónde enfocar los cursos de capacitación laboral, el apoyo a emprendimientos y los programas de inserción de empleo según las verdaderas necesidades detectadas.

## 5. Pregunta principal
¿Qué características están asociadas con las situaciones de desempleo en la población de Freyre?

## 6. Preguntas secundarias
1. ¿Qué proporción de las personas de 16 años o más está desocupada y busca trabajo (r5)?
2. ¿Esa proporción cambia según el nivel educativo (r4)?
3. ¿Cambia según los grupos de edad (r2)?
4. ¿Cambia según sexo o género (r3)?
5. Entre quienes están desocupados, ¿qué proporción hizo changas (r5c) o participa de un emprendimiento (r12)?

## 7. Objetivo general
Caracterizar y describir la situación del desempleo en la población de 16 años o más en la localidad de Freyre, identificando las variables asociadas a esta condición a partir de los datos del Censo Comunitario.

## 8. Objetivos específicos
1. Calcular la tasa de desocupación general para la población de 16 años o más en Freyre.
2. Comparar la distribución del desempleo según el nivel educativo, grupos de edad y género.
3. Cuantificar la participación en changas y emprendimientos dentro de la población desocupada.
4. Generar un reporte final con gráficos estadísticos legibles para las autoridades municipales.

## 9. Alcance del proyecto
- **9.1. Territorio:** Localidad de Freyre, Córdoba.
- **9.2. Población o unidad de análisis:** Persona (individuos de 16 años o más).
- **9.3. Período de estudio:** El período en el que se realizó el relevamiento del Censo Comunitario.
- **9.4. Variables principales:** r5 (Condición de actividad), r2 (Año de nacimiento / Edad), r4 (Nivel educativo), r3 (Sexo o género), r5c (Changas) y r12 (Emprendimientos).
- **9.5. Productos que se desarrollarán:** Base de datos limpia, diccionario de variables, tablas de cruces estadísticos y un informe con conclusiones gráficas.

## 10. Fuera de alcance
No se analizará el tiempo que las personas llevan buscando trabajo, el tipo de trabajo específico que buscan, ni los motivos de la pérdida de su último empleo, ya que el Censo no incluye estas preguntas. Tampoco se realizará una fusión de registros individuales (join) con la Encuesta Permanente de Hogares (EPH-INDEC).

## 11. Destinatarios
La Municipalidad de Freyre (Áreas de Empleo, Producción y Acción Social) y la comunidad educativa.

## 12. Beneficios esperados
Aportar datos reales y confiables para que el municipio pueda diseñar programas de empleo, asistencia y capacitación técnica orientados específicamente a los sectores más vulnerables de la localidad.

## 13. Datos requeridos

| Información necesaria | Variable o indicador posible | Fuente potencial |
| :--- | :--- | :--- |
| Condición laboral de desocupado | Tasa de desocupación (r5) | Censo Comunitario Freyre |
| Edad y Grupos Etarios | Edad calculada mediante r2 | Censo Comunitario Freyre |
| Nivel de estudios alcanzado | Nivel educativo (r4) | Censo Comunitario Freyre |
| Género de los encuestados | Sexo o género (r3) | Censo Comunitario Freyre |
| Actividades complementarias | Proporción de changas (r5c) y emprendimientos (r12) | Censo Comunitario Freyre |

## 14. Fuentes de datos iniciales

| Fuente | Institución responsable | Tipo de fuente | Disponibilidad |
| :--- | :--- | :--- | :--- |
| Censo Comunitario | Municipalidad de Freyre | Primaria / Interna | Alta (Planilla oficial disponible) |
| EPH-INDEC | INDEC | Secundaria / Externa | Alta (Pública como benchmark de contexto) |

## 15. Entregables principales
- Dataset preparado y limpio.
- Diccionario de datos de las variables utilizadas.
- Indicadores calculados (TD16 y TPEA).
- Gráficos estadísticos y tablas de cruces.
- Informe analítico final.

## 16. Criterios de éxito
- La pregunta principal se responde utilizando la evidencia de los datos del censo.
- Las limitaciones de los datos quedan explícitamente aclaradas en el informe.
- Los indicadores macro son comparables con la EPH para contextualizar la magnitud del problema.
- Los resultados finales son claros y comprensibles para personas ajenas al equipo técnico.

## 17. Restricciones y supuestos
- **Restricciones:** El análisis está limitado estrictamente a las preguntas que contiene el censo local. No se pueden extrapolar conclusiones causales directas (asociación no implica causa).
- **Supuestos:** Se asume que las respuestas recolectadas mediante el autorreporte de los ciudadanos en el censo son honestas y reflejan la realidad.

## 18. Riesgos iniciales

| Riesgo | Probabilidad | Impacto | Acción preventiva |
| :--- | :--- | :--- | :--- |
| Sesgo por autorreporte incorrecto en r5 | Media | Media | Explicitar la limitación en el informe final. |
| Datos faltantes en variables clave | Baja | Alta | Aplicar reglas de limpieza y filtrado de nulos al inicio. |
| Confundir indicadores de EPH como si fueran de Freyre | Media | Alta | Documentar estrictamente que la EPH es solo un marco de comparación. |

## 19. Responsabilidades iniciales

| Rol | Integrante | Responsabilidades |
| :--- | :--- | :--- |
| Coordinación | Gastón Girón | Gestión de plazos y entregas en GitHub. |
| Datos | Gastón Girón | Limpieza y procesamiento del archivo del Censo. |
| Análisis | Gastón Girón | Cálculo de indicadores y armado de gráficos. |
| Documentación | Gastón Girón | Redacción del informe final y actualización del repositorio. |

## 20. Aprobación del equipo
¿El equipo considera que el proyecto está suficientemente definido para comenzar? **Sí.**  
- **Fecha de aprobación:** 08 de Octubre de 2026  
- **Versión aprobada:** v1.0
