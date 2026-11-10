# Aula23_BigData_M2
# Análise Estatística de Crimes Violentos Letais Intencionais (CVLI)

## Descrição

Este projeto realiza uma análise estatística dos dados de Crimes Violentos Letais Intencionais (CVLI) do Estado do Rio de Janeiro utilizando dados públicos disponibilizados pelo Instituto de Segurança Pública (ISP-RJ).

Os scripts calculam medidas estatísticas, identificam padrões de distribuição, detectam outliers e geram visualizações gráficas para auxiliar na interpretação dos dados.

## Fonte dos Dados

Os dados são obtidos diretamente do portal ISP Dados:

https://www.ispdados.rj.gov.br/Arquivos/BaseDPEvolucaoMensalCisp.csv

## Arquivos do Projeto

### atividade_cvli.py

Realiza a análise agregada de CVLI por Área Integrada de Segurança Pública (AISP).

Funcionalidades:

- Importação automática dos dados.
- Agrupamento das ocorrências por AISP.
- Cálculo do percentual de participação de cada AISP.
- Cálculo de medidas estatísticas:
  - Média
  - Mediana
  - Variância
  - Desvio padrão
  - Coeficiente de variação
  - Assimetria
  - Curtose
- Cálculo dos quartis (Q1, Q2 e Q3).
- Identificação de valores discrepantes (outliers).
- Identificação dos grupos com maiores e menores ocorrências.
- Geração de painel gráfico contendo:
  - Boxplot
  - Resumo estatístico
  - Top 10 AISPs com mais ocorrências
  - Histograma da distribuição

---

### atividade_cvli_munic.py

Realiza a análise de CVLI por município, agrupado por AISP.

Funcionalidades:

- Importação automática dos dados.
- Agrupamento por:
  - AISP
  - Município
- Cálculo das medidas estatísticas da distribuição.
- Identificação de quartis e outliers.
- Avaliação da dispersão dos dados.
- Geração de gráficos para análise visual da distribuição.
- Exibição dos municípios com maiores e menores índices de CVLI.

## Bibliotecas Utilizadas

- pandas
- numpy
- matplotlib
- subprocess

Instalação:

```bash
pip install pandas numpy matplotlib
```

## Métricas Estatísticas Utilizadas

### Tendência Central

- Média
- Mediana

### Dispersão

- Amplitude
- Variância
- Desvio Padrão
- Coeficiente de Variação

### Posição

- Quartil 1 (Q1)
- Quartil 2 (Mediana)
- Quartil 3 (Q3)

### Forma da Distribuição

- Assimetria (Skewness)
- Curtose

### Outliers

A identificação dos outliers é realizada pelo método do Intervalo Interquartil (IQR):

```text
IQR = Q3 - Q1

Limite Inferior = Q1 - 1.5 × IQR
Limite Superior = Q3 + 1.5 × IQR
```

## Como Executar

### Análise por AISP

```bash
python atividade_cvli.py
```

### Análise por Município

```bash
python atividade_cvli_munic.py
```

## Visualizações Geradas

Os scripts produzem um painel com quatro componentes:

1. Boxplot da distribuição dos CVLI.
2. Resumo das principais medidas estatísticas.
3. Ranking dos maiores registros de CVLI.
4. Histograma para avaliação da distribuição dos dados.

## Objetivos do Projeto

- Aplicar conceitos de Estatística Descritiva.
- Analisar a distribuição dos crimes letais no estado do Rio de Janeiro.
- Identificar áreas com maior concentração de ocorrências.
- Detectar valores atípicos.
- Apoiar análises exploratórias de segurança pública baseadas em dados.

## Autor

Rodrigo Peçanha