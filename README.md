# ia1--2bots---Predicción_valor_facturación_energía_hogar_Colombia-
# 📊 Descripción de los datos

Dataset: Superservicios - Facturación a Usuarios - Energía (Formato TC2)

Fuente: Datos Abiertos Colombia

Cantidad de datos: 94 millones de registros (trabajamos con muestras representativas).

# ❓ Preguntas a responder
🔹 Antes del EDA (conceptual)

Queremos predecir el consumo de energía de los usuarios en Colombia para anticipar el valor de sus facturas. Este problema es relevante porque el consumo eléctrico impacta la planeación de subsidios, la sostenibilidad financiera de las empresas y la gestión de la demanda en un sector crítico como el energético. Un modelo predictivo permite identificar patrones de consumo y apoyar decisiones tanto regulatorias como empresariales.

El EDA busca entender la distribución del consumo, detectar outliers, explorar relaciones entre consumo y variables como tarifa, tipo de usuario y subsidios, e identificar qué predictores tienen mayor influencia. Esta fase permite preparar un modelo más robusto y segmentado.

Se consideran el consumo promedio, la mediana y los percentiles 95–99.9 para medir extremos. La correlación entre variables numéricas identifica predictores útiles. Además, se analizarán métricas de error (MAE, RMSE) en la fase de modelado. Estas métricas son útiles porque capturan tanto tendencias centrales como desviaciones extremas en el consumo.

El consumo de energía es un problema real y con impacto social en Colombia. Elegimos este tema porque conecta datos abiertos de gran escala con un problema práctico de predicción y optimización de recursos.

🔹 Después del EDA (basado en datos)

Usamos datos tabulares de facturación eléctrica a usuarios en Colombia (94M registros). Incluyen consumo en kWh, tarifas aplicadas, subsidios, moras, fechas de facturación y empresa prestadora del servicio.

Las variables principales incluyen: consumo de usuario (car_t1743_cons_usuario), promedio histórico (car_t1743_cons_prom_sem), tarifa aplicada (tarifa_apl), tipo de usuario (car_t1743_tipo_usu_rc), subsidios (car_t1743_cons_subsist, val_subs_usu), días facturados, valor total de factura y empresa prestadora. Estas variables permiten segmentar usuarios en residenciales, comerciales e industriales, identificar beneficiarios de subsidios y relacionar patrones de consumo con precios, tiempos de facturación y regiones.

El dataset presenta retos de tamaño (94M filas), outliers extremos en consumo (hasta 588.000 kWh), valores nulos en algunas columnas, y categorías sin documentación clara (ej. tipo de usuario 1, 2, 3). También existen sesgos regionales, pues empresas pequeñas registran menos datos. Estos factores requieren muestreo, transformaciones logarítmicas y segmentación por tipo de usuario para entrenar un modelo robusto.
