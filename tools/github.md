## Tools Directory Structure

- [tools.md](./tools.md)
- [github.md](./github.md)
- [markdown_cheatsheet.md](./markdown_cheatsheet.md)
- [vs_code.md](./vs_code.md)
- [communication_links.md](./communication_links.md) *(Optional)*
- [platform_integrations.md](./platform_integrations.md) *(Optional)*
- [additional_resources.md](./additional_resources.md) *(Optional)*

---

# Using GitHub & GitHub Desktop

This guide explains how to **use GitHub** to collaborate on code and documentation—even if you have **no prior Git experience**. We cover the basics of Git, show how to install and use **GitHub Desktop**, and provide best practices for branching, committing, and contributing changes to the project.

---

## Why are we using Github?

We chose GitHub as our version control and collaboration platform because it provides **real-time tracking of changes**, transparent peer review through **pull requests**, and intuitive **branching** for isolating new ideas or bug fixes. By keeping our code and documentation centralized in GitHub, we ensure that every contributor’s work is backed up, easily referenced, and continuously improved. This approach helps avoid overwriting each other’s files, fosters open discussion on potential enhancements, and streamlines the process of moving trading strategies from concept to robust implementation.

--

## Team Training on Github

Initially, please refer to this guide and the videos below to get an overview of:
- using Github
- copying the Team repositories to your computer
- creating and updating files

In the future we may have a zoom call about using Github and Github Desktop and record it.

---

## 1. What Is Git & GitHub?

- **Git** is a **version control system** that keeps track of changes in your files (e.g., code, documentation).
- **GitHub** is a **web platform** that stores Git repositories online, letting you collaborate with others. You can view a project’s files, see their histories, discuss issues, and propose changes.

**Videos**: Here are some useful videos to help understand git and github.

**Quick Overview:**
- [Learn GIT & GITHUB in 5 Minutes! (Beginner Tutorial)](https://www.youtube.com/watch?v=X2Kc1ZCADig)
- [How Git Works: Explained in 4 Minutes](https://www.youtube.com/watch?v=e9lnsKot_SQ)

**Tutorials:**  Note: The end of this guide contains a detailed outline and timestamp for the following two videos.

- [`Git, GitHub, & GitHub Desktop for beginners`](https://www.youtube.com/watch?v=8Dd7KRpKeaE) (YouTube). It walks you through Git fundamentals and introduces GitHub Desktop.
- [`How to Use Git & GitHub Desktop Tutorial for Beginners`](https://www.youtube.com/watch?v=MaqVvXv6zrU)

---

## 2. Setting Up GitHub Desktop

If you’re new to Git, **GitHub Desktop** is the easiest way to start. It offers a **graphical interface** (GUI) to manage your repositories without typing Git commands.

### 2.1 Install GitHub Desktop

1. **Download**  
   - Visit the [GitHub Desktop website](https://desktop.github.com/) and download the installer for your operating system.
2. **Install**  
   - Run the installer and follow any on-screen prompts.
3. **Sign In**  
   - When prompted, log in with your GitHub account (create one if you don’t have it).

### 2.2 Cloning a Repository

1. **Open GitHub Desktop**  
   - Go to **File → Clone repository** in the top menu.
2. **Choose URL**  
   - Select the **URL** tab if it’s not already selected.
3. **Enter Repo URL**  
   - Paste the project’s GitHub URL (e.g., `https://github.com/etradeteam/strategy_development.git`).
4. **Local Path**  
   - Pick a folder on your computer where you want the project files stored.
5. **Clone**  
   - Click **Clone**. GitHub Desktop will download all files, branches, and history from GitHub.

### 2.3 Basic Navigation

- **Changes Tab**: Shows the files you’ve modified locally.  
- **History Tab**: Displays the commits (snapshots) that have been made, along with commit messages.  
- **Branch Menu**: Lets you switch between different branches or create new ones.

---

## 3. Basic GitHub Workflow

Here’s a simple workflow using **GitHub Desktop** and the GitHub website:

1. **Create / Switch Branches**  
   - In GitHub Desktop, click the current branch name at the top, then “New branch” or choose an existing feature branch.  
   - Branches let you isolate changes so you don’t affect the main code until you’re ready.

2. **Make Changes Locally**  
   - Open the files in your preferred text editor (e.g., VS Code) and modify them.  
   - Save your edits. GitHub Desktop will automatically detect these changes.

3. **Commit**  
   - Return to GitHub Desktop.  
   - In the bottom-left panel, enter a **commit message** summarizing your changes.  
   - Click **Commit to [branch name]**. This creates a local commit—a mini snapshot of your changes.

4. **Push Your Changes**  
   - Click **Push origin** (top panel in GitHub Desktop) to upload the commits to GitHub.  
   - Now your changes are visible in the repository’s branch on the GitHub website.

5. **Open a Pull Request**  
   - On the GitHub website, find your branch under “Branches.”  
   - Click **New pull request**. Describe what you changed, why, and any relevant issue numbers.  
   - Request feedback. Other team members can comment, approve, or suggest modifications.

6. **Merge**  
   - Once approved, your branch can be **merged** into the `main` (or `master`) branch.  
   - After merging, the changes are part of the official codebase.

---

## 4. Key Git & GitHub Terminology

- **Repository (Repo)**: A project folder tracked by Git, containing your files and their revision history.  
- **Branch**: A parallel version of the repository. By branching, you can develop features or fix bugs without disturbing the main code.  
- **Commit**: A snapshot of your changes with a message describing what was done.  
- **Pull Request (PR)**: A request to merge your branch’s changes into another branch. This is where code review happens.  
- **Merge**: The action of integrating changes from one branch into another.

---

## 5. Working With the Repository

1. **Syncing Changes**  
   - If others make commits, you can **Pull** updates from GitHub Desktop to keep your local copy current.  
   - This helps avoid merge conflicts.

2. **Resolving Merge Conflicts**  
   - If two people edited the same lines, Git needs help deciding whose changes to keep.  
   - GitHub Desktop can show you the conflicting parts. You’ll manually reconcile them in a text editor, then commit again.

3. **Project Organization**  
   - Typically, code or `.md` files are organized by subfolders (e.g., `Tools`, `Process`, `Team`).  
   - Keep file names and structure consistent.

4. **Issues & Project Boards** (Optional)  
   - GitHub also has **Issues** for tracking bugs/enhancements and **Projects** for Kanban boards.  
   - You can open a new issue to propose an idea or report a bug, then link your pull request to that issue.

---

## 6. Best Practices for Non-Developers

1. **Frequent Commits**  
   - Commit your work in small chunks. This way, if an error arises, it’s easier to pinpoint the cause.  
   - Write clear commit messages: “Added RSI-based mean reversion logic” is more helpful than “Changed stuff.”

2. **Use Branches Liberally**  
   - Create a branch for each feature or fix. Avoid mixing multiple unrelated changes in a single branch.  
   - This keeps your main code stable and easier to review.

3. **Ask for Reviews**  
   - On your pull request, you can request feedback from specific team members.  
   - Be open to suggestions or code style comments—this is a collaborative process.

4. **Stay Organized**  
   - Use descriptive file names and keep documentation updated.  
   - If you’re updating instructions or code samples, reflect that in the relevant `.md` file.

5. **Keep Learning**  
   - The linked video above is a great start. Searching “GitHub Desktop tutorial” or “Git basics” on YouTube can yield more tips.  
   - Don’t hesitate to open a new **issue** in this repo if you have questions about the workflow.

---

## 7. Common Pitfalls

- **Forgetting to Pull**  
  - Always **Pull** (fetch updates) before starting new work, or you may overwrite teammates’ changes.  
- **Merge Conflicts**  
  - Common in collaborative projects. They aren’t a crisis—just carefully resolve them in your text editor.  
- **Huge Unstructured Commits**  
  - Try not to commit dozens of unrelated files at once. It makes reviews harder.  
- **Editing Directly on Main**  
  - This can cause confusion if you accidentally push half-baked changes. Branching is safer.

---

## 8. More Resources

- [Git and GitHub Crash Course (YouTube)](https://www.youtube.com/watch?v=8Dd7KRpKeaE)  
  Comprehensive intro—if you’re brand new, start here.
- [GitHub Docs](https://docs.github.com/en)  
  Official docs with step-by-step guides and troubleshooting tips.

---

**That’s it!** With GitHub Desktop and the basic Git/GitHub workflow, you can track revisions, collaborate seamlessly, and build robust trading strategies without worrying about losing or overwriting work. If you have any questions, open a GitHub **issue** or ask a teammate.



# Videos & Timestamps


## How to Use Git & GitHub Desktop Tutorial for Beginners

This video serves as a helpful tutorial for individuals interested in learning how to use GitHub Desktop. It guides viewers through the entire process, from downloading and installing the software to creating new projects, managing code changes, and synchronizing them with the cloud. With clear explanations and demonstrations, this video empowers users to effectively utilize GitHub for organizing and tracking their development projects, making it an excellent resource for beginners.

Below is the outline with updated timestamps for the YouTube video: [`How to Use Git & GitHub Desktop Tutorial for Beginners`](https://www.youtube.com/watch?v=MaqVvXv6zrU).

---

1. **Setting up GitHub Desktop:**

   - Download and Install GitHub Desktop: [0:43](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=43s)  
   - Sign in to GitHub: [1:17](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=77s)

2. **Creating a Local Git Repository:**

   - Initialize a New Repository: [2:32](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=152s)  
   - Add Necessary Files (README, License, etc.): [2:42](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=162s)

3. **Managing Files with Git:**

   - Show Repository in Explorer: [3:45](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=225s)  
   - Create a New File: [4:13](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=253s)  
   - Stage and Commit Changes: [5:26](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=326s)

4. **Sharing Your Code on GitHub:**

   - Push to GitHub: [8:59](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=539s)  
   - Publish Repository: [9:29](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=569s)

5. **Working with Remote Repositories:**

   - Understand Cloning: [8:36](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=516s)  
   - Pull Changes: [11:19](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=679s)

6. **Advanced Commit History Management:**

   - Revert Commits: [12:46](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=766s)  
   - Amend Commits: [14:00](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=840s)

7. **Isolated Development with Branches:**

   - Understand Branching: [17:17](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=1037s)  
   - Create a New Branch: [17:29](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=1049s)  
   - Add Files to the Branch: [18:46](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=1126s)  
   - Switch Branches: [19:53](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=1193s)

8. **Merging Branches:**

   - Understand Merging: [23:05](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=1385s)  
   - Merge a Branch into the Current Branch: [23:12](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=1392s)  
   - Merge Multiple Branches: [23:33](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=1413s)  
   - Delete Branches: [23:51](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=1431s)

9. **Collaborative Work with Pull Requests:**

   - Understand Pull Requests: [27:34](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=1654s)  
   - Create a Pull Request: [27:57](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=1677s)  
   - Review and Merge Pull Requests: [28:27](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=1707s)

10. **Git Fundamentals Recap:**

   - Key Git Functions: [16:36](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=996s)

11. **Additional Resources:**

   - TheServerSide Tutorials: [32:25](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=1945s)  
   - Twitter Updates: [32:43](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=1963s)  
   - Books by the Author: [32:53](https://www.youtube.com/watch?v=MaqVvXv6zrU&t=1973s)

This more detailed outline provides a more structured overview of the video, focusing on the specific steps and concepts covered.



## Git, Github, & Github Desktop for beginners video

Video Outline: [`Git, GitHub, & GitHub Desktop for beginners`](https://www.youtube.com/watch?v=8Dd7KRpKeaE)

---

1. Introduction ([0:35](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=35s))

- What is Git? ([0:38](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=38s))
- What is GitHub? ([1:30](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=90s))
- What is GitHub Desktop? ([2:48](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=168s))

2. Setting up GitHub Desktop ([2:48](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=168s))

- Download the app: https://desktop.github.com ([2:47](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=167s))
- Sign in to your GitHub account ([2:51](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=171s))
- Set global Git configuration ([3:36](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=216s))
- Save your settings. ([4:02](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=242s))

3. Basic Git Workflow: Create, Commit, Publish ([4:12](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=252s))

- Creating a new repository ([4:19](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=259s))
- Adding files to the repository ([7:56](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=476s))
- Creating a commit ([8:42](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=522s))
- Publishing the repository to GitHub ([9:44](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=584s))

4. Understanding GitHub ([10:02](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=602s))

- Repository information ([10:22](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=622s))
- Commit history ([10:35](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=635s))
- File browsing ([11:11](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=671s))

5. Ignoring Files ([11:38](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=698s))

- Unchecking the staging box ([11:57](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=717s))
- Adding files to .gitignore ([12:12](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=732s))
- Using wildcards in .gitignore ([13:07](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=787s))
- Committing and pushing changes ([13:30](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=810s))

6. Updating Files ([14:19](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=859s))

- Git's tracking of modifications ([14:44](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=884s))
- Committing and pushing changes ([15:06](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=906s))

7. Deleting Files and Reverting Commits ([15:38](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=938s))

- Deleting files ([15:43](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=943s))
- Committing the deletion.
- Reverting commits ([16:24](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=984s))
- Pushing changes ([16:50](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=1010s))

8. Branching ([17:01](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=1021s))

- What are branches? ([17:07](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=1027s))
- Creating a new branch ([18:22](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=1102s))
- Making changes in a branch ([18:46](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=1126s))
- Switching branches ([19:16](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=1156s))
- Merging branches ([19:47](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=1187s))
- Pushing changes ([20:29](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=1229s))

9. Pull Requests ([20:42](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=1242s))

- What are pull requests? ([20:49](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=1249s))
- How they're used in team development ([20:58](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=1258s))

10. Conclusion ([21:41](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=1301s))

- Recap of concepts ([21:41](https://www.youtube.com/watch?v=8Dd7KRpKeaE&t=1301s))
