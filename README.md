
# API Tests com CI usando Newman e GitHub Actions

Este repositório de estudos tem como objetivo aplicar testes automatizados de API utilizando Postman + Newman, integrados a um fluxo de CI com GitHub Actions.

---

## Objetivo

Automatizar testes de APIs REST, garantindo qualidade e validação contínua a cada push na branch `main`, utilizando autenticação via token e integração com CI/CD.

---

## Tecnologias e Ferramentas

- [Postman](https://www.postman.com/) — criação e execução de collections de API
- [Newman](https://www.npmjs.com/package/newman) — executor de coleções Postman via CLI
- [GitHub Actions](https://docs.github.com/actions) — integração contínua
- [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) — scripts de validação nos testes

---

## Autenticação

Algumas requisições utilizam autenticação do tipo **Bearer Token**. O token é referenciado por variável de ambiente (`{{TOKEN}}`) no Postman, que é definido via arquivo `auth-env.json`.

---

## Como executar os testes

### Localmente (com Node.js e Newman)

```bash
npm install -g newman newman-reporter-html
newman run postman/collection.json -e postman/auth-env.json -r cli,html --reporter-html-export reports/report.html
```

### CI (GitHub Actions)

Os testes são executados automaticamente a cada `push` na branch `main`.

---

## Em andamento / Próximos passos

- [ ] Automatizar fluxo completo: login → criação de pedido → consulta por ID
- [ ] Adicionar validações de schema nas respostas
- [ ] Testes com dados dinâmicos/randomizados
- [ ] Incluir testes negativos (erros esperados)
- [ ] Deploy do relatório em GitHub Pages

