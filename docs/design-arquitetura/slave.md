# Arquitetura - Slave

## Padrão arquitetural - MVT

Com o objetivo de fornecer um meio de comunicação com os transdutor instalados na universidade, o Slave utiliza os princípios da arquitetura MVT (Model View Template) do Django, mais especificamente o Django Rest Framework, para alcançar seus objetivos.

O Django Rest Framework é similar ao Django, porém com menos template e mais serializador. Com a camada de Modelo preocupada com as operações de dados de uma aplicação, a camada de Serializador focada em validar esses dados, e por último a camada de Visualização que fornece uma interface para o usuário.

Ciente dessa arquitetura e do uso das camadas para os aplicativos no Django Rest Framework, os principais app do Slave são:

- transductor: Gerenciamento dos transdutores
- measurement: Gerenciamento das medições, como voltagem e corrente que são salvos dados de minuto a minuto, trimestalmente e mensalmente.
- events: Gerenciamento dos eventos da rede, como queda de fase, voltagem crítica e falha de conexão com un transdutor.
