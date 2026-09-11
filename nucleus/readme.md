# ⚙️ Nucleus: O Motor Oficial e o Coração do Ecossistema

Bem-vindo ao diretório **`nucleus/`** do projeto **World-GitHub**. 

Este diretório abriga estritamente o **núcleo nativo, oficial e essencial** do ecossistema de controle de versão. Aqui estão concentrados os comandos fundamentais, os fluxos de trabalho padrão da indústria e as extensões oficiais fornecidas nativamente pelas plataformas de desenvolvimento (Git, GitHub e GitLab).

---

## 🌳 Estrutura do Núcleo

```text
nucleus/
├── README.md                                       # Documentação geral do núcleo (este arquivo)
├── git/                                            # O motor de versionamento local e utilitários
│   ├── README.md                                   # Guia e índice do diretório Git
│   ├── git-graph/                                  # Visualização de histórico e interfaces em árvore
│   ├── git-hooks/                                  # Automações e scripts locais disparados pelo fluxo do Git
│   └── git-lfs/                                    # Gerenciamento de arquivos binários grandes (Large File Storage)
├── github/                                         # O ecossistema oficial, CLI e recursos do GitHub
│   ├── README.md                                   # Guia e índice do diretório GitHub
│   ├── github-actions/                             # Automação de CI/CD, workflows e robôs de integração
│   ├── github-flow/                                # Metodologias e fluxos oficiais de trabalho em equipe
│   ├── github-pages/                               # Hospedagem gratuita de sites estáticos direto do repositório
│   └── github-security/                            # Chaves SSH, tokens de acesso (PAT) e governança de segurança
└── gitlab/                                         # A plataforma corporativa, comandos e ecossistema GitLab
    ├── README.md                                   # Guia e índice do diretório GitLab
    ├── 01-fundamentos-visao-geral/                 # Introdução aos conceitos e arquitetura base
    │   ├── arquitetura-componentes.md              # Estrutura interna e componentes essenciais do GitLab
    │   ├── comparativo-ferramentas.md              # Comparativo prático entre plataformas de versionamento
    │   ├── licenciamento-versoes.md                # Diferenças entre licenças (Free, Premium, Ultimate)
    │   └── readme.md                               # Guia e índice específico do módulo 01
    ├── 02-fluxo-gitlab-flow/                       # Metodologias e fluxos oficiais de trabalho em equipe
    │   ├── ciclo-merge-request.md                  # O ciclo de vida completo de um Merge Request (MR)
    │   ├── estrategias-branching.md                # Estratégias eficientes de ramificação de código
    │   ├── protecoes-branch-governance.md          # Regras de proteção de branches e governança de código
    │   └── readme.md                               # Guia e índice específico do módulo 02
    ├── 03-cli-glab-terminal/                       # Domínio da ferramenta de linha de comando oficial (`glab`)
    │   ├── hierarquia-planejamento.md              # Organização de tarefas e planejamento via terminal
    │   ├── quadros-kanban-avancados.md             # Manipulação de quadros ágeis diretamente pelo CLI
    │   ├── templates-rastreabilidade.md            # Padrões de rastreabilidade de tarefas e issues
    │   └── readme.md                               # Guia e índice específico do módulo 03
    ├── 04-integracao-git-local/                    # Conexão e configuração da máquina local com o GitLab
    │   ├── autenticacao-ssh.md                     # Configuração segura de chaves SSH para comunicação
    │   ├── multiplos-perfis-gitconfig.md           # Gestão de múltiplos perfis, e-mails e chaves no Git
    │   ├── personal-access-tokens.md               # Geração e uso seguro de Tokens de Acesso Pessoal (PAT)
    │   └── readme.md                               # Guia e índice específico do módulo 04
    ├── 05-pipelines-ci-cd/                         # Automação de processos, testes e entrega contínua
    │   ├── deploy-multi-ambiente.md                # Automação de deploys entre ambientes (Dev, Staging, Prod)
    │   ├── variaveis-secrets.md                    # Gestão segura de variáveis de ambiente e segredos
    │   └── readme.md                               # Guia e índice específico do módulo 05
    ├── 06-gestao-projetos-issues/                  # Governança de projetos, marcos e acompanhamento de entregas
    │   ├── dor-dod-policy.md                       # Definição de Pronto (DoD) e Pronto para Iniciar (DoR)
    │   ├── issue-templates.md                      # Padronização de abertura de issues e tarefas
    │   ├── merge-request-templates.md              # Templates padronizados para revisões de código
    │   ├── milestones-boards.md                    # Acompanhamento de entregas através de marcos e boards
    │   ├── workflow-labels.md                      # Taxonomia e uso estratégico de etiquetas (labels)
    │   └── readme.md                               # Guia e índice específico do módulo 06
    ├── 07-seguranca-devsecops/                     # Segurança integrada ao ciclo de desenvolvimento de software
    │   ├── compliance-pipelines.md                 # Conformidade automatizada e pipelines obrigatórios
    │   ├── dependency-container-scanning.md        # Varredura de vulnerabilidades em dependências e containers
    │   ├── sast-secret-detection.md                # Análise estática de código (SAST) e detecção de segredos
    │   └── readme.md                               # Guia e índice específico do módulo 07
    ├── 08-recursos-avancados-api/                  # Integrações avançadas e automações via programação
    │   ├── api-rest-automations.md                 # Automações avançadas utilizando a API REST do GitLab
    │   ├── gitlab-pages.md                         # Hospedagem nativa de sites estáticos dentro da plataforma
    │   ├── webhooks-integration.md                 # Integração de eventos em tempo real com webhooks externos
    │   └── readme.md                               # Guia e índice específico do módulo 08
    ├── 09-cheatsheet-comandos/                     # Guias de referência rápida para o dia a dia técnico
    │   ├── advanced-git-commands.md                # Operações avançadas (rebase, cherry-pick, reflog)
    │   ├── git-essentials-cli.md                   # Comandos essenciais do Git utilizados no cotidiano
    │   ├── glab-cli-cheatsheet.md                  # Referência rápida de comandos do terminal `glab`
    │   └── readme.md                               # Guia e índice específico do módulo 09
    ├── 10-registry-pacotes/                        # Armazenamento e versionamento de artefatos de software
    │   ├── advanced-artifact-retention.md          # Políticas de retenção e limpeza de artefatos de build
    │   ├── container-registry.md                   # Armazenamento seguro de imagens de containers Docker
    │   ├── package-registries-npm-maven.md         # Hospedagem de pacotes e dependências (NPM, Maven, etc.)
    │   └── readme.md                               # Guia e índice específico do módulo 10
    └── 11-portal-interface-web/                    # Customização e navegação otimizada na interface gráfica
        ├── navigation-dashboards.md                # Painéis de controle e navegação otimizada na plataforma
        ├── project-settings-governance.md          # Configurações avançadas de governança e segurança de projetos
        ├── web-ide-editing.md                      # Edição ágil de código direto pelo navegador via Web IDE
        └── readme.md                               # Guia e índice específico do módulo 11
```

## 🚀 Detalhamento dos Módulos Oficiais
  1. O Motor de Versionamento Local: (**```git/```**)

     O diretório raiz do versionamento descentralizado. Focado nos comandos essenciais de terminal que todo desenvolvedor executa localmente:
      *   **Comandos Fundamentais**: Ciclo de vida do código (init, clone, add, commit, push, pull, stash, rebase).
      *   **```git-graph/```**: Ferramentas e comandos de terminal customizados para renderizar árvores de histórico limpas (git log --graph).
      *   **```git-hooks/```**: Scripts executados automaticamente em pontos específicos do fluxo (pre-commit, pre-push) para validação de qualidade de código.
      *   **```git-lfs/```**: Gerenciamento e versionamento eficiente de arquivos pesados que excedem os limites convencionais do Git.
      
  2. A Plataforma e Seus Recursos Nativos: (**```github/```**)

     Focado no ecossistema de nuvem e ferramentas oficiais fornecidas pelo GitHub:
      
      * **```github-actions/```**: Automação nativa de pipelines de CI/CD para testes, builds e deploys automáticos baseados em arquivos YAML.
      * **```github-flow/```**: O padrão oficial de ramificação (branches), abertura de Pull Requests e revisão de código em equipe.
      * **```github-pages/```**: Publicação e configuração de páginas web estáticas diretamente integradas ao repositório.
      * **```github-security/```**: Boas práticas de proteção de dados, configuração de chaves SSH para autenticação segura e tokens de acesso pessoal (PAT).
      
  3. O Ecossistema de Plataforma Unificada: (**```gitlab/```**)

     Focado nas ferramentas, conceitos e comandos específicos do ecossistema GitLab, abordando desde a interação via CLI (```glab```) até a gestão de merge requests e pipelines nativos da plataforma.

## 💡 Como Contribuir para o Núcleo

Como o **```nucleus/```** foca estritamente na base oficial das ferramentas, todas as contribuições devem manter o rigor técnico, priorizando comandos de terminal limpos, exemplos práticos e compatibilidade com os principais sistemas operacionais (**GNU/Linux**, **Windows** e **macOS**).
        
