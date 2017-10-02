# Git Step by Step

## git config

```sh=
$ git config --global user.name 'Name Surname'
$ git config --global user.email 'name@example.com'
```

## create directory

```sh=
$ mkdir begin
$ cd begin 
$ git init 
Initialized empty Git repository in ~/begin/.git/
```

## create file begin.txt

```sh=
$ echo 'let begin' > begin.txt
$ cat begin.txt
let begin
```

## Git add file to git

```sh=
$ git add begin.txt
warning: LF will be replaced by CRLF in begin.txt.
The file will have its original line endings in your working directory.
```

## Git Check status

```sh=
$ git status
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   begin.txt
```

## Git commit 

```sh=
$ git commit -m 'add begin'
[master (root-commit) efde6e4] edit file
warning: LF will be replaced by CRLF in begin.txt.
```

## Check status add

```sh=
$ git status
On branch master
nothing to commit, working directory clean
```

## Git edit and new file

```sh=
$ echo 'line second' >> begin.txt
$ echo 'git md' > README.md
$ echo 'test' > test.md
```

## Git check status

```sh=
$ git status

On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   begin.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        README.md
        test.md

no changes added to commit (use "git add" and/or "git commit -a")
```

## Git add file new and checkus

```sh=
$ git add begin.txt RAEDME.md test.md
$ git status
warning: LF will be replaced by CRLF in begin.txt.
The file will have its original line endings in your working directory.
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   README.md
        modified:   begin.txt
        new file:   test.md

```

## Git commit file

```sh=
$ git commit -m 'edit file and add'
The file will have its original line endings in your working directory.
 3 files changed, 3 insertions(+)
 create mode 100644 README.md
 create mode 100644 test.md
```

## Git edit file and remove file and commit

### edit text 'test' to README.md

README.md
```sh=
git md
test
```

### remove test.md
```sh=
$ git rm test.md
rm 'test.md'
```

### add file check status
```sh=
$ git add README.md
warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory.
```

### check status
```sh=
$ git status
warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory.
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   README.md
        deleted:    test.md
```

### commit
```sh=
$ git commit -m 'edit and delete'
[master warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory.
817cdb7] edit and delete
warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory.
 2 files changed, 2 insertions(+), 1 deletion(-)
 delete mode 100644 test.md

```


## Branch

### Create Branch

```sh=
$ git branch hophop
```

### Check Branch

```sh=
$ git branch
  hophop
* master
```

### Switch to branch hophop

```sh=
$ git checkout hophop
Switched to branch 'hophop'
```

### Edit file and add new

```sh=
$ echo 'testt' >> begin.txt
$ echo 'dev' >> def.txt
```

### Check status new

```sh=
$ git status

On branch hophop
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   begin.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        def.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

### Clean file git

```sh=
$ git clean -f
Removing def.txt
```

### Commit file commit `auto`

'-a' is add file auto 
```sh=
$git commit -am 'update file'
```

### Delete branch 

```sh=
$ git checkout master
Switched to branch 'master'
$ git branch hophop -D
Deleted branch hophop (was 0aa8bda).
```

## Merge

### Create New Branch and switch branch

```sh=
$ git checkout -b hiphip
Switched to new branch 'hiphip'
```

### edit begin.txt
```sh=
$ echo 'hip' >> begin.txt
```

### Add and commit 
```sh=
$ git commit -am 'add file'

warning: LF will be replaced by CRLF in begin.txt.
The file will have its original line endings in your working directory.
[hiphip warning: LF will be replaced by CRLF in begin.txt.
The file will have its original line endings in your working directory.
3979e8a] add file
warning: LF will be replaced by CRLF in begin.txt.
The file will have its original line endings in your working directory.
 1 file changed, 1 insertion(+)
```

### Switch to master

```sh=
$ git checkout master
Switched to branch 'master'
```

### Merge File 

```sh=
$ git merge hiphip
Updating 817cdb7..3979e8a
Fast-forward
 begin.txt | 1 +
 1 file changed, 1 insertion(+)
```

### Delte branch hiphip '-d' is check branch has merge

```sh=
$ git branch hiphip -d
Deleted branch hiphip (was 3979e8a).
```

## Multi Merge

```sh=
$ git checkout -b hithit
Switched to a new branch 'hithit'
```

### edit file begin.txt again
```sh=
$ echo 'hithit add' >> begin.txt
```

### commit new begin.txt in hithit branch
```sh=
$ git commit -am 'add hithit -h help'

warning: LF will be replaced by CRLF in begin.txt.
The file will have its original line endings in your working directory.
[hithit warning: LF will be replaced by CRLF in begin.txt.
The file will have its original line endings in your working directory.
c6ccdc2] add hithit -h help
warning: LF will be replaced by CRLF in begin.txt.
The file will have its original line endings in your working directory.
 1 file changed, 1 insertion(+)

```

### checkout master and new branch hishis
```sh=
$ git checkout master
Switched to branch 'master'

$ git checkout -b hishis
Switched to a new branch 'hishis'

$ echo 'hishis add' >> begin.txt

$ git commit -am 'add hishis'

warning: LF will be replaced by CRLF in begin.txt.
The file will have its original line endings in your working directory.
[hishis warning: LF will be replaced by CRLF in begin.txt.
The file will have its original line endings in your working directory.
f2232d6] add hishis
warning: LF will be replaced by CRLF in begin.txt.
The file will have its original line endings in your working directory.
 1 file changed, 1 insertion(+)
```

### Switch master 
```sh=
$ git checkout master
Switched to branch 'master'
```

### Diff branch hishis and master
```sh=
$ git diff master hishis

diff --git a/begin.txt b/begin.txt
index ef8f0f2..f8bb1da 100644
--- a/begin.txt
+++ b/begin.txt
@@ -2,3 +2,4 @@ let begin

 line second
 hip
+hishis add
```

### merge branch 

```sh=
$ git merge hishis hithit

$ git commit -am 'updater after merge'

$ git branch --no-merged
$ git branch --merged
* master
  hishis
  hithit
```

### delete branch 
```sh=
$ git branch hishis hithit -d
Deleted branch hishis (was f2232d6).
Deleted branch hithit (was c6ccdc2).
```



