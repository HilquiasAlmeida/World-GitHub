# 🔀 Múltiplos Perfis Git (`.gitconfig`)

Se você utiliza a mesma máquina para projetos corporativos (GitLab da empresa) e projetos pessoais (GitHub), configurar perfis condicionais evita que você faça commits com o e-mail errado.

---

## 1. Estrutura de Arquivos de Configuração

Em vez de alterar o nome e o e-mail manualmente a cada repositório, vamos estruturar o arquivo global do Git (`~/.gitconfig`) para alternar automaticamente com base na pasta onde o repositório está salvo.

### Organização sugerida de pastas:
* Projetos da empresa: `~/Projetos/empresa/`
* Projetos pessoais: `~/Projetos/pessoal/`

---

## 2. Criando os Perfis Específicos

Crie dois arquivos separados no seu diretório de usuário (`~`):

### A. Perfil Corporativo (`~/.gitconfig-empresa`)
Crie o arquivo com o seguinte conteúdo (substitua pelos seus dados da empresa):

```ini
[user]
    name = Seu Nome Corporativo
    email = seu-email@empresa.com
```

### B. Perfil Pessoal (`~/.gitconfig-pessoal`)
Crie o arquivo com o seguinte conteúdo (substitua pelos seus dados pessoais):

```ini
[user]
    name = Seu Nome Pessoal
    email = seu-email@pessoal.com
```

---

## 3. Configurando o Arquivo Global (`~/.gitconfig`)

Abra ou edite o seu arquivo principal de configuração global do Git (`~/.gitconfig`) e adicione as regras condicionais (`includeIf`):

```ini
[core]
    editor = code --wait

# Aplica o perfil corporativo automaticamente para qualquer repositório dentro da pasta da empresa
[includeIf "gitdir:~/Projetos/empresa/"]
    path = ~/.gitconfig-empresa

# Aplica o perfil pessoal automaticamente para qualquer repositório dentro da pasta pessoal
[includeIf "gitdir:~/Projetos/pessoal/"]
    path = ~/.gitconfig-pessoal
```

---

## 4. Verificação de Sucesso

Para testar se o perfil está sendo aplicado corretamente de acordo com a pasta:

1. Navegue até um repositório dentro da pasta corporativa e execute:
   ```bash
   git config user.email
   ```
   * **Verificação**: O terminal deve retornar o e-mail corporativo (`seu-email@empresa.com`).

2. Navegue até um repositório dentro da pasta pessoal e execute:
   ```bash
   git config user.email
   ```
   * **Verificação**: O terminal deve retornar o e-mail pessoal (`seu-email@pessoal.com`).
