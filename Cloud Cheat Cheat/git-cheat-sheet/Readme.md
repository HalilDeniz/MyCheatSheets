# **GitHub Cheat Sheet: Essential Commands for Git Services**

<img src="../source/git-cheat-cheet.png"></img>

## **What is GitHub?**
GitHub is a cloud-based platform that is widely used for version control and collaboration. 
It allows multiple people to work together on projects from anywhere in the world. 
Built around the Git version control system, GitHub provides a web-based graphical interface
along with additional features such as access control, bug tracking, feature requests, task management, and wikis for every project.

## **Why GitHub?**
The power of GitHub lies in its ability to facilitate collaboration among software developers. 
Its primary function is to host code and provide tools for version control, but it has evolved into much more. 
GitHub makes it easy for developers to track changes, revert to previous stages, and efficiently manage multiple versions of their projects. 
This is crucial in today's fast-paced software development world, where team members often work on different parts of a project simultaneously.



### **1. Git Setup and Configuration**
1. **Install Git**: `git install git`
   - This is the first step in setting up Git. However, the correct command varies based on your operating system. For example, on macOS, it's typically `brew install git`, and on Windows, you might download and install Git from [git-scm.com](https://git-scm.com/).

2. **Set User Name**: `git config --global user.name "username"`
   - This command sets your Git username. It's important to choose a username that you're comfortable having displayed in your project histories.

3. **Set Email**: `git config --global user.email "email_address"`
   - Similar to setting the username, this command sets your email address for Git. This should be the same email associated with your GitHub account if you plan to use GitHub for your repositories.

4. **Check Git Version**: `git --version`
   - It's useful to know what version of Git you're working with, especially when troubleshooting or using specific features.

5. **List Existing Configurations**: `git config --list`
   - This command shows all the configuration settings Git is using, which can be useful for verifying your setup.

6. **Edit Global Git Configuration**: `git config --global --edit`
   - This opens the global Git configuration file in a text editor, allowing you to make detailed adjustments to your Git setup.

7. **Set Default Pull Behavior**: `git config --global pull.rebase false`
   - This command sets the default behavior for `git pull`. Setting it to `false` uses the merging strategy, which is often easier for beginners.

8. **Cache Credentials**: `git config --global credential.helper cache`
   - Use this command to avoid entering your credentials every time you interact with a remote repository. This stores your credentials in memory for a certain period.

9. **Ignoring Files Globally**: `git config --global core.excludesfile '~/.gitignore_global'`
   - This sets a global `.gitignore` file, allowing you to specify files to ignore across all your Git repositories.

10. **Set Default Branch Name**: `git config --global init.defaultBranch main`
    - This command changes the default branch name for new repositories from 'master' to 'main' (or any other name you prefer).

11. **Setting Up Aliases for Common Commands**: 
    - For example, `git config --global alias.co checkout` lets you use `git co` as a shortcut for `git checkout`.

By adding these points, the section becomes more comprehensive, covering a wider range of Git setup and configuration tasks, which can be especially helpful for new Git users.

---


### **2. Local Repository Operations**
1. **Create a New Repository**: `git init`
   - This command initializes a new Git repository in your current directory. It creates a `.git` directory with all the necessary metadata for version control.

2. **Clone an Existing Repository**: `git clone [url]`
   - Use this to copy an existing repository from a remote server to your local machine. Replace `[url]` with the URL of the repository. This command creates a new directory, initializes a `.git` directory inside it, and pulls down all the data for that repository.

3. **View the Status of Your Repository**: `git status`
   - This command shows the status of changes as untracked, modified, or staged. It's a useful way to see what changes are pending and which files are not being tracked by Git.

4. **List All Files in the Repository**: `git ls-files`
   - This will list all the files that Git is currently tracking in the repository. It's helpful for getting a quick overview of what's been added to version control.

5. **Add Files to Staging Area**: `git add [file_name]` or `git add .`
   - Use this command to start tracking new files or to stage modifications to existing files. `git add .` adds all current changes in the directory to the staging area.

6. **Remove Files from Staging Area or Source**: `git rm --cached [file_name]` and `git rm [file_name]`
   - The `--cached` option will remove files from the staging area while keeping them in the working directory. Without `--cached`, the command will remove files from both the staging area and your working directory.

7. **Unstage Changes**: `git reset HEAD [file_name]`
   - If you change your mind about staging some files, this command will unstage them.

8. **View Changes Between the Working Directory and Staging Area**: `git diff`
   - This command shows the differences that are not yet staged.

9. **View Changes Between the Staging Area and the Repository**: `git diff --staged`
   - This shows the changes that are staged but not yet committed.

10. **Committing Changes**: `git commit -m "commit message"`
    - This command takes your staged changes and commits them to the repository with a descriptive message.

11. **View Commit History**: `git log`
    - Use this to see the chronological commit history for the current branch.

By including these additional commands and explanations, the section becomes more comprehensive, covering a wide range of local operations that are fundamental to working with Git. This will be especially helpful for beginners to understand the basic workflows in Git.

---

### **3. File Changes and Commits**
1. **Start Tracking Files and Add Changes to Staging Area**: 
   - **For a Single File**: `git add [file_name]`
     - This command adds a specific file to the staging area, making it ready for a commit. Replace `[file_name]` with the name of the file you want to track.
   - **To Add All Changes**: `git add .`
     - This adds all new or modified files in your current directory to the staging area. Useful for batching many changes at once.

2. **Commit Changes**: `git commit -m "[commit message]"`
   - This command takes the staged changes and saves them to the repository. The `[commit message]` should be a clear, concise description of the changes made.

3. **Check Status of Changes**: `git status`
   - Shows the current status of your working directory and staging area. It lets you see which changes are staged, unstaged, or untracked.

4. **Amend a Commit**: `git commit --amend`
   - If you need to make changes to your most recent commit, this command lets you amend it. This is useful for fixing mistakes in your last commit.

5. **Untrack Files**: `git rm --cached [file_name]`
   - Removes files from being tracked by Git without deleting them from your file system.

6. **View Changes Not Yet Staged**: `git diff`
   - Shows file differences not yet staged.

7. **View Changes Already Staged**: `git diff --staged`
   - Shows what has been staged so far compared to the last commit.

8. **Ignore Files**: Create a `.gitignore` file
   - List files and directories you don’t want Git to track in `.gitignore`.

9. **Stash Changes**: `git stash`
   - Temporarily stashes changes you've made so you can work on something else and then come back to your stashed changes later.

10. **Apply Stashed Changes**: `git stash pop`
    - Re-applies the changes that were stashed away.

11. **Viewing Commit History**: `git log`
    - This command displays the commit history, showing the detailed list of past commits.

By adding these points, the "File Changes and Commits" section becomes more robust and informative, covering a broader range of scenarios and commands that are commonly used in Git workflows. This expanded section will be particularly beneficial for users who are looking to deepen their understanding of managing file changes and version control in Git.

---

Expanding the "Branch Operations" section will provide a more comprehensive understanding of managing branches in Git, which is a fundamental aspect of its functionality. Here's a detailed version:

### *4. *Branch Operations**
1. **Create New Branch**: `git branch [branch_name]`
   - This command creates a new branch named `[branch_name]`. However, it doesn’t automatically switch you to that branch. Replace `[branch_name]` with your desired branch name.

2. **List Branches**: `git branch`
   - Lists all branches in your repository. The current branch will be highlighted and marked with an asterisk.

3. **Switch to a Branch**: `git checkout [branch_name]`
   - This command is used to switch from one branch to another. Replace `[branch_name]` with the name of the branch you want to switch to.

4. **Create and Switch to New Branch**: `git checkout -b [branch_name]`
   - A combination of the above two commands, this one creates a new branch and immediately switches to it.

5. **Rename a Branch**: `git branch -m [old_branch_name] [new_branch_name]`
   - If you need to rename a branch, you can do so with this command. This is particularly useful if the name of the branch no longer reflects its purpose.

6. **Delete a Branch**: 
   - Locally: `git branch -d [branch_name]`
   - Remotely: `git push origin --delete [branch_name]`
   - Use the first command to delete a branch locally. The second command is used to delete a branch on a remote repository.

7. **Merge Branches**: `git merge [branch_name]`
   - This command is used to merge the changes from `[branch_name]` into your current branch. It's a common practice to merge changes from feature or development branches into the main branch.

8. **Viewing All Branches (Including Remote)**: `git branch -a`
   - Lists all branches in your local and remote repositories, giving you a full overview of the branches associated with the repository.

9. **Stashing Changes Before Switching Branches**: `git stash`
   - If you have uncommitted changes that you don’t want to commit yet, you can stash them before switching branches. You can later apply these changes using `git stash pop`.

10. **Checking Out Remote Branches**: `git checkout -b [branch_name] origin/[branch_name]`
    - This command is used to check out a branch from a remote repository. It creates a new local branch that tracks the remote branch.

11. **Comparing Branches**: `git diff [branch_name_1]..[branch_name_2]`
    - Use this command to see the differences between two branches.

By including these additional commands and explanations, the "Branch Operations" section becomes more thorough and informative. It covers various scenarios and commands that are commonly used in branch management, making it a valuable resource for Git users at all levels.

---

### **5. Remote Repository Operations**
1. **Add Remote Repository**: `git remote add origin [remote_repo_url]`
   - This command is used to add a new remote repository. Replace `[remote_repo_url]` with the URL of the remote repository. `origin` is a conventional name used to denote the primary remote repository, but you can use any name.

2. **View Remote Repositories**: `git remote -v`
   - Lists all the remote connections you have to other repositories along with the URLs. The `-v` flag stands for "verbose", showing the URLs for fetch (download) and push (upload) operations.

3. **Push Changes to Remote Repository**: `git push origin [branch_name]`
   - This command is used to upload the contents of your local branch to a remote repository. Replace `[branch_name]` with the name of your local branch.

4. **Pull Changes from Remote Repository**: `git pull origin [branch_name]`
   - This combines two operations: it fetches changes from the remote branch and then merges them into your current local branch.

5. **Fetch Changes from Remote Repository**: `git fetch origin`
   - Fetches updates from the remote repository but does not merge them into your current branch. This is useful for reviewing changes before merging.

6. **Set Upstream Branch**: `git push -u origin [branch_name]`
   - When pushing a branch for the first time, this sets the remote branch as the upstream for your local branch. The `-u` flag sets the upstream relationship.

7. **Inspect a Remote Repository**: `git remote show origin`
   - Provides detailed information about a particular remote, such as the URL, branches, and its configuration on your local system.

8. **Remove a Remote Repository**: `git remote remove [remote_name]`
   - Use this command to remove a connection to a remote repository. Replace `[remote_name]` with the name of the remote you want to remove.

9. **Pruning Remote-Tracking Branches**: `git remote prune origin`
   - Cleans up stale references to remote branches that no longer exist on the remote repository.

10. **Pushing Tags to Remote Repository**: `git push origin --tags`
    - This command is used to push all your tags to the remote repository.

11. **Cloning a Specific Branch from a Remote Repository**: `git clone -b [branch_name] [remote_repo_url]`
    - Use this command to clone a specific branch from a remote repository instead of the default branch.

By adding these points, the "Remote Repository Operations" section becomes more comprehensive, covering a range of operations that are essential for collaborating and managing code in remote repositories. This expanded section will be particularly beneficial for Git users who work in collaborative environments or manage multiple remote repositories.

---

Expanding on the "Merging and Conflict Resolution" section will provide a deeper understanding of how to handle the integration of different branches and resolve conflicts in Git. Here's a more detailed version:

### **6. Merging and Conflict Resolution**
1. **Merge Branches**: `git merge [other_branch_name]`
   - This command merges changes from `[other_branch_name]` into your current branch. It's a key operation for incorporating new features or updates into your main branch.

2. **Resolve Conflicts**: 
   - Conflicts occur when the same lines of code are changed in different branches. When this happens, Git pauses the merge and asks you to resolve the conflicts.
   - **Manual Resolution**: Open the files with conflicts and manually edit them to resolve the discrepancies. Git marks conflicts in the file, showing the conflicting changes from both branches.
   - After resolving the conflicts, use `git add [file_name]` to stage the resolved files.
   - Then, complete the merge with `git commit`. Git will automatically create a commit message indicating that a merge conflict was resolved.

3. **Abort a Merge**: `git merge --abort`
   - If you decide not to proceed with a merge, this command will abort the merge operation and return your branch to the state before the merge began.

4. **Using a Merge Tool**: `git mergetool`
   - For complex conflicts, Git's merge tool utility can be helpful. It provides a visual interface to aid in resolving conflicts.

5. **Fast-Forward Merge vs. No-Fast-Forward Merge**: 
   - **Fast-Forward Merge**: If the branch being merged into hasn’t diverged, Git performs a fast-forward merge. It just moves the branch pointer forward.
   - **No-Fast-Forward Merge**: Use `git merge --no-ff [other_branch_name]` to create a new commit even if the merge could be resolved with a fast-forward. This is useful for maintaining a history of merges.

6. **Squash Merging**: `git merge --squash [other_branch_name]`
   - This combines all changes from the feature branch into a single commit in the main branch. It's useful for keeping a clean history.

7. **Checking for Merge Conflicts Before Merging**: `git merge --no-commit --no-ff [other_branch_name]`
   - This command performs the merge but stops before creating a commit, allowing you to check for conflicts or other issues before finalizing the merge.

8. **Rebasing as an Alternative to Merging**: `git rebase [base_branch_name]`
   - Rebasing is an alternative to merging that can create a cleaner project history. It integrates changes from one branch into another by applying the changes onto the base branch.

By expanding this section with additional commands and explanations, readers can gain a more thorough understanding of merging processes, conflict resolution strategies, and the choices available to them when integrating changes from different branches in Git. This will be especially useful for developers working in collaborative environments and managing complex projects.

---

Enhancing the "Useful Extra Commands" section with more details and additional commands will provide a comprehensive toolkit for managing various aspects of Git repositories. Here's an expanded version:

### **7. Useful Extra Commands**
1. **View Commit History**: `git log`
   - This command displays the commit history of the current branch, showing each commit with its ID, author, date, and message. It's crucial for tracking changes and understanding the history of the project.

2. **Revert to a Specific Commit**: `git checkout [commit_id]`
   - This command is used to view the state of the repository at the time of a specific commit. Replace `[commit_id]` with the desired commit's hash. Note that this puts you in a 'detached HEAD' state.

3. **Reverting Changes**: `git revert [commit_id]`
   - Unlike `git checkout`, `git revert` creates a new commit that undoes the changes made in `[commit_id]`. It's a safe way to undo changes as it doesn't alter the project history.

4. **View Specific Commit**: `git show [commit_id]`
   - Use this to view the changes associated with a specific commit. It shows the log message and textual differences.

5. **List Tags**: `git tag`
   - Displays the list of tags. Tags are often used to mark specific points in history as important, typically for release versions.

6. **Create a Tag**: `git tag [tag_name] [commit_id]`
   - This creates a new tag at the specified commit. Tags are used for marking releases or other significant points in the repository history.

7. **Log Graph**: `git log --graph`
   - Shows the commit history in a graphical representation. It's useful for visualizing the branch structure of the repository.

8. **Log on a Specific File**: `git log -- [file_name]`
   - Displays the commit history for a specific file, tracking the changes made over time.

9. **Checking Out a Remote Branch**: `git checkout -t origin/[branch_name]`
   - This command is used to check out a branch from a remote repository, setting it up to track the remote branch.

10. **Stashing Uncommitted Changes**: `git stash`
    - Temporarily stores uncommitted changes, allowing you to switch branches with a clean working directory. You can later reapply the stashed changes with `git stash pop`.

11. **Cleaning Untracked Files**: `git clean -f`
    - Removes untracked files from your working directory. This is useful for getting rid of build outputs, log files, and other unneeded files.

12. **Interactive Rebase**: `git rebase -i [commit_id]`
    - This allows you to modify commits in various ways before pushing them. It's a powerful tool for cleaning up your commit history.

By including these additional commands and their explanations, the "Useful Extra Commands" section becomes a comprehensive guide to various Git operations beyond the basic workflow, covering everything from viewing history and handling commits to managing tags and stashes. This expanded list will be particularly beneficial for users looking to leverage Git's full capabilities for their project management needs.

---

## Conclusion
GitHub is more than just a tool for programmers. 
It's a platform that fosters collaboration and innovation. 
Whether you're a professional developer, a student learning to code, or even a non-technical person involved in software projects, GitHub offers a set of powerful tools to help manage and contribute to software projects. 
Its ability to integrate with various other tools and its extensive community support makes it an indispensable tool in the world of software development

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, feel free to open an issue or submit a pull request.

## Contact

If you have any questions, comments, or suggestions about **GitHub Cheat sheet**, please feel free to contact me:

- LinkedIn: [Halil Ibrahim Deniz](https://www.linkedin.com/in/halil-ibrahim-deniz/)
- TryHackMe: [Halilovic](https://tryhackme.com/p/halilovic)
- Instagram: [deniz.halil333](https://www.instagram.com/deniz.halil333/)
- YouTube: [Halil Deniz](https://www.youtube.com/c/HalilDeniz)
- Email: halildeniz313@gmail.com


## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## 💰 You can help me by Donating
  Thank you for considering supporting me! Your support enables me to dedicate more time and effort to creating useful **Cheat Sheet** and developing new projects. By contributing, you're not only helping me improve existing tools but also inspiring new ideas and innovations. Your support plays a vital role in the growth of this project and future endeavors. Together, let's continue building and learning. Thank you!"<br>
[![BuyMeACoffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-ffdd00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://buymeacoffee.com/halildeniz)
[![Patreon](https://img.shields.io/badge/Patreon-F96854?style=for-the-badge&logo=patreon&logoColor=white)](https://patreon.com/denizhalil) 

  