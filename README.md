# petshop-crud-oracle

Aplicação de terminal em Python para gerenciar o cadastro de pets de um petshop, com operações CRUD completas sobre um banco de dados Oracle. Projeto de estudo desenvolvido na FIAP.

## Funcionalidades

1. Cadastrar pet (tipo, nome e idade)
2. Listar pets (exibidos em um DataFrame do pandas)
3. Alterar os dados de um pet pelo ID
4. Excluir um pet pelo ID
5. Excluir todos os pets (e reiniciar a sequência de IDs)
6. Sair

## Requisitos

- Python 3.10+ (usa `match/case`)
- Acesso a um banco Oracle

```bash
pip install -r requirements.txt
```

## Banco de dados

```sql
CREATE TABLE petshop (
    id       NUMBER GENERATED AS IDENTITY PRIMARY KEY,
    tipo_pet VARCHAR2(50),
    nome_pet VARCHAR2(100),
    idade    NUMBER
);
```

## Configuração

As credenciais são lidas de variáveis de ambiente:

| Variável          | Padrão               |
|-------------------|----------------------|
| `ORACLE_USER`     | —                    |
| `ORACLE_PASSWORD` | —                    |
| `ORACLE_HOST`     | `oracle.fiap.com.br` |
| `ORACLE_PORT`     | `1521`               |
| `ORACLE_SID`      | `ORCL`               |

No PowerShell:

```powershell
$env:ORACLE_USER = "seu_usuario"
$env:ORACLE_PASSWORD = "sua_senha"
python crud.py
```
