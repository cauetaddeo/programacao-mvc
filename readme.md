### Aula 5 programação:


### Models 
Os models são responsáveis por representar os dados da aplicação e interagir com o banco de dados.  
Por exemplo, o model Aluno pode ter funções para criar, buscar, atualizar ou excluir registros de alunos no banco de dados.

### Controllers 
Os controllers atuam como intermediários entre o que o usuário faz e o processamento dos dados.  
Quando um usuário envia uma solicitação, como preencher um formulário, o controller recebe essa informação, consulta ou altera os dados com os models e, em seguida, envia uma resposta, como renderizar uma página ou retornar uma mensagem.

### Endpoints 
Os endpoints representam as URLs da aplicação que o usuário acessa.  
Cada URL corresponde a uma rota específica, como `/alunos`, `/cursos` ou `/login`.  
Cada rota está associada a um controller e geralmente responde a diferentes métodos HTTP, como `GET` (para buscar dados), `POST` (para enviar dados), `PUT` (para atualizar dados) ou `DELETE` (para remover dados).
