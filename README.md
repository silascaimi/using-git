# setting-git

Default settings and files I use in git to use it with Sublime Text editor.

## Configure tooling

```sh
$ git config --global user.name "[name]"
$ git config --global user.email "[email address]"
$ git config --global color.ui auto
$ git config --global push.default upstream
$ git config --global merge.conflictstyle diff3
```

## Configure editor

```sh
$ git config --global core.editor "'C:/Program\ Files/Sublime\ Text\ 3/sublime_text.exe' -n -w"
```

* Baixar os arquivos `.bash_profile` `git-completion.bash` `git-prompt.sh` e colar na pasta raiz de usuário em `C:\Users\user_name`

* Abrir arquivo `.bash_profile` e adicionar a linha abaixo. 

*`alias subl="C:/Program\ Files/Sublime\ Text\ 3/sublime_text.exe"`*

Isto permitirá utilizar o atalho `subl` para abrir arquivos e incluir as mensagens de commit com o Sublime Text com o comando simples de commit

```
$ subl nome_do_arquivo
$ git commit
```

Há um [plugin][packagecontrol] que você pode baixar e usar para visualizar arquivos de markdown no computador.

[packagecontrol]:<https://packagecontrol.io/installation#st3>
