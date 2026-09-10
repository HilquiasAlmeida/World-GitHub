# 📦 Dependency Scanning e Container Scanning

Este documento aborda a segurança de componentes externos, englobando bibliotecas de código de terceiros (npm, Maven, pip) e imagens de contêineres Docker.

---

## 1. Dependency Scanning (Varredura de Dependências)
  Aplicações modernas utilizam centenas de pacotes externos. 
  O Dependency Scanning verifica se as versões importadas pelo projeto possuem vulnerabilidades conhecidas registradas na base de dados de CVEs.

### Configuração no `.gitlab-ci.yml`
  ```yaml
  include:
    - template: Security/Dependency-Scanning.gitlab-ci.yml
  
  dependency_scanning:
    stage: test
    tags:
      - docker-runner
  ```

## 2. Container Scanning (Varredura de Imagens Docker)
  Antes que uma imagem de contêiner seja enviada para o Registry corporativo ou implantada em produção, 
    ela passa por uma auditoria de vulnerabilidades em seus pacotes do sistema operacional base (Alpine, Ubuntu, Debian, etc.).

  Exemplo de Stage de Container Scanning na Pipeline:
  
  ```
  YAML
  include:
    - template: Security/Container-Scanning.gitlab-ci.yml
  
  container_scanning:
    stage: test
    variables:
      DOCKER_IMAGE: $CI_REGISTRY_IMAGE/$CI_COMMIT_REF_SLUG:$CI_COMMIT_SHA
    tags:
      - docker-runner
    ```
