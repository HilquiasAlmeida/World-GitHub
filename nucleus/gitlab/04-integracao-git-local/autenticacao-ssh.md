# 🔑 Autenticação Segura via Chave SSH

O uso de chaves SSH evita a necessidade de digitar senhas ou tokens a cada `git push` ou `git pull`.

## 1. Gerando uma Nova Chave SSH

Abra o terminal na sua máquina e execute o comando abaixo (substituindo pelo seu e-mail corporativo):

```bash
ssh-keygen -t ed25519 -C "seu-email@empresa.com"
```

**Verificação de sucesso**: O terminal exibirá a mensagem de confirmação de criação da chave e mostrará o local do arquivo gerado (`~/.ssh/id_ed25519`).

---

## 2. Adicionando a Chave ao GitLab

**Passo 1**: Copie o conteúdo da chave pública para a área de transferência executando o comando:

```bash
cat ~/.ssh/id_ed25519.pub
```

**Passo 2**: No seu navegador, acesse o GitLab, vá em **Preferences** > **SSH Keys**.

**Passo 3**: Cole a chave pública no campo indicado, defina um título descritivo e clique em **Add key**.

---

## 3. Testando a Conexão

Execute o comando de teste no terminal:

```bash
ssh -T git@gitlab.com
```

**Verificação de sucesso**: O terminal deve retornar a mensagem exata: `Welcome to GitLab, @seu-usuario!`

---

## 4. Configuração Avançada de Host (`~/.ssh/config`)

Se você gerencia múltiplos repositórios ou diferentes chaves SSH na mesma máquina, crie ou edite o arquivo `~/.ssh/config` com o seguinte conteúdo para garantir que o GitLab utilize sempre a chave correta:

```text
Host gitlab.com
  User git
  IdentityFile ~/.ssh/id_ed25519
  IdentitiesOnly yes
```

**Verificação de sucesso**: O arquivo garante que o comando aponte explicitamente para a chave correta, eliminando conflitos de permissão (`Permission denied (publickey)`).
