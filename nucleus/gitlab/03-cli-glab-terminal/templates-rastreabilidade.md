# 📝 Templates de Issues e Rastreabilidade de Tempo

Para manter a consistência e garantir que os desenvolvedores forneçam todas as informações técnicas necessárias, o GitLab utiliza modelos padronizados baseados em arquivos no repositório.

## 1. Estrutura de Issue Templates (`.gitlab/issue_templates/`)
Criamos templates dedicados para diferentes tipos de entrega. Exemplo de um template para novas Features (`.gitlab/issue_templates/feature.md`):

  ## 🎯 Resumo da Funcionalidade
  [Descreva claramente qual o valor de negócio e o objetivo desta feature]
  
  ## 🛠️ Requisitos Técnicos
  - [ ] Alteração de API necessária
  - [ ] Atualização de banco de dados / Migrations
  - [ ] Testes unitários cobrindo ao menos 80% do código novo
  
  ## 🧪 Critérios de Aceite (Definition of Done)
  1. O código passou por todas as etapas do pipeline sem erros.
  2. Code review aprovado por um Tech Lead.
  3. Documentação atualizada.

## 2. Controle de Tempo e Estimativas (Time Tracking)
    
  O GitLab possui comandos nativos (Slash Commands) que podem ser digitados diretamente nos comentários de uma issue para gerenciar estimativas e horas gastas sem precisar de ferramentas externas:

  *  ```/estimate 3d 4h``` -> Define que a issue tem uma estimativa de 3 dias e 4 horas de esforço.
  *  ```/spend 6h``` -> Registra que foram gastas 6 horas de trabalho nesta issue.
  *  Relatórios consolidados de tempo aparecem nativamente para acompanhamento de custos de projeto e capacidade da equipe.
