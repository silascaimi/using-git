# setting-git

Default settings and files I use in git to use it with Sublime Text editor

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

* Abrir arquivo `.bash_profile` e adicionar a linha abaixo

*`alias subl="C:/Program\ Files/Sublime\ Text\ 3/sublime_text.exe"`*

