# Continuação do projeto da ALURA: TelecomX_BR


---

# Análise de Evasão (Churn) de Clientes em Telecomunicações

## Visão Geral do Projeto

Este projeto tem como objetivo principal analisar e prever a evasão (churn) de clientes em uma empresa de telecomunicações. Utilizando técnicas de preparação de dados, análise exploratória e modelos de Machine Learning, buscamos identificar os principais fatores que levam os clientes a cancelar seus serviços e propor estratégias de retenção eficazes.

## Objetivos Específicos

* **Preparação de Dados:** Limpar e transformar os dados brutos, tornando-os adequados para análise e modelagem.
* **Análise de Correlação:** Identificar relações entre as variáveis do dataset e a variável alvo (evasão).
* **Modelagem Preditiva:** Desenvolver e avaliar modelos de Machine Learning capazes de prever a probabilidade de um cliente evadir.
* **Interpretação de Modelos:** Entender quais características dos clientes são mais relevantes para a previsão de evasão.
* **Recomendações:** Propor estratégias de negócios baseadas nos insights obtidos para reduzir a taxa de churn.

## Estrutura do Projeto

O projeto é dividido nas seguintes etapas principais:

### A) Preparação dos Dados

1.  **Remoção de Colunas Irrelevantes:** Eliminação de identificadores únicos (como `customerID`) que não contribuem para a previsão.
2.  **Encoding de Variáveis Categóricas:** Transformação de dados textuais em formato numérico, utilizando `OneHotEncoder` para variáveis categóricas, tornando-as compatíveis com algoritmos de Machine Learning. Para mais detalhes sobre métodos de codificação, consulte o artigo da Alura: [get_dummies vs OneHotEncoder](https://www.alura.com.br/artigos/get-dummies-vs-onehotencoder-qual-metodo-escolher).
3.  **Verificação da Proporção de Evasão:** Análise do desequilíbrio entre as classes de clientes que evadiram e os que permaneceram, utilizando `value_counts()` do Pandas: [pandas.DataFrame.value_counts](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.value_counts.html).
4.  **Balanceamento de Classes (Opcional):** Consideração de técnicas como `oversampling` (e.g., SMOTE) ou `undersampling` se o desequilíbrio de classes for muito acentuado e afetar o desempenho do modelo (não aplicado na baseline).
5.  **Normalização/Padronização (Condicional):** Avaliação e aplicação de padronização (`StandardScaler`) em variáveis numéricas, especialmente para modelos sensíveis à escala como Regressão Logística e KNN. Modelos baseados em árvore (Random Forest) geralmente não exigem essa etapa. Mais informações sobre padronização/normalização: [Padronização Normalização Dados Machine Learning](https://medium.com/ipnet-growth-partner/padronizacao-normalizacao-dados-machine-learning-f8f29246c12).

### B) Correlação e Seleção de Variáveis

1.  **Análise de Correlação:** Visualização da matriz de correlação entre variáveis numéricas, incluindo a variável alvo `Churn`, para identificar as relações mais fortes.
2.  **Análises Direcionadas:** Gráficos (Boxplots) para explorar a relação entre `Tempo de Contrato (Tenure)` vs. `Evasão` e `Total Gasto (TotalCharges)` vs. `Evasão`.

### C) Modelagem Preditiva

1.  **Separação de Dados:** Divisão do dataset em conjuntos de treino e teste (e.g., 80% treino, 20% teste) para validação dos modelos.
2.  **Criação de Modelos:** Implementação de pelo menos dois modelos de classificação:
    * **Regressão Logística:** Um modelo linear que exige padronização das features.
    * **Random Forest Classifier:** Um modelo de ensemble baseado em árvores que não é sensível à escala dos dados.
3.  **Avaliação dos Modelos:** Análise do desempenho de cada modelo utilizando métricas essenciais:
    * **Acurácia**
    * **Precisão**
    * **Recall**
    * **F1-score**
    * **Matriz de Confusão**
    Uma análise crítica é realizada para comparar os modelos, identificar possíveis casos de *overfitting* ou *underfitting* e discutir as causas e ajustes.

### D) Interpretação e Conclusões

1.  **Análise de Importância das Variáveis:** Investigação dos principais fatores que contribuem para a previsão de evasão. Para Regressão Logística, são analisados os coeficientes; para Random Forest, a importância das features intrínseca ao modelo.
2.  **Conclusão e Recomendações:** Um relatório detalhado que destaca os fatores mais influentes na evasão e propõe estratégias de retenção de clientes baseadas nos resultados obtidos.


---
