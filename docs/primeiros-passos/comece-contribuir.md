## 1. Como contribuir

Assim como em todos os projetos Open Source, para fazer uma contribuição é necessário escolher uma issue para ser feita, suprir a tarefa que a issue pede e realizar o pull request ao repositório principal.

Com o SIGE não é diferente. Para fazer uma contribuição ao projeto é necessário seguir algumas regras impostas pelo(s) mantenedor(es) do repositório.

## 2. Política de contribuições do SIGE

Para se contribuir com o SIGE é necessário seguir as seguintes regras:

1. Os commits devem estar em português.
2. Os commits devem ser atômicos e significativos, seguindo o padrão especificado pelo [Conventional Commits](conventional-commits.md).
    
    - [Instale os git hooks](instalar-git-hooks.md) de acordo com o projeto.
    
3. O nome da branch em que a alteração será feita deve ter o nome da issue e uma breve descrição a respeito da issue.
4. Quando der assign em uma issue, escreva um comentário dizendo que a mesma está sendo feita.
5. Quando finalizar a issue e fizer o pull request, retorne nos comentários da issue e mencione que existe um pull request aberto para aquela issue.
6. Quando abrir o pull request, mencione (via link) nos comentários do PR a issue que está relacionada a ele.

Após isto basta esperar que a issue seja revisada e aprovada por um mantenedor e pronto, você contribuiu para o projeto.

### 2.1 Política de issues

Antes de abrir uma nova issue, é recomendável consultar um mantenedor do projeto para saber se é uma boa issue para ser resolvida. Caso seja uma boa issue, siga ao template para uma nova funcionalidade ou bug.

```
#Nome da feature

#Descrição

- Descreva brevemente a issue.

#Objetivo

- Descreva o objetivo da issue.

#Contexto adicional

- Adicione qualquer informação necessária para melhor compreensão da issue, como instruções de reprodução do bug ou informações sobre a nova funcionalidade a ser implementada.
```

1. É necessário adicionar as tags (labels) pertinentes para a issue ex "docs", "SIGE-front" , "SIGE-master", "SIGE-slave".
2. Ao abrir um merge request, mencione (via link) nos comentários da issue o MR relacionado a ela.

#### Checklist

Para garantir que sua issue esteja de acordo com o padrão do repositório, utilize este checklist como guia.

- [ ] A issue foi discutida previamente com um mantenedor do projeto.
- [ ] A issue possui um nome significativo.
- [ ] A descrição da issue é clara e concisa.
- [ ] Foram adicionadas tags (labels) relevantes.
- [ ] Foram adicionadas screenshots quando necessárias.
- [ ] A issue segue as políticas de contribuição do projeto.


### 2.2 Política de Branches

Para manter a organização e permitir um fluxo de trabalho adequado, é necessário seguir as seguintes regras ao criar branches:

- A branch master é a branch principal do projeto e contém apenas código estável e funcional. Commits diretos nesta branch são restritos aos mantenedores.

- A branch development é a branch a partir de qual todas as outras devem ser criadas. Qualquer nova funcionalidade implementada/bug corrigido será primeiro inserido na development, testado e somente após revisão será adicionado na master.

- Para cada nova funcionalidade ou correção de bug, deve ser criada uma nova branch a partir da development. O nome da branch deve seguir o padrão: feature/nome-da-funcionalidade ou bugfix/nome-do-bug.

- Para manter um histórico de alterações do projeto, é recomendado que seja utilizada a estratégia de merge no estilo "rebase and merge". 

- Para mais informações consulte o Git Branching Model de Vincent Driessen. https://nvie.com/posts/a-successful-git-branching-model/