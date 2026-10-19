# Separação H2O Conex

Sistema de conferência de separação de pedidos: lê o PDF do pedido de venda do GestãoClick, imprime a lista de separação e as etiquetas de prateleira (Code 128) e confere a separação com leitor de código de barras.

Endereço: https://h2oconex-brazil.github.io/separacao-h2oconex/

## Arquivos
- `index.html`: o sistema inteiro (bibliotecas de PDF e código de barras já embutidas).
- `manifest.webmanifest` e ícones: permitem instalar como aplicativo.
- `sw.js`: guarda uma cópia para uso sem internet e entrega as atualizações.
- `produtos.csv` (opcional): cadastro oficial de produtos (codigo;descricao;local). Quando existe, todos os aparelhos usam ele.

## Fluxo de separação
1. Carregar o PDF do pedido (GestãoClick) e imprimir a lista de separação.
2. Para cada item, na ordem do papel: bipar o código do item no papel → bipar a etiqueta da prateleira → contar → OK (código OK do papel, botão ou Enter).
3. O papel usa códigos próprios por item (ex.: P116I01) e a prateleira usa o código do produto (ex.: CRM1214). Por isso bipar o papel duas vezes não libera o item.

## Como publicar uma versão nova
1. Troque o número da versão em `index.html` (cabeçalho) e em `sw.js` (`VERSAO`).
2. Suba os arquivos alterados no GitHub com uma descrição do que mudou.
3. Em até 2 minutos o site atualiza. Nos aparelhos, a versão nova entra ao abrir o app com internet.

## Onde ficam os dados
Cadastro de produtos, pedidos e histórico ficam no navegador de cada aparelho (não vão para o GitHub). Baixe o CSV do histórico de tempos em tempos.

## Histórico de versões
- v1.2.2: "Encerrar com pendência" mostra a confirmação na tela e some quando a conferência já terminou.
- v1.2.1: lista de pedidos com nome longo não desalinha mais a situação.
- v1.2.0: fluxo papel → prateleira → contagem → OK; importação/exportação do cadastro; produtos.csv como cadastro oficial.
- v1.1.0: app instalável e funcionamento offline.
- v1.0.0: primeira versão (leitura do PDF, lista de separação, etiquetas, conferência e histórico).
