# ia1--2bots---Predicción_valor_facturación_energía_hogar_Colombia-
**Curso: Inteligencia Artificial I -2025-2 C1**<br>
**Equipo: 2bots**<br>
**Autores** 
 <ul> <li>Daniel Fernando Leal Ayala 2191430</li>
     <li>Rafael Andres Pinilla Vargas </li>
 </ul>

# Descripción de los datos

Dataset: Superservicios - Facturación a Usuarios - Energía (Formato TC2)

Fuente: https://www.datos.gov.co/Minas-y-Energ-a/Superservicios-Facturaci-n-a-Usuarios-Energia/gw2d-7n7y/about_data

Cantidad de datos: 50000 registros 

# ❓ Preguntas a responder
## Antes del EDA 
### Problema y relevancia

*El análisis del consumo de energía en Colombia permite predecir el consumo de los usuarios para anticipar sus facturas y comprender los patrones de uso. Esto es importante porque ayuda a planificar la demanda, garantizar la sostenibilidad financiera del sector eléctrico y optimizar la operación de la red. Además, proporciona información útil para los usuarios, al permitir una facturación más precisa y detectar consumos inusuales, mientras apoya la toma de decisiones estratégicas y regulatorias en el sector..*

### Objetivo del análisis
El EDA busca entender la distribución del consumo, detectar outliers, explorar relaciones entre consumo y variables como tarifa, tipo de usuario y subsidios, e identificar qué predictores tienen mayor influencia. Esta fase ayuda a organizar y limpiar los datos, seleccionar variables relevantes y establecer una base sólida para construir predicciones confiables del consumo de energía.

### Métricas o indicadores
Se pueden usar métricas descriptivas como el consumo promedio, la mediana y percentiles altos (95–99.9) para evaluar la distribución y detectar valores extremos. También son útiles las correlaciones entre consumo y variables como tipo de usuario, tarifa, días facturados o número de familias, ya que permiten identificar predictores relevantes. Estas medidas ayudan a entender la variabilidad del consumo y orientar la selección de variables antes de construir modelos predictivos.

Estas métricas permiten comprender la distribución y variabilidad del consumo, detectar valores atípicos que podrían distorsionar el análisis y evaluar qué variables están más relacionadas con el consumo. Esto ayuda a seleccionar predictores relevantes y a preparar los datos de manera adecuada antes de construir modelos de predicción.

### Motivación de la elección
Se eligió este problema porque el consumo de energía tiene impacto práctico y social en Colombia, ofrece un desafío con datos reales de gran escala y permite explorar patrones relevantes que son útiles tanto para usuarios como para la gestión del sector eléctrico.

## Después del EDA 

Usamos datos tabulares de facturación eléctrica a usuarios en Colombia (94M registros). Incluyen consumo en kWh, tarifas aplicadas, subsidios, moras, fechas de facturación y empresa prestadora del servicio.

Las variables principales incluyen: consumo de usuario (car_t1743_cons_usuario), promedio histórico (car_t1743_cons_prom_sem), tarifa aplicada (tarifa_apl), tipo de usuario (car_t1743_tipo_usu_rc), subsidios (car_t1743_cons_subsist, val_subs_usu), días facturados, valor total de factura y empresa prestadora. Estas variables permiten segmentar usuarios en residenciales, comerciales e industriales, identificar beneficiarios de subsidios y relacionar patrones de consumo con precios, tiempos de facturación y regiones.

El dataset presenta retos de tamaño (94M filas), outliers extremos en consumo (hasta 588.000 kWh), valores nulos en algunas columnas, y categorías sin documentación clara (ej. tipo de usuario 1, 2, 3). También existen sesgos regionales, pues empresas pequeñas registran menos datos. Estos factores requieren muestreo, transformaciones logarítmicas y segmentación por tipo de usuario para entrenar un modelo robusto.
