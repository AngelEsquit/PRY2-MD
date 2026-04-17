# Avances Semana 3

## Objetivo de este documento
Centralizar el estado real de avance de Semana 3 (validación y tuning inicial) para que la siguiente etapa continúe con el mismo diseño experimental, sin suposiciones y sin romper comparabilidad.

## Alcance cubierto hasta ahora
Este avance consolida lo realizado en:
- Validación y diseño experimental (equivalente al bloque de validación base).
- Optimización de Regresión Logística y KNN.

No incluye todavía:
- Optimización de SVM con análisis profundo de overfitting/underfitting.
- Comparación final de los tres modelos optimizados.
- Selección final de modelo de Semana 3.

## Notebook de referencia
- notebook/Validacion y Diseno Experimental.ipynb

Este notebook contiene todo el flujo vigente de Semana 3 y debe mantenerse como fuente única para continuidad.

## Diseño experimental ya fijado (no cambiar)
1. Dataset de entrada: data/Datos_modelado.csv
2. Split heredado de Semana 2: 80/20 estratificado
3. Random state: 42
4. Escenarios de variables:
- Escenario A: todas las variables
- Escenario B: top 3 variables (Bare Nuclei, Uniformity of Cell Size, Uniformity of Cell Shape)
5. Validación: StratifiedKFold con 5 folds (shuffle=True, random_state=42)
6. Regla anti fuga:
- Escalado dentro de Pipeline
- Test set sin uso en tuning
- Decisiones de selección basadas en validación

## Avance de validación base (pre-tuning)
Ya está implementado y ejecutado en el notebook:
- Definición del esquema de validación y métricas comunes.
- Evaluación base de LR, KNN y SVM en ambos escenarios.
- Tablas de resultados CV globales y por escenario.
- Tabla de consistencia CV vs Test.
- Sección de control de fuga de información.

Variables/artefactos disponibles en kernel:
- cv_strategy
- scoring_metrics
- modelos_base
- cv_results_store
- df_cv_results
- df_cv_vs_test

## Avance de optimización (LR y KNN)
Ya está implementado y ejecutado en el notebook:
- Tuning en ambos escenarios con GridSearchCV.
- Métrica principal de selección: recall de clase maligna (Class=4).
- Grilla media y trazable para LR y KNN.
- Tabla de mejores hiperparámetros.
- Tabla comparativa base vs optimizado.
- Tabla de deltas (optimizado - base).
- Diagnóstico de ajuste con gap train-valid.

Variables/artefactos disponibles en kernel:
- scorer_recall_maligna
- param_grid_lr
- param_grid_knn
- tuning_store
- best_params_df
- df_compare
- df_delta
- df_fit_diag

## Hallazgos funcionales ya documentados
1. LR optimizada muestra mejora competitiva respecto a su baseline, especialmente en reducción de falsos negativos.
2. KNN optimizado no muestra mejora consistente respecto al baseline en los dos escenarios.
3. En LR y KNN no se observan señales fuertes de sobreajuste con el criterio de gap train-valid aplicado.

## Condiciones obligatorias para continuar
Para mantener rigor y comparabilidad en lo que sigue:
1. Reutilizar exactamente el mismo split y cv_strategy.
2. Mantener el test set intacto hasta evaluación final de cada candidato.
3. Reportar resultados nuevos en el mismo formato de tablas ya existente.
4. No cambiar la métrica principal del tuning sin dejar trazabilidad explícita.

## Qué necesita la siguiente etapa para cerrar Semana 3
1. Tomar SVM base y ejecutar tuning con el mismo protocolo.
2. Repetir comparación base vs optimizado para SVM.
3. Incorporar análisis de sobreajuste/subajuste con criterio equivalente al ya usado.
4. Integrar LR/KNN/SVM optimizados en una sola tabla comparativa formal.
5. Definir modelo final con justificación técnica y trade-offs.

## Checklist rápido de continuidad
- [ ] Abrir notebook/Validacion y Diseno Experimental.ipynb
- [ ] Ejecutar en orden desde imports hasta sección de tuning ya implementada
- [ ] Verificar existencia de best_params_df, df_compare, df_delta, df_fit_diag
- [ ] Implementar tuning de SVM con el mismo protocolo
- [ ] Consolidar comparación final de optimizados
