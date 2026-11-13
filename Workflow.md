# Gymix – Development Workflow

This document explains how the Gymix development team should organize their work, use GitHub, write code, test changes, and upload their work.

The goal is to keep the project organized and avoid conflicts between team members.

# 1. GitHub Repositories

The project uses two GitHub repositories:

### 1. Gymix-Planning

This repository contains project documentation, planning files, requirements, diagrams, team distribution, and meeting notes.

### 2. Gymix

This repository contains the actual application source code.

All developers must use the Gymix repository when working on the application.

# 2. Project Board

The team will use GitHub Projects to organize and track development tasks.

The project board contains four columns:

- **Todo:** Tasks that have not started yet.
- **In Progress:** Tasks currently being developed.
- **In Review:** Tasks that are completed and waiting for review.
- **Done:** Tasks that have been reviewed and approved.

Every developer must update their task status when work progresses.

# 3. GitHub Account and Repository Access

Before starting development, every team member must:

1. Create a GitHub account at https://github.com.
2. Send their GitHub username to the project owner.
3. Accept the repository collaboration invitation.
4. Open the Gymix repository.
5. Make sure they have permission to contribute to the project.

# 4. How to Get the Project on Your Computer

Every developer must download the project repository to their computer.

### Step 1: Install Git

Download Git from:

https://git-scm.com/downloads

Install it using the default installation settings.

### Step 2: Open the Repository

1. Open the Gymix repository on GitHub.
2. Click the green Code button.
3. Copy the HTTPS repository link.

### Step 3: Clone the Repository

Open CMD or Git Bash.

Move to the folder where you want to save the project.

Example:

```bash
cd Desktop
```

Clone the repository:

```bash
git clone YOUR_REPOSITORY_URL
```

Enter the project folder:

```bash
cd Gymix
```

Now the project files are available on your computer.

**Important:** Each team member should clone the repository only once. After that, use `git pull` to get new changes.

# 5. Git Branching Strategy

The main branch contains stable and approved code.

Developers must not work directly on the main branch.

Each developer must create a separate branch for their assigned task.

### Branch Naming Examples

```text
feature/admin-dashboard
feature/member-dashboard
feature/coach-dashboard
feature/authentication
feature/subscriptions
feature/training-sessions
feature/attendance
fix/booking-validation
```

### How to Create a Branch

Before starting a new task, open the project folder and run:

```bash
git checkout main
git pull origin main
git checkout -b feature/your-feature-name
```

Example:

```bash
git checkout -b feature/admin-dashboard
```

Now you are working on your own branch.

All changes must be made on this branch.

# 6. How to Work on Your Task

Every developer must follow these steps:

### Step 1: Check Your Assigned Task

Open the GitHub Project Board.

Find your assigned task in the Todo column.

Read the task description and acceptance criteria carefully.

Move the task to In Progress when you start working.

### Step 2: Understand the Existing Code

Before changing anything:

- Check the project folder structure.
- Read the related files.
- Understand how the existing code works.
- Avoid modifying files that belong to another developer without discussion.

### Step 3: Write Your Code

Implement only the features assigned to you.

Keep your code organized and follow the project's coding standards.

Use clear names for variables, functions, classes, and files.

### Step 4: Test Your Code

**Testing is mandatory before uploading any code.**

Before committing or pushing, you must:

- Run your application locally.
- Test the feature you implemented.
- Check that it works correctly.
- Check for errors in the terminal and browser console.
- Make sure you did not break existing features.

For example:

- Frontend developers must run the React application and test their pages.
- Node.js developers must run their API and test the endpoints.
- ASP.NET Core developers must run their application and test their endpoints.

**DO NOT UPLOAD CODE THAT YOU HAVE NOT TESTED.**

**DO NOT UPLOAD CODE THAT CAUSES ERRORS.**

If the feature is not finished, do not upload it as completed work. If you need to share unfinished work for collaboration, tell the team clearly and use a separate Pull Request marked as a Draft.

# 7. How to Save and Upload Your Work

Git has three important steps:

1. Add: Select the files you want to upload.
2. Commit: Save a snapshot of your changes with a message.
3. Push: Upload your commits to GitHub.

### Step 1: Check Your Changes

```bash
git status
```

This command shows which files you modified or added.

### Step 2: Add Your Changes

```bash
git add .
```

This selects all changed files in the current repository.

Make sure you do not include passwords, API keys, database credentials, or unnecessary files.

### Step 3: Commit Your Changes

```bash
git commit -m "feat: add admin dashboard"
```

Write a clear message describing your changes.

### Step 4: Push Your Branch to GitHub

```bash
git push -u origin feature/your-feature-name
```

Example:

```bash
git push -u origin feature/admin-dashboard
```

After the first push, you can use:

```bash
git push
```

Your branch and changes are now uploaded to GitHub.

**Important:** Pushing your branch does not mean your code has been added to the main branch.

# 8. How to Create a Pull Request

After pushing your branch:

1. Open the Gymix repository on GitHub.
2. You may see a message saying your branch had recent pushes.
3. Click Compare & pull request.
4. Select your feature branch as the source.
5. Select main as the destination.
6. Write a clear Pull Request title.
7. Describe what you implemented.
8. Add the related Issue number if there is one.
9. Click Create pull request.

Example Pull Request:

**Title:**

```text
feat: implement admin dashboard
```

**Description:**

```text
## Changes
- Added admin dashboard layout.
- Added navigation sidebar.
- Added dashboard summary cards.

## Testing
- Ran the React application successfully.
- Tested dashboard navigation.
- Checked browser console for errors.
```

If the work is unfinished, create a Draft Pull Request instead of presenting it as ready for approval.

# 9. Code Review and Merging

Before merging a Pull Request into main:

1. Another team member must review the changes.
2. Check that the code follows the project structure.
3. Check that the feature works correctly.
4. Check for unnecessary or unrelated changes.
5. Request corrections if needed.
6. Approve the Pull Request when everything is correct.
7. Merge the Pull Request into main.

Only approved and tested code should be merged into main.

The developer who created the Pull Request should not merge it without the required review.

# 10. How to Get the Latest Updates

Before starting a new task, make sure your local main branch is updated.

Run:

```bash
git checkout main
git pull origin main
```

If you are starting another feature, create a new branch:

```bash
git checkout -b feature/new-feature-name
```

If you are already working on a feature branch and want to bring the latest main changes into it:

```bash
git fetch origin
git merge origin/main
```

If Git reports merge conflicts, resolve them carefully, test the application again, and then commit the resolution.

# 11. Commit Message Convention

All team members must use clear and meaningful commit messages.

Examples:

```text
feat: add member management
feat: implement login
feat: add subscription plans
fix: resolve booking validation
fix: correct session capacity
docs: update API documentation
refactor: organize backend services
style: improve dashboard layout
```

Common prefixes:

- **feat:** New feature.
- **fix:** Bug fix.
- **docs:** Documentation changes.
- **refactor:** Code restructuring.
- **style:** Formatting and visual changes.
- **test:** Adding or updating tests.

# 12. Task Management Rules

Every task must include:

- Clear title.
- Description.
- Assigned team member.
- Priority.
- Acceptance criteria.

A developer must move the task through the following stages:

```text
Todo → In Progress → In Review → Done
```

Only move a task to Done after the related Pull Request has been reviewed and merged.

# 13. Important Team Rules

All team members must follow these rules:

1. Never work directly on the main branch.
2. Never upload untested code.
3. Never merge code that causes errors.
4. Never push unfinished work as a completed feature.
5. Always test your application before committing and pushing.
6. Always use a separate branch for each feature or task.
7. Always write clear commit messages.
8. Always create a Pull Request before merging into main.
9. Review other team members' code before approving it.
10. Never upload passwords, secret keys, or database credentials.
11. Do not delete or overwrite another developer's work without discussion.
12. Communicate with the team before changing shared APIs, database structures, or project configurations.
13. Update your task status on the GitHub Project Board.
14. Pull the latest changes before starting new work.

# 14. Team Communication

The team must communicate regularly during development.

- Discuss important changes before implementation.
- Inform the team when a task is completed.
- Report errors and blockers as soon as possible.
- Coordinate API changes between frontend and backend developers.
- Agree on database changes before implementation.
- Keep project documentation updated.

# 15. Final Development Rule

**Do not upload code just because you finished writing it. Upload it only after running it, testing it, and confirming that it works correctly.**

The main branch must always remain stable and contain only reviewed and approved code.

Every team member is responsible for the quality and correctness of their own contributions.
