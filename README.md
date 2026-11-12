# 📊 Evaluación de Impacto Causal y Econometría Aplicada en Campañas Financieras

> **Objetivo del Proyecto:** Aislar el retorno incremental real de una campaña comercial en el sector bancario utilizando técnicas avanzadas de Inferencia Causal (Propensity Score Matching) y Econometría de Panel (Diferencias en Diferencias), evitando sesgos de atribución orgánica.

---

## 🎯 1. Contexto de Negocio y El Problema
En la banca y gestión patrimonial, medir el éxito de una campaña basándose únicamente en métricas descriptivas tradicionales suele sobreestimar los resultados, ya que confunde el crecimiento natural del mercado (tendencia orgánica) con el impacto real de la intervención. 

Este proyecto resuelve este desafío respondiendo a la pregunta clave: 
*¿Cuánto incrementó realmente la conversión y el saldo de los clientes gracias a la campaña, controlando el sesgo de selección?*

---

## 🛠️ 2. Metodología y Stack Tecnológico
El pipeline analítico se divide en dos enfoques complementarios:
1. **Machine Learning Causal (PSM + IPW):** Uso de Regresión Logística para estimar la probabilidad de tratamiento (Propensity Score) y ponderación por probabilidad inversa para calcular el Efecto Promedio del Tratamiento (ATE).
2. **Econometría Clásica (Diferencias en Diferencias - DiD):** Modelamiento con Mínimos Cuadrados Ordinarios (OLS) sobre un panel longitudinal de clientes para evaluar el impacto neto en saldo promedio, validando el supuesto de **tendencias paralelas**.

* **Stack:** Python, Pandas, Statsmodels, Scikit-learn, Matplotlib, Seaborn, Google Colab / Databricks-ready.

---

## ⚙️ 3. Consideraciones Clave de Calidad de Datos (Data Governance)
* **Prevención de Data Leakage:** Se identificó y excluyó de forma estricta la variable `duration` (duración de la llamada), ya que representa una fuga de información del futuro al no conocerse ex-ante.
* **Verificación de Solapamiento (*Overlap*):** Se validó gráficamente el soporte común entre el grupo de control y de tratados para asegurar que los individuos comparados posean características similares.

---

## 📈 4. Resultados Principales

* **Efecto Causal (IPW):** La intervención generó un incremento absoluto del **+5.53%** en la tasa de conversión, elevando la probabilidad de éxito del grupo de control (9.83%) al grupo tratado (15.36%).
* **Modelo DiD (Panel):** El coeficiente de interacción econométrica (`treated:period`) demostró un impacto causal neto de **+938.94 unidades monetarias** en el saldo promedio de los clientes, con alta significancia estadística ($p < 0.001$).

---

## 🚀 5. Cómo Ejecutar el Proyecto

1. Clona el repositorio:
   ```bash
   git clone [https://github.com/tu-usuario/financial-campaign-causal-impact.git](https://github.com/tu-usuario/financial-campaign-causal-impact.git)
