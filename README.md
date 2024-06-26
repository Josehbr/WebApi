# Web API com integração ao banco de dados SQL Server

Uma aplicação web API criada com o ASP.NET Core que se integra a um banco de dados SQL Server. A API fornece operações CRUD para manipular registros de contatos em um banco de dados. O exemplo usa um modelo chamado `Contato` e se integra ao banco de dados por meio do Entity Framework Core.

## Tecnologias Utilizadas

- ASP.NET Core
- SQL Server (banco de dados)
- Entity Framework Core
- C#

## Estrutura do Projeto

- `ContatoController.cs`: Este é o controlador principal da API que lida com as operações CRUD para contatos.
- `AgendaContext.cs`: Classe de contexto do Entity Framework que representa a conexão com o banco de dados.
- `Contato.cs`: Modelo de dados que representa um contato na aplicação.

## Configuração do Banco de Dados

Para configurar a conexão com o banco de dados SQL Server, você deve fornecer a cadeia de conexão no arquivo `appsettings.Development.json`. A seção de configuração pode ser semelhante à seguinte:

```json
{
  "ConnectionStrings": {
    "ConexaoPadrao" : "Server=Nome_do_Server; Initial Catalog=Agenda; Integrated Security=True; Encrypt=False;"}
  }
}
```
## Uso da API

### Criar um Contato (POST)

- Rota: `POST /Contato`
- Cria um novo contato no banco de dados.
- Parâmetros: Um objeto JSON representando o contato a ser criado.
- Exemplo de corpo da solicitação:
```json
{
    "Nome": "João",
    "Telefone": "123-456-7890",
    "Ativo": true
}
```

### Obter um Contato por ID (GET)

- Rota: `GET /Contato/{id}`
- Recupera um contato específico com base no ID fornecido.
- Parâmetros: `id` - o ID do contato que deseja recuperar.

### Obter Contatos por Nome (GET)

- Rota: `GET /Contato/ObterPorNome`
- Recupera contatos com base no nome fornecido.
- Parâmetros: `nome` - o nome a ser pesquisado.

### Atualizar um Contato por ID (PUT)

- Rota: `PUT /Contato/{id}`
- Atualiza as informações de um contato existente com base no ID fornecido.
- Parâmetros: `id` - o ID do contato que deseja atualizar.
- Exemplo de corpo da solicitação:
```json
{
    "Nome": "João Atualizado",
    "Telefone": "987-654-3210",
    "Ativo": false
}
```

### Deletar um Contato por ID (DELETE)

- Rota: `DELETE /Contato/{id}`
- Exclui um contato com base no ID fornecido.
- Parâmetros: `id` - o ID do contato que deseja excluir.