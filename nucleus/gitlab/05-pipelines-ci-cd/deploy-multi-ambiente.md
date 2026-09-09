# 🌐 Estratégias de Deploy Multi-Ambiente

Para projetos de nível corporativo avançado, o processo de entrega exige separação rígida entre ambientes de Homologação (Staging) e Produção, implementando barreiras de segurança e aprovação humana.

---

## 1. Pipeline com Staging Automático e Produção Manual

O arquivo abaixo configura um fluxo onde o ambiente de staging roda de forma automatizada após o build, mas a produção exige aprovação manual explícita:

```yaml
stages:
  - build
  - staging
  - production

build_app:
  stage: build
  image: node:20-alpine
  script:
    - npm ci
    - npm run build
  artifacts:
    paths:
      - dist/

deploy_staging:
  stage: staging
  image: alpine:latest
  environment:
    name: staging
    url: [https://staging.suaempresa.com](https://staging.suaempresa.com)
  script:
    - echo "Efetuando deploy automático em Staging..."
  only:
    - develop

deploy_production:
  stage: production
  image: alpine:latest
  environment:
    name: production
    url: [https://app.suaempresa.com](https://app.suaempresa.com)
  script:
    - echo "Efetuando deploy crítico em Produção..."
  when: manual
  allow_failure: false
  only:
    - main
```

---

## 2. Diretrizes de Governança

* **`when: manual`**: Trava o estágio de produção, exigindo que um mantenedor ou líder técnico clique manualmente no botão de play na interface do GitLab para efetivar o deploy.
* **`environment`**: Habilita o painel de rastreabilidade de ambientes em **Operate** > **Environments**, permitindo monitorar versões ativas e realizar rollbacks imediatos em caso de falhas em produção.
