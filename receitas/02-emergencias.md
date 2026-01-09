# Kit de Primeiros Socorros e Emergências

Comandos para situações de pânico, erros comuns e mudanças de contexto.

## 1. A Gaveta Temporária (Git Stash)

**Cenário:**
Você está no meio de um trabalho (código quebrado/incompleto) e precisa mudar de branch urgentemente para corrigir outra coisa.
*   Você não quer fazer commit de código ruim.
*   Você não pode perder o que já digitou.

**Solução:**
Guardar as mudanças na "Gaveta" (Stash) e recuperar depois.

**Comandos:**

1. **Guardar tudo e limpar a mesa:**
   ```bash
   git stash
   ```
   *O código volta ao estado do último commit. Seus arquivos novos ficam salvos na memória do Git.*

2. **Listar o que está guardado (caso tenha esquecido):**
   ```bash
   git stash list
   ```

3. **Pegar de volta (Recuperar):**
   ```bash
   git stash pop
   ```
   *Traz as mudanças de volta para o seu arquivo e apaga da gaveta.*

---

## 2. Desfazer alterações locais (Panic Button)

**Cenário:**
Você mexeu em um arquivo, estragou tudo, não gostou e quer que ele volte a ser exatamente como era no último commit.

**Comando:**
```bash
git checkout nome-do-arquivo
# ou (versão moderna)
git restore nome-do-arquivo
```

---

## 3. Corrigindo Commits (A Máquina do Tempo)

### Caso 1: Errei a mensagem ou esqueci um arquivo (Amend)
Altera o **último** commit feito.
1. Adicione o arquivo esquecido (opcional): `git add .`
2. Reescreva o commit:
   ```bash
   git commit --amend -m "Nova mensagem correta aqui"
   ```

### Caso 2: Quero desfazer o commit, mas manter o código (Soft Reset)
Útil quando você commita algo incompleto por engano. O commit desaparece do histórico, mas seus arquivos continuam na área de preparação (Verdes/Staged) prontos para serem editados.
```bash
git reset --soft HEAD~1
```
*Explicação: `HEAD~1` significa "volte 1 passo para trás no histórico".*
```