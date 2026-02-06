# ApiWeb

Esse projeto se trata de uma API RESTful desenvolvida em ASP.NET Core (.NET 9) para gerenciamento de produtos. Permite operações de CRUD (Criar, Ler, Atualizar, Deletar) sobre produtos.

## Funcionalidades

- Listar todos os produtos
- Buscar produto por ID
- Criar novo produto
- Editar produto existente
- Deletar produto

## Tecnologias Utilizadas

- .NET 9
- ASP.NET Core Web API
- Entity Framework Core
- SQL Server (ou outro banco de dados configurado)
- C#
- Scalar

## Pré-requisitos

- [.NET 9 SDK](https://dotnet.microsoft.com/download/dotnet/9.0)
- [SQL Server](https://www.microsoft.com/pt-br/sql-server/sql-server-downloads) (ou outro banco de dados relacional)
- [Git](https://git-scm.com/)

## Como rodar o projeto

### 1. Clone o repositório

```sh
git clone <URL_DO_REPOSITORIO>
cd "16 - API/ApiWeb/ApiWeb"
```

### 2. Configure o banco de dados

- Abra o arquivo `appsettings.json` (ou crie, caso não exista) e configure a string de conexão do Entity Framework para o seu banco de dados SQL Server, por exemplo:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=localhost;Database=ApiWebDb;Trusted_Connection=True;TrustServerCertificate=True;"
  }
}
```

- Certifique-se de que o contexto (no meu caso, nomeado como `AppDbContext.cs` na pasta Data) está usando essa string de conexão.

### 3. Restaure os pacotes

```sh
dotnet restore
```

### 4. Execute as migrações do banco de dados

```sh
dotnet ef database update
```

> Se o comando acima não funcionar, instale o pacote de ferramentas do EF Core:
>
> ```bash
> dotnet tool install --global dotnet-ef
> ```

### 5. Execute a aplicação

```sh
dotnet run
```

A API estará disponível em `https://localhost:5001` ou `http://localhost:5000` (verifique o terminal).

## Endpoints

| Método | Rota                  | Descrição                  |
|--------|-----------------------|----------------------------|
| GET    | /api/produto          | Lista todos os produtos    |
| GET    | /api/produto/{id}     | Busca produto por ID       |
| POST   | /api/produto          | Cria um novo produto       |
| PUT    | /api/produto/{id}     | Atualiza um produto        |
| DELETE | /api/produto/{id}     | Deleta um produto          |

### Exemplo de requisição para criar produto

```json
POST /api/produto
Content-Type: application/json

{
  "nome": "Produto Exemplo",
  "descricao": "Descrição do produto",
  "marca": "Marca X",
  "quantidadeEstoque": 10,
  "codigoDeBaras": "1234567890123"
}
```

## Testando a API

Você pode utilizar ferramentas como [Postman](https://www.postman.com/) ou [Insomnia](https://insomnia.rest/) para testar os endpoints.

## Autor

<p>Desenvolvido por Fernando Gonzaga:</p>

  - Linkedln: https://www.linkedin.com/in/fernando-gonzaga21/
  - GitHub: https://github.com/fernandoGonzaga0

## Licença

Este projeto está sob a licença MIT.
