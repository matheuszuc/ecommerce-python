# Análise de Dados de E-commerce com Python

Este projeto tem como objetivo realizar a limpeza, tratamento e análise de uma base de pedidos de e-commerce, utilizando Python para gerar indicadores de negócio, identificar padrões de vendas e visualizar os resultados por meio de gráficos.

O foco do projeto é simular uma análise próxima de um cenário real, passando por etapas como verificação da qualidade dos dados, correção de inconsistências, criação de KPIs e geração de insights para apoiar decisões.

---

## Objetivo do Projeto

Analisar os pedidos de uma operação de e-commerce para responder perguntas como:

- Qual foi o faturamento total e líquido?
- Quais categorias geraram mais receita?
- Quais produtos mais contribuíram para o faturamento?
- Qual foi a taxa de cancelamento?
- Quais formas de pagamento geraram mais faturamento?
- Quais estados tiveram maior faturamento?
- Quais estados tiveram maior quantidade vendida?
- Como o faturamento variou ao longo dos meses?

---

## Ferramentas Utilizadas

- Python
- Pandas
- Matplotlib
- Jupyter Notebook

---

## Estrutura do Projeto

```bash
├── ecommerce_pedidos.csv
├── ecommerce_pedidos_limpo.csv
├── limpeza.ipynb
├── analise_insights.ipynb
├── grafico_faturamento_mensal.png
├── grafico_faturamento_categoria.png
├── grafico_faturamento_estado.png
├── grafico_pagamento.png
├── grafico_status_pedidos.png
├── grafico_top_produtos.png
├── grafico_quantidade_vendida_estado.png
└── README.md
```

---

## Etapas da Análise

### 1. Importação dos dados

A base foi carregada a partir de um arquivo CSV contendo informações sobre pedidos, clientes, produtos, categorias, estados, formas de pagamento, status dos pedidos e datas.

---

### 2. Limpeza dos dados

Durante a etapa de limpeza, foram realizados os seguintes tratamentos:

- Verificação de valores nulos.
- Preenchimento de campos ausentes em `cliente`, `estado` e `pagamento` com `Não informado`.
- Verificação de duplicatas usando `pedido_id` como identificador único.
- Correção do `valor_total` com base em:

```python
valor_total = quantidade * valor_unitario
```

- Conversão das colunas de data para o formato correto.
- Tratamento de datas de entrega inválidas, sem remover o pedido inteiro da base.
- Criação de colunas auxiliares, como mês, ano, dias de entrega e pedido válido.

---

## Critérios usados nos KPIs

Para evitar distorções nos resultados, os indicadores foram separados em três tipos principais:

| Indicador | Critério |
|---|---|
| Faturamento bruto | Considera todos os pedidos |
| Faturamento líquido | Exclui pedidos cancelados |
| Faturamento entregue | Considera apenas pedidos entregues |

Essa separação é importante porque pedidos cancelados não devem ser tratados como receita real da empresa.

---

## KPIs Principais

| KPI | Resultado |
|---|---:|
| Pedidos totais | 510 |
| Pedidos válidos | 431 |
| Pedidos entregues | 304 |
| Pedidos cancelados | 79 |
| Faturamento bruto | R$ 1.007.678,60 |
| Faturamento líquido | R$ 835.990,70 |
| Faturamento entregue | R$ 606.431,50 |
| Ticket médio líquido | R$ 1.939,65 |
| Itens vendidos | 1.291 |
| Taxa de cancelamento | 15,49% |
| Taxa de entrega | 59,61% |
| Prazo médio de entrega | 8,50 dias |

---

## Análises Realizadas

### Faturamento por mês

Foi analisada a evolução do faturamento líquido ao longo dos meses, permitindo identificar períodos de maior e menor desempenho.

O mês de maior faturamento foi agosto, enquanto junho apresentou um dos menores resultados da base.

---

### Faturamento por categoria

A categoria com maior destaque foi Eletrônicos, representando a maior parte do faturamento líquido.

Isso indica uma forte dependência da empresa em produtos de maior valor agregado.

---

### Produtos com maior faturamento

O produto com maior impacto no faturamento foi o Notebook Dell, ficando muito acima dos demais produtos.

Esse resultado mostra que poucos produtos podem ter grande influência no desempenho financeiro do e-commerce.

---

### Forma de pagamento

A análise por forma de pagamento mostrou quais métodos mais contribuíram para o faturamento líquido.

As opções com maior participação foram cartões, principalmente cartão de débito e cartão de crédito.

---

### Status dos pedidos

A análise dos status permitiu identificar a quantidade de pedidos entregues, pendentes, em trânsito e cancelados.

A taxa de cancelamento foi um ponto de atenção, pois representa uma perda direta de receita potencial.

---

### Faturamento por estado

Também foi analisado o faturamento líquido por estado, considerando apenas pedidos que não foram cancelados.

Essa análise permite identificar quais regiões geraram maior receita para a empresa, não apenas maior volume de pedidos.

O estado de Santa Catarina (SC) apresentou o maior faturamento da base, mesmo não sendo o estado com maior volume de pedidos. Esse comportamento indica que SC pode ter concentrado pedidos de maior valor ou produtos com ticket médio mais alto.

---

### Quantidade vendida por estado

Além da quantidade de pedidos por estado, também foi analisada a quantidade total de unidades vendidas.

Essa análise foi feita somando a coluna `quantidade`, permitindo entender melhor quais estados concentraram maior volume de produtos vendidos.

No caso de SC, o estado ficou entre os maiores volumes de produtos vendidos, mas o principal destaque foi o faturamento. Isso reforça que não basta analisar apenas quantidade, pois um estado pode vender menos unidades ou ter menos pedidos e ainda assim gerar mais receita.

---

## Insights Encontrados

### 1. Eletrônicos concentram a maior parte do faturamento

A categoria Eletrônicos foi responsável pela maior parte do faturamento líquido. Isso mostra que a operação depende bastante de produtos de maior valor.

### 2. Notebook Dell é o principal produto da base

O Notebook Dell foi o produto com maior faturamento, indicando que ele tem papel estratégico nos resultados da empresa.

### 3. Cancelamentos impactam o faturamento

A taxa de cancelamento ficou em aproximadamente 15,5%. Esse indicador merece acompanhamento, pois pedidos cancelados reduzem o faturamento real da operação.

### 4. Cartões geram mais faturamento que outros métodos

Cartão de débito e cartão de crédito tiveram forte participação no faturamento líquido, ficando à frente de outros métodos como PIX e boleto.

### 5. Estados com mais vendas podem indicar regiões estratégicas

A análise de quantidade vendida por estado ajuda a identificar regiões com maior volume de produtos vendidos, o que pode apoiar decisões de estoque, logística e campanhas regionais.

### 6. SC tem o maior faturamento, mesmo sem liderar todos os indicadores de volume

Santa Catarina (SC) foi o estado com maior faturamento líquido da base. Porém, ao comparar com os indicadores de volume, percebe-se que SC não lidera todos eles.

Na análise de quantidade vendida, SC aparece entre os maiores estados em volume de produtos. Já na quantidade de pedidos, SC não é o primeiro colocado. Mesmo assim, o estado lidera em faturamento.

Esse comportamento sugere que SC teve pedidos com maior valor médio, possivelmente por uma maior concentração de produtos de alto valor agregado. Esse é um bom exemplo de por que é importante analisar faturamento, quantidade vendida e número de pedidos separadamente.

---

## Gráficos Gerados

Foram gerados gráficos para facilitar a visualização dos principais resultados:

- Faturamento líquido por mês
- Faturamento líquido por categoria
- Faturamento líquido por estado
- Faturamento líquido por forma de pagamento
- Quantidade de pedidos por status
- Top 10 produtos por faturamento
- Quantidade vendida por estado

---

## Como Executar o Projeto

1. Clone este repositório:

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
```

2. Instale as bibliotecas necessárias:

```bash
pip install pandas matplotlib
```

3. Abra os notebooks no Jupyter:

```bash
jupyter notebook
```

4. Execute primeiro o notebook de limpeza:

```bash
limpeza.ipynb
```

5. Depois execute o notebook de análise:

```bash
analise_insights.ipynb
```

---

## Conclusão

Este projeto mostra um processo completo de análise de dados com Python, começando pela limpeza da base, passando pela correção de inconsistências e finalizando com KPIs, insights e gráficos.

A análise permitiu identificar categorias e produtos mais relevantes, formas de pagamento mais representativas, impacto dos cancelamentos e regiões com maior faturamento e maior quantidade vendida.

Um dos principais aprendizados foi comparar métricas diferentes antes de tirar conclusões. O caso de SC mostra que um estado pode não ser o primeiro em volume de pedidos, mas ainda assim liderar em faturamento, indicando maior valor médio por venda.

O projeto reforça habilidades importantes para a área de dados, como tratamento de dados, criação de indicadores, análise exploratória e comunicação de resultados.

---

## Autor

Desenvolvido por Matheus como projeto de prática em Análise de Dados.
