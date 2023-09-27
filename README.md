# Predicción de Precios de Diamantes - Proyecto Kaggle

Este proyecto se enfoca en la competencia de Kaggle para predecir los precios de los diamantes en función de diversas características. El objetivo principal es entrenar un modelo de aprendizaje automático que pueda realizar predicciones precisas sobre el precio de los diamantes en función de las características proporcionadas.

![Descripción de la imagen](https://raw.githubusercontent.com/Stefy-Castillo/Kaggle_competition/main/03_imagenes/02_Diamante.JPG)

## Datos

Los datos utilizados en este proyecto provienen de la competencia de Kaggle y se pueden encontrar en la carpeta de `01_data`. El conjunto de datos consta de 40455 observaciones y 10 columnas, que incluyen características como el peso (`carat`), calidad de corte (`cut`), color, claridad, dimensiones (`x`, `y`, `z`), profundidad (`depth`), tabla (`table`) y el precio (`price`) que se utilizará como variable respuesta.

## Preprocesamiento de Datos

### Gestión de Nulos

No se encontraron valores nulos en el conjunto de datos original. Sin embargo, se identificaron ceros en las dimensiones `x`, `y` y `z` de algunos diamantes. Estos ceros no se eliminaron del conjunto de entrenamiento debido a la necesidad de mantener la consistencia entre el conjunto de entrenamiento y prueba.

### Gestión de Outliers

Para abordar la presencia de outliers, se tomaron las siguientes medidas:

- Se observó que las dimensiones `y` y `z` tenían outliers extremos. Para mantener la consistencia en el conjunto de prueba, se optó por eliminarlos. Además, debido a su alta correlación con la variable respuesta, se eliminaron para reducir la multicolinealidad.

![Descripción de la imagen](https://raw.githubusercontent.com/Stefy-Castillo/Kaggle_competition/main/03_imagenes/03_Correlacion_variables.JPG)
![Descripción de la imagen](https://raw.githubusercontent.com/Stefy-Castillo/Kaggle_competition/main/03_imagenes/04_Outliers_y_z.JPG)

- Los outliers en otras columnas se manejaron reemplazándolos por la media de los valores correspondientes.

### Encoding

El encoding de las variables categóricas (`cut`, `color` y `clarity`) se realizó utilizando el método de ordinal encoding. Este enfoque se eligió después de analizar gráficamente la relación entre estas variables y el precio, viendo que existe un orden entre dichas variables.

![Descripción de la imagen](https://raw.githubusercontent.com/Stefy-Castillo/Kaggle_competition/main/03_imagenes/05_Orden_variables_categoricas.JPG)

## Puntuación en Kaggle

El modelo entrenado logró una puntuación RMSE (Error Cuadrático Medio) de 0.13860 en la competencia de Kaggle, lo que indica una alta precisión en la predicción de precios de diamantes.

