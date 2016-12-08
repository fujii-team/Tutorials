# 概要
以下の手順で環境を構築する。

+ Anacondaのインストール
+ SmartGit の導入
+ GitHubアカウントの作成
+ Gitでのファイル管理

基本的にUbuntu OSでの作業を想定している。

# Anaconda のインストール

(Anaconda)[https://www.continuum.io/downloads#_unix]
にアクセスし、 **PYTHON 3.5 64bit** をダウンロードする。

<img src=prep/Anaconda_download.png width=480pt>


homeディレクトリにAnaconda2ディレクトリを作成

`mkdir ~/Anaconda2`

`mv [Anaconda2のパス] ~/Anaconda2/`

`bash ~/Anaconda2/Anaconda2-4.0.0-Linux-x86_64.sh`

ページの指示に沿ってインストールを行う。

**最後にパスを追加するか聞かれるので Yes を選択する**


# SmartGitのダウンロード

プログラムコードのバージョン管理・共有は **(Git)[https://ja.wikipedia.org/wiki/Git]**
で行なうほうがよい。

少し難しいシステムなので、

http://koseki.hatenablog.com/entry/2014/04/22/inside-git-1

http://www.find-job.net/startup/7-git-slides

など、仕組みや使い方を調べておくこと。

**git** は基本的にコマンドラインで実行するソフトウェアだが、直感的でないので、
GUIアプリケーションであるSmartGitを導入する。


http://www.syntevo.com/smartgit/download

からSmartGitをダウンロードする。

<img src=prep/SmartGit_download.png width=480pt>

## 解凍

Linux で圧縮ファイルを解答するには、以下を実行する。

`tar -xvf Download/smartgit-linux-7_1_2.tar.gz`

<img src=prep/SmartGit_unzip.png width=480pt>



# GitHubアカウントの作成

GitHubは、Gitシステムで管理されたファイルを共有するためのウェブサービスである。

https://github.com/

に従ってアカウントを作成する。


# 作業ディレクトリの作成
ホームディレクトリに適当なフォルダ(study/python/tutorials　など)を作成

`cd ~/`  
`mkdir -p study/python/tutorials`

# Gitでのファイル管理
## チュートリアル リポジトリのClone
**clone** は **リモート** (この場合はGitHub)にあるファイルセット（リポジトリと呼ぶ）を
**ローカル** （各自のコンピュータ）に新規にコピーする作業である。

SmartGitを起動し、右上のRepository > **clone** を選択する。

<img src=prep/SmartGit_clone.png width=480pt>  

<img src=prep/SmartGit_directory.png width=480pt>


## 作業Branchの作成

**Branch** とは、ファイルを更新する作業単位である。
同じファイルを複数人で変更すると後々問題が出てくる可能性があるので、
基本的に各作業は各自のブランチで行なう。

それらの修正を最後に **master** ブランチにマージすることで、ひとつのソフトウェアを作り上げていく。

SmartGit 上のメニューから Branch > Add Branch を選択する。
各自の名前などブランチ名として入力し、Add Branch & Checkout を実行する。

<img src=prep/SmartGit_add_branch.png width=480pt>

左下のBranchesの枠内に、作ったブランチが表示され、かつそれが選択されていれば（Checkoutされていれば）OK

<img src=prep/SmartGit_branch.png width=480pt>


## Commit

ファイルを更新していき一段落すると、チェックポイントを作成する。
その作業を **commit** と呼ぶ。

その後ファイルを変更していっても、いつでもそのcommit時のファイルに戻すことができる。

適当なコメントを入力し、Commitを実行する。
これにより、履歴データをGitファイルとして保存できる。

## Push

**push** は、ローカルのファイルをリモートにアップロードする作業である。

基本的には課題の提出や、ソースコードの共有野ために行なう。

SmartGit右上の Push をクリックする

<img src=prep/SmartGit_push.png width=480pt>


右下のOutputウィンドウ内に、エラーメッセージがでなければOK

GitHub ページにに行って、自分のBranchが作成されていることを確認する。



<img src=prep/Github_branch.png width=480pt>

作業は基本的に、自分のブランチで行う。
他人のブランチには触らない。
Masterブランチは、余程のことがない限り触らない。
