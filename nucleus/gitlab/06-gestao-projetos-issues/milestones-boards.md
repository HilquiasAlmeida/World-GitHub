# 📊 Guia de Governança: Milestones e Issue Boards

Este documento formaliza a estrutura de ciclos temporais (**Milestones**) e organização visual de fluxos (**Issue Boards / Kanban**) do projeto World GitHub, garantindo alinhamento entre planejamento estratégico e execução operacional.

---

## 📑 Índice de Estrutura
1. [Conceito e Padronização de Milestones](#1-conceito-e-padronização-de-milestones)
2. [Arquitetura de Visualização: Issue Boards](#2-arquitetura-de-visualização-issue-boards)
3. [Exemplo Prático de Fluxo Kanban Integrado](#3-exemplo-prático-de-fluxo-kanban-integrado)

---

## 1. Conceito e Padronização de Milestones
As **Milestones (Marcos temporais)** funcionam como contêineres de prazo e entregáveis para ciclos de desenvolvimento ágil (Sprints) ou versões de release do produto.

* **Padrão de Nomenclatura:** 
  * Ciclos Ágeis: `Sprint [Número] - [Mês/Ano]` (Ex: `Sprint 14 - Junho/2026`)
  * Versões de Release: `Release v[Major].[Minor].[Patch]` (Ex: `Release v2.4.0`)
* **Regras de Governança:**
  * Toda issue crítica ou de feature deve obrigatoriamente estar associada a uma Milestone ativa para compor o escopo de entrega do time.
  * O encerramento de uma Milestone exige que todas as issues remanescentes sem conclusão sejam reavaliadas e migradas para o ciclo subsequente (replanejamento).

---

## 2. Arquitetura de Visualização: Issue Boards
Os quadros Kanban nativos refletem exatamente a taxonomia de labels do namespace `status::`, garantindo rastreabilidade visual sem esforço manual de movimentação quando integrados a automações.

* **Coluna 1: Backlog / Triagem**
  * *Filtro de Label:* `status::aguardando-triagem`
  * *Objetivo:* Centralizar todas as novas entradas geradas pelos templates para qualificação técnica.
* **Coluna 2: Desenvolvimento Ativo**
  * *Filtro de Label:* `status::em-desenvolvimento`
  * *Objetivo:* Acompanhar as demandas que estão sendo codificadas pelos desenvolvedores alocados.
* **Coluna 3: Revisão por Pares (Code Review)**
  * *Filtro de Label:* `status::em-code-review`
  * *Objetivo:* Isolar gargalos de revisão de código e garantir qualidade antes dos testes.
* **Coluna 4: Homologação e QA**
  * *Filtro de Label:* `status::homologacao`
  * *Objetivo:* Validar cenários de negócio em ambiente espelhado ao de produção.
* **Coluna 5: Concluído**
  * *Filtro de Label:* `status::concluido`
  * *Objetivo:* Repositório histórico de entregas válidas do ciclo vigente.

---

## 3. Exemplo Prático de Fluxo Kanban Integrado

O diagrama abaixo ilustra o ciclo de vida completo de uma issue desde a sua criação via template enterprise até a conclusão no Board de Governança:

```mermaid
stateDiagram-v2
    [*] --> AguardandoTriagem: Abertura via Template [CORP/BUG/FEAT]
    AguardandoTriagem --> EmDesenvolvimento: Atribuição de Responsável & Sprint
    EmDesenvolvimento --> EmCodeReview: Abertura de Pull / Merge Request
    EmCodeReview --> Homologacao: Aprovação de Código & Build CI/CD Sucesso
    Homologacao --> Concluido: Validação de QA & Deploy em Produção
    Concluido --> [*]
