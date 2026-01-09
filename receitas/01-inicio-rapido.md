# Início Rápido (Cheat Sheet)

O fluxo "arroz com feijão" para trabalhar sozinho ou sincronizar máquinas.

## 1. Começando o dia (Sync)
Sempre baixe a versão mais atual antes de tocar em qualquer arquivo.
```bash
git pull
```

## 2. Trabalhando (O Ciclo)
1.  (Opcional) Crie uma branch se for algo arriscado: `git switch -c nome-da-branch`
2.  Edite seus códigos.
3.  Verifique o que mudou: `git s` (status)
4.  Adicione ao palco: `git add .`
5.  Tire a foto (Commit): `git cm "feat: descrição do que fiz"`

## 3. Terminando o dia (Backup/Sync)
Envie tudo para o GitHub para garantir que não vai perder nada se o PC queimar.
```bash
git push
```
*(Se estiver em uma branch nova, o Git vai pedir para rodar um comando de 'set-upstream', apenas copie e cole o que ele sugerir).*