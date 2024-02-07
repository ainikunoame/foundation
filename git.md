# git

## 

### commit massage

| 先頭   | 意味       | 
| ------ | ---------- | 
| Add    | 追加       | 
| Fix    | 問題の修正 | 
| Edit   | 編集       | 
| Update | 更新       | 
| Remove | 削除、除去 | 
| Rename | 名前の変更 | 
| Use    | 使用       | 
| Make   | 作成、改良 | 
| Change | 変更       | 
| Avoid  | 回避       | 
| Allow  | 許可       | 
| Don't  | 否定       | 

|command|説明|
|:----|:----|
|git init|current directoryにgit repositoryを作成する。git repositoryを初期化する。|
|git status|作業directoryとステージングエリア上のfileの状態を表示する|
|git add ファイル名|変更済みのファイルをステージングエリアに追加する|
|git commit|ステージ済みのファイルのスナップショットをgit repository保存する。コミットメッセージはエディタで入力する。|
|git commit -m "massage"|コミットメッセージをインラインで指定する|
|git commit -amend|直前のcommitをやり直す|
|git commit --amend --no-edit|コミットメッセージをインラインで指定する変更せずに直前のコミットをやり直す|
|git log|コミットの履歴を表示する|
|git log -p|git logの項目を表示しつつ、コミットの変更点も表示する。|
|git log --oneline --decorate|commitの履歴を見やすく表示する|
|git branch|branchの一覧を表示する|
|git branch ブランチ名|branchを新規作成する|
|git checkout 切替先ブランチ名|ブランチの切り替えを行う|
|git checkout -b ブランチ名|ブランチを作成、切り替えを同時に行う|
|git checkout -- ファイル名|特定のファイルのステージされていない変更を取り消す|
|git merge マージ元のブランチ名|ファイルのmergeを実行する|
|git branch -d ブランチ名|branchを新規作成する削除する|
|git --version|gitのversion確認|
|git config --global user.name "ユーザー名"|ユーザー名の設定|
|git config --global user.email "メールアドレス"|メールアドレスの設定|
|git config --list|設定値の確認|
|git reset --soft コミット|指定したコマンドまでHEADを移動する|
|git reset (--mixed)  コミット|--softに加えステージングエリアを指定コミット時の状態と一致させる|
|git reset --hard コミット|--mixedに加え作業ディレクトリを指定コミット時の状態と一致させる|
|git コマンド -h|指定コマンドのヘルプ|
|git remote -v|登録済みのremote repositoryの「リモート名」「リポジトリURL」を表示する|
|git remote add リモート名 リポジトリURL|remote repositoryを登録する。|
|git push リモート名　ブランチ名|local repositoryの内容をremote repositoryに反映する|
|git clone リポジトリURL|リポジトリURLに存在するリモートリポジトリをlocalに複製する|
|git pull リモート名 ブランチ名|remote repositoryの内容をlocal repositoryに反映する|
