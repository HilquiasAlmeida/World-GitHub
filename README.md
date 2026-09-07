# 🌍 World-GitHub
Bem-vindo ao **World GitHub**, o seu guia definitivo e centralizado sobre todo o ecossistema do github, de controle de versão, ferramentas Git, plataformas de hospedagem e fluxos de trabalho, ferramentas visuais, automações e muito mais...

Este repositório foi criado para documentar, ensinar e servir como consulta rápida para desenvolvedores de todos os níveis.

## 📁 Estrutura do Repositório
A organização das pastas e seus respectivos conteúdos segue o formato abaixo:

```Plaintext
world-github/
├── README.md               # Documentação principal (este arquivo)
├── /git                    # Comandos essenciais, histórico e guias do Git
├── /github                 # Guia do GitHub, perfis e recursos
├── /gitlab                 # Comandos, diferenças e uso do GitLab
├── /github-pages           # Como hospedar sites estáticos gratuitamente
├── /git-hooks              # Automações e scripts executados no fluxo do Git
├── /github-flow            # Metodologias e fluxos de trabalho em equipe
├── /git-graph/              # Ferramentas visuais e interfaces gráficas (Git GUI)
├── /github-actions/         # Automação de CI/CD e robôs de teste
├── /git-lfs/                # Gerenciamento de arquivos grandes e binários
└── /github-security/        # Chaves SSH, tokens (PAT) e boas práticas de segurança
```

## 🚀 O que você vai encontrar em cada pasta?

   * **Git**: Aprenda os comandos fundamentais (```clone```, ```commit```, ```push```, ```pull```, ```stash```, ```rebase```), histórico da ferramenta e boas práticas.
   * **GitHub**: Dicas de como criar um Profile README atrativo, gerenciar issues, pull requests e introdução a pipelines (GitHub Actions).
   * **GitLab**: Recursos específicos da plataforma, comandos e introdução ao GitLab CI/CD.
   * **GitHub** Pages: Passo a passo detalhado de como transformar seu repositório em um site publicado na web.
   * **Git Hooks**: Como configurar gatilhos automáticos para validar seu código antes de enviar para o repositório.
   * **GitHub Flow**: Entenda como funcionam as ramificações (```branches```), Pull Requests e organização de equipes.
   * **Git Graph**: Conheça extensões e interfaces gráficas (como o Git Graph do VS Code e Lazygit) para visualizar seu histórico de forma visual.
   * **Git LFS**: Essencial para gerenciar arquivos grandes (como vídeos, imagens pesadas, modelos 3D ou binários) que o Git normal não aguenta bem (Git Large File Storage).
   * **GitHub Actions**: O sistema poderoso do GitHub para criar robôs que rodam testes automáticos, fazem deploy de códigos e automatizam tarefas (Automação e CI/CD).
   * **GitHub Security**: Como configurar chaves SSH, tokens de acesso pessoal (PAT), autenticação de dois fatores (2FA) e avisos de vulnerabilidade (Segurança).
   * **GitHub Projects**: O uso de quadros Kanban, issues avançadas e gerenciamento de tarefas direto no GitHub (Gestão de Projetos).
   * **Gists**: Como criar trechos de código rápidos e compartilháveis usando o recurso de Gist do GitHub.

## 🧰 Ferramentas de terceiros, produtos de mercado e infraestrutura externa

1. Outras Plataformas de Hospedagem de Código (Concorrentes ou Alternativas)
   Além do GitHub e do GitLab, existem outras plataformas gigantescas de hospedagem baseadas em Git:

   * **Bitbucket (da Atlassian)**: Plataforma de hospedagem baseada em Git muito utilizada no mundo corporativo devido à sua integração nativa com o Jira e Confluence.
   
   Plataformas de código aberto voltadas para comunidades de software livre e privacidade:
   * **Codeberg**: Plataforma comunitária e sem fins lucrativos focada em privacidade e sem rastreadores.
   * **Gitea**: Software de serviço Git leve, rápido e de código aberto.
   * **Forgejo**: Fork comunitário e independente do Gitea, focado em governança aberta.
   
   * **Sourcehut**: Uma alternativa minimalista e focada em desempenho para gerenciar repositórios Git via e-mail e web.

2. Servidores Git Self-Hosted (**Para hospedar seu próprio "GitHub"**)
   Muitas empresas não usam o GitHub na nuvem por questões de segurança e criam o seu próprio "GitHub" dentro dos servidores da própria empresa usando:

   Softwares leves que permitem criar um servidor Git próprio em minutos, até mesmo em um computador antigo ou Raspberry Pi:
   * **GitLab Self-Hosted**: Versão completa para rodar toda a infraestrutura do GitLab nos computadores da própria empresa.
   * **Gitea**: Permite criar um servidor Git privado e completo rapidamente.
   * **Gogs**: Serviço Git auto-hospedado extremamente leve escrito em Go.

3. Clientes Gráficos (**GUIs**) independentes
   O Git roda no terminal, mas o "mundo do Git" criou dezenas de softwares visuais avançados para quem não gosta de tela preta:
   
   Programas instalados no computador que gerenciam o histórico visualmente, criam branches com cliques e resolvem conflitos de código com interfaces gráficas complexas:
   * **GitKraken**: Cliente gráfico corporativo avançado e multiplataforma.
   * **Sourcetree**: Cliente Git gráfico gratuito desenvolvido pela Atlassian.
   * **Fork**: Cliente Git rápido, limpo e moderno para macOS e Windows.
   * **TortoiseGit**: Ferramenta para Windows integrada diretamente ao Explorador de Arquivos.
   * **Git Cola**: Cliente gráfico para Git minimalista e rápido escrito em Python.

4. Ferramentas de CI/CD e Automação Independentes (Além do GitHub Actions)
   O ecossistema de controle de versão é fortemente ligado a automações que rodam quando você envia um código.
   Antes do GitHub Actions se popularizar, o mundo usava ferramentas dedicadas apenas a isso:

   * **Jenkins**: O servidor de automação mais antigo e usado em grandes corporações.
      
   Plataformas externas que se conectam ao Git para rodar testes automáticos e entregas contínuas:
   * **CircleCI**: Plataforma de CI/CD baseada em nuvem focada em velocidade.
   * **Travis CI**: Uma das ferramentas pioneiras de integração contínua para o GitHub.
   * **Drone.io**: Sistema de CI/CD nativo de contêineres e altamente escalável.

6. Protocolos de Rede e Baixo Nível (**A Engenharia do Git**)
   
   Por trás dos comandos, o Git funciona usando protocolos de comunicação na internet e na rede local:

   * **Smart HTTP Protocol**: Protocolo padrão moderno que usa portas HTTP/HTTPS normais para transferir dados de forma inteligente.
   * **Git Protocol (`git://`)**: Protocolo de rede de baixo nível, não criptografado e extremamente rápido (hoje em dia pouco usado).
   
   Os sistemas criptográficos de chaves de segurança que autenticam quem você é para o GitHub ou GitLab sem precisar digitar senha:
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
