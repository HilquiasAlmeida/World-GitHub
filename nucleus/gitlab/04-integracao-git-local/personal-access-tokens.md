# 🎫 Personal Access Tokens (PATs) para HTTPS

Caso sua rede corporativa bloqueie a porta SSH (porta 22), a alternativa padrão é utilizar conexões seguras via HTTPS autenticadas por **Personal Access Tokens (PATs)**.

---

## 1. Gerando um PAT no GitLab

**Passo 1**: No canto superior direito do GitLab, acesse **Preferences** (ou **User Settings**) > **Access Tokens**.

**Passo 2**: Defina um nome descritivo para o token (ex: `notebook-corporativo-https`) e uma data de expiração compatível com a política de segurança da sua empresa.

**Passo 3**: Selecione os escopos essenciais para o fluxo de desenvolvimento diário:
* `read_repository` (Permite clonar e ler repositórios)
* `write_repository` (Permite realizar push, commit e alterações)
* `api` (Permite acesso completo à API para integração com ferramentas)

**Passo 4**: Clique no botão **Create personal access token** e **salve o código gerado imediatamente** em um local seguro (ele não será exibido novamente pelo GitLab).

---

## 2. Clonando e Configurando o Repositório Local

Ao clonar um repositório via HTTPS, utilize a URL padrão fornecida pelo GitLab:

```bash
git clone [https://gitlab.com/seu-grupo/seu-projeto.git](https://gitlab.com/seu-grupo/seu-projeto.git)
```

* **Autenticação**: Quando o terminal solicitar o seu **Username**, digite o seu nome de usuário do GitLab. Quando solicitar a **Password**, **cole o Personal Access Tokens (PAT)** gerado anteriormente (sua senha de login padrão não funcionará se a autenticação de dois fatores estiver ativa).

---

## 3. Armazenando Credenciais com Segurança (Credential Helper)

Para evitar que o Git solicite o seu usuário e token manualmente a cada comando `git push` ou `git pull`, configure o cache de credenciais local:

```bash
git config --global credential.helper store
```

* **Verificação de sucesso**: Na primeira autenticação bem-sucedida após esse comando, o Git salvará suas credenciais de forma segura no arquivo `~/.git-credentials`, automatizando as próximas conexões via HTTPS.
