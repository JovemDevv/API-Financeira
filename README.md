# Simple Banking App 
Este é um backend simples para um sistema bancário construído usando Express.js. A aplicação permite aos usuários criar contas, realizar transações (depósitos e saques), verificar extratos, atualizar informações da conta e obter o saldo da conta.

## Instalação
Antes de executar a aplicação, certifique-se de ter o Node.js instalado. Em seguida, siga estas etapas:

### Clone o repositório:

````
git clone https://github.com/seu-nome/aplicativo-bancario-backend.git

````
### Navegue até o diretório do projeto:

````
cd aplicativo-bancario-backend
````

### Instale as dependências:

````
npm install
````
## Uso
Para iniciar o servidor, execute:

````
npm start
````
O servidor estará em execução em http://localhost:3030.

### Endpoints
Criar Conta
Endpoint: POST /account

Corpo da Solicitação:

````
{
  "cpf": "123.456.789-00",
  "name": "João Silva"
}
````

### Obter Informações da Conta
Endpoint: GET /account

Cabeçalhos da Solicitação:

````
cpf: 123.456.789-00
````

### Atualizar Informações da Conta
Endpoint: PUT /account

Cabeçalhos da Solicitação:

````
cpf: 123.456.789-00
````

### Corpo da Solicitação:

````
{
  "name": "Nome Atualizado"
}
````

### Excluir Conta
Endpoint: DELETE /account

Cabeçalhos da Solicitação:

````
cpf: 123.456.789-00
````

### Obter Saldo da Conta
Endpoint: GET /balance

Cabeçalhos da Solicitação:

````
cpf: 123.456.789-00
````

### Obter Extrato da Conta
Endpoint: GET /statement

Cabeçalhos da Solicitação:

````
cpf: 123.456.789-00
````

### Depósito
Endpoint: POST /deposit

Cabeçalhos da Solicitação:

````
cpf: 123.456.789-00
````
Corpo da Solicitação:

````
{
  "description": "Descrição do Depósito",
  "amount": 100.00
}
````
### Saque
Endpoint: POST /withdraw

Cabeçalhos da Solicitação:

````
cpf: 123.456.789-00
````
Corpo da Solicitação:

````
{
  "amount": 50.00
}
````
Obter Extrato por Data
Endpoint: GET /statement/date

Cabeçalhos da Solicitação:

````
cpf: 123.456.789-00
````
### Parâmetros de Consulta da Solicitação:

````
date: 2024-01-21
````

### Middleware
verifyIfExistsAccountCPF
Este middleware verifica a existência de uma conta com base no CPF fornecido (número de identificação do cliente). É usado em vários endpoints para garantir que a conta solicitada exista antes de prosseguir.

### Notas Importantes
Esta aplicação utiliza um array em memória (customers) para armazenar informações da conta. Em um ambiente de produção, considere o uso de um banco de dados.
Certifique-se de ter tratamento de erros adequado, medidas de segurança e validações em um cenário do mundo real.
Sinta-se à vontade para contribuir e aprimorar a funcionalidade deste simples aplicativo bancário!
