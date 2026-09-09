# 🦊 GitLab Nucleus: A Central Definitiva do Ecossistema GitLab

Bem-vindo ao diretório oficial do **GitLab** dentro do núcleo (**`nucleus/gitlab/`**) do projeto **World-GitHub**. 

Este documento serve como uma central de referência técnica completa para dominar o ecossistema GitLab. Seja você um desenvolvedor escrevendo código localmente, um engenheiro configurando pipelines de CI/CD ou um líder técnico estruturando governança DevSecOps, tudo o que você precisa saber sobre o GitLab está centralizado aqui.

  ```
    nucleus/gitlab/
      ├── README.md                      <-- O Portal Mestre (Espelho Interativo)
      ├── 01-fundamentos-visao-geral/    <-- Conceitos de Single Application e o ecossistema DevSecOps
      ├── 02-fluxo-gitlab-flow/          <-- Guia visual e regras de branches (main, features e MRs)
      ├── 03-cli-glab-terminal/          <-- Guia de instalação e automações via terminal com a CLI oficial
      ├── 04-integracao-git-local/       <-- Blueprint de sincronização entre máquina local e repositórios remotos
      ├── 05-pipelines-ci-cd/            <-- Modelos prontos de `.gitlab-ci.yml` e guias de Runners
      ├── 06-gestao-projetos-issues/     <-- Estratégias de Kanban, Milestones e templates de Issues
      ├── 07-seguranca-devsecops/        <-- Configurações de SAST, Secret Detection e varredura de dependências
      ├── 08-recursos-avancados-api/     <-- Scripts de GitLab Pages, automações via API REST e Webhooks
      ├── 09-cheatsheet-comandos/        <-- Tabelas de referência rápida para consultas diárias
      ├── 10-registry-pacotes/           <-- O guia técnico para desenvolvedores lidarem com Docker, npm, Maven e PyPI via terminal, IDEs e arquivos de configuração
      └── 11-portal-interface-web/       <-- O manual completo para quem prefere navegar, configurar e operar tudo direto pelo site do GitLab sem mexer no terminal
  ```

---
## 📑 Sumário de Conteúdos
1. [Visão Geral: O que é o GitLab?](#1-visão-geral-o-que-é-o-gitlab)
2. [Arquitetura e Fluxo de Trabalho (GitLab Flow)](#2-arquitetura-e-fluxo-de-workflow-gitlab-flow)
3. [GitLab CLI (`glab`): O Poder no Terminal](#3-gitlab-cli-glab-o-poder-no-terminal)
4. [Integração Local: Git com GitLab](#4-integração-local-git-com-gitlab)
5. [GitLab CI/CD: Automação e Pipelines](#5-gitlab-cicd-automação-e-pipelines)
6. [Gestão de Projetos e Colaboração (Merge Requests e Issues)](#6-gestão-de-projetos-e-colaboração-merge-requests-e-issues)
7. [DevSecOps e Segurança Integrada](#7-devsecops-e-segurança-integrada)
8. [Recursos Avançados: GitLab Pages, API e Webhooks](#8-recursos-avançados-gitlab-pages-api-e-webhooks)
9. [Cheatsheet: Comandos Essenciais do Dia a Dia](#9-cheatsheet-comandos-essenciais-do-dia-a-dia)

---

## 1. Visão Geral: O que é o GitLab?
O **GitLab** é uma plataforma de desenvolvimento colaborativo baseada em Git e concebida como uma **única aplicação (Single Application)** para todo o ciclo de vida de DevOps (**DevSecOps**). 

Enquanto outras plataformas exigem integrações de terceiros para testes, segurança e gerenciamento de projetos, o GitLab integra nativamente:
* Controle de versão Git de alta performance.
* Rastreamento de issues e planejamento ágil (Kanban, Milestones, Epics).
* Servidor de CI/CD nativo com runners escaláveis.
* Varredura automatizada de segurança de código (SAST, DAST, Secrets).
* Hospedagem de pacotes, containers (Registry) e sites estáticos (GitLab Pages).

---

## 2. Arquitetura e Fluxo de Trabalho (GitLab Flow)
O GitLab utiliza o **GitLab Flow**, uma metodologia que combina controle de ramificações (*branching*) com rastreabilidade contínua de releases.

* **Branch Principal (`main` ou `master`)**: O código está sempre pronto para produção. Nenhuma alteração direta é feita nela.
* **Feature Branches**: Cada nova funcionalidade ou correção nasce de uma branch dedicada (ex: `feature/login-oauth` ou `bugfix/fix-null-pointer`).
* **Merge Requests (MRs)**: O mecanismo oficial do GitLab para propor, revisar e debater alterações de código antes de uni-las à branch principal.
* **Ambientes e Staging**: O GitLab permite associar branches ou tags a ambientes específicos (Review Apps, Staging, Production) para validação contínua.

---

## 3. GitLab CLI (`glab`): O Poder no Terminal
A ferramenta oficial de linha de comando do GitLab é o **`glab`**. Ela permite interagir com o GitLab diretamente pelo terminal do seu sistema operacional (**Linux, macOS ou Windows**), eliminando a necessidade de alternar para o navegador.

### Instalação Rápida
* **GNU/Linux (Debian/Ubuntu)**: `sudo apt install glab`
* **macOS (Homebrew)**: `brew install glab`
* **Windows (Winget)**: `winget install GitLab.Glac` (ou via Chocolatey/Scoop)

### Autenticação Inicial
Para conectar sua máquina ao GitLab (SaaS ou instância privada):
```bash
glab auth login
```

## 4. Integração Local: Git com GitLab

  O ciclo básico de interação entre sua máquina local e o GitLab envolve comandos padronizados de Git:

  1. Clonar um repositório do GitLab: 
  ```bash
      git clone https://gitlab.com/seu-usuario/seu-projeto.git
  ```

  2. Configurar o Remote (caso o repositório tenha sido criado vazio localmente):
    
    ```bash
    git remote add origin https://gitlab.com/seu-usuario/seu-projeto.git
    git branch -M main
    git push -u origin main
    ```
    
  3. Enviar alterações:
    
    ```bash
    git add .
    git commit -m "feat: adiciona nova funcionalidade de pagamento"
    git push origin feature/pagamento
    ```
## 5. GitLab CI/CD: Automação e Pipelines
    
  O coração da automação no GitLab é o arquivo .gitlab-ci.yml, colocado na raiz do repositório. Ele define os estágios, empregos (jobs) e regras de execução.
  
  Anatomia Básica de um ```.gitlab-ci.yml```
```
stages:
  - test
  - build
  - deploy

variables:
  NODE_VERSION: "20"

run_tests:
  stage: test
  image: node:${NODE_VERSION}
  script:
    - npm install
    - npm test

build_application:
  stage: build
  image: node:${NODE_VERSION}
  script:
    - npm run build
  artifacts:
    paths:
      - dist/

deploy_production:
  stage: deploy
  script:
    - echo "Fazendo deploy para o servidor de produção..."
  rules:
    - if: '$CI_COMMIT_BRANCH == "main"'
```
**GitLab Runners**
  Os Runners são os agentes que executam os scripts definidos no pipeline. Eles podem ser executados em infraestruturas próprias (**Self-Hosted Runners** em **Linux**, **Docker** ou **Windows**) ou utilizando os recursos em nuvem fornecidos pelo **GitLab SaaS**.

## 6. Gestão de Projetos e Colaboração
   * **Merge Requests (MRs)**:
     * Para abrir um MR direto pelo terminal usando o **```glab```**:
       ```Bash
       glab mr create --title "Nova feature" --description "Descrição detalhada das mudanças" --assignee @me
       ```

     * Para aprovar ou fazer merge via CLI:
       ```Bash
        glab mr approve
        glab mr merge
       ```

  * **Issues**: Gestão de tarefas e bugs.
    * Listar issues abertas no terminal: glab issue list
    * Criar nova issue: glab issue create --title "Bug na tela de login"
## 7. DevSecOps e Segurança Integrada
  
  O GitLab oferece segurança nativa que roda diretamente nos pipelines de CI/CD sem plugins externos:
    * **SAST (Static Application Security Testing)**: Analisa o código-fonte em busca de vulnerabilidades de segurança conhecidas.
    * **Secret Detection**: Impede que chaves de API, senhas ou tokens sejam commitados acidentalmente no repositório.
    * **Dependency Scanning**: Verifica bibliotecas de terceiros (como **```package.json```**, **```requirements.txt```**) em busca de pacotes desatualizados ou vulneráveis.

## 8. Recursos Avançados: GitLab Pages, API e Webhooks
  
  * **GitLab Pages**: Permite hospedar sites estáticos (documentações, portfolios, landing pages) de graça. Basta configurar um job no pipeline que envie os arquivos compilados para a pasta **```public/```**.
  * **API REST** e **GraphQL**: O GitLab possui uma API robusta. Você pode disparar pipelines, criar issues ou extrair métricas usando comandos **```curl```**:
    ```
    curl --header "PRIVATE-TOKEN: <seu_token>" "https://gitlab.com/api/v4/projects"
    ```
  * **Webhooks**: Gatilhos HTTP para notificar sistemas externos (como **Discord**, **Slack** ou **servidores próprios**) sempre que ocorrer um evento (**```push```**, **```merge```** **```request```**, **```pipeline```** falhou).

## 9. Cheatsheet: Comandos Essenciais do Dia a Dia (glab & Git)

| Categoria | Ação / Recurso no GitLab | Comando no Terminal (`glab`) |
| :--- | :--- | :--- |
| **Autenticação** | Fazer login na instância do GitLab | `glab auth login` |
| **Autenticação** | Verificar credenciais ativas | `glab auth status` |
| **Repositórios** | Clonar repositório via CLI | `glab repo clone <usuario/projeto>` |
| **Repositórios** | Criar novo repositório remotamente | `glab repo create` |
| **Merge Requests** | Criar novo Merge Request | `glab mr create` |
| **Merge Requests** | Listar MRs abertos | `glab mr list` |
| **Merge Requests** | Visualizar detalhes de um MR | `glab mr view <id>` |
| **Merge Requests** | Aprovar um MR via terminal | `glab mr approve <id>` |
| **Merge Requests** | Executar o Merge de um MR | `glab mr merge <id>` |
| **CI/CD** | Verificar status dos pipelines | `glab ci status` |
| **CI/CD** | Acompanhar logs de execução | `glab ci trace` |
| **Issues** | Listar issues do projeto | `glab issue list` |
| **Issues** | Criar nova issue pelo terminal | `glab issue create` |
| **Issues** | Fechar uma issue específica | `glab issue close <id>` |

## 10. A Interface Web do GitLab (Navegador)
  
  Além do terminal e da sua IDE local, o GitLab oferece uma plataforma rica em recursos visuais e administrativos gerenciados diretamente pelo navegador:
  Utilize a tabela abaixo como um mapa interativo do site do GitLab. Cada categoria representa um módulo da plataforma web que possui documentação detalhada nas subpastas correspondentes do nosso projeto:

| Módulo / Categoria no Site | O que você encontra / Descrição Geral | Onde acessar no Site do GitLab | Link para a Subpasta do Projeto |
| :--- | :--- | :--- | :--- |
| **Planejamento Ágil (Plan)** | Gestão de tarefas, quadros Kanban (Issue Boards), Marcos (Milestones), Epics e documentação em Wiki. | `Plan > Issues`, `Boards`, `Milestones`, `Wiki` | [📁 Ir para Subpasta de Planejamento](./site/plan/README.md) |
| **Repositório & Código (Code)** | Visualização de arquivos, histórico de commits, comparações de branches e gráficos de contribuição. | `Code > Files`, `Commits`, `Branches`, `Graph` | [📁 Ir para Subpasta de Repositório](./site/code/README.md) |
| **Integração Contínua (Build)** | Painel de monitoramento de pipelines, visualizador de estágios, jobs, agendamentos e testes. | `Build > Pipelines`, `Jobs`, `Pipeline schedules` | [📁 Ir para Subpasta de CI/CD](./site/ci-cd/README.md) |
| **Segurança & Compliance (Secure)** | Relatórios de vulnerabilidades (SAST), varredura de dependências e análise de conformidade de código. | `Secure > Vulnerability report`, `Security dashboard` | [📁 Ir para Subpasta de Segurança](./site/security/README.md) |
| **Entrega & Pacotes (Deploy)** | Gerenciamento de Releases, hospedagem GitLab Pages, Container Registry e Package Registry (npm, Maven, etc.). | `Deploy > Releases`, `Pages`, `Package registry` | [📁 Ir para Subpasta de Deploy](./site/deploy/README.md) |
| **Operações & Monitoramento (Monitor)** | Rastreamento de erros, métricas de performance da aplicação, gestão de incidentes e Feature Flags. | `Monitor > Error tracking`, `Incidents`, `Metrics` | [📁 Ir para Subpasta de Operações](./site/monitor/README.md) |
| **Métricas & Análises (Analyze)** | Análises de fluxo de valor (Value Stream), métricas de produtividade e relatórios de velocidade do time. | `Analyze > Value stream analytics`, `CI/CD analytics` | [📁 Ir para Subpasta de Analytics](./site/analyze/README.md) |
| **Governança & Configurações (Settings)** | Controle de membros, permissões (Roles), chaves de API/Tokens, branches protegidas e Webhooks. | `Settings > General`, `Members`, `Repository`, `Webhooks` | [📁 Ir para Subpasta de Governança](./site/governance/README.md) |
