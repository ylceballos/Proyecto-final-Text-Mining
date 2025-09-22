# Resultados y Conclusiones

## Comparación de Modelos

| Modelo | val_loss | val_acc  | test_acc |
|--------|----------|----------|----------|
| A (CNN básica) | 0.399 | 0.909 | – |
| B (CNN profunda + BN + L2) | 1.810 | 0.179 | – |
| C (MobileNetV2 Transfer Learning) | 0.065 | **0.986** | **0.967** |

 El **mejor modelo** fue **C (MobileNetV2 con Transfer Learning)** con `val_acc ≈ 98.6%` y `test_acc ≈ 96.7%`.

---

# Métricas en el conjunto de prueba (Modelo C)

- **Accuracy global:** 0.97  
- **Precision / Recall / F1 macro:** ≈ 0.97  
- **Clases con mejor desempeño:** *FreshStrawberry* (100% precisión y recall).  
- **Clases con mayor confusión:** *RottenBellpepper* (precisión 0.93, recall 0.91), con errores principalmente hacia *RottenTomato* y *RottenCarrot*.  

La matriz de confusión confirma que el modelo distingue muy bien frutas frescas, aunque todavía presenta pequeñas confusiones entre vegetales en mal estado (clases visualmente similares).

---

# Justificación

- **Modelo A (baseline):** sirvió como referencia inicial con desempeño aceptable (`val_acc = 0.91`), pero su baja complejidad limitó su capacidad de generalización.  
- **Modelo B (profundo con BN + L2):** a pesar de incluir más capas y regularización, no logró buen rendimiento (`val_acc = 0.18`), probablemente por sobreajuste o mal ajuste de hiperparámetros.  
- **Modelo C (MobileNetV2 Transfer Learning):** alcanzó los mejores resultados (`val_acc = 0.986`, `test_acc = 0.967`) gracias a:
  - Uso de **features preentrenadas en ImageNet**, que capturan patrones universales como bordes y texturas.  
  - **GlobalAveragePooling y Dropout**, que reducen el sobreajuste.  
  - Eficiencia en entrenamiento con pocas épocas y datos.

---

# Conclusión Final

El **Modelo C (MobileNetV2 con Transfer Learning)** es la mejor opción para la clasificación de frutas y verduras en este proyecto, ya que combina:

- **Alto rendimiento** en validación y prueba.  
- **Generalización superior** a arquitecturas entrenadas desde cero.  
- **Eficiencia** en recursos y tiempo de entrenamiento.  

Por lo tanto, este modelo se selecciona como la **arquitectura final** para el proyecto.
