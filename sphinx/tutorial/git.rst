.. _git:

=========
Using git
=========

Git is a useful version-control tool that uses distributed version-control system (DVCS) 
which can be used to track changes in source codes during software development.

::

 $ man git

or

::

 $ git --help

----

1. git configuration
--------------------

::

 $ git config --global user.name "user"
 $ git config --global user.email user@email.com
 $ git config --global core.editor "vim"

2. git initialization
---------------------

* create the directory

::

 $ mkdir myproject
 $ cd myproject

* initialize

::

 $ git init
 Initialized empty Git repository in /home/user/myproject/.git/
 $ ls -a
 .  ..  .git

3. git status
-------------

::

 $ git status
 # On branch master
 #
 # Initial commit
 #
 nothing to commit (create/copy files and use "git add" to track)

4. Adding & commiting files
---------------------------

* create files

::

 $ touch readme.md
 $ git status
 # On branch master
 #
 # Initial commit
 #
 # Untracked files:
 #   (use "git add <file>..." to include in what will be committed)
 #
 #       readme.md

* git add

::

 $ git add readme.md
 $ git status
 # On branch master
 #
 # Initial commit
 #
 # Changes to be committed:
 #   (use "git rm --cached <file>..." to unstage)
 #
 #       new file:   readme.md
 #

* git commit

::

 $ git commit -m "1st commit"
 Committer: user <user@machine>
  0 files changed, 0 insertions(+), 0 deletions(-)
  create mode 100644 readme.md
 $ git status
 # On branch master
 nothing to commit (working directory clean)

5. Checking history
-------------------

* git log

::

 $ git log
 commit 528162ad370cc29ccfe58cefe34a226e06fa5255
 Author: user <user@machine>
 Date:   Wed Mar 11 14:04:41 2020 +0800
 
     2nd commit
 
 commit e5f65a6b1c2c10bd8af95b6a13cb848c6c4a0de5
 Author: user <user@machine>
 Date:   Wed Mar 11 13:54:59 2020 +0800
 
     1st commit

* git diff

::

 $ git diff
 diff --git a/readme.md b/readme.md
 index 8d0e412..05fe86c 100644
 --- a/readme.md
 +++ b/readme.md
 @@ -1 +1,2 @@
  hello git
 +hello world

6. Restoring previous status
----------------------------

* for non-committed cases

::

 $ git checkout -- <filename>

* for committed cases

::

 $ git log
 commit 1d8295dba8cdf062ad854be72fb0a582db777761
 Author: user <user@machine>
 Date:   Wed Mar 11 14:40:20 2020 +0800
 
     3rd commit
 
 commit 528162ad370cc29ccfe58cefe34a226e06fa5255
 Author: user <user@machine>
 Date:   Wed Mar 11 14:04:41 2020 +0800
 
     2nd commit
 
 commit e5f65a6b1c2c10bd8af95b6a13cb848c6c4a0de5
 Author: user <user@machine>
 Date:   Wed Mar 11 13:54:59 2020 +0800
 
     1st commit
 $ git reset --hard 528162ad
 HEAD is now at 528162a 2nd commit
 $ git log
 commit 528162ad370cc29ccfe58cefe34a226e06fa5255
 Author: user <user@machine>
 Date:   Wed Mar 11 14:04:41 2020 +0800
 
     2nd commit
 
 commit e5f65a6b1c2c10bd8af95b6a13cb848c6c4a0de5
 Author: user <user@machine>
 Date:   Wed Mar 11 13:54:59 2020 +0800
 
     1st commit

* git revert

::

 $ git revert 
 Finished one revert.
 [detached HEAD f941937] Revert "2nd commit"
  Committer: user <user@machine>
  1 files changed, 0 insertions(+), 1 deletions(-)

7. Creating branches
--------------------

* list branches

::

 $ git branch
 * master

* create the new branch

::

 $ git branch new
 $ git branch
 * master
   new
 
* change the current branch

::

 $ git checkout new
 Switched to branch 'new'
 $ git branch
   master
 * new
 $ git checkout master
 Switched to branch 'master'
 
* delete the branch

::

 $ git branch -d new
 Deleted branch new (was 528162a).
 $ git branch
 * master

