# 🌿 Estratégias de Branching: Por que o GitLab Flow?

Para entender o fluxo ideal, é preciso contrapor as três principais metodologias de mercado e entender o motivo pelo qual o GitLab Flow resolve os gargalos corporativos.

## 1. Comparativo das Estratégias

| Critério | Git Flow (Legado) | GitHub Flow (Simples) | GitLab Flow (Ideal Corporativo) |
| :--- | :--- | :--- | :--- |
| **Complexidade** | Alta (muitas branches ativas simultaneamente) | Baixa (focado apenas em *main* e *feature*) | Equilibrada (simplicidade com suporte a ambientes) |
| **Ambientes de Homologação** | Difícil gerenciamento (merge hell entre *develop* e *release*) | Inexistente nativamente (geralmente vai direto para prod) | Nativo através de *Production/Staging Branches* ou Tags |
| **Correção de Hotfixes** | Complexa (exige merge em *develop* e *master* manual) | Relativamente simples, mas sem versionamento estruturado | Clara, utilizando o princípio *upstream-first* |
| **Adequação Corporativa** | Baixa para ciclos rápidos (causa atrito e conflitos) | Boa para microsserviços simples SaaS | Excelente para empresas de qualquer porte (SaaS ou Enterprise) |

---

## 2. O Princípio "Upstream-First"
No GitLab Flow, se você precisa corrigir um bug crítico diretamente em um ambiente de homologação ou em uma versão anterior (*Release Branch*):
1. Você aplica a correção na branch correspondente àquele ambiente.
2. O princípio **Upstream-first** exige que você faça o merge ou traga essa mesma correção de volta para a branch principal (`main`), garantindo que o erro não volte a ocorrer nas próximas versões do software.
