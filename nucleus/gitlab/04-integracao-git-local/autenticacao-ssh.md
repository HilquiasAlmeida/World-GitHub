# 🔑 Autenticação Segura via Chave SSH

O uso de chaves SSH evita a necessidade de digitar senhas ou tokens a cada `git push` ou `git pull`.

## 1. Gerando uma Nova Chave SSH
Abra o terminal na sua máquina e execute o comando abaixo (substituindo pelo seu e-mail corporativo):
```bash
ssh-keygen -t ed25519 -C "seu-email@empresa.com"
```

* **Verificação de sucesso**:
    O terminal exibirá a mensagem de confirmação de criação da chave
      e mostrará o local do arquivo gerado (geralmente em ```~/.ssh/id_ed25519```).

## 2. Adicionando a Chave ao GitLab
  1. Copie o conteúdo da chave pública para a área de transferência:
    ```bash
      cat ~/.ssh/id_ed25519.pub
    ```
  2. Acesse o GitLab -> Preferences -> SSH Keys.
  3. Cole a chave pública, defina um título descritivo e clique em Add key.

## 3. Testando a Conexão

  Execute o comando de teste no terminal:
  ```Bash
  ssh -T git@gitlab.com
  ```

  * **Verificação de sucesso**: O terminal deve retornar a mensagem:
      ```Welcome to GitLab, @seu-usuario!```
