# Comparador de compras e estoque

Painel em uma única página HTML que transforma pedidos de compra em informação para decidir: **quanto foi pago, para quem, se o preço subiu e quem vende mais barato**.

**[Abrir a demonstração](https://jadielluis-santos.github.io/Comparador-de-compras-e-estoque/)** · todos os dados são fictícios

## O problema

Num setor de compras, eu repetia as mesmas cotações e não tinha um histórico fácil de consultar. Os preços ficavam espalhados em PDFs de pedido, então não dava para ver rapidamente:

- se um item estava mais caro do que na última compra;
- qual fornecedor cobrava menos pelo mesmo material;
- onde o gasto se concentrava;
- o que precisava ser reposto.

## A solução

- **Leitura de pedidos em PDF:** extrai fornecedor, itens, quantidades, preços, desconto, IPI e frete. Também aceita lançamento manual.
- **Preço líquido real:** o desconto, as outras despesas e o frete do rodapé do pedido são rateados entre os itens pelo valor de cada um.
- **Oscilação de preço:** compara cada compra com a anterior do mesmo código, com tolerância ajustável.
- **Comparativo de fornecedores:** mostra a diferença entre o menor e o maior preço médio pago pelo mesmo material e calcula quanto foi pago acima do menor preço.
- **Curva ABC e gasto por fornecedor.**
- **Estoque:** itens abaixo do mínimo com sugestão de compra e fornecedor, saldo negativo, itens parados há mais de um ano, inativos com saldo e inventário divergente.
- **Exportação em CSV.**

## O que a demonstração encontra

Com 118 pedidos fictícios de julho a outubro de 2026:

- Fornecedores cobrando de 39% a 60% a mais pelo mesmo item (fita dupla face, fonte de LED, tinta esmalte, corrediça, acrílico).
- Alta de preço da chapa ACM e do módulo de LED a partir de setembro.
- Cerca de R$ 19 mil pagos acima do menor preço disponível no período.
- 15 itens abaixo do estoque mínimo, com sugestão de reposição.

## Como foi feito

Eu defini o problema, as regras de negócio (rateio, oscilação, critérios de reposição) e testei com pedidos reais no meu trabalho. O código foi desenvolvido com apoio de IA (Claude).

Esta versão pública usa **apenas dados inventados**: empresas, fornecedores, itens e preços não são reais.

**Ferramentas:** HTML, CSS, JavaScript e PDF.js. Roda direto no navegador, sem servidor e sem instalação.

## Como usar

Baixe o `index.html` e abra no navegador, ou acesse o link da demonstração. O que você lançar fica só na aba aberta e some ao recarregar.
