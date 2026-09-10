# 🔔 Integração via Webhooks

Os Webhooks permitem que o GitLab envie notificações HTTP assíncronas (payloads em JSON) para sistemas externos sempre que eventos específicos ocorrem no repositório (como pushes, abertura de Merge Requests ou falhas em pipelines).

---

## 1. Configuração de um Webhook no GitLab
1. Acesse o seu projeto no GitLab.
2. Navegue até **Settings** > **Webhooks**.
3. No campo **URL**, insira o endpoint do receptor (ex: um microsserviço, API Gateway ou canal corporativo).
4. Em **Trigger**, selecione os eventos desejados (ex: *Push events*, *Merge request events*, *Pipeline events*).
5. Clique em **Add webhook**.

---

## 2. Exemplo de Payload JSON Recebido (Pipeline Event)
Quando uma pipeline muda de status, o GitLab envia uma estrutura semelhante a esta para o seu servidor:

```json
{
  "object_kind": "pipeline",
  "object_attributes": {
    "id": 15482,
    "ref": "main",
    "status": "failed",
    "stages": ["build", "test", "deploy"]
  },
  "project": {
    "name": "world-github",
    "web_url": "https://gitlab.com/world-github/nucleus"
  }
}
```
