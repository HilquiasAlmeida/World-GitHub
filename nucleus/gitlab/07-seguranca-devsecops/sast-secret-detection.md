# 🔍 SAST e Secret Detection (Análise Estática e Segredos)

Este guia detalha a implementação e a resposta a incidentes para Análise Estática de Código (SAST) e Detecção de Segredos (*Secret Detection*) no GitLab.

---

## 1. SAST (Static Application Security Testing)
O SAST analisa o código-fonte em busca de falhas estruturais, vulnerabilidades lógicas e falhas de injeção (como SQL Injection, XSS, deserialização insegura) sem executar a aplicação.

### Configuração Completa no ``.gitlab-ci.yml``

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
```

## 2. Secret Detection (Detecção de Credenciais Vazadas)
  
  O vazamento acidental de chaves de API, tokens de acesso, chaves privadas SSH ou senhas em texto plano no repositório é uma falha crítica de segurança.

  O que fazer caso um Segredo seja Detectado:
  1. Bloqueio Automático: A pipeline falhará e o Merge Request será travado.
  2. Revogação Imediata: Acesse o provedor da credencial vazada (AWS, Google Cloud, Stripe, GitHub) e revogue a chave imediatamente.
  3. Expurgo do Histórico do Git: Se o segredo já tiver sido enviado para o histórico do repositório,
       utilize a ferramenta oficial de limpeza (git-filter-repo ou BFG Repo-Cleaner):
     ```bash
     git filter-repo --path caminho/do/arquivo/sensível --invert-path
     ```
* Configuração no ``.gitlab-ci.yml``
  ```YAML
    include:
    - template: Security/Secret-Detection.gitlab-ci.yml
  
  secret_detection:
    stage: test
    tags:
      - docker-runner
  ```
  
