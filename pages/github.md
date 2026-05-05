---
title: Github
nav_order: 7
parent: Handbook   # optional grouping
---

# CMG-UA GitHub Manual

This is the GitHub page of the Center for Medical Genetics (CMG) at UZA and the University of Antwerp. If you are new here and want to collaborate on projects, take a look at these best practices and workflow guidelines.

More information about CMG can be found on the [CMG website](https://www.genetica-antwerpen.be/en/).

## Best Practices

All CMG code must be stored on GitHub, not just on the server.

**GITHUB IS NOT A DATA STORAGE PLATFORM! Do not commit files larger than 50MB.**

- Always document your code properly.
- Each project should have its own repository with a dedicated `README.md` file.
- Use special repositories for code that is commonly used across projects.

## How to Use GitHub

A useful cheat sheet for reference: [GitHub Education Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf).

### Essential Git Commands

To clone a repository on your local machine:
```bash
git clone <ssh_link_github_repository>
```

To create a new branch for making changes without modifying the original code:

```bash
git checkout -b <branch_name>
```

To check the status of your local branch:

```bash
git status
```

To add your changes to Git:

```bash
git add <your_changes>
```

To commit your changes with a descriptive message:

```bash
git commit -m "<descriptive commit message>"
```

To push your changes to GitHub:

```bash
git push
```

### Merging Your Code into the Main Branch

Once your work is complete, you need to create a **pull request** on the CMG GitHub page to merge your changes into the main branch.

Steps to create a pull request:
1. Go to the project repository and select your branch.
2. Click on **Contribute** → **Compare & pull request**.
3. Review your changes and click **Open pull request**.

**NEVER PUSH DIRECTLY TO THE MAIN BRANCH!**

### Reporting Issues

If you encounter an issue, you can create a **GitHub Issue** in the project repository.

- Be as detailed as possible to help the person resolving the issue.
- Asking questions is encouraged—your discussion may help others in the future.

To create an issue:
1. Navigate to the **Issues** tab next to the **Code** tab.
2. Click **New issue**.

### Forking Another Person’s Project

Need something from another project but can’t modify it directly? You can **fork** the repository to create your own copy. Once you’ve made your updates, submit a pull request to contribute your changes back.

### Special Repositories for Common Code

If you have code that is widely useful, place it in a common library to benefit your colleagues.

This code should be:
- Well-documented (with a `README.md` file).
- Thoroughly tested (strongly recommended).

To use a special repository in your project, you can **add it as a submodule**, which creates a soft link to the repository.

## Collaboration Workflow

Follow this workflow when working with GitHub:

1. Create your own branch from the project.
2. Clone the repository locally.
3. Modify the code or add new features.
4. Add, commit, and push your changes to your branch.
5. When ready, merge the latest changes from the main branch into your branch.
6. Fix any issues that arise after merging.
7. Once everything is resolved, submit a **pull request** to merge your branch into the main branch.

![GitHub Flow](https://media.geeksforgeeks.org/wp-content/uploads/20220214111138/GitHubFlow.jpg)  
(Source: [GeeksforGeeks](https://www.geeksforgeeks.org/git-flow-vs-github-flow/))

Kind regards,  
**Bioinformatics Team**
