# Arquivos Grandes e Versionamento (LFS & Tags)

## 1. Git LFS (Large File Storage)

**Problema:**
O GitHub bloqueia arquivos maiores que 100MB. O Git fica lento com arquivos binários grandes (Datasets, Modelos de IA, JARs).

**Solução:**
Usar o Git LFS para gerenciar esses arquivos.

**Como usar:**
1. Instalar (uma vez na máquina): `git lfs install`
2. Rastrear extensões no projeto:
   ```bash
   git lfs track "*.csv"
   git lfs track "*.pkl"
   git lfs track "*.h5"
   ```
3. **Importante:** Commitar o arquivo `.gitattributes` gerado.

---

## 2. Tags (Versionamento de Entregas)

**Cenário:**
Você enviou um artigo ou entregou um código. Você precisa "congelar" esse momento para referência futura, caso precise voltar exatamente para essa versão.

**Comandos:**

*   **Criar Tag (Anotada):**
    ```bash
    git tag -a v1.0 -m "Submissão para Revista Nature"
    ```

*   **Listar Tags:**
    ```bash
    git tag
    ```

*   **Mostrar detalhes de uma Tag:**
    ```bash
    git show v1.0
    ```

*   **Voltar para uma Tag (somente leitura):**
    ```bash
    git checkout v1.0
    ```
    *(Para voltar ao normal depois: `git switch main`)*

*   **Criar Tag (Leve):**
    ```bash
    git tag v1.1
    ```

*   **Criar uma Branch a partir de uma Tag:**
    ```bash
    git checkout -b nova-branch v1.0
    ```