# Alterar Commits na Origin

As vezes acontece de após realizar um commit, perceber que deveria ter feito mais alterações, ou que o commit deveria ser dividido em mais de um, sendo necessário alterar o histórico de commits.

## Alterar o último commit usando amend

Para alterar o último commit, basta realizar as alterações necessárias e em seguida executar o comando `git commit --amend`. Isso irá abrir o editor de texto padrão do git, onde você poderá alterar a mensagem do commit, e em seguida salvar e fechar o editor.

```bash
git commit --amend
```

---

_E se houver mais de um commit?_

## Alterar commits anteriores usando rebase

Para alterar commits anteriores, você pode utilizar o comando `git rebase -i HEAD~n`, onde `n` é o número de commits que deseja alterar. Isso irá abrir um editor de texto com uma lista dos commits que você deseja alterar. Basta alterar a palavra `pick` para `edit` no commit que deseja alterar, salvar e fechar o editor.

```bash
git rebase -i HEAD~n
git rebase --interactive HEAD~n
```

Após isso o git irá parar no commit que você deseja alterar, e você poderá realizar as alterações necessárias com o comando `git commit --amend`. Em seguida, execute o comando `git rebase --continue` para continuar o rebase.

---

_o camando `git rebase -i HEAD~n` permite que você altere a ordem dos commits, exclua commits, ou até mesmo juntar commits._

## Capacidades do `rebase -i`

```bash
# Commands:
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
```
