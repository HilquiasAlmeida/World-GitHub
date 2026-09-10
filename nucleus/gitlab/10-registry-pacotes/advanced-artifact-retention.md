# 🧹 Políticas de Retenção e Limpeza de Artefatos (Lifecycle Management)

Gerenciar o espaço de armazenamento do GitLab é essencial para evitar custos excessivos com infraestrutura e manter o ambiente limpo de imagens órfãs ou pacotes obsoletos.

---

## 1. Configurando Políticas de Limpeza de Contêineres (Cleanup Policies)
  No GitLab, você pode configurar regras automáticas para apagar imagens antigas do Container Registry que não são mais utilizadas.
  
  ### Configuração via Portal Web:
  1. Acesse o seu projeto no GitLab.
  2. Navegue até **Settings** > **Packages & registries** > **Container registry**.
  3. Em **Cleanup policies**, defina:
     * **Keep framework/tags:** Quantidade ou padrão de tags protegidas que nunca devem ser apagadas (ex: `main`, `v*`).
     * **Remove tags older than:** Período de retenção (ex: remover imagens com mais de 30 dias).
     * **Matching name:** Expressão regular para filtrar quais tags serão elegíveis para remoção (ex: `.*-rc.*` para versões de Release Candidate).
  
  ---
  
## 2. Deleção Programática via API REST
  Caso precise expurgar artefatos específicos de pacotes ou imagens programaticamente, utilize a API do GitLab:
  
  ```bash
  # Deletar um pacote específico no Registry de pacotes
  curl --request DELETE \
       --header "PRIVATE-TOKEN: <seu-token>" \
       "https://gitlab.com/api/v4/projects/<project_id>/packages/<package_id>"
  ```
  
---
