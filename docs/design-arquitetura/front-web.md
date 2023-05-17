# Arquitetura - Front Web

#### Histórico de versão

| Data       | Versão | Descrição                        | Autor          |
| ---------- | ------ | -------------------------------- | -------------- |
| 09/02/2022 | 0.1    | Ajuste dos tópicos do documentos | Leonardo Gomes |
| 10/02/2022 | 1.0    | Criação de tópico de tecnologias | Leonardo Gomes |

### 1. Visão geral

O Sistema de Gestão Energética SIGE-UnB, desenvolvido pela Universidade de Brasília (Brasil) em parceria com a CEB (Companhia Energética de Brasília), é um aplicativo web desenvolvido para auxiliar no monitoramento e gerenciamento do consumo de energia da Universidade de Brasília e distribuição.

### 2. Estrutura de pastas

```mark-down
.
|_deploy
  |_production
  |_staging
|_scripts
|_src
  |_assets
  |_boot
  |_components
    |_charts
    |_dashboard
      |_cards
  |_css
  |_layouts
  |_mixins
  |_pages
    |_Campi
    |_Groups
    |_Slave
    |_Transductor
  |_router
  |_services
    |_masterApi
    |_ssr-import
  |_statics
    |_icons
  |_store
    |_module-consumptionCurse
    |_module-totalCost
    |_module-transductor
    |_module-user
  |_utils
|_src-ssr
```

- `deploy`: Armazena arquivos yml compose com imagens de staging e prod
- `scripts`: Armazena shortcuts para facilitar construção dos arquivos compose
- `src`
  - `assets`: Contém arquivos estáticos utilizados na plataforma (deprecated)
  - `boot`: Contém scripts de funcionalidades estruturais do projeto
  - `components`: Contém os components visuais da aplicação
  - `css`: Contém a folha de estilo do projeto
  - `layouts`: Contém wrapper components da aplicação, utilizados para autenticar e definir funcionalidades padrões do projeto.
  - `pages`: Contém page components que serão utilizados principalmente para navegação das páginas
  - `router`: Contém as rotas do projeto
  - `services`: Contém os endpoints para comunicação com a api
  - `statics`: Contém arquivos estáticos utilizados na plataforma
  - `store`: Contém os contextos que rodeiam o projeto
  - `utils`: Contém funções auxiliares a plataforma
- `src-ssr`: Contém arquivos que serão executado via server side

### 3. Arquitetura

Nós estamos utilizando `Vue.js`, uma biblioteca javascript que tem focado na camada [ViewModel](https://012.vuejs.org/guide/#ViewModel) do padrão MVVM. Ele conecta a View e a Model por meio de ligações de dados bidirecionais. As manipulações reais do DOM e a formatação de saída são abstraídas em `diretivas` e `filtros`.

![mvvm](../assets/images/mvvm.png)

### 4. Tecnologias

#### 4.1 Vue

Segundo a documentação do proprio Vue.js é uma estrutura progressiva para construir interfaces de usuário. Este é um framework que utiliza componentes, que utilizam de props e Eventos para se comunicar.

Para mais informações relacionadas a o framework Vue.js segue o link da sua [documentação](https://vuejs.org/v2/guide/).

#### 4.2 Quasar

Segundo o [wikipedia - quasar](https://en.wikipedia.org/wiki/Quasar_framework) Quasar é um framework de open source que tem como base Vue.JS que é utilizado para a construção de aplicativos, com uma única base de código, e ainda assim permite implantar na Web algumas tecnologias como SPA, PWA, SSR, para um aplicativo móvel, para este projete é utilizado o SSR.

Para mais informações relacionadas a o framework Quasar Vue.js segue o link da sua [documentação](https://quasar.dev/).
