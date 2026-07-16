# Projeto de Análise de Risco de Crédito

Este repositório contém o desenvolvimento completo de um modelo de machine learning para avaliação de risco de crédito. O projeto foca em identificar perfis de clientes com maior probabilidade de inadimplência, utilizando técnicas de processamento de dados, análise exploratória e modelagem preditiva.

## 📁 Estrutura do Projeto
O projeto foi organizado para garantir reprodutibilidade e clareza no fluxo de trabalho:

* `data/`: Armazena o dataset original (`german_credit_data.csv`).
* `notebooks/`: Contém os cadernos de desenvolvimento:
    * `EDA.ipynb`: Análise exploratória, tratamento de outliers e visualização de correlações.
    * `Modelagem.ipynb`: Desenvolvimento do modelo *Random Forest*, incluindo a comparação entre o modelo base e a versão tunada.
    * `Avaliacao_Modelo.ipynb`: Validação final da performance do modelo e análise de métricas.
* `models/`: Armazena os modelos treinados e serializados (`.pkl`).
* `processed/`: Contém os dados limpos e preparados para treino e teste.

## 🛠 Tecnologias e Bibliotecas
* **Linguagem:** Python
* **Manipulação de Dados:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn (Random Forest)
* **Persistência de Dados:** Joblib
* **Versionamento:** Git e GitHub

## 🚀 Etapas do Desenvolvimento
1. **Limpeza de Dados:** Tratamento de variáveis categóricas e preenchimento de valores ausentes para garantir a integridade do dataset.
2. **Análise Exploratória (EDA):** Identificação dos principais fatores que influenciam a concessão de crédito.
3. **Modelagem Preditiva:** Treinamento de algoritmos *Random Forest*, com foco em maximizar a capacidade de generalização do modelo.
4. **Avaliação:** Análise crítica dos resultados obtidos, garantindo que o modelo seja robusto para cenários reais de risco.

---
*Desenvolvido por Vinicius Torres.*
