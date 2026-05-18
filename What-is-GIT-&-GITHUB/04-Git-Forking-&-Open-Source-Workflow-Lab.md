
# 🚀 Challenge: Git Forking & Open-Source Workflow Lab

<img width="1408" height="768" alt="Group 22" src="https://github.com/user-attachments/assets/7b19e2e6-d07f-4e51-a8a2-9ca735b236ee" />


Welcome to the **Git Forking & Collaboration Lab**! This practical assignment is designed to master the exact workflow used by engineering teams and open-source contributors worldwide.

By completing this lab, you will demonstrate proficiency in managing forks, tracking multiple remotes (`origin` vs `upstream`), isolating features using branches, and keeping local code synchronized with a parent repository.

---

## 🎯 Objectives

* Fork and clone a target repository correctly.
* Manage multiple Git remotes (`origin` and `upstream`).
* Implement a feature-branch workflow.
* Synchronize a local repository with upstream changes to prevent merge conflicts.
* Simulate an open-source Pull Request (PR).

## 🛠️ Prerequisites

* A GitHub account.
* Git installed and configured on your local machine (Linux/Unix terminal preferred).
* A text editor (like VS Code).

---

## 💻 Hands-On Tasks

### Task 1: The Fork & Clone Strategy

1. **Target:** Find a target repository (you can use a friend's public repo, a dummy test repo, or a practice open-source project).
2. Click the **Fork** button in the upper right-hand corner of the GitHub interface to create a copy under your account.
3. Open your terminal and clone **your forked version** to your local machine:
```bash
git clone https://github.com/YOUR-USERNAME/target-repo-name.git

```


4. Move into the project directory:

```bash
   cd target-repo-name

```

### Task 2: Establishing the Upstream Pipeline

Right now, your local machine only knows about *your* GitHub copy (`origin`). You need to link it to the original creator's repository (`upstream`).

1. Verify your current remotes:
```bash
git remote -v

```


*(You should only see `origin` URLs right now.)*
2. Add the original repository as your `upstream`:

```bash
   git remote add upstream https://github.com/ORIGINAL-OWNER/target-repo-name.git

```

3. Run `git remote -v` again to verify that both `origin` and `upstream` are properly listed.

### Task 3: Isolated Feature Branching

Never make changes directly on the `main` or `master` branch when working on a fork.

1. Create and switch to a new descriptive feature branch:

```bash
   git checkout -b feature/add-profile-card

```

2. Create or modify a file (e.g., add your own profile markdown file or contribute a bug fix).
3. Stage and commit your modifications:

```bash
   git add .
   git commit -m "feat: add user profile to contributors list"

```

### Task 4: The Sync Test (Simulating Real-World Updates)

Before pushing code, a good developer always checks if the original project has changed while they were coding.

1. Switch back to your local `main` branch:

```bash
   git checkout main

```

2. Fetch the latest changes from the original creator:
```bash
git fetch upstream

```


3. Merge those changes into your local `main` to keep it perfectly updated:
```bash
git merge upstream/main

```


4. Bring your feature branch up to date with your newly updated `main`:
```bash
git checkout feature/add-profile-card
git merge main

```



### Task 5: Delivery & Pull Request

1. Push your completed feature branch to **your fork**:

```bash
   git push origin feature/add-profile-card

```

2. Go to your GitHub repository page. You will see a green button that says **"Compare & pull request"**.
3. Click it, write a clear description of the changes you made, and submit the Pull Request to the original owner.

---

## 📋 Verification Checklist for Portfolio

To prove you completed this lab successfully, take screenshots or save terminal logs of the following milestones to include in your repository's write-up:

* [ ] Output of `git remote -v` showing both `origin` and `upstream` configurations.
* [ ] Output of `git branch` showing your isolated feature branch.
* [ ] A link to a successfully opened (or closed/merged) Pull Request.

> 💡 **Pro-Tip for Friends:** If you are practicing this together, one person can act as the **Project Maintainer** (the original repository owner) and the other can act as the **Contributor** (the person forking and submitting the PR)!

```

```
