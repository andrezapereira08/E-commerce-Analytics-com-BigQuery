RESUMO DO PROJETO — E-commerce Analytics com BigQuery

Este projeto consistiu na construção de um Data Warehouse analítico no BigQuery para avaliar o desempenho de vendas, clientes, produtos e eficiência logística de um e-commerce.

Abaixo, o resumo de cada processo realizado:

1. Criação do Data Warehouse (DW)
Contexto

Os dados foram fornecidos em múltiplos arquivos CSV simulado um ambiente transacional: pedidos, itens de pedido, clientes, produtos, regiões e SLA logístico.

Ações

✔ Upload dos dados no BigQuery
✔ Criação do dataset ecommerce_dw
✔ Padronização dos tipos de dados (datas, numéricos e textos)
✔ Criação das tabelas base:

pedidos

itens_pedido

clientes

produtos

regiao

sla_logistica

Resultado

Base sólida para construção de visões analíticas.

2. Construção das Dimensões (Dimensional Model)
Objetivo

Criar tabelas auxiliares para facilitar análises por data, cliente, produto e região.

Ações

✔ dim_calendario: separa ano/mês/dia para análises temporais
✔ dim_cliente: perfil e origem do cliente
✔ dim_produto: categoria, preço unitário
✔ dim_regiao: mapeamento geográfico

Resultado

Modelo mais limpo e preparado para análises OLAP.

3. Criação da Fato de Vendas — fato_pedidos
Objetivo

Centralizar métricas do pedido com tipos corretamente convertidos.

Ações

✔ Conversões com SAFE_CAST
✔ Normalização de campos
✔ Cálculo do tempo de entrega real
✔ Indicador de pedidos dentro/fora do SLA

Resultado

Uma tabela única e pronta para análises de faturamento, KPIs e eficiência.

4. View Analítica Geral — vw_sales_analytics
Objetivo

Unificar dimensões + fatos para análises completas.

Inclui

Dados do pedido

Regionais

Características do produto

Valores de venda

Indicadores de SLA

Resultado

Visão única usada como base para todas as análises posteriores.

5. KPI por Filial — vw_kpi_filial
Objetivo

Criar os principais KPIs de operação por regional.

Métricas calculadas

Faturamento

Total de pedidos

Ticket médio

% de pedidos dentro do SLA

Prazo médio de entrega

Resultado

Dashboard analítico por filial pronto para tomada de decisão.

 6. Análise de Faturamento por Ano/Mês
Objetivo

Visualizar a evolução mensal das vendas.

Inclui

✔ Somatório do valor total
✔ Formatação de mês por extenso
✔ Ordenação cronológica

Resultado

Série temporal completa — ideal para gráficos de tendência.

7. Ranking de Faturamento por Filial
Objetivo

Identificar quais regionais possuem maior potencial comercial.

Resultado

Ranking automático das filiais do maior para o menor faturamento.

8. Análise de SLA – Eficiência Logística
Objetivo

Identificar quais filiais entregam mais dentro do SLA.

Resultado

Percentual por região com ordenação decrescente (melhor performance no topo).

9. Ticket Médio por Canal de Venda
Objetivo

Comparar a qualidade dos canais (APP, Web, Loja Física).

Resultado

APP apresentou maior ticket médio → insights de comportamento do cliente.

 10. Produtos Mais Vendidos
Objetivo

Identificar mix de produtos mais relevantes.

Métricas

Quantidade vendida

Receita por item

Categoria do produto

Resultado

Ranking dos produtos com maior impacto no faturamento.

11. Análise ABC (Curva Pareto de Produtos)
Objetivo

Classificar produtos conforme sua importância no faturamento.

Resultado

Classe A → produtos que representam ~80% da receita

Classe B → próximos 15%

Classe C → cauda longa

Ferramenta poderosa para gestão de estoque e priorização comercial.

12. Dashboard Final — KPIs Integrados
Objetivo

Oferecer visão única do negócio consolidando:

Faturamento

Ticket médio

SLA

Receita por produto

Performance por filial

Evolução mensal

Resultado

Ambiente analítico totalmente funcional pronto para tomada de decisão.

🚀 CONCLUSÃO

Este projeto demonstra:

✔ Construção completa de um DW em BigQuery
✔ Domínio de modelagem dimensional (Star Schema)
✔ Criação de views analíticas e KPIs avançados
✔ Aplicação de conceitos de BI: SLA, ticket médio, ABC, evolução temporal, performance regional
✔ Base ideal para dashboards em Looker Studio, Power BI ou Data Studio
