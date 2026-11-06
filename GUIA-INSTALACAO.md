# Novo tema DonnaGê: guia de instalação na Magazord

Versão 1.1 · 06/11/2026 (novidade: blocos 05 e 06, logo abaixo dos banners)

## O que tem nesta pasta

| Arquivo | O que é |
|---|---|
| `donnage-tema.css` | O visual novo: cores, fontes, topo, menu, títulos, categorias, cards de produto e rodapé |
| `blocos/01-mosaico-categorias.html` | Mosaico com 4 categorias em foto grande |
| `blocos/02-historia-da-marca.html` | Bloco "Nossa história" (Egidiane, Antônio Prado) |
| `blocos/03-faixa-vantagens.html` | Faixa com P ao G8, frete grátis, 6x e 5% no Pix |
| `blocos/04-destaque-masculino.html` | Destaque da linha masculina plus size, em vinho |
| `blocos/05-condicoes-especiais.html` | Faixa fina com frete grátis, 6x, 5% no Pix e troca fácil, logo abaixo dos banners |
| `blocos/06-guia-por-tamanho.html` | "Escolha pelo seu tamanho": botões P ao G8 que levam às peças daquele tamanho |

O CSS já contém o estilo dos blocos. Os blocos só funcionam com o CSS instalado.

---

## Passo 1: instalar o CSS (o mais importante)

A Magazord carrega arquivos CSS próprios da loja pelo recurso **Recursos** (no código do site eles aparecem como `data-resource-name`).

**Atenção:** hoje a loja aponta para um arquivo chamado `basenutribomba.css`, mas esse arquivo não existe mais (o servidor responde "acesso negado"). Então hoje a loja não carrega nenhum CSS próprio. O novo arquivo entra no lugar dele.

1. No painel da Magazord, abra a área de **Recursos / arquivos do layout**. Se não encontrar, peça ao suporte: "quero subir um arquivo CSS próprio da loja, no lugar do basenutribomba.css".
2. Suba o arquivo `donnage-tema.css`.
3. Remova a referência ao `basenutribomba.css`, ou substitua o conteúdo dele pelo do novo arquivo.
4. Abra o site em uma aba anônima e confira. Se nada mudar, limpe o cache (no painel e no navegador).

**Para editar o recado do topo:** no começo do arquivo, troque o texto de `--dg-aviso`. A versão do celular fica na seção 14 (`content: "CUPOM DE BOAS-VINDAS: 10% OFF"`). Desde a versão 1.1, o topo mostra o cupom, porque frete, parcelas e Pix passaram para o bloco 05.

---

## Passo 2: ajustes no painel (sem código)

São configurações que o CSS não faz sozinho.

1. **Menu.** Cadastrar no menu principal: Lançamentos, Feminino, Masculino, Plus Size, Alfaiataria, Inverno e Outlet. Hoje são só três itens.
2. **Banner principal.** Trocar as artes que têm texto escrito na imagem por fotos de campanha limpas, como a da modelo na Serra. Subir uma versão para computador (horizontal) e outra para celular (vertical). O recado de frete e parcelamento já aparece na barra do topo.
3. **Categorias ("Nossas Categorias").** As imagens atuais já são redondas no próprio arquivo, então o CSS não consegue deixá-las retangulares. Escolha uma das opções:
   - trocar as imagens por fotos retangulares em pé (proporção 3x4, ex.: 900x1200). O CSS já transforma o carrossel em mosaico com o nome sobre a foto; ou
   - tirar esse componente e usar o bloco `01-mosaico-categorias.html`.
4. **Vitrines no celular.** Hoje cada vitrine mostra 4 produtos por linha no celular, e os cards ficam muito estreitos. Se o componente permitir, configure **2 produtos por linha no celular**.
5. **Nomes de produto.** Corrigir os produtos que aparecem com código no lugar do nome (ex.: "VESTCURTFLORALJU29679").

---

## Passo 3: colocar os blocos HTML na página inicial

Cada arquivo da pasta `blocos/` é um trecho de HTML pronto para colar.

1. Na edição da página inicial, veja se existe um componente de **HTML / conteúdo livre**.
2. Se existir, crie um componente para cada bloco e cole o conteúdo do arquivo. Ordem sugerida:
   1. Banner principal
   2. **Bloco 05** (condições especiais)
   3. **Bloco 06** (guia por tamanho)
   4. **Bloco 01** (mosaico de categorias)
   5. Vitrine de lançamentos
   6. **Bloco 04** (destaque masculino)
   7. Vitrine masculina
   8. **Bloco 02** (história) e **Bloco 03** (vantagens)
   9. Avaliações

   Os botões do bloco 06 usam os filtros de tamanho da loja (`?derivacao=`), conferidos em 06/11/2026. Se a Magazord recriar os tamanhos, clique em cada botão para conferir se ainda abre o tamanho certo.
3. Se **não** existir componente de HTML, peça ao suporte da Magazord para incluir os blocos, ou transforme o mosaico e o destaque masculino em banners de imagem.

As fotos dos blocos usam imagens que já estão no site. Quando houver fotos de campanha, basta trocar o endereço em `src=""`.

---

## Passo 4: o que depende da Magazord

O cabeçalho **transparente por cima do banner** (igual ao da Principessa) muda a estrutura do cabeçalho, e não só o visual. Isso precisa ser feito pela Magazord ou por um parceiro. Sugestão de pedido:

> "Na página inicial, queremos o cabeçalho transparente sobre o banner principal, com logo e menu em branco, ficando branco com texto escuro ao rolar a página. É o mesmo comportamento do site lojaprincipessa.com.br, que também é Magazord. O restante do visual já está no nosso CSS próprio."

Sem isso, o tema funciona normalmente, com o cabeçalho branco.

---

## O que já foi testado

Em 16/10/2026, o CSS e os blocos foram aplicados no site ao vivo, só no navegador de teste (nada foi publicado), no computador (1440 px) e no celular (390 px). Ficaram certos o topo, o menu, os títulos, os blocos, as vitrines no computador e o rodapé.

**O que não foi testado:** páginas de produto, de categoria, o carrinho e o checkout. O CSS foi escrito para não mexer nelas além de fontes e botões, mas confira depois de instalar.

## Como desfazer

Remova o `donnage-tema.css` dos Recursos e o site volta ao visual atual. Os blocos HTML são componentes separados: é só desativá-los.
