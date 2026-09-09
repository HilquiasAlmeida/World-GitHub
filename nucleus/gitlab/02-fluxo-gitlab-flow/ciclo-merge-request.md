# 🔄 O Ciclo de Vida do Merge Request (MR) no GitLab

O **Merge Request (MR)** é o coração da colaboração e da qualidade de código no GitLab. Ele deixa de ser apenas um pedido de inclusão de código e se torna um portão de qualidade automatizado.

## 1. Anatomia de um MR de Alta Performance
Um MR corporativo padrão deve conter:
* **Vinculação de Issue**: Sempre referenciar a issue de origem utilizando palavras-chave automatizadas (ex: `Closes #42` ou `Relates to #18`), garantindo rastreabilidade no Kanban.
* **Template Padronizado**: Descrição clara contendo o *Contexto da Mudança*, *Testes Realizados* e *Evidências de QA*.
* **Pipelines Verdes**: O MR só pode ser aceito se todos os testes unitários, de integração e varreduras de segurança (*SAST/Secret Detection*) passarem com sucesso.

---

## 2. Estratégias de Merge (Merge Methods)
O GitLab suporta diferentes estratégias de fechamento de MR para manter o histórico do Git limpo:
* **Merge Commit**: Cria um commit de merge explícito. Preserva todo o histórico detalhado de qual branch veio a alteração (ideal para auditorias rígidas).
* **Fast-forward Merge**: Insere os commits da feature diretamente na branch de destino de forma linear, sem commit de merge (mantém o histórico linear, mas exige rebase frequente).
* **Squash and Merge**: Compacta todos os commits da branch de feature em **um único commit limpo** antes de injetá-lo na branch principal. É a estratégia mais recomendada para evitar poluição no histórico de commits da `main`.
