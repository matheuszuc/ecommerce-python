# 🛒 E-commerce — Limpeza e Análise de Dados

## Sobre o Projeto

Projeto criado para estudos. Analisei um dataset fictício de um e-commerce para aprofundar meus conhecimentos em Python e pandas. Nesse projeto utilizei conceitos de **Limpeza de Dados** para tratar dados nulos e inválidos.

Após o tratamento, realizei a exploração dos dados para gerar insights valiosos para a empresa — desde o faturamento total até descobrir quais estados vendem mais em quantidade e se isso se reflete no faturamento.

-----

## 📌 KPIs Principais

|Indicador                           |Valor        |
|------------------------------------|-------------|
|💵 Faturamento Total                 |R$ 875.797,80|
|🏆 Produto com Maior Faturamento     |Notebook Dell|
|📦 Produto Mais Vendido em Quantidade|Tênis Vans   |
|🗺️ Estado com Maior Faturamento      |SC           |
|📍 Estado com Mais Pedidos           |GO           |

-----

## 🛠️ Ferramentas Utilizadas

- Python 3
- Pandas
- Matplotlib
- Jupyter Notebook

-----

## 🔍 Problemas Encontrados e Tratados

1. **Dados Nulos (cliente, estado, pagamento)** — Identificados e mantidos. Não havia como determinar o valor correto sem criar informações fictícias, o que distorceria a análise. Um cliente sem pagamento registrado, por exemplo, pode simplesmente não ter concluído a compra.
1. **Entregue sem Data de Entrega** — 12 pedidos com status “Entregue” apresentavam `data_entrega` nula. Mantidos e documentados pois não há como saber a data real de entrega — criar uma data fictícia seria um erro de análise.
1. **Dados Duplicados** — 9 linhas duplicadas encontradas e **removidas**. Linhas idênticas em cliente, produto, quantidade, valor e data representam registros inválidos.
1. **Formato de Data Inconsistente** — Datas misturavam os formatos `dd/mm/yyyy` e `yyyy-mm-dd`. **Corrigidas** e padronizadas para `datetime`.
1. **Valores Impossíveis** — Pedidos com `valor_total` igual a R$ 0,00 ou negativo foram **removidos**. Um pedido sem valor financeiro não representa uma transação real e interfere diretamente no cálculo de faturamento.
1. **Erro de Cálculo** — `quantidade × valor_unitario` diferente do `valor_total` em 20 linhas. **Corrigidos** recalculando o valor total correto.
1. **Data de Entrega Anterior ao Pedido** — Logicamente impossível: nenhum pedido pode ser entregue antes de ser feito. Registros **removidos**.

-----

## 📊 Insights Gerados

### 🏆 Produtos — Quantidade de Pedidos

![Quantidade por Produto](graficos/quantidade_por_produto.png)

### 💰 Produtos — Faturamento Total

![Faturamento por Produto](graficos/faturamento_por_produto.png)

> **Insight:** Tênis Vans é o produto mais vendido em quantidade, mas o **Notebook Dell** lidera o faturamento. O **Óculos Ray-Ban** é o que menos vende, mas é a 3ª maior fonte de receita — perfil premium.

-----

### 🗺️ Estados — Quantidade de Pedidos

![Pedidos por Estado](graficos/pedidos_por_estado.png)

### 🗺️ Estados — Faturamento Total

![Faturamento por Estado](graficos/faturamento_por_estado.png)

> **Insight:** **GO** lidera em número de pedidos mas é apenas a 3ª maior fonte de renda. **SC** tem o maior faturamento mas apenas o 6º lugar em quantidade — perfil de cliente premium.

-----

### 💳 Formas de Pagamento — Quantidade de Pedidos

![Formas de Pagamento](graficos/formas_de_pagamento.png)

### 💳 Formas de Pagamento — Faturamento Total

![Faturamento por Pagamento](graficos/faturamento_por_pagamento.png)

> **Insight:** **Boleto** é a forma mais utilizada, mas uma das menores em faturamento. **Cartão de Débito** concentra a maior parte da receita.

-----

## ✅ Conclusões e Recomendações

Com base na análise realizada, as seguintes ações são recomendadas para a empresa:

**1. Investigar estados com alto faturamento e baixa quantidade de pedidos**
Estados como SC apresentam ticket médio elevado, indicando clientes com maior poder de compra. Vale entender o perfil desse público e criar estratégias para aumentar o volume de pedidos nessas regiões.

**2. Criar campanhas para produtos premium**
O Óculos Ray-Ban é o produto menos vendido em quantidade, mas ocupa a 3ª posição em faturamento. Uma campanha direcionada para esse produto pode aumentar significativamente a receita sem precisar crescer em volume.

**3. Analisar o comportamento dos usuários de Boleto**
O Boleto lidera em quantidade de uso mas tem menor participação no faturamento total. Isso pode indicar que clientes que pagam por boleto tendem a comprar produtos de menor valor — vale investigar se incentivos como desconto no PIX ou cartão poderiam migrar esse público.

-----

## ▶️ Como Executar

1. Instale o [VS Code](https://code.visualstudio.com/)
1. Instale o [Python](https://www.python.org/) e o Jupyter Notebook
1. Instale as dependências:

```
pip install pandas matplotlib
```

1. Execute o arquivo `limpeza.ipynb`
1. Execute o arquivo `analise_insights.ipynb`

-----

## 👤 Autor

**Matheus** — [github.com/matheuszuc](https://github.com/matheuszuc)
