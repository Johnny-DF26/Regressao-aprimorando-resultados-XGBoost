# Automotive Price Intelligence: Predição de Preços com XGBoost 🚗💨

Este projeto desenvolve uma solução de ponta a ponta para a precificação inteligente de veículos usados. Através de um pipeline robusto de Machine Learning, o objetivo é auxiliar uma concessionária a estimar valores de mercado com base em características técnicas e de consumo.

## 📌 Visão Geral do Projeto
O projeto aborda desde a extração e limpeza de dados até a exportação de um modelo pronto para produção. Foram aplicadas técnicas avançadas de regressão e interpretabilidade para garantir que o modelo não seja apenas preciso, mas também explicável para o negócio.

## 🛠️ Tecnologias e Ferramentas
*   **Linguagem:** Python 3.x
*   **Manipulação de Dados:** `Pandas`, `NumPy`
*   **Visualização:** `Seaborn`, `Matplotlib`
*   **Machine Learning:** `XGBoost` (Scikit-learn API & Native API), `Scikit-learn`
*   **Explicabilidade (XAI):** `SHAP` (SHAP Values)
*   **Persistência:** `Joblib`

## 🚀 Pipeline de Desenvolvimento

### 1. Limpeza e Tratamento de Dados
*   Tratamento de valores nulos e duplicados.
*   **Engenharia de Outliers:** Aplicação do método **IQR (Interquartile Range)** para remover ruídos nas variáveis de consumo, resultando em dados mais estáveis para o treinamento.
*   **Conversão de Unidades:** Engenharia de atributos para converter milhas por galão (MPG) para Km/L e valores monetários para Real (R$).

### 2. Análise Exploratória (EDA)
*   Identificação de correlações e distribuições.
*   Insights sobre a influência da potência do motor e do ano de fabricação na depreciação dos veículos.

### 3. Modelagem e Otimização
*   **Algoritmo:** XGBoost Regressor.
*   **Tuning de Hiperparâmetros:** Uso de `GridSearchCV` e busca iterativa manual para otimizar `learning_rate` (eta), `max_depth` e `subsample`.
*   **Validação Cruzada:** Implementação de `xgb.cv` com `early stopping` para evitar overfitting e garantir generalização.

### 4. Interpretabilidade com SHAP
Utilizamos **SHAP Values** para entender o "porquê" por trás das previsões. O gráfico de resumo (*Summary Plot*) revelou que variáveis como **Ano** e **Potência do Motor** são as principais alavancas de preço, enquanto o **Modelo** possui um peso categórico determinante.

## 📊 Resultados Finais
O modelo final apresentou uma performance excepcional no conjunto de teste:
*   **R² Score:** 0.9627 (Explica ~96% da variância dos preços)
*   **MAE (Erro Médio Absoluto):** $2,077.42
*   **RMSE (Raiz do Erro Quadrático Médio):** $2,926.45

## 📁 Estrutura de Arquivos
*   `modelo_regressor_xgboost_final.pkl`: Modelo treinado e serializado.
*   `readme_xgboost.json`: Metadados e métricas do modelo final.
*   `notebook.ipynb`: Workflow completo do projeto.

---
* Curso Alura
* Instrutor(a): Valquíria Alencar
* Desenvolvido com foco em alta performance e explicabilidade técnica.* 🚀
