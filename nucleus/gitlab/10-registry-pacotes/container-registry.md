# 🐳 GitLab Container Registry (Docker / OCI)

O Container Registry nativo do GitLab permite armazenar, gerenciar e versionar imagens de contêineres diretamente associadas ao seu projeto ou grupo.

---

## 1. Autenticação no Registry
  Para interagir com o registry via linha de comando, faça o login utilizando as credenciais da sua conta ou um Deploy Token com permissões de leitura/escrita:

  ```bash
  docker login registry.gitlab.com -u <seu-usuario-ou-deploy-token> -p <seu-token-ou-senha>
  ```

## 2. Construção e Envio (Build & Push)
  Para enviar uma imagem para o registry do projeto, siga o padrão de nomenclatura exigido pelo GitLab:
  ```bash
  # Construir a imagem mapeando para o caminho do repositório GitLab
  docker build -t https://registry.gitlab.com/world-github/nucleus/app:v1.0.0

  # Enviar a imagem para o registry remoto
  docker push https://registry.gitlab.com/world-github/nucleus/app:v1.0.0
  ```

## 3. Automação no CI/CD (`.gitlab-ci.yml`)
  Exemplo de job para compilar e enviar a imagem automaticamente utilizando as variáveis de ambiente nativas do GitLab:
  ```bash
    stages:
    - build
  
  build_container:
    stage: build
    image: docker:latest
    services:
      - docker:dind
    script:
      - docker login -u $CI_REGISTRY_USER -p $CI_REGISTRY_PASSWORD $CI_REGISTRY
      - docker build -t $CI_REGISTRY_IMAGE:$CI_COMMIT_SHA -t $CI_REGISTRY_IMAGE:latest .
      - docker push $CI_REGISTRY_IMAGE:$CI_COMMIT_SHA
      - docker push $CI_REGISTRY_IMAGE:latest
    tags:
      - docker-runner
    ```
