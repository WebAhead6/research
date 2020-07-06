## Git
1. What is origin ? _eg. `git push origin master`_



'origin' is the default name for the repository when you run git clone.
its used instead of the original repository`s URL.
it makes referencing easier 
'git push origin master' is the command when your project is ready to be shareaable and to push it upstream

2. How can you find the current origin ? and How can you change the origin's url ?

you can find the origin with the command: 
git remote -v
you can change the origin`s url through the command: 
git remote set-url new.git.url/here

![](https://i.imgur.com/BpZHkqG.png)


3. **How to merge between 2 branches using `git merge` ? 

```
git checkout feature1
git merge master
```

What would happen if you do `git merge master current-branch`**

git-merge - Join two or more development histories together

![](https://i.imgur.com/2bSfdBb.png)
```
git merge topic
```
![](https://i.imgur.com/Wsrx7ON.png)



4. **different uses of `git-reset`.**

To undo changes, you can go hard, soft and mixed.

**Hard** 
Revert to previous commit!
Any changes to tracked files in the working tree since <commit> are discarded.


![image alt](https://media.giphy.com/media/3KVcCFmm4vemxPcoAq/giphy.gif)


**Soft**
Tells Git to reset HEAD to another commit, so index and the working directory will not be altered in any way. All of the files changed between the original HEAD and the commit will be staged.

*This differ from commit --amend as:*

* it **doesn't** create a new commit.
* it can actually move HEAD to any commit (as commit --amend is only about not moving HEAD, while allowing to redo the current commit)

**Mixed**
Just like the soft, this will reset HEAD to another commit. It will also reset the index to match it while working directory will not be touched. 

![](https://i.imgur.com/kKUDiwE.jpg)









---
### Talk about and give a demo of the following commands, when would you use each one?:
 - `1. git stash`
![](https://i.imgur.com/yBxLVeX.png)




[for more watch about -Git stash on Youtube :movie:](https://www.youtube.com/watch?v=Ie1EXmd9k0s)



 - `2. git diff` => shows unstaged changes
 - `git diff --staged` => shows staged changes

![](https://i.imgur.com/utwPbpf.png)
![](https://i.imgur.com/KayDmQ6.jpg)


 ## -3. `git log` => shows commit history 
  
![](https://i.imgur.com/ZwxUU8w.jpg)

![](https://i.imgur.com/Oyg09AQ.jpg)

[Git log on Youtube](https://www.youtube.com/watch?v=Jql9qEvaEPc)

- `4. git fetch` =>gits the changes from the remote repository.  but it dose not change our locale repo
mening it's not yet merged into our local branch 

![](https://i.imgur.com/LBSZzy1.jpg)

![](https://i.imgur.com/uBA57mn.png)



### Useful links
- [Git documentation](https://git-scm.com/doc)
- [An aggressive blogpost about git :laughing: ](https://ohshitgit.com/)



