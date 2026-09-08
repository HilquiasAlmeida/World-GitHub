# 🌐 Layers: A Camada de Mercado, Terceiros e Infraestrutura Externa

Bem-vindo ao diretório **`layers/`** do projeto **World-GitHub**.

Enquanto o `nucleus/` abriga o motor oficial e nativo, este diretório é dedicado ao **ecossistema externo de mercado, ferramentas de terceiros e infraestrutura de rede**. Ele concentra as soluções alternativas de hospedagem, servidores auto-hospedados, clientes gráficos independentes, ferramentas de automação e os protocolos de baixo nível que sustentam o universo do controle de versão.

---

## 🌳 Estrutura da Camada de Terceiros

```text
layers/
├── README.md                                       # Guia da camada de ferramentas externas (este arquivo)
└── thirdparty-market-infra/                        # Ecossistema de terceiros, mercado e infraestrutura
    ├── README.md                                   # Documentação geral do ecossistema de mercado
    ├── gui-clients/                                # Clientes Gráficos e GUIs independentes
    │   ├── README.md                               # Guia de GUIs independentes
    │   ├── fork/                                   # Fork (rápido, limpo e moderno para macOS/Windows)
    │   ├── git-cola/                               # Git Cola (minimalista em Python)
    │   ├── gitkraken/                              # GitKraken (corporativo avançado e multiplataforma)
    │   ├── sourcetree/                             # Sourcetree (gratuito da Atlassian)
    │   └── tortoisegit/                            # TortoiseGit (integrado ao Explorador do Windows)
    ├── hosting-platforms/                          # Plataformas de Hospedagem de Código
    │   ├── README.md                               # Guia de plataformas de hospedagem
    │   ├── corporate/                              # Soluções focadas no mundo corporativo
    │   │   └── bitbucket/                          # Bitbucket (Atlassian + Jira/Confluence)
    │   └── open-source-privacy/                    # Plataformas de código aberto e privacidade
    │       ├── codeberg/                           # Codeberg (sem fins lucrativos e sem rastreadores)
    │       ├── forgejo/                            # Forgejo (fork independente focado em governança aberta)
    │       ├── gitea/                              # Gitea (leve, rápido e open source como plataforma)
    │       └── sourcehut/                          # Sourcehut (alternativa minimalista via e-mail e web)
    ├── independent-ci-cd-tools-automation/         # Ferramentas de CI/CD e Automação Independentes
    │   ├── README.md                               # Guia de CI/CD e automação
    │   ├── enterprise/                             # Soluções para grandes corporações
    │   │   ├── README.md                           # Guia de ferramentas corporativas
    │   │   └── jenkins/                            # Jenkins (servidor de automação tradicional)
    │   └── external-git-platforms/                 # Plataformas baseadas em nuvem conectadas ao Git
    │       ├── README.md                           # Guia de plataformas externas de CI/CD
    │       ├── circleci/                           # CircleCI (baseada em nuvem focada em velocidade)
    │       ├── drone-io/                           # Drone.io (nativo de contêineres e escalável)
    │       └── travis-ci/                          # Travis CI (pioneiro de integração contínua)
    ├── network-low-level-protocols-engit/          # Protocolos de Rede, Baixo Nível e Engenharia do Git
    │   ├── README.md                               # Guia de protocolos e engenharia
    │   ├── cryptography-auth/                      # Sistemas criptográficos e autenticação
    │   │   ├── gpg-keys/                           # GPG Keys (assinaturas digitais de commits)
    │   │   └── ssh/                                # SSH Secure Shell (autenticação por chaves)
    │   └── network-protocols/                      # Protocolos de comunicação de rede
    │       ├── git-protocol/                       # Git Protocol (baixo nível, não criptografado)
    │       └── smart-http/                         # Smart HTTP Protocol (padrão moderno via HTTP/HTTPS)
    └── self-hosted-servers/                        # Servidores Git Self-Hosted (Hospedar seu próprio "GitHub")
        ├── README.md                               # Guia de servidores auto-hospedados
        ├── gitea/                                  # Gitea (servidor privado e rápido auto-hospedado)
        ├── gitlab-self-hosted/                     # GitLab Self-Hosted (infraestrutura corporativa própria)
        └── gogs/                                   # Gogs (serviço leve escrito em Go)
```

## 🛠️ Detalhamento dos Módulos de Mercado
  1. Plataformas de Hospedagem: (**```hosting-platforms/```**)

     Alternativas e complementos às plataformas principais de nuvem:
      * ```corporate/```: Focado no ecossistema empresarial tradicional, destacando o Bitbucket e sua sinergia com o Jira e Confluence.
      * ```open-source-privacy/```: Soluções orientadas à privacidade e software livre, como Codeberg, Forgejo, Gitea e Sourcehut.

  2. Servidores Auto-Hospedados: (**```self-hosted-servers/```**)

     Ferramentas destinadas a hospedar instâncias próprias de servidores Git por questões de segurança, autonomia ou compliance (desde soluções corporativas robustas como o GitLab Self-Hosted até alternativas leves que rodam em servidores locais ou Raspberry Pi, como Gitea e Gogs).

  3. Clientes Gráficos Independentes: (**```gui-clients/```**)

     Interfaces visuais independentes para o gerenciamento de repositórios sem depender exclusivamente da tela preta do terminal (Fork, Git Cola, GitKraken, Sourcetree e TortoiseGit).

  4. Automação e CI/CD: (**```independent-ci-cd-tools-automation/```**)

     Ecossistemas desacoplados de integração contínua divididos em soluções corporativas (Jenkins) e plataformas nativas de nuvem (CircleCI, Drone.io e Travis CI).

  6. Engenharia de Rede e Protocolos: (**```network-low-level-protocols-engit/```**)

     A fundação invisível que viabiliza o transporte e a segurança dos dados:

      * ```network-protocols/```: Protocolos de comunicação de rede como o Smart HTTP e o clássico Git Protocol.
      * ```cryptography-auth/```: Mecanismos de identificação e assinatura digital via chaves SSH e GPG Keys.

## 💡 Como Contribuir para as Camadas
  
  As documentações presentes neste diretório devem manter o foco em guiar desenvolvedores sobre como interagir, configurar e operar essas ferramentas de mercado integradas aos sistemas operacionais (GNU/Linux, Windows e macOS) e ambientes de desenvolvimento.
  
