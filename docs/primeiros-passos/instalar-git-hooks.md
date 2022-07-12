## 1. O que são Git hooks?

[Git hooks](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks) são 
scripts personalizados executados antes ou depois de comandos
do Git. Servem para garantir que a base de código mantenha certo de nível de
qualidade e que segue alguns padrões. 

Casos de uso para hooks:

- executar lint para forçar que o código siga um estilo definido (antes de `git commit`)
- executar lint na mensagem de commit (antes de `git commit`)
- rodar testes unitários (antes de `git commit`)
- rodar testes de integração (antes de `git push`)

## 2. Instalação

Para os repositórios SMI-Master e SMI-Slave, é usado o 
[pre-commit](https://pre-commit.com/) como framework para instalar e executar
hooks. Por enquanto, utilizamos apenas o 
[commitizen](https://github.com/commitizen/cz-cli), configurado para forçar que
as mensagens de commit sigam o padrão do [Conventional Commits](./conventional-commits.md).

Certifique-se que você tem Python 3.6+ instalado em seu computador.

Assumindo que você executa os comandos Git _fora_ do ambiente do container Docker,
entre na raíz do repositório desejado:

```sh
cd <caminho para o repo no seu PC>/smi-master 
# ou 
cd <caminho para o repo no seu PC>/smi-slave
```

Instale as dependências e o hook:

```sh
pip install -r requirements-dev.txt
pre-commit install --hook-type commit-msg
```

<!-- 
TODO: adicionar o restante das instruções. Pode ser que esse
documento vire, no futuro, algo do tipo "Monte seu ambiente 
de desenvolvimento"

No futuro, ## 2. Instalação vai ter duas subseções
### 2.1. Projetos Python (Master, Slave)
texto atual

### 2.2. Projetos JavaScript (Front, Mobile)
explicar como instalar Husky
-->