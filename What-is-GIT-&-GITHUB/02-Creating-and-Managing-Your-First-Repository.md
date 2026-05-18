
# 🚀 GitHub Fundamentals: Creating and Managing Your First Repository

<img width="1408" height="768" alt="Group 20" src="https://github.com/user-attachments/assets/903c78cb-4f21-4b7b-822f-b7e0184452a8" />


Welcome to this Git and GitHub learning repository! This documentation serves as a comprehensive study guide based on the Git & GitHub tutorial series. This repository focuses on understanding the foundational workflow of GitHub directly through its web interface.

---

## 📌 1. Registration & GitHub Account Types
To get started, visit [github.com](https://github.com). GitHub offers different account tiers, including:
* **Free Account:** Supports unlimited public and private repositories. However, for private repositories, the number of collaborators is limited to a maximum of **3 people**.
* **Paid Account:** Removes collaborator limits on private repositories and provides advanced security features and increased storage.

---

## 📁 2. Understanding and Creating a Repository
A **Repository** (often shortened to "Repo") is essentially a digital project folder where you store all your project files—whether they are source code, text documents, or digital assets.

### Steps to Create a New Repository on GitHub Web:
1. Click the **`+`** icon in the top-right corner of the GitHub dashboard and select **`New repository`**.
2. **Repository Name:** Type your project name. *Note: Repository names cannot contain spaces. If you type a space, GitHub will automatically replace it with a hyphen (`-`).*
3. **Description:** Add a brief summary of what your project is about.
4. **Visibility:** Choose either **Public** (visible to anyone) or **Private** (visible only to you and chosen collaborators).
5. **Initialize README:** It is highly recommended to check the `Initialize this repository with a README` option. The `README.md` file acts as the homepage for your project, providing details, installation guides, or project documentation.
6. Click **`Create repository`**.

---

## 📝 3. File Management Directly via GitHub Web
In this introductory phase, you can manipulate files directly within your web browser without touching your local machine:
* **Creating a New File:** Click the **`Create new file`** button, name your file along with its extension (e.g., `resolution.txt`, `index.html`), and write your content in the built-in editor.
* **Editing a File:** Open the specific file you want to change, and click the **Pencil icon (`Edit this file`)** located in the top-right corner of the file view.

---

## 🔄 4. Core Concepts of the Git Workflow

### A. Commit (Saving Changes)
In Git, we don't use a standard "Save" button. Every time you finish creating or modifying a file, you must perform a **Commit**.
* **Commit Message:** A mandatory, concise description explaining *what* changes you made (e.g., `Add resolution.txt file`).
* **Target Branch:** By default, in a brand-new repository, this commit will be saved directly to the main timeline, known as the **`master`** or **`main`** branch.

### B. Tracking Version History
One of Git's greatest strengths is its ability to record every single change over time. By navigating to a file's **`History`** tab, you can view:
* 🟢 **Green Highlights (with a `+` sign):** New lines or code that have been added.
* 🔴 **Red Highlights (with a `-` sign):** Old lines or code that have been removed or modified.

### C. Commit Hash
Every successful commit generates a unique, random alphanumeric string known as a **Commit Hash**. This unique identifier allows Git to track the exact state of your project at that specific moment in time (acting like a *save point* in a game).

### D. Network Diagram (Visualizing the Workflow)
To view a visual chronology of your project's development, you can navigate to **`Insights` > `Network`**. This graph feature is incredibly useful for team collaboration, as it visually illustrates when branches are created, when commits are made by different contributors, and when branches are merged back together.

---

## 🎯 Case Study & Practical Exercise
Put your knowledge into practice by completing this challenge on your own GitHub account:
1. Create a new public repository named `[your-name]-resolution`.
2. Check the box to *Initialize with a README*.
3. Create a new plain text file (`.txt`) listing your tech stack goals or IT learning targets for this year.
4. Modify this file 2 to 3 times (e.g., adding new goals or removing completed ones), making sure to write a clear *commit message* for each session.
5. Explore the *History* tab and the *Insights > Network* view to see how Git meticulously tracks your progress.

---
*Study Notes - Adapted from the Web Programming Unpas Git & GitHub Course.*  
**Don't forget the semicolon! `;`**
