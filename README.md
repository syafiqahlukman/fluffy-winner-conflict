# fluffy-winner-conflict
Demonstration to show how git pull works when there's conflict. Here's what I have done

First, I create a repository named fluffy-winner-conflict in GitHub. Then I add an empty file named file1\
Then, on my local computer, i clone the repository so now I have a local copy of the remote repository in my local computer
```
git clone git@github.com:syafiqahlukman/fluffy-winner-conflict.git
```
Then i go inside the repository and add new file also named file1 then I add content to the file1 
```
cd fluffy-winner-conflict
echo "this is written from local" > file1
```

Then i stages the changes, and commit the changes to my local repository
```
git add .
git commit -m "add 1 line from local"
```

Then on GitHub, inside the existing file1, i add the content "this is from GitHub" and commit it.

Then on my local computer i run these command. The first command is to ensure that `git pull` will merge changes instead of rebasing, preserving the branching strategy\
The second command means I download changes from the remote repository and attempts to merge them into the local branch. 
```
git config pull.rebase false
git pull
```

However, after I run the previous 2 commands, there will be error saying that there's conflict in merging the conflict in file1
```
Auto-merging file1
CONFLICT (content): Merge conflict in file1
Automatic merge failed; fix conflicts and then commit the result.
```

So to resolve this conflict, I use Visual Studio Code to open the conflicted file, then there will be options for you either to choose ```Accept current changes```,```Accept incoming changes```,```Accept both changes```,```Compare changes```
Choose the ```Accept both changes```

Then open new terminal in VS Code, run these command
```
git add
git commit -m "Accept both changes from local and github"`
git push
```
After run the ```git push``` command, it uploads the local branch commits to the remote repository, updating it with the resolved file. So basically the content from both file from local and GitHub has been merged



