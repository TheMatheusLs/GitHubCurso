# Fluxo de Branches (Universos Paralelos)

## Conceito
Nunca trabalhe ou faça testes diretamente na branch `main` (ou `master`). A `main` deve conter apenas código que funciona. Para qualquer alteração (nova feature, correção de bug, experimento), crie uma **Branch**.

## O Ciclo de Vida (Workflow)

### 1. Criar e entrar no universo paralelo
Cria uma cópia exata do estado atual para você trabalhar seguro.
```bash
# Sintaxe moderna
git switch -c nome-da-sua-branch

# Sintaxe clássica (ainda muito usada)
git checkout -b nome-da-sua-branch
```

### 2. Trabalhar
Faça suas edições, salve e faça commits normalmente (`git add`, `git commit`).
*Nota: Tudo que você faz aqui **não** afeta a branch principal.*

### 3. Voltar para a base
Quando terminar (ou se precisar pausar), volte para a principal.
```bash
git switch main
# ou
git checkout main
```

### 4. Fundir (Merge)
Se o trabalho na branch ficou bom, traga-o para a principal.
1. Garanta que você está na principal: `git switch main`
2. Puxe as alterações da outra branch:
```bash
git merge nome-da-sua-branch
```

### 5. Limpeza
Após o merge, a branch perde a utilidade. Pode deletar.
```bash
git branch -d nome-da-sua-branch
```

## Comandos Úteis
*   `git branch`: Lista todas as branches locais.
*   `git lg`: Visualiza o grafo das branches e como elas se uniram.
```