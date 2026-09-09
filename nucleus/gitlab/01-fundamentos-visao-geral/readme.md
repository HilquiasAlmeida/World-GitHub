# 🌐 01. Fundamentos e Visão Geral do GitLab: Da Arquitetura ao Ecossistema DevSecOps

Este diretório aprofunda a base conceitual e estrutural do GitLab, indo desde os fundamentos de plataforma até a sua arquitetura interna de microsserviços e a filosofia de "Single Application".

---

## 1. O Conceito de "Single Application" vs. Toolchain Fragmentada
No ecossistema tradicional de desenvolvimento (*Toolchain Chaos*), as empresas costumam fragmentar as ferramentas:
* **Gerenciamento de Projetos**: Jira ou Trello.
* **Repositório Git**: GitHub ou Bitbucket.
* **CI/CD**: Jenkins ou CircleCI.
* **Segurança (SAST/DAST)**: SonarQube ou Snyk.
* **Registry**: Artifactory ou Nexus.

O **GitLab** elimina o atrito de integrações via plugins e APIs de terceiros ao unificar tudo sob a mesma base de código e banco de dados. 
* **Vantagens de escala**: Contexto de segurança unificado, rastreabilidade ponta a ponta (de uma Issue até o deploy em produção) e redução drástica de custos de manutenção de infraestrutura de integrações.

---

## 2. Arquitetura Interna do GitLab (Por Trás do Painel)
Para entender o GitLab em nível de engenharia de infraestrutura (especialmente em ambientes *Self-Hosted*), ele não é apenas uma aplicação monolítica simples, mas um ecossistema composto por componentes desacoplados:

* **GitLab Rails (Puma)**: A aplicação principal que gerencia a interface web, API REST/GraphQL e a lógica de negócios central.
* **GitLab Workhorse**: Um proxy reverso escrito em Go que fica na frente do Puma para descarregar conexões lentas, downloads grandes de Git e uploads de arquivos.
* **Gitaly**: O serviço de microsserviço em Go responsável por gerenciar chamadas de armazenamento Git de alta performance no disco. É o coração que lida com todos os repositórios.
* **Sidekiq**: O motor de filas em background (baseado em Ruby/Redis) que processa tarefas assíncronas como disparar pipelines, enviar e-mails e rodar webhooks.
* **PostgreSQL & Redis**: O banco de dados relacional principal e a camada de cache/gerenciamento de filas de sessão.
* **GitLab Shell**: Gerencia conexões SSH para operações de git clone/push/pull.

---

## 3. Topologias de Implantação: SaaS vs. Self-Hosted
O GitLab atende a dois modelos principais de operação:

* **GitLab.com (SaaS)**: Gerenciado pela própria GitLab Inc. Ideal para times que buscam zero manutenção de infraestrutura, com escalabilidade elástica gerenciada em nuvem.
* **GitLab Self-Hosted (Instalação Própria)**:
  * **Omnibus Package**: Instalação em máquina virtual Linux única (tudo empacotado de forma otimizada para empresas que querem gerenciar seu próprio servidor on-premise ou na nuvem).
  * **Cloud-Native GitLab (Helm Charts)**: Implantação distribuída em clusters **Kubernetes (K8s)**, permitindo alta disponibilidade real (HA), failover automático e escalabilidade horizontal massiva para milhares de desenvolvedores.

---

## 4. O Ciclo DevSecOps Nativo
Diferente do DevOps tradicional (onde a segurança entra apenas no final), o GitLab injeta segurança desde o primeiro commit:
1. **Planejamento**: A issue nasce no Kanban.
2. **Desenvolvimento**: O código é escrito e enviado (Push/MR).
3. **Build & Test**: O pipeline executa testes automatizados.
4. **Secure (DevSecOps)**: Varreduras automáticas de SAST (código estático), DAST (aplicação em execução), DDI (Dependency Scanning) e Secret Detection rodam em paralelo. Se houver falha crítica, o Merge Request é bloqueado nativamente.
5. **Deploy & Monitor**: Publicação controlada e monitoramento de erros em produção.

---

## 📂 Documentação Detalhada Deste Módulo
Para aprofundar em tópicos específicos sem sair do fluxo de leitura, acesse os documentos complementares desta pasta:

* 📊 **Matriz de Mercado**: Leia o comparativo completo em [`comparativo-ferramentas.md`](./comparativo-ferramentas.md) sobre o ganho de eficiência ao eliminar o *Toolchain Chaos*.
* ⚙️ **Raio-X de Infraestrutura**: Consulte os detalhes técnicos de cada microsserviço em [`arquitetura-componentes.md`](./arquitetura-componentes.md) (Puma, Workhorse, Gitaly, Sidekiq e PostgreSQL).
* 🏷️ **Governança Corporativa**: Analise as diferenças de compliance e segurança em [`licenciamento-versoes.md`](./licenciamento-versoes.md) entre as Tiers Free, Premium e Ultimate.
