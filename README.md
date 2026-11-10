# Aula23_BigData_M2
# Análise Estatística de Crimes Violentos Letais Intencionais (CVLI)

Dois scripts em Python que realizam uma análise estatística descritiva dos dados de **Crimes Violentos Letais Intencionais (CVLI)** do Estado do Rio de Janeiro, utilizando informações públicas disponibilizadas pelo **Instituto de Segurança Pública do Rio de Janeiro (ISP-RJ)**.

Os scripts calculam medidas estatísticas, identificam padrões de distribuição, detectam valores discrepantes (outliers) e apresentam visualizações gráficas para auxiliar a interpretação dos resultados.

### Arquivos

| Arquivo | O que faz |
|----------|----------|
| atividade_cvli.py | Analisa os dados de CVLI agrupados por **AISP (Área Integrada de Segurança Pública)**. |
| atividade_cvli_munic.py | Analisa os dados de CVLI agrupados por **AISP e Município**. |

### Pré-requisitos

- Python 3.9 ou superior
- Bibliotecas:

```bash
pip install pandas numpy matplotlib
```

### Fonte dos dados

Os scripts obtêm os dados diretamente do portal ISP Dados:

```text
https://www.ispdados.rj.gov.br/Arquivos/BaseDPEvolucaoMensalCisp.csv
```

Não é necessário realizar download manual dos dados.

### Formato dos dados

Arquivo CSV disponibilizado pelo ISP-RJ:

- Separador: `;`
- Codificação: `iso-8859-1`

Principais colunas utilizadas:

| Coluna | Descrição |
|----------|----------|
| aisp | Área Integrada de Segurança Pública |
| munic | Município |
| cvli | Crimes Violentos Letais Intencionais |

### Como executar

#### Análise por AISP

```bash
python atividade_cvli.py
```

#### Análise por Município

```bash
python atividade_cvli_munic.py
```

### Estatísticas calculadas

Os scripts calculam as seguintes métricas:

#### Tendência Central

- Média
- Mediana

#### Medidas de Posição

- Valor mínimo
- Q1 (1º Quartil)
- Q2 (Mediana)
- Q3 (3º Quartil)
- Valor máximo

#### Dispersão

- Amplitude
- Variância
- Desvio-padrão
- Coeficiente de variação

#### Forma da distribuição

- Assimetria
- Curtose

### Identificação de outliers

Os valores discrepantes são identificados utilizando o método do Intervalo Interquartil (IQR):

```text
IQR = Q3 - Q1

Limite Inferior = Q1 - (1,5 x IQR)

Limite Superior = Q3 + (1,5 x IQR)
```

Os scripts exibem:

- Outliers inferiores
- Outliers superiores
- Registros acima do terceiro quartil
- Registros abaixo do primeiro quartil

### Visualizações geradas

Cada script gera um painel contendo quatro análises gráficas:

| Gráfico | Objetivo |
|----------|----------|
| Boxplot | Visualizar a distribuição dos CVLI e os possíveis outliers |
| Resumo Estatístico | Exibir as principais medidas estatísticas calculadas |
| Top 10 Ocorrências | Mostrar os maiores registros de CVLI |
| Histograma | Avaliar a distribuição dos dados e sua assimetria |

### Informações exibidas no terminal

Além dos gráficos, os scripts apresentam:

- Quantidade total de CVLI.
- Participação percentual de cada grupo analisado.
- Maiores ocorrências.
- Menores ocorrências.
- Outliers identificados.
- Interpretação estatística dos resultados.
- Faixas de frequência obtidas pelo histograma.

### Diferenças entre os scripts

#### atividade_cvli.py

Agrupa os dados por AISP:

```python
df_cvli.groupby('aisp')['cvli'].sum()
```

Objetivo:

- Comparar o volume de CVLI entre as áreas de segurança pública do estado.

#### atividade_cvli_munic.py

Agrupa os dados por AISP e Município:

```python
df_cvli.groupby(['aisp', 'munic'])['cvli'].sum()
```

Objetivo:

- Detalhar a distribuição dos CVLI considerando os municípios pertencentes a cada AISP.

### Objetivos do projeto

- Aplicar conceitos de Estatística Descritiva.
- Realizar análise exploratória de dados de segurança pública.
- Identificar regiões com maior concentração de crimes letais.
- Detectar valores discrepantes.
- Avaliar a dispersão dos dados.
- Produzir visualizações para apoio à tomada de decisão baseada em dados.

### Observações

- Os scripts utilizam:

```python
subprocess.run('cls', shell=True)
```

para limpar o terminal, comando compatível apenas com Windows.

Em Linux ou macOS substitua por:

```python
subprocess.run('clear', shell=True)
```

- Os dados são carregados diretamente do portal do ISP-RJ a cada execução.
- Caso ocorra algum erro, o script exibe a mensagem da exceção e, em alguns casos, a linha onde o problema ocorreu.

### Autor

Rodrigo Peçanha
