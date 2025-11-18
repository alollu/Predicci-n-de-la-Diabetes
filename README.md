# Prediccion-de-la-Diabetes
Clasificación binaria de diabetes utilizando modelos SVM y Gradient Boosting, con análisis de calidad de datos (imputación de ceros)

Introducción:
Este proyecto tiene como objetivo desarrollar y evaluar modelos de Clasificación Binaria para predecir si un paciente es diabético o no, utilizando el famoso Dataset Pima Indians Diabetes.

El enfoque se centra en la calidad de los datos, la optimización de hiperparámetros y la justificación de métricas en un contexto médico (priorizando el Recall)

Metodología y Modelos:
El flujo de trabajo siguió un proceso riguroso de ciencia de datos, desde la limpieza hasta la optimización:

1. Preprocesamiento Crucial (Calidad del Dato)
Problema: Se identificaron valores inviables (0) en variables fisiológicas clave (Glucosa, IMC, Presión Arterial).
Solución: Los ceros se trataron como datos faltantes y se imputaron con la mediana de su columna correspondiente, ya que el análisis demostró que el 41.18% de los casos con datos faltantes de Insulina eran diabéticos (indicando un alto riesgo).
Escalado: Los datos fueron estandarizados utilizando StandardScaler para optimizar el rendimiento de modelos basados en distancia (SVM, KNN).

2. Modelos Evaluados:
Se entrenó y comparó una amplia gama de clasificadores, incluyendo:
Modelos Lineales: Regresión Logística.
Modelos Basados en Vecinos: K-Nearest Neighbors (KNN).
Modelos de Árbol: Decision Tree, Random Forest.
Modelos de Boosting: Gradient Boosting (Mejor rendimiento base).
Modelo Optimizado Final: Support Vector Machine (SVM).

Resultados y Conclusión Final.
La evaluación se centró en el Recall (Exhaustividad) para la clase positiva (Diabetes), ya que minimiza los Falsos Negativos (no detectar la enfermedad).

Modelo	                 AUC (Poder de Discriminación)	      Recall (Métrica Clave)
Regresión Logística	                 8.624	                         ≈0.63
SVM Optimizado                       8.795	                          0.65


Conclusión.
El modelo seleccionado como el más adecuado para el diagnóstico es el SVM Optimizado (mediante GridSearchCV con kernel RBF). 
1. Ofrece el **Recall más alto (0.65)**, cumpliendo con el objetivo de minimizar Falsos Negativos.
2. Posee el **AUC más alto (0.8795)**, demostrando la mejor capacidad de predicción y robustez.

El proyecto concluye que un clasificador no lineal y rigurosamente ajustado (SVM con kernel RBF) es la opción más segura y efectiva para la predicción de la diabetes en este conjunto de datos

*Requisitos de Ejecución
Para reproducir este análisis en su totalidad:

Entorno: Google Colab o Jupyter Notebook.

Librerías Esenciales:

pandas, numpy

matplotlib, seaborn

scikit-learn (especialmente GridSearchCV, StandardScaler, y clasificadores SVC, RandomForestClassifier, etc.)

Datos: El archivo diabetes.csv (Dataset Pima Indians Diabetes) debe estar en el mismo directorio que el notebook.
