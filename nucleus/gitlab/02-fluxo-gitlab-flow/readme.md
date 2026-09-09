# 🔀 02. Fluxo de Trabalho: GitLab Flow e Governança de Merge Requests

Este diretório estabelece o modelo oficial de engenharia para o fluxo de desenvolvimento, estratégias de *branching*, padrões de revisão de código e governança de entregas dentro do ecossistema do GitLab.

---

## 1. O que é o GitLab Flow?
O **GitLab Flow** combina a simplicidade do controle baseado em features com a robustez de ambientes de produção isolados. Diferente do Git Flow tradicional (que sofre de múltiplos *long-lived branches* como *develop*, *release*, *hotfix* complexos), o GitLab Flow simplifica o ciclo utilizando o princípio fundamental de **Upstream-first** (o código flui sempre das branches de desenvolvimento para as instâncias de homologação e produção).

* **Regra de Ouro**: Todo código transita através de **Merge Requests (MRs)** bem fundamentados, garantindo rastreabilidade entre a Issue de planejamento e o artefato entregue em produção.

---

## 2. Gerenciamento de Ambientes e Release Branches
Em ambientes corporativos de alta escala, o GitLab Flow permite gerenciar múltiplos ambientes de forma transparente:
* **Ambientes de Produção Contínua**: Branches orientadas a tags de versão ou deploys automáticos via *main/master*.
* **Ambientes de Staging / Pre-production**: Branches dedicadas a homologação (`staging`) onde o código é validado antes de atingir o usuário final.
* **Release Branches (quando necessário)**: Em softwares versionados (on-premise ou pacotes fechados), criam-se branches de release a partir da `main` apenas para correção de bugs pontuais (*patch releases*), aplicando o conceito *upstream-first* (corrigindo na branch de release e fazendo *cherry-pick* ou merge de volta para a `main`).

---

## 📂 Documentação Detalhada Deste Módulo
Para dominar a engenharia por trás do fluxo de trabalho, consulte os documentos complementares:

* 📊 **Estratégias de Branching**: Leia a comparação técnica em [`estrategias-branching.md`](./estrategias-branching.md) contrastando Git Flow, GitHub Flow e GitLab Flow.
* 🔄 **Anatomia do Merge Request**: Consulte o padrão corporativo de revisões, automações e estratégias de merge em [`ciclo-merge-request.md`](./ciclo-merge-request.md).
* 🛡️ **Governança e Proteções**: Analise as políticas de segurança de branches e arquivos `CODEOWNERS` em [`protecoes-branch-governance.md`](./protecoes-branch-governance.md).
