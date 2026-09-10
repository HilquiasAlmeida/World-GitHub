# 🚀 Git Avançado: Resolução de Crises e Manipulação de Histórico (Nível Infinito)

Comandos avançados para engenheiros que precisam consertar o histórico do repositório, resgatar código perdido ou realizar refatorações estruturais.

---

## 1. Reescrevendo o Histórico com Rebase Interativo
  ```bash
  # Unir os últimos N commits em um único commit limpo (squash)
  git rebase -i HEAD~4
  ```

## 2. Resgatando o que parecia Perdido (reflog)
  
  O reflog registra cada alteração de ponteiro (HEAD) no repositório local. 
  Se você apagou uma branch por engano ou fez um reset agressivo, o reflog salva sua vida:

  ```bash
  # Exibir o histórico de movimentações do repositório
  git reflog
  
  # Voltar o repositório para um estado anterior específico pelo hash do log
  git reset --hard HEAD@{numero}
  ```

## 3. Aplicando Commits Seletivos (cherry-pick)
  ```bash
  # Pegar um commit específico de outra branch e aplicar na branch atual
  git cherry-pick <hash-do-commit>
  ```

## 4. Caçando Bugs com Busca Binária (bisect)
  O bisect automatiza a busca pelo commit exato que introduziu um bug no sistema:

  ```bash
  # Iniciar o modo de busca binária
  git bisect start
  
  # Informar que o commit atual está quebrado (com bug)
  git bisect bad
  
  # Informar o último hash conhecido onde o sistema funcionava perfeitamente
  git bisect good <hash-antigo>
  
  # O Git testará commits intermediários automaticamente até apontar o culpado.
  # Ao terminar, encerre o modo bisect:
  git bisect reset
  ```

## 5. Salvamento Temporário Avançado (stash)
  ```bash
  # Guardar alterações sujas incluindo arquivos novos/não rastreados
  git stash -u
  
  # Listar todas as pilhas de stash salvas
  git stash list
  
  # Reaplicar o último stash e removê-lo da pilha
  git stash pop
  ```
