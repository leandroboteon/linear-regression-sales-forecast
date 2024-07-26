# Regressão Linear: Avaliação de Investimentos em Marketing

## Introdução
Neste projeto, utilizando dados de uma empresa fictícia, nosso objetivo é desenvolver um modelo de regressão para estimar as vendas com base nos investimentos realizados em plataformas de publicidade online, como YouTube, Facebook e jornais.

Após o tratamento dos outliers, analisaremos de forma mais precisa a relação entre os investimentos em marketing e as vendas geradas. Isso resultará na criação de um modelo preditivo refinado, que oferecerá insights estratégicos para otimizar o retorno sobre o investimento.

Para acessar o projeto no Colab, clique [aqui](https://colab.research.google.com/github/leandroboteon/regressao-invest-mkt/blob/main/Regressao_para_MKT.ipynb).

## Tecnologias utilizadas
* `python`
* `pandas`
* `numpy`
* `matplotlib`
* `seaborn`
* `scikit-learn`
* `statsmodels`

## Estrutura do Projeto

O projeto está dividido nas seguintes etapas:
1. Análise Exploratória de Dados (EDA)
2. Pré-processamento de Dados
3. Análise Estatística com `statsmodels`
4. Construção do Modelo
5. Avaliação do ModeloConclusão
6. Conclusão


## Base de Dados

Utilizamos a base de dados "MKT.csv", que contém informações sobre investimentos em marketing e vendas. As colunas do dataset são:

- **youtube**: Investimento em publicidade no Youtube.
- **facebook**: Investimento em publicidade no Facebook.
- **newspaper**: Investimento em publicidade em jornais.
- **sales**: Valor das vendas.

## Metodologia

#### 1. Análise Exploratória de Dados (EDA)
Exploramos os dados do dataset "MKT.csv" para compreender melhor as variáveis e identificar problemas. Utilizamos a biblioteca Pandas para importar e manipular os dados, realizando cálculos estatísticos e visualizações para entender a distribuição dos dados.

<img width="213" alt="image" src="https://github.com/leandroboteon/regressao-invest-mkt/assets/167100723/91755b51-fcc0-4eda-9c2a-2019058e3daf">
<img width="275" alt="image" src="https://github.com/leandroboteon/regressao-invest-mkt/assets/167100723/194bc5be-9614-44bb-8d0b-47ae06b9a8cd">


Exploramos mais a fundo os dados, identificando relações entre as variáveis e descobrindo padrões relevantes. Utilizamos técnicas de visualização de dados e análises estatísticas para buscar possíveis correlações e identificar outliers.

<img width="311" alt="image" src="https://github.com/leandroboteon/regressao-invest-mkt/assets/167100723/57902692-a057-4ea0-bb09-408a77d80746">
<img width="291" alt="image" src="https://github.com/leandroboteon/regressao-invest-mkt/assets/167100723/e52715f6-32c1-4bb5-9ad2-875bd86f2da0">

#### 2. Pré-processamento de Dados

#### 2.1 Identificação e Tratamento de Outliers
- Inicialmente, utilizamos gráficos boxplot para identificar visualmente a presença de outliers na coluna 'newspaper'. Observamos também o histograma desta feature e constatamos que os dados não seguem uma distribuição normal. Portanto, optamos pelo método do intervalo interquartil (IQR) para identificar e tratar os outliers devido à sua robustez contra distribuições não normais.

   ![image](https://github.com/leandroboteon/linear-regression-sales-forecast/assets/167100723/a6af6f12-941a-4d34-ac7a-63d7d0b35114)

  ![image](https://github.com/leandroboteon/linear-regression-sales-forecast/assets/167100723/46fdee2d-8b4e-4888-9cba-7daa928f69f7)


- Após calcularmos os limites inferior e superior com base no IQR, filtramos o dataframe para excluir os dados que se encontravam fora desses limites. Como resultado do tratamento, removemos os outliers identificados.

   ![image](https://github.com/leandroboteon/linear-regression-sales-forecast/assets/167100723/ebcf019e-3ef1-4ff4-a0c8-8c10cf5b2504)

#### 2.2 Normalização dos Dados utilizando MinMaxScaler

Nesta etapa, aplicamos o MinMaxScaler para normalizar os dados, garantindo que todas as variáveis estejam na mesma escala e, assim, melhorar o desempenho dos modelos preditivos.

![image](https://github.com/user-attachments/assets/96d7ccc0-ba3a-44c9-8dab-ce6c5a24fbe5)

#### 3. Análise Estatística com `statsmodels`
Utilizamos a biblioteca statsmodels para realizar uma análise estatística detalhada. Esta etapa nos permitiu compreender melhor as relações entre os investimentos em marketing e as vendas, avaliando a significância das variáveis independentes no modelo de regressão.
Decidimos remover a variável `newspaper`, pois seu p-value está maior que 5%, indicando que não é estatisticamente significativa.

![image](https://github.com/user-attachments/assets/6d1d3dbf-e979-4a47-a8eb-d57cd3654f35)


#### 4. Construção do Modelo
Inicialmente os dados são divididos em conjuntos de treinamento e teste, com 70% dos dados reservados para treinamento e 30% para teste, utilizando a função `train_test_split` do `scikit-learn`. Em seguida, é importada a biblioteca necessária para realizar uma regressão linear utilizando `LinearRegression` do `sklearn.linear_model`.

   ![image](https://github.com/user-attachments/assets/16039141-62dd-4750-a4b6-01fbea288f95)


#### 5. Avaliação do Modelo
Avaliação do desempenho do modelo de regressão linear utilizando as seguintes métricas:

![image](https://github.com/user-attachments/assets/0b59a0da-216c-4249-8c2f-337c8c60a7e9)

Analisamos os seguintes aspectos:

- **Gráfico de Linha**: Comparação entre valores reais e predições, com a linha vermelha representando as predições e a linha azul representando os dados de teste.
  
![image](https://github.com/user-attachments/assets/c890ea56-9b6a-427b-88d2-7ee45ebb8504)

  
- **Gráfico de Dispersão**: Comparação entre valores reais e predições, onde os pontos estão próximos da linha vermelha ideal.
  
![image](https://github.com/user-attachments/assets/ccc41a92-eb62-4ac2-a437-5a195692c7f4)


- **Histograma dos Resíduos**: Mostra a distribuição dos resíduos com uma linha de tendência indicando a normalidade dos resíduos.
  
![image](https://github.com/user-attachments/assets/71c358f5-17c2-42df-8cc5-3a8dbc9fcc1a)
  

## 6. Conclusão

Neste projeto, desenvolvemos um modelo de regressão linear para prever o valor de vendas com base em investimentos em marketing.

- 📈 Identificamos uma forte correlação entre a variável `youtube` e as vendas (`sales`), indicando que os investimentos nesta plataforma têm um impacto positivo nas vendas.
- 🧪 A análise com `statsmodels` revelou que a variável `newspaper` não é estatisticamente significativa, com um p-value superior a 5%. Portanto, a removemos do modelo. As variáveis `youtube` e `facebook` mostraram-se mais relevantes para o aumento das vendas.
- 📊 As métricas de desempenho do modelo foram:
  - **R²**: 0.9147
  - **MAE**: 0.0477
  - **MSE**: 0.0034
  - **RMSE**: 0.0585

  Esses resultados demonstram um bom ajuste do modelo aos dados.
- 🔍 Observando o gráfico de valores, notamos que o modelo prevê com boa precisão. O gráfico de dispersão entre valores reais e preditos mostra que os pontos estão próximos da linha ideal, e o histograma dos resíduos indica uma distribuição normal.
