# Resumo – Aula 03: Introdução ao Versionamento e Deploy

**Professor:** Prof. Me. Deivison S. Takatu  
**Disciplina:** Programação Web

## Versionamento e backup

O versionamento identifica e registra cada versão de um software ou documento, permitindo acompanhar o que mudou, quem realizou a alteração e quando ela ocorreu. Já o backup é uma cópia de segurança de determinado estado dos dados.

| Versionamento | Backup |
|---|---|
| Histórico das alterações | Cópia pontual |
| Rastreabilidade e autoria | Não necessariamente registra autoria |
| Colaboração e integração de mudanças | Recuperação de dados |
| Reversão de alterações específicas | Restauração de cópias |

Os principais benefícios são trabalho simultâneo, redução de retrabalho, auditoria, recuperação de versões, testes antes da publicação e integração com ferramentas de desenvolvimento.

## Versionamento semântico (SemVer)

O padrão MAJOR.MINOR.PATCH comunica a natureza das mudanças.

| Campo | Significado | Exemplo |
|---|---|---|
| MAJOR | Alteração incompatível com versões anteriores | 2.0.0 |
| MINOR | Nova funcionalidade retrocompatível | 1.1.0 |
| PATCH | Correção de bugs sem quebra de compatibilidade | 1.1.1 |

A versão 1.0.0 representa o primeiro lançamento estável; versões 0.x.x indicam desenvolvimento inicial. O padrão facilita a gestão de dependências e a previsibilidade das atualizações.

Alterações podem envolver correção de bugs, novas funcionalidades, melhorias, refatoração, desempenho, segurança, atualização de dependências e inclusão de testes.

## Git e GitHub

Git é um sistema de controle de versões instalado localmente. GitHub permite hospedar repositórios e sincronizar o código entre desenvolvedores.

Comandos apresentados na aula:

```bash
git --version
git config --global user.name "Nome"
git config --global user.email "Email"
git tag
git tag 1.0.0
git push origin 1.0.0
```

No VS Code, o fluxo consiste em abrir a pasta do projeto, criar o arquivo index.html, inicializar o repositório na aba de controle de código-fonte, registrar um commit e publicar a branch no GitHub (pública ou privada).

## Tags, branches e merge

Tags marcam pontos importantes no histórico, como versões estáveis. Tags leves identificam um commit; tags anotadas armazenam informações adicionais, como mensagem, autor e data.

- **main/master:** versão principal estável.
- **develop:** integração de funcionalidades em desenvolvimento.
- **feature:** desenvolvimento isolado de uma nova funcionalidade.
- **hotfix:** correção urgente.

Merge integra alterações entre branches. Quando alterações incompatíveis atingem a mesma parte do código, pode ser necessário resolver conflitos manualmente.

Boas práticas: commits pequenos e frequentes, mensagens claras, atualização da branch antes do merge, testes automatizados e preservação da estabilidade da main.

## Deploy e Vercel

Deploy é o processo de disponibilizar uma aplicação em produção. Envolve compilação quando necessária, configuração do ambiente, testes finais e publicação.

- **Desenvolvimento:** ambiente local.
- **Staging:** ambiente de testes semelhante à produção.
- **Produção:** ambiente acessado pelos usuários.

Vercel é apresentada como plataforma para sites estáticos e aplicações modernas, com integração Git, deploy automático, rollback, suporte a frameworks como React e Vue, funções serverless e CDN global.

## Atividade proposta

1. Criar uma página HTML em um repositório GitHub.
2. Versionar as alterações e marcar versões estáveis com tags.
3. Personalizar a aplicação e publicar na Vercel.
4. Documentar escolhas de design, alterações e procedimentos, incluindo prints e links do GitHub e da Vercel.

## Conclusão da aula

O Git facilita a evolução e colaboração no código, enquanto o deploy disponibiliza o resultado para os usuários. O SemVer e as boas práticas tornam o processo mais organizado.

**Fonte:** slides da Aula 03 – Introdução ao Versionamento e Deploy (p. 3–30).
