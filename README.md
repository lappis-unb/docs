# SIGE - Sistema de Gestão Energética 
## Sobre o Projeto
O Sistema de Gestão Energética - Universidade de Brasília (SIGE-UnB), consiste em uma aplicação web desenvolvida para auxiliar o monitoramento e gestão das instalações elétricas das edificações dos campi da Universidade de Brasília. A ideia visa que cada Campus contido na UnB possa ser capaz de utilizar a ferramenta e ter um maior conhecimento de como está o consumo de seus insumos importantes ao longo do tempo, possibilitando, assim, elaborar possíveis estratégias que auxiliem em sua economia.

### Coordenação do Projeto
|        Membro       |            E-mail            |     GitLab     |
|:-------------------:|:----------------------------:|:--------------:| 
|      Loana Velasco     |     loana@unb.br     |   -   |
|      Alex Reis     |     alexreis@unb.br     |   @REIALEX   |
|    Renato Coral     | renatocoral@unb.br | @renatocoral |


### Equipe
|        Membro       |            E-mail            |     GitLab     |
|:-------------------:|:----------------------------:|:--------------:| 
|      Álax Alves     |     alaxallves@gmail.com     |   @alaxalves   |
|    André de Sousa   |  andre.filho001@outlook.com  |  @andre-filho  |
|     Arthur Assis    |    arthur120496@gmail.com    |  @arthur0496   |
| Ezequiel de Oliveira | ezequiel1de1oliveira@gmail.com | @EzequielDeOliveira | 
| Gabriela Guedes | gabrielabguedes@gmail.com | @gabibguedes |
|  Guilherme Augusto  | guilherme.francais@gmail.com |  @guiaugusto   |
|    Lucas Martins    |  lucasamartins465@gmail.com  |  @lucasmartins |
| Renato Britto Araujo | renatobritto@protonmail.com | @renatoba |
|    Rodrigo Maia     | contato@rodmaia.com.br | @rodmaia |
|   Thalisson Melo    |   tallisonmelo@hotmail.com   | @thalissonmelo |

## Como subir 

Para criar o network é necessário subir o ambiente do slave primeiro. Para subir cada um dos ambientes rode o comando abaixo em cada um dos repositórios:
``` sh
docker-compose up
```
Se você não tem interesse em subir o ambiente do slave, basta criar um network para conectar com os outros ambientes, para isso rode o seguinte comando:
``` sh
docker network create smi-network
``` 
E suba o ambiente que preferir com:
``` sh
docker-compose up
```
Para ter a conexão do master com o slave é necessário cadastra-lo, para isso siga o seguinte [tutorial](./tutoriais/como-cadastrar-transdutor).

## Arquitetura
- **TODO: imagem da arquitetura representando cada serviço e suas conexões**

### Tecnologias do Projeto
- [VueJS](https://vuejs.org/) - Usado na implementação do frontend do projeto
- [Django REST](https://www.django-rest-framework.org/) - Usado para implementar as APIs master e slave
- [PostgreSQL](https://www.postgresql.org/) - Utilizado para o Banco de Dados do master e slave

### Front
Apresenta dashboards para analisar os dados coletados pelos transdutores. Os dados do frontend são coletados a partir do master.

Para saber mais sobre este módulo acesse [FrontEnd](./frontend/home)

### Master
O master fornece os dados coletados para o frontend. Seus dados são coletados a por conexões periódicas com o slave.

As conexões com o slave são feitas nos tempos:
- **TODO: especificar os tempos que o master conecta com o slave**

Para saber mais sobre este módulo acesse [Master](./master/home)  
### Slave
O slave fornece os dados coletados para o master. Seus dados são coletados a partir de conexões periódicas com os Transdutores.

As conexões com os Transdutores são feitas nos tempos:

- **Minutely** - A cada minuto
- **Quarterly** - A cada 15 minutos
- **Monthly** - Mensalmente

Para saber mais sobre este módulo acesse [Slave](./slave/home)  
### Transdutores

![TR4020](./img/tr4020.jpeg)

O transdutor foi projetado para medir grandezas elétricas essenciais em sistemas de gestão de energia. é uma poderosa ferramenta para coletas de dados, que está integrado nesse sistema de gestão de energia.

Para saber mais sobre os Transdutores acesse [Transdutores](./transdutores/home)  

## Tutoriais
- [Como cadastrar um Transdutor e um Slave](./tutoriais/como-cadastrar-transdutor)
- [Como conectar com o Transdutor do Lappis](./tutoriais/conectar-transdutor-lappis)
