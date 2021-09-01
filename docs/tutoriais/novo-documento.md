# Como criar e adicionar novos documentos na documentação

Esse tutuorial tem como objetivo explicar o passo a passo para adicionar um novo documento na documentação do projeto.

## Histórico de Versão

|    Data    | Versão | Descrição            | Autor(es)       |
| :--------: | :----: | :------------------: | :-------------: |
| 18/02/2021 |  0.1   | Criação do documento | Durval Carvalho |
| 11/08/2021 |  1.0   | Alteração do gerador da página estática | [Lieverton Silva](https://gitlab.com/lievertom) |

## Configuração de ambiente

A documentação do projeto foi construida utilizando [`Material for MkDocs`](https://squidfunk.github.io/mkdocs-material/). O [`Material for MkDocs`](https://squidfunk.github.io/mkdocs-material/) é um gerador de site estático voltado para documentação de projeto (técnica) a partir de um conjunto de arquivos `Markdown`.

A integração do [`Material for MkDocs`](https://squidfunk.github.io/mkdocs-material/) com o gitlab é feita automaticamente, desse modo, toda vez que um novo commit é adicionado na master é atualizado os arquivos do [`Material for MkDocs`](https://squidfunk.github.io/mkdocs-material/), não sendo necessário nenhuma outra ação para atualizar o site da documentação.

Para executar a aplicação localmente, proceda com os seguintes passos:

1. Instale o Docker [neste link](https://docs.docker.com/install/linux/docker-ce/ubuntu/);
2. Instale o Docker Compose [neste link](https://docs.docker.com/compose/install/);
3. Na pasta raiz do projeto, inicialize: `sudo docker-compose up --build`;
4. Acesso no navegador: http://localhost:8009/.

## Criando novos documentos

A criação de novas páginas na documentação é bastante simples, e envolve somente a escrita de um arquivo `markdown`.

Primeiro analise a estrutura de diretório atual e localize o melhor local para o novo documento.

## Navegação

A configuração das rotas no mkdocs é bastante simples, basta adicionar novos arquivos e mapeá-los na sessão `Content Menu` do arquivo de configuração __mkdocs.yml__ .

## Conclusão

Com essas informações, você já conhece o mínimo necessário para criar novos documentos. O [`MkDocs`](https://www.mkdocs.org/) é uma ferramenta bastante simples e flexível. Para mais informações sobre como criar novos documentos, navegação ou links, acesse a [documentação oficial do `MkDocs`](https://www.mkdocs.org/user-guide/writing-your-docs/).
