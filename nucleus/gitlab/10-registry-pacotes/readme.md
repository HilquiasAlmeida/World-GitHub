# 📦 10: GitLab Registries e Gestão de Artefatos

Este módulo centraliza a infraestrutura de armazenamento e distribuição de artefatos do ecossistema **World GitHub**. Ele capacita as equipes a publicarem e consumirem dependências privadas de forma segura, unificando imagens de contêineres e pacotes de linguagem em um único local.

---

## 📑 Estrutura de Documentos do Módulo
* [Container Registry (Docker/OCI)](./container-registry.md) — Gestão completa de imagens de contêineres, build, push, pull e versionamento.
* [Package Registries (NPM, Maven, PyPI)](./package-registries-npm-maven.md) — Publicação e consumo de pacotes de código para diferentes linguagens de programação.
* [Políticas de Retenção e Limpeza](./advanced-artifact-retention.md) — Governança de armazenamento, limpeza automática e políticas de expiração de artefatos.

---

## 🎯 Objetivo Arquitetural
Eliminar a dependência de serviços externos de armazenamento de pacotes terceirizados, garantindo que o ciclo de vida DevOps utilize o ecossistema integrado e seguro do GitLab.
