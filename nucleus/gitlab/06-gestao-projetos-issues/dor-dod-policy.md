# 📋 Política de Governança: Definition of Ready (DoR) e Definition of Done (DoD)

Este documento define os critérios objetivos que impedem a entrada de demandas mal estruturadas no ciclo de desenvolvimento e estipulam o patamar de qualidade obrigatório para que uma entrega seja considerada finalizada.

---

## 1. Definition of Ready (DoR) - Critérios de Entrada no Sprint
Uma issue só pode ser puxada da coluna de triagem para o desenvolvimento ativo se cumprir integralmente os seguintes requisitos:
* **Escopo Definido:** O objetivo de negócio e a proposta de solução técnica estão descritos no padrão do template.
* **Issue Vinculada:** Possui taxonomia de labels correta (`tipo::`, `prioridade::`).
* **Dependências Mapeadas:** Os impactos em APIs, bancos de dados ou microsserviços vizinhos foram identificados e documentados.
* **Estimativa Atribuída:** A pontuação de complexidade foi definida pelo time técnico.

---

## 2. Definition of Done (DoD) - Critérios de Conclusão da Entrega
Uma issue só pode ser movida para a coluna `status::concluido` e implantada em produção mediante a validação de todos os itens abaixo:
* **Código Revisado:** O Merge Request foi aprovado por pelo menos um Tech Lead ou desenvolvedor sênior (Code Review).
* **Testes Automatizados:** A cobertura de testes unitários atinge o patamar mínimo exigido para o módulo (>= 80%).
* **Pipeline Verde:** O build de integração contínua (CI/CD) executou sem falhas de compilação ou alertas críticos de segurança (SAST).
* **Documentação Atualizada:** Os arquivos de arquitetura ou guias de referência do World GitHub refletem as alterações introduzidas.
* **Deploy Homologado:** A funcionalidade ou correção foi validada em ambiente de homologação pela equipe de qualidade (QA).
