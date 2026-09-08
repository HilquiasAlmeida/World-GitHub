# 🦊 GitLab Nucleus: A Central Definitiva do Ecossistema GitLab

Bem-vindo ao diretório oficial do **GitLab** dentro do núcleo (**`nucleus/gitlab/`**) do projeto **World-GitHub**. 

Este documento serve como uma central de referência técnica completa para dominar o ecossistema GitLab. Seja você um desenvolvedor escrevendo código localmente, um engenheiro configurando pipelines de CI/CD ou um líder técnico estruturando governança DevSecOps, tudo o que você precisa saber sobre o GitLab está centralizado aqui.

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
