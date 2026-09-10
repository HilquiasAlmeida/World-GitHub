# 🔒 Compliance Pipelines e Governança de Segurança

  Este guia estabelece as diretrizes de conformidade corporativa, 
  regras de aprovação obrigatória e bloqueio automático de merges baseados em achados de segurança (*Security Gate*).

---

## 1. Regras de Bloqueio em Merge Requests (Security Gate)
  
  Para garantir que nenhum código vulnerável chegue à branch principal (`main`), 
   configuramos os portões de segurança (*Merge Request Approvals*):

  * **Bloqueio por Vulnerabilidade Crítica:**

      Se o relatório de SAST ou Container Scanning apontar uma vulnerabilidade com nível `
        Critical` ou `High`, o botão de Merge é desativado automaticamente pelo GitLab.
    
  * **Aprovação Obrigatória de Segurança (Infosec):**

      Achados de segurança exigem o crivo obrigatório de um membro do grupo
        corporativo de SegInfo através de regras de aprovação por elegibilidade de branch.

---

## 2. Compliance Frameworks globais
  No painel corporativo do GitLab (`Settings > General > Compliance frameworks`), 
    aplicamos frameworks que injetam obrigatoriamente pipelines de auditoria em todos os subgrupos do World GitHub, 
      impedindo que desenvolvedores desativem etapas de segurança nos arquivos `.gitlab-ci.yml` locais.
      
