# Trabalho em Equipe e Code Review (GitHub Flow)

Quando trabalhamos com outras pessoas (ou queremos uma revisão formal do nosso próprio código), não fazemos o merge direto no terminal. Usamos o GitHub.

## O Fluxo do Pull Request (PR)

### 1. Enviar a Branch para a Nuvem
Em vez de fazer o merge localmente, você empurra sua branch de experimento para o GitHub.
```bash
# Estando na branch 'experimento-raiz':
git push -u origin experimento-raiz
```

### 2. Criar o Pull Request (No Site)
1.  Abra o repositório no GitHub.
2.  Você verá um botão amarelo: **"Compare & pull request"**. Clique nele.
3.  Escreva um título e descrição: *"Professor, aqui está a implementação da raiz quadrada para revisão."*
4.  Clique em **Create pull request**.

### 3. A Revisão (Code Review)
Agora o código está numa "sala de espera".
*   Outras pessoas podem ver o `Files changed`, comentar nas linhas específicas e pedir mudanças.
*   Você pode fazer novos commits no seu PC e dar `push` na mesma branch. O PR atualiza automaticamente.

### 4. O Merge (Botão Verde)
Se tudo estiver aprovado:
1.  No site do GitHub, clique em **Merge pull request**.
2.  Clique em **Confirm merge**.
3.  O código da branch entra na `main`.

### 5. Sincronizar o Local
Agora a `main` da nuvem está atualizada, mas a do seu PC não.
```bash
git switch main
git pull
git branch -d experimento-raiz  # Pode apagar a branch velha
```