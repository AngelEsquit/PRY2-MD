# Proyecto 2 - Data Mining

### Deteccion de Cancer de Mama - Wisconsin Breast Cancer Dataset

**Universidad del Valle de Guatemala | Semestre I 2026**

Javier Espana #23361 | Angel Esquit #23221 | Roberto Barreda #23354 | Diego Lopez #23747

## Objetivo
Construir y comparar modelos de clasificacion binaria para predecir `Class` en el dataset Wisconsin Breast Cancer:
- `2 = Benigno`
- `4 = Maligno`

## Estado del proyecto
- Semana 1: EDA completado.
- Semana 2: preprocesamiento + 3 modelos base completados (Regresion Logistica, KNN, SVM).
- Semana 3: validacion, tuning, comparacion final y seleccion de modelo completados.

## Archivos clave
- `notebook/EDA.ipynb`: flujo principal integrado de Semana 1 y Semana 2.
- `notebook/PrepData y Modelos Base.ipynb`: soporte de preparacion de datos y modelos base.
- `notebook/Validacion y Diseno Experimental.ipynb`: flujo de Semana 3 con validacion, tuning, analisis de ajuste y comparacion.
- `docs/Documento_Semana3.tex`: fuente LaTeX del documento final de Semana 3.
- `docs/Documento_Semana3.pdf`: salida compilada del documento final de Semana 3.
- `data/Datos.csv`: dataset original.
- `data/Datos_limpio.csv`: dataset limpio con identificador.
- `data/Datos_modelado.csv`: dataset limpio sin identificador, listo para modelado.
- `data/resultados_semana3_csv/`: tablas exportadas del notebook de Semana 3 en formato CSV.

## Ejecucion
1. Abrir `notebook/EDA.ipynb` para el flujo de Semana 1 y Semana 2.
2. Abrir `notebook/Validacion y Diseno Experimental.ipynb` para el flujo de Semana 3.
3. Ejecutar las celdas en orden.
4. Verificar dependencias: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`.

## Entregables
- Semana 2 en notebook: preprocesamiento, seleccion de variables, train/test split, 3 modelos base, metricas y matrices de confusion.
- Semana 3 en notebook: validacion cruzada, tuning de LR/KNN/SVM, diagnostico de ajuste, comparacion integrada y exportacion de tablas a CSV.
- Documento formal de entrega: `docs/Documento_Semana3.tex` (fuente) y `docs/Documento_Semana3.pdf` (compilado).
