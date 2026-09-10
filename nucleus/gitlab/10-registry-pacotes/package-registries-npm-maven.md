# 📦 Package Registries (NPM, Maven, PyPI, NuGet)

O GitLab abriga registries nativos para diversas linguagens de programação, permitindo publicar bibliotecas privadas e consumi-las em outras aplicações do grupo corporativo.

---

## 1. Publicação de Pacotes NPM
  Para publicar um pacote NPM no registry do projeto, configure o arquivo `.npmrc` com o escopo e o token de acesso:

  ```text
  @world-github:registry=https://gitlab.com/api/v4/projects/<project_id>/packages/npm/
  //https://gitlab.com/api/v4/projects/<project_id>/packages/npm/:_authToken="<seu-personal-access-token>"
  //https://gitlab.com/api/v4/projects/<project_id>/packages/npm/:always-auth=true
  ```

  * Com a configuração pronta, execute o comando de publicação:
  ```Bash
  npm publish
  ```

## 2. Publicação de Artefatos Maven (Java)
  Para projetos Java, o arquivo pom.xml deve apontar para o repositório de distribuição do GitLab:
  
  ```bash
  XML
  <distributionManagement>
    <repository>
      <id>gitlab-maven</id>
      <url>https://gitlab.com/api/v4/projects/<project_id>/packages/maven</url>
    </repository>
  </distributionManagement>
  ```
  * Para realizar o deploy via linha de comando:
  
  ```Bash
  mvn deploy
  ```
