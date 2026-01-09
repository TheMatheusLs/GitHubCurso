# Contexto Acadêmico (Python, LaTeX e Jupyter)

Este documento reúne estratégias específicas para lidar com arquivos de pesquisa e escrita científica no Git.

## 1. Limpando Jupyter Notebooks automaticamente

**Cenário/Problema:**
Notebooks (`.ipynb`) não são apenas código; eles salvam gráficos, tabelas e logs de execução dentro do arquivo.
*   Isso polui o histórico com milhares de linhas de "lixo" (código de imagem base64).
*   Deixa o repositório pesado desnecessariamente.
*   Torna impossível usar o `git diff` para ver o que mudou no código.

**Solução:**
Usar a ferramenta **`nbstripout`**. Ela age como um filtro que remove (strip) as saídas (outputs) e números de execução antes do commit.

**Comandos de Configuração:**
```bash
# 1. Instalar a biblioteca (apenas uma vez na máquina)
pip install nbstripout

# 2. Ativar o filtro no repositório atual (Executar na raiz do projeto)
nbstripout --install
```

**Resultado:**
O Git armazena apenas o código-fonte (input). Seus gráficos continuam visíveis no seu computador, mas não pesam no histórico do Git.

---

## 2. Escrita Amigável ao Git (LaTeX e Markdown)

**Cenário/Problema:**
Textos acadêmicos sofrem constantes revisões. Se você escreve um parágrafo inteiro em uma única linha de código, ao mudar uma vírgula, o Git marca o parágrafo todo como alterado. Isso dificulta a revisão (diff).

**Solução:**
Adotar a técnica **"One Sentence Per Line"** (Uma frase por linha).

**Como fazer:**
Nunca escreva blocos infinitos de texto na mesma linha. Dê um `ENTER` no teclado após cada ponto final.

**Exemplo Prático:**

*❌ Ruim (Git vê 1 linha):*
```latex
A introdução aborda o contexto. O problema foi identificado em 2020. A solução proposta usa IA.
```

*✅ Bom (Git vê 3 linhas):*
```latex
A introdução aborda o contexto.
O problema foi identificado em 2020.
A solução proposta usa IA.
```

**Benefício:**
O LaTeX/Markdown junta as linhas automaticamente no PDF final (o leitor não vê diferença), mas no Git você consegue ver exatamente qual frase foi alterada, excluída ou adicionada.