# ⚙️ Configurações e Governança de Projetos via Portal Web

  O painel de configurações (*Settings*) do GitLab centraliza as políticas de segurança, controle de acesso e regras de integração do repositório.

---

## 1. Proteção de Branches (Protected Branches)
  Para impedir que qualquer usuário sobrescreva a branch principal (`main`), configure as proteções visuais:
  1. Acesse **Settings** > **Repository** > **Protected branches**.
  2. Selecione a branch `main`.
  3. Em **Allowed to push**, defina como *No one* (ninguém faz push direto).
  4. Em **Allowed to merge**, defina quem pode aprovar e mesclar (ex: *Maintainers*).
  5. Marque a opção **Require approval from code owners** para garantir validação técnica.

---

## 2. Gestão de Membros e Permissões (Members)
  1. Acesse **Settings** > **Members**.
  2. Clique em **Invite members**.
  3. Atribua o nível de acesso adequado:
     * **Guest:** Apenas visualização e comentários em issues.
     * **Reporter:** Leitura de código, abertura de issues e visualização de relatórios.
     * **Developer:** Criação de branches, abertura de MRs, execução de pipelines e escrita de código.
     * **Maintainer:** Gerenciamento total de configurações, proteção de branches e gestão do projeto.
