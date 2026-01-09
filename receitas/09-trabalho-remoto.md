# Trabalho Remoto e Sincronização (GitHub)

## Conceitos Básicos
*   **Remote (Origin):** É a versão do seu repositório que vive na nuvem (GitHub). Por padrão, chamamos de `origin`.
*   **Clone:** Baixar um repositório da nuvem para uma máquina nova pela primeira vez.
*   **Push (Empurrar):** Enviar suas alterações locais para a nuvem.
*   **Pull (Puxar):** Baixar as alterações da nuvem para o seu computador.

---

## 1. Verificando a Conexão
Para saber se você está usando HTTPS ou SSH:
```bash
git remote -v
```
*   Se começar com `https://`: Você está usando senha/token web.
*   Se começar com `git@github.com`: Você está usando chaves SSH (Autenticação automática).

### Como trocar de HTTPS para SSH (Opcional)
Se você já configurou suas chaves SSH no GitHub e quer mudar o protocolo sem baixar tudo de novo:
```bash
git remote set-url origin git@github.com:SeuUsuario/git-mastery-playbook.git
```

---

## 2. Configurando a Segunda Máquina (Ex: Lab da Universidade)

**Cenário:** Você chegou no laboratório e quer baixar o projeto pela primeira vez.

1.  Abra o terminal na pasta onde quer salvar.
2.  Faça o clone (Cópia inicial):
    ```bash
    git clone https://github.com/SeuUsuario/git-mastery-playbook.git
    # Ou via SSH (se a chave do Lab estiver configurada no GitHub):
    git clone git@github.com:SeuUsuario/git-mastery-playbook.git
    ```
3.  Entre na pasta: `cd git-mastery-playbook`
4.  **Importante:** Rode o script de setup para configurar seus Aliases e o filtro do Jupyter nessa máquina também!
    *   Configure usuário/email.
    *   Configure os aliases (`git config ...`).
    *   Instale o `nbstripout` (`pip install nbstripout` e `nbstripout --install`).

---

## 3. O Ciclo de Trabalho Diário (Home & Lab)

**Regra de Ouro:** Sempre comece o dia com um Pull.

1.  **Chegou na máquina (Casa ou Lab):**
    ```bash
    git pull
    ```
    *Garante que você tem a última versão do trabalho.*

2.  **Trabalhou, codou, salvou:**
    ```bash
    git add .
    git cm "feat: avanço na analise de dados"
    ```

3.  **Antes de desligar o PC:**
    ```bash
    git push
    ```
    *Envia para a nuvem para poder pegar na outra máquina depois.*
```