# Previsão de Criptomoedas com LSTM

Este projeto é um estudo sobre a previsão de preços de criptomoedas utilizando redes neurais LSTM (Long Short-Term Memory). O projeto analisa três criptomoedas principais: Bitcoin (BTC), Ethereum (ETH) e Solana (SOL), com foco em diferentes abordagens de modelagem e análise de dados.

## 📊 Estrutura do Projeto

```
├── data/
│   ├── processed/         # Dados processados e transformados
│   └── raw/              # Dados brutos baixados do Yahoo Finance
├── notebooks/
│   ├── BTC/             # Notebooks relacionados ao Bitcoin
│   ├── ETH/             # Notebooks relacionados ao Ethereum
│   └── SOL/             # Notebooks relacionados à Solana
└── requirements.txt      # Dependências do projeto
```

## 🔍 Abordagens de Modelagem

O projeto implementa diferentes abordagens para a previsão de preços:

1. **Modelo Univariado**

    - Utiliza apenas o preço de fechamento (Close) para previsão
    - Implementado com diferentes janelas temporais (7, 14, 30 dias)
    - Implementado com diferentes splits (5, 10)
    - Inclui variações com dados completos e dados cortados

2. **Modelo Multivariado**

    - Utiliza múltiplas features (High, Low, Open, Volume) e em alguns casos (crypto)
    - Implementado com diferentes janelas temporais (7, 14, 30 dias)
    - Implementado com diferentes splits (5, 10)
    - Inclui variações com dados completos e dados cortados

3. **Modelo com Análise de Sentimento**
    - Incorpora tendências da palavra "crypto" nos dados
    - Analisa o impacto de eventos externos (ex: eleição de Trump)

## 🛠️ Características Técnicas

### Preparação dos Dados

-   Extração de dados via Yahoo Finance API
-   Limpeza e normalização dos dados
-   Criação de diferentes conjuntos de dados (raw, all, cropped)
-   Geração de features de lag para análise temporal
-   Agregação da tendências da palavra "crypto" nos dados

### Modelagem LSTM

-   Arquitetura: LSTM com camadas duplas
-   Dropout para regularização
-   Early Stopping para evitar overfitting
-   Grid Search para otimização de hiperparâmetros

### Hiperparâmetros Otimizados

-   Número de neurônios: [32, 64, 96]
-   Taxa de dropout: [0.1, 0.2, 0.3]
-   Batch size: [16, 32]
-   Épocas: [50, 100]

### Métricas de Avaliação

-   RMSE (Root Mean Square Error)
-   MAE (Mean Absolute Error)
-   MAPE (Mean Absolute Percentage Error)
-   R² Score

## 📈 Análise de Eventos

O projeto inclui análise do impacto de eventos significativos no mercado de criptomoedas, como:

-   Eleição de Donald Trump (5 de novembro de 2024)
-   Tendências históricas do mercado

## 🚀 Como Usar

1. Clone o repositório
2. Instale as dependências:
    ```bash
    pip install -r requirements.txt
    ```
3. Execute os notebooks na ordem:
    - 01*data*\*\_etl.ipynb: Extração e transformação dos dados
    - 02*data*\*\_eda.ipynb: Análise exploratória
    - 03*lstm*\*\_univariate.ipynb: Modelo univariado
    - 04*lstm*\*\_multivariate.ipynb: Modelo multivariado

## 📦 Dependências Principais

-   pandas
-   numpy
-   matplotlib
-   scikit-learn
-   keras
-   tensorflow
-   yfinance

## 🎯 Resultados

O projeto demonstra diferentes níveis de acurácia dependendo da abordagem:

-   Modelos univariados tendem a ter melhor performance em períodos estáveis
-   Modelos multivariados capturam melhor as mudanças bruscas de mercado
-   A inclusão de análise de sentimento melhora a capacidade preditiva em eventos significativos
