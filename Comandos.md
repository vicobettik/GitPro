# Comandos

### Inicializar un proyecto de git

`git init`

### agrega archivos para seguimiento

`git add *.md`
`git add Comandos.md`

### Estatus de los archivos en git

![Estatus de los archivos en git](https://git-scm.com/book/en/v2/images/lifecycle.png)

### Revisar el estatus de los archivos

```bash
git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean

```

agregar un archivo README.md

```bash
git status
On branch master
Your branch is up-to-date with 'origin/master'.
Untracked files:
  (use "git add <file>..." to include in what will be committed)
  README
nothing added to commit but untracked files present (use "git add" to track)

```

#### Comenzar a rastrear nuevos archivos (incluirlos en la foto)

`git add README`

```bash

$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
29
  (use "git restore --staged <file>..." to unstage)
  new file: README

```

agregar un archivo README.md

```bash

$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)
  new file: README
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)
  modified: CONTRIBUTING.md


```

agregar el archivo CONTRIBUTING a trackeo y commit

```bash

$ git add CONTRIBUTING.md
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)
  new file: README
30
  modified: CONTRIBUTING.md

```

#### Comenzar a rastrear nuevos archivos (incluirlos en la foto)

```bash

$ git status -s
$ git status --short

M README
MM Rakefile
A lib/git.rb
M lib/simplegit.rb
?? LICENSE.txt

```

M - modificado
A - agregado
?? - sin trackeo

MM - primera columna en stage, segunda fuera del stage

### Remover un archivo del trackeo

```bash

F
```