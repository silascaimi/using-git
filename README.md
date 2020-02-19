# Using-git

Default settings and files I use in git to use it with Sublime Text editor.

## Configure tooling

```sh
git config --global user.name "[name]"
git config --global user.email "[email address]"
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

## Add-on

Há um [plugin][packagecontrol] que você pode baixar e usar para visualizar arquivos de markdown no computador.

## Initial Config

```sh
git init
git remote add origin '[link do repositório no github]'
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
git show <SHA>

git add <fil1> <file2> <fileN>
git commit
git commit -m # short message
git commit --amend # modifica o ultimo commit
git revert <SHA> # modifica o commit commit
git reset # apaga um commit

git diff

git rm --cached <file> # to unstage the commit

git tag # exibe as tags
git tag -a <nome> # cria a tag 
git tag -d <nome> # deleta a tag
git branch
git branch -d <name> # deleta um branch
git branch sidebar <SHA> # cria um branch de outro branch
git ceckout <nome>
git merge

git remote add origin <link>
git push origin master
git pull
```

[packagecontrol]:<https://packagecontrol.io/installation#st3>
