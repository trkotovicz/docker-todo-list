# Boas-vindas ao repositório do projeto Docker Todo List!

Projeto desenvolvido no módulo de BackEnd, do curso de desenvolvimento web da Trybe.
Neste projeto foi colocado em prática os conhecimentos Docker para:
- **_Conteinerizar_** aplicações;
- Criar uma conexão entre elas;
- Orquestrar seu funcionamento.

Temos uma aplicação full-stack neste repositório: um **aplicativo de tarefas**! _(desenvolvida pela Trybe)_
Esta aplicação foi conteinerizada para funcionar. Foi desenvolvido os arquivos de configuração para cada frente específica: `Front-end`, `Back-end` e para um aplicativo de `teste` que valida se as aplicações estão se comunicando.

---
## O que foi desenvolvido

Foram desenvolvidos os comandos do CLI para os requisitos abaixo.

Cada comando foi escrito em um arquivo próprio. Você poderá acessar os arquivos e comandos relacionados ao Docker, dentro do diretório `docker`, onde encontrará:
- o `docker-commands` (um diretório com todos os comandos do CLI *(Interface de Linha de Comando)* do Docker que resolve seu respectivo requisito)
- o diretório `todo-app` (onde se encontra a aplicação para as frentes de _front-end_, _back-end_ e _testes_ e um arquivo `Dockerfile` para cada frente)
- e o arquivo `docker-compose.yml`.

### Requisitos

1. Crie um container em modo interativo, sem rodá-lo, nomeando-o como `01container` e utilizando a imagem `alpine` na versão `3.12`
2. Inicie o container `01container`
3. Liste os containers filtrando pelo nome `01container`
4. Execute o comando `cat /etc/os-release` no container `01container` sem se acoplar a ele
5. Remova o container `01container`
6. Faça o download da imagem `nginx` com a versão `1.21.3-alpine` sem criar ou rodar um container
7. Rode um novo container com a imagem  `nginx` com a versão `1.21.3-alpine` em segundo plano nomeando-o como `02images` e mapeando sua porta padrão de acesso para porta `3000` do sistema hospedeiro
8. Pare o container `02images` que está em andamento
9. Gere uma build a partir do Dockerfile do `back-end` do `todo-app` nomeando a imagem para `todobackend`
- O arquivo `Dockerfile` deverá ter as seguintes configurações:
  - Deve rodar uma imagem `node` utilizando a versão `14`;
    - Recomenda-se o uso da variante `-alpine`, pois ela é otimizada para desempenho;
  - Deve estar com a porta `3001` exposta;
  - Deve adicionar o arquivo `node_modules.tar.gz` a imagem;
  - Deve copiar todos os arquivos da pasta `back-end` para a imagem;
  - Ao iniciar a imagem deve rodar o comando `npm start`.
  - Ao *buildar* o Dockerfile, o nome da imagem gerada deve ser igual a `todobackend`.
10. Gere uma build a partir do Dockerfile do `front-end` do `todo-app` nomeando a imagem para `todofrontend`
- O arquivo `Dockerfile` deverá ter as seguintes configurações:
  - Deve rodar uma imagem `node` utilizando a versão `14`;
    - Recomenda-se o uso da variante `-alpine`, pois ela é otimizada para desempenho;
  - Deve estar com a porta `3000` exposta;
  - Deve adicionar o arquivo `node_modules.tar.gz` a imagem, de maneira que ele seja extraído dentro do `container`;
  - Deve copiar todos os arquivos da pasta `front-end` para a imagem;
  - Ao iniciar a imagem deve rodar o comando `npm start`;
  - Ao *buildar* o Dockerfile, o nome da imagem gerada deve ser igual a `todofrontend`.
11. Gere uma build a partir do Dockerfile dos `testes` do `todo-app` nomeando a imagem para `todotests`
- O arquivo `Dockerfile` deverá ter as seguintes configurações:
  - O Dockerfile deve rodar a imagem `mjgargani/puppeteer:trybe1.0` para que os testes funcionem;
  - Deve adicionar o arquivo `node_modules.tar.gz` a imagem;
  - Deve copiar todos os arquivos da pasta `tests` para a imagem;
  - Ao iniciar a imagem deve rodar o comando `npm test`;
  - Ao *buildar* o Dockerfile, o nome da imagem gerada deve ser igual a `todotests`.
**Docker-compose**
12. Suba uma orquestração em segundo plano com o docker-compose de forma que `backend`, `frontend` e `tests` consigam se comunicar
