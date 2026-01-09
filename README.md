Título: Desfazer o último commit (mas manter o código)
Cenário: Fiz o commit, mas esqueci de adicionar um arquivo ou a mensagem ficou ruim.
Comando: git reset --soft HEAD~1
Explicação: O --soft volta o histórico, mas deixa seus arquivos na área de preparação (staging) para commitar de novo.