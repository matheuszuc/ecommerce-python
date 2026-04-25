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

- 🏆 **Produto mais vendido em quantidade:** Tênis Vans
- 💰 **Produto que mais fatura:** Notebook Dell
- 💎 **Produto premium:** Óculos Ray-Ban — pouco vendido mas 3ª maior fonte de receita
- 🗺️ **Estado com maior faturamento:** SC — porém apenas 6º em quantidade de pedidos
- 📦 **Estado com mais pedidos:** GO — mas apenas 3ª maior fonte de renda
- 💳 **Pagamento mais utilizado:** Boleto — porém menor faturamento por pedido
- 💳 **Maior faturamento por pagamento:** Cartão de Débito
- 💵 **Faturamento total:** R$ 875.797,80

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