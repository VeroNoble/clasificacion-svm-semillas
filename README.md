# Clasificación de semillas con SVM

Trabajo práctico de la Tecnicatura Superior en Ciencia de Datos e IA.

## Objetivo

Clasificar variedades de semillas de trigo a partir de sus características geométricas, usando Support Vector Machines (SVM), y comparar el desempeño de distintos kernels.

## Datos

Dataset **Seeds** del UCI Machine Learning Repository (descargado directamente desde el repositorio en el notebook). Contiene 210 muestras de semillas de trigo de 3 variedades (Kama, Rosa, Canadian), descriptas por 7 atributos geométricos: área, perímetro, compacidad, longitud, ancho, coeficiente de asimetría y longitud del surco.

## Enfoque

1. Carga de datos directamente desde la fuente (UCI) y partición 80/20 en train/test, con estandarización de variables (`StandardScaler`).
2. Entrenamiento de un modelo SVM con kernel lineal.
3. Comparación de desempeño entre kernel **lineal** y kernel **RBF**.
4. Visualización de las fronteras de decisión de ambos kernels (usando 2 variables, área y perímetro, para poder graficarlas en 2D).
5. Extracción e interpretación de los pesos y sesgos del modelo lineal para cada enfrentamiento entre clases (uno-contra-uno).

## Resultados

- Accuracy con kernel lineal: **90.48%** (38 de 42 casos de prueba)
- Accuracy con kernel RBF: **90.48%**
- Ambos kernels obtienen el mismo desempeño en este dataset, lo que sugiere que las clases son mayormente separables de forma lineal. Con solo 42 casos de prueba la diferencia entre modelos es poco concluyente; una validación cruzada daría una comparación más robusta.

## Herramientas

Python · pandas · numpy · scikit-learn · matplotlib

## Cómo correrlo

```bash
pip install -r requirements.txt
jupyter notebook clasificacion_svm_semillas.ipynb
```

El notebook descarga el dataset automáticamente desde UCI, no requiere archivos adicionales. Funciona tanto en Google Colab como en local.
