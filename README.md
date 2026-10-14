# Projeto Web – LH Pets (Protótipo 1)

Atividade de Codificação Back-End – SENAI.

Projeto web em .NET (minimal API) com três rotas:

| Rota | O que mostra |
|---|---|
| `/` | Texto da versão inicial: **LH Pets - Protótipo 1** |
| `/index` | Página `wwwroot/index.html` feita pelo front-end |
| `/listaClientes` | Lista de clientes lida do banco **vendas** (SQL Server) |

- `Banco.cs`: conecta no SQL Server, guarda os clientes na **lista** (atributo da classe) e monta o HTML em `GetListaString()`.
- `Clientes.cs`: modelo do cliente.
- `Program.cs`: cria as rotas.
- `vendas.sql`: script que cria o banco `vendas` e a tabela `tblclientes`.

## Como rodar no Mac

1. Ligar o SQL Server no Docker:
   ```
   docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=LhPets@2026" -p 1433:1433 --name sqlserver --platform linux/amd64 -d mcr.microsoft.com/mssql/server:2022-latest
   ```
2. Rodar o `vendas.sql` (VS Code com a extensão **SQL Server (mssql)**: servidor `localhost,1433`, usuário `sa`, senha `LhPets@2026`, marcar *Trust server certificate*).
3. Na pasta do projeto:
   ```
   dotnet run
   ```
4. Abrir `http://localhost:5000`, `http://localhost:5000/index` e `http://localhost:5000/listaClientes`.

> No Windows (SQL Server Express) a conexão seria `Server=localhost\SQLEXPRESS` com a senha configurada no SSMS.

Desenvolvido por Gabriel Rodrigues.
