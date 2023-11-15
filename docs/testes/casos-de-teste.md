# Documentação de Cenários de Teste para SIGE - Sistema de Gestão Energética - UnB

## Mapeamento das principais funcionalidades <a name="feature-mapping"></a>

## Casos de teste mapeados <a name="mapped-test-cases"></a>

### 1. Tela de cadastro

1.1 Caminho feliz<br>
1.2 Campos obrigatórios/inválidos<br>
1.2.1 Nome<br>
1.2.2 Email<br>
1.2.3 Senha<br>
1.2.4 Confirme a senha<br>
1.3 Senhas não coincidem<br>

### 2. Esqueci minha senha 

2.1 Caminho feliz<br>
2.2 Email obrigatório/inválido<br>

### 3. Login

3.1 Caminho feliz<br>
3.2 Campos obrigatórios/inválidos<br>
3.2.1 Email<br>
3.2.2 Senha<br>
3.3 Dados incorretos<br>
3.3.1 Email<br>
3.3.2 Senha<br>

### 4. 

## Testes Automatizados com BDD

Agora, vamos definir os cenários de teste automatizado usando a abordagem BDD (Behavior-Driven Development). Esses cenários descreverão o comportamento esperado do sistema em relação às funcionalidades mapeadas.

### 1. Tela de cadastro

#### 1.1 Caminho feliz

Dado que o usuário está na página de cadastro  
Quando o usuário preenche todos os campos corretamente  
E clica no botão de cadastro  
Então o usuário deve ser redirecionado para a página principal do sistema  

#### 1.2 Campos obrigatórios/inválidos

##### 1.2.1 Nome

Dado que o usuário está na página de cadastro  
Quando o usuário deixa o campo de nome em branco  
E preenche os demais campos corretamente  
E clica no botão de cadastro  
Então deve haver uma mensagem de erro informando que o nome é obrigatório  

##### 1.2.2 Email

Dado que o usuário está na página de cadastro  
Quando o usuário deixa o campo de email em branco  
E preenche os demais campos corretamente  
E clica no botão de cadastro  
Então deve haver uma mensagem de erro informando que o email é obrigatório  

##### 1.2.3 Senha

Dado que o usuário está na página de cadastro  
Quando o usuário deixa o campo de senha em branco  
E preenche os demais campos corretamente  
E clica no botão de cadastro  
Então deve haver uma mensagem de erro informando que a senha é obrigatória  

##### 1.2.4 Confirme a senha

Dado que o usuário está na página de cadastro  
Quando o usuário preenche o campo de senha  
E preenche o campo de confirmação de senha de forma diferente  
E clica no botão de cadastro  
Então deve haver uma mensagem de erro informando que as senhas não coincidem  

##### 1.2.4 Confirme a senha

Dado que o usuário está na página de cadastro  
Quando o usuário preenche o campo de senha  
E preenche o campo de confirmação de senha de forma diferente  
E clica no botão de cadastro  
Então deve haver uma mensagem de erro informando que as senhas não coincidem  

##### 1.3 Email já cadastrado

Dado que o usuário está na página de cadastro  
Quando o usuário preenche todos os campos corretamente, incluindo um email que já está cadastrado no sistema  
E clica no botão de cadastro  
Então deve haver uma mensagem de erro informando que o email já está cadastrado no sistema 

### 2. Esqueci minha senha

#### 2.1 Caminho feliz

Dado que o usuário está na página de login  
Quando o usuário clica no link "Esqueceu minha senha?"  
E preenche seu email válido  
E clica no botão de recuperação de senha  
Então o usuário deve receber um email com instruções de recuperação  

#### 2.2 Email obrigatório/inválido

Dado que o usuário está na página de login  
Quando o usuário clica no link "Esqueceu minha senha?"  
E deixa o campo de email em branco ou insere um email inválido  
E clica no botão de recuperação de senha  
Então deve haver uma mensagem de erro informando que o email é obrigatório ou inválido  

### 3. Login

#### 3.1 Caminho feliz
Dado que o usuário está na página de login  
Quando o usuário insere um email e senha válidos  
E clica no botão de login  
Então o usuário deve ser redirecionado para a página principal do sistema  

#### 3.2 Campos obrigatórios/inválidos

##### 3.2.1 Email

Dado que o usuário está na página de login  
Quando o usuário deixa o campo de email em branco  
E preenche a senha corretamente  
E clica no botão de login  
Então deve haver uma mensagem de erro informando que o email é obrigatório  

##### 3.2.2 Senha

Dado que o usuário está na página de login  
Quando o usuário insere um email válido  
E deixa o campo de senha em branco  
E clica no botão de login  
Então deve haver uma mensagem de erro informando que a senha é obrigatória  

#### 3.3 Dados incorretos

##### 3.3.1 Email

Dado que o usuário está na página de login  
Quando o usuário insere um email válido, mas senha incorreta  
E clica no botão de login  
Então deve haver uma mensagem de erro informando que os dados de login estão incorretos  

##### 3.3.2 Senha

Dado que o usuário está na página de login  
Quando o usuário insere a senha correta, mas email incorreto  
E clica no botão de login  
Então deve haver uma mensagem de erro informando que os dados de login estão incorretos

### 4. Página Principal

#### Acessar os Cards

##### 4.1 Acessar Medidores

Dado que o usuário está na página principal  
Quando o usuário clica no card "Medidores"  
Então o usuário deve ser redirecionado para a página de "Medidores"  

##### 4.2 Acessar Custo Total

Dado que o usuário está na página principal  
Quando o usuário clica no card "Custo Total"  
Então o usuário deve ser redirecionado para a página de "Custo Total"  

##### 4.3 Acessar Curva de Carga

Dado que o usuário está na página principal  
Quando o usuário clica no card "Curva de Carga"  
Então o usuário deve ser redirecionado para a página de "Curva de Carga"  

##### 4.4 Acessar Relatórios

Dado que o usuário está na página principal  
Quando o usuário clica no card "Relatórios"  
Então o usuário deve ser redirecionado para a página de "Relatórios"  

#### Acessar Elementos Side Bar

##### 4.5 Acessar Início

Dado que o usuário está na página de "Medidores"  
Quando o usuário abre a barra lateral e clica em "Início"  
Então o usuário deve ser redirecionado para a página de "Início"  

##### 4.6 Acessar Medidores a partir da Side Bar

Dado que o usuário está na página principal  
Quando o usuário abre a barra lateral e clica em "Medidores"  
Então o usuário deve ser redirecionado para a página de "Medidores"  

##### 4.7 Acessar Custo Total a partir da Side Bar

Dado que o usuário está na página principal  
Quando o usuário abre a barra lateral e clica em "Custo Total"  
Então o usuário deve ser redirecionado para a página de "Custo Total"  

##### 4.8 Acessar Curva de Carga a partir da Side Bar

Dado que o usuário está na página principal  
Quando o usuário abre a barra lateral e clica em "Curva de Carga"  
Então o usuário deve ser redirecionado para a página de "Curva de Carga"  

##### 4.9 Acessar Relatórios a partir da Side Bar

Dado que o usuário está na página principal  
Quando o usuário abre a barra lateral e clica em "Relatórios"  
Então o usuário deve ser redirecionado para a página de "Relatórios"  

##### 4.10 Acessar Sobre o Projeto a partir da Side Bar

Dado que o usuário está na página principal  
Quando o usuário abre a barra lateral e clica em "Sobre o Projeto"  
Então o usuário deve ser redirecionado para a página de "Sobre o Projeto"  

##### 4.11 Deslogar

Dado que o usuário está na página principal  
Quando o usuário clica no botão "Sair" na barra lateral  
Então o usuário deve ser deslogado e uma mensagem de confirmação deve ser exibida  

#### Acessar Elementos Top Bar

##### 4.12 Alterar Dados

Dado que o usuário está na página principal  
Quando o usuário clica no botão "Alterar Dados" na barra superior  
Então o usuário deve ser redirecionado para a página de "Alterar Dados"  

##### 4.13 Sair a partir da Top Bar

Dado que o usuário está na página principal  
Quando o usuário clica no botão "Sair" na barra superior  
Então o usuário deve ser deslogado e uma mensagem de confirmação deve ser exibida  