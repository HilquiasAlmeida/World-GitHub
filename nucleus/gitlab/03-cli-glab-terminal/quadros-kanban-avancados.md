# 📋 Quadros Kanban Avançados: Automação e Visibilidade

Os *Issue Boards* do GitLab vão muito além de quadros estáticos. Eles permitem gerenciar o fluxo de trabalho de ponta a ponta com regras automatizadas.

## 1. O Poder das *Scoped Labels* (Rótulos Escopados)
Para evitar o caos de cores e tags desorganizadas, o GitLab suporta *Scoped Labels*, que impedem que uma issue tenha estados conflitantes ao mesmo tempo. 
* Exemplo de sintaxe:
  * `workflow::backlog`
  * `workflow::in-dev`
  * `workflow::in-review`
  * `workflow::qa`
  * `workflow::done`
* *Regra de Negócio*: Se uma issue está marcada com `workflow::in-dev`, o sistema remove automaticamente qualquer outra label que comece com `workflow::`, garantindo que a issue esteja em apenas uma coluna por vez no quadro.

## 2. Configuração de *Swimlanes* (Raias)
Em quadros corporativos complexos, você pode fatiar o Kanban horizontalmente utilizando **Swimlanes**:
* **Por Assignee**: Para visualizar a carga de trabalho individual de cada engenheiro.
* **Por Milestone**: Para separar visualmente o que pertence à Sprint atual versus o backlog geral.
* **Por Epic**: Para enxergar o avanço das iniciativas de negócio separadas em faixas horizontais.

## 3. Automação de Listas no Board
Você pode configurar listas especiais no quadro que alteram o estado da issue automaticamente ao serem arrastadas:
* Arrastar uma issue para a coluna **Closed** fecha a issue nativamente.
* Atribuir marcos temporais automáticos baseados em listas de colunas de progresso.
