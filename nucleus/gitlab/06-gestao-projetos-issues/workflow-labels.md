# 🏷️ Guia de Taxonomia e Governança de Labels

Este documento estabelece o ecossistema padronizado de **Labels (Etiquetas)** para rastreabilidade, filtragem e automação de fluxos de trabalho no repositório. O uso rigoroso desta taxonomia garante que qualquer issue seja instantaneamente categorizada e direcionada ao time responsável.

---

## 📑 Índice de Categorias
1. [Namespace: Tipo de Demanda (`tipo::`)](#1-namespace-tipo-de-demanda-tipo)
2. [Namespace: Nível de Prioridade (`prioridade::`)](#2-namespace-nível-de-prioridade-prioridade)
3. [Namespace: Status do Ciclo de Vida (`status::`)](#3-namespace-status-do-ciclo-de-vida-status)
4. [Namespace: Segurança e Governança (`seguranca::`)](#4-namespace-segurança-e-governança-seguranca)

---

## 1. Namespace: Tipo de Demanda (`tipo::`)
Define a natureza estrutural da issue, determinando qual equipe técnica realizará a triagem inicial e qual template foi aplicado na abertura.

* **`tipo::bug`**
  * **Definição:** Identificação de falhas, comportamentos inesperados ou quebras de contrato em funcionalidades existentes em ambiente homologado ou produtivo.
  * **Exemplo de Aplicação:** O gateway de pagamento retorna erro 500 intermitente após o último commit na branch principal.
* **`tipo::feature`**
  * **Definição:** Proposta de evolução arquitetural, criação de novos microsserviços ou entrega de novas capacidades de negócio.
  * **Exemplo de Aplicação:** Implementação do módulo de autenticação multifator (MFA) via TOTP.
* **`tipo::enterprise`**
  * **Definição:** Demandas corporativas críticas de infraestrutura, auditoria, conformidade regulatória ou governança global.
  * **Exemplo de Aplicação:** Atualização obrigatória de certificados SSL corporativos em todos os clusters Kubernetes.
* **`tipo::debt`**
  * **Definição:** Refatoração técnica necessária para reduzir débito tecnológico acumulado sem alterar regras de negócio visíveis.
  * **Exemplo de Aplicação:** Migração da biblioteca de logs legada para o padrão estruturado em JSON.

---

## 2. Namespace: Nível de Prioridade (`prioridade::`)
Estabelece a urgência temporal e o impacto operacional da demanda sobre os SLAs definidos pela engenharia.

* **`prioridade::critica`**
  * **Definição:** Sistema fora do ar, perda de dados transacionais ou falha de segurança iminente que exige interrupção imediata das atividades da squad.
  * **Exemplo de Aplicação:** Vazamento de tokens de acesso identificados nos logs de produção.
* **`prioridade::alta`**
  * **Definição:** Funcionalidade principal degradada, sem contorno automatizado (workaround) viável para o operador.
  * **Exemplo de Aplicação:** Relatórios gerenciais mensais falhando na exportação em massa.
* **`prioridade::media`**
  * **Definição:** Ajustes pontuais ou melhorias de fluxo que não impedem a operação diária do sistema.
  * **Exemplo de Aplicação:** Correção de desalinhamento visual em componentes de formulário mobile.
* **`prioridade::baixa`**
  * **Definição:** Demandas cosméticas ou melhorias de documentação de baixo impacto imediato.
  * **Exemplo de Aplicação:** Ajuste de typo em mensagens descritivas de tooltips.

---

## 3. Namespace: Status do Ciclo de Vida (`status::`)
Mapeia a posição exata da issue dentro do fluxo Kanban do projeto, automatizando transições e visibilidade de progresso.

* **`status::aguardando-triagem`**
  * **Definição:** Estado inicial atribuído automaticamente pelo template no momento da abertura, aguardando a análise do Tech Lead ou Scrum Master.
* **`status::em-desenvolvimento`**
  * **Definição:** A issue foi designada a um responsável e o código/solução está ativamente sendo construído na branch correspondente.
* **`status::em-code-review`**
  * **Definição:** O Pull/Merge Request foi aberto e o código está sob validação cruzada pelos pares de engenharia.
* **`status::homologacao`**
  * **Definição:** A solução foi integrada ao ambiente de testes e está sob validação de qualidade (QA).
* **`status::concluido`**
  * **Definição:** A entrega foi validada, mergeada na branch principal e implantada com sucesso em produção.

---

## 4. Namespace: Segurança e Governança (`seguranca::`)
Filtros voltados para auditoria de compliance, controle de acesso e validação regulatória.

* **`seguranca::revisar`**
  * **Definição:** Indica que a issue mexe com dados sensíveis (LGPD/GDPR), criptografia ou controle de acesso e exige o crivo obrigatório do time de Infosec.
* **`seguranca::auditado`**
  * **Definição:** Certificação de que a entrega passou por varredura de vulnerabilidades estáticas (SAST) e dinâmicas (DAST) sem achados críticos.
