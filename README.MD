# 🎯 Projeto de Análise de Risco de Crédito

O projeto desenvolve uma solução de **classificação supervisionada para análise de risco de crédito**, utilizando técnicas de Machine Learning para classificar clientes entre **bom (`good`) e mau risco de crédito (`bad`)**.

O desenvolvimento contempla as principais etapas de um projeto de Machine Learning, incluindo **análise exploratória, preparação dos dados, engenharia de atributos, treinamento, otimização de hiperparâmetros, validação cruzada e avaliação do modelo**.

Além da otimização do modelo, foi realizado o ajuste do **classification threshold**, buscando melhorar o equilíbrio entre Precision e Recall na identificação de clientes classificados como `bad`.

---

## 📂 Estrutura

```text
Credit_Risk_Project/
│
├── data/
│   └── german_credit_data.csv       # Dataset original utilizado
│
├── notebooks/
│   ├── 01_EDA.ipynb                 # Análise Exploratória dos Dados
│   ├── 02_Modelagem.ipynb           # Preparação, treinamento e otimização
│   └── 03_Avaliacao_Modelo.ipynb    # Avaliação e otimização do threshold
│
├── models/
│   ├── random_forest_baseline.pkl   # Modelo baseline
│   └── random_forest_tuned.pkl      # Modelo otimizado
│
├── processed/
│   ├── X_train.pkl                  # Variáveis preditoras de treino
│   ├── y_train.pkl                  # Variável alvo de treino
│   ├── X_test.pkl                   # Variáveis preditoras de teste
│   └── y_test.pkl                   # Variável alvo de teste
│
└── README.md
```

---

# 🏗️ Desenvolvimento do Projeto

O projeto foi dividido em três etapas principais:

## 📊 1. Análise Exploratória dos Dados

**Arquivo:** `notebooks/01_EDA.ipynb`

Nesta etapa foi realizada a exploração inicial do dataset com o objetivo de compreender sua estrutura, distribuição e características antes da modelagem.

Principais atividades:

* Inspeção inicial do dataset;
* Análise dos tipos e estrutura das variáveis;
* Estatísticas descritivas;
* Análise da distribuição das variáveis;
* Identificação de valores ausentes;
* Análise de outliers;
* Análise de variáveis categóricas;
* Análise da distribuição da variável alvo;
* Análise das relações entre as características dos clientes e o risco de crédito;
* Visualização dos dados e das principais relações encontradas.

A etapa de EDA serviu como base para definir os procedimentos de preparação e transformação utilizados posteriormente na modelagem.

---

## 🤖 2. Modelagem Preditiva & Otimização

**Arquivo:** `notebooks/02_Modelagem.ipynb`

Nesta etapa foram realizados o tratamento final dos dados, treinamento e otimização do modelo de Machine Learning.

### Preparação dos Dados

Foram realizadas as transformações necessárias para tornar os dados adequados ao algoritmo, incluindo:

* Tratamento de valores ausentes;
* Preenchimento das categorias ausentes;
* Codificação das variáveis categóricas utilizando **One-Hot Encoding**;
* Separação entre variáveis preditoras (`X`) e variável alvo (`y`);
* Divisão dos dados em conjuntos de treino e teste.

### Modelo

Foi utilizado o **Random Forest Classifier** para realizar a classificação binária entre `good` e `bad`.

Inicialmente foi desenvolvido um **modelo baseline**, utilizado como referência para o processo de otimização.

### Hyperparameter Tuning

A otimização dos hiperparâmetros foi realizada utilizando `RandomizedSearchCV` com **5-Fold Cross-Validation**.

Foram avaliados diferentes valores para parâmetros como:

* `n_estimators`;
* `max_depth`;
* `min_samples_split`;
* `min_samples_leaf`;
* `max_features`;
* `class_weight`.

O **Recall** foi utilizado como métrica principal durante a busca, devido à importância de identificar corretamente a classe `bad`.

Também foi utilizado `class_weight="balanced"` para considerar o desbalanceamento existente entre as classes.

### 💾 Persistência dos Modelos

Após o treinamento, os modelos foram serializados utilizando **Joblib**, permitindo que fossem posteriormente carregados para a etapa de avaliação sem a necessidade de realizar novamente o treinamento.

---

# 🛡️ 3. Avaliação do Modelo & Otimização do Threshold

**Arquivo:** `notebooks/03_Avaliacao_Modelo.ipynb`

Nesta etapa foi realizada a avaliação dos modelos desenvolvidos, incluindo a comparação entre o **Random Forest baseline** e o **modelo otimizado**.

Foram utilizadas diferentes métricas para avaliar o desempenho da classificação:

* Accuracy;
* Precision;
* Recall;
* F1-Score;
* ROC-AUC.

Também foram utilizadas ferramentas de análise visual, como:

* Matriz de Confusão;
* Curva ROC;
* Curva Precision-Recall.

---

## 🎚️ Otimização do Classification Threshold

Além da otimização dos hiperparâmetros, foi realizada uma etapa de otimização do **limiar de classificação (*classification threshold*)**.

O threshold padrão de `0.50` foi substituído por um valor definido a partir da análise da relação entre **Precision e Recall**.

Para realizar essa otimização, foram obtidas probabilidades utilizando **validação cruzada no conjunto de treinamento**, através de `cross_val_predict`.

O threshold que apresentou o maior **F1-Score** foi selecionado e posteriormente aplicado ao conjunto de teste.

---

## 🔎 Interpretabilidade com SHAP

Para aumentar a interpretabilidade do modelo, foi utilizada a técnica **SHAP (SHapley Additive exPlanations)**.

O SHAP permite identificar a contribuição de cada variável para as previsões do modelo, possibilitando analisar tanto o comportamento global quanto as decisões individuais.

Foram utilizadas:

* **Análise global:** identificação das variáveis que apresentam maior influência nas previsões;
* **Análise individual:** identificação de como cada característica contribuiu para aumentar ou diminuir a previsão de risco de um determinado cliente.

Essa etapa permite compreender melhor como o modelo chegou às suas decisões, tornando os resultados mais transparentes e interpretáveis.

---

# 🚀 Roadmap e Melhorias Futuras

O projeto pode ser expandido futuramente com novas técnicas de **Data Science e Machine Learning**.

### 🧠 Data Science & Machine Learning

* **Balanceamento de Dados:** testar técnicas como SMOTE e comparar seu impacto nas métricas de classificação.
* **Otimização baseada em custos:** definir uma função de custo que represente financeiramente Falsos Positivos e Falsos Negativos e utilizar esse critério para selecionar o threshold.
* **Modelos adicionais:** comparar o Random Forest com outros algoritmos de classificação, como Logistic Regression, XGBoost e Gradient Boosting.


---

## 📞 Contato

* **Desenvolvedor:** Vinicius Torres
* **GitHub:** [VincTorres](https://github.com/VincTorres)

