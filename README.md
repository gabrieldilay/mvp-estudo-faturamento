# 📊 Previsão de Faturamento - Rossmann Store Sales

Este repositório contém o **MVP (Minimum Viable Project)** desenvolvido para a pós-graduação em Data Science & Analytics, cujo objetivo foi aplicar técnicas de aprendizado de máquina e séries temporais para prever o faturamento da rede de lojas Rossmann.  

O projeto cobre desde a preparação e exploração dos dados até a avaliação de diferentes algoritmos, análise de variáveis relevantes e consolidação de previsões em níveis diário, mensal e semestral.

---

## 🚀 Objetivo

Construir e avaliar modelos capazes de prever o faturamento das lojas Rossmann, identificando os fatores que mais impactam as vendas e fornecendo previsões confiáveis para apoiar a **tomada de decisão estratégica**.

---

## 📂 Estrutura do Projeto

- [`notebook.ipynb` no Google Colab](https://colab.research.google.com/drive/1ukgaX1b5_F6I6mL2NxgOv4EL4HLBX5J9?usp=sharing) → Notebook principal com todo o fluxo do MVP.  
- `train.zip`, `test.csv`, `store.csv` → Dados utilizados (disponíveis no repositório).  
- `xgb_diario_tunado.pkl` → Modelo final salvo (XGBoost diário tunado).  
- `xgb_importances_gain.csv` → Importância das variáveis extraída do modelo.  

---


## 🛠️ Metodologia

O trabalho seguiu as seguintes etapas:

1. **Exploração e Preparação de Dados**  
   - Tratamento de valores ausentes.  
   - Criação de variáveis de calendário (ano, mês, dia da semana, feriados, finais de semana).  
   - Encoding de variáveis categóricas (`StateHoliday`).  
   - Engenharia de atributos com defasagens e médias móveis (lags e rolling).  

2. **Modelagem**  
   - Baselines: Regressão Linear e Naive sazonal.  
   - Supervisionados: Ridge, Árvore de Regressão, Random Forest, KNN, XGBoost.  
   - Séries Temporais: ARIMA, SARIMA.  
   - Comparação entre granularidade diária e mensal.  
   - Otimização de hiperparâmetros no XGBoost com RandomizedSearchCV.  

3. **Avaliação**  
   - Métricas: MAE, RMSE, MAPE e R².  
   - Análise de overfitting/underfitting.  
   - Importância de variáveis (gain do XGBoost e análise de promoções, feriados e clientes).  

---

## 📈 Principais Resultados

- **XGBoost Tunado (diário)** → melhor desempenho granular:  
  - MAE: ~350 mil  
  - RMSE: ~507 mil  
  - MAPE: **5,55%**  
  - R²: **0,97**

- **Regressão Ridge (mensal)** → melhor desempenho consolidado:  
  - MAPE: **5,4%**  
  - Erro semestral: **2,37%**  

- **Previsões consolidadas**:  
  - Semestre (6 meses): ~**R$ 1,12 bi**  
  - Ano (12 meses): ~**R$ 2,34 bi**

- **Variáveis mais impactantes**:  
  - `Customers` → maior fator explicativo.  
  - `Promo` → aumento médio de +38,8% nas vendas.  
  - `CompetitionDistance` → impacto da concorrência.  
  - Fatores de calendário (fins de semana +18,3%, feriados -3,9%).  

---

## 📌 Conclusões

-Modelos baseados em árvores (XGBoost, Random Forest) são mais eficazes para previsões granulares de faturamento.
-A regressão regularizada (Ridge) se mostrou robusta para análises agregadas (mensais/semestrais).
-Promoções e número de clientes são os principais drivers de crescimento.
-O MVP cumpre todos os requisitos acadêmicos e também se apresenta como uma solução aplicável ao mercado, podendo ser integrado em dashboards (ex.: Power BI).
-Os resultados demonstram o potencial do Machine Learning aplicado a negócios reais, apoiando decisões em pricing, promoções e expansão de rede.

---

## 👩‍💻 Autor

**Gabriel Dilay de Oliveira**  
Pós-graduação em Data Science & Analytics  

