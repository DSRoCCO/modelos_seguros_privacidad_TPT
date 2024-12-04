# Proyecto: Predicción de Beneficios de Seguro y Protección de Datos

Este proyecto tiene como objetivo ayudar a la compañía de seguros **Sure Tomorrow** a realizar varias tareas utilizando técnicas de machine learning, asegurando la protección de los datos personales de los clientes sin comprometer el rendimiento del modelo.

## Tareas

1. **Encontrar clientes similares a un cliente determinado**: Esta tarea ayuda a los agentes de marketing a identificar clientes con características similares para optimizar sus estrategias de marketing.
   
2. **Predecir si un nuevo cliente recibirá un beneficio de seguro**: Se comparan los resultados de un modelo entrenado con los de un modelo dummy no entrenado para evaluar su efectividad.

3. **Predecir la cantidad de beneficios de seguro que recibirá un cliente**: Utilizando un modelo de regresión lineal, se predicen los beneficios basados en diversas características del cliente.

4. **Proteger los datos personales de los clientes sin afectar el modelo de predicción**: Se desarrolla un algoritmo de enmascaramiento de datos para asegurar que los datos personales de los clientes sean difíciles de recuperar en caso de filtraciones, sin afectar la calidad de los modelos de machine learning.

## Descripción de los Datos

El dataset se encuentra en el archivo **/datasets/insurance_us.csv** y contiene las siguientes características:

- **Sexo**
- **Edad**
- **Salario**
- **Número de familiares**
  
El objetivo es predecir el **número de beneficios de seguro** recibidos por una persona asegurada en los últimos cinco años.

## Resultados de las Tareas

### Tarea 1: Encontrar clientes similares
Usando distancia euclidiana, se identificaron los clientes más similares al cliente de índice 0. Los resultados muestran distancias pequeñas para los clientes más cercanos, ayudando a los agentes de marketing a orientar mejor sus campañas.

### Tarea 2: Predecir la probabilidad de recibir un beneficio
- **Modelo Dummy**: Precisión de 0.89
- **Modelo entrenado** (Regresión Logística): Precisión de 0.99

Se comprobó que el modelo entrenado supera ampliamente al modelo dummy, evidenciando que el aprendizaje automático mejora la precisión en la predicción.

### Tarea 3: Predecir la cantidad de beneficios de seguro
- **Modelo de Regresión Lineal**:
  - MSE: 0.13
  - R2: 0.44
- **Modelo Random Forest**:
  - MSE: 0.06
  - R2: 0.75

El modelo Random Forest mostró mejores resultados que la regresión lineal, con un menor MSE y un mayor R2, sugiriendo que es más efectivo para capturar relaciones complejas entre las características.

### Tarea 4: Proteger los datos personales de los clientes
Se aplicó un método de ofuscación de datos, agrupando por edad y añadiendo ruido controlado al salario, lo que resultó en modelos de regresión lineal y Random Forest entrenados con los datos ofuscados.

- **Modelo de Regresión Lineal (con datos ofuscados)**:
  - MSE: 0.06
  - R2: 0.76
- **Modelo Random Forest (con datos ofuscados)**:
  - MSE: 0.08
  - R2: 0.69

Comparando con los resultados de los modelos entrenados con datos normales, se observó que la regresión lineal mejoró ligeramente su precisión, mientras que el Random Forest disminuyó debido a la pérdida de complejidad en las relaciones entre las características.

## Conclusiones

- **Tarea 1**: Se utilizó la distancia euclidiana para identificar clientes similares, con un algoritmo que encontró el top 5 de clientes con características semejantes.
  
- **Tarea 2**: La regresión logística mostró un rendimiento superior a un modelo dummy, destacando la efectividad del modelo entrenado para predecir beneficios.

- **Tarea 3**: La regresión lineal no proporcionó buenos resultados, pero el modelo Random Forest superó a la regresión lineal al capturar mejor las relaciones entre las características. La regularización con Ridge no mostró mejoras significativas en este caso.

- **Tarea 4**: El enmascaramiento de datos protegió la información personal sin afectar drásticamente el rendimiento de los modelos, aunque se observó que la regresión lineal se benefició más del enmascaramiento que el Random Forest, probablemente debido a la simplicidad del modelo.

Este proyecto demuestra la capacidad de los modelos de machine learning para predecir beneficios de seguros y cómo se puede proteger la privacidad de los clientes sin comprometer significativamente el rendimiento del modelo.
