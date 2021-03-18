# Using-git

Default settings and files I use in git to use it with Sublime Text editor.

## Configure tooling

```sh
git config --global user.name 'name'
git config --global user.email 'email address'
git config --global color.ui auto
git config --global push.default upstream
git config --global merge.conflictstyle diff3

git config # aplica configurações no repositório
git config --global # aplica configurações de usuário
git config --system # aplica configurações para todos usuários
```

## Configure editor

```sh
ssh-keygen -t rsa -b 4096 -C "email"
git config --global core.editor "'C:/Program Files/Sublime Text 3/sublime_text.exe' -n -w"
```
## Files

Baixar os arquivos `.bash_profile` `git-completion.bash` `git-prompt.sh` e colar na pasta raiz de usuário em `C:\Users\user_name`

## Shortcut to Sublime

Abrir arquivo `.bash_profile` e adicionar a linha abaixo. 

*`alias subl="'C:/Program Files/Sublime Text 3/sublime_text.exe'"`*

Ou executar o comando

```sh
git config --global alias.subl "comando" # cria atalho para o comando
```

Isto permitirá utilizar o atalho `subl` para abrir arquivos e incluir as mensagens de commit com o Sublime Text com o comando simples de commit

```sh
subl nome_do_arquivo
git commit
```

## Formatting

Se você estiver em uma máquina Windows, isso converte as terminações LF em CRLF quando você faz o check-out do código:
```sh
git config --global core.autocrlf true
```
Caso esteja usando Linux ou macOs você pode dizer ao Git para converter CRLF para LF no commit:
```sh
git config --global core.autocrlf input
```
Caso o time esteja em sistemas diferentes é necessário desativar a conversão automática para quebra de linha (Recomendado)
```sh
git config --global core.autocrlf false
```
Entendendo a quebra de linhas [aqui](https://www.akitaonrails.com/2009/02/23/pequena-dica-de-git-para-windows#:~:text=O%20melhor%20jeito%20de%20usar,problema%20na%20configura%C3%A7%C3%A3o%20padr%C3%A3o%20dele.&text=Para%20quem%20n%C3%A3o%20sabe%20o,10%20(U%2B000A).)

## Add-on

Há um [plugin](https://packagecontrol.io/installation#st3) que você pode baixar e usar para visualizar arquivos de markdown no computador.

## Initial Config

```sh
git init
git remote add origin 'link do repositório'
git branch --set-upstream master origin/master
git add .
git commit -m "Initial files"
git push -u origin master
git branch --set-upstream master origin/master
```

## Main Comands

```sh
git init
git clone
git status

git log
git log --oneline --graph
git log --oneline --graph --all --decorate
git log -p
git shortlog
git shortlog -sne
git show SHA
git stat
git reflog # log de todos commits (inclui deletados)

git remote -v

git add file1 file2 fileN
git commit
git commit -m "messsage" # short message
git commit -am "message" # commit all modified files in stage 
git commit --amend    # modifica o ultimo commit

git stash # salva as mudanças do working directory
git stash list
git stash apply
git stash pop # aplica e remove o stash
git stash drop # remove o ultimo stash adicionado
git stash branch name # cria um branch, faz checkout e aplica stash

git reset file # unstage arquivo
git checkout -- file # desfaz alterações no arquivo
git checkout HEAD~1 # aponta para o último commit

git reset # remove do staged area e mantém alterações
git reset --hard # remove do staged area e desfaz alterações
git reset HEAD~1 # apaga um commit e mantém alterações
git reset --hard HEAD~1 # apaga um commit e desfaz alterações

git revert SHA # cria um novo commit que desfaz um determinado commit
git rebase -i HEAD~4 # para realizar modificações nos commits

git rm file # remove arquivo do commit e diretório
git rm --cached file # remove arquivo do commit e mantém no diretório
git rm -r file/folder # remove arquivo/pasta do remoto
 
git diff SHA1..SHA2
git diff --cached # staging area

git tag # exibe as tags
git tag -a nome # cria a tag com anotação
git tag -s nome # cria a tag assianda autenticação ssh
git tag -v nome # verifica uma tag
git tag -d nome # deleta a tag
git push --tags # envia tags para o remoto

git branch # cria uma branch
git branch -d nome # deleta um branch, use -D para forçar
git branch -m old_name new_name # renomeia um branch
git branch sidebar SHA # cria um branch a partir de um commit
git branch nome SHA # cria um branch para recuperar um commit de branch deletado
git checkout -b name # cria um branch e faz o checkout
git checkout nome
git branch -r # lista branch no remoto
git branch --set-upstream-to=origin/<branch> <local_branch> # tracking remote branch com local branch
git push origin :branch_name # deleta o branch no remoto

## Processo de merge
### Atualiza a feature com base na master
$ git checkout feature/do-something
$ git rebase master
### Merge feature na master
$ git checkout master
$ git merge --no-ff feature/do-something

git merge mergetool
git cherry-pick SHA # adiciona um commit especifico ao branch

git push
git push origin branch # envia branch para o remoto
git push origin branch:new_name # especificando novo nome no remoto
git fetch origin master # atualiza o repo local
git pull # git fetch + git merge
git pull --rebase # agrupa todas branchs em uma unica linha(indicado)

ssh-keygen -t rsa -b 4096 -C "email"
eval `ssh-agent -s` # inicial o agent ssh em background
ssh-add ~/.ssh/chave # adiciona chave ao agente

git config --system --unset credential.helper # remove configuração de credenciais armazenadas
```

## Guides

[Git rebase](https://raphaelfabeni.com/git-alterando-commits-parte-1/)

## Git branching model

<p align="center">
<img src="https://user-images.githubusercontent.com/9321996/88289855-41f21400-cccc-11ea-910a-7405624c3545.png" width="50%">
</p>

Author: Vincent Driessen
Original blog post: http://nvie.com/posts/a-successful-git-branching-model
License: Creative Commons BY-SA
