To remove branches locally 
git branch -d branchName          //Safe delete, checks for unmerged changes
git branch -D branchName          //Force delete, ignores unmerged changes

To remove branches remotely  
git push origin --delete branch_name 

And to cleanup the reference to the branch in my local repo after deleting it remotely to keep sync with the remote
git fetch --prune

--------------------------------------

Lightweight Tags:
    -Just a pointer to a commit (like a bookmark).
    -No extra metadata (author, date, message).
    -Best for temporary/internal use.
    -how to make: git tag v1.0-light
    -for quick marks
Annotated Tags
    Full Git object with:
        -Tag author
        -Date
        -Message (like a commit)
        -Can be GPG-signed
        -Created with -a (and -m for message): git tag -a v1.7 -m "first release"
        -Best for releases (stores more info).
        -for important versions

--------------------------------------

When to use Rebase?
    1- Before pushing – Clean up local commits.
        - Squashing/fixing commits.
        - Making history linear & readable.
    2- Updating a feature branch.
        - Use git rebase main instead of merging to avoid extra merge commits.
    3- Fixing conflicts early.
        - Resolve conflicts in your branch before merging.
    4- Interactive rebase (-i).
        - Edit, reorder, or squash commits for a cleaner history.
    5- how to use:  (git rebase main)   Replay your commits on top of latest main  

--------------------------------------

How to list tags ?
- git tag

--------------------------------------

How to delete tag locally and remotely?
locally: git tag -d tagName
remotely: git push origin --delete tagName

--------------------------------------

![art image](art.jpg) or i can use URL to an image hosted somewhere else. 
<img src="art.jpg" width="200" alt="Cat Image"> 

--------------------------------------

I created secret file called .env and ignored it in gitignore by just adding its name
and it wont appear in git status as untracked files
and if i accidentally committed it i use:
    git rm --cached .env  Untracks but keeps the file locally
    git commit -m "Remove secrets"