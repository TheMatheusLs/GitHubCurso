# Contexto Acadêmico (Python, LaTeX e Jupyter)

## 1. Limpando Jupyter Notebooks automaticamente

**Cenário/Problema:**
Notebooks (`.ipynb`) salvam gráficos, tabelas e logs de erro dentro do próprio arquivo. Isso polui o histórico do Git, deixa o repositório pesado (MBs ou GBs desnecessários) e torna impossível comparar versões com `git diff`.

**Solução:**
Usar a ferramenta `nbstripout`. Ela age como um filtro que remove (strip) as saídas (outputs) antes do arquivo ser enviado para o commit.

**Comandos de Configuração:**
```bash
# 1. Instalar a biblioteca (apenas uma vez na máquina)
pip install nbstripout

# 2. Ativar o filtro no repositório atual (fazer em cada projeto novo)
nbstripout --install