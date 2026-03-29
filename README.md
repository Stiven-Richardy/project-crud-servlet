# 👥 Projeto: CRUD de Funcionários (Java Servlets & MySQL)

Este projeto acadêmico foi desenvolvido como parte da disciplina de **Sistemas Web I**, com o objetivo de implementar um sistema básico de CRUD (Create, Read, Update, Delete) para o gerenciamento de funcionários. A aplicação web integra formulários HTML com um banco de dados **MySQL** no back-end utilizando **Java Servlets**.

## 🎯 Objetivos

- **Interface Web**: Desenvolver telas em HTML e via Servlets para cadastro, listagem e edição de dados contendo os campos: Nome, Senha, Email e País.
- **Persistência de Dados**: Implementar as operações de banco de dados (inserção, leitura, atualização e exclusão) utilizando a classe `EmpDao` com conexão JDBC.
- **Roteamento Dinâmico**: Utilizar anotações `@WebServlet` para o roteamento inteligente das requisições (Salvar, Visualizar, Editar, Deletar).
- **Gerenciamento de Estado**: Transitar dados dos objetos `Emp` entre o banco de dados e a interface do usuário renderizada dinamicamente.

## 🛠️ Ferramentas Utilizadas

- Java (Servlets / Jakarta EE)
- MySQL Server
- JDBC (mysql-connector-java-8.0.21)
- Eclipse IDE (Dynamic Web Project)
- HTML
- Apache Tomcat (Servidor Web)
- Git e GitHub

## 🗄️ Estrutura do Banco de Dados

O projeto utiliza o banco de dados **MySQL** (database `swii5` com timezone configurado para `America/Sao_Paulo`).

Antes de executar, é necessário criar a tabela `user905` com a seguinte estrutura:

#### Tabela: `user905`
| Column Name | Data Type | Allow Nulls | Descrição |
| :--- | :--- | :--- | :--- |
| **id** | `INT` | Não | Chave Primária (PK) - Auto Incremento |
| **name** | `VARCHAR(4000)` | Sim | Nome do funcionário |
| **password** | `VARCHAR(4000)` | Sim | Senha de acesso |
| **email** | `VARCHAR(4000)` | Sim | E-mail de contato |
| **country** | `VARCHAR(4000)` | Sim | País de origem |

**Script SQL (também presente no arquivo `init-database.sql`):**
```sql
CREATE DATABASE swii5;

USE swii5;

CREATE TABLE user905 (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(4000),
    password VARCHAR(4000),
    email VARCHAR(4000),
    country VARCHAR(4000)
);
````

## 🗂️ Estrutura do Projeto

```text
📁 crud-servlet/
├── 📁 WebContent/
│   ├── 📁 META-INF/
│   │   └── 📄 MANIFEST.MF
│   ├── 📁 WEB-INF/
│   │   └── 📁 lib/
│   │       └── 📄 mysql-connector-java-8.0.21.jar
│   └── 📄 index.html
├── 📁 src/
│   ├── 📄 DeleteServlet.java
│   ├── 📄 EditServlet.java
│   ├── 📄 EditServlet2.java
│   ├── 📄 Emp.java
│   ├── 📄 EmpDao.java
│   ├── 📄 SaveServlet.java
│   └── 📄 ViewServlet.java
├── 📄 init-database.sql
└── 📄 README.md
```

## 🚀 Como Executar

1.  Configuração do Banco de Dados:
      - Certifique-se de ter o **MySQL** rodando localmente na porta `3306`.
      - Crie o banco de dados `swii5` e a tabela `user905` (veja o script acima).
      - As credenciais de acesso no arquivo `EmpDao.java` estão configuradas como padrão (`user: root` e `password: root`). Altere-as se necessário para refletir o seu ambiente local.

2.  Configuração do Ambiente (Eclipse):
      - Importe a pasta do projeto no Eclipse: `File > Import > General > Existing Projects into Workspace`.
      - Certifique-se de que o **Apache Tomcat** está configurado e associado ao projeto (`Project Properties > Target Runtimes`).
      - Verifique se o conector `mysql-connector-java-8.0.21.jar` está corretamente mapeado no `Java Build Path`.

3.  Iniciando a Aplicação:
      - Clique com o botão direito no projeto ou no `index.html`.
      - Selecione `Run As > Run on Server`.
      - O navegador abrirá automaticamente a tela de cadastro em `http://localhost:8080/crudservlet/index.html`.

## 👨‍🏫 Autores

  - **Stiven Richardy Silva Rodrigues** Estudante de Análise e Desenvolvimento de Sistemas | IFSP — Campus Cubatão  
    [@Stiven-Richardy](https://github.com/Stiven-Richardy)

  - **Guilherme Mendes de Sousa** Estudante de Análise e Desenvolvimento de Sistemas | IFSP — Campus Cubatão  
    [@Guilh3rme-M3ndes](https://github.com/Guilh3rme-M3ndes)

## 📚 Referências

  - Documentação do MySQL Connector/J: https://www.google.com/search?q=https://dev.mysql.com/doc/connector-j/8.0/en/
  - Documentação de Java Servlets: https://javaee.github.io/tutorial/servlets.html
  - Eclipse Web Tools Platform (WTP): https://www.google.com/search?q=https://eclipse.org/webtools/
