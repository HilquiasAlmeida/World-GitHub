# 🔌 Automações via API REST do GitLab

A API REST do GitLab permite controlar praticamente qualquer aspecto de projetos, grupos, usuários e pipelines de forma programática.

---

## 1. Autenticação e Geração de Token
  Para interagir com a API, utilize um **Personal Access Token (PAT)** com o escopo `api`. Passe o token no cabeçalho de todas as requisições HTTP:

  ```bash
  PRIVATE-TOKEN: <seu-personal-access-token>
  ```

## 2. Exemplos Práticos com cURL
  * Listar Projetos de um Grupo
    `
    curl --header "PRIVATE-TOKEN: <seu-token>" "[https://gitlab.com/api/v4/groups/](https://gitlab.com/api/v4/groups/)<group_id>/projects"
  
  * Criar uma Issue Programaticamente via API
    
    curl --request POST \
     --header "PRIVATE-TOKEN: <seu-token>" \
     --header "Content-Type: application/json" \
     --data '{"title": "Bug crítico detectado em produção", "description": "Investigar falha de conexão com o banco de dados."}' \
     "[https://gitlab.com/api/v4/projects/](https://gitlab.com/api/v4/projects/)<project_id>/issues"
  
  * Disparar uma Pipeline de CI/CD via API
    
    curl --request POST \
     --header "PRIVATE-TOKEN: <seu-token>" \
     "[https://gitlab.com/api/v4/projects/](https://gitlab.com/api/v4/projects/)<project_id>/pipeline?ref=main"
