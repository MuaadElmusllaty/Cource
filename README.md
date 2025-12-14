
⚙️ Essential Git Workflow: Creating, Editing, and Deleting Files

This section outlines the precise order of Git commands required to get your local changes successfully onto GitHub (the remote repository).

 1. Creating or Editing a File

This is the most common workflow. It moves a change from your local working directory to the remote repository.

1.  **Work on the File:**
    * Create a **NEW** file (e.g., `git_commands.txt`) or open and edit an **EXISTING** file.
2.  **Stage the Changes:**
    * Tell Git to track this specific change for the next commit.
    ```bash
    git add <file-name>
    # OR to stage ALL modified files:
    git add .
    ```
3.  **Commit the Changes:**
    * Record the staged changes permanently in your local repository history.
    ```bash
    git commit -m "Descriptive message about the changes"
    ```
4.  **Push to GitHub:**
    * Upload the new commit from your local repository to the remote repository (`origin`).
    ```bash
    git push origin main
    ```

---

 2. Deleting a File

You must specifically tell Git that a file has been intentionally deleted.

1.  **Delete the File:**
    * Use your file explorer or the command line to delete the file.
    ```bash
    rm <file-name>  # On Linux/macOS
    # OR
    del <file-name> # On Windows
    ```
2.  **Stage the Deletion:**
    * Use the `git rm` command or use `git add` to stage the deletion action.
    ```bash
    git rm <file-name>
    # OR
    git add .
    ```
3.  **Commit the Changes:**
    * Record the deletion in your local history.
    ```bash
    git commit -m "Removed unused file: <file-name>"
    ```
4.  **Push to GitHub:**
    * Send the deletion commit to the remote repository.
    ```bash
    git push origin main
    ```

---

 3. Integrating Remote Changes (Pull)

Always perform a `pull` *before* starting work or *before* attempting a `push` if you suspect the remote repository has newer commits.

1.  **Pull Changes:**
    * Fetch and merge all new commits from the remote repository to your local branch.
    ```bash
    git pull origin main
    ```

***

**Pro Tip:** If you encounter an error during the `push` saying you were "rejected (fetch first)," it means you must run **`git pull origin main`** first to resolve the difference before attempting to **`git push origin main`** again.

