# 📝 Templates do Issues do Gitlab em todos níveis profissionais

Este documento estabelece a arquitetura completa e padronizada para a abertura de chamados (Issues) no repositório. O framework foi desenhado para abranger múltiplos níveis operacionais — desde o suporte básico até a governança de engenharia avançada.

---

## 📑 Índice de Níveis de Governança
1. [Nível 1: Estrutura Base e Localização (Fundação)](#1-nível-1-estrutura-base-e-localização-fundação)
2. [Nível 2: Nível Operacional / Padrão (`bug-report.md`)](#2-nível-2-nível-operacional--padrão-bug-reportmd)
3. [Nível 3: Nível Avançado / Arquitetural (`feature-request.md`)](#3-nível-3-nível-avançado--arquitetural-feature-requestmd)
4. [Nível 4: Nível Enterprise / Automação via Frontmatter](#4-nível-4-nível-enterprise--automação-via-frontmatter)

---

## 1. Nível 1: Estrutura Base e Localização (Fundação)

O GitLab exige uma hierarquia rígida de diretórios para que o motor de templates reconheça os arquivos nativamente na interface de criação de chamados.

* **Caminho obrigatório na raiz:** `.gitlab/issue_templates/`
* **Mapeamento de Arquivos:**
  * `.gitlab/issue_templates/bug-report.md` (Para falhas e incidentes)
  * `.gitlab/issue_templates/feature-request.md` (Para evoluções e novas demandas)

---

## 2. Nível 2: Nível Operacional / Padrão (`bug-report.md`)

Destinado a capturar o contexto mínimo necessário para que qualquer desenvolvedor reproduza, isole e corrija uma falha sem atritos de comunicação.

### Conteúdo de referência para o arquivo `.gitlab/issue_templates/bug-report.md`:
```markdown
---
name: 🐛 Relatório de Bug (Nível Operacional)
about: Relate comportamentos inesperados com dados de reprodução e ambiente.
title: "[BUG] "
labels: "tipo::bug, status::aguardando-triagem"
---
```

## 📋 Descrição do Problema
O botão de autenticação na tela de login travou e parou de responder aos cliques após o último deploy da versão 2.4, impedindo o acesso dos operadores da fila de atendimento.

## 🌐 Contexto e Ambiente
- **Versão/Release:** v2.4.1-rc
- **Ambiente afetado:** [X] Produção [ ] Homologação [ ] Desenvolvimento
- **Navegador / OS (se aplicável):** Google Chrome / Windows 11

## 🔄 Passos para Reproduzir
1. O operador acessa a URL de login do sistema.
2. Insere as credenciais corporativas válidas.
3. Clica no botão "Entrar" e o sistema congela sem retornar nenhuma mensagem de erro na interface.

## 🎯 Comportamento Esperado
O sistema valida as credenciais instantaneamente, autentica o usuário e redireciona a navegação para o Dashboard principal em até 2 segundos.

## 📸 Evidências, Logs ou Stacktrace
```text
[ERROR] 2026-06-06 14:10:22 - AuthController: Uncaught TypeError: Cannot read properties of undefined (reading 'token')
    at handleLoginSubmit (auth.service.js:45:18)
```

---

## 3. Nível 3: Nível Avançado / Arquitetural (`feature-request.md`)

Destinado a demandas de alto impacto, mudanças estruturais, melhorias de performance ou novas features de produto que exigem validação de critérios de aceite rigorosos.

### Conteúdo de referência para o arquivo `.gitlab/issue_templates/feature-request.md`:
```markdown
---
name: ✨ Nova Funcionalidade (Nível Avançado)
about: Proponha evoluções de arquitetura, fluxos ou melhorias de produto.
title: "[FEAT] "
labels: "tipo::feature, status::aguardando-triagem"
---
```

## 🎯 Objetivo de Negócio
Redução do tempo de triagem manual de chamados em 40%, automatizando a atribuição de labels e prioridades críticas logo na abertura da issue pela equipe de suporte.

## 🚀 Proposta de Solução Técnica
Implementação de um webhook no GitLab integrado a um script em Python que lê o bloco Frontmatter do arquivo de template e aplica as tags correspondentes no sistema Kanban corporativo no momento da criação.

## 📐 Critérios de Aceite (Definition of Done)
- [ ] O componente atende aos padrões de segurança definidos na Pasta 07.
- [ ] Os testes unitários cobrem ao menos 80% da nova regra de negócio.
- [ ] Documentação atualizada nos arquivos de arquitetura do repositório.

## 🔗 Dependências ou Impactos Colaterais
Esta alteração exige a atualização prévia da API de Permissões v2 e impacta diretamente o pipeline de CI/CD do microsserviço de gestão de usuários.

---

## 4. Nível 4: Nível Enterprise / Automação via Frontmatter

Em projetos de grande escala corporativa, o uso do bloco YAML Frontmatter no início de cada template garante a padronização e acelera o fluxo de trabalho automatizado no GitLab:

```yaml
---
name: "🏢 [Enterprise] Demanda Corporativa Crítica"
about: "Template avançado com governança, labels automáticas e atribuições pré-definidas."
title: "[CORP] "
labels: "tipo::enterprise, prioridade::critica, status::aguardando-triagem, seguranca::revisar"
milestone: "Sprint de Governança"
---
```

**Propriedades do Frontmatter Enterprise**:
  * `name`: Nome amigável e formal exibido no menu suspenso de criação de issues do GitLab.
  * `about`: Contexto descritivo exibido para orientar o colaborador antes da seleção.
  * `title`: Prefixo automatizado (`[CORP]`) aplicado na abertura, assegurando a indexação e busca.
  * `labels`: Injeção simultânea de múltiplas taxonomias (tipo::enterprise, prioridade::critica, status::aguardando-triagem, seguranca::revisar) para direcionamento imediato ao fluxo correto no Kanban.
  * `milestone`: Associação opcional a ciclos de entrega corporativos pré-definidos.
