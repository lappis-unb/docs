# Arquitetura - Mobile

#### Histórico de versão

| Data       | Versão | Descrição                   | Autor              |
| ---------- | ------ | --------------------------- | ------------------ |
| 09/02/2022 | 0.1    | Ajuste dos documento        | Matheus Estanislau |
| 09/02/2022 | 1.0    | Adicionado item Tecnologias | Matheus Estanislau |

### 1. Visão geral

O SIGE (Sistema de Gestão Energética da Universidade de Brasília) mobile tem como foco fornecer dados de maneira rápida em campo para funcionarios que assim desejam. Para sua criação é utilizado PWA, isentando a necessidade de baixar um aplicativo para ter acesso ao Sige, ele é construido com o framework [Vue.js](https://vuejs.org/v2/guide/), juntamente javascript, html e Sass.

### 2. Estrutura de pastas

```
|_ deploy
  |_ production
  |_ staging
|_ images
|_scripts
|src
  |_ assets
  |_ boot
  |_ components
  |_ css
  |_ layouts
  |_ pages
  |_ router
  |_ services
    |_ firebaseAPI
    |_ masterApi
    |_ ssr-import
  |_ statics
    |_ icons
  |_ store
    |_ module-campus
    |_ module-notification
    |_ module-tab
  |_ utils
|_ src-pwa
|_ src-ssr
```

- `deploy`: Diretório responsável pelo arquivos de deploy da aplicação, tanto para desenvolvimento quanto produção.
- `src`: Diretório onde ficam contidos os arquivos principais da aplicação, responsável pelo código fone.
  - `assets`: Diretório onde ficam contidos as imagens utilizadas dentro da aplição.
  - `boot`: Diretório que contém arquivos de inicialização do firebase e do redux persist
  - `components`: Diretório que contém os componentes visuais que serão reutilizados na aplicação
  - `css`: Diretório que contém os arquivos de configuração de estilizção globais
  - `layouts`: Diretório utilizado para definir funcionalidades padrões do projeto
  - `pages`: Diretório que contém arquivos que serão utilizados para renderização das páginas do projeto
  - `router`: Diretório que contém arquivos responsáveis pela configuração das rotas
  - `services`: Diretório que contém arquivos de configuração com a apis utilizadas no projeto
  - `statics`: Diretório que contém arquivos de icones e imagens utilizados na aplicação
- `store`: Diretório que contém arquivos de inicializão e configuração da biblioteca de gerenciamento global de estados da aplicaçao
  - `utils`: Diretório que contém funções utilitárias que serão utilizas na aplicação
- `src-pwa`: Diretório que contém arquivos de configuração PWA
- `src-ssr`: Diretório que contém arquivos de configuração SSR

### 3. Arquitetura

![mvvm](../images/mvvm.png)

Nós estamos utilizando Vue.js, uma biblioteca javascript que tem focado na camada [ViewModel](https://012.vuejs.org/guide/#ViewModel) do padrão MVVM. Ele conecta a View e a Model por meio de ligações de dados bidirecionais. As manipulações reais do DOM e a formatação de saída são abstraídas em diretivas e filtros.

### 4. Tecnologias

#### 4.1. Vue

Segundo a documentação do proprio Vue.js é uma estrutura progressiva para construir interfaces de usuário. Este é um framework que utiliza componentes, que utilizam de props e Eventos para se comunicar.
Para mais informações relacionadas a o framework Vue.js segue o link da sua [documentação](https://vuejs.org/v2/guide/).

#### 4.2. Quasar

Segundo o [wikipedia - quasar](https://en.wikipedia.org/wiki/Quasar_framework) Quasar é um framework de open source que tem como base Vue.JS que é utilizado para a construção de aplicativos, com uma única base de código, e ainda assim permite implantar na Web algumas tecnologias como SPA, PWA, SSR, para um aplicativo móvel, para este projete é utilizado o PWA. Para mais informações relacionadas a o framework Quasar Vue.js segue o link da sua [documentação](https://quasar.dev/).

#### 4.3. PWA

Como é descrito no [wikipedia - PWA](https://en.m.wikipedia.org/wiki/Progressive_web_application) o PWA (progressive web application) consiste de um software de aplicativo que é distribuido pela web. Tendo como objetivo funcionar como esperado pelo desenvolvedor utilizando qualquer navegador compátivel com os padrões, seja desktop ou dispositivos móveis.
