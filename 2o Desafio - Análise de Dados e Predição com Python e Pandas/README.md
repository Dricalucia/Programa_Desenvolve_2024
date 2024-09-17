
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
| 	     |area	  |bedrooms|garage |rent    |
|-------|-------|--------|-------|--------|
|count	|11646.0|11646.0 |11646.0|11646.0 |
|mean	|85.0	|2.0	 |1.0	 |3250.0  |
|std	|74.0	|1.0	 |1.0	 |2649.0  |
|min	|0.0	|0.0	 |0.0	 |500.0   |
|25%	|40.0	|1.0	 |0.0	 |1590.0  |
|50%	|60.0	|2.0	 |1.0	 |2420.0  |
|75%	|96.0	|3.0	 |2.0	 |3800.0  |
|max	|580.0	|6.0	 |6.0	 |25000.0 |

Análise da variável: area
- Média: 84.66
- Desvio Padrão: 74.02
- Mínimo: 0.00
- Máximo: 580.00
- Percentil 25%: 40.00
- Mediana (50%): 60.00
- Percentil 75%: 96.00


Análise da variável: bedrooms
- Média: 1.97
- Desvio Padrão: 0.93
- Mínimo: 0.00
- Máximo: 6.00
- Percentil 25%: 1.00
- Mediana (50%): 2.00
- Percentil 75%: 3.00


Análise da variável: garage
- Média: 1.06
- Desvio Padrão: 1.13
- Mínimo: 0.00
- Máximo: 6.00
- Percentil 25%: 0.00
- Mediana (50%): 1.00
- Percentil 75%: 2.00


Análise da variável: rent
- Média: 3250.22
- Desvio Padrão: 2649.22
- Mínimo: 500.00
- Máximo: 25000.00
- Percentil 25%: 1590.00
- Mediana (50%): 2420.00
- Percentil 75%: 3800.00

A análise dos dados mostra que a média área da maioria dos imóveis é de 85 m², porém possuem um desvio padrão muito alto, isso indica a variação nos tamanhos dos imóveis.

No dataset existe dados de imoveis com 0m² e que pode indicar erros de lançamento. Deste modo, deve-se considerar os imóveis com mais de 40m², o que correspondem ao percentil de 25% dos imóveis.

A média e a mediana de quartos por imóvel são de 2 quartos. Do mesmo modo, a média e a mediana de garagem por imóvel é de 1 vaga.

A média do aluguel é R$ 3.251,00, porém apresenta um desvio padrão muito alto, assim como o tamanho dos imóveis em metros quadrados. Isso sugere que o valor do aluguel varia de acordo com o tamanho dos imóveis.

Além disso, a mediana do aluguel é de R$ 2.415,00, o que indica que metade dos imóveis possuem aluguel abaixo desse valor.
## Regressão Linear

### Correlação
<img src="https://github.com/Dricalucia/Programa_Desenvolve_2024/blob/ca202b6853814bb4061316e33c5fd13d6e676119/2o%20Desafio%20-%20An%C3%A1lise%20de%20Dados%20e%20Predi%C3%A7%C3%A3o%20com%20Python%20e%20Pandas/graficos/correlacao.png" height="500" width="500">

A área do imóvel está fortemente correlacionada com o número de quartos e garagem, o que indica que imóveis maiores tendem a ter mais quartos e mais vagas de garagem. A área, quartos e garagem têm correlações positivas moderadas com o valor do aluguel. Isso sugere que imóveis maiores, com mais quartos e vagas de garagem, geralmente têm aluguéis mais altos.


### Boxplot
<img src="https://github.com/Dricalucia/Programa_Desenvolve_2024/blob/ca202b6853814bb4061316e33c5fd13d6e676119/2o%20Desafio%20-%20An%C3%A1lise%20de%20Dados%20e%20Predi%C3%A7%C3%A3o%20com%20Python%20e%20Pandas/graficos/boxplot.png" height="300" width="800">

<img src="https://github.com/Dricalucia/Programa_Desenvolve_2024/blob/ca202b6853814bb4061316e33c5fd13d6e676119/2o%20Desafio%20-%20An%C3%A1lise%20de%20Dados%20e%20Predi%C3%A7%C3%A3o%20com%20Python%20e%20Pandas/graficos/dist_qtd_quartos.png" height="300" width="800">

A representação deste gráfico apresenta uma visão da distribuição dos valores de aluguel em diversas faixas de preço. Essa visualização é fundamental para uma avaliação precisa do comportamento dos preços dos alugueis.

<img src="https://github.com/Dricalucia/Programa_Desenvolve_2024/blob/ca202b6853814bb4061316e33c5fd13d6e676119/2o%20Desafio%20-%20An%C3%A1lise%20de%20Dados%20e%20Predi%C3%A7%C3%A3o%20com%20Python%20e%20Pandas/graficos/dist_qtd_quartos_garagem.png" height="500" width="800">


Na análise da quantidade de quartos e garagem nos valores de aluguel demonstra que imóveis com mais quartos geralmente têm aluguéis mais elevados, refletindo uma relação direta entre espaço e custo. E ao considerar a garagem, verifica-se que os imóveis com mais vagas apresentam aluguéis superiores, destacando variações conforme a quantidade de quartos.


## Distribuição de frequências
<img src="https://github.com/Dricalucia/Programa_Desenvolve_2024/blob/ca202b6853814bb4061316e33c5fd13d6e676119/2o%20Desafio%20-%20An%C3%A1lise%20de%20Dados%20e%20Predi%C3%A7%C3%A3o%20com%20Python%20e%20Pandas/graficos/dist_frequencia.png" height="300" width="500">

Nota-se que ainda existe uma dispersão, mesmo após o ajuste dos dados, indicando que a variância dos erros não é constante.

## Dispersão entre variáveis
<img src="https://github.com/Dricalucia/Programa_Desenvolve_2024/blob/ca202b6853814bb4061316e33c5fd13d6e676119/2o%20Desafio%20-%20An%C3%A1lise%20de%20Dados%20e%20Predi%C3%A7%C3%A3o%20com%20Python%20e%20Pandas/graficos/dispersao.png" height="300" width="800">
A análise do gráfico mostra que ainda existe uma dispersão, mesmo após o ajuste dos dados, indicando que a variância dos erros não é constante.

## Análise das Previsões do Modelo
<img src="https://github.com/Dricalucia/Programa_Desenvolve_2024/blob/ca202b6853814bb4061316e33c5fd13d6e676119/2o%20Desafio%20-%20An%C3%A1lise%20de%20Dados%20e%20Predi%C3%A7%C3%A3o%20com%20Python%20e%20Pandas/graficos/prev_real.png" height="400" width="600">
A análise do gráfico indica que ainda existe uma dispersão, mesmo após o ajuste dos dados, indicando que a variância dos erros não é constante.

# Distribuição de Frequências dos Resíduos

<img src="https://github.com/Dricalucia/Programa_Desenvolve_2024/blob/ca202b6853814bb4061316e33c5fd13d6e676119/2o%20Desafio%20-%20An%C3%A1lise%20de%20Dados%20e%20Predi%C3%A7%C3%A3o%20com%20Python%20e%20Pandas/graficos/res_prev.png" height="400" width="800">

<img src="https://github.com/Dricalucia/Programa_Desenvolve_2024/blob/ca202b6853814bb4061316e33c5fd13d6e676119/2o%20Desafio%20-%20An%C3%A1lise%20de%20Dados%20e%20Predi%C3%A7%C3%A3o%20com%20Python%20e%20Pandas/graficos/res_prev2.png" height="400" width="800">

A análise do gráfico indica que a variância dos erros não é constantes.


## Conclusão
A análise dos preços de aluguel em São Paulo revela uma grande variação nos valores influenciado pelo tamanho do imóvel, número de quartos e vagas de garagem.

A regressão linear mostrou que imóveis maiores, com mais quartos e garagens, tendem a ter aluguéis mais elevados. No entanto, a dispersão dos dados e a variância não constante dos erros sugerem que outros fatores também podem influenciar nos preços dos aluguéis. Isso aponta para necessidade de considerar outras variáveis para uma previsão mais precisa. ​


## 🔗 Links
[![GitHub](https://img.shields.io/badge/GitHub-E44C30?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Dricalucia/)  

[![GoogleColab](https://img.shields.io/badge/-GoogleColab-FFA500?style=for-the-badge&logo=googlecolab&logoColor=white)](https://drive.google.com/file/d/1sMaS4athLj6Fe84tm2tAewWADTX_0fSV/view?usp=sharing/)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/adrianalfrodrigues/)

[![E-mail](https://img.shields.io/badge/-Email-00FFF00?style=for-the-badge&logo=microsoft-outlook&logoColor=007BFF)](mailto:alfr@cesar.school)








