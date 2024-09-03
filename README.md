# Sistema de Registro de Alunos e Notas

## Descrição do Projeto

Este projeto é um sistema de gerenciamento de registros de alunos, cursos e suas respectivas notas, desenvolvido utilizando SQL. O sistema permite criar um banco de dados relacional para armazenar informações de alunos, cursos e notas, além de realizar operações básicas de inserção, consulta, atualização e exclusão de dados.

## Estrutura do Banco de Dados

O banco de dados chamado **Escola** contém três tabelas principais:

1. **Alunos**: Armazena informações sobre os alunos, como nome, data de nascimento e endereço.
   - **Campos**:
     - `id_aluno` (INT, chave primária, auto incremento)
     - `nome` (VARCHAR, nome do aluno)
     - `data_nascimento` (DATE, data de nascimento do aluno)
     - `endereco` (VARCHAR, endereço do aluno)

2. **Cursos**: Contém informações sobre os cursos disponíveis.
   - **Campos**:
     - `id_curso` (INT, chave primária, auto incremento)
     - `nome_curso` (VARCHAR, nome do curso)
     - `descricao` (TEXT, descrição do curso)

3. **Notas**: Armazena as notas dos alunos em cursos específicos.
   - **Campos**:
     - `id_nota` (INT, chave primária, auto incremento)
     - `id_aluno` (INT, chave estrangeira, referencia `Alunos`)
     - `id_curso` (INT, chave estrangeira, referencia `Cursos`)
     - `nota` (DECIMAL, nota atribuída ao aluno no curso)

## Funcionalidades

- **Criação de Banco de Dados**: Criação do banco de dados `Escola`.
- **Criação de Tabelas**: Criação das tabelas `Alunos`, `Cursos`, e `Notas` com chaves primárias e estrangeiras para assegurar integridade referencial.
- **Inserção de Dados**: Inserção de registros de alunos, cursos e notas.
- **Consultas**:
  - Listagem de alunos e suas notas.
  - Cálculo da média das notas por curso.
  - Identificação do aluno com a maior nota em cada curso.
- **Atualização de Dados**:
  - Atualização de notas de alunos.
  - Modificação de endereços de alunos.
- **Exclusão de Dados**:
  - Exclusão de alunos e notas associadas.
  - Remoção de cursos e notas associadas.

## Instruções de Uso

1. **Criação do Banco de Dados e Tabelas**
   - Execute o script SQL para criar o banco de dados `Escola` e as tabelas associadas.

2. **Inserção de Dados**
   - Insira registros de alunos, cursos e notas utilizando os comandos `INSERT`.

3. **Consultas**
   - Utilize os comandos `SELECT` com `JOIN` para consultar os dados conforme necessário.

4. **Atualização e Exclusão de Dados**
   - Use os comandos `UPDATE` para atualizar registros e `DELETE` para remover alunos, cursos e suas notas.

## Exemplos de Uso

- Para listar todos os alunos com suas notas:
  ```sql
  SELECT Alunos.nome, Cursos.nome_curso, Notas.nota
  FROM Notas
  JOIN Alunos ON Notas.id_aluno = Alunos.id_aluno
  JOIN Cursos ON Notas.id_curso = Cursos.id_curso;
