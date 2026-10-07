## Em construção...

# Análise de Vendas e Opotunidades Comerciais
Análise exploratória, de associação e probabilidades dos dados sobre vendas de uma loja física de protudos de informatica e eletrodomésticos utilizando o Excel.

# Sobre o Projeto

Este projeto apresenta uma análise exploratória, de associação (Information Value) e probabilidades de uma base de dados de uma loja física que atua na área de informática e eletrodomésticos. A base de dados é sintética (não possui dados reais), mas é muito boa para a análise de vendas e de oportunidades comercias. Os dados foram coletados no período de uma ano 12/09/2025 à 12/09/2026. 

Fonte: https://www.kaggle.com/datasets/suzanemartinss/dados-de-vendas-informatica-brasil.

Os dados também podem ser acessados na pasta dados (https://github.com/ewerton-lemes/analise-comercial-vendas/tree/main/dados).

# Objetivos

O objetivo principal dessa análise é responder a seguinte pergunta de negócio:

_Quais características estão associadas às vendas de maior valor e onde estão as principais oportunidades de crescimento comercial?_

# Método

Primeiramente separamos a pergunta de negócio em duas:

- Parte A: _Quais características estão associadas às vendas de maior valor?_
- Parte B: _Onde estão as principais oportunidades de crescimento comercial?_

## Segmentação das variáveis

Para responder às duas partes da pergunta de negócio, algumas variáveis foram segmentadas com base na distribuição dos dados, utilizando quartis como referência para a definição dos pontos de corte.

### 1. Características associadas às vendas de maior valor

<div align="center">
  
| Variável | Segmentação | Critério | Justificativa |
|---|---|---|---|
| **Valor total da venda** | Alto valor / Não alto valor | > R$ 1.500 / ≤ R$ 1.500 | R$ 1.500 corresponde aproximadamente ao 80º percentil das vendas |
| **Preço unitário** | Preço alto / Preço baixo | > R$ 850 / ≤ R$ 850 | R$ 850 corresponde aproximadamente ao 75º percentil dos preços unitários |
| **Quantidade por venda** | Quantidade alta / Quantidade baixa | 3 a 5 / 1 a 2 produtos | Até 2 produtos correspondem aproximadamente a 75% das vendas |
| **Frequência de vendas do produto** | Alta frequência / Baixa frequência | > 800 / ≤ 800 vendas no período | 75% dos produtos venderem 800 unidades ou menos |

</div>

### 2. Identificação de oportunidades de crescimento comercial

Além de segmentações, foi criada a nova variável **ticket médio por cliente**, calculado pela seguinte fórmula:

$$
\text{Ticket Médio} =
\frac{\text{Faturamento gerado pelo cliente}}
{\text{Número de vendas realizadas pelo cliente}}
$$

<div align="center">

| Variável | Segmentação | Critério | Justificativa |
|---|---|---|---|
| **Ticket médio por cliente** | Ticket alto / Ticket baixo | ≥ R$ 1.800 / < R$ 1.800 | Tickets abaixo de R$ 1.800 correspondem aproximadamente a 75% dos clientes |
| **Frequência de compras do cliente** | Alta frequência de compras / Baixa frequência de compras | > 9 / ≤ 9 compras no período | Até 9 compras correspondem aproximadamente a 75% dos clientes |

</div>

Com esse método aplicado vários insights foram obtidos e, a partir deles, chegamos à resposta de pergunta de negócio. A seguir estão os principais insights.

# Principais Insights

1. De 10/2025 a 08/2026 os valores ficaram entre R$ 1.712.021,25 e 2.036.392,50 de reais, ou seja, os valores se mantiveram relativamente próximos. O mês que apresentou queda na vendas foi o mês de setembro, no ano de 2025 foi R$1.241.196,25. No ano de 2026 foi de R$ 645.576,25, mas nos dados estão somente os 12 primeiros dias do mês.

<p align="center">
  <img src="https://raw.githubusercontent.com/ewerton-lemes/analise-comercial-vendas/main/imagens/grafico_de_linhas.png" alt="grafico de linhas" width="800">
</p>

2. As vendas de alto valor correspondem a 20,4% do total de vendas. Embora esse não seja um número expressivo, as vendas de alto valor são responsáveis por 69% do faturamento no período em que os dados foram coletados.

<p align="center">
  <img src="https://raw.githubusercontent.com/ewerton-lemes/analise-comercial-vendas/main/imagens/percentual_faturamento_vendas.png" alt="faturamento vendas" width="500">
</p>


3. A quantidade de produtos vendidos está relacionada com as vendas de alto valor (IV=0,37). Dentre as vendas de 4 produtos e 5 produtos, as vendas de alto valor correspondem a 50,5% e 57,9%. Já na faixa de 3 produtos vendidos, 37,2% das vendas são de alto valor.

<div align="center">

| Quantidade | % Alto valor |
|---|---|
| 1 | 13,8% |
| 2 | 26,5% |
| 3 | 37,2% |
| 4 | 50,5% |
| 5 | 57,9% |

</div>

Porém, há um detalhe importante relacionado às essas quantidades de produtos vendidos, elas representam apenas 12,92% da quantidade de vendas, isto é, 87,08% das vendas são de 2 ou um produto apenas.

<p align="center">
  <img src="https://raw.githubusercontent.com/ewerton-lemes/analise-comercial-vendas/main/imagens/quantidade_vendida.png" alt="faturamento vendas" width="550">
</p>

4. O preço unitário dos produtos também tem uma forte associação com as vendas de alto valor (IV=0,42). Produtos com valores unitários acima de 1500 reais geram vendas de alto valor com apenas um produto vendido. Nas vendas de produtos com faixa de preço unitário entre R$ 785,00 e R$ 1385,00, em média, 35% são de alto valor.

<div align="center">

| Preço Unitário | Taxa |
|---|---:|
| 35-184 | 0,0% |
| 185-334 | 0,4% |
| 335-484 | 3,9% |
| 485-634 | 9,0% |
| 635-784 | 15,3% |
| 785-934 | 33,8% |
| 935-1084 | 37,7% |
| 1085-1234 | 35,1% |
| 1385-1534 | 35,5% |
| 1535-1684 | 97,6% |
| 2135-2284 | 100,0% |
| 2885-3034 | 100,0% |
| 3785-3934 | 100,0% |
| 4385-4534 | 100,0% |
| **Total Geral** | **20,4%** |

</div>

**Observação:** O preço mínimo é R$ 35,00 e o máximo é R$ 4500,00. As faixas de valores tem intervalos de R$ 150,00. Não existem preços unitários entre R$ 1234,00 e R$ 1385,00, entre R$ 1684,00 e R$ 2135,00, entre R$ 2284,00 e R$ 2885,00, entre R$ 3034,00 e R$ 3785,00 e, por fim, entre R$ 3934,00 e R$ 4385,00.

5. Cruzando as variáveis quantidade de produtos vendidos e preço unitário, temos que 70,45% da vendas de alto valor ocorrem com a venda de até dois produtos com preços unitários acima de 850 reais enquanto que apenas 12,5% das vendas de alto valor ocorrem com mais de dois produtos vendidos com preço unitário abaixo de 850 reais.

<p align="center">
  <img src="https://raw.githubusercontent.com/ewerton-lemes/analise-comercial-vendas/main/imagens/vendas_alto_valor.png" alt="faturamento vendas" width="500">
</p>

6. A probabilidade de uma venda de alto valor ocorrer com até dois produtos com preço unitários acima de 850 reais é de 69%, enquanto que é de apenas 25,7% em vendas com produtos com quantidade acima de 2 e preço abaixo de R$ 850,00.

<p align="center">
  <img src="https://raw.githubusercontent.com/ewerton-lemes/analise-comercial-vendas/main/imagens/probabilidades.png" alt="faturamento vendas" width="450">
</p>

7. A categoria possui uma associação importante com as vendas de alto valor (IV=0,78). Cerca de 52% das vendas de Eletrônicos correspondem a vendas de alto valor. Nas categorias de Informática e Mobiliário esses valores são 28% e 20%.

<div align="center">

| Categoria | Taxa de Alto valor |
|---|---:|
| Acessórios | 0,0% |
| Eletrodomésticos | 4,7% |
| Eletrônicos | 52,4% |
| Informática | 28,2% |
| Mobiliário | 20,1% |

</div>

8. Mais de 75% do faturamento estão em apenas 11 produtos. Mais de 50% do faturamento estão em apenas 4 produtos.

<p align="center">
  <img src="https://raw.githubusercontent.com/ewerton-lemes/analise-comercial-vendas/main/imagens/produtos_faturamento.png" alt="faturamento vendas" width="550">
</p>

9. Os descontos não apresentam associação relevante com as vendas de alto valor. Um total de 79,5% das vendas de alto valor não receberam desconto.

<div align="center">
  
| Desconto| % em vendas de alto valor |
|---|---:|
| 10% | 4,5% |
| 5% | 16,0% |
| 0% | 79,5% |

</div>

Além disso, o número de vendas de alto valor corresponde a 20,4% do quantidade total de vendas e, restringindo às vendas que tiveram desconto, temos 21% de vendas de alto valor, ou seja, os resultados não indicam que a concessão de descontos esteja associada a uma maior ocorrência de vendas de alto valor.

10. A categoria de acessórios é a segunda categoria com maior quantidade de vendas (24,2%) porém é a que menos participa do faturamento total com apenas 4% de participação.

<p align="center">
  <img src="https://raw.githubusercontent.com/ewerton-lemes/analise-comercial-vendas/main/imagens/grafico_barras.png" alt="faturamento vendas" width="650">
</p>

11. Um percentual de 63,04% dos clientes apresentam simultaneamente baixa frequência de compras e baixo ticket médio. Além disso, a probabilidade de um cliente apresentar ticket alto é de 46,17% entre aqueles com alta frequência, contra 20,82% entre os de baixa frequência. 

# Resposta da pergunta de negócio

Parte A: Quais características estão associadas às vendas de maior valor?

Diante desses fatos, podemos concluir que as vendas de alto valor, acima de R$ 1500,00 estão predominantemente associadas a vendas de quantidade baixa de produtos e valores altos de preços unitários. Embora a quantidade de produtos também apresente forte associação com o alto valor, o cruzamento das variáveis indica que o preço unitário possui papel particularmente importante, 70,45% das vendas de alto valor ocorrem em transações com até dois produtos e preço unitário superior a R$850.


Parte B:
Quais segmentos apresentam oportunidades de crescimento?

Os resultados sugerem que a frequência de compra está associada a uma maior ocorrência de tickets altos. Dessa forma, clientes de baixa frequência e baixo ticket podem representar uma oportunidade para estratégias de aumento da frequência de compras.

Adicionar produtos de maior valor na categoria de acessórios, pois é bastante procurada, tem uma variação preço muito pequena, com média de 131,74 reais e baixa participação no faturamento.

Há uma dependência muito alta de apenas 4 produtos responsáveis por mais de 50% do faturamento. Seria bom criar planos para não depender somente desse produtos.


