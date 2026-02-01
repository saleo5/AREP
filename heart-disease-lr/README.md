# Heart Disease Risk Prediction with Logistic Regression

## Exercise Summary

Implementación de regresión logística desde cero para predecir enfermedad cardíaca, incluyendo:
- Análisis exploratorio de datos (EDA)
- Entrenamiento con Gradient Descent
- Visualización de decision boundaries
- Regularización L2
- Deployment en Amazon SageMaker

## Dataset

**Fuente:** [Kaggle Heart Disease Dataset](https://www.kaggle.com/datasets/neurocipher/heartdisease)

| Característica | Valor |
|----------------|-------|
| Pacientes | 270 |
| Features | 14 (6 seleccionadas) |
| Target | Presence/Absence de enfermedad cardíaca |
| Tasa de enfermedad | 44.4% |

### Features utilizadas

| Feature | Descripción | Rango |
|---------|-------------|-------|
| Age | Edad del paciente | 29-77 años |
| BP | Presión arterial (mm Hg) | 94-200 |
| Cholesterol | Colesterol sérico (mg/dL) | 126-564 |
| Max HR | Frecuencia cardíaca máxima | 71-202 |
| ST depression | Depresión ST por ejercicio | 0-6.2 |
| Number of vessels fluro | Vasos coloreados (0-3) | 0-3 |

## Resultados del Modelo

| Métrica | Train | Test |
|---------|-------|------|
| Accuracy | 80.42% | 77.78% |
| Precision | 83.10% | 78.12% |
| Recall | 70.24% | 69.44% |
| F1-Score | 76.13% | 73.53% |

### Pesos aprendidos (interpretación)

- **Number of vessels fluro (+1.08):** Mayor factor de riesgo
- **ST depression (+0.91):** Indica isquemia cardíaca
- **Max HR (-0.94):** Factor protector
- **BP (+0.66):** Hipertensión aumenta riesgo

## Deployment en SageMaker

[Aquí agregarás tu experiencia con SageMaker]

### Proceso
1. Creación de notebook instance en SageMaker
2. Upload del modelo entrenado
3. Configuración del endpoint
4. Testing con datos de ejemplo

### Evidencia

[Insertar screenshots aquí]

1. **Training Job Status**
   ![Training](images/sagemaker_training.png)

### Ejemplo de predicción

**Input:**
```json
{
  "Age": 60,
  "BP": 140,
  "Cholesterol": 300,
  "Max HR": 140,
  "ST depression": 2.5,
  "Number of vessels fluro": 2
}
```

**Output:**
```json
{
  "probability": 0.85,
  "prediction": "Alto riesgo",
  "risk_level": "HIGH"
}
```

## Estructura del Repositorio
```
heart-disease-lr/
├── heart_disease_lr_analysis.ipynb   # Notebook principal
├── heart.csv                          # Dataset
├── model_params.npy                   # Modelo guardado
├── README.md                          # Este archivo
└── images/                            # Screenshots de SageMaker
    ├── sagemaker_training.png
    ├── sagemaker_endpoint.png
    └── sagemaker_inference.png
```

## Autor

**Samuel Leonardo Albarracin Vergara**  
Escuela Colombiana de Ingeniería Julio Garavito  
Curso: AREP 

## Referencias

- Dataset: https://www.kaggle.com/datasets/neurocipher/heartdisease
- AWS SageMaker: https://docs.aws.amazon.com/sagemaker/