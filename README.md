# Dashboard de produtividade médica

Dashboard feito no Power BI com dados fictícios criados a partir da biblioteca Faker (Python).

## Dados

Os dados foram criados no Google Colab, utilizando a linguagem Python e as bibliotecas Faker (para geração dos dados) e Pandas (para transformar as listas de dicionários em dataframes e exportá-los para csv).

Foram criados 50 médicos fictícios distribuídos por 5 estabelecimentos de saúde (arquivo "dmedicos.csv), bem como 200.000 entradas únicas de procedimentos (entre Consulta, Fisioterapia e Raio-X) distribuídas ao longo de 2023 (arquivo "fproducao").

Datas e valores foram criados aleatoriamente a partir de parâmetros, e pesos diferentes foram conferidos aos procedimentos para escolha semi-aleatória. Para mais detalhes, é possível conferir o notebook "dataset_faker.ipynb", disponível neste repositório.

Os dados foram incrementados no Power BI por meio do Power Query e linguagem M, em especial acrescentando quantidades de procedimentos (com valores aleatórios parametrizados) e atribuindo um identificador para cada procedimento. Foi, ainda, criada uma tabela dimensão para esses procedimentos.

## Dashboard

O dashboard busca, de maneira simples e intuitiva, destacar a produtividade médica de cada clínica. Para isso, dois índices foram utilizados:
- R$/Consulta: a soma dos valores de cada entrada da tabela "fproducao" dividido pela quantidade de procedimentos do tipo "Consulta"
- Procedimentos por consulta: a soma da quantidade de procedimentos dividida pela quantidade de procedimentos do tipo "Consulta"

É possível filtrar ambos por estabelecimento, procedimentos específicos ou datas.
Na matriz, foram atribuídas regras condicionais indicando, em cor verde, uma variação positiva em relação ao mês anterior e, em cor vermelha, uma variação negativa.
Por fim, alguns KPIs gerais, como médias e volumes totais, foram incluídos para referência cruzada com a produtividade específica de cada médico.
