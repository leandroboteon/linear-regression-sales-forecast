# Construindo um Modelo de Regressão para Marketing

## Visão Geral

Este projeto tem como objetivo construir um modelo de regressão para prever o valor de vendas com base em investimentos em plataformas de publicidade online, como Youtube, Facebook e jornais. O projeto analisa a relação entre os investimentos em marketing e as vendas geradas, criando um modelo preditivo que auxilia na tomada de decisões estratégicas para otimizar o retorno sobre o investimento.

## Objetivos do Projeto

1. **Analisar os dados de investimento em marketing e vendas.**
2. **Identificar padrões e correlações entre as variáveis.**
3. **Construir um modelo de regressão linear para prever vendas com base em novos investimentos.**
4. **Avaliar o modelo.**
5. **Fornecer previsões de vendas com base em diferentes níveis de investimento.**

## Tecnologias utilizadas
* python
* pandas
* numpy
* scikit-learn
* matplotlib
* seaborn

## Estrutura do Projeto

O projeto está dividido nas seguintes etapas:

1. **Análise Descritiva**
2. **Análise Exploratória**
3. **Construção do Modelo de Regressão**
4. **Predições**
5. **Conclusão**

## Base de Dados

Utilizamos a base de dados "MKT.csv", que contém informações sobre investimentos em marketing e vendas. As colunas do dataset são:

- **youtube**: Investimento em publicidade no Youtube.
- **facebook**: Investimento em publicidade no Facebook.
- **newspaper**: Investimento em publicidade em jornais.
- **sales**: Valor das vendas.

## Metodologia

#### Etapa 01: Análise Descritiva
Exploramos os dados do dataset "MKT.csv" para compreender melhor as variáveis e identificar problemas. Utilizamos a biblioteca Pandas para importar e manipular os dados, realizando cálculos estatísticos e visualizações para entender a distribuição dos dados.

<img width="213" alt="image" src="https://github.com/leandroboteon/regressao-invest-mkt/assets/167100723/91755b51-fcc0-4eda-9c2a-2019058e3daf">
<img width="275" alt="image" src="https://github.com/leandroboteon/regressao-invest-mkt/assets/167100723/194bc5be-9614-44bb-8d0b-47ae06b9a8cd">


#### Etapa 02: Análise Exploratória
Exploramos mais a fundo os dados, identificando relações entre as variáveis e descobrindo padrões relevantes. Utilizamos técnicas de visualização de dados e análises estatísticas para buscar possíveis correlações e identificar outliers.

<img width="311" alt="image" src="https://github.com/leandroboteon/regressao-invest-mkt/assets/167100723/57902692-a057-4ea0-bb09-408a77d80746">
<img width="291" alt="image" src="https://github.com/leandroboteon/regressao-invest-mkt/assets/167100723/e52715f6-32c1-4bb5-9ad2-875bd86f2da0">


#### Etapa 03: Construção do Modelo de Regressão
Construímos e treinamos o modelo de regressão linear utilizando os dados limpos. Dividimos os dados em conjuntos de treinamento e teste, escalamos as features e treinamos o modelo. Avaliamos o desempenho do modelo utilizando a métrica do R².

<img width="510" alt="image" src="https://github.com/leandroboteon/regressao-invest-mkt/assets/167100723/7ab99def-151f-42f2-8f11-f030a4c998c6">


#### Etapa 04: Predições
Utilizamos o modelo treinado para prever o valor de vendas com base em novos dados de investimento fornecidos pelo usuário.

<img width="498" alt="image" src="https://github.com/leandroboteon/regressao-invest-mkt/assets/167100723/6a11f5e1-4408-45d8-8c79-9c153ee881ed">


## Resultados
Após a análise e construção do modelo, os principais resultados foram:
* Uma forte correlação entre os investimentos no Youtube e as vendas (0.78)
* Outliers identificados em newspaper
* Um modelo de regressão linear treinado com um R² de 0.8

## Conclusão
Neste projeto, exploramos e analisamos os dados de investimentos em marketing para construir um modelo de regressão linear que prevê o valor de vendas. Identificamos outliers, exploramos correlações entre variáveis e construímos um modelo preditivo. O modelo foi avaliado e utilizado para fazer previsões com novos dados fornecidos pelo usuário, ajudando a empresa a tomar decisões mais informadas sobre seus investimentos em marketing.
