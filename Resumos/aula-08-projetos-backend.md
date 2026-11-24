# Resumo – Aula 08: Atividade com Projetos Back-end

**Professor:** Prof. Me. Deivison S. Takatu  
**Disciplina:** Programação Web

## Revisão de back-end e HTTP

Frameworks organizam o código com MVC, arquitetura em camadas e módulos independentes, facilitando manutenção e reutilização.

HTTP é o protocolo de comunicação entre cliente e servidor. Cada requisição é independente. JSON (JavaScript Object Notation) representa dados por objetos com pares chave/valor e listas ordenadas (arrays).

| Método HTTP | Operação |
|---|---|
| GET | Recuperar informações |
| POST | Criar um recurso |
| PUT | Substituir um recurso |
| PATCH | Atualizar parcialmente |
| DELETE | Remover um recurso |

GET é seguro e idempotente quanto ao efeito; POST pode criar registros repetidos. DELETE é idempotente quanto à remoção pretendida.

## Projeto de notas com Express

A aula evolui a API de data e hora para uma aplicação de gerenciamento de notas, utilizando CRUD (Create, Read, Update e Delete).

O projeto possui um arquivo server.js para configurar o servidor e definir as rotas, e data.json para armazenar as notas. A interface apresentada no slide 13 possui formulário de cadastro e cartões com botões de edição e exclusão.

### Rotas da API

| Método | Endpoint | Ação |
|---|---|---|
| GET | /api/notes | Listar todas as notas |
| POST | /api/notes | Criar uma nota com título e texto |
| PUT | /api/notes/:id | Atualizar a nota identificada pelo ID |
| DELETE | /api/notes/:id | Excluir uma nota |

### Desenvolvimento

```bash
npm install express
npm install body-parser
node server.js
```

O código apresentado importa Express, body-parser e fs (módulo de arquivos do Node.js). O body-parser permite interpretar JSON recebido no corpo das requisições. Um middleware adiciona o cabeçalho Access-Control-Allow-Origin.

- readNotes(): lê o arquivo com fs.readFileSync e converte o JSON; em caso de erro, retorna uma lista vazia.
- saveNotes(): grava os dados com fs.writeFileSync e JSON.stringify.
- GET: retorna a lista.
- POST: gera um ID com Date.now().toString(), adiciona título e texto e salva.
- PUT: encontra o ID, atualiza a nota e retorna 404 caso não encontre.
- DELETE: filtra a lista removendo o ID e salva novamente.

Exemplo de estrutura de data.json (slide 21):

```json
[
  {
    "id": "1",
    "titulo": "Lembretes",
    "texto": "Comprar leite e pão",
    "criadoEm": "2025-04-29T10:00:00Z"
  }
]
```

**Observação sobre os slides:** a descrição das rotas (p. 14) menciona data de criação e status 204 no DELETE. O código das páginas 18 e 20 não inclui a data no POST e retorna uma mensagem JSON no DELETE. Esses detalhes precisam ser alinhados na implementação.

## Deploy e integração

Render é apresentado como hospedagem em nuvem para o servidor, com integração ao GitHub e deploy contínuo. Após publicar o back-end, a interface React deve substituir o endpoint localhost:3000/api/notes pela URL online. O front-end é publicado separadamente na Vercel.

O front-end deve consumir todas as quatro operações CRUD.

## Segurança, persistência e organização

A aula propõe refletir sobre riscos de segurança, vantagens e desvantagens do armazenamento em JSON, limitações com 10 mil registros e os problemas de concentrar toda a lógica em server.js. São questões de análise para avaliar se a solução didática é adequada à produção.

## Postman e documentação de APIs

Postman é uma ferramenta para criar, testar, documentar e monitorar APIs. Permite enviar requisições HTTP, analisar respostas e organizar endpoints em coleções compartilháveis.

A documentação deve descrever endpoints, métodos, parâmetros, formatos de resposta, códigos de status e exemplos de requisições.

Outros recursos apresentados: variáveis de ambiente, scripts pré-request, testes automatizados, geração de documentação, Newman para CI/CD, Mock Servers, monitoramento e suporte a GraphQL, WebSockets e OAuth 2.0.

## Atividade proposta

1. Desenvolver e publicar a API Express no Render.
2. Criar um front-end para cadastrar, visualizar, editar e excluir notas.
3. Documentar com prints, links do GitHub e da Vercel.
4. Criar uma coleção Postman com as quatro operações CRUD.
5. Configurar parâmetros e descrever os códigos de resposta.
6. Incluir o link da coleção e entregar a documentação no repositório da disciplina.

## Conclusão da aula

A prática reúne desenvolvimento de APIs, persistência de dados em JSON, integração front-end e back-end, publicação, testes e documentação técnica.

**Fonte:** slides da Aula 08 – Atividade com Projetos Back-end (p. 3–33).
