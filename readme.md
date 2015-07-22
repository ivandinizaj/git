## Atualizar dados


### Caso deseje substituir o login
```
$ git congig --global user.name "seu usuário"
```

### Caso deseje substituir o e-mail

```
$ git congig --global user.email seuemail@example.com
```

##HEAD

Remover todos os arquivos que foram `add` no HEAD

```
$ git reset HEAD  
```

Para retirar o arquivo `file.txt` do HEAD

```
$ git reset HEAD file.txt 
```

## Atualizar

Para atualizar seu repositório local com a mais nova versão

```
$ git pull 
```

Adiciona o git repositorio

```
$ git remote add upstream repositorio.git 
````


##Tag

Criar tag Anotada

```
$ git tag -a v1.4 -m 'my version 1.4'
```

Deletar tag (legal apenas quando não tiver publicado)

```
$ git tag -d v1
```

Subir tag para repositório

```
$ git push origin v1.5
```

##Diff

Compara dois branchs

```
$ git diff branch_1..branch_2
```

##Remote

Alterar repositório

```
$ git remote set-url origin http://repositorio
```

Visualizar repositório atual

```
$ git remote -v
```

Atualizar com **repositório** com o branch que escolher

```
$ git pull origin master
```


##Merge


Caso esteja no `master`  irá unir todos os arquivos do `1-correcao-bug-menu`

```
$ git merge 1-correcao-bug-menu
```

## Branch

Mostra todos os branchs do local

```
$ git branch 
```

Remover branch local

```
$ git branch -d name-branch
```

Mostra todos os branchs do repositório. Acrescente `-v` e veja com commits

```
$ git branch -r

```

Excluir um branch no **repositório**

```
$ git push origin :branch 
```


## Plus

Mostra a parte  visual do GIT

```
$ gitk
```

`git log` de forma resumida

```
$ git log --oneline 
```

## Deu Merda

Quando fez a merda de alterar arquivos em um branch errado

```
$ git stash
$ git stash branch temporario
$ git checkout nova-consulta
$ git merge --no-ff temporario
$ git branch -d temporario
```