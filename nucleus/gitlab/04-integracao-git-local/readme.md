# 💻 04. Integração Git Local: Conectando sua Máquina ao GitLab

Este diretório documenta o processo completo para configurar a máquina de desenvolvimento do engenheiro e integrá-la de forma segura ao ecossistema do GitLab.

---

## 1. O Pipeline de Conexão Local
Para que sua máquina interaja com os repositórios remotos do GitLab, é necessário configurar dois pilares principais:
* **Autenticação Segura**: Uso de chaves SSH (recomendado) ou Personal Access Tokens (PATs) para HTTPS.
* **Identidade Global (`.gitconfig`)**: Garantir que seus commits estejam assinados e associados ao seu e-mail corporativo correto.

---

## 📂 Documentação Detalhada Deste Módulo
* 🔑 **Configuração de Chaves SSH**: Passo a passo em [`autenticacao-ssh.md`](./autenticacao-ssh.md).
* 🎫 **Personal Access Tokens (PATs)**: Gestão de tokens de acesso em [`personal-access-tokens.md`](./personal-access-tokens.md).
* 🔀 **Múltiplos Perfis Git**: Configuração avançada de múltiplos repositórios em [`multiplos-perfis-gitconfig.md`](./multiplos-perfis-gitconfig.md).
