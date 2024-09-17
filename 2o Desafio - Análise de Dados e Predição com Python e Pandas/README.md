
# Análise de Dados e Predição com Python e Pandas
Análise da base de dados de preços de aluguéis, em São Paulo, usando Python e a biblioteca Pandas com foco em regressão linear, para modelar a relação entre variáveis do conjunto de dados.

## Coleta de dados
Dataset: base-alugueis-sp.csv

Importação de bibliotecas para manipulação e análise dos dados.
## Dicionário de Dados
- address: endereço do imóvel
- district: bairro
- area: m² do imovel
- bedrooms: quantidade de quartos do imóvel
- garage: quantidade de garagens do imóvel
- type: tipo do imóvel
- rent: valor do aluguel do imóvel
- total: valor total não especificado

## Análise Descritiva
 	    |area	|bedrooms|garage |rent    |
|-------|-------|--------|-------|--------|
|count	|11646.0|11646.0 |11646.0|11646.0 |
|mean	|85.0	|2.0	 |1.0	 |3250.0  |
|std	|74.0	|1.0	 |1.0	 |2649.0  |
|min	|0.0	|0.0	 |0.0	 |500.0   |
|25%	|40.0	|1.0	 |0.0	 |1590.0  |
|50%	|60.0	|2.0	 |1.0	 |2420.0  |
|75%	|96.0	|3.0	 |2.0	 |3800.0  |
|max	|580.0	|6.0	 |6.0	 |25000.0 |


A análise dos dados mostra que a média área da maioria dos imóveis é de 85 m², porém possuem um desvio padrão muito alto, isso indica a variação nos tamanhos dos imóveis.

No dataset existe dados de imoveis com 0m² e que pode indicar erros de lançamento. Deste modo, deve-se considerar os imóveis com mais de 40m², o que correspondem ao percentil de 25% dos imóveis.

A média e a mediana de quartos por imóvel são de 2 quartos. Do mesmo modo, a média e a mediana de garagem por imóvel é de 1 vaga.

A média do aluguel é R$ 3.251,00, porém apresenta um desvio padrão muito alto, assim como o tamanho dos imóveis em metros quadrados. Isso sugere que o valor do aluguel varia de acordo com o tamanho dos imóveis.

Além disso, a mediana do aluguel é de R$ 2.415,00, o que indica que metade dos imóveis possuem aluguel abaixo desse valor.
## Regressão Linear

### Correlação

A área do imóvel está fortemente correlacionada com o número de quartos e garagem, o que indica que imóveis maiores tendem a ter mais quartos e mais vagas de garagem. A área, quartos e garagem têm correlações positivas moderadas com o valor do aluguel. Isso sugere que imóveis maiores, com mais quartos e vagas de garagem, geralmente têm aluguéis mais altos.


### Boxplot
<img src="https://img.icons8.com/color/48/000000/python--v1.png" height="40" width="40"/>

A representação deste gráfico apresenta uma visão da distribuição dos valores de aluguel em diversas faixas de preço. Essa visualização é fundamental para uma avaliação precisa do comportamento dos preços dos alugueis.




Na análise da quantidade de quartos e garagem nos valores de aluguel demonstra que imóveis com mais quartos geralmente têm aluguéis mais elevados, refletindo uma relação direta entre espaço e custo. E ao considerar a garagem, verifica-se que os imóveis com mais vagas apresentam aluguéis superiores, destacando variações conforme a quantidade de quartos.



## Distribuição de frequências

Na representação do gráfico percebemos uma alta concentração de imóveis com valores mais baixos,mas há uma cauda longa à direita, indicando a presença de alguns imóveis com aluguéis muito altos.

A representação através do gráfico boxplot oferece uma visão abrangente da distribuição dos valores de aluguel em diversas faixas de preço.
## Análise das Previsões do Modelo

A análise do gráfico mostra que  ainda existe uma dispersão, mesmo após o ajuste dos dados, indicando que a variância dos erros não é constante.


A análise do Resíduo x Previsão   indica que a variância dos erros não é constantes.


# Distribuição de Frequências dos Resíduos



## 🔗 Link
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Dricalucia/)  

[![GoogleColab](https://img.shields.io/badge/-GoogleColab-FFA500?style=for-the-badge&logo=colab&logoColor=white)](https://drive.google.com/file/d/1sMaS4athLj6Fe84tm2tAewWADTX_0fSV/view?usp=sharing/)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/adrianalfrodrigues/)




## Data Analysis

| Projeto               | Link                                          | 
| ----------------- | ---------------------------------------------------------------- |
| Analise do IDHM dos Municípios Brasileiros|  !![Ler análise](https://img.shields.io/badge/-Análise-E44C30?style=for-the-badge) |
| Análise de Dados e Predição com Python e Pandas       | ![Ler análise](https://img.shields.io/badge/-Análise-0077B5?style=for-the-badge)  |
| Análise de Dados com BigQuery e Looker e Storytelling       | ![Ler análise](https://img.shields.io/badge/-Análise-E44C30?style=for-the-badge) |
-----------------------------






