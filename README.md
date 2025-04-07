# GitHub_Basic

#事前準備

```
[実行コマンド]
git config --list

[結果]
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/etc/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=false
pull.rebase=false
credential.helper=manager
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master
user.name=halchil
user.email=halzcreate1215@gmail.com
```

クローン
```
git clone https://github.com/halchil/GitHub_Basic.git
Cloning into 'GitHub_Basic'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (3/3), done.
```

ローカルでcloneした時

```
git clone https://github.com/ユーザー名/awesome-project.git

このときGitは勝手にこう設定されてる↓
設定	内容
リモート名	origin（Gitが自動で命名）
リモートブランチ	origin/main（GitHubのmainブランチ）
ローカルブランチ	main（クローン時にチェックアウトされてる）
```

# Commit CLI

## 1. サーバでリポジトリを初期化する

サーバ内でリポジトリにしたいディレクトリに移動する。

```
$ cd /path/to/your/files
```
次にGitリポジトリを初期化する。
```
[実行コマンド]
git init

[結果]
Reinitialized existing Git repository in C:/Users/halzc/OneDrive/デスクトップ/GitHub_Basic/.git/
```

文ランチを切る
```
[実行コマンド]
git checkout -b feature/test-branch

[結果]
Switched to a new branch 'feature/test-branch'

[確認コマンド]
git branch

[結果]
* feature/test-branch
  list
  main

[確認コマンド]
git checkout main

[結果]
M       README.md
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

[確認コマンド]
git branch       

[結果]
  feature/test-branch
  list
* main


```


次に変更ステージングする

```
[実行コマンド]
git add . 

[結果]
何も表示されない
```

次に、コミットする。

```
[実行コマンド]
git commit -m "firtst commit"

[結果]
[main 20b1156] firtst commit
 1 file changed, 102 insertions(+), 1 deletion(-)
```

次に、リモートリポジトリへ変更をプッシュする。
コマンドは以下となる。
```
git push [リモートリポジトリ名(デフォルトでorigin)] [ローカルブランチ名]
```


```
[実行コマンド]
git push origin feature/test-branch

[結果]

```

pushする前のイメージは以下である。

```
ローカルPC
└── main ブランチ（変更済み）

GitHub（origin）
└── main ブランチ（まだ古い状態）
```

pushするとこうなる

```
ローカルPC
└── main ブランチ（最新）

GitHub（origin）
└── main ブランチ（最新に更新された！）
```




# TroubleShoot

## 

```
[実行コマンド]
git commit -m "firtst commit"     

[結果]
On branch feature/test-branch
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        img/

no changes added to commit (use "git add" and/or "git commit -a")

```



## 

```

git push origin future/test-branch
error: src refspec future/test-branch does not match any
error: failed to push some refs to 'https://github.com/halchil/GitHub_Basic.git'


```
これは「ブランチ名のタイプミス」か「コミットしてないからpushできない」どっちかが原因。




## 2. GitHubリポジトリをリモートに設定する


GitHubのリポジトリURLをコピーする。
例: `https://github.com/username/my-repo.git`

そのURLを使ってリモートリポジトリを設定する。

```
$ git remote add origin https://github.com/username/my-repo.git
```

## 3. ファイルをステージングしてコミットする

リポジトリ内のファイルをすべてステージングする。

```
$ git add .
```
ファイルをコミットする。

```
$ git commit -m "Initial commit"
```

## 4. GitHubにファイルをプッシュする

リポジトリの内容をGitHubにプッシュする。
```
$ git branch -M main
```
表示
```
$ git branch
```
変更

```
$ git checkout test-branch
```
-M オプションは、ブランチの名前を強制的に変更するためのもの

```
$ git push -u origin test-branch



# Commit VSCode

