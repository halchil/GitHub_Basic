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

git clone https://github.com/halchil/GitHub_Basic.git
Cloning into 'GitHub_Basic'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (3/3), done.

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

