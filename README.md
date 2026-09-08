# 🌍 World-GitHub
Bem-vindo ao **World GitHub**, o seu guia definitivo e centralizado sobre todo o ecossistema do github, de controle de versão, ferramentas Git, plataformas de hospedagem e fluxos de trabalho, ferramentas visuais, automações e muito mais...

Este repositório foi criado para documentar, ensinar e servir como consulta rápida para desenvolvedores de todos os níveis. E também foi estruturado sob uma ótica de **arquitetura de sistemas rigorosa e hierárquica**, separando de forma estrita o motor nativo e oficial (`nucleus/`) do ecossistema de mercado, ferramentas de terceiros e infraestrutura de rede (`layers/`).

---

## 🏛️ Visão Geral da Arquitetura

A organização divide-se em duas grandes vertentes:
1. **`nucleus/`**: O coração do ecossistema Git e das plataformas oficiais (Git, GitHub, GitLab), focado no núcleo de comandos, fluxos e ferramentas nativas.
2. **`layers/`**: A camada externa de mercado, abrangendo plataformas alternativas, servidores auto-hospedados, clientes gráficos, ferramentas de CI/CD e a engenharia de protocolos de rede.

---

## 📁 Estrutura do Repositório
A organização das pastas e seus respectivos conteúdos segue o formato abaixo:
```text
world-github/
├── README.md                                       # Documentação principal do repositório
├── layers/                                         # Camada de mercado, terceiros e infraestrutura externa
│   ├── README.md                                   # Guia da camada de ferramentas externas
│   └── thirdparty-market-infra/                    # Ecossistema de terceiros, mercado e infraestrutura
│       ├── README.md                               # Documentação geral do ecossistema de mercado
│       ├── gui-clients/                            # Clientes Gráficos e GUIs independentes
│       │   ├── README.md                           # Guia de GUIs independentes
│       │   ├── fork/                               # Fork (rápido, limpo e moderno para macOS/Windows)
│       │   ├── git-cola/                           # Git Cola (minimalista em Python)
│       │   ├── gitkraken/                          # GitKraken (corporativo avançado e multiplataforma)
│       │   ├── sourcetree/                         # Sourcetree (gratuito da Atlassian)
│       │   └── tortoisegit/                        # TortoiseGit (integrado ao Explorador do Windows)
│       ├── hosting-platforms/                      # Plataformas de Hospedagem de Código
│       │   ├── README.md                           # Guia de plataformas de hospedagem
│       │   ├── corporate/                          # Soluções focadas no mundo corporativo
│       │   │   └── bitbucket/                      # Bitbucket (Atlassian + Jira/Confluence)
│       │   └── open-source-privacy/                # Plataformas de código aberto e privacidade
│       │       ├── codeberg/                       # Codeberg (sem fins lucrativos e sem rastreadores)
│       │       ├── forgejo/                        # Forgejo (fork independente focado em governança aberta)
│       │       ├── gitea/                          # Gitea (leve, rápido e open source como plataforma)
│       │       └── sourcehut/                      # Sourcehut (alternativa minimalista via e-mail e web)
│       ├── independent-ci-cd-tools-automation/     # Ferramentas de CI/CD e Automação Independentes
│       │   ├── README.md                           # Guia de CI/CD e automação
│       │   ├── enterprise/                         # Soluções para grandes corporações
│       │   │   ├── README.md                       # Guia de ferramentas corporativas
│       │   │   └── jenkins/                        # Jenkins (servidor de automação tradicional)
│       │   └── external-git-platforms/             # Plataformas baseadas em nuvem conectadas ao Git
│       │       ├── README.md                       # Guia de plataformas externas de CI/CD
│       │       ├── circleci/                       # CircleCI (baseada em nuvem focada em velocidade)
│       │       ├── drone-io/                       # Drone.io (nativo de contêineres e escalável)
│       │       └── travis-ci/                      # Travis CI (pioneiro de integração contínua)
│       ├── network-low-level-protocols-engit/      # Protocolos de Rede, Baixo Nível e Engenharia do Git
│       │   ├── README.md                           # Guia de protocolos e engenharia
│       │   ├── cryptography-auth/                  # Sistemas criptográficos e autenticação
│       │   │   ├── gpg-keys/                       # GPG Keys (assinaturas digitais de commits)
│       │   │   └── ssh/                            # SSH Secure Shell (autenticação por chaves)
│       │   └── network-protocols/                  # Protocolos de comunicação de rede
│       │       ├── git-protocol/                   # Git Protocol (baixo nível, não criptografado)
│       │       └── smart-http/                     # Smart HTTP Protocol (padrão moderno via HTTP/HTTPS)
│       └── self-hosted-servers/                    # Servidores Git Self-Hosted (Hospedar seu próprio "GitHub")
│           ├── README.md                           # Guia de servidores auto-hospedados
│           ├── gitea/                              # Gitea (servidor privado e rápido auto-hospedado)
│           ├── gitlab-self-hosted/                 # GitLab Self-Hosted (infraestrutura corporativa própria)
│           └── gogs/                               # Gogs (serviço leve escrito em Go)
└── nucleus/                                        # O núcleo e ferramentas oficiais do ecossistema Git
    ├── README.md                                   # Documentação geral do núcleo
    ├── git/                                        # Comandos essenciais, histórico e guias do Git
    │   ├── README.md                               # Guia e índice do diretório Git
    │   ├── git-graph/                              # Ferramentas visuais e interfaces gráficas (Git GUI)
    │   ├── git-hooks/                              # Automações e scripts executados no fluxo do Git
    │   └── git-lfs/                                # Gerenciamento de arquivos grandes e binários
    ├── github/                                     # Guia do GitHub, perfis e recursos
    │   ├── README.md                               # Guia e índice do diretório GitHub
    │   ├── github-actions/                         # Automação de CI/CD e robôs de teste
    │   ├── github-flow/                            # Metodologias e fluxos de trabalho em equipe
    │   ├── github-pages/                           # Como hospedar sites estáticos gratuitamente
    │   └── github-security/                        # Chaves SSH, tokens (PAT) e boas práticas de segurança
    └── gitlab/                                     # Comandos, diferenças e uso do GitLab
        └── README.md                               # Guia e índice do diretório GitLab
```

## 🚀 O que você vai encontrar em cada pasta?

1. O Núcleo Oficial:(```nucleus```/)
   * **Git** (nucleus/git/):
       * Aprenda os comandos fundamentais (```clone```, ```commit```, ```push```, ```pull```, ```stash```, ```rebase```) e entre outros comandos; histórico da ferramenta e as boas práticas.
       * **Git Graph**: Conheça extensões e interfaces gráficas (como o Git Graph do VS Code e Lazygit) para visualizar seu histórico de forma visual.
       * **Git Hooks**: Como configurar gatilhos automáticos para validar seu código antes de enviar para o repositório.
       * **Git LFS**: Essencial para gerenciar arquivos grandes (como vídeos, imagens pesadas, modelos 3D ou binários) que o Git normal não aguenta bem (Git Large File Storage).

    * **GitHub** (nucleus/github/):
         * Dicas de como criar um Profile README atrativo, gerenciar issues, pull requests e introdução a pipelines (GitHub Actions).
         * **GitHub Actions**: O sistema poderoso do GitHub para criar robôs que rodam testes automáticos, fazem deploy de códigos e automatizam tarefas (Automação e CI/CD).
         * **GitHub Flow**: Entenda como funcionam as ramificações (```branches```), Pull Requests e organização de equipes.
         * **GitHub Gists**: Como criar, versionar e compartilhar trechos de código rápido, scripts isolados e notas de forma pública ou secreta.
         * **GitHub Pages**: Passo a passo detalhado de como transformar seu repositório em um site publicado na web.
         * **GitHub Projects**: O uso de quadros Kanban, gerenciamento avançado de issues e acompanhamento visual de tarefas direto no ecossistema do GitHub. (Gestão de Projetos).
         * **GitHub Security**: Como configurar chaves SSH, tokens de acesso pessoal (PAT), autenticação de dois fatores (2FA) e avisos de vulnerabilidade (Segurança).

    * **GitLab**: Recursos específicos da plataforma, comandos e introdução ao GitLab CI/CD.

## 🧰 The third-party tools, market products, and external infrastructure 

  2. As Camadas:(```layers/```)
      Outras Plataformas de Hospedagem de Código (Concorrentes ou Alternativas)
      Além do GitHub e do GitLab, existem outras plataformas gigantescas de hospedagem baseadas em Git
      Plataformas de código aberto voltadas para comunidades de software livre e privacidade:
     
     * ```thirdparty-market-infra/```: Concentra todas as soluções externas e de mercado divididas em subpastas especializadas:
       * **Hosting Platforms** (hosting-platforms/):
         * Corporate:
           * **Bitbucket (da Atlassian)**: Plataforma de hospedagem baseada em Git muito utilizada no mundo corporativo devido à sua integração nativa com o Jira e Confluence.
         * Open Source & Privacy:
           * **Codeberg** Plataforma comunitária e sem fins lucrativos focada em privacidade e sem rastreadores.
           * **Gitea** Software de serviço Git leve, rápido e de código aberto.
           * **Forgejo** Fork comunitário e independente do Gitea, focado em governança aberta.
           * **Sourcehut** Uma alternativa minimalista e focada em desempenho para gerenciar repositórios Git via e-mail e web.
             
       * **Self-Hosted Servers** (self-hosted-servers/):
           * **GitLab Self-Hosted**: Versão completa para rodar toda a infraestrutura do GitLab nos computadores da própria empresa.
           * **Gitea**: Permite criar um servidor Git privado e completo rapidamente.
           * **Gogs**: Serviço Git auto-hospedado extremamente leve escrito em Go.
      * **GUI Clients** (```gui-clients/```):
           * **Fork**: Cliente Git rápido, limpo e moderno para macOS e Windows.
           * **Git Cola**: Cliente gráfico para Git minimalista e rápido escrito em Python.
           * **GitKraken**: Cliente gráfico corporativo avançado e multiplataforma.
           * **Sourcetree**: Cliente Git gráfico gratuito desenvolvido pela Atlassian.
           * **TortoiseGit**: Ferramenta para Windows integrada diretamente ao Explorador de Arquivos.
      * **Independent CI/CD Tools & Automation** (```independent-ci-cd-tools-automation/```):
          * **Enterprise**:
              * **Jenkins**: O servidor de automação mais antigo e usado em grandes corporações.
           
          * **External Git Platforms**:
              * **CircleCI**: Plataforma de CI/CD baseada em nuvem focada em velocidade.
              * **Travis CI**: Uma das ferramentas pioneiras de integração contínua para o GitHub.
              * **Drone.io**: Sistema de CI/CD nativo de contêineres e altamente escalável.

      * **Network, Low-Level Protocols & Engineering** (network-low-level-protocols-engit/):
          * **Network Protocols**:
              * **Smart HTTP Protocol**: Protocolo padrão moderno que usa portas HTTP/HTTPS normais para transferir dados de forma inteligente.
              * **Git Protocol (`git://`)**: Protocolo de rede de baixo nível, não criptografado e extremamente rápido (hoje em dia pouco usado).
   
      * **Cryptography & Auth**:
          * **SSH (Secure Shell)**: Protocolo de rede criptografado para autenticação por chaves.
          * **GPG Keys**: Assinaturas criptográficas digitais usadas para assinar commits e provar a autoria do código.

## 💡 Como Contribuir
Sugestões, correções e novas adições são sempre muito bem-vindas!

 1. Faça um Fork deste projeto.
 2. Crie uma branch para a sua melhoria (```git checkout -b feature/new-documentation```).
 3. Faça o Commit das suas alterações (```git commit -m 'Adds documentation about X'```).
 4. Envie para a Branch (```git push origin feature/new-documentation```).
 5. Abra um Pull Request.



## 📜 Licença
Este projeto está sob a licença MIT. Sinta-se livre para usar, estudar e compartilhar o conhecimento!
