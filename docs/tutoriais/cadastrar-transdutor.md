# Como cadastrar um Transdutor e um Slave

O cadastro de um transdutor (medidor) pela interface web (`front`) exige que os
contêineres `front`, `master` e `slave` estejam funcionando e que consigam se
comunicar entre si.

## Procedimento para inicialização dos contêineres para uso local

O procedimento para registro assume que os contêineres nunca foram executados.
Caso os tenha executado anteriormente, não esqueça de limpar os volumes:
verificar os volumes com `docker volume ls`, remover os escolhidos com
`docker volume rm` e apagar as dependências desnecessárias com
`docker volume prune`.

### Modificando o contêiner front

Para execução local, o contêiner `front` deve ser modificado para que possa
acessar o ambiente `master` que será executado localmente, e não o em produção.

Para isso, deve-se alterar o arquivo `src/services/masterApi/http-common.js`
no repositório `front`:

```
import axios from 'axios'

const MASTER = axios.create({
	baseURL: 'http://localhost:8001/'
})

export default MASTER
```

### Iniciando os contêineres

1\. Vá ao diretório do contêiner `slave` e inicialize-o. Isso irá inicializar o
contêiner e a rede que será usada para a comunicação. A inicialização pode
demorar, pois é necessário baixar e processar as dependências.

```
cd smi-slave
docker compose up
```

2\. Vá ao diretório do contêiner `master` e inicialize-o. A inicialização pode
demorar, pois é necessário baixar e processar as dependências.
```
cd smi-master
docker compose up
```

3\. Vá ao diretório do contêiner `front` e inicialize-o. A inicialização pode
demorar, pois é necessário baixar e processar as dependências.
```
cd smi-front
docker compose up
```

## Cadastrando um transdutor (medidor)

O cadastro de um medidor deve ser feito em um endereço específico, e exige que
exista um usuário no sistema. Para isso, devem ser executados os seguintes
passos:

1\. Acesse a interface de gerenciamento Web local em `http://localhost:8080`

2\. Cadastre uma conta de acesso com:
- nome
- email
- senha

3\. Acesse a área administrativa relativa à instalação do sistema, e realize
os cadastros na ordem informada em tela:

1. campus
2. tipos de agrupamentos
3. agrupamentos
4. servidores distribuídos
5. medidores
6. tarifas

### Registrando um novo campus

O registro de um novo **campus** exige que se informe os seguintes dados:

- **Nome:** nome do campus
- **Acrônimo:** acrônimo do campus
- **Latitude:** latitude do campus em graus, usando ponto como caractere decimal
- **Longitude:** longitude do campus em graus, usando ponto como caractere
decimal

### Registrando um novo tipo de agrupamento

O registro de um novo **tipo de agrupamento** exige que se informe os seguintes
dados:

- **Nome:** nome do **tipo de agrupamento**, usado para organizar os
**agrupamentos** que serão criados posteriormente

### Registrando um novo agrupamento

O registro de um novo **agrupamento** exige que se informe os seguintes dados:

- **Nome do grupo:** nome do **agrupamento**, usado para organizar os
**medidores**
- **Tipo do grupo:** nome do **tipo de agrupamento** ao qual este
**agrupamento** pertence

### Registrando um novo servidor distribuído

O registro de um novo **servidor distribuído** (*slave*) exige que se informe os
seguintes dados:

- **Endereço IP:** endereço IPv4 do **servidor distribuído**
- **Porta:** porta do **servidor distribuído**
- **Localização:** termo usado para localizar onde está o
**servidor distribuído**

#### Obtendo o endereço do servidor distribuído

O endereço do *slave* é modificado sempre que a rede criada pelo `smi-slave` é
reiniciada. O seguinte *script*, que usa a ferramenta `jq`, pode ser usado para
identificar o endereço IP atual do *slave* em execução:

```
docker network inspect smi-network | jq '.[].Containers[] | select(.Name == "slave-api").IPv4Address'
```

A porta do servidor distribuído normalmente é a 8000. Isso pode ser confirmado
executando-se o comando `docker container list`.

### Registrando um novo medidor

O registro de um novo **medidor** (*transdutor*) exige que se informe os
seguintes dados:

- **Número de série:** Número de oito caracteres, único para cada medidor
- **Endereço IP:** endereço IP do medidor
- **Porta:** porta do medidor, normalmente 1000
- **Latitude:** latitude do **medidor** em graus, usando ponto como caractere
decimal
- **Longitude:** longitude do **medidor** em graus, usando ponto como caractere
decimal
- **Campus:** **campus** onde o **medidor** está instalado
- **Versão:** versão do *firmware*, normalmente 1.42
- **Nome:** nome do **medidor**
- **Modelo:** modelo do **medidor**, atualmente somente `MD30` ou `TR2040`
- **Grupo:** **grupo** ao qual pertence o **medidor**
- **Servidor distribuído:** *slave* que lerá o **medidor**
- **History:** campo opcional para anotações

### Registrando uma nova tarifa
O registro de uma nova **tarifa** exige que se informe os seguintes dados, além
do **campus** a que ela pertence:

- **Vigência:** data de vigência da tarifa no formato ISO 8601
- **Tarifa fora de ponta:** tarifa em reais, usando ponto como separador decimal
- **Tarifa de ponta:** tarifa em reais, usando ponto como separador decimal