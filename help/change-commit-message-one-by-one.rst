.. <title>
   <author>
   <date>
=======================
コミットメッセージの変更
=======================

.. contents::
   :depth: 1
   :local:

コミットメッセージに不明確、不正確、または機密情報が含まれている場合、ローカルでメッセージを修正して、GitHubに新しいメッセージで新しいコミットをプッシュできます。 また、コミットメッセージを変更して、不足している情報を追加することも可能です。

直近のコミットメッセージの書き換え
==============================

``git commit --amend``コマンドで、直近のコミットメッセージを変更できます。
Gitでは、コミットメッセージのテキストはコミットの一部として扱われます。コミットメッセージを変更すると、コミットID(コミットのSHA1チェックサム)も変更されます。
実質的には古いコミットに変わる新しいコミットを作成することになります。

オンラインにプッシュされていないコミット
=====================================

コミットがローカルリポジトリにのみ存在し、GitHub.comにプッシュされていない場合、``git commit --amend``コマンドでコミットメッセージを修正できます。

#. コマンドラインで、修正したいコミットのあるリポジトリに移動します。
#. ``git commit --amend``と入力して**Enter**を押します。
#. テキストエディタでコミットメッセージを編集し、コミットを保存します。

次回のプッシュ時に、GitHub.comに新たなコミットとメッセージが表示されます。

古い、又は複数のコミットメッセージの修正
=======================================

直近でプッシュされたコミットのメッセージを変更する
---------------------------------------------
1. 上記の手順に従って、コミットメッセージを修正する。

2. `` push --force-with-lease``コマンドにより、古いコミットをフォースプッシュで上書きします。

   ::
   
      $ git push --force-with-lease origin EXAMPLE-BRANCH


古い、又は複数のコミットメッセージを変更する。
----------------------------------------------
複数のコミット、又は古いコミットのメッセージを修正する必要がある場合は、インタラクティブなリベースを利用した後にフォースプッシュして、コミットの履歴を変更できます。

1. コマンドラインで、修正したいコミットのあるリポジトリに移動します。
2. `` git rebase -i HEAD~n``コマンドで、デフォルトのエディタに直近の`` n``コミットの一覧を表示できます。
   ::
      # Displays a list of the last 3 commits on the current branch
      $ git rebase -i HEAD~3
   
   リストは以下のようになります。
   ::
      pick e499d89 Delete CNAME
      pick 0c39034 Better README
      pick f7fde4a Change the commit message but push the same commit.

      # Rebase 9fdb3bd..f7fde4a onto 9fdb3bd
      #
      # Commands:
      # p, pick = use commit
      # r, reword = use commit, but edit the commit message
      # e, edit = use commit, but stop for amending
      # s, squash = use commit, but meld into previous commit
      # f, fixup = like "squash", but discard this commit's log message
      # x, exec = run command (the rest of the line) using shell
      #
      # These lines can be re-ordered; they are executed from top to bottom.
      #
      # If you remove a line here THAT COMMIT WILL BE LOST.
      #
      # However, if you remove everything, the rebase will be aborted.
      #
      # Note that empty commits are commented out

3. 各コミットメッセージを変更する前に、`` pick``を`` reword``に置換して下さい。
   ::
      pick e499d89 Delete CNAME
      reword 0c39034 Better README
      reword f7fde4a Change the commit message but push the same commit.

4. コミット一覧のファイルを保存して閉じます。
5. 生成された各コミットファイルに、新しいコミットメッセージを入力し、ファイルを保存して閉じます。
6. 変更をGithubにプッシュする準備ができたら、`` push --force``コマンドを使用して、古いコミットを強制的にプッシュします。
   ::
      $ git push --force origin EXAMPLE-BRANCH

留意
====

この方法でも、コミットメッセージを修正すると、IDが新しい新たなコミットメッセージが作成されます。
ただし、この方法では、修正したコミットに続く各コミットも新しいIDを取得します。
各コミットには親のIDが含まれているためです。

参考
========

`コミットメッセージの変更 - GitHub Docs <https://docs.github.com/ja/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/changing-a-commit-message>`_

