# Projeto EBAC - Restaurante com Bootstrap

## Menu
[Aula 1 - Navbar](#aula-1---navbar)  

## Aula 1 - Navbar
### Descrição Geral
Este projeto foi desenvolvido como parte das aulas da EBAC, com o objetivo de praticar e aplicar os conhecimentos adquiridos sobre HTML, CSS e, principalmente, Bootstrap. O foco principal é construir cerca de 85% do layout utilizando Bootstrap, com apenas pequenas intervenções em CSS puro.

### Etapas do Projeto

#### 1. Estrutura Inicial
O início do projeto foi básico: criação do arquivo HTML e do CSS, seguido da importação do Bootstrap. Desta vez, utilizamos a importação diretamente pela internet (CDN), sem baixar os arquivos ou criar uma pasta `lib` local.

#### 2. Header e Menu
Após importar algumas classes, iniciamos a construção do `header`. Dentro da tag `header`, foi criada uma `div.container` contendo um `h1` com o nome do restaurante (no caso "Restro", como nome provisório). Esse `h1` recebeu a classe `navbar-brand`, que já estiliza adequadamente o título com o padrão do Bootstrap.

Na sequência, seguimos o padrão já utilizado em projetos anteriores:
- Utilização da tag `nav`
- Dentro dela, uma `ul` com a classe `nav nav-pills`
- Cada `li` com a classe `nav-item`
- E dentro da `li`, um `a` com a classe `nav-link`

O primeiro item do menu recebeu também a classe `active`, para destacar visualmente o item selecionado, como se estivesse com efeito de `hover`.

#### 3. Fixação do Menu
Durante o estudo sobre o Bootstrap avançado, vimos que era necessário fixar o menu no topo da página. Em projetos anteriores, isso foi feito manualmente, usando CSS com `sticky`, `top-0`, `start-0` (ou `left-0`, conforme a versão), e `z-index` ajustado (ex: `1200` ou `1300`) para garantir prioridade de exibição.

Neste projeto, adotamos uma solução mais prática, utilizando diretamente a classe `sticky-top`, que já resolve esse comportamento sem a necessidade de escrever CSS adicional.

Esse foi o conteúdo coberto na primeira aula do projeto, com base no uso eficiente de Bootstrap e organização dos elementos iniciais da interface.

## Aula 2 - Menu Responsivo
