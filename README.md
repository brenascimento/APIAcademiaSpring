<em>Projeto feito com a ajuda da Digital Innovation One no Bootcamp Carrefour Web Developer</em>

<hr>

<em> [Link para o repositório original](https://github.com/cami-la/academia-digital) </em>

<p>Nesse projeto fiz uma API Rest para uma Academia com as seguintes Entidades: </p>
<ul>
    <li>Alunos</li>
    <li>Avaliação Física</li>
    <li>Matrículas</li>
</ul>

<p>Todos com o seu devido endpoint</p>

## GET
### Alunos
* `localhost:8080/alunos` - retorna todos os Alunos
* `localhost:8080/alunos/{id}` - retorna somente um Aluno pela Id
* `localhost:8080/alunos/avaliacoes/{id}` - retorna todas as avaliações pela Id do Aluno
* `localhost:8080/alunos?dataDeNascimento={valor}` - retorna uma lista de alunos baseado no parametro Data de Nascimento

### Avaliação Física
* `localhost:8080/avaliacoes` - retorna todas as Avaliações Físicas
* `localhost:8080/avaliacoes/{id}` - retorna uma Avaliação Física pela Id

### Matrículas
* `localhost:8080/matriculas` - Retorna todas as matrículas
* `localhost:8080/matriculas/{id}` - Retorna uma matrícula pelo Id
* `localhost:8080/matriculas?bairro={valor}` - Retorna uma lista de matrículas baseados no bairro do Aluno matriculado.

## POST
### Alunos
* `localhost:8080/alunos` - cria um aluno no banco de dados, e retorna seu valor.
    * Request Body:
        * `Nome`
        * `CPF`
        * `Bairro`
        * `Data de Nascimento`

### Avaliação Física
* `localhost:8080/avaliacoes` - cria uma avaliação fisíca no banco de dados, e retorna seu valor.
    * Request Body:
        * `AlunoId`
        * `Peso`
        * `Altura`

### Matrículas
* `localhost:8080/matriculas` - cria uma matrícula no banco de dados, e retorna seu valor.
    * Request Body:
        * `AlunoId`

## PUT
### Alunos
* `localhost:8080/alunos/{id}`
    * Request Body:
        * `Nome`
        * `Bairro`
        * `Data de Nascimento`

### Avaliação Física
* `localhost:8080/avaliacoes/{id}`
    * Request Body:
        * `Peso`
        * `Altura`


## DELETE

### Alunos
* `localhost:8080/alunos/{id}` - Deleta um aluno pela Id

### Avaliação Física
* `localhost:8080/avaliacoes/{id}` - Deleta uma avaliação física pela Id

### Matrículas
* `localhost:8080/matriculas/{id}` - Deleta uma matrícula pela Id

## Observações
* Por conta de um pequeno erro na hora de deletar registros com relacionamento em outras tabelas, decidi utilizar `@OnDelete(action = OnDeleteAction.CASCADE)` em todos os campos com algum tipo de relacionamento, por exemplo: 

```java
    @ManyToOne
    @OnDelete(action = OnDeleteAction.CASCADE)
    @JoinColumn(name = "aluno_id")
    private Aluno aluno;
```




