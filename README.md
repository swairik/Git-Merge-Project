# Git-Merge-Project

```
C:\Dev\Antwalk Training\Git Merging Project> git init
Initialized empty Git repository in C:/Dev/Antwalk Training/Git Merging Project/.git/
C:\Dev\Antwalk Training\Git Merging Project [main]> git pull origin main
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 601 bytes | 66.00 KiB/s, done.
 * branch            main       -> FETCH_HEAD
C:\Dev\Antwalk Training\Git Merging Project [main +1 ~0 -0 !]> git add .
C:\Dev\Antwalk Training\Git Merging Project [main +1 ~0 -0 ~]> git commit -m "added countries.txt"
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 countries.txt
```

# Part 1 : Fast Forward

```
C:\Dev\Antwalk Training\Git Merging Project [main]> git switch -c ffMerge
Switched to a new branch 'ffMerge'
C:\Dev\Antwalk Training\Git Merging Project [ffMerge +0 ~1 -0 ~]> git commit -m "added South American countries"
C:\Dev\Antwalk Training\Git Merging Project [ffMerge]> git add .
C:\Dev\Antwalk Training\Git Merging Project [ffMerge +0 ~1 -0 ~]> git commit -m "added Asian countries"
 1 file changed, 4 insertions(+), 1 deletion(-)
C:\Dev\Antwalk Training\Git Merging Project [main]> git merge ffMerge
Updating 718dadd..73f777f
 countries.txt | 5 +++++
 1 file changed, 5 insertions(+)
```

# Part 2 : No Merge Conflicts

```
C:\Dev\Antwalk Training\Git Merging Project [main]> git switch -c noMergeConflicts
Switched to a new branch 'noMergeConflicts'
C:\Dev\Antwalk Training\Git Merging Project [noMergeConflicts]> git add .
C:\Dev\Antwalk Training\Git Merging Project [noMergeConflicts +0 ~1 -0 ~]> git commit -m "added european countries from noMergeConflicts branch"
[noMergeConflicts 3b8ee37] added european countries from noMergeConflicts branch
 1 file changed, 4 insertions(+), 1 deletion(-)
C:\Dev\Antwalk Training\Git Merging Project [noMergeConflicts]> git switch main
Switched to branch 'main'
C:\Dev\Antwalk Training\Git Merging Project [main]> git add .
C:\Dev\Antwalk Training\Git Merging Project [main +0 ~1 -0 ~]> git commit -m "change from main branch"
[main 6623b9a] change from main branch
 1 file changed, 1 insertion(+), 1 deletion(-)
C:\Dev\Antwalk Training\Git Merging Project [main]> git merge noMergeConflicts
Auto-merging countries.txt
Merge made by the 'recursive' strategy.
 countries.txt | 5 ++++-
 1 file changed, 4 insertions(+), 1 deletion(-)
```

# Part 3 : Merge Conflicts

```
C:\Dev\Antwalk Training\Git Merging Project [main]> git switch -c mergeConflicts
Switched to a new branch 'mergeConflicts'
C:\Dev\Antwalk Training\Git Merging Project [mergeConflicts]> git add .
C:\Dev\Antwalk Training\Git Merging Project [mergeConflicts +0 ~1 -0 ~]> git commit -m "added european countries from mergeConflicts branch"
[mergeConflicts 8802620] added european countries from mergeConflicts branch
 1 file changed, 4 insertions(+), 1 deletion(-)
C:\Dev\Antwalk Training\Git Merging Project [mergeConflicts]> git switch main
Switched to branch 'main'
C:\Dev\Antwalk Training\Git Merging Project [main]> git add .
C:\Dev\Antwalk Training\Git Merging Project [main +0 ~1 -0 ~]> git commit -m "added north american countries from main"
[main e4a9b75] added north american countries from main
 1 file changed, 4 insertions(+), 1 deletion(-)
C:\Dev\Antwalk Training\Git Merging Project [main]> git merge mergeConflicts
Auto-merging countries.txt
CONFLICT (content): Merge conflict in countries.txt
Automatic merge failed; fix conflicts and then commit the result.
C:\Dev\Antwalk Training\Git Merging Project [main +0 ~0 -0 !1 | +0 ~0 -0 !1 !]> git commit -m "merge branch 'mergeConflicts'"
[main 0fddae2] merge branch 'mergeConflicts'
```

# Pushing to GitHub : 

```
C:\Dev\Antwalk Training\Git Merging Project [main]> git push origin --all
Enumerating objects: 28, done.
Counting objects: 100% (28/28), done.
Delta compression using up to 8 threads
Compressing objects: 100% (22/22), done.
Writing objects: 100% (27/27), 2.62 KiB | 669.00 KiB/s, done.
Total 27 (delta 4), reused 0 (delta 0), pack-reused 0        
remote: Resolving deltas: 100% (4/4), done.
To github.com:swairik/Git-Merge-Project.git
   c19b770..0fddae2  main -> main
 * [new branch]      ffMerge -> ffMerge
 * [new branch]      mergeConflicts -> mergeConflicts    
 * [new branch]      noMergeConflicts -> noMergeConflicts
```

