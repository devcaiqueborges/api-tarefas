# API de Gestão de Tarefas 📝

Projeto desenvolvido como atividade prática da disciplina de **Desenvolvimento Web Back-end** do curso de Análise e Desenvolvimento de Sistemas (Uninter).

## 💻 Sobre o Projeto
Esta é uma API RESTful desenvolvida em Java com Spring Boot. O objetivo do sistema é gerenciar tarefas (CRUD), permitindo criar, listar, atualizar e remover registros em um banco de dados relacional, garantindo a persistência e integridade dos dados.

## 🚀 Tecnologias Utilizadas
* **Java 21** (LTS)
* **Spring Boot 3.4**
* **Spring Data JPA** (Hibernate)
* **PostgreSQL** (Banco de Dados)
* **Maven** (Gerenciador de Dependências)
* **Postman** (Para testes e documentação dos endpoints)

## ⚙️ Endpoints da API

A aplicação roda nativamente na porta `8080` com o base path `/tarefas`.

| Método | Endpoint        | Descrição                                  |
|:-------|:----------------|:-------------------------------------------|
| `POST`   | `/tarefas`      | Cadastra uma nova tarefa.                  |
| `GET`    | `/tarefas`      | Lista todas as tarefas cadastradas.        |
| `GET`    | `/tarefas/{id}` | Busca os detalhes de uma tarefa pelo ID.   |
| `PUT`    | `/tarefas/{id}` | Atualiza os dados de uma tarefa existente. |
| `DELETE` | `/tarefas/{id}` | Remove uma tarefa do banco de dados.       |

### 📋 Exemplo de JSON (Body)
Para cadastrar (`POST`) ou atualizar (`PUT`) uma tarefa, utilize o seguinte formato no corpo da requisição:

```json
{
  "nome": "Desenvolver API REST",
  "dataEntrega": "2025-12-12",
  "responsavel": "Carlos Caique"
}
```

---

## 🛠️ Como Rodar o Projeto Localmente

Siga os passos abaixo para configurar e executar a aplicação na sua máquina.

### Pré-requisitos
Antes de começar, certifique-se de ter instalado:
* **Java JDK 17** ou superior.
* **PostgreSQL** (Serviço rodando na porta 5432).
* **Git** (Para clonar o repositório).
* **Maven** (Opcional, pois o projeto inclui o wrapper `mvnw`).

### 👣 Passo a Passo

#### 1. Clone o repositório
Abra o terminal e execute o comando:
```bash
git clone [https://github.com/SEU_USUARIO/tarefas.git](https://github.com/SEU_USUARIO/tarefas.git)
cd tarefas
```

#### 2. Configuração do Banco de Dados
Você precisa criar um banco de dados vazio para a aplicação se conectar.
* **Via pgAdmin:** Crie um database chamado `db_tarefas`.
* **Via SQL (Terminal):**
  ```sql
  CREATE DATABASE db_tarefas;
  ```

#### 3. Configure as Credenciais
Abra o arquivo `src/main/resources/application.properties` e verifique se as credenciais batem com as do seu PostgreSQL local:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/db_tarefas
spring.datasource.username=postgres
spring.datasource.password=SUA_SENHA_AQUI
spring.jpa.hibernate.ddl-auto=update
```
> **Nota:** Substitua `SUA_SENHA_AQUI` pela senha que você configurou na instalação do PostgreSQL.

#### 4. Execute a Aplicação
Você pode rodar de duas formas:

* **Pela IDE (Mais fácil):**
  Abra o projeto no IntelliJ, aguarde o Maven carregar as dependências, procure a classe principal `TarefasApplication.java` e clique no botão **Run** (▶).

* **Pelo Terminal (Profissional):**
  Dentro da pasta do projeto, execute:
  ```bash
  ./mvnw spring-boot:run
  ```

#### 5. Testando
Após iniciar, você verá a mensagem `Started TarefasApplication` no console.
Para verificar se está funcionando, acesse no seu navegador ou Postman:
* **URL:** `http://localhost:8080/tarefas`

---
Desenvolvido por **Carlos Caique Borges de Sousa** 🎓