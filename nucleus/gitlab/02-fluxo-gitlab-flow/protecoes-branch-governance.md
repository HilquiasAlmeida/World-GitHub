# 🛡️ Governança e Proteção de Branches (*Protected Branches & Code Owners*)

Em ambientes corporativos, deixar a branch principal (`main`/`production`) aberta a qualquer commit é uma falha crítica de segurança. O GitLab oferece mecanismos rígidos de proteção.

## 1. Regras de Proteção de Branches (Protected Branches)
Para as branches críticas, configuramos restrições rígidas no GitLab:
* **Allowed to push**: Ninguém (nem mesmo desenvolvedores seniores) pode fazer `git push origin main` diretamente. O push direto é bloqueado por padrão.
* **Allowed to merge**: Define quais papéis ou grupos específicos têm permissão para aprovar e efetivar o merge.
* **Code Review Obrigatório**: Exige pelo menos uma ou mais aprovações de revisores antes que o botão de merge seja habilitado.

---

## 2. O Poder do Arquivo `CODEOWNERS`
Para automatizar a governança, um arquivo `.gitlab/CODEOWNERS` deve ser colocado na raiz do repositório para definir quem é responsável por aprovar alterações em partes específicas do código:

```text
# Exemplo de configuração do arquivo CODEOWNERS
[Infraestrutura & Terraform]
/terraform/ @corporate/devops-team

[Segurança & Compliance]
/security-policies/ @corporate/secops-lead

[Código Geral da Aplicação]
* @corporate/core-maintainers
```
