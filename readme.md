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

# Aula 6 programação:

### Arquitetura MVC
O projeto usa a arquitetura MVC, que divide o código em três partes:

Model (Modelo): Cuida dos dados e do banco de dados. No cadastro de alunos, o Model guarda informações como nome, idade e matrícula dos alunos. Também é quem salva, busca, atualiza ou apaga esses dados no banco.

View (Visão): É a parte que mostra as informações na tela. São as páginas HTML que têm formulários para cadastrar alunos e tabelas que mostram a lista de alunos.

Controller (Controlador): Liga tudo. O Controller recebe os pedidos do usuário, pega ou salva informações no Model e depois escolhe qual página (View) vai ser mostrada ou se a resposta será em JSON.

### Como eles se comunicam
Quando o usuário faz alguma ação (como cadastrar um aluno ou abrir a lista), quem recebe é o Controller. O Controller conversa com o Model para buscar ou salvar os dados. Depois, ele manda os dados para a View, que monta a página para o usuário ver.

O caminho funciona assim:
Usuário → Controller → Model → Controller → View

### Envio e recebimento de dados JSON:
O projeto também tem rotas que trabalham com JSON, que é um jeito simples de enviar e receber dados, sem precisar de uma página HTML.

### Exemplo de rota que responde em JSON:
```
javascript
Copiar
Editar
app.get('/api/alunos', (req, res) => {
    Aluno.findAll()
        .then(alunos => res.json(alunos));
}); 
```
Essa rota pega todos os alunos do banco de dados e responde em JSON. Ela é usada para quem quer os dados de alunos direto, como em uma API ou integração com outro sistema.

### Por que usar HTML:
Mesmo com JSON e API, usar HTML com formulários e tabelas é importante porque:

1- Permite que o usuário cadastre e veja os alunos direto pelo navegador.

2- Os formulários servem para enviar informações (como nome, idade, matrícula).

3- As tabelas ajudam a mostrar os alunos de forma organizada e fácil de entender.

### Por que isso ainda é útil no back-end:
Ter páginas simples em HTML no próprio back-end com Node.js é útil porque:

1- É mais rápido e fácil de fazer.

2- Não precisa de outro sistema para o front-end.

3- Serve muito bem para sistemas internos, testes e projetos mais simples.
