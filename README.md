[README.md](https://github.com/user-attachments/files/30367091/README.md)
# Painel — leitor de quadrinhos

Aplicação web de página única (um único arquivo `.html`) para ler quadrinhos digitais direto no navegador, sem precisar instalar nada ou enviar seus arquivos para nenhum servidor.

## O que ela faz

- Abre arquivos **.cbz**, **.cbr**, **.zip** e **.rar**, extraindo as imagens de dentro do arquivo e exibindo-as como páginas de leitura.
- Duas formas de ler: **rolagem contínua** (todas as páginas em sequência, como uma tira longa) ou **página única** (uma página por vez, com navegação por clique/teclado).
- Controle de **zoom** para ajustar o tamanho das páginas.
- Painel de **miniaturas** para pular direto para qualquer página.
- Modo **tela cheia** para leitura sem distrações.
- Todo o processamento acontece **no próprio navegador** — nada é enviado pela internet, o arquivo nunca sai do seu computador.

## Como usar

1. Abra o arquivo `leitor-cbz-cbr.html` em qualquer navegador moderno (Chrome, Edge, Firefox, Safari).
2. Arraste seu arquivo de quadrinho para a área indicada, ou clique em "Escolher arquivo".
3. Aguarde a extração das páginas (uma barra de carregamento mostra o progresso).
4. Leia! Use os controles no topo da tela para trocar o modo de leitura, ajustar o zoom, ver as miniaturas ou entrar em tela cheia.

**Atalhos de teclado** (na tela de leitura):
- `←` / `→` ou `Espaço`: navegar entre páginas (ou rolar, no modo contínuo)
- `F`: alternar tela cheia
- `G` ou `T`: abrir/fechar o painel de miniaturas
- `Esc`: fechar miniaturas ou sair da tela cheia

## Como funciona por baixo dos panos

- É um único arquivo HTML autocontido (HTML + CSS + JavaScript).
- Arquivos `.cbz`/`.zip` são lidos com a biblioteca **JSZip**.
- Arquivos `.cbr`/`.rar` são lidos com a biblioteca **node-unrar-js** (que roda RAR via WebAssembly no navegador).
- Ambas as bibliotecas são carregadas de um CDN público, então é necessário estar conectado à internet ao abrir a página (mesmo que o quadrinho em si seja processado localmente).

## Requisitos

- Um navegador moderno com suporte a JavaScript e WebAssembly.
- Conexão com a internet (apenas para carregar as bibliotecas externas via CDN).

## Limitações conhecidas

- Arquivos RAR protegidos por senha não são suportados.
- Arquivos muito grandes podem demorar mais para extrair, dependendo do navegador e do dispositivo.

---

*Este README descreve o funcionamento geral da aplicação e pode não refletir detalhes de versões futuras.*
