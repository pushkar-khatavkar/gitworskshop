changes by alex2
changes by alex.
Changes by bob2
changes by bob
Changes by pushkar***

# GIT WORKSHOP NOTES
Windows: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

## Repository
A repository contains all of your project's files and each file's revision history. You can discuss and manage your project's work within the repository.

## Branch
Use a branch to isolate development work without affecting other branches in the repository. Each repository has one default branch, and can have multiple other branches. You can merge a branch into another branch using a pull request.

## Staging Area
The Staging Area is when git starts tracking and saving changes that occur in files. These saved changes reflect in the .git directory. That is about it when it comes to the Staging Area. 

## Local Area
The Local Repository is everything in your .git directory. Mainly what you will see in your Local Repository are all of your checkpoints or commits. It is the area that saves everything (so don’t delete it).

## Basis Commands of Git

```git init```

The ```git init``` command Create an empty Git repository or reinitialize an existing one. This command creates an empty Git repository - basically a .git directory with subdirectories for objects, refs/heads, refs/tags, and template files. An initial branch without any commits will be created

<br/><br/>
```git add```

The ```git add``` command adds a change in the working directory to the staging area. After making changes, running this command will tell git to track this changes. 

<br/><br/>
```git status```

The ```git status``` command displays the state of the working directory and the staging area. It lets you see which changes have been staged, which haven’t, and which files aren’t being tracked by Git.

<br/><br/>
```git commit```

The ```git commit``` command basically save our tracked changes to the local area. Git add command will only tell git to track the changes, git commit will save the chanegs to the local repository.

<br/><br/>
```git log```

The ```git log``` command displays committed snapshots. It lets you list the project history, filter it, and search for specific changes. 


- ```-n``` to list limited number of commits
- ```--oneline``` condensed commits to oneline.
- ```--graph --decorate --oneline``` --graph flag that will draw a text based graph of the commits on the left hand side of the commit messages. --decorate adds the names of branches or tags of the commits that are shown.

<br/><br/>
```git branch```

This command is used to list, create, or delete the branches from the repository. There are key strokes that can be use. 
- ```-r``` will list the branches from remote repository
- ```-a``` will list all the branches
- ```-d``` to delete a branch
- ```-m``` renames a current branch to "name"

<br/><br/>
```git checkout```

The ```git checkout``` command operates upon three distinct entities: files, commits, and branches. Assuming the repo you're working in contains pre-existing branches, you can switch between these branches using git checkout.
It can be used to create branches, switch branches, and checkout remote branches.
- ```-b``` creates new branch

Note: The checkout is also used to add index to tracked files which helps restoring changes which are made on the files but are untracked.

<br/><br/>
```git switch```

The ```git switch``` command was introduced in the git version 2.23.0 to split the ```checkout``` command as the latter served two different purposes i.e. switching branches and restoring the changes.
- -c to create new branch 


## Create the Public Repository on GitHub
1. Login to your GitHub Account ( https://github.com/ )
2. Click on the ```new``` button on the left top side.
3. Enter your Repository Name
4. Insert Proper description 
5. Select ```Public``` Radio button.
6. Click on the ```Create repository``` at the end.
<br/><br/>
## Personal token to push to the Repository
1. Click on the right top corner on your profile.
2. Click on the ```Settings```
3. Go to the last option in the list ```Developer Settings```
4. Click on the ```Personal access tokens``` > ```Tokens (Classic)```
5. ```Generate new token (classic)``` > Enter your MFA code.
6. Write a understandable note for that token with the Expiration time of 30 days.
7. Select ```repo``` in select scopes.
8. Click on ```Generate token```

<br/><br/>
## Remote commands
```git remote```

The ```git remote``` command is used to add a remote repository to our git repository.
- To add remote repository 
```
git add remote <remote_repo_name> <git_url>
```

<br/><br/>
```git push```

The ```git push``` command is used to upload local repository content to a remote repository. Pushing is how you transfer commits from your local repository to a remote repo.
- ```--all``` to push all the local branches to remote
- ```--tag``` to push tags to remote as well
```
git push <remote_repo_name> <branch_name>
```

<br/><br/>
```git pull```

The ```git pull``` command is used to fetch and download content from a remote repository and <b>immediately update the local repository to match that content</b>.

Merging remote upstream changes into your local repository is a common task in Git-based collaboration work flows. The git pull command is actually a combination of two other commands, git fetch followed by git merge.

- ```--no-commit``` for not merging the commits
- ```--rebase``` to use rebase in place of merge
- ```--verbose``` for extra details
```
git pull <remote_repo_name> <branch_name>
```
<br/><br/>
```git fetch```

The ```git fetch``` command downloads commits, files, and refs from a remote repository into your local repo. 

Fetching is what you do when you want to see what everybody else has been working on. 

It’s similar to svn update in that it lets you see how the central history has progressed, <b>but it doesn’t force you to actually merge the changes into your repository.</b>

- ```--all``` to fetch all the registered remote and their branches
- ```--dry-run``` to perform a demo of what will be fetched.

