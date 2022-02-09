## 1. Primeiros Passos

Assim como em todo projeto, uma boa maneira de dar os primeiros passos é explorando o projeto em si. Um bom começo seria seguir os seguintes passos:

1. Entender o que é o projeto
2. Se situar em relação aos objetivos do projeto
3. Rodar / subir os ambientes localmente
4. Aprender como contribuir
5. Contribuir

### 1.1 Mas afinal, o que é o SIGE? 

Todas as informações sobre o que é o SIGE podem ser encontradas na [página inicial](/projects/SMI/docs/) desta documentação mas, aqui vai um breve resumo:

O SIGE (Sistema de Gestão Energética) é um projeto que visa fornecer auxílio no monitoramento e na gestão de instalações elétricas em edificações dos campi da UNB. O objetivo do SIGE é coletar dados para uma análise energética por prédio visto que a UnB possui apenas um medidor geral. Essa análise pode proporcionar a prática de manutenções preventivas e ações remediativas que podem, por sua vez, prevenir danos materiais.

Após entender com clareza quais são os objetivos do projeto, é hora de entender como ele está estruturado.

### 1.2 Como o site está estruturado?

O SIGE está estruturado da seguinte forma:

Servidores de coleta pegam dados dos medidores nos prédios dos campi e enviam a um servidor principal. Este por sua vez trata os dados e os distribui para a aplicação web e para a aplicação móvel.

Uma descrição mais detalhada sobre a estrutura do projeto pode ser encontrada [aqui](/projects/SMI/docs/design-arquitetura/arquitetura/).

### 1.3 Requisitos para rodar o projeto

Quando se sentir confortável com o que é o projeto, o próximo passo seria rodá-lo em sua máquina. Normalmente, cada repositório possui um README explicando como aquela parte do projeto deve ser rodada. Em geral utiliza-se docker e docker-compose, então caso não possua-os em sua máquina, recomenda-se instalá-los.
