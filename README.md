git-lesson
==========

lesson git command

`git clone`
`git add`
`git commit -m`
`git status`
`git push origin master`
`git pull`

1. Githubでリポジトリ作成
2. git cloneしてみる
3. git add, git commitしてみる
5. git pushでリモートサーバーに情報をpushしてみよう
6. git pullで変更した内容を取得しよう

# 1.Githubでリポジトリ作成

+ Githubにログイン
+ 画面右上の「＋」を押して、　**New repository** を選択
+ 適当に設定して **create repository** を選択。なお、 **Initialize this repository with a README**  についてはチェックを入れておき、READMEファイルを作成すること。
 
# 2.git cloneしてみる

+ Githubのページでリポジトリが作成できているはずなのでリポジトリ画面を表示し、画面右下の **HTTPS clone URL** の値をコピペ
+ gitコマンドが使える場所で以下のように打ち込む

`$git clone <repository_name>`

とするとローカルにファイルが作成されているはず。

# 3.git add,git commitしてみる

ファイルを編集

    $cd <repository_name>
    $vi README.md
    (編集)
    $git status
    $git add README.md
    $git status
    $git commit -m "mofify README"
    $git status
    
ファイルを追加

    $touch abc.txt
    $mdkri dir
    $touch dir/bcd.txt
    $git status
    $git add .
    $git status
    $git commit
    $git status
    
# 4.git pushでリモートリポジトリに情報をpushしてみよう

    $git branch
    $git remote -v
    $git push origin master

上記コマンドのoriginは **pushするサーバー** であり、masterは **branch名** となる。

Githubにアクセスし、リポジトリを確認する。

# 5.git pullで変更した内容を取得しよう

Githubにアクセスし、READMEを編集する。

    $git pull

ブラウザで変更した内容がローカルでも確認できること。

# 6.同じファイルを編集していた場合

+ 単純に追加したとかであればgitで良い感じにマージしてくれる
+ 競合している場合にはファイルを編集してその後、pushすれば良い

# 7.Tips

+ Cygwinでは git-completion パッケージをインストールするとgitのコマンド補完をしてくれる
+ PS1 変数をいじるとプロンプトにブランチ名が表示されるので良い
+ git-creadentialsを使うとHTTP認証の入力を1回のみで良い
