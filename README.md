# Proyecto 2 - Data Mining

### Detección de Cáncer de Mama – Wisconsin Breast Cancer Dataset

**Universidad del Valle de Guatemala | Semestre I 2026**

Javier España #23361 | Angel Esquit #23221 | Roberto Barreda #23354 | Diego Lopez #23747


## Objetivo
Construir y comparar modelos de clasificación binaria para predecir `Class` en el dataset Wisconsin Breast Cancer:
- `2 = Benigno`
- `4 = Maligno`

## Estado del proyecto
- Semana 1: EDA completado.
- Semana 2: preprocesamiento + 3 modelos base completados (Regresión Logística, KNN, SVM).
- Semana 3: pendiente (optimización y selección final).

## Archivos clave
- `notebook/EDA.ipynb`: flujo principal integrado (EDA, limpieza, split, modelos base y comparación).
- `data/Datos.csv`: dataset original.
- `data/Datos_limpio.csv`: dataset limpio con identificador.
- `data/Datos_modelado.csv`: dataset limpio sin identificador (listo para modelado).

## Ejecución
1. Abrir `notebook/EDA.ipynb`.
2. Ejecutar las celdas en orden.
3. Verificar dependencias: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`.

## Entregables (resumen)
- Semana 2 en notebook: preprocesamiento, selección de variables, train/test split, 3 modelos base, métricas y matrices de confusión.
- Documento formal de entrega: consolidar en `docs/` según formato solicitado por el curso.
