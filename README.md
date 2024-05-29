## Análise de Dados da Covid-19

Este repositório contém scripts para explorar dados da Covid-19. As habilidades utilizadas incluem:

* Joins: Combinando dados de tabelas relacionadas.
* CTEs (Common Table Expressions): Subconsultas nomeadas para melhorar a legibilidade do código.
* Tabelas Temporárias: Armazenamento temporário de dados dentro de um script.
* Funções de Janela: Cálculos baseados em linhas anteriores ou posteriores dentro de um grupo de dados.
* Funções de Agregação: Operações como soma, média e contagem em grupos de dados.
* Criação de Visualizações de Dados:  Preparação de dados para uso em ferramentas de visualização.
* Conversão de Tipos de Dados: Alteração do formato dos dados para a análise desejada.

**Exploração Inicial:**

* O script inicial seleciona todos os dados da tabela `CovidDeaths`, desde que o continente não seja nulo, ordenando por duas colunas específicas (ajuste de acordo com a sua necessidade).
* Uma consulta subsequente seleciona dados específicos como localidade, data, casos totais, novos casos, mortes totais e população, novamente filtrando por continente não nulo e ordenando por localidade e data.

**Análise de Mortalidade:**

* O script calcula a porcentagem de mortalidade por Covid-19 em cada localidade, dividindo o número de mortes pelo total de casos.
* Os resultados são filtrados para locais que contenham a palavra "estados" (ajuste de acordo com o padrão de nome usado nos seus dados) e ordenados por localidade e data.

**Análise de Infecção:**

* O script calcula a porcentagem da população infectada pela Covid-19 em cada localidade, dividindo o total de casos pela população.
* Os resultados são ordenados por localidade e data.

**Países Mais Afetados:**

* O script identifica os países com a maior taxa de infecção por Covid-19, considerando o número máximo de casos em relação à população.
* A consulta também determina a porcentagem máxima da população infectada.
* Os resultados são agrupados por localidade e população, e ordenados de forma decrescente pela porcentagem de infecção.

* O script identifica os países com o maior número total de mortes por Covid-19.
* Os resultados são agrupados por localidade e ordenados de forma decrescente pelo número total de mortes.

**Análise por Continente:**

* O script identifica os continentes com o maior número total de mortes por Covid-19 em relação à população.
* Os resultados são agrupados por continente e ordenados de forma decrescente pelo número total de mortes.

**Números Globais:**

* O script calcula o total de casos novos, total de mortes novas e a porcentagem global de mortalidade.
* Os resultados são filtrados para locais com continente não nulo e ordenados pelo total de casos e total de mortes.

**Vacinação vs. População:**

* O script analisa a população total comparada à vacinação contra a Covid-19.
* Une as tabelas `CovidDeaths` e `CovidVaccinations` para obter dados sobre localidade, data, população e novas vacinações.
* Calcula o número acumulado de pessoas vacinadas em cada localidade ao longo do tempo usando uma função de janela.
* Os resultados são ordenados por localidade e data.

**Consultas com CTE e Tabelas Temporárias:**

* O script demonstra o uso de CTE (Common Table Expressions) e tabelas temporárias para realizar o mesmo cálculo de porcentagem da população vacinada.
* A CTE é uma subconsulta nomeada que melhora a legibilidade do código.
* A tabela temporária é criada e descartada dentro do script para armazenar dados intermediários.
    * É importante notar que o uso de tabelas temporárias pode ter impacto na performance em alguns bancos de dados.

**Visualização de Dados:**

* O script final cria uma view denominada `PercentPopulationVaccinated` para armazenar os dados necessários para visualizações futuras.
* A view materializada pode melhorar a performance de consultas frequentes.

**Observações:**

* Lembre-se de ajustar as consultas de acordo com os nomes específicos das tabelas e colunas em seu banco de dados.
* Os comentários nas consultas fornecem uma explicação básica da lógica por trás de cada script.
* Este repositório oferece uma base para explorar dados da Covid-19. Você pode estender as análises para incluir outros fatores e métricas.
