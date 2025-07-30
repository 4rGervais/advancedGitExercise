# advancedGitExercise
# Getting Started

```
hp@Gervais-NIYONSHUTI MINGW64 /d/cogito ergo sum/advancedGitExercise (main)
[main 49c52ab] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
nother file"
[main 75b701c] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

hp@Gervais-NIYONSHUTI MINGW64 /d/cogito ergo sum/advancedGitExercise (main)
$ git add test3.md && git commit -m "chore: Create third and fourth files"
[main 31b4198] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
```

## PART 1

  ### 1. Missing file fix
  ```

  hp@Gervais-NIYONSHUTI MINGW64 /d/cogito ergo sum/advancedGitExercise (main)
  [main 49c52ab] chore: Create initial file
  1 file changed, 0 insertions(+), 0 deletions(-)
  nother file"

  hp@Gervais-NIYONSHUTI MINGW64 /d/cogito ergo sum/advancedGitExercise (main)
  $ git status
  On branch main
  Your branch is ahead of 'origin/main' by 3 commits.
    (use "git push" to publish your local commits)

  Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
          modified:   README.md

  Untracked files:
    (use "git add <file>..." to include in what will be committed)
          test4.md

  no changes added to commit (use "git add" and/or "git commit -a")

  hp@Gervais-NIYONSHUTI MINGW64 /d/cogito ergo sum/advancedGitExercise (main)
  $ git log
  commit 31b4198f656ec60b534ce62e650b8894e2f6a1c7 (HEAD -> main)
  Author: 4rGervais <gervaisniyonshuti@gmail.com>
  Date:   Mon Jul 28 09:49:19 2025 +0200

      chore: Create third and fourth files

  commit 75b701c29dedff864d2ff2bc711179fbe0ddaed8
  Author: 4rGervais <gervaisniyonshuti@gmail.com>
  commit 31b4198f656ec60b534ce62e650b8894e2f6a1c7 (HEAD -> main)
  Author: 4rGervais <gervaisniyonshuti@gmail.com>
  Date:   Mon Jul 28 09:49:19 2025 +0200

      chore: Create third and fourth files

  commit 75b701c29dedff864d2ff2bc711179fbe0ddaed8
  Author: 4rGervais <gervaisniyonshuti@gmail.com>
  Date:   Mon Jul 28 09:49:00 2025 +0200

      chore: Create another file

  commit 49c52ab0bd7117d626c77373cceffd7870c63906
  Author: 4rGervais <gervaisniyonshuti@gmail.com>
  Date:   Mon Jul 28 09:48:59 2025 +0200

      chore: Create initial file

  commit 33794d72f13f58cc603a8cc8ed9199813c0ea4d3 (origin/main, origin/HEAD)
  Author: 4rGervais <164742695+4rGervais@users.noreply.github.com>
  Date:   Mon Jul 28 09:44:52 2025 +0200

      Initial commit
  hp@Gervais-NIYONSHUTI MINGW64 /d/cogito ergo sum/advancedGitExercise (main)
  $ git add .

  hp@Gervais-NIYONSHUTI MINGW64 /d/cogito ergo sum/advancedGitExercise (main)
  $ git commit --amend -m 'missing file error handled'
  [main 51b6202] missing file error handled        
  Date: Mon Jul 28 09:49:19 2025 +0200
  3 files changed, 81 insertions(+), 1 deletion(-)
  create mode 100644 test3.md
  create mode 100644 test4.md

  hp@Gervais-NIYONSHUTI MINGW64 /d/cogito ergo sum/advancedGitExercise (main)
  $ git status
  On branch main
  Your branch is ahead of 'origin/main' by 3 commits.
    (use "git push" to publish your local commits)

  nothing to commit, working tree clean

  hp@Gervais-NIYONSHUTI MINGW64 /d/cogito ergo sum/advancedGitExercise (main) 
  $ git log --oneline
  51b6202 (HEAD -> main) missing file error handled
  75b701c chore: Create another file
  49c52ab chore: Create initial file
  33794d7 (origin/main, origin/HEAD) Initial commit
  ```
  ### 2. Editing Commit History
  ```
  hp@Gervais-NIYONSHUTI MINGW64 /d/cogito ergo sum/advancedGitExercise (main|REBASE 1/2)
  $git rebase -i HEAD~2
  [detached HEAD 5788fdd] create Second file
  Date: Fri Feb 28 12:29:54 2025 +0200
  1 file changed, 0 insertions(+), 0 deletions(-)
  create mode 100644 test2.md
  Successfully rebased and updated refs/heads/main.
  ```
  ###  3. Keeping History Tidy - squashing commits

  ```
  hp@Gervais-NIYONSHUTI MINGW64 /d/cogito ergo sum/advancedGitExercise (main|REBASE 1/2)
  $git rebase -i HEAD~2
  interactive rebase in progress; onto 327fb1c
  Last commands done (2 commands done):
    pick 1b3fdef initial commit
    squash 4296568 .
  No commands remaining.
  You are currently rebasing branch 'main' on '327fb1c'.
    (all conflicts fixed: run "git rebase --continue")
  ```
  ### 4. Splitting a commit
  ```
  hp@Gervais-NIYONSHUTI MINGW64 /d/cogito ergo sum/advancedGitExercise (main|REBASE 1/2)
  $ git log --oneline
  c874e8c (HEAD -> main, origin/main, origin/HEAD) new changes
  00f7653 new changes
  51b6202 missing file error handled
  75b701c chore: Create another file
  49c52ab chore: Create initial file
  33794d7 Initial commit

  hp@Gervais-NIYONSHUTI MINGW64 /d/cogito ergo sum/advancedGitExercise (main|REBASE 1/2)
  $ git reset --soft 75b701c

  hp@Gervais-NIYONSHUTI MINGW64 /d/cogito ergo sum/advancedGitExercise (main|REBASE 1/2)
  $ git restore --staged test4.md

  hp@Gervais-NIYONSHUTI MINGW64 /d/cogito ergo sum/advancedGitExercise (main|REBASE 1/2)
  $ git commit -m 'create third file'
  [main cf7e3e6] create third file
  2 files changed, 115 insertions(+), 1 deletion(-)    
  create mode 100644 test3.md

  hp@Gervais-NIYONSHUTI MINGW64 /d/cogito ergo sum/advancedGitExercise (main|REBASE 1/2)
  $ git add test4.md

  hp@Gervais-NIYONSHUTI MINGW64 /d/cogito ergo sum/advancedGitExercise (main|REBASE 1/2)
  $ git commit -m 'creaate fourth file'
  [main e97ec10] creaate fourth file
  1 file changed, 0 insertions(+), 0 deletions(-)      
  create mode 100644 test4.md

  hp@Gervais-NIYONSHUTI MINGW64 /d/cogito ergo sum/advancedGitExercise (main|REBASE 1/2)
  $ git rebase --continue
  You must edit all merge conflicts and then
  mark them as resolved using git add
  ```


## PART 2
  ### challenge 1:
  ```
    D:\cogito ergo sum\advancedGitExercise>git branch ft/new-feature

    D:\cogito ergo sum\advancedGitExercise>git branch
      ft/new-feature
    * main
    D:\cogito ergo sum\advancedGitExercise>git switch ft/new-feature
    M       README.md
    Switched to branch 'ft/new-feature'
  ```
  ### challenge  2:
  ```
    D:\cogito ergo sum\advancedGitExercise>echo "Implemented core functionality for new feature" > feature.txt

    D:\cogito ergo sum\advancedGitExercise>git add feature.txt
    D:\cogito ergo sum\advancedGitExercise>git commit -m "added new file"
    [ft/new-feature ef5baf7] added new file
    1 file changed, 1 insertion(+)
    create mode 100644 feature.txt
  ```
  ### Challenge 3
  ```
    D:\cogito ergo sum\advancedGitExercise>git switch main
    M       README.md
    Switched to branch 'main'
    Your branch and 'origin/main' have diverged,
    and have 1 and 5 different commits each, respectively.     
      (use "git pull" if you want to integrate the remote branch with yours)

    D:\cogito ergo sum\advancedGitExercise>echo "This is the updated project readme." > readme.txt

    D:\cogito ergo sum\advancedGitExercise>
    D:\cogito ergo sum\advancedGitExercise>git add readme.txt

    D:\cogito ergo sum\advancedGitExercise>git commit -m "added new file on main branch"
    [main 8d4ba26] added new file on main branch
    1 file changed, 1 insertion(+)
    create mode 100644 readme.txt

    D:\cogito ergo sum\advancedGitExercise>git log --oneline
    8d4ba26 (HEAD -> main) added new file on main branch
    706ce4f new changes
    00f7653 new changes
    51b6202 missing file error handled
    75b701c chore: Create another file
    49c52ab chore: Create initial file
    33794d7 Initial commit
  ```
  ### challenge 4
  ```
    D:\cogito ergo sum\advancedGitExercise>git remote -v
    origin  https://github.com/4rGervais/advancedGitExercise.git (fetch)
    origin  https://github.com/4rGervais/advancedGitExercise.git (push)
  ```
  ### challenge 5
  ```
    