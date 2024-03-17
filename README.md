# API para Gerenciamento de Cursos de Programação

Este projeto consiste na implementação de uma API fictícia para uma empresa de cursos de programação. Inicialmente, a API oferece operações básicas de CRUD (Create, Read, Update, Delete) para gerenciamento de cursos.

## Funcionalidades

A API oferece as seguintes funcionalidades:

- Criação de um novo curso
- Listagem de todos os cursos
- Atualização de um curso pelo `id`
- Remoção de um curso pelo `id`
- Alteração do status de ativação de um curso

## Estrutura de Dados

Cada curso possui as seguintes propriedades:

- `id`: Identificador único de cada curso
- `name`: Nome do curso
- `category`: Categoria do curso
- `Active`: Define se o curso está ativo ou não
- `created_at`: Data de criação do curso
- `updated_at`: Data da última atualização do curso

## Rotas e Regras de Negócio

### `POST - /cursos`

Cria um novo curso no banco de dados, enviando os campos `name` e `category` no corpo da requisição. Os campos `id`, `created_at` e `updated_at` são preenchidos automaticamente.

### `GET - /cursos`

Lista todos os cursos salvos no banco de dados. Permite busca filtrando os cursos pelo `name` e `category`.

### `PUT - /cursos/:id`

Atualiza um curso pelo `id`. No corpo da requisição, deve receber somente o `name` e/ou `category` para atualização. Se for enviado somente o `name`, o `category` não pode ser atualizado e vice-versa. O campo `active`, se informado, será ignorado, pois a atualização do status deve ser feita através da rota PATCH.

### `DELETE - /cursos/:id`

Remove um curso pelo `id`.

### `PATCH - /cursos/:id/active`

Marca se o curso está ativo ou não (toggle entre true or false).

## Indo Além

Algumas sugestões para expandir o projeto:

- Validar se as propriedades `name` e `category` das rotas `POST` e `PUT` estão presentes no corpo da requisição.
- Utilizar um ENUM para definir o status de ativação dos cursos.
- Implementar tratamento de exceções para lidar com possíveis erros.

💡 Dica: Utilize as anotações `@CreationTimestamp` e `@UpdateTimestamp` para automatizar o preenchimento das datas de criação e atualização dos cursos.
