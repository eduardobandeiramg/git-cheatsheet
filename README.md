# Comandos Git

### Iniciar repositório local
`git init`
### Configurar repositório local
`git config [--local]  [--global]  [--system]`
### Clonar repositório remoto
`git clone`
### Linkar repositório local a um repositório remoto
`git remote add origin <nome da branch remota>`
### Adicionar arquivos à área de staging
`git add <arquivo>`
### Fazer commit
`git commit -m "mensagem"`
### Verificar status da área de trabalho (arquivos já commitados, arquivos modificados ou staged)
`git status`
### Mudar de branch
`git checkout <nome-da-branch-que-irá-caminhar>`
### Recuperar arquivos deletados (passo 1)
`git checkout <commit-antes da deleção>` </br>
pegar o arquivo </br>
`git checkout <branch-mais atual>` </br>
soltar o arquivo na área de trabalho`
### Recuperar arquivos deletados (passo 2)
`git checkout <commit-antes-da-delecao> -- <nome-do-arquivo>` </br>
(O git "volta" para o commit anterior, mas especificamente apenas para o arquivo mencionado, trazendo ele para o commit atual)
### Juntar a branch <feature> à branch <main>
`git checkout main` </br>
`git merge <feature> -m "mensagem de merge"` </br>
`git merge <nome-da-branch-que-aponta-para-o-commit-que-desejo-que-a-branch-atual-passe-a-apontar>`
### Merge abrindo o editor
`git checkout main` </br>
`git merge <feature>` </br>
"i" > mensagem > esq > :wq > enter
### Merge abrindo o nano
`git checkout main` </br>
`git merge <feature>` </br>
mensagem > control o > enter > control x
### Mostrar detalhes do último commit ou de um commit específico
`git show` </br>
`git show *hash de um commit qualquer*`
### Enviar mudanças para o repositório remoto
`git push`
### Trazer modificações do repositório remoto
`git pull`
### Criar branch
`git branch <nome-da-branch>`
### Listar branches
`git branch`
### Deletar branch
`git branch -d <branch-1>`
### Restaurar arquivos para último commit
`git restore <arquivo>`
### Remover arquivos da área de staging
`git restore --staged <arquivo>`
### Desfazer último commit
`git reset --soft HEAD~1`
### Visualizar o projeto em uma branch ou commit específico
`git checkout <nome-da-branch>` </br>
`git checkout <hash-do-commit>`
### Visualizar histórico de commits
`git log  [--graph]  [--oneline]  [--all]  [--decorate]  [--pretty]` </br>
# Observações
* Branches são meramente ponteiros que apontam para um commit específico.
* Um repositório pode ter várias branches, cada uma apontando para um commit.
* Ao fazer checkout entre branches ou entre commits, o que está se movendo é o ponteiro HEAD.
* É possível que o ponteiro HEAD esteja apontando para um commit em vez de para uma branch. Neste caso, diz-se que o repositório está em um estado de HEAD destacado (detached HEAD).
* Quando se faz um `git merge <branch-1>`, o git procura o commit comum passado entre a branch atual e a branch "branch-1". Então, pega as alterações feitas na branch-1 que não conflitam com o commit atual da branch atual e passa essas mudanças para um novo commit. Commit este que a branch atual irá apontar.
* Existe um tipo de merge chamado "fast-forward". Ele acontece quando se faz um merge da <branch-1> na main; e a main não teve novos commits em relação ao ancestral comum das duas branches (quando elas já foram iguais). Ou seja, ocorreram mudanças apenas na branch <branch-1>, mas não na main. Neste caso, não faz sentido criar um commit de merge exatamente igual ao último commit da branch <branch-1>. Então, acontece um mero apontamento da branch <main> para o último commit da branch <branch-1>.
* Ao fazer o merge da <branch-1> na <main>, pode-se apagar a <branch-1> ou integrar a <main> nesta, fazendo o merge, desta vez, da <main> na <branch-1>.
* Quando uma nova branch é criada, (QUAIS COMMITS ELA INCORPORA NO SEU HISTÓRICO ? (GIT LOG))
* RESPONDER ^^^^^
