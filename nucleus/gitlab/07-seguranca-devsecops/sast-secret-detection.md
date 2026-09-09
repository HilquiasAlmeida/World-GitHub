# 🔍 SAST e Secret Detection (Análise Estática e Segredos)

Este guia detalha a implementação e a resposta a incidentes para Análise Estática de Código (SAST) e Detecção de Segredos (*Secret Detection*) no GitLab.

---

## 1. SAST (Static Application Security Testing)
O SAST analisa o código-fonte em busca de falhas estruturais, vulnerabilidades lógicas e falhas de injeção (como SQL Injection, XSS, deserialização insegura) sem executar a aplicação.

### Configuração Completa no `.gitlab-ci.yml`
```yaml
include:
  - template: Security/SAST.gitlab-ci.yml

sast:
  stage: test
  variables:
    SAST_EXCLUDED_PATHS: "spec/*, test/*, tests/*"
  rules:
    - if: $CI_PIPELINE_SOURCE == "merge_request_event"
    - if: $CI_COMMIT_BRANCH ==$CI_DEFAULT_BRANCH
  tags:
    - docker-runner
