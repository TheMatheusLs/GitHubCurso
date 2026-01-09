# Commit Parcial (Cirurgia de Arquivos)

## Cenário
Você fez duas alterações distintas no **mesmo arquivo**.
*   Exemplo: Criou uma nova função (Feature) E corrigiu um erro de português no comentário (Docs).
*   **Problema:** Se der `git add .`, tudo vai num commit só, misturando conceitos.
*   **Objetivo:** Fazer um commit `feat:` e depois um commit `docs:`, separando as mudanças lógicas.

## Solução 1: Via VS Code (Visual & Rápido)
A forma mais recomendada para o dia a dia.

1.  Abra a aba de **Controle de Código (Source Control)** no menu lateral.
2.  Clique no nome do arquivo alterado para abrir a visualização de **Diff** (Comparação).
3.  Selecione com o mouse apenas as linhas que deseja enviar no primeiro commit.
4.  Clique com o **botão direito** sobre a seleção.
5.  Escolha **Stage Selected Ranges** (Preparar Intervalos Selecionados).

**O que acontece:**
O arquivo aparecerá duplicado na lista:
*   **Staged (Verde):** Contém apenas o trecho selecionado. Pronta para o commit.
*   **Changes (Vermelho):** Contém o resto do arquivo. Ficará para o próximo commit.

Faça o commit do que está verde, e depois repita o processo para o resto.

---

## Solução 2: Via Terminal (Modo Interativo)
Útil para servidores ou quando não se tem interface gráfica.

Comando:
```bash
git add -p nome-do-arquivo
```
*(O `-p` significa Patch/Pedacinho)*

O Git vai mostrar trecho por trecho (Hunk) e perguntar:
`Stage this hunk [y,n,q,a,d,/,s,e]?`

*   **y (Yes):** Adiciona esse pedaço.
*   **n (No):** Ignora esse pedaço por enquanto.
*   **s (Split):** Divide o pedaço em pedaços menores (se o Git achou que era tudo uma coisa só).
```