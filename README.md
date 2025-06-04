# Comandos Git

# Trabalhando com repositório local
git restore, git reset, git rebase

### Iniciar repositório local
`git init`
### Configurar repositório local
`git config [--local]  [--global]  [--system]`
### Verificar status da área de trabalho (arquivos já commitados, arquivos modificados ou staged)
`git status`
### Adicionar arquivos à área de staging
`git add <arquivo>`
### Adicionar todos os arquivos à área de staging
`git add .`
### Remover arquivos da área de staging
`git rm --cached <nome-do-arquivo>`
### Remover pasta da área de staging
`git rm -r --cached <nome-da-pasta/>`
### Fazer commit
`git commit -m "mensagem"`
### Criar branch
`git branch <nome-da-branch>`
### Listar branches
`git branch`
### Deletar branch
`git branch -d <branch-1>`
### Mudar de branch
`git checkout <nome-da-branch-que-irá-caminhar>`
### Renomear branch atual
`git branch -m <novo-nome>` (`-M` para forçar)
### Juntar a branch 'feature' à branch 'main'
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
### Comparar arquivos entre branch atual e outra branch
`git diff <branch-1>` </br>
Irá aparecer em vermelho as linhas que estão na <branch-1> mas não na atual; e em verde as linhas que não estão na <branch-1> e que estão na atual.
### Comparar arquivos entre duas branches
`git diff <branch-1> <branch-2>` </br>
Irá mostrar de vermelho o que está na <branch-1> e não está na <branch-2> </br>
Irá mostrar de verde o que está na <branch-2> e que não está na <branch-1>
###
### Recuperar arquivos deletados (passo 1)
`git checkout <commit-antes da deleção>` </br>
pegar o arquivo </br>
`git checkout <branch-mais atual>` </br>
soltar o arquivo na área de trabalho`
### Recuperar arquivos deletados (passo 2)
`git checkout <commit-antes-da-delecao> -- <nome-do-arquivo>` </br>
(O git "volta" para o commit anterior, mas especificamente apenas para o arquivo mencionado, trazendo ele para o commit atual)
### Mostrar detalhes do último commit ou de um commit específico
`git show` </br>
`git show *hash de um commit qualquer*`
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
### Visualizar histórico de commits completo:
`git --no-pager log`

# Trabalhando com repositório remoto

### Clonar repositório remoto
`git clone`
### Linkar repositório local a um repositório remoto
`git remote add <origin> <nome da branch remota>`
### Remover o link do repositório local com um repositório remoto
`git remote remove <origin>`
### Listar os repositórios remotos configurados
`git remote -v`
### Linkar branch local com uma branch remota específica
`git branch --set-upstream-to=origin/<branch-remota> <branch-local>`
### Linkar branch local com uma branch remota específica (versão enxuta)
`git branch -u origin/<branch-remota> <branch-local>`
### Enviar mudanças para o repositório remoto
`git push <apelido-repositorio-remoto(padrao=origin)> <branch-repositorio-remoto>`</br>
(criará a branch remota caso ela não exista)
### Enviar mudanças para o repositório remoto e linkar branch atual com a branch remota ao mesmo tempo
`git push -u <apelido-repositorio-remoto(padrao=origin)> <nome-branch-remota>` </br>
(criará a branch remota caso ela não exista)
### Enviar mudanças para o repositório remoto (caso o remoto padrão tenha sido definido)
`git push`
### Trazer modificações do repositório remoto
`git pull`
### Listar branches remotas
`git branch -r`
### Criar branch local que rastreia branch remota
`git branch <nome-branch-loca> <nome-branch-remota>`
### Criar branch local que rastreia branch remota e fazer checkout para ela diretamente
`git checkout -b <nome-branch-local> <nome-branch-remota>`
### Visualizar a lista de branches locais e as respectivas branches remotas
`git branch -vv`

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
