# Projeto EBAC - Restaurante com Bootstrap

## Menu
[Aula 1 - Navbar](#aula-1---navbar)  
[Aula 2 - Menu responsivo](#aula-2---menu-responsivo)  
[Aula 3 - Sobre, carrossel e alterações no menu](#aula-3---sessão-sobre-carrossel-e-ajustes-no-menu)  
[Aula 4 - Eventos - criação de cards](#aula-4---eventos-criação-de-cards)  
[Aula 5 - Cardapio](#aula-5---cardapio)  

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

## Aula 3 - Sessão sobre, carrossel e ajustes no menu.

### 1. Criação da Section "Sobre"
- Criar uma `section` com o atributo `id="sobre"`.

### 2. Construção da Estrutura Inicial do Carrossel
- Dentro da `section`, criar uma `div` com as classes `carousel` e `slide`.
- Dentro dessa `div`, criar outra `div` com a classe `carousel-inner`.
- Dentro da `carousel-inner`, criar uma `div` para cada imagem:
  - Cada `div` de imagem deve ter a classe `carousel-item`.
  - Dentro de cada `carousel-item`, inserir uma imagem (`<img>`).

### 3. Configuração da Imagem Inicial
- Em uma das `divs` `carousel-item`, adicionar também a classe `active`.
- Isso indicará que essa será a primeira imagem mostrada no carrossel.

### 4. Ativação Automática do Carrossel
- Na `div` principal do carrossel (aquela com `carousel` e `slide`), adicionar o atributo `data-bs-ride="carousel"`.

### 5. Controle de Tempo entre as Imagens (Opcional)
- Em cada `carousel-item`, é possível adicionar o atributo `data-bs-interval="tempo_em_milissegundos"`.
- Se não for definido, o tempo padrão é entre 3 e 5 segundos.

### 6. Adição de Controles Manuais (Botões de Navegação)
- Criar dois botões:
  - Botão de voltar: classe `carousel-control-prev`.
  - Botão de avançar: classe `carousel-control-next`.
- Cada botão deve:
  - Ter o tipo `button`.
  - Conter um `span` com a classe de ícone respectiva (`carousel-control-prev-icon` ou `carousel-control-next-icon`).

### 7. Configuração dos Botões
- A `div` principal do carrossel precisa ter um `id`, por exemplo, `id="carouselSobre"`.
- Nos botões, adicionar:
  - `data-bs-target="#carouselSobre"`
  - `data-bs-slide="prev"` para o botão de voltar.
  - `data-bs-slide="next"` para o botão de avançar.

### 8. Criação dos Indicadores do Carrossel
- Criar uma `div` com a classe `carousel-indicators`.
- Dentro dela, adicionar um botão para cada imagem:
  - Definir o tipo como `button`.
  - Adicionar `data-bs-target="#carouselSobre"`.
  - Adicionar `data-bs-slide-to="0"`, `data-bs-slide-to="1"`, etc., respeitando a numeração começando do 0.
  - No botão do slide 0, adicionar a classe `active`.

### 9. Construção da Parte Textual da Section "Sobre"
- Fora da `div` do carrossel, criar uma `div` extra que receberá as classes de espaçamento (`pt-5 pb-5`).
- Dentro dela:
  - Criar uma `div` com a classe `container`.
  - Dentro da `container`, criar uma `div` com a classe `row`.
  - Criar duas colunas:
    - Primeira coluna: `col-md-5`
      - Inserir uma imagem (`<img>`) com as classes `d-block`, `w-100` e `rounded`.
    - Segunda coluna: `col-md-7`
      - Inserir os conteúdos:

#### Sobre o Restaurante
> No coração da cidade, nosso restaurante combina tradição e sofisticação. Oferecemos uma experiência gastronômica única, com pratos preparados cuidadosamente e um ambiente acolhedor, perfeito para encontros especiais e momentos inesquecíveis.

#### Sobre o Espaço
> Nosso espaço foi projetado para oferecer conforto e charme em cada detalhe. Com iluminação aconchegante e decoração refinada, garantimos uma atmosfera ideal tanto para jantares íntimos quanto para celebrações.

#### Características:
- Salão principal com capacidade para até 150 pessoas
- Espaço reservado para eventos privativos
- Área externa com jardim e iluminação especial

### 10. Customizações Visuais
- Criar a classe CSS `.section-title` para aplicar a fonte "Pacifico" (ou uma alternativa cursiva) a todos os títulos.
- Englobar palavras importantes dos títulos (ex: "restaurante", "espaço") dentro de uma tag `<span>`, e definir a cor laranja para esses spans no CSS.
- Definir uma cor de fundo para a section "Sobre", usando a mesma cor aplicada aos itens ativos do menu.

### 11. Implementação do ScrollSpy no Menu
- Englobar todo o conteúdo abaixo do header em uma `div` com:
  - `data-bs-spy="scroll"`
  - `data-bs-target="#cabecalho"`
- No `header`, adicionar `id="cabecalho"`.
- Garantir que as `id`s nas `section`s correspondam aos `href`s dos itens do menu.

## Aula 4 - Eventos, criação de cards

### 1. Estrutura Inicial
- Criar uma `section` com o atributo `id="eventos"` e adicionar as classes `pt-5 pb-5` para espaçamento.
- Dentro da `section`, criar uma `div` com a classe `container`.

### 2. Título da Seção
- Criar uma `row` dentro do `container`.
- Inserir um `h2` com o texto "Para todas as ocasiões":
  - Classe `section-title` para a fonte especial "Pacifico".
  - Classe `text-center` para centralizar o título.
  - A palavra "ocasiões" é envolvida em uma tag `<span>` com a classe `text-colored`, aplicando a cor laranja.

### 3. Criação dos Cards de Eventos
- Criar outra `row` logo abaixo do título, com a classe `mt-4` para adicionar espaçamento superior.
- Cada evento é representado por uma coluna `col-md-4`, utilizando 1/3 do espaço em telas médias ou maiores.

#### Conteúdo de Cada Card
Para cada card:
- Inserir uma imagem:
  - Classes: `d-block w-100 rounded mb-2`.
  - A imagem ocupa toda a largura da coluna e tem bordas arredondadas.
- Inserir um título `h3`:
  - Classes: `section-title text-colored fs-4`.
  - Dentro do `h3`, antes do texto, adicionar um ícone utilizando uma tag `<i>`:
    - Aniversários: `<i class="bi bi-calendar-heart-fill"></i>`
    - Recepção para casamentos: `<i class="bi bi-arrow-through-heart-fill"></i>`
    - Confraternizações: `<i class="bi bi-people-fill"></i>`
- Inserir um parágrafo `<p>` com descrições reais sobre cada tipo de evento:

##### Aniversários
> Celebre momentos especiais com a gente! Nosso espaço oferece o ambiente perfeito para tornar seu aniversário inesquecível, com serviços personalizados e uma atmosfera acolhedora para todos os convidados.

##### Recepção para casamentos
> Realize o sonho do seu grande dia em um espaço que combina charme e sofisticação. Oferecemos uma estrutura completa para recepções, garantindo que cada detalhe da sua celebração seja memorável.

##### Confraternizações
> Compartilhe momentos únicos com quem você mais gosta! Nosso restaurante é ideal para confraternizações empresariais, encontros entre amigos ou comemorações familiares em um ambiente agradável e descontraído.

### 4. Ajustes de Design
- A cor laranja foi padronizada usando a classe `text-colored`, aplicada tanto nos títulos das seções quanto nos títulos dos cards.
- O tamanho da fonte dos títulos dos cards foi reduzido usando a classe `fs-4`.

### 5. ScrollSpy
- A `section` de eventos está devidamente configurada com `id="eventos"` para ser reconhecida pelo `data-bs-spy="scroll"`, permitindo que o menu de navegação destaque corretamente a seção atual ao rolar a página.

## Aula 5 - Cardapio

### 1. Estrutura Inicial
- Criar uma `section` com `id="cardapio"`.
- Aplicar as classes `pt-5 pb-5` para espaçamento superior e inferior.
- Definir o fundo da seção com a mesma cor do "Sobre" (`#ffeae6`).

### 2. Título da Seção
- Inserir um `h2` com as classes `section-title`, `text-center` e `mb-5`.
- Estrutura do título:
  - "Nosso " normal
  - "cardápio" dentro de uma tag `<span class="text-colored">` para aplicar a cor laranja.

### 3. Estrutura de Navegação Lateral (Menu de Categorias)
- Utilizar a tag `<aside>` com classe `col-md-2`.
- Dentro do `aside`, criar uma `<nav>` com as classes `nav`, `nav-pills`, `flex-column`, e `nav-cardapio`.
- Cada categoria do cardápio é um `<button>`:
  - Tipo `button`.
  - Classes: `fw-bold`, `text-start`, `nav-link`, `text-colored`.
  - A primeira categoria ("Bebidas não alcoólicas") inicia com a classe `active`.
- Atributos adicionados aos botões:
  - `data-bs-toggle="tab"`
  - `data-bs-target="#id-correspondente"`

#### Categorias criadas:
- Bebidas não alcoólicas
- Bebidas alcoólicas
- Entradas
- Pratos principais
- Sobremesas

### 4. Conteúdo das Abas (Tab Content)
- Criar uma `div` com a classe `col-md-10` ao lado do `aside`.
- Dentro dela, criar uma `div` com a classe `tab-content`.

#### Cada aba (`tab-pane`) contém:
- Um `id` correspondente ao seu botão de navegação.
- A primeira aba (bebidas sem álcool) recebe também a classe `active`.
- Dentro de cada `tab-pane`, uma `row` que agrupa os itens em `col-md-3`, totalizando 4 itens por linha.

#### Cada item (produto) contém:
- Uma imagem `<img>` com classes `d-block w-100`.
- Um título `<h5>` com as classes `text-colored fw-bold mt-2`.
- Um parágrafo `<p>` com descrição do item (ainda com texto Lorem Ipsum nesta fase).

### 5. Estilizações Específicas para o Cardápio
- Todos os botões de navegação lateral usam a cor laranja (`text-colored`) para itens inativos.
- O item ativo no cardápio usa:
  - Fundo laranja (`background-color: #e15f41`)
  - Texto branco (`color: #fff`)
- Ao passar o mouse sobre os botões:
  - Se for inativo, permanece laranja.
  - Se for ativo, o hover mantém o texto branco.
- Todos os botões estão com fonte em **negrito** (`fw-bold`).
- O texto dos botões é alinhado à esquerda (`text-start`).

### 6. Conclusão
- Finalizada a estrutura do cardápio com funcionamento de abas via Bootstrap.
- Todo o design foi adaptado para manter a identidade visual consistente com as demais seções do projeto.
