# Detección de Cáncer de Pulmón a Partir de Tomografías

---

## Descripción

Este proyecto tiene como objetivo la clasificación automática de tomografías pulmonares en tres categorías:

- Adenocarcinoma
- Carcinoma de células grandes
- Tejido pulmonar normal

Se implementaron redes neuronales convolucionales (CNN) preentrenadas, aprovechando técnicas de Transfer Learning para mejorar el rendimiento del modelo con un conjunto de datos relativamente pequeño.

El propósito principal es identificar el modelo más robusto y preciso, con miras a desarrollar una herramienta de apoyo en el diagnóstico médico del cáncer de pulmón.

---

## Conjunto de Datos

El conjunto de datos está compuesto por aproximadamente 1000 imágenes de tomografías pulmonares, distribuidas en las tres clases mencionadas.

Se utilizaron imágenes médicas reales organizadas por categoría para entrenar y evaluar los modelos de clasificación.

---

## Balance de Clases

Las imágenes fueron divididas en tres subconjuntos:

- Entrenamiento
- Validación
- Prueba

Posteriormente, se analizó la distribución de clases en cada subconjunto.

Se identificó un ligero desbalance de clases, el cual fue mitigado mediante la asignación de pesos de clase (class weights) durante el entrenamiento. Esto permite que el modelo otorgue la misma importancia a todas las categorías y reduzca el sesgo hacia la clase mayoritaria.

---

## Metodología

### 1. Preprocesamiento de datos

- Redimensionamiento de imágenes.
- Normalización de valores de píxeles.
- Aumento de datos (Data Augmentation) para mejorar la capacidad de generalización.

### 2. Transfer Learning

- Uso de modelos preentrenados en ImageNet.
- Congelación inicial de capas convolucionales.
- Ajuste fino (Fine-Tuning) de las últimas capas.

### 3. Entrenamiento

- Función de pérdida: Categorical Crossentropy.
- Optimizador: Adam.
- Implementación de class weights para compensar el desbalance.

### 4. Evaluación

- Matriz de confusión.
- Precisión, recall y F1-score.
- Análisis comparativo entre modelos.

---

## Resultados

Se compararon distintos modelos preentrenados para determinar cuál presenta mejor desempeño en términos de precisión y capacidad de generalización.

El modelo con mejor desempeño mostró:

- Alta precisión en las tres clases.
- Buen equilibrio entre recall y precisión.
- Bajo sobreajuste en el conjunto de validación.

---

## Conclusión

Los resultados obtenidos demuestran que el uso de Transfer Learning es una estrategia efectiva para la clasificación de imágenes médicas cuando se dispone de un conjunto de datos limitado.

Este proyecto representa un paso hacia el desarrollo de herramientas de apoyo diagnóstico que podrían complementar la evaluación médica especializada.
