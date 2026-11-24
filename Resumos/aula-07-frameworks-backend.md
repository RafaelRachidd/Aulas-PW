# Resumo – Aula 07: Introdução a Frameworks Back-end

**Professor:** Prof. Me. Deivison S. Takatu  
**Disciplina:** Programação Web

## Frameworks back-end

Um framework back-end reúne ferramentas, bibliotecas e convenções para organizar a lógica do servidor, as APIs e a integração com bancos de dados. Em relação ao desenvolvimento sem frameworks, reduz configurações repetitivas e facilita a manutenção, a organização das rotas e a escalabilidade.

Características apresentadas:

- Arquitetura MVC ou em camadas, separando responsabilidades.
- Componentização em módulos, serviços e middlewares.
- Programação assíncrona para operações de entrada e saída, como acesso a bancos e APIs.
- Recursos de segurança, autenticação, validação e logging, conforme o framework e sua configuração.
- Gerenciamento de rotas e APIs REST ou GraphQL.

| Framework | Linguagem | Características |
|---|---|---|
| Express.js | JavaScript / Node.js | Minimalista, flexível e extensível por middlewares |
| Django | Python | ORM, autenticação e painel administrativo |
| Laravel | PHP | Eloquent, sistema de rotas e Artisan |

A escolha depende da complexidade, desempenho, curva de aprendizado, manutenção e comunidade.

## Arquitetura e padrões de projeto

A arquitetura deve atender aos requisitos, tamanho da equipe, objetivos do negócio e necessidades de evolução. MVC (Model-View-Controller) separa modelo, visão e controlador.

Os design patterns são organizados em três categorias:

- **Criacionais:** Factory, Singleton e Builder; organizam a criação de objetos.
- **Estruturais:** Adapter, Composite e Proxy; organizam a composição de classes e objetos.
- **Comportamentais:** Observer, Strategy e Command; organizam interações e responsabilidades.

| Monolito | Microsserviços |
|---|---|
| Módulos integrados em uma aplicação | Serviços independentes |
| Operação inicialmente mais simples | Escalabilidade independente e flexibilidade |
| Pode dificultar escala isolada | Maior complexidade operacional |

O caso Amazon Prime Video apresentado na aula relata redução de custos de 90% após reorganizar uma solução distribuída em uma arquitetura monolítica. A lição é que a arquitetura deve atender ao problema, sem seguir tendências automaticamente.

## Express.js

Express é um framework leve para criar servidores web e APIs com Node.js. Facilita o roteamento, o processamento de requisições e o uso de middlewares (funções intermediárias para autenticação, logs e outras tarefas).

O fluxo de uma requisição é: front-end → requisição HTTP → servidor Express → banco de dados ou API externa → resposta JSON → atualização da interface.

Express é indicado para APIs REST, integração com dados e prototipação. Aplicações em tempo real podem utilizar WebSockets; processamento pesado pode ser separado em Workers.

## HTTP, API e REST

HTTP estabelece a comunicação cliente-servidor. Cada requisição é independente (stateless). Uma API define como componentes ou sistemas interagem.

REST é um estilo arquitetural que utiliza recursos identificados por URIs, comunicação sem estado, métodos HTTP e representações como JSON. Um endpoint é um endereço de acesso a um recurso ou funcionalidade.

| Método | Finalidade |
|---|---|
| GET | Consultar recursos, sem alterar dados |
| POST | Criar recursos |
| PUT | Substituir um recurso existente |
| PATCH | Atualizar parte de um recurso |
| DELETE | Remover um recurso |

GET e DELETE são idempotentes quanto ao efeito pretendido; POST pode criar novos recursos em chamadas repetidas.

O servidor back-end executa regras de negócio, gerencia dados e fornece respostas. Web services permitem a comunicação padronizada entre sistemas por HTTP/HTTPS.

JSON é um formato leve de troca de dados baseado em objetos (pares chave/valor) e arrays (listas ordenadas).

## Criando e publicando uma API

A aula utiliza Express e CORS, mecanismo que controla o acesso a recursos entre origens diferentes no navegador.

```bash
npm install express
npm install cors express
node api.js
```

No exemplo do slide 25, o arquivo api.js configura Express, utiliza cors(), define uma rota GET que retorna a data e hora em JSON e inicia o servidor com uma porta configurada pelo ambiente ou 3000.

Para publicação, enviar o projeto ao GitHub, criar um Web Service no Render, conectar o repositório, configurar os comandos de build e start e utilizar a URL gerada. O Render oferece integração Git, deploy contínuo, SSL e monitoramento; o material apresenta opções para projetos acadêmicos.

## Atividade proposta

1. Criar uma API Express com uma rota de consulta de data e hora.
2. Publicar o back-end no Render.
3. Criar um front-end que consuma a API e exiba data e hora, em outro repositório.
4. Documentar com prints do código, aplicação e painéis Render/Vercel, incluindo links dos repositórios.

## Conclusão da aula

Frameworks back-end organizam a lógica do servidor. Express permite desenvolver APIs REST que utilizam HTTP e JSON para integrar aplicações.

**Fonte:** slides da Aula 07 – Introdução a Frameworks Back-end (p. 3–30).
