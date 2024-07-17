# Projeto API REST com Node.js e Sequelize

## Descrição

Este projeto tem como objetivo aprimorar as habilidades de desenvolvimento com Node.js e Sequelize, integrando uma API REST a um banco de dados SQL. Este projeto foi desenvolvido durante um curso de Sequelize, onde foram adicionadas diversas funcionalidades à API. O projeto segue os princípios da programação orientada a objetos (POO) para organizar e estruturar o código.

## Estrutura do Projeto

O projeto está estruturado da seguinte forma:

- `models/`: Contém os modelos Sequelize para interação com o banco de dados.
- `controllers/`: Contém os controladores que definem a lógica das rotas.
- `services/`: Contém as regras de negócios e lógica de serviços.
- `routes/`: Contém as definições das rotas da API.
- `config/`: Contém as configurações do banco de dados.
- `migrations/`: Contém as migrações para criação e alteração de tabelas no banco de dados.
- `seeders/`: Contém os seeders para popular o banco de dados com dados iniciais.

## Funcionalidades Implementadas

- **CRUD Completo**: Criação, leitura, atualização e exclusão de registros nas tabelas do banco de dados.
- **Relacionamentos**: Manipulação de relações entre tabelas, como um-para-muitos e muitos-para-muitos.

## Objetivos

- **Preservação de Registros**: Registros importantes, como Pessoas, não são apagados definitivamente do banco de dados.
- **Filtro de Usuários Ativos**: Exibir apenas usuários ativos na lista de Pessoas por padrão.
- **Validação de Dados**: Implementação de validações no backend para evitar dados inválidos, como emails incorretos.
- **Consulta Rápida de Matrículas Confirmadas**: Possibilidade de consultar rapidamente todas as matrículas confirmadas de um determinado estudante.
- **Consulta de Turmas por Intervalo de Data**: Filtrar turmas abertas por intervalo de data para evitar informações desnecessárias.
- **Consulta de Matrículas por Curso**: Consultar matrículas por curso e identificar quais estão lotadas.
- **Cancelamento Automático de Matrículas**: Ao desativar o cadastro de um estudante, todas as suas matrículas são automaticamente canceladas.

## Instalação

1. Clone o repositório:
    ```sh
    git clone https://github.com/AndreAragaoSoftware/API-Escola
    ```

2. Navegue até o diretório do projeto:
    ```sh
    cd API-Escola
    ```

3. Instale as dependências:
    ```sh
    npm install
    ```

4. Configure o banco de dados:
    - Crie um banco de dados SQL.
    - Configure as credenciais do banco de dados no arquivo `config/config.json`.

5. Execute as migrações para criar as tabelas:
    ```sh
    npx sequelize db:migrate
    ```

6. Popule o banco de dados com dados iniciais (opcional):
    ```sh
    npx sequelize db:seed:all
    ```

7. Inicie o servidor:
    ```sh
    npm start
    ```

## Uso

A API possui diversas rotas para manipulação dos dados. Exemplos de uso das rotas:

- **GET** `/pessoas`: Retorna a lista de todos os usuários.
- **GET** `/pessoas/todos`: Retorna a lista de todos os usuários, incluindo inativos.
- **GET** `/pessoas/:id`: Retorna os detalhes de um usuário específico.
- **POST** `/pessoas`: Cria um novo usuário.
- **PUT** `/pessoas/:id`: Atualiza os dados de um usuário específico.
- **PUT** `/pessoas/:estudante_id/cancela`: Cancela o registro de um estudante e suas matrículas.
- **DELETE** `/pessoas/:id`: Marca um usuário como inativo ao invés de deletar.
- **GET** `/pessoas/:estudante_id/matriculas`: Retorna as matrículas ativas de um estudante.
- **GET** `/pessoas/:estudante_id/matriculas/todos`: Retorna todas as matrículas de um estudante.
- **GET** `/pessoas/:estudante_id/matriculas/confirmadas`: Retorna as matrículas confirmadas de um estudante.
- **GET** `/pessoas/matriculas/lotadas`: Retorna os cursos lotados.
- **GET** `/pessoas/:estudante_id/matriculas/:id`: Retorna uma matrícula específica de um estudante.
- **POST** `/pessoas/:estudante_id/matriculas`: Cria uma nova matrícula para um estudante.
- **PUT** `/pessoas/:estudante_id/matriculas/:id`: Atualiza uma matrícula específica de um estudante.
- **DELETE** `/pessoas/:estudante_id/matriculas/:id`: Exclui uma matrícula específica de um estudante.

## Próximos Passos

Embora a API esteja funcional, há várias melhorias que podem ser implementadas:

- **Funções Auxiliares**: Adicionar funções auxiliares para simplificar e organizar o código.
- **Validações**: Implementar validações mais robustas para os dados de entrada.
- **Melhorias na Estrutura do Código**: Refinar a estrutura do projeto para seguir melhores práticas e facilitar a manutenção.
- **Novas Funcionalidades**: Continuar expandindo a API conforme necessário para o negócio ou produto.

## Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues e pull requests.

## Licença

Este projeto está licenciado sob a licença MIT. Consulte o arquivo LICENSE para obter mais informações.

## Modelo de Dados

Abaixo está o diagrama de relacionamento das tabelas do banco de dados:

![Diagrama de Relacionamento](path/to/image.png)
