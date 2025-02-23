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

| **ID**   | **Caso de Teste**            | **Entradas** | **Resultado Esperado** | **Prioridade** | **Pós-condições** |
|----------|------------------------------|--------------|------------------------|----------------|------------------|
| **CT001** | Nome Completo Válido         | "Mateus Luiz Moraes Silva" | Nome registrado corretamente. | Alta | Nome salvo no sistema com sucesso. |
| **CT002** | Nome com Caracteres Inválidos | "M@teus Luiz Moraes Silva" | O sistema deve exibir um erro informando que caracteres especiais não são permitidos. | Alta | Nenhuma alteração, o sistema exibe mensagem de erro. |
| **CT003** | Nome Muito Curto             | "Ma" | Caso o sistema tenha uma regra de negócio que defina um tamanho mínimo para o nome, ele deve exibir uma mensagem informando o tamanho mínimo permitido. Caso contrário, o nome deve ser aceito. | Média | Nenhuma alteração, a menos que a regra de negócio permita. |
| **CT004** | Nome Muito Longo             | "Mateus Luiz Moraes Silva da Silva da Silva da Silva da Silva da Silva da Silva da Silva da Silva" | Caso o sistema tenha uma regra de negócio que defina um tamanho máximo para o nome, ele deve exibir uma mensagem informando o limite permitido. Caso contrário, o nome deve ser aceito. | Média | Nenhuma alteração, a menos que a regra de negócio permita. |


## Roteiro de Teste 2

| **RT002** | Alteração de E-mail  |
|----|---|
| **Objetivo do Roteiro de Teste** | Validar a entrada de e-mails para garantir que o formato esteja correto e que o sistema rejeite e-mails inválidos|
| **Localização**                    |Campo "E-mail" |
| **Pré-condições**                   | O formulário de atualização está acessível.  |
| **Passo a Passo**                   | 1. Acessar o formulário de atualização de usuário. <br> 2. Inserir diferentes valores no campo "E-mail". <br> 3. Submeter formulário. <br> 4. Verificar se o sistema aceita o e-mail válido e rejeita as entradas inválidas.|
| **Nível de Teste**                  | Funcional |
| **Técnica de Teste**                | Caixa preta  |
| **Critério de Seleção de Entradas** | Partição de equivalência |

### Casos de Teste  

| **ID**   | **Caso de Teste**            | **Entradas** | **Resultado Esperado** | **Prioridade** | **Pós-condições** |
|----------|------------------------------|--------------|------------------------|----------------|------------------|
| **CT001** | Validar E-mail Válido | "mateus@email.com" | E-mail registrado corretamente. | Alta | E-mail salvo no sistema com sucesso. |
| **CT002** | E-mail sem @ | "mateusemail.com" | O sistema deve exibir um erro informando que o e-mail está no formato inválido. | Alta | Nenhuma alteração, o sistema exibe mensagem de erro. |
| **CT003** | E-mail com Caracteres Especiais Inválidos  | "mateus#@gmail.com" |Erro de validação indicando caracteres especiais inválidos. | Média | Nenhuma alteração, o e-mail permanece o mesmo. |



