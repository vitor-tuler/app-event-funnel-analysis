# 📱 Análise de Funil de Eventos de Aplicativo

## 📋 Descrição
Projeto de limpeza, pré-processamento e análise exploratória de logs de eventos de um aplicativo móvel/web. O foco principal é preparar os dados de eventos de usuários para análise de conversão através do funil: **MainScreenAppear → Tutorial → OffersScreenAppear → CartScreenAppear → PaymentScreenSuccessful**.

Este projeto trabalha com dados experimentais (A/B test) contendo mais de 7.500 usuários únicos e seus eventos registrados ao longo de 2 meses.

## 📊 Dataset
- `logs_exp_us.csv` - Logs brutos de eventos do aplicativo
  - **Usuários**: 7.551 únicos
  - **Eventos**: Múltiplos eventos de interação (5 tipos principais)
  - **Período**: ~2 meses de dados
  - **Formato**: Tab-separated values com timestamp, ID do usuário, tipo de evento e grupo de experimento

## 🔄 Funil de Conversão
```
MainScreenAppear 
    ↓
Tutorial 
    ↓
OffersScreenAppear 
    ↓
CartScreenAppear 
    ↓
PaymentScreenSuccessful
```

## 🚀 Como Executar
```bash
pip install -r requirements.txt
jupyter notebook analysis.ipynb
```

## 🔧 Etapas de Processamento
- **Renomeação de colunas**: Padronização de nomes (EventName → event_name, etc.)
- **Tratamento de valores faltantes**: Remoção de linhas incompletas
- **Remoção de duplicatas**: Eliminação de eventos duplicados
- **Conversão de tipos**: Otimização de tipos de dados (category, int16, datetime)
- **Feature engineering**: Extração de features temporais (data, hora)
- **Análise exploratória**: Distribuição de eventos por hora, dia e grupo

## 📈 Insights Incluídos
- Distribuição de eventos por hora do dia
- Distribuição de eventos por data
- Comparação de volumes entre períodos
- Análise de usuários únicos por evento
- Média de eventos por usuário

## 🛠️ Tecnologias
- **Python** 3.8+
- **pandas** - Manipulação de dados
- **numpy** - Operações numéricas
- **matplotlib**, **seaborn** - Visualizações
- **scipy**, **statsmodels** - Análise estatística e testes de hipótese
- **plotly** - Visualizações interativas
