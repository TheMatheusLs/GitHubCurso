# Configuração Inicial e Produtividade

Este guia cobre a configuração "fazer uma vez e esquecer" para preparar uma nova máquina para desenvolvimento profissional.

## 1. Identidade do Desenvolvedor
---

**Cenário:**
O Git precisa saber quem é o autor das mudanças para registrar no histórico. Sem isso, os commits ficam sem dono ou bloqueados.

**Comandos:**
```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu.email@exemplo.com"
```

## 2. Modernização (Main Branch)
---

**Cenário:**
Antigamente, o branch principal se chamava master. O padrão moderno da indústria e do GitHub agora é main. É preciso alinhar sua máquina local para evitar conflitos de nomenclatura.

**Comandos:**
```bash
git config --global init.defaultBranch main
```

## 3. Kit de Produtividade (Aliases)
---

**Problema:**
Muitos comandos Git são longos e repetitivos. Usar aliases (apelidos) pode acelerar o fluxo de trabalho.

**Soluções:**
Criar "apelidos" (aliases) mnemônicos para os comandos mais usados.

**Configuração (Executar uma vez no terminal):**
```bash
# 's' -> status (Visualizar o estado do palco/arquivos)
git config --global alias.s status

# 'co' -> checkout (Trocar de branch ou recuperar arquivos)
git config --global alias.co checkout

# 'br' -> branch (Listar, criar ou deletar ramificações)
git config --global alias.br branch

# 'cm' -> commit message (Commitar rápido com mensagem)
git config --global alias.cm "commit -m"

# 'lg' -> Log Visual (O "Grafo do Metrô")
# Mostra histórico colorido, resumido e com linhas de conexão
git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(auto)%d%C(reset)'"
```

**Como usar no dia a dia:**
- Em vez de `git status`, use: `git s`
- Em vez de `git commit -m "msg"`, use: `git cm "msg"`
- Em vez de `git log ...`, use: `git lg`