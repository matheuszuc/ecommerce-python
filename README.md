# 🛒 E-commerce — Limpeza e Análise de Dados

## Sobre o Projeto

Projeto criado para estudos. Analisei um dataset fictício de um e-commerce para aprofundar meus conhecimentos em Python e pandas. Nesse projeto utilizei conceitos de **Limpeza de Dados** para tratar dados nulos e inválidos.

Após o tratamento, realizei a exploração dos dados para gerar insights valiosos para a empresa — desde o faturamento total até descobrir quais estados vendem mais em quantidade e se isso se reflete no faturamento.

---

## 🛠️ Ferramentas Utilizadas

- Python 3
- Pandas
- Matplotlib
- Jupyter Notebook

---

## 🔍 Problemas Encontrados e Tratados

1. **Dados Nulos** — Identificados nas colunas `cliente`, `estado` e `pagamento`. Documentados e mantidos para análise.
2. **Entregue sem Data de Entrega** — 12 pedidos com status "Entregue" apresentavam `data_entrega` nula. Documentados.
3. **Dados Duplicados** — 9 linhas duplicadas encontradas e removidas.
4. **Formato de Data Inconsistente** — Datas misturavam os formatos `dd/mm/yyyy` e `yyyy-mm-dd`. Padronizadas para `datetime`.
5. **Valores Impossíveis** — Pedidos com `valor_total` igual a R$ 0,00 ou negativo. Removidos.
6. **Erro de Cálculo** — `quantidade × valor_unitario` diferente do `valor_total` em 20 linhas. Corrigidos.
7. **Data de Entrega Anterior ao Pedido** — Alguns pedidos apresentavam `data_entrega` anterior à `data_pedido`. Removidos.

---

## 📊 Insights Gerados

### 🏆 Produtos — Quantidade de Pedidos
![Quantidade por Produto](graficos/quantidade_por_produto.png)

### 💰 Produtos — Faturamento Total
![Faturamento por Produto](graficos/faturamento_por_produto.png)

> **Insight:** Tênis Vans é o produto mais vendido em quantidade, mas o **Notebook Dell** lidera o faturamento. O **Óculos Ray-Ban** é o que menos vende, mas é a 3ª maior fonte de receita — perfil premium.

---

### 🗺️ Estados — Quantidade de Pedidos
![Pedidos por Estado](graficos/pedidos_por_estado.png)

### 🗺️ Estados — Faturamento Total
![Faturamento por Estado](graficos/faturamento_por_estado.png)

> **Insight:** **GO** lidera em número de pedidos mas é apenas a 3ª maior fonte de renda. **SC** tem o maior faturamento mas apenas o 6º lugar em quantidade — perfil de cliente premium.

---

### 💳 Formas de Pagamento — Quantidade de Pedidos
![Formas de Pagamento](graficos/formas_de_pagamento.png)

### 💳 Formas de Pagamento — Faturamento Total
![Faturamento por Pagamento](graficos/faturamento_por_pagamento.png)

> **Insight:** **Boleto** é a forma mais utilizada, mas uma das menores em faturamento. **Cartão de Débito** concentra a maior parte da receita.

---

### 💵 Faturamento Total

> **R$ 875.797,80**

---

## ▶️ Como Executar

1. Instale o [VS Code](https://code.visualstudio.com/)
2. Instale o [Python](https://www.python.org/) e o Jupyter Notebook
3. Instale as dependências:
```
pip install pandas matplotlib
```
4. Execute o arquivo `limpeza.ipynb`
5. Execute o arquivo `analise_insights.ipynb`

---

## 👤 Autor

**Matheus** — [github.com/matheuszuc](https://github.com/matheuszuc)
