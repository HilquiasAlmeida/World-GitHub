# ⚙️ Raio-X de Arquitetura: Componentes Internos do GitLab

Para engenheiros de infraestrutura que operam instâncias corporativas (*Self-Hosted*), o GitLab não opera como um monólito comum, mas como um ecossistema desacoplado de microsserviços:

* **GitLab Rails (Puma)**: 
  * *Função*: Camada web principal e motor de APIs (REST/GraphQL). Processa a lógica de negócios, autenticação de usuários, renderização de views e gerenciamento geral de projetos.
* **GitLab Workhorse**: 
  * *Função*: Um proxy reverso inteligente escrito em Go que intercepta requisições HTTP antes de chegarem ao Puma. Descarrega tarefas pesadas como uploads grandes de arquivos e downloads de repositórios Git, blindando a aplicação contra gargalos de I/O.
* **Gitaly**: 
  * *Função*: Microsserviço em Go responsável por toda a comunicação de leitura e escrita em disco dos repositórios Git. Ele remove o acesso direto ao sistema de arquivos via NFS tradicional, garantindo alta performance e escalabilidade de armazenamento distribuído (*Gitaly Cluster*).
* **Sidekiq**: 
  * *Função*: O mecanismo de processamento assíncrono em background (construído sobre Ruby e Redis). Gerencia filas para disparo de pipelines, envio de notificações por e-mail, sincronização de branch protections e webhooks.
* **PostgreSQL & Redis**: 
  * *Função*: O banco de dados relacional central (PostgreSQL) para armazenamento de metadados, usuários e issues, aliado ao cache em memória de alta velocidade (Redis) para controle de sessões e filas de background.
