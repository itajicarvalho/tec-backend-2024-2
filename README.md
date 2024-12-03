# Aluno Online


---

## Descrição dos Pacotes e Arquivos

### 1. **Pacote `config`**
- **`SwaggerConfig.java`**
   - Configuração do Swagger/OpenAPI para gerar automaticamente a documentação da API.
   - Define endpoints como `/swagger-ui.html` para acesso à interface de documentação.

### 2. **Pacote `controller`**
Contém os controladores da aplicação, responsáveis por gerenciar as requisições HTTP e delegar chamadas para os serviços.

- **`AlunoController.java`**
   - Controlador para endpoints relacionados aos alunos, como cadastro, consulta e atualização de dados.

- **`DisciplinaController.java`**
   - Gerencia operações relacionadas às disciplinas, como listar disciplinas disponíveis.

- **`MatriculaAlunoController.java`**
   - Controlador para gerenciar as matrículas dos alunos em disciplinas.

- **`ProfessorController.java`**
   - Gerencia operações relacionadas aos professores, como cadastro e atribuição de disciplinas.

### 3. **Pacote `dtos`**
Contém **Data Transfer Objects (DTOs)** usados para transferência de dados entre as camadas.

- **`AtualizarNotasRequest.java`**
   - Representa a estrutura de dados enviada para atualizar as notas dos alunos.

- **`DisciplinasAlunoResponse.java`**
   - Define a resposta para listar as disciplinas de um aluno específico.

- **`HistoricoAlunoResponse.java`**
   - Representa o histórico acadêmico de um aluno.

### 4. **Pacote `enums`**
Define enumeradores que representam valores fixos no sistema.

- **`MatriculaAlunoStatusEnum.java`**
   - Enumeração que representa os estados de uma matrícula (ex.: MATRICULADO, APROVADO, REPROVADO, TRANCADO;).

### 5. **Pacote `model`**
Contém as entidades que representam os dados persistidos no banco de dados.

- **`Aluno.java`**
   - Representa a entidade **Aluno** com atributos como `nome`, `cpf`, e relacionamento com matrículas.

- **`Disciplina.java`**
   - Representa uma disciplina acadêmica, com atributos como `nome` e `cargaHoraria`.

- **`MatriculaAluno.java`**
   - Entidade que vincula alunos e disciplinas, representando uma matrícula.

- **`Professor.java`**
   - Entidade que representa os professores responsáveis pelas disciplinas.

### 6. **Pacote `repository`**
Contém as interfaces que fazem a comunicação com o banco de dados, utilizando o **Spring Data JPA**.

- **`AlunoRepository.java`**
   - Repositório para a entidade `Aluno`, permitindo operações CRUD no banco.

- **`DisciplinaRepository.java`**
   - Gerencia a persistência de dados da entidade `Disciplina`.

- **`MatriculaAlunoRepository.java`**
   - Repositório para gerenciar matrículas de alunos em disciplinas.

- **`ProfessorRepository.java`**
   - Interface para acesso aos dados de professores.

### 7. **Pacote `service`**
Contém as regras de negócio da aplicação, centralizando a lógica que será chamada pelos controladores.

- **`AlunoService.java`**
   - Lida com a lógica de negócio para alunos, como registro e consulta de dados.

- **`DisciplinaService.java`**
   - Regras para disciplinas, como listagem e criação.

- **`MatriculaAlunoService.java`**
   - Gerencia as operações relacionadas a matrículas de alunos.

- **`ProfessorService.java`**
   - Regras de negócio para gerenciamento de professores.

### 8. **`AlunoOnlineApplication.java`**
- Classe principal do projeto, contendo o método `main`.
- Inicia a aplicação Spring Boot e configura todos os componentes automaticamente.

---

## Testes

### Pacote `test`
- Contém testes automatizados para validar o funcionamento da aplicação.

- **`AlunoOnlineApplicationTests.java`**
   - Classe de teste para validar o contexto da aplicação e garantir que todos os componentes são carregados corretamente.

---

## Observações Gerais

1. **Configuração do Swagger/OpenAPI**
   - Documentação da API pode ser acessada em:
      - `/swagger-ui.html` ou `/swagger-ui/index.html`
      - Documentação em formato JSON disponível em `/v3/api-docs`.

2. **Arquitetura**
   - A aplicação segue o padrão **MVC** (Model-View-Controller):
      - **Model:** Pacote `model`, representando a camada de persistência.
      - **Controller:** Pacote `controller`, responsável pelas rotas HTTP.
      - **Service:** Pacote `service`, que concentra as regras de negócio.

3. **Banco de Dados**
   - Integração com PostgreSQL usando Spring Data JPA.

4. **Boas Práticas**
   - Código organizado por responsabilidade.
   - Uso de DTOs para isolar camadas.
   - Separação clara entre lógica de negócio e persistência.

---

# Dependências do Projeto

O projeto **Aluno Online** utiliza as seguintes bibliotecas e ferramentas:

## Dependências Principais

1. **Spring Boot Starter Data JPA**
    - **Descrição:** Fornece integração com o JPA, permitindo a interação com bancos de dados de forma simplificada.

2. **Spring Boot Starter Web**
    - **Descrição:** Fornece suporte para desenvolvimento de APIs REST e aplicações web.

3. **PostgreSQL**
    - **Descrição:** Driver JDBC para integração com o banco de dados PostgreSQL.

## Dependências para Documentação

4. **SpringFox Swagger 2**
    - **Descrição:** Gera documentação automática para APIs REST no formato Swagger.

5. **SpringDoc OpenAPI Starter WebMVC UI**
    - **Descrição:** Gera documentação no padrão OpenAPI e disponibiliza interface gráfica para visualização (Swagger UI).

## Dependências para Testes

6. **Spring Boot Starter Test**
    - **Descrição:** Inclui frameworks e utilitários para testes automatizados de aplicações Spring.


## Plugins do Build

1. **Spring Boot Maven Plugin**
    - **Descrição:** Facilita o empacotamento e execução de aplicações Spring Boot.

---