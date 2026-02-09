Git
===

## Install

https://git-scm.com/install/mac

## Setup

### Global user

```
git config --global user.name 'xxxx'
git config --global user.email 'xxxxxx@example.com'

git config --global -l
```

### Change default branch name

```
git config --global init.defaultBranch main
```

### Color setting

```
git config --global color.ui auto
```

### Use uppercase and lowercase as different file names

```
git config --global core.ignorecase false
```

### Global gitignore

@ ~/.config/git/ignore

```
Thumbs.db
.DS_Store
.env
.env.*
node_modules/
```

---

## Commands

### Clone repository
```git clone https://github.com/xxxx/xxxx.git```

### Push
```
git add --all
git commit -m "Comment"
git push
```

### Pull
```git pull origin main```

### Restore working tree files
```
git checkout HEAD .
git checkout .
```
### Revert some existing commits
```git revert <commit>```

### List branches
```git branch```

### Create a new bran
```
git branch <branch name>
  or
git checkout main
git checkout -b <branch name>
```

### Change branch
```git checkout <branch name>```

### Delete branch
```git checkout -d <branch name>```

### Merge
```
git checkout main
git merge develop
```

#### __Ex__
```
git add --all
git commit -m "modified"
git push -u origin develop
git checkout main1
git merge develop
git push -u origin main
git checkout develop
git branch
```

## Rebase
```
git checkout main
git pull origin main
git checkout hoge
git rebase main

git add 〜
git rebase --continue

git push -f origin hoge
```

1. rebaseしたいブランチを最新にする
2. 作業ブランチに戻る
3. rebaseする (git branch で確認すると一時的なブランチにいる)
4. コンフリクトが発生したら解決する
5. リモートのoriginと相違している状態になったためpushしようとするとエラーになるので、-fで強制的にpushする
