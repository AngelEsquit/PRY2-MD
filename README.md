# Proyecto 2 - Data Mining

## Estado actual
Este repositorio documenta el avance del proyecto de clasificación binaria para detección de cáncer de mama usando el dataset Wisconsin Breast Cancer.

Actualmente se encuentra completado:
- Semana 1: comprensión del problema y análisis exploratorio (EDA).
- Semana 2 (preparación de datos): limpieza, validación, selección de variables y partición de datos.

## Objetivo del proyecto
Construir, evaluar y comparar modelos de clasificación para predecir la variable Class:
- 2 = Benigno
- 4 = Maligno

## Estructura del repositorio
- data/: datasets en distintas etapas.
- docs/: lineamientos oficiales del proyecto y reporte de avance.
- notebook/: notebook principal con todo el flujo de trabajo.

## Artefactos disponibles
### Datos
- data/Datos.csv: dataset original.
- data/Datos_limpio.csv: dataset limpio con identificador para trazabilidad.
- data/Datos_modelado.csv: dataset limpio sin identificador, listo para modelado.

### Documentación
- docs/Proyecto2_PBL (3).pdf: lineamientos oficiales y rúbrica por semanas.
- docs/Semana1_EDA_Report.pdf: reporte técnico de Semana 1.

### Notebook principal
- notebook/EDA.ipynb: contiene EDA, limpieza/validación y la preparación para modelado.

## Qué ya quedó listo para modelar
Dentro de notebook/EDA.ipynb ya están definidos y ejecutados:
- Escenario A: todas las variables predictoras.
- Escenario B: subconjunto top de variables discriminativas.
- Train/Test split estratificado 80/20.
- random_state fijo para reproducibilidad.
- Validación de proporciones de clase en train y test.
- Handoff de matrices en memoria para entrenamiento.

Variables disponibles para la siguiente etapa:
- X_train_all, X_test_all, y_train, y_test
- X_train_top, X_test_top, y_train, y_test

## Cómo continuar (siguiente etapa)
Para continuar de forma consistente con el trabajo ya realizado:
1. Usar el notebook principal como fuente única de ejecución y evidencia.
2. Entrenar los modelos base sobre los mismos splits ya definidos.
3. Evaluar cada modelo con Accuracy, Precision, Recall y F1.
4. Construir matriz de confusión por modelo.
5. Consolidar resultados en una tabla comparativa única.
6. Documentar hallazgos con foco en desempeño de la clase maligna.

## Criterios de consistencia recomendados
- No redefinir splits ni cambiar random_state durante la comparación base.
- Mantener trazabilidad entre resultados, celdas del notebook y documento escrito.
- Reportar métricas con el mismo formato para todos los modelos.
- Evitar conclusiones sin evidencia cuantitativa.

## Ejecución rápida
1. Abrir notebook/EDA.ipynb.
2. Verificar que el entorno tenga pandas y scikit-learn.
3. Ejecutar celdas en orden.
4. Continuar desde la sección de modelado sobre las matrices ya generadas.

## Nota
Este README resume el estado operativo del repositorio para permitir continuidad técnica inmediata, manteniendo coherencia con los documentos oficiales y el notebook principal.
