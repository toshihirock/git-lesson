git-lesson
==========

lesson git command

`git clone`
`git add`
`git commit`
`git status`
`git push`
`git pull`

1. Githubでリポジトリ作成
1. git cloneしてみる
1. git add, git commitしてみる
1. git pushでリモートサーバーに情報をpushしてみよう
1. git pullで変更した内容を取得しよう
1. 同じファイルを編集していた場合
1. Tips
1. 使いそうなコマンド


# 1.Githubでリポジトリ作成

+ Githubにログイン
+ 画面右上の「+」を押して、　**New repository** を選択
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
+ git管理に含めない設定は **.gitignore** を作成し、除外ファイルを指定できる。正規表現が指定可能。.gitignoreファイルを配置したディレクトリ及びそのサブディレクトリも有効。

# 8.よく使うコマンド

各コマンドのhelp

    $git help <command>

gitの設定を確認

    $git config -l

commitの確認

    $git log

直前のcommitを取り消してHEADの一つ前に戻る

    $git reset --hard HEAD^

特定のバージョンに戻る。fugaはgit logで確認

    $git reset --hard fuga

ステージングからの削除、移動

    $git rm hoge
    $git mv hoge fuga

ステージングの変更を取り消し

    $git checkout hoge.txt

ブランチの変更。hogeブランチに変更

    $git branch hoge
    
タグ付け。hogeという名前のタグをHEADに付ける

    $git tag hoge
