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
        
        git remote rm <nome>: remove o repositório remoto na máquina local

18º passo: Enviando mudanças para o repositório remoto:
   
    git push origin (meu repositório remoto) master (branch que estou)

19º passo: Puxando alterações do remoto pro local:

    git pull origin master

20º passo (opcional): Clonar repositório remoto:

    git clone <ssh> <newrepname>

21º passo (opcional): Criar uma ramificação do projeto (branch)

    git checkout -b <branchname>

    git branch
        Mostra os branchs existentes e em qual você está no momento

    git checkout <branchname>
        Alterna entre branchs

    git branch -D <branchname>
        Deleta um branch

22º passo (opcional): União dos branchs

    MERGE:
        Cria um novo commit juntando os commits separados de todos os branchs. Mais usado em pull requests.

        git merge <branch que você quer juntar>

    REBASE:
        Move os commits da branch secundária e jogar na frente do último commit da master (ou da branch pra qual você quer mover).

        git pull --rebase
            Evita problemas de histórico quando for dar pull no repositório

        git rebase <branch que você quer juntar> 

23º passo (opcional): Ignorar arquivos na hora do push (gitignore)

    Criar um arquivo .gitignore
    Nele eu vou descrever quem eu não quero que suba. Pra que ele ignore todos os arquivos de um tipo específico, botar "*.<extensão>"

24º passo (opcional): Salvar modificações para terminar depois, pra não levar  pra outro branch quando eu mudar

    git stash

    Quando for retomar:
        git stash apply

    Listar:
        git stash list

    Deletar os stashs:
        git stash list

25º passo (opcional): Criar atalhos no terminal

    git config --global alias.<atalho> <o que o atalho faria>

26º passo (opcional): Criar tags para marcar as versões:

    git tag -a <versão> -m "<mensagem>"

    git push origin master --tags

27º passo (opcional): Reverter um commit específico sem desfazer o commit que "deu errado". Você pode analisar o que deu errado depois, por exemplo.

    git revert <hash>

28º passo (opcional): Apagar tags e branchs:
    
    git push origin : <tag ou branch>