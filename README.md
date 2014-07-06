サブモジュールの作り方。

➜  TestRepository git:(master) git submodule add git@github.com:suakig/Sub.git
Cloning into 'Sub'...
remote: Reusing existing pack: 4, done.
remote: Counting objects: 3, done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 7 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (7/7), done.
Checking connectivity... done.

設定ファイル                .gitmodules
サブモジュールディレクトリ   Sub 
が作成される
➜  TestRepository git:(master) ✗ git status
On branch master
Your branch is up-to-date with 'origin/master'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    new file:   .gitmodules
    new file:   Sub 

.gitmodulesの中身にはサブモジュールへのパスが書いてある
➜  TestRepository git:(master) ✗ cat .gitmodules
[submodule "Sub"]
    path = Sub 
    url = git@github.com:suakig/Sub.git




Subモジュールが更新した場合、addして更新したバージョンにあわせる必要がありる。
 ➜  TestRepository git:(master) ✗ git status
 On branch master
 Your branch is up-to-date with 'origin/master'.
 
 Changes not staged for commit:
   (use "git add <file>..." to update what will be committed)
   (use "git checkout -- <file>..." to discard changes in working directory)
   
     modified:   Sub (new commits)
     
 no changes added to commit (use "git add" and/or "git commit -a")
 ➜  TestRepository git:(master) ✗ git diff 
 
 diff --git a/Sub b/Sub
 index ce1cca0..2878983 160000
 --- a/Sub
 +++ b/Sub
 @@ -1 +1 @@
 -Subproject commit ce1cca0d1d5e7fcb13202b92c599234ebd94cd55
 +Subproject commit 287898303655f2d2acde68b27545fdc3dd32e6b6
