## Atualizar dados


Verificar configurações gerais.

```
$ git config --list
```

Para trocar o login
```
$ git config --global user.name "seu usuário"
```

Para trocar o e-mail

```
$ git config --global user.email seuemail@example.com
```

Para salvar senhas: 

1. `$ git config --global credential.helper store`
2. `$ git push -u origin seu-branch`

---
## HEAD

Remover todos os arquivos que foram `add` no HEAD

```
$ git reset HEAD  
```

Para retirar o arquivo `file.txt` do HEAD

```
$ git reset HEAD file.txt 
```

---
## COMMIT

### Cancelar um commit local.

windows
```
$ git reset --soft HEAD~
```

Linux, Mac
```
$ git reset --soft HEAD^
```
### Adicionar Arquivos ao commit atual
```
$ git add seu-arquivo
$ git commit --amend --no-edit
```
---
## ATUALIZAR

Para atualizar seu repositório local com a mais nova versão

```
$ git pull 
```

Adiciona o git repositório

```
$ git remote add upstream repositorio.git 
```

### Para mover commits para outro branch

O exemplo abaixo move os três últimos commits para newbranch

```
$ git branch newbranch
$ git reset --hard HEAD~3
$ git checkout newbranch
```
O exemplo abaixo move o commit C para o branch master, onde C é o hash do commit.

```
git checkout master
git merge C
```


---
## TAG

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

---
## Diff

Compara dois branchs

```
$ git diff branch_1..branch_2
```

---
## Remote

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

---
## Merge


Caso esteja no `master`  irá unir todos os arquivos do `1-correcao-bug-menu`

```
$ git merge 1-correcao-bug-menu
```

---
## BRANCH

Mostra todos os branchs do local. Acrescente `-v` e veja com commits

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

---
## Rebase

Apesar do agrupamento por finalidade ser melhor do que o agrupamento por autor,
há como aumentar ainda mais a legibilidade do histórico, usando a opção
`--no-ff` na hora de fazer o Merge:

```
$ git checkout feature/do-something
$ git rebase master
$ git checkout master
$ git merge --no-ff feature/do-something
```

---
## Conflito

Resolvendo conflitos de códigos

```
$ git checkout -b branch
$ git checkout  master
$ git pull origin master
$ git checkout branch
$ git merge master

```
---
## Deu Merda

Quando fez a besteira de alterar arquivos no branch errado

```
$ git stash
$ git stash branch temporario
$ git checkout -b nova-consulta
$ git merge --no-ff temporario
$ git branch -d temporario
```

---
## PLUS


Exibe os commits em um painel visual

```
$ gitk
```

`git log` de forma resumida

```
$ git log --oneline 
```