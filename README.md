# Gerenciamento de Setores e Funcionários

Este projeto é uma aplicação básica utilizando **Sequelize** e **SQLite** para gerenciar setores e funcionários de uma empresa. Ele demonstra a utilização de operações CRUD (Create, Read, Update, Delete) para manipular dados em um banco de dados relacional.

## Tecnologias Utilizadas

- **Node.js**: Plataforma para execução de JavaScript no lado do servidor.
- **Sequelize**: ORM (Object-Relational Mapping) para Node.js.
- **SQLite**: Banco de dados leve e embutido para armazenamento dos dados.

## Estrutura do Projeto

### Modelos

1. **Setor**
    - Campos:
        - `idsetor`: ID único e chave primária.
        - `nome`: Nome do setor.
        - `ramal`: Número do ramal.
        - `email`: E-mail do setor.
    - Representado na tabela `setores`.

2. **Funcionario**
    - Campos:
        - `matricula`: ID único e chave primária.
        - `idsetor`: Chave estrangeira referenciando o setor.
        - `nome`: Nome do funcionário.
        - `nascimento`: Data de nascimento.
        - `telefone`: Telefone do funcionário.
    - Representado na tabela `funcionarios`.

## Funcionalidades

1. **Criação de Setores e Funcionários**
    - Criação de setores com nome, ramal e e-mail.
    - Criação de funcionários vinculados a setores.

2. **Leitura de Dados**
    - Listagem de setores.
    - Listagem de funcionários.

3. **Atualização de Dados**
    - Atualização de informações de setores (ex.: nome).

4. **Exclusão de Dados**
    - Remoção de setores do banco de dados.

## Pré-requisitos

- Node.js instalado.
- Pacotes do projeto instalados via `npm install`.


## Estrutura do Banco de Dados

- `setores`: Tabela que armazena os setores da empresa.
- `funcionarios`: Tabela que armazena os funcionários, com referência ao setor em que trabalham.

## Exemplo de Saída

**Lista de setores:**
```json
[
  {
    "idsetor": 1,
    "nome": "Financeiro",
    "ramal": "2134",
    "email": "financeiro@empresa.com"
  },
  {
    "idsetor": 2,
    "nome": "Secretaria",
    "ramal": "2135",
    "email": "secretaria@empresa.com"
  }
]
```

**Lista de funcionários:**
```json
[
  {
    "matricula": 1,
    "idsetor": 2,
    "nome": "Ana",
    "nascimento": "1978-04-12",
    "telefone": "01219219"
  },
  {
    "matricula": 2,
    "idsetor": 3,
    "nome": "Ivo",
    "nascimento": "2000-12-01",
    "telefone": "07280921"
  }
]
```

## Observações

- O banco de dados SQLite é criado automaticamente como `empresa.sqlite` na raiz do projeto.
- O parâmetro `force: true` no método `sync` recria as tabelas sempre que o projeto é executado. Em produção, altere para `force: false` para evitar perda de dados.

---
