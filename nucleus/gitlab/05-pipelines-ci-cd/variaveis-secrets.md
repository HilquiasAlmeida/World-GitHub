# 🔒 Gestão de Variáveis e Secrets no GitLab CI/CD

Em projetos corporativos avançados, credenciais sensíveis (chaves de API, senhas de banco de dados, tokens de cloud) jamais devem ser expostas no código-fonte. Elas devem ser gerenciadas via **CI/CD Variables** do GitLab.

---

## 1. Configurando Variáveis com Segurança

**Passo 1**: No seu projeto do GitLab, acesse **Settings** > **CI/CD** > **Variables** e clique em **Add variable**.

**Passo 2**: Preencha os parâmetros de governança:
* **Key**: Nome da variável em letras maiúsculas (ex: `AWS_PRODUCTION_KEY`).
* **Value**: O valor sensível ou token secreto.
* **Protect variable**: Marque para que a variável seja exposta apenas em branches protegidas (como `main`).
* **Mask variable**: **Obrigatório** para mascarar o valor automaticamente nos logs da pipeline caso ele seja impresso por engano.

---

## 2. Consumindo Variáveis na Pipeline (`.gitlab-ci.yml`)

Veja como injetar e consumir essas variáveis de forma segura dentro de um job customizado:

```yaml
deploy_secure:
  stage: deploy
  image: alpine:latest
  script:
    - echo "Executando deploy seguro utilizando secrets protegidos..."
    - ./scripts/deploy.sh --token "$AWS_PRODUCTION_KEY"
  rules:
    - if: '$CI_COMMIT_BRANCH == "main"'
```

## 3. Verificação de Sucesso
  * Verificação: Ao rodar a pipeline, valide nos logs do job que os valores mascarados aparecem estritamente como `[MASKED]`,
      impedindo qualquer vazamento de dados confidenciais para a equipe.
