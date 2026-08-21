# Mini Projeto: Análise de Dados de Varejo
 
Este projeto realiza uma análise exploratória de dados de vendas de varejo, focando em limpeza de dados, estatísticas descritivas e identificação de padrões de agrupamento.
 
## Objetivo
 
O principal objetivo é processar e analisar um conjunto de dados de vendas de varejo (`Base Varejo.csv`) para extrair insights sobre os hábitos de compra dos clientes, as categorias de produtos mais populares e identificar possíveis áreas para análises mais aprofundadas.
 
## Dados
 
O conjunto de dados utilizado é `Base Varejo.csv`, contendo informações sobre transações de vendas, incluindo:
 
- `DATA`: Data da transação.
- `CO_ID`: ID da compra.
- `CL_ID`: ID do cliente.
- `CL_GENERO`: Gênero do cliente.
- `CL_EC`: Estado Civil do cliente.
- `CL_FHL`: Número de filhos do cliente.
- `CL_SEG`: Segmento do cliente.
- `PR_ID`: ID do produto.
- `PR_CAT`: Categoria do produto.
- `PR_NOME`: Nome do produto.
 
## Etapas Realizadas
 
1. **Carregamento de Dados:**
   - O arquivo `Base Varejo.csv` foi carregado usando `pandas`, com o separador correto (`;`).
 
2. **Limpeza e Pré-processamento:**
   - **Remoção de Colunas Vazias:** As colunas 'Unnamed: 10', 'Unnamed: 11', 'Unnamed: 12', 'Unnamed: 13' foram identificadas e removidas por estarem completamente vazias.
   - **Tratamento de Categorias:** A categoria `PR_CAT` `#N/D` (Not Available/Defined) foi identificada e removida (representava aproximadamente 0.44% dos dados).
   - **Remoção de Duplicatas:** Foram encontradas e removidas 96.131 linhas duplicadas, resultando em um conjunto de dados mais limpo com 730.219 registros únicos.
   - **Conversão de Tipo de Dados:** A coluna `DATA` foi convertida para o formato `datetime` (`datetime64[ns]`) para permitir análises temporais futuras.
 
3. **Análise Exploratória de Dados (EDA):**
   - **Estatísticas Descritivas:** Cálculos de média, mediana, desvio padrão, moda, máximo e mínimo para a coluna `CL_FHL` (Número de Filhos), revelando que a maioria dos clientes tem poucos ou nenhum filho.
   - **Vendas por Gênero (`CL_GENERO`):** Verificou-se que clientes do gênero feminino (`F`) contribuíram com um número ligeiramente maior de vendas do que o masculino (`M`).
   - **Vendas por Categoria de Produto (`PR_CAT`):** 'ALIMENTOS' se destacou como a categoria de produto mais vendida, seguida por 'HIGIENE' e 'LIMPEZA'.
   - **Vendas por Gênero e Categoria:** A análise combinada confirmou a dominância da categoria 'ALIMENTOS' para ambos os gêneros, mantendo o padrão de vendas F > M na maioria das categorias.
 
## Principais Insights
 
- O dataset foi cuidadosamente limpo, removendo inconsistências e duplicatas, tornando-o apto para análises mais aprofundadas.
- O perfil demográfico inicial sugere que clientes com poucos ou nenhum filho são predominantes na base.
- Mulheres realizam um volume ligeiramente maior de compras na base de dados analisada.
- A categoria de `ALIMENTOS` é o carro-chefe de vendas, independentemente do gênero do cliente.
 
## Próximos Passos e Problemas Remanescentes
 
1. **Valor Monetário das Vendas:** A análise atual é baseada apenas na contagem de transações. A inclusão de uma coluna com o valor monetário de cada venda permitiria uma compreensão mais completa do impacto financeiro.
2. **Segmentação de Clientes:** Embora `CL_ID` e `CL_SEG` existam, uma análise mais aprofundada de segmentos de clientes ou dados demográficos adicionais enriqueceria a segmentação e a personalização de estratégias.
3. **Análise Temporal:** Explorar as tendências de vendas ao longo do tempo (por dia da semana, mês, etc.) utilizando a coluna `DATA` seria valioso para identificar sazonalidades.
4. **Significado das Categorias:** Aprofundar o entendimento dos segmentos de clientes (`CL_SEG`) para derivar insights específicos para cada grupo.
 
## Como Executar o Projeto
 
1. **Ambiente:**
   - **Google Colab:** Acesse [Google Colab](https://colab.research.google.com/) e crie um novo notebook.
   - **VSCode:** Certifique-se de que a extensão Python esteja instalada e abra um novo arquivo Python ou um notebook Jupyter.
 
2. **Dados:**
   - Certifique-se de que o arquivo `Base Varejo.csv` esteja na mesma pasta que o notebook (se estiver usando VSCode) ou acessível via Google Drive (se estiver usando Google Colab). Para montar seu Google Drive no Colab:
     ```python
     from google.colab import drive
     drive.mount('/content/drive')
     ```
   - Após montar, forneça o caminho correto para o arquivo.

3. **Execução:**
   - Rode todas as células do notebook sequencialmente clicando na célula e pressionando `Shift + Enter`.
   - Verifique os resultados e insights gerados ao longo do processo.
 
## Dicas Adicionais
 
- **Verifique Dependências:** Certifique-se de que todas as bibliotecas necessárias (como `pandas`, `numpy`, etc.) estejam instaladas. No Google Colab, você pode instalar pacotes com `!pip install nome_do_pacote`.
- **Explore os Resultados:** Após a execução, explore os gráficos e tabelas geradas para obter insights mais detalhados.
