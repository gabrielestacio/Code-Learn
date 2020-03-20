1º passo: Configurar o nome de usuário do git
    git config --global user.name "<usuário>"

2º passo: Configurar o email ligado ao git
    git config --global user.email "<email>"

3º passo (opcional): Definir editor preferido
    git config --global core.editor "<editor (sublime é .subl)>"

4º passos (opcional): Consultar alguma das configurações anteriores:
    git config <configuração>
        ex: git config user.name
    git config --list (exibe todas as configutações do meu usuário)

5º passo: Inicializar o repositório:
    git init

6º passo (opcional): Utilizando o editor do terminal
    vi <filename>
    i (para escrever)
    esc (sair do modo de inserção)
    : (para digitar um comando)
    w (para salvar)
    q (para sair do arquivo)

7º passo (opcional): Visualizar o status do repositório:
    git status

8º passo: Adicionando arquivo untracked pro staged
    git add <filename>
        se eu editar o arquivo, preciso dar outro git add pra passar as alterações do modified pro staged

9º passo: Criando nova versão (commit)
    git commit -m "Adicionando arquivo"
        -m é para a mensagem

        git commit -am "Mensagem" (O am pode ser utilizado se os arquivos que serão commitados já existirem numa versão anterior. Evita o git add)
    
10º passo (opcional): Visualizar o histórico de commits
    git log
        git log --decorate (Adiciona algumas informações a mais)
        git log --author="<nome do autor>" (Filtra os commits pelo user que commitou)
        git log --graph (Mostra de forma gráfica como estão organizadas as branchs)

    git shortlog (Histórico rápido)
    
    git show <hash> (Descrição detalhada do commit)

11º passo (opcional):  Visualizar mudanças antes de commitar
    git diff
        git diff --name-only (Somente o nome do arquivo modificado)

12º passo (opcional): Resetar um arquivo editado antes do staged
    git checkout <filename>

12º passo (opcional): Resetar um arquivo editado depois do staged
    git reset HEAD <filename>
        pra desfazer a mudança depois desse passo, é só fazer o 11º

12º passo (opcional): Resetar um arquivo editado depois do commit
    git reset --soft (Volta pro staged) --mixed (Volta pra antes do staged) --hard (Destrói o último commit) <hash do anterior ao que eu quero desfazer>

13º passo: Criando chave ssh:
    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

14º passo: Pegando a chave ssh:
    cd ~/.ssh
    cat id_rsa.pub

15º passo: Ligando ssh no GitHub:
    Settings > SSH and GPG keys > New SSH key

16º passo (Opcional): Criando repositório remoto localmente:
    echo "# <repname>" >> README.md
    git init
    git add README.md
    git commit -m "first commit"
    git remote add origin git@github.com:gabrielestacio/<repname>.git
    git push -u origin master

17º passo: Ligando repositório local ao remoto:
    git remote add origin git@github.com:gabrielestacio/<repname>.git
    git push -u origin master