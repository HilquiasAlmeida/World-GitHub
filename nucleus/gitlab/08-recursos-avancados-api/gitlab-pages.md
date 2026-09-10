# 🌐 GitLab Pages (Hospedagem de Sites e Documentações)

O **GitLab Pages** permite publicar sites estáticos diretamente de um repositório do GitLab. É a ferramenta ideal para hospedar a documentação consolidada do **World GitHub**.

---

## 1. Configuração do `.gitlab-ci.yml` para GitLab Pages
  
  Para que o GitLab hospede automaticamente o site, a pipeline deve conter obrigatoriamente um job chamado exatamente de `pages` que envie os arquivos compilados para uma pasta pública (`public/`).

  ```yaml
  stages:
    - deploy
  
  pages:
    stage: deploy
    image: alpine:latest
    script:
      - echo "Compilando e movendo arquivos estáticos para a pasta public..."
      - mkdir -p public
      - cp -r docs/* public/
    artifacts:
      paths:
        - public
    rules:
      - if: $CI_COMMIT_BRANCH ==$CI_DEFAULT_BRANCH
    tags:
      - docker-runner
  ```

## 2. URL de Acesso Padrão
  Após a execução bem-sucedida da pipeline de deploy, o site estará disponível publicamente no formato:
  
  `https://<seu-usuario-ou-grupo>.gitlab.io/<nome-do-projeto>/`
  
