# 🧪 Experimento A/B en Landing Page: ¿Qué versión convierte y vende más?

Análisis estadístico de un experimento A/B con **40,000 usuarios** para decidir, con datos, qué versión de una página de inicio (A o B) debe implementarse. Incluye pruebas de hipótesis, validación de supuestos, visualizaciones y un resumen ejecutivo para stakeholders.

![Python](https://img.shields.io/badge/Python-3.x-blue) ![Pandas](https://img.shields.io/badge/Pandas-Análisis-150458) ![SciPy](https://img.shields.io/badge/SciPy-Pruebas_estadísticas-8caae6) ![Statsmodels](https://img.shields.io/badge/Statsmodels-z--test-orange) ![Seaborn](https://img.shields.io/badge/Seaborn-Visualización-4c72b0)

## 🎯 Pregunta de negocio
¿Qué versión de la landing page genera más conversión y mayor gasto por cliente, y qué papel juegan el canal de tráfico y el tipo de usuario?

## ✅ Resultado principal
**La Página B supera a la A en conversión y en gasto, y ambas diferencias son estadísticamente significativas.**

| Métrica | Página A | Página B | Prueba | p-value |
|---|---|---|---|---|
| Usuarios expuestos | 19,982 | 20,018 | — | — |
| Conversiones | 2,512 | 3,194 | — | — |
| **Tasa de conversión** | 12.57% | **15.96%** | Z-test de dos proporciones | < 0.001 |
| **Gasto promedio (usuarios que convirtieron)** | $61.09 | **$68.75** (+12.5%) | t-test de Welch (tras Levene) | < 0.001 |

**Recomendación:** implementar la Página B, y replicar el test con controles adicionales antes de atribuir la mejora al diseño (el análisis no establece causalidad).

## 🔎 Hallazgos secundarios
- **Fuente de tráfico:** hay asociación estadísticamente significativa con la conversión (χ² = 8.66, p = 0.034), pero el efecto práctico es pequeño: Email 14.99%, Ads 14.74%, Referral 13.88%, Organic 13.79%. Antes de reasignar presupuesto conviene evaluar el costo de adquisición por canal.
- **Tipo de usuario:** no hay diferencia significativa entre nuevos (14.36%) y recurrentes (14.09%), p = 0.464.

## 🧪 Metodología
1. **Validación de datos:** sin nulos ni duplicados en `user_id`, conversión de `date` a datetime, rango del experimento (1–28 ene 2026) y revisión de categorías.
2. **Gasto promedio (A vs B):** prueba de Levene para elegir entre t-test estándar o de Welch.
3. **Tasa de conversión (A vs B):** z-test de dos proporciones.
4. **Fuente de tráfico vs. conversión:** chi-cuadrado, con verificación de independencia y frecuencias esperadas.
5. **Tipo de usuario vs. conversión:** z-test de dos proporciones.
6. **Visualización:** gráficos de volumen y de proporción para cada variable.
7. **Resumen ejecutivo** con interpretación de negocio y límites de cada conclusión.

## 🛠️ Stack
`Python` · `Pandas` · `NumPy` · `SciPy` · `Statsmodels` · `Seaborn` · `Matplotlib` · `Jupyter Notebook`

## ⚠️ Limitaciones
- Las pruebas son observacionales: no prueban causalidad.
- La comparación de gasto usa solo usuarios que convirtieron.
- El análisis no evalúa si la magnitud de la diferencia justifica el costo del cambio.

## 📁 Estructura
```
├── Proyecto_Landing_Experiment.ipynb
├── landing_experiment.csv
└── README.md
```

## 👤 Autor
**Miguel Angel Rodriguez Vega** · [LinkedIn](https://www.linkedin.com/in/miguel-rodriguez-dataanalyst/) · [Correo](mian.rove04@gmail.com)
