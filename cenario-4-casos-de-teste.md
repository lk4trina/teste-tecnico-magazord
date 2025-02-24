# Casos de Teste 
Para a validação de dados cadastrais em um sistema de gerenciamento de usuários, considerando os campos modificados, podemos criar os seguintes casos de teste:

## Roteiro de Teste 1

| **RT001** | Alteração de Nome Completo  |
|----|---|
| **Objetivo do Roteiro de Teste** | Validar que o sistema permite a alteração do nome completo com caracteres válidos e se impede nomes com caracteres especiais |
| **Localização**                    |Campo "Nome" |
| **Pré-condições**                   | A funcionalidade de atualização deve estar acessível na interface de usuário.  |
| **Passo a Passo**                   | 1. Acessar o formulário de atualização de usuário. <br> 2. Inserir diferentes valores no campo "Nome". <br> 3. Submeter formulário. <br> 4. Verificar a resposta do sistema, que deve aceitar apenas se válido. <br> 5. Verificar se o sistema aceita um nome válido e rejeitas entradas inválidas com erros de validação apropriados.|
| **Nível de Teste**                  | Funcional |
| **Técnica de Teste**                | Caixa preta  |
| **Critério de Seleção de Entradas** |Análise de valor limite  |

### Casos de Teste  

| **ID**   | **Caso de Teste**   | **Entradas** | **Resultado Esperado** | **Pós-condições** |
|----------|---------------------|--------------|------------------------|-------------------|
| **CT001** | Nome Completo Válido        | "Mateus Luiz Moraes Silva" | Nome registrado corretamente. | Nome salvo no sistema com sucesso. |
| **CT002** | Nome com Caracteres Inválidos | "M@teus Luiz Moraes Silva" | O sistema deve exibir um erro informando que caracteres especiais não são permitidos. | Nenhuma alteração, o sistema exibe mensagem de erro. |
| **CT003** | Nome Muito Curto             | "Ma" | Caso o sistema tenha uma regra de negócio que defina um tamanho mínimo para o nome, ele deve exibir uma mensagem informando o tamanho mínimo permitido. Caso contrário, o nome deve ser aceito. | Nenhuma alteração, a menos que a regra de negócio permita. |
| **CT004** | Nome Muito Longo             | "Mateus Luiz Moraes Silva da Silva da Silva da Silva da Silva da Silva da Silva da Silva da Silva" | Caso o sistema tenha uma regra de negócio que defina um tamanho máximo para o nome, ele deve exibir uma mensagem informando o limite permitido. Caso contrário, o nome deve ser aceito. | Nenhuma alteração, a menos que a regra de negócio permita. |


## Roteiro de Teste 2

| **RT002** | Alteração de E-mail  |
|----|---|
| **Objetivo do Roteiro de Teste** | Validar a entrada de e-mails para garantir que o formato esteja correto e que o sistema rejeite e-mails inválidos|
| **Localização**                    |Campo "E-mail" |
| **Pré-condições**                   | O formulário de atualização está acessível.  |
| **Passo a Passo**                   | 1. Acessar o formulário de atualização de e-mail. <br> 2. Inserir diferentes valores no campo "E-mail". <br> 3. Submeter formulário. <br> 4. Verificar se o sistema aceita o e-mail válido e rejeita as entradas inválidas.|
| **Nível de Teste**                  | Funcional |
| **Técnica de Teste**                | Caixa preta  |
| **Critério de Seleção de Entradas** | Partição de equivalência |

### Casos de Teste  

| **ID**   | **Caso de Teste**    | **Entradas** | **Resultado Esperado** | **Pós-condições** |
|----------|----------------------|--------------|------------------------|-------------------|
| **CT001** | Validar E-mail Válido | "mateus@email.com" | Aceito pelo sistema. | E-mail salvo no sistema com sucesso. |
| **CT002** | E-mail com caracteres especiais inválidos | "usuario#luiz@email.com" | Nenhuma alteração, o sistema exibe mensagem de erro | E-mail não alterado |
| **CT003** | E-mail com subdomínios | "mateus@sub.dominio.com" | Aceito pelo sistema. | E-mail salvo no sistema com sucesso. |
| **CT004** | E-mail sem "@" | "mateus.email.com" | Nenhuma alteração, o sistema exibe mensagem de erro | E-mail não alterado |
| **CT005** | E-mail sem domínio | "meteus@" | Nenhuma alteração, o sistema exibe mensagem de erro  | E-mail não alterado |
| **CT006** | E-mail com espaço  | "mateus @email.com"  | Nenhuma alteração, o sistema exibe mensagem de erro | E-mail não alterado |
| **CT007** | E-mail com dois pontos seguidos | "mateus..luiz@email.com" | Nenhuma alteração, o sistema exibe mensagem de erro | E-mail não alterado |
| **CT008** | E-mail começando com ponto | ".mateus@email.com" | Nenhuma alteração, o sistema exibe mensagem de erro  | E-mail não alterado |
| **CT09** | E-mail terminando com ponto | "mateus.@email.com" | Nenhuma alteração, o sistema exibe mensagem de erro. | E-mail não alterado. |
| **CT010** | E-mail muito longo (acima de 64 caracteres na parte local) | "mateusluizmoraesdasilvadasilvadaSilva1234567890@email.com" | Nenhuma alteração, o sistema exibe mensagem de erro | E-mail não alterado |

## Roteiro de Teste 3

| **RT003** | Alteração de Número de Telefone  |
|----|---|
| **Objetivo do Roteiro de Teste** | Verificar se o sistema valida corretamente a entrada do número de telefone, com o formato correto|
| **Localização**                    |Campo "Número de Telefone" |
| **Pré-condições**                   | O formulário de atualização está acessível.  |
| **Passo a Passo**                   | 1. Acessar o formulário de atualização de telefone. <br> 2. Inserir diferentes valores no campo "Número de telefone". <br> 3. Submeter formulário. <br> 4. Verificar se o sistema aceita o telefone válido e rejeita as entradas inválidas.|
| **Nível de Teste**                  | Funcional |
| **Técnica de Teste**                | Caixa preta  |
| **Critério de Seleção de Entradas** | Partição de equivalência |

### Casos de Teste  

| **ID**   | **Caso de Teste**    | **Entradas** | **Resultado Esperado** | **Pós-condições** |
|----------|----------------------|--------------|------------------------|-------------------|
| **CT001** | Validar número de telefone válido | "(XX)91234-56XX" | Número aceito pelo sistema (mascarado para testes)|  Número de telefone alterado com sucesso. |
| **CT002** | Número com caracteres inválidos | "(47)91234-567y" | Erro de validação, o sistema exibe mensagem de erro | Telefone não alterado |
| **CT003** | Número de Telefone sem DDD | "91234-5678" | Erro de validação, o sistema exibe mensagem de erro | Telefone não alterado |
| **CT004** | Número de Telefone com DDD inválido | "(01)91234-56XX" | Erro de validação, o sistema exibe mensagem de erro | Telefone não alterado |
| **CT005** | Número de Telefone com formato incompleto | "(XX)91234" | Erro de validação, o sistema exibe mensagem de erro | Telefone não alterado |

## Roteiro de Teste 4

| **RT004** | Alteração de Data de Nascimento  |
|----|---|
| **Objetivo do Roteiro de Teste** | Verificar se o sistema valida corretamente a entrada do número de telefone, com o formato correto|
| **Localização**                    |Campo "Data de Nascimento" |
| **Pré-condições**                   | O formulário de atualização está acessível.  |
| **Passo a Passo**                   | 1. Acessar o formulário de atualização de data de nascimento. <br> 2. Inserir diferentes valores no campo "Data de nascimento". <br> 3. Submeter formulário. <br> 4. Verificar se o sistema valida as datas corretamente.|
| **Nível de Teste**                  | Funcional |
| **Técnica de Teste**                | Caixa preta  |
| **Critério de Seleção de Entradas** | Partição de equivalência |

### Casos de Teste  

| **ID**   | **Caso de Teste**    | **Entradas** | **Resultado Esperado** | **Pós-condições** |
|----------|----------------------|--------------|------------------------|-------------------|
| **CT001** | Validar data de nascimento válida | "15/05/1980" | Data validada pelo sistema|  Data de nascimento alterada com sucesso. |
| **CT002** | Data de nascimento no futuro| "24/02/2026" | Erro de validação informando que a data não pode ser no futuro | Data de nascimento não alterada |
| **CT003** | Data de nascimento com formato inválido | "15-05-1980" | Erro de validação informando que a data não está no formato válido | Data de nascimento não alterada |
| **CT004** | Data de nascimento com idade avançada | "24/02/1900" | Erro de validação informando que a data está além do intervalo permitido | Data de nascimento não alterada |
| **CT005** | Data de nascimento com idade inferior ao permitido pelo sistema | "24/02/2020" | Erro de validação, o sistema exibe mensagem de erro | Data de nascimento não alterada|
| **CT006** | Data de nascimento com valores inválidos | "32/13/2000" | Erro de validação, o sistema exibe mensagem de erro | Data de nascimento não alterada|
| **CT007** | Data de nascimento com valores faltando | "02/2000" | Erro de validação, o sistema exibe mensagem de erro | Data de nascimento não alterada|

## Roteiro de Teste 5

| **RT005** | Alteração de Endereço  |
|----|---|
| **Objetivo do Roteiro de Teste** | Verificar se o sistema valida corretamente a entrada de endereço com rua, cidade, estado e cep, impedindo alterações inválidas e incompletas|
| **Localização**                    |Formulário de Endereço |
| **Pré-condições**                   | O formulário de atualização está acessível.  |
| **Passo a Passo**                   | 1. Acessar o formulário de atualização de endereço. <br> 2. Preencher os campos Rua, Cidade, Estado e CEP com diferentes valores. <br> 3. Submeter formulário. <br> 4. Verificar se o sistema aceita apenas entradas válidas e rejeita entradas inválidas.|
| **Nível de Teste**                  | Funcional |
| **Técnica de Teste**                | Caixa preta  |
| **Critério de Seleção de Entradas** | Partição de equivalência |

### Casos de Teste  

| **ID**   | **Caso de Teste**    | **Entradas** | **Resultado Esperado** | **Pós-condições** |
|----------|----------------------|--------------|------------------------|-------------------|
| **CT001** | Validar endereço válido | Rua: "Av. Mininistro João Gonçalves de Souza" <br> Cidade: "Manaus" <br> Estado: "Amazonas" <br> CEP: "69075-830"  | Endereço aceito pelo sistema |  Endereço alterado com sucesso. |
| **CT002** | Endereço sem rua | Rua: "" <br> Cidade: "São Paulo" <br> Estado: "São Paulo" <br> CEP: "05653-070" | Erro de validação, o sistema exibe mensagem de erro informando ausência de rua | Endereço não alterado |
| **CT003** | Endereço sem cidade | Rua: "Engenheiro Ostoja Roguski" <br> Cidade: "" <br> Estado: "Paraná" <br> CEP: "80210-391" | Erro de validação, o sistema exibe mensagem de erro informando ausência de cidade | Endereço não alterado |
| **CT004** | Endereço sem estado | Rua: "Manoel Antônio Galvão" <br> Cidade: "Salvador" <br> Estado: "" <br> CEP: "41741-550" | Erro de validação, o sistema exibe mensagem de erro informando ausência de estado | Endereço não alterado |
| **CT005** | Endereço sem CEP | Rua: "Avenida Contorno" <br> Cidade: "Goiânia" <br> Estado: "Goiás" <br> CEP: "" | Erro de validação, o sistema exibe mensagem de erro informando ausência de CEP| Endereço não alterado |
| **CT005** | Endereço com caracteres inválidos | Rua: "Avenida Min. João Gon!çalves" <br> Cidade: "Manaus" <br> Estado: "Amazonas" <br> CEP: "69075-830" | Erro de validação, o sistema exibe mensagem de erro informando que não podem ser utilizados caracteres especiais | Endereço não alterado |
| **CT006** | Endereço com CEP inexistente | Rua: "Manoel Antônio Galvão" <br> Cidade: "Salvador" <br> Estado: "Bahia" <br> CEP: "12345-020" | Erro de validação, o sistema exibe mensagem de erro informando que o CEP não existe | Endereço não alterado |
| **CT007** | Endereço com Estado inexistente | Rua: "Avenida Contorno" <br> Cidade: "Goiânia" <br> Estado: "Rio Vermelho" <br> CEP: "74055-150" | Erro de validação, o sistema exibe mensagem de erro informando que o Estado não existe | Endereço não alterado |
| **CT008** | Endereço com CEP não pertencente à cidade | Rua: "Doutor Getúlio Vargas" <br> Cidade: "Ibirama" <br> Estado: "Santa Catarina" <br> CEP: "89150-000" | Erro de validação, o sistema exibe mensagem de erro informando que o CEP não pertence à cidade| Endereço não alterado |
