# 🛡️ 7. Visão Geral de Segurança e DevSecOps

Este documento serve como a porta de entrada para o ecossistema de segurança corporativa do **World GitHub**. No modelo Enterprise, a segurança não é um obstáculo burocrático no final do ciclo, mas sim um conjunto de trilhos automatizados que acompanham o desenvolvedor desde a primeira linha de código até a produção.

---

## 📑 Estrutura de Documentos do Módulo
* [SAST e Detecção de Segredos](./sast-secret-detection.md) — Análise estática de código e prevenção de vazamento de credenciais.
* [Varredura de Dependências e Contêineres](./dependency-container-scanning.md) — Auditoria de bibliotecas de terceiros (CVEs) e imagens Docker.
* [Compliance e Pipelines de Conformidade](./compliance-pipelines.md) — Governança global, bloqueio de merges e políticas corporativas obrigatórias.

---

## 🚀 Filosofia Shift Left (Segurança no Início)
A cultura de *Shift Left* desloca os testes de segurança para o início do ciclo de desenvolvimento (ciclo de Merge Request). No World GitHub, aplicamos os seguintes princípios:
1. **Automação Nativa:** Nenhuma varredura depende de ação manual do desenvolvedor.
2. **Fail Fast (Falha Rápida):** Se uma vulnerabilidade de severidade crítica ou um segredo for identificado, a pipeline bloqueia o avanço imediatamente.
3. **Visibilidade Unificada:** Os resultados aparecem diretamente na tela do Merge Request, permitindo a correção antes do código atingir a branch principal (`main`).
