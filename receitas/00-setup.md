Título: Iniciando o Git em uma nova máquina
Cenário: Você está configurando o Git em uma nova máquina e precisa definir seu nome de usuário e email.
Comando: 
```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu.email@exemplo.com"
```
Explicação: Configura o nome de usuário e email globalmente para todos os repositórios Git no sistema.

---

Título: Definindo o padrão de ```main''' para novos respositórios
Cenário: Você deseja que todos os novos repositórios Git criados tenham "main" como o branch padrão.
Comando:
```bash
git config --global init.defaultBranch main
```
Explicação: Define "main" como o nome padrão do branch inicial para novos repositórios Git.

---

Título: Criando um apelido para o Git log colorido e com formatação
Cenário: Você quer facilitar a visualização do histórico de commits com cores e formatação
Comando:
```bash
git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(auto)%d%C(reset)'"
```
Explicação: Cria um alias "lg" para um comando de log formatado e colorido, facilitando a leitura do histórico de commits.