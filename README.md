# Análise de Vendas e Opotunidades Comerciais
Análise exploratória, de associação e probabilidades dos dados sobre vendas de uma loja física de protudos de informatica e eletrodomésticos utilizando o Excel.

# Sobre o Projeto

Este projeto apresenta uma análise exploratória, de associação (Information Value) e probabilidades de uma base de dados de uma loja física que atua na área de informática e eletrodomésticos. A base de dados é sintética (não possui dados reais), mas é muito boa para a análise de vendas e de oportunidades comercias. Os dados foram coletados no período de uma ano 12/09/2025 à 12/09/2026. 

Fonte: https://www.kaggle.com/datasets/suzanemartinss/dados-de-vendas-informatica-brasil.

# Objetivos

O objetivo principal dessa análise é responder a seguinte pergunta de negócio:

_Quais características estão associadas às vendas de maior valor e onde estão as principais oportunidades de crescimento comercial?_

# Método

Os dados podem ser acessados na pasta dados (https://github.com/ewerton-lemes/analise-comercial-vendas/tree/main/dados).

Para responder à pergunta de negócio acima, foi feita uma análise exploratótia dos dados com tabelas de frequência, medidas resumo e de variabilidade e também gráficos das variáveis relacionadas às vendas, aos produtos, aos clientes e funcionários. Foram aplicadas técnicas de ETL para tratamento dos dados e junção de tabelas para cruzar os dados e verificar a associção entre algumas variáveis e a probabilidade de alguns eventos. A pasta de trabalho excel, com o nome Vendas, onde estão todas as análises feitas está na pasta análise (https://github.com/ewerton-lemes/analise-comercial-vendas/tree/main/analise).

A primeira parte da pergunta de negócio diz _Quais características estão associadas às vendas de maior valor..._. Pensando nisso definimos _vendas de alto valor_ as vendas com um valor total acima de R$ 1500,00. Foi adotado esse valor pois 80% das vendas estão abaixo dele. Os preços unitários dos produtos foram segmentados entre preço _preço Alto_ e _preço baixo_ onde preço baixo são produtos com preço unitário menor ou igual a R$ 850,00 e preço alto são produtos com preço acima desse valor. O valor de R$ 850,00 foi adotado pois 75% dos produtos estão abaixo de R$ 850,00. A quantidade de produtos vendidos, por venda, foi dividade em _quantidade baixa_ e _quantidade alta_ onde quantidade baixa signfica 2 ou menos produtos foram vendidos e quantidade alta 3 ate 5 produtos foram vendidos (5 é a quantidade máxima em uma venda). A quantidade 2 foi escolhida pois 75% das vendas tem até 2 produtos iguais vendidos. Ainda para responder a essa parte da pergunta de negócio, pensando no total de produtos vendidos no ano, produtos com mais de 800 unidades vendidas no ano foram classificados como _Alta frequência_ e os como uma quantidade menor ou igual a 800 vendidos no ano como _Baixa frequência_

Considerando agora a segunda parte de pergunta de negócio _... onde estão as principais oportunidades de crescimento comercial?_ mais algumas segmentações foram criadas. Foi calculado o Ticket Médio de cada cliente no período em que os dados foram coletados usando a fórmula:

$$\mbox{Ticket Médio} = \displaystyle\frac{\mbox{Faturamento gerado pelo cliente}}{\mbox{número de vendas a esse cliente}}$$

Considerando o Ticket Médio por cliente, os clientes foram segmentados em _Ticket Alto_ aqueles com ticket médio acima ou igual a R$ 1800,00 e _Ticket Baixo_ aqueles com ticket médio abaixo desse valor. Tickets médios abaixo desse valor correspondem a 75% dos clientes. Os clientes também foram segmentados de acordo com a quantidade de compras que fizeram do período em que os dados foram coletados, separamos em _Alta frequência_ os que fizeram mais de 9 compras no ano e o restante em _Baixa frequência._. A quantidade de até 9 produtos vendidos no ano correspondem a 75% dos clientes.

Com esse método aplicado vários insights foram obtidos e, a partir deles, chegamos à resposta de pergunta de negócio. A seguir estão os principais insights.

# Principais Insights

1. De 10/2025 a 08/2026 os valores ficaram entre R$ 1.712.021,25 e 2.036.392,50 de reais, ou seja, os valores se mantiveram relativamente próximos. O mês que apresentou queda na vendas foi o mês de setembro, no ano de 2025 foi R$1.241.196,25. No ano de 2026 foi de R$ 645.576,25, mas nos dados estão somente os 12 primeiros dias do mês.

2. As vendas de alto valor correspondem a 20,4% do total de vendas. Embora esse não seja um número expressivo, as vendas de alto valor são responsáveis por 69% do faturamento no período em que os dados foram coletados.

3. A quantidade de produtos vendidos está relacionada com as vendas de alto valor (IV=0,37). Dentre as vendas de 4 produtos e 5 produtos, as vendas de alto valor correspondem a 50% e 57%. Já na faixa de 3 produtos vendidos, 37% das vendas são de alto valor. Porém, há um detalhe importante relacionado às essas quantidade de produtos vendidos, elas representam apenas 25% da quantidade de vendas, isto é, 75% das vendas são de 2 ou um produto apenas.

4. O preço unitário dos produtos também tem uma forte associação com as vendas de alto valor (IV=0,42). Produtos com valores unitários acima de 1500 reais geram vendas de alto valor com apenas um produto vendido. Nas vendas de produtos com faixa de preço unitário entre R$ 785,00 e R$ 1385,00, em média, 35% são de alto valor.

5. Cruzando as variáveis quantidade de produtos vendidos e preço unitário, temos que 70,45% da vendas de alto valor ocorrem com a venda de até dois produtos com preços unitários acima de 850 reais enquanto que apenas 12,5% das vendas de alto valor ocorrem com mais de dois produtos vendidos com preço unitário abaixo de 850 reais.

6. A probabilidade de uma venda alta ocorrer com até dois produtos com preço unitários acima de 850 reais é de 69%, enquanto que é de apenas 25,7% em vendas com produtos com quantidade acima de 2 e preço abaixo de 850 reais.

7. A categoria possui uma associação importante com as vendas de alto valor (IV=0,78). Cerca de 52% das vendas de Eletrônicos correspondem a vendas de alto valor. Nas categorias de Informática e Mobiliário esses valores são 28% e 20%.

8. Mais de 75% do faturamento estão em apenas 11 produtos.

9. Mais de 50% do faturamento estão em apenas 4 produtos.

10. Os descontos não apresentam associação relevante com as vendas de alto valor. Aproximadamente 79% das vendas de alto valor não receberam desconto. Além disso, o número de vendas de alto valor corresponde a 20,4% do quantidade total de vendas e, restringindo às vendas que tiveram desconto, temos 21% de vendas de alto valor, ou seja, os resultados não indicam que a concessão de descontos esteja associada a uma maior ocorrência de vendas de alto valor.

11. A categoria de acessórios é a segunda categoria com maior quantidade de vendas (24,2%) porém é a que menos participa do faturamento total com apenas 4% de participação.

# Resposta da pergunta de negócio

Diante desses fatos, podemos concluir que as vendas de alto valor, acima de 1500 reais, Estão predominantemente associadas a vendas de quantidade baixa de produtos e valores altos de preços unitários. Embora a quantidade de produtos também apresente forte associação com o alto valor (IV = 0,37), o cruzamento das variáveis indica que o preço unitário possui papel particularmente importante, 70,45% das vendas de alto valor ocorrem em transações com até dois produtos e preço unitário superior a R$850.


Pergunta B — comercial
Quais segmentos apresentam oportunidades de crescimento?

63,04% dos clientes apresentam simultaneamente baixa frequência de compras e baixo ticket médio. Além disso, a probabilidade de um cliente apresentar ticket alto é de 46,17% entre aqueles com alta frequência, contra 20,82% entre os de baixa frequência. Os resultados sugerem que a frequência de compra está associada a uma maior ocorrência de tickets altos. Dessa forma, clientes de baixa frequência e baixo ticket podem representar uma oportunidade para estratégias de aumento da frequência de compras.

Adicionar produtos de maior valor na categoria de acessórios, pois é bastante procurada, tem uma variação preço muito pequena, com média de 131,74 reais e baixa participação no faturamento.

Há uma dependência muito alta de apenas 4 produtos responsáveis por mais de 50% do faturamento. Seria bom criar planos para não depender somente desse produtos.


