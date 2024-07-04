# Modelo de Regressão para Avaliar Investimentos em Marketing

## Introdução
Neste projeto, utilizando dados de uma empresa fictícia, nosso objetivo é desenvolver um modelo de regressão para estimar as vendas com base nos investimentos realizados em plataformas de publicidade online, como YouTube, Facebook e jornais.

Após o tratamento dos outliers, analisaremos de forma mais precisa a relação entre os investimentos em marketing e as vendas geradas. Isso resultará na criação de um modelo preditivo refinado, que oferecerá insights estratégicos para otimizar o retorno sobre o investimento.

Para acessar o projeto no Colab, clique [aqui](https://colab.research.google.com/github/leandroboteon/regressao-invest-mkt/blob/main/Regressao_para_MKT.ipynb).

## Objetivos do Projeto

- **Identificar padrões e correlações entre as variáveis.**
- **Identificar e tratar outliers.**
- **Construir um modelo de regressão linear para prever vendas com base em novos investimentos.**
- **Fornecer previsões de vendas com base em diferentes níveis de investimento.**

## Tecnologias utilizadas
* `python`
* `pandas`
* `numpy`
* `matplotlib`
* `seaborn`
* `scikit-learn`

## Estrutura do Projeto

O projeto está dividido nas seguintes etapas:

1. **Análise Descritiva**
2. **Análise Exploratória**
3. **Identificação e Tratamento de Outliers**
4. **Construção do Modelo de Regressão**
5. **Predições**
6. **Conclusão**

## Base de Dados

Utilizamos a base de dados "MKT.csv", que contém informações sobre investimentos em marketing e vendas. As colunas do dataset são:

- **youtube**: Investimento em publicidade no Youtube.
- **facebook**: Investimento em publicidade no Facebook.
- **newspaper**: Investimento em publicidade em jornais.
- **sales**: Valor das vendas.

## Metodologia

#### 1. Análise Descritiva
Exploramos os dados do dataset "MKT.csv" para compreender melhor as variáveis e identificar problemas. Utilizamos a biblioteca Pandas para importar e manipular os dados, realizando cálculos estatísticos e visualizações para entender a distribuição dos dados.

<img width="213" alt="image" src="https://github.com/leandroboteon/regressao-invest-mkt/assets/167100723/91755b51-fcc0-4eda-9c2a-2019058e3daf">
<img width="275" alt="image" src="https://github.com/leandroboteon/regressao-invest-mkt/assets/167100723/194bc5be-9614-44bb-8d0b-47ae06b9a8cd">


#### 2. Análise Exploratória
Exploramos mais a fundo os dados, identificando relações entre as variáveis e descobrindo padrões relevantes. Utilizamos técnicas de visualização de dados e análises estatísticas para buscar possíveis correlações e identificar outliers.

<img width="311" alt="image" src="https://github.com/leandroboteon/regressao-invest-mkt/assets/167100723/57902692-a057-4ea0-bb09-408a77d80746">
<img width="291" alt="image" src="https://github.com/leandroboteon/regressao-invest-mkt/assets/167100723/e52715f6-32c1-4bb5-9ad2-875bd86f2da0">

#### 3. Identificação e Tratamento de Outliers
- Inicialmente, utilizamos gráficos boxplot para identificar visualmente a presença de outliers na coluna 'newspaper'. Observamos também o histograma desta feature e constatamos que os dados não seguem uma distribuição normal. Portanto, optamos pelo método do intervalo interquartil (IQR) para identificar e tratar os outliers devido à sua robustez contra distribuições não normais.

   ![image](https://github.com/leandroboteon/linear-regression-sales-forecast/assets/167100723/a6af6f12-941a-4d34-ac7a-63d7d0b35114)

  ![image](https://github.com/leandroboteon/linear-regression-sales-forecast/assets/167100723/46fdee2d-8b4e-4888-9cba-7daa928f69f7)


- Após calcularmos os limites inferior e superior com base no IQR, filtramos o dataframe para excluir os dados que se encontravam fora desses limites. Como resultado do tratamento, removemos os outliers identificados.

   ![image](https://github.com/leandroboteon/linear-regression-sales-forecast/assets/167100723/ebcf019e-3ef1-4ff4-a0c8-8c10cf5b2504)

- Para validar o impacto do tratamento, geramos um novo gráfico boxplot e constatamos que não há mais outliers presentes, indicando que os dados agora estão dentro dos limites da distribuição dos dados concentrados.

  ![image](https://github.com/leandroboteon/linear-regression-sales-forecast/assets/167100723/56b0afcc-26b5-4f99-955a-83f67948c06e)


#### 4. Construção do Modelo de Regressão
- Inicialmente os dados são divididos em conjuntos de treinamento e teste, com 70% dos dados reservados para treinamento e 30% para teste, utilizando a função `train_test_split` do `scikit-learn`. Em seguida, é importada a biblioteca necessária para realizar uma regressão linear utilizando `LinearRegression` do `sklearn.linear_model`.

  ![image](https://github.com/leandroboteon/linear-regression-sales-forecast/assets/167100723/e330a18b-6e5c-4cb7-bb07-ffd294724c66)


- Um modelo de regressão linear é definido e inicializado com *lm = LinearRegression()*. Posteriormente, o modelo é treinado com os dados de treinamento utilizando *lm.fit(X_train, Y_train)*.

  ![image](https://github.com/leandroboteon/linear-regression-sales-forecast/assets/167100723/9d3376b9-096d-4bcf-b3a2-7f97c949a467)


- Após o treinamento, são feitas predições utilizando os dados de teste com *Y_pred = lm.predict(X_test)*. Para visualizar a eficácia do modelo, os valores reais de vendas *(Y_test.values)* e as predições *(Y_pred)* são comparados em um gráfico. Neste gráfico, os valores reais são representados pela linha azul e as predições pelo linha vermelha, permitindo uma avaliação visual da precisão do modelo na previsão de vendas.

  ![image](https://github.com/leandroboteon/linear-regression-sales-forecast/assets/167100723/170df5a3-7424-4df2-9075-a15f9634db06)


#### 5. Métrica para avaliação da eficácia
Para avaliar a eficácia do modelo construído, utilizamos o coeficiente de determinação (R-quadrado). O valor obtido para esta métrica foi de 0.91, indicando que o modelo explica cerca de 91% da variabilidade dos dados de vendas com base nos investimentos em plataformas de publicidade online (Youtube, Facebook e jornais).

![image](https://github.com/leandroboteon/linear-regression-sales-forecast/assets/167100723/72f88c3b-c663-4ae4-9abf-27327030f40a)


#### 6. Predições
Utilizamos o modelo treinado para prever o valor de vendas com base em novos dados de investimento fornecidos pelo usuário. Obtivemos um valor de vendas de 6.21 para as seguintes entradas: *YouTube = 20*, *Facebook = 10*, e *Newspaper = 5*.

![image](https://github.com/leandroboteon/linear-regression-sales-forecast/assets/167100723/2d8f865b-6b2e-40e5-895a-b66ccbad626d)


## Resultados
Após a análise e construção do modelo, destacamos os principais resultados alcançados:
- Identificamos uma correlação significativa entre os investimentos no Youtube e as vendas (correlação de 0.78), indicando que aumentos nos investimentos nesta plataforma estão associados a aumentos nas vendas.
- Durante a análise, identificamos outliers nos dados de investimentos em newspaper e aplicamos técnicas de tratamento para removê-los, melhorando assim a robustez do modelo.
- O modelo de regressão linear treinado apresentou um coeficiente de determinação (R²) de 0.91, demonstrando sua eficácia em explicar a variabilidade dos dados de vendas com base nos investimentos em marketing.

## Conclusão
Neste projeto, exploramos e analisamos os dados de investimentos em marketing para construir um modelo de regressão linear que prevê o valor de vendas. Durante o processo, identificamos outliers nos investimentos em newspaper e aplicamos técnicas para removê-los, o que aprimorou a qualidade das previsões do modelo.

📈 Identificamos uma forte correlação entre os investimentos no Youtube e as vendas (correlação de 0.78), destacando que aumentos nos investimentos nesta plataforma estão associados a aumentos nas vendas.

📊 O modelo de regressão linear treinado demonstrou um bom desempenho, com um coeficiente de determinação (R²) de 0.91. Isso significa que aproximadamente 91% da variabilidade das vendas pode ser explicada pelos investimentos em marketing analisados.

⚙ Para futuras melhorias, recomenda-se a avaliação de outras métricas de desempenho do modelo, além do R-quadrado. Por exemplo, métricas como o erro médio absoluto (MAE) e o erro médio quadrático (MSE) podem fornecer uma visão mais detalhada da precisão das previsões e da robustez do modelo em diferentes cenários.

🚀 Em suma, o modelo desenvolvido neste projeto não apenas fornece insights sobre a relação entre investimentos em marketing e vendas, mas também serve como uma ferramenta prática para tomada de decisões estratégicas. Ao utilizar previsões baseadas em dados, a empresa pode otimizar seus investimentos em marketing e maximizar o retorno sobre esses investimentos
