# Avances Semana 3

## Objetivo de este documento
Centralizar el estado real de avance de Semana 3 para que la comparacion final y el documento se construyan sobre un mismo diseno experimental, sin suposiciones y sin romper comparabilidad entre modelos.

## Alcance cubierto hasta ahora
Este avance consolida lo realizado en:
- Validacion y diseno experimental.
- Optimizacion de Regresion Logistica y KNN.
- Optimizacion de SVM con kernel RBF.
- Analisis integrado de sobreajuste/subajuste y comportamiento sesgo-varianza.

Todavia falta:
- Definir la seleccion final de modelo de Semana 3.
- Redactar el documento formal de 3-4 paginas.
- Revisar consistencia final entre notebook y documento.

## Notebook de referencia
- notebook/Validacion y Diseno Experimental.ipynb

Este notebook debe mantenerse como fuente unica para continuidad. Ahora incluye:
- Validacion base.
- Tuning de LR y KNN.
- Tuning de SVM.
- Tablas integradas de base vs optimizado.
- Evidencia de ajuste y ranking de candidatos optimizados.

## Diseno experimental ya fijado (no cambiar)
1. Dataset de entrada: data/Datos_modelado.csv
2. Split heredado de Semana 2: 80/20 estratificado
3. Random state: 42
4. Escenarios de variables:
- Escenario A: todas las variables
- Escenario B: top 3 variables (Bare Nuclei, Uniformity of Cell Size, Uniformity of Cell Shape)
5. Validacion: StratifiedKFold con 5 folds (shuffle=True, random_state=42)
6. Regla anti fuga:
- Escalado dentro de Pipeline
- Test set sin uso en tuning
- Decisiones de seleccion basadas en validacion

## Avance de validacion base (pre-tuning)
Ya esta implementado y ejecutado en el notebook:
- Confirmacion del dataset final y del split heredado de Semana 2.
- Definicion del esquema de validacion y metricas comunes.
- Evaluacion base de LR, KNN y SVM en ambos escenarios.
- Tablas CV globales y por escenario.
- Tabla de consistencia CV vs Test.
- Seccion de control de fuga de informacion.

Variables/artefactos disponibles en kernel:
- cv_strategy
- scoring_metrics
- modelos_base
- cv_results_store
- df_cv_results
- df_cv_vs_test

## Avance de optimizacion (LR, KNN y SVM)
Ya esta implementado en el notebook:
- Tuning en ambos escenarios con GridSearchCV.
- Metrica principal de seleccion: recall de la clase maligna (Class=4).
- Grillas trazables para LR, KNN y SVM-RBF.
- Tabla de mejores hiperparametros por modelo y escenario.
- Comparacion base vs optimizado en la misma metrica objetivo.
- Tabla de deltas y tabla integrada de candidatos optimizados.
- Diagnostico de ajuste con gap train-valid.

Variables/artefactos disponibles en kernel:
- scorer_recall_maligna
- param_grid_lr
- param_grid_knn
- param_grid_svm
- tuning_store
- svm_best_params_df
- df_svm_compare
- df_svm_fit
- df_svm_errors
- df_svm_top
- best_params_df_all
- df_compare_all
- df_delta_all
- df_fit_diag_all
- df_optimized_only

## Hallazgos funcionales ya documentados
1. LR optimizada mejora frente a su baseline y sigue siendo competitiva por AUC y balance precision-recall.
2. KNN optimizado no muestra mejora consistente respecto al baseline.
3. SVM optimizado es el modelo mas fuerte en recall de malignos y reduccion de falsos negativos.
4. En escenario A, SVM optimizado alcanza recall_test_maligna = 1.0000 y FN_Test = 0.
5. En escenario B, SVM optimizado reduce falsos negativos de 4 a 1.
6. No se observan senales fuertes de sobreajuste por gap train-valid en los modelos optimizados; el trade-off mas claro en SVM-A es una caida de precision/AUC a cambio de mayor sensibilidad.

## Condiciones obligatorias para cerrar Semana 3
Para mantener rigor y comparabilidad en la etapa final:
1. Reutilizar exactamente el mismo split y cv_strategy.
2. Mantener el test set intacto; ya no debe usarse para decisiones nuevas de tuning.
3. Reportar la comparacion final usando las tablas integradas del notebook.
4. Justificar la seleccion final con recall de malignos, falsos negativos, estabilidad y trade-offs, no solo con accuracy.

## Que necesita la siguiente etapa para cerrar Semana 3
1. Tomar `df_optimized_only` como base para la comparacion final formal.
2. Definir el modelo final y justificar si se privilegia sensibilidad clinica (SVM) o separacion probabilistica mas balanceada (LR).
3. Redactar el documento final de 3-4 paginas.
4. Verificar consistencia entre las tablas del notebook y el texto final.

## Checklist rapido de continuidad
- [x] Abrir notebook/Validacion y Diseno Experimental.ipynb
- [x] Verificar split heredado y esquema de validacion
- [x] Implementar tuning de LR y KNN
- [x] Implementar tuning de SVM con el mismo protocolo
- [x] Consolidar comparacion integrada de modelos optimizados
- [ ] Seleccionar el modelo final
- [ ] Redactar el documento final de Semana 3
