# uber-lyft-regresion-predictiva
Análisis de regresión predictiva para estimar precios de viajes Uber/Lyft usando datos reales de Boston, MA.

# 🚕 Predicción de Precios de Viajes en Uber y Lyft – Modelado de Regresión Predictiva

Este proyecto aplica técnicas de **regresión predictiva** para estimar el precio de viajes de Uber y Lyft en Boston, MA, usando variables como distancia, clima, hora del día y tipo de servicio. El análisis está basado en el **Capítulo 5 del libro _Essentials of Marketing Analytics_**, que combina fundamentos de regresión lineal (simple y múltiple) con métodos modernos de predicción y validación de modelos.

---

## 🎯 Objetivos

- Utilizar regresión lineal simple y múltiple como base para modelos predictivos.
- Evaluar la capacidad del modelo para predecir precios con nuevas observaciones.
- Identificar variables clave que explican el comportamiento del precio del viaje.
- Aplicar buenas prácticas de codificación de datos, validación cruzada y selección de variables.

---

## 📁 Estructura del Proyecto

📦 uber-lyft-regresion-predictiva/
├── data/
│ └── rideshare_kaggle.csv # Dataset original descargado de Kaggle
├── notebooks/
│ └── modelo_regresion.ipynb # Análisis paso a paso en Jupyter
├── diccionario_variables.md # Diccionario detallado de las 57 variables
├── README.md # Documentación del proyecto

## 🧠 Enfoque Metodológico

Este proyecto implementa un **modelo de regresión predictiva**, apoyado en técnicas clásicas de regresión lineal, pero con un enfoque orientado a la predicción precisa de valores futuros.

**Técnicas cubiertas del Capítulo 5 del libro:**

- Regresión lineal simple y múltiple
- Modelado predictivo supervisado
- Validación cruzada (k-fold)
- Métricas de evaluación: MAE, RMSE, MAPE
- Codificación dummy de variables categóricas
- Selección automática de variables (forward, backward, stepwise)
- Prevención de sobreajuste (overfitting) y detección de multicolinealidad
## 🤖 Modelado Predictivo

Se construyó un modelo de regresión lineal múltiple con las siguientes características:

- División de datos en entrenamiento y validación
- Aplicación de validación cruzada (k-fold)
- Codificación dummy de variables categóricas
- Selección de variables basada en su importancia predictiva

### 📈 Resultados del modelo:

- **RMSE (Root Mean Squared Error):** aproximadamente \$11.43
- **MAE (Mean Absolute Error):** se mantiene dentro de márgenes aceptables
- **MAPE (Mean Absolute Percentage Error):** útil para comparar modelos relativos

Estos resultados indican que el modelo tiene un desempeño razonable al predecir el precio de viajes con datos históricos similares.


## 📑 Diccionario de Variables

| Variable                        | Tipo de dato | Descripción                                             |
|---------------------------------|--------------|---------------------------------------------------------|
| `id`                            | object       | Identificador único del viaje                          |
| `timestamp`                     | float64      | Marca de tiempo en formato Unix                        |
| `hour`                          | int64        | Hora del día (0–23)                                    |
| `day`                           | int64        | Día del mes                                             |
| `month`                         | int64        | Mes del año                                             |
| `datetime`                      | object       | Fecha y hora en formato legible                        |
| `timezone`                      | object       | Zona horaria del viaje                                 |
| `source`                        | object       | Ubicación de inicio del viaje                          |
| `destination`                   | object       | Ubicación de destino del viaje                         |
| `cab_type`                      | object       | Tipo de servicio (Uber o Lyft)                         |
| `product_id`                    | object       | ID del producto o tipo de servicio                     |
| `name`                          | object       | Nombre del tipo de viaje (UberX, Lyft XL, etc.)        |
| `price`                         | int64        | Precio del viaje (USD)                                 |
| `distance`                      | float64      | Distancia del viaje (en millas)                        |
| `surge_multiplier`             | int64        | Multiplicador de tarifa dinámica (por demanda)         |
| `latitude`                      | float64      | Latitud del punto de origen                            |
| `longitude`                     | float64      | Longitud del punto de origen                           |
| `temperature`                   | float64      | Temperatura en Fahrenheit                              |
| `apparentTemperature`          | float64      | Sensación térmica (Fahrenheit)                         |
| `short_summary`                | object       | Resumen breve del clima                                |
| `long_summary`                 | object       | Descripción larga del clima                            |
| `precipIntensity`              | float64      | Intensidad de precipitación                            |
| `precipProbability`            | int64        | Probabilidad de precipitación (%)                      |
| `humidity`                      | float64      | Humedad relativa (%)                                   |
| `windSpeed`                     | float64      | Velocidad del viento                                   |
| `windGust`                      | float64      | Ráfaga de viento máxima                                |
| `windGustTime`                 | int64        | Hora de la ráfaga de viento máxima (Unix)              |
| `visibility`                    | float64      | Visibilidad (en millas)                                |
| `temperatureHigh`              | float64      | Temperatura máxima del día                             |
| `temperatureHighTime`         | int64        | Hora de la temperatura máxima (Unix)                   |
| `temperatureLow`               | float64      | Temperatura mínima del día                             |
| `temperatureLowTime`          | int64        | Hora de la temperatura mínima (Unix)                   |
| `apparentTemperatureHigh`     | float64      | Sensación térmica máxima del día                       |
| `apparentTemperatureHighTime` | int64        | Hora de la sensación térmica máxima                    |
| `apparentTemperatureLow`      | float64      | Sensación térmica mínima del día                       |
| `apparentTemperatureLowTime`  | int64        | Hora de la sensación térmica mínima                    |
| `icon`                          | object       | Ícono representativo del clima                         |
| `dewPoint`                      | float64      | Punto de rocío                                         |
| `pressure`                      | float64      | Presión atmosférica                                    |
| `windBearing`                  | int64        | Dirección del viento (en grados)                       |
| `cloudCover`                   | float64      | Porcentaje de nubosidad                                |
| `uvIndex`                       | int64        | Índice UV                                              |
| `visibility.1`                 | float64      | Visibilidad secundaria (duplicada)                     |
| `ozone`                         | float64      | Nivel de ozono                                         |
| `sunriseTime`                  | int64        | Hora del amanecer (Unix)                               |
| `sunsetTime`                   | int64        | Hora del atardecer (Unix)                              |
| `moonPhase`                    | float64      | Fase lunar                                             |
| `precipIntensityMax`          | float64      | Intensidad máxima de precipitación                     |
| `uvIndexTime`                 | int64        | Hora del índice UV (Unix)                              |
| `temperatureMin`              | float64      | Temperatura mínima (otra medida)                       |
| `temperatureMinTime`         | int64        | Hora de la temperatura mínima                          |
| `temperatureMax`              | float64      | Temperatura máxima (otra medida)                       |
| `temperatureMaxTime`         | int64        | Hora de la temperatura máxima                          |
| `apparentTemperatureMin`     | float64      | Sensación térmica mínima (otra medida)                 |
| `apparentTemperatureMinTime` | int64        | Hora de la sensación térmica mínima                    |
| `apparentTemperatureMax`     | float64      | Sensación térmica máxima (otra medida)                 |
| `apparentTemperatureMaxTime` | int64        | Hora de la sensación térmica máxima                    |
