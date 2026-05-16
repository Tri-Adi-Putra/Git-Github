# Troubleshooting Guide: Git Push & Remote Origin Errors

This reference document provides complete solutions for resolving repository synchronization issues and remote link attachment failures in Git.

---

## Issue: `[rejected] main -> main (fetch first)`

### Why Does This Issue Occur?
Git rejects your `git push` command because your remote repository on GitHub is **not synchronized** with your local computer. GitHub detects that there are files on the server (such as a `README.md`, `.gitignore`, or `LICENSE` file automatically created when setting up the repository on the GitHub website) which **do not exist** in your local project folder yet.

Git enforces this rule to prevent you from accidentally overwriting or deleting existing files on GitHub.

### Solution 1: The Safe Way (Merging History)
Use this method if you want to keep the files already existing on GitHub while uploading your new local project files.

1. **Pull the files from GitHub and force the histories to merge:**
   Since Git considers the local project and the GitHub repository to have unrelated histories, add the special `--allow-unrelated-histories` flag:
   ```bash
   git pull origin main --allow-unrelated-histories
   ```

2. **Check for Conflicts (If Any):**
   * **No Conflict Scenario:** If there are no conflicting filenames, VS Code will usually open an automatic text tab containing a merge confirmation message (*Merge branch 'main'...*). Simply **close** that text tab to proceed. (If your terminal changes into the Vim editor, type `:wq` and press **Enter**).
   * **Conflict Scenario:** If files share the exact same name and clash, they will turn red. Open the conflicting file in VS Code, choose one of the quick actions above the code highlights (*Accept Current Change* or *Accept Incoming Change*), save the file, and then run:
     ```bash
     git add .
     git commit -m "resolve merge conflicts"
     ```

3. **Push back to GitHub:**
   Now that your local folder is synchronized with the files from GitHub, your push command will succeed:
   ```bash
   git push -u origin main
   ```

### Solution 2: The Fast Way (Force Push / Overwrite Total)
Use this method **ONLY IF** your GitHub repository is brand new, and you do not care about any files currently on it. This action will completely wipe out everything on GitHub and replace it 100% with the files from your computer.

1. **Force push using the `-f` (Force) flag:**
   ```bash
   git push -f origin main
   ```

---

## Issue: `remote origin already exists`

### Why Does This Issue Occur?
This error shows up when you run the `git remote add origin <URL>` command. The message means that **the alias name `origin` is already registered and mapped** to a GitHub URL inside your local project folder. Git strictly forbids registering the exact same alias name twice.

### How to Check the Active Link
Before changing anything, verify which GitHub URL is currently attached to your project folder by running:
```bash
git remote -v
```
The terminal will display an output similar to this:
```text
origin  https://github.com (fetch)
origin  https://github.com (push)
```

### Solutions Based on Your Condition

#### Scenario A: If the Displayed URL is Already Correct
If the result of `git remote -v` shows the exact GitHub repository address you intend to target, you **do not need** to run the `git remote add` command again. Your setup is already complete.
* **Solution:** Skip straight to uploading your code:
  ```bash
  git push origin main
  ```

#### Scenario B: If the Displayed URL is Wrong (Update/Change Link)
If you mistyped the repository name, used the wrong account, or want to move the link to a completely different repository, use the **`set-url`** command (instead of `add`):
```bash
git remote set-url origin https://github.com
```

#### Scenario C: If You Want to Delete and Restart From Scratch
If you prefer to completely remove the old remote entry cleanly before typing a brand new setup command:
1. **Remove the existing remote named origin:**
   ```bash
   git remote remove origin
   ```
2. **Register your new remote link freely:**
   ```bash
   git remote add origin https://github.com
   ```
