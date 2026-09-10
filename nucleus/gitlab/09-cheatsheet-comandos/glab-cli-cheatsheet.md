# ⚡ GitLab CLI (`glab`): Automação via Terminal

A ferramenta oficial `glab` permite interagir com o GitLab diretamente pela linha de comando, sem precisar abrir o navegador web.

---

## 1. Autenticação Inicial
  ```bash
  # Autenticar na instância do GitLab (GitLab.com ou Self-Hosted)
  glab auth login
  ```

## 2. Gestão de Merge Requests (MRs)
  ```bash
  # Criar um Merge Request interativamente direto da branch atual
  glab mr create
  
  # Listar os Merge Requests abertos no projeto
  glab mr list
  
  # Aprovar um Merge Request via terminal
  glab mr approve <id-do-mr>
  
  # Realizar o merge automático de um MR aprovado
  glab mr merge <id-do-mr>
  ```

## 3. Gestão de Issues
  ```bash
  # Criar uma nova issue rapidamente
  glab issue create --title "Correção de layout no painel" --label "tipo::bug"
  
  # Listar issues atribuídas a você
  glab issue list --assignee @me
  ```

## 4. Monitoramento de Pipelines CI/CD
  ```bash
  # Visualizar o status da pipeline da branch atual
  glab ci status
  
  # Acompanhar a execução de uma pipeline em tempo real
  glab ci trace
  ```
