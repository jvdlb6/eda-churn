# 📊 Exploratory Data Analysis (EDA) - Análise de Churn de Clientes

Projeto completo de **Análise Exploratória de Dados (EDA)** com análise estatística de churn de clientes utilizando **Python**, **Pandas**, **NumPy** e **SciPy**.

---

## 🎯 Objetivos do Projeto

✅ **Fase 1 - Preparação de Dados:**

- Carregamento e inspeção de múltiplos datasets (Customers, Services, Contracts)
- Transformações de tipos de dados e renomeação de colunas
- Unificação de datasets via merge
- Detecção e tratamento de valores ausentes

✅ **Fase 2 - Análise Univariada:**

- Distribuições de frequência (Churn, Contract Type, Tenure)
- Medidas de posição (média, mediana, moda)
- Medidas de dispersão (desvio padrão, coeficiente de variação)
- Visualizações com histogramas e gráficos de barras

✅ **Fase 3 - Análise Bivariada:**

- Tabelas de contingência (crosstabs)
- Testes de hipótese Chi-Square para variáveis categóricas
- Correlação de Pearson e Spearman para variáveis numéricas
- Análise de scatter plots

✅ **Fase 4 - Detecção de Outliers:**

- Método de Tukey (IQR)
- Z-score para distribuição normal
- Box plots agrupados

✅ **Fase 5 - Relatórios Automatizados:**

- Geração de análises visuais com SweetViz


## 📊 Principais Descobertas

### Hipótese 1: Faixa Etária (65+) ↔ Churn

- **χ² = 159.43** | **p-value ≈ 0**
- ✅ **CONFIRMADA** - Forte correlação significativa

### Hipótese 2: Tipo de Contrato (Mensal) ↔ Churn

- **χ² ≈ 4180** | **p-value ≈ 0**
- ✅ **CONFIRMADA** - Correlação muito forte
- 88% dos clientes que cancelaram tinham contrato mensal

### Hipótese 3: Tenure < 6 meses ↔ Churn

- **χ² > 100** | **p-value ≈ 0**
- ✅ **CONFIRMADA** - Correlação moderada

### Análise Numérica: Tenure ↔ Total Charges

- **Pearson: 0.86** | **Spearman: 0.84**
- ✅ Forte correlação positiva

---

## 🗂️ Estrutura do Projeto

```text
.
├── datasets_aula/
│   ├── churn_customers.csv      (Customer demographics)
│   ├── churn_services.csv       (Services subscribed)
│   └── churn_contracts.csv      (Contract details)
│
├── eda_churn.ipynb              (Notebook com análise completa)
├── eda_churn_report.html        (Relatório SweetViz)
└── README.md
```

---

## 🛠️ Tecnologias Utilizadas

| Biblioteca | Versão | Função |
| --- | --- | --- |
| **Pandas** | 2.x | Manipulação e transformação de dados |
| **NumPy** | 2.4+ | Operações numéricas e arrays |
| **SciPy** | 1.x | Testes estatísticos (Chi-Square) |
| **Matplotlib** | 3.x | Visualizações estáticas |
| **SweetViz** | 2.x | Análises visuais automatizadas |

---

## 🚀 Como Executar

### Pré-requisitos

- Python 3.11+
- pipenv (gerenciador de dependências)

### Instalação

```bash
# Instale as dependências
pipenv install

# Ative o ambiente virtual
pipenv shell
```

### Executar o Notebook

```bash
# Inicie o Jupyter
jupyter notebook eda_churn.ipynb

# Ou use o vscode
code .
```

### Gerar Relatório SweetViz

Dentro do notebook, execute a célula com o código SweetViz:

```python
import numpy as np
if not hasattr(np, 'VisibleDeprecationWarning'):
    np.VisibleDeprecationWarning = DeprecationWarning

import sweetviz as sv
sv_churn_report = sv.analyze(df_churn, target_feat='Churn')
```

---

## 📈 Resultados Esperados

O notebook gera:

- ✅ DataFrames consolidados com dados limpos e transformados
- ✅ Tabelas estatísticas com medidas de posição e dispersão
- ✅ Testes de hipótese com valores chi-quadrado e p-values
- ✅ Matrizes de correlação (Pearson e Spearman)
- ✅ Visualizações de distribuições e relações entre variáveis
- ✅ Detecção de outliers usando múltiplos métodos
- ✅ Relatório visual interativo (SweetViz)

---

## 📚 Conceitos Aplicados

- **Análise Exploratória de Dados (EDA)**
- **Estatística Descritiva** (média, mediana, desvio padrão)
- **Testes de Hipótese** (Chi-Square test)
- **Análise de Correlação** (Pearson e Spearman)
- **Detecção de Outliers** (Tukey IQR, Z-score)
- **Data Wrangling** (limpeza, transformação, consolidação)

---

## 📝 Notas Importantes

- O notebook foi desenvolvido com **NumPy 2.4**, que removeu `VisibleDeprecationWarning`
- O workaround no SweetViz adiciona o atributo faltante manualmente
- Todos os testes estatísticos usam **significância α = 0.05**
- As correlações são consideradas significativas quando **p-value ≤ 0.05**
