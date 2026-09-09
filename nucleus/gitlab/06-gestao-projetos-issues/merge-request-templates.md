# 🔀 Guia de Governança: Merge Requests (MR)

Este documento estabelece o padrão técnico e de rastreabilidade obrigatório para a abertura de Merge Requests (MR) no repositório, garantindo que toda alteração de código esteja vinculada a uma issue e passe por validações automatizadas de CI/CD.

---

## 1. Padrão de Nomenclatura de Branches
As ramificações de desenvolvimento devem seguir rigidamente o prefixo vinculado ao tipo de issue de origem:
* `bug/[numero-da-issue]-[descricao-curta]` (Ex: `bug/42-auth-timeout`)
* `feature/[numero-da-issue]-[descricao-curta]` (Ex: `feature/89-webhook-kanban`)
* `enterprise/[numero-da-issue]-[descricao-curta]` (Ex: `enterprise/102-ssl-rotation`)

---

## 2. Conteúdo de Referência para o Template de MR (`.gitlab/merge_request_templates/default.md`)

## 📝 Resumo da Alteração
Refatoração do módulo de autenticação para corrigir o vazamento de tokens de acesso e otimizar o tempo de resposta do middleware em 30%.

## 🔗 Issue Relacionada
Closes #[42]

## 🛠️ Tipo de Mudança
- [X] Correção de Bug (`tipo::bug`)
- [ ] Nova Funcionalidade (`tipo::feature`)
- [ ] Refatoração de Código (`tipo::debt`)
- [ ] Mudança de Infraestrutura / Enterprise (`tipo::enterprise`)

## 🧪 Como Testar e Validar
1. Executar a suíte de testes unitários com `npm test`.
2. Simular a requisição de login inválido via Postman e verificar o retorno HTTP 401 estruturado.
3. Validar a ausência de exceções no console do servidor.

## 📸 Evidências de Testes ou Prints
- Testes unitários executados com 100% de cobertura no módulo alterado.
- Build validado com sucesso no Pipeline CI/CD ID #8942.
