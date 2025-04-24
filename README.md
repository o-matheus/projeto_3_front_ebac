# Projeto EBAC - Restaurante com Bootstrap

## Menu
[Aula 1 - Navbar](#aula-1---navbar)  
[Aula 1 - Menu responsivo](#aula-2---menu-responsivo)  

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

### Ícones do Bootstrap
Na segunda aula do projeto, começamos a trabalhar com funcionalidades ainda não exploradas, como o uso dos ícones do Bootstrap.

Esses ícones não estão disponíveis por padrão com o primeiro link CDN usado na aula 1. Para utilizá-los, acessamos o site oficial do Bootstrap, buscamos pela seção de ícones e copiamos o CDN disponibilizado na opção *Install*. Esse link é colado no código HTML, assim como o Bootstrap principal.

Para utilizar um ícone, usamos a tag `i`, que antes era usada para itálico, mas agora também é usada para exibir ícones. As classes aplicadas nessa tag são:
- `bi`: indica que estamos usando Bootstrap Icons
- `bi-[nome-do-ícone]`: substituímos pelo nome desejado (ex: `bi-house-door`)

Os ícones foram inseridos dentro das tags `a` dos itens do menu, ao lado do texto. Também utilizamos a classe `me-1` (margin-end) para dar espaçamento entre o ícone e o texto. Os níveis de margem vão de `1` (menor) a `5` (maior).

**Ícones utilizados:**
- Casa: `house-door`
- Calendário: `calendar-check`
- Cartão: `card-text`
- Chat: `chat-left-text`

---

### Estilizações Adicionais
Transformamos os textos dos itens do menu em negrito utilizando a classe `fw-bold` dentro das tags `li`. Também aplicamos *padding* ao cabeçalho com a classe `p-[n]`, onde `n` varia de `1` a `5`, para ajustar o espaçamento.

---

### Responsividade e Menu Hamburger
Para tornar o menu responsivo em telas menores, utilizamos:
- A classe `navbar-expand-lg`, que exibe o menu completo em telas grandes e oculta em telas pequenas.
- Um botão com a classe `navbar-toggler` que ativa o menu *hamburger*
- Dentro desse botão, usamos `span` com a classe `navbar-toggler-icon`, que exibe o ícone do *hamburger*

A `nav` recebeu as classes `navbar-collapse` e `collapse`, e os atributos `data-bs-toggle="collapse"` e `data-bs-target="#menu-nav"`. Também foi definida a `id="menu-nav"` na `nav`.

Quando clicamos no botão, os itens do menu aparecem. Porém, por padrão, ficam um ao lado do outro — o que não é ideal em telas pequenas. Para resolver:
- Adicionamos `d-block` na `ul`, para empilhar os itens.
- Para evitar empilhamento também em telas grandes, usamos o conceito *mobile first* com `d-md-flex`, que aplica `display: flex` a partir do *breakpoint* `md`.

---

### Ajustes Visuais
O título do site e os itens do menu ficaram colados após a aplicação das classes de colapso. Para ajustar o alinhamento, adicionamos à tag `nav` a classe `justify-content-end`, que alinha os itens à direita.

Também fizemos uma alteração no *background* do menu usando o CSS criado anteriormente. A cor foi definida como um branco acinzentado para melhorar o contraste e a visualização.

Por fim, o título do restaurante estava desalinhado devido a uma margem aplicada pela classe `navbar-brand`. Para corrigir, aplicamos a classe `m-0`, que remove a margem e alinha corretamente o título.

