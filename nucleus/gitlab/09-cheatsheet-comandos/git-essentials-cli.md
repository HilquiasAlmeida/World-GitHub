# 🛠️ Git Essentials: Comandos Diários (Básico ao Intermediário)

Referência rápida para os comandos mais utilizados no ciclo de desenvolvimento diário com Git.

---

## 1. Inicialização e Clonagem
  ```bash
  # Clonar um repositório existente via HTTPS ou SSH
  git clone [https://gitlab.com/world-github/nucleus.git](https://gitlab.com/world-github/nucleus.git)
  git clone git@gitlab.com:world-github/nucleus.git
  
  # Inicializar um repositório vazio localmente
  git init
```

## 2. Sincronização e Fluxo de Trabalho (Workflow)
  ```bash
  # Verificar o status atual do repositório e arquivos modificados
  git status
  
  # Adicionar arquivos modificados para a área de preparação (staging)
  git add .                    # Adiciona todos os arquivos alterados
  git add <caminho/arquivo>    # Adiciona um arquivo específico
  
  # Consolidar as alterações com uma mensagem descritiva
  git commit -m "feat(modulo-09): adiciona cheatsheet de comandos básicos"
  
  # Enviar alterações locais para o repositório remoto
  git push origin <nome-da-branch>
  
  # Sincronizar e baixar alterações da branch remota atual
  git pull origin <nome-da-branch>
  ```

## 3. Gestão de Branches
  ```bash
  # Listar todas as branches locais e remotas
  git branch -a
  
  # Criar e mudar imediatamente para uma nova branch
  git checkout -b feature/nova-funcionalidade
  # ou na sintaxe moderna:
  git switch -c feature/nova-funcionalidade
  
  # Alternar entre branches existentes
  git switch main
  ```

