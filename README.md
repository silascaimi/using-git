# Using-git

Default settings and files I use in git to use it with Sublime Text editor.

## Configure tooling

```sh
git config --global user.name 'name'
git config --global user.email 'email address'
git config --global color.ui auto
git config --global push.default upstream
git config --global merge.conflictstyle diff3
```

## Configure editor

```sh
git config --global core.editor "'C:/Program Files/Sublime Text 3/sublime_text.exe' -n -w"
```
## Files

Baixar os arquivos `.bash_profile` `git-completion.bash` `git-prompt.sh` e colar na pasta raiz de usuário em `C:\Users\user_name`

## Shortcut to Sublime

Abrir arquivo `.bash_profile` e adicionar a linha abaixo. 

*`alias subl="'C:/Program Files/Sublime Text 3/sublime_text.exe'"`*

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

## Add-on

Há um [plugin](https://packagecontrol.io/installation#st3) que você pode baixar e usar para visualizar arquivos de markdown no computador.

## Initial Config

```sh
git init
git remote add origin 'link do repositório no github'
git add .
git commit -m "Initial files"
git push -u origin master
```

## Main Comands

```sh
git init
git clone
git status

git log
git log --oneline
git stat
git log -p
git show SHA

git add file1 file2 fileN
git commit
git commit -m # short message
git commit --amend    # modifica o ultimo commit

git reset file # unstage arquivo
git checkout -- file # desfaz alterações no arquivo
git checkout HEAD~1 # aponta para o último commit

git reset # apaga um commit e mantém alterações
git reset --hard # apaga um commit e desfaz alterações
git reset HEAD~1 # apaga um commit e mantém alterações
git reset --hard HEAD~1 # apaga um commit e desfaz alterações

git revert SHA # desfaz um determinado commit

git rm file # remove arquivo do commit e diretório
git rm --cached file # remove arquivo do commit e mantém no diretório
 
git diff

git tag # exibe as tags
git tag -a nome # cria a tag 
git tag -d nome # deleta a tag

git branch # cria uma branch
git branch -d nome # deleta um branch
git branch sidebar SHA # cria um branch de outro branch
git ceckout nome
git merge --no-ff nome

git remote add origin link
git push origin master
git pull
```

## Git branching model

<p align="center">
<img src="https://user-images.githubusercontent.com/9321996/88289855-41f21400-cccc-11ea-910a-7405624c3545.png" width="60%">
</p>

Author: Vincent Driessen
Original blog post: http://nvie.com/posts/a-successful-git-branching-model
License: Creative Commons BY-SA
