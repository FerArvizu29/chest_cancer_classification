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

<img width="819" height="951" alt="image" src="https://github.com/user-attachments/assets/b31e47da-1269-43f5-bdd8-59b4a2cf51b9" />


---

## Balance de Clases

Las imágenes fueron divididas en tres subconjuntos:

- Entrenamiento
- Validación
- Prueba

Posteriormente, se analizó la distribución de clases en cada subconjunto.

<img width="695" height="451" alt="image" src="https://github.com/user-attachments/assets/8c7b5327-e8a7-42b1-a1a1-53e3618bb1aa" />

<img width="686" height="451" alt="image" src="https://github.com/user-attachments/assets/51e7eed1-cd0d-45fe-89db-3a9a66747428" />

<img width="695" height="451" alt="image" src="https://github.com/user-attachments/assets/c5bcce84-d92e-4352-85a2-8ce64cde1ba3" />


Se identificó un ligero desbalance de clases en el conjunto de entrenamiento, el cual fue mitigado mediante la asignación de pesos de clase (class weights) durante el entrenamiento. Esto permite que el modelo otorgue la misma importancia a todas las categorías y reduzca el sesgo hacia la clase mayoritaria.

---

## Metodología

### 1. Preprocesamiento de datos

- Redimensionamiento de imágenes.
- Normalización de valores de píxeles.

### 2. Transfer Learning

- Uso de modelos preentrenados en ImageNet. EfficientNetB0, Xception y VGG16.
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

El modelo con mejor desempeño fue EfficientNetB0 **mostró:

- Alta precisión en las tres clases.
- Buen equilibrio entre recall y precisión.
- Bajo sobreajuste en el conjunto de validación.

---

## Conclusión

Los resultados obtenidos demuestran que el uso de Transfer Learning es una estrategia efectiva para la clasificación de imágenes médicas cuando se dispone de un conjunto de datos limitado.

Este proyecto representa un paso hacia el desarrollo de herramientas de apoyo diagnóstico que podrían complementar la evaluación médica especializada.
