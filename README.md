# README.md: Miniprojeto Avaliativo - Análise de Dados de Varejo

## Visão Geral do Projeto
Este notebook faz parte do Miniprojeto Avaliativo da disciplina de Visualização de Dados T1 do SCTEC. O objetivo principal é realizar uma análise exploratória e de limpeza de dados de vendas de varejo, utilizando a biblioteca Pandas em Python. O projeto foi desenvolvido no Google Colab, e pode ser acessado através do link https://colab.research.google.com/drive/1uhyUbp5OYVfjk3Tee9yEnDhrYeSSPN-G

## Conjunto de Dados
O projeto utiliza o arquivo `Base Varejo.csv`, que contém dados transacionais de um cenário de varejo. As colunas incluem informações sobre datas, IDs de compra, IDs de clientes, características demográficas dos clientes (gênero, estado civil, número de filhos, segmento) e detalhes dos produtos (ID, categoria, nome).

## Como Rodar o Código
Para executar este notebook, siga os passos abaixo:

1.  **Faça o upload do arquivo CSV**: Certifique-se de que o arquivo `Base Varejo.csv` esteja uploaded no ambiente do Google Colab (ou no diretório correto, se estiver executando localmente).
2.  **Execute as células em sequência**: Basta rodar cada célula do notebook na ordem em que aparecem. As células estão organizadas de forma lógica, desde a importação até a exploração e conclusões.

### Bibliotecas Necessárias:

As seguintes bibliotecas Python são utilizadas e serão importadas automaticamente pelas células do notebook:

*   `pandas`
*   `matplotlib.pyplot`
*   `seaborn`

Certifique-se de que seu ambiente Python tenha essas bibliotecas instaladas. Em um ambiente Colab, elas geralmente já vêm pré-instaladas.

## Etapas do Projeto
O projeto foi estruturado para cobrir as seguintes fases, conforme as tarefas obrigatórias:

### 1. Importação e Inspeção Inicial dos Dados
- Carregamento da base `Base Varejo.csv` utilizando `pandas`.
- Exibição do número de registros, colunas e seus respectivos tipos de dados.
- Visualização das primeiras linhas do DataFrame.

### 2. Verificação e Relato de Problemas Básicos
- Identificação e contagem de valores nulos por coluna.
- Verificação da existência de linhas duplicadas.
- Análise de possíveis inconsistências (ex: categorias de produtos vazias).

### 3. Limpeza Mínima Necessária dos Dados
- **Remoção de Colunas Vazias**: Colunas sem nenhum valor (100% nulas) foram removidas.
- **Remoção de Duplicatas**: Linhas duplicadas foram identificadas e eliminadas para garantir a unicidade dos registros.
- **Tratamento de Nulos**: Colunas críticas como `CO_ID` e `CL_ID` foram verificadas para nulos (neste caso, não havia), e categorias de produtos nulas foram preenchidas com 'Sem Categoria' (embora no dataset atual não existissem, a lógica foi implementada).
- **Ajuste de Tipos de Dados**: A coluna `DATA` foi convertida para o formato `datetime`, e colunas categóricas (`CL_GENERO`, `CL_SEG`, `PR_CAT`, `PR_NOME`) foram convertidas para o tipo `string` para otimização e melhor manipulação.
- O DataFrame limpo (`df_limpo`) foi exportado para `df_limpo.csv`.

### 4. Geração de Estatísticas Descritivas
- Cálculo de estatísticas básicas (média, mediana, desvio padrão, moda, máximo, mínimo e contagem) para a coluna `CL_FHL` (número de filhos do cliente).

### 5. Exploração de Padrões de Agrupamento
- **Tamanho médio da cesta de compras por número de filhos**: Análise de como o número de filhos de um cliente pode influenciar a quantidade média de produtos em uma compra, utilizando `groupby()`.
- **Volume mensal de vendas**: Extração do mês da coluna `DATA` e cálculo do volume de vendas por mês para identificar tendências sazonais.

### 6. Conclusões e Insights
Um bloco final com os principais insights obtidos da análise dos dados foi apresentado, contendo os seguintes insights:
- A grande maioria dos clientes não possui filhos.
- O número de filhos por cliente não interfere no tamanho médio das compras
- O mês com pior performance de vendas da série histórica, visto de maneira agregada, é novembro.

## Tecnologias Utilizadas
- **Python**
- **Pandas**: Para manipulação e análise de dados.
- **Matplotlib** e **Seaborn**: Para visualização de dados (utilizados no volume mensal de vendas).

Este projeto demonstra a capacidade de realizar um fluxo completo de análise de dados, desde a carga e limpeza até a exploração e a geração de insights relevantes, essencial para a compreensão de conjuntos de dados complexos em um contexto de varejo.
