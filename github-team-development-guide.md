# GitHub and Team Development Basics – Practical Guide for Developers

This guide is designed for developers who are new to team development workflows. It covers essential concepts and practices that will help you work effectively in a collaborative development environment.

---

## 1. What is Git and GitHub?

### What is Git?

Git is a version control system. Think of it as a time machine for your code. Every time you save your work (called a "commit"), Git takes a snapshot of your files. If something goes wrong, you can go back to any previous snapshot.

Git runs on your computer and tracks changes to your code files. It helps you:
- Keep a history of all changes
- Work on different features without breaking existing code
- Merge changes from multiple developers
- Revert to previous versions if needed

### What is GitHub?

GitHub is a website that hosts Git repositories in the cloud. While Git is the tool that tracks changes, GitHub is the platform where you store your code online and collaborate with others.

Think of Git as the engine of a car, and GitHub as the garage where you park it. Git does the work of tracking changes, while GitHub provides:
- Online storage for your code
- A place for team members to access the same codebase
- Tools for code review and collaboration
- A web interface to view your project history

### Difference between Git and GitHub

- **Git**: A command-line tool installed on your computer that tracks file changes locally
- **GitHub**: A cloud-based platform that stores Git repositories and provides collaboration features

You can use Git without GitHub (working locally only), but GitHub makes it easy to share code and collaborate with a team.

### What is Version Control?

Version control is a system that records changes to files over time. Imagine writing a document and saving multiple versions:
- Document_v1.docx
- Document_v2.docx
- Document_final.docx
- Document_final_really.docx

Version control does this automatically and intelligently. Instead of creating multiple copies, it tracks what changed between versions. This means:
- You can see exactly what changed and when
- You can compare different versions
- You can merge changes from different people
- You can revert to any previous state

### Simple Analogy for Repository and Version History

Think of a repository (or "repo") as a filing cabinet for a project:

- **Repository**: The entire filing cabinet containing all project files
- **Commit**: A snapshot of the filing cabinet at a specific moment in time
- **Branch**: A separate drawer in the filing cabinet where you can organize related changes
- **Version History**: The logbook that records every time someone opened a drawer, added files, or made changes

When you make a commit, you're essentially taking a photo of the filing cabinet and labeling it with a message like "Added user login feature" or "Fixed payment bug." Later, you can look at any photo to see exactly what the project looked like at that moment.

---

## 2. What is an IDE?

### What IDE Means

IDE stands for Integrated Development Environment. An IDE is a software application that provides everything you need to write, test, and debug code in one place.

While you could write code in a simple text editor like Notepad, an IDE gives you powerful tools that make development much easier and faster. Think of it as the difference between using a basic calculator versus a scientific calculator with advanced functions.

### Examples of Popular IDEs

Different programming languages and projects often use different IDEs:

- **Visual Studio Code (VS Code)**: A lightweight, free IDE that works with many languages (Python, JavaScript, TypeScript, Go, etc.). Very popular for web development and general-purpose coding.

- **PyCharm**: Specifically designed for Python development. Available in free (Community) and paid (Professional) versions.

- **IntelliJ IDEA**: A powerful IDE primarily for Java development, but supports many other languages through plugins.

- **Other examples**: Eclipse, Xcode (for macOS/iOS), Android Studio (for Android development)

### Simple Analogy

Imagine you're building a piece of furniture:

- **Text Editor**: Like having only a hammer - you can do the work, but it's slow and difficult
- **IDE**: Like having a complete workshop with a hammer, saw, measuring tape, drill, and all the tools organized and ready to use

An IDE provides:
- **Code Editor**: Where you write your code with syntax highlighting (colors that make code easier to read)
- **File Explorer**: Navigate through your project files easily
- **Terminal/Console**: Run commands and see output without leaving the IDE
- **Debugger**: Step through your code line by line to find bugs
- **Git Integration**: See file changes, commit, and push code directly from the IDE
- **Extensions/Plugins**: Add features like linters, formatters, and language support

### How IDE Connects to GitHub

Modern IDEs have built-in Git and GitHub integration. This means you can perform most Git operations without using the command line.

Common IDE features for GitHub:
- View which files have changed (highlighted in different colors)
- Stage files for commit (select which changes to include)
- Write commit messages
- Push code to GitHub
- Pull latest changes from GitHub
- Create and switch between branches
- View commit history
- Resolve merge conflicts with a visual interface

### Setting Up GitHub Account Inside IDE

Most IDEs allow you to authenticate with GitHub directly:

1. **Sign in through IDE**: The IDE will open a browser window where you log in to GitHub
2. **Token Authentication**: Some IDEs use personal access tokens (like a password for applications)
3. **SSH Keys**: For more secure, password-less authentication

Once connected, the IDE remembers your credentials and can push/pull code automatically.

### SSH vs HTTPS (Basic Explanation)

When connecting to GitHub, you have two main options:

**HTTPS**:
- Uses your GitHub username and password (or token)
- Easier to set up initially
- Works through firewalls easily
- Requires entering credentials periodically

**SSH**:
- Uses cryptographic keys instead of passwords
- More secure for automated processes
- Set up once, then works without entering passwords
- Requires initial configuration of SSH keys

For beginners, HTTPS is simpler to start with. As you become more comfortable, SSH provides a smoother workflow. Most IDEs support both methods and can guide you through the setup process.

---

## 3. Creating a Repository (Lead Developer Responsibilities)

When starting a new project, the lead developer or project manager typically creates the initial repository. This section explains what needs to be considered during repository setup.

### Repository Name

Choose a clear and meaningful name that describes what the project does. Good repository names are:
- **Descriptive**: `user-authentication-service` instead of `project1`
- **Consistent**: Follow team naming conventions (e.g., all lowercase, use hyphens)
- **Searchable**: Easy to find when looking through multiple repositories

Examples:
- `payment-processing-api`
- `data-pipeline-etl`
- `customer-dashboard-frontend`

Avoid:
- Generic names like `test`, `new-project`, `my-app`
- Names with personal identifiers unless it's a personal project
- Names that don't indicate the project's purpose

### Description

The repository description appears on GitHub's main page and helps team members understand what the project is about. A good description is:
- One to two sentences explaining the project's purpose
- Mentions the main technology stack if relevant
- Clear enough for new team members to understand quickly

Example: "REST API service for user authentication and authorization. Built with Python FastAPI and PostgreSQL."

### Public vs Private

**Private Repository**:
- Only invited team members can see and access the code
- Required for proprietary code, internal tools, or projects with sensitive data
- Most company projects should be private

**Public Repository**:
- Anyone on the internet can view the code
- Used for open-source projects, portfolio pieces, or public documentation
- Be careful: never commit secrets or credentials to public repos

For most team projects, start with a private repository. You can always make it public later if needed.

### README

A README file (README.md) is the first thing people see when they visit your repository. It should include:
- Project overview and purpose
- Setup instructions (how to install dependencies, configure environment)
- How to run the project locally
- Basic usage examples
- Important notes or warnings

Think of README as the instruction manual for your project. Without it, new team members will struggle to understand how to get started.

### License (Optional)

A license tells others how they can use your code. Common choices:
- **MIT License**: Very permissive, allows almost any use
- **Apache 2.0**: Similar to MIT but includes patent protection
- **GPL**: Requires derivative works to also be open source
- **Proprietary**: No license means all rights reserved

For internal company projects, you may not need a license. For open-source projects, always include a license.

### .gitignore (Why It Matters)

The `.gitignore` file tells Git which files and folders to ignore and not track. This is critical because:

**Why it matters**:
- Prevents committing sensitive files (passwords, API keys, tokens)
- Avoids tracking generated files (compiled code, build artifacts)
- Keeps the repository clean and focused on source code
- Reduces repository size by excluding large unnecessary files

**Common files to ignore**:
- Environment files: `.env`, `.env.local`
- IDE settings: `.vscode/`, `.idea/`, `*.swp`
- Python: `__pycache__/`, `*.pyc`, `venv/`, `.pytest_cache/`
- Node.js: `node_modules/`, `dist/`, `.next/`
- OS files: `.DS_Store` (macOS), `Thumbs.db` (Windows)
- Logs: `*.log`, `logs/`
- Database files: `*.db`, `*.sqlite`

**Example**: If you commit a file with database credentials, anyone with repository access can see those credentials. If that file is later made public or accessed by unauthorized users, your database is compromised. The `.gitignore` file prevents this mistake.

### GitHub Secrets (for API Keys, Tokens, Credentials)

GitHub Secrets are encrypted variables stored in your repository settings. They are used for:
- Storing API keys and tokens securely
- Providing credentials to CI/CD pipelines
- Keeping sensitive configuration out of code

**How it works**:
- Secrets are encrypted and only accessible to authorized workflows
- They never appear in logs or code
- They can be updated without changing code

**What should be secrets**:
- Database passwords
- API keys (AWS, Stripe, etc.)
- Authentication tokens
- Third-party service credentials
- Encryption keys

**What should NOT be secrets**:
- Public configuration values
- Non-sensitive environment variables
- Default values that are safe to expose

Always use GitHub Secrets for any value that could be used maliciously if exposed.

### Adding Collaborators

After creating a repository, you need to add team members as collaborators. This gives them access to the repository.

**How to add collaborators**:
1. Go to repository Settings
2. Click on "Collaborators" or "Manage access"
3. Click "Add people"
4. Enter GitHub usernames or email addresses
5. Assign appropriate permission level

### Roles and Permissions

GitHub provides different permission levels for team members:

**Read**:
- Can view and clone the repository
- Cannot make changes or push code
- Suitable for stakeholders, designers, or external reviewers who only need to view code

**Triage**:
- All Read permissions, plus:
- Can manage issues and pull requests
- Can add labels and assignees
- Cannot push code or merge PRs
- Suitable for project managers or QA team members

**Write**:
- All Triage permissions, plus:
- Can push code to branches (except protected branches like main)
- Can create branches and pull requests
- Cannot delete branches or change repository settings
- Standard permission for developers working on the project

**Maintain**:
- All Write permissions, plus:
- Can manage repository settings (except dangerous operations)
- Can manage releases and packages
- Cannot delete the repository or transfer ownership
- Suitable for senior developers or tech leads

**Admin**:
- Full access to everything
- Can delete the repository
- Can manage all settings and access
- Should be limited to repository owners and senior technical leadership

### Who Should Get What Access Level and Why

**Read**: Stakeholders, external consultants who need visibility only, documentation writers who need to reference code.

**Triage**: Project managers, QA engineers, product managers who need to manage issues and track progress but don't write code.

**Write**: All active developers working on the project. This is the standard permission for team members contributing code.

**Maintain**: Senior developers, tech leads, or developers responsible for repository maintenance and releases.

**Admin**: Repository creator, CTO, or senior technical leadership who need full control over the repository.

**Best Practice**: Start with the minimum permission needed. You can always increase permissions later. It's easier to grant more access than to recover from someone accidentally deleting important code.

---

## 4. Cloning a Repository

### What Git Clone Means

Cloning a repository means creating a complete copy of a remote repository (like one on GitHub) on your local computer. When you clone, you download:
- All the code files
- The complete version history
- All branches
- Configuration files

Think of cloning like downloading a complete backup of a shared document folder. You get everything, not just the current version, but the entire history of changes.

### Why Cloning is Needed

Before you can work on a project, you need the code on your computer. Cloning is the standard way to:
- Get started on an existing project
- Work on code locally in your IDE
- Make changes and test them on your machine
- Contribute to a team project

Without cloning, you'd have to manually download files one by one, and you wouldn't have access to Git's version control features.

### Basic Example Command

The basic command to clone a repository is:

```bash
git clone <repository-url>
```

**HTTPS example**:
```bash
git clone https://github.com/company/project-name.git
```

**SSH example**:
```bash
git clone git@github.com:company/project-name.git
```

**What happens**:
1. Git creates a new folder with the repository name
2. Downloads all files and history into that folder
3. Sets up the connection to the remote repository (GitHub)
4. You're now ready to work on the code

### What Happens After Cloning

After cloning, you'll have:
- A local folder containing all project files
- A connection to the remote repository (called "origin")
- Access to all branches (though you'll be on the default branch, usually `main`)
- The ability to make changes, commit, and push

**Important**: After cloning, you're working with your own local copy. Changes you make won't affect others until you push them to GitHub.

### Why You Should Pull Before Starting Work

Before you start making changes, always pull the latest changes from the remote repository. This ensures you're working with the most up-to-date code.

**Command**:
```bash
git pull
```

**Why this matters**:
- Other team members may have added new features or fixed bugs
- The code you cloned might be hours or days old
- Starting with outdated code can cause conflicts later
- You might accidentally duplicate work that's already been done

**Best Practice**: Make pulling a habit. Every time you start working on a project, run `git pull` first. This is especially important if you haven't worked on the project in a while or if multiple people are actively contributing.

**What `git pull` does**:
- Fetches the latest changes from GitHub
- Merges those changes into your current branch
- Updates your local files to match the remote repository

If someone else modified the same files you're working on, Git will either merge the changes automatically (if they don't conflict) or ask you to resolve conflicts manually.

---

## 5. Branches Explained Clearly

### What is a Branch?

A branch is an independent line of development. Think of it as creating a parallel timeline where you can make changes without affecting the main codebase.

Imagine you're writing a book:
- **Main branch**: The published version that everyone reads
- **Feature branch**: A draft copy where you experiment with a new chapter
- If the new chapter works well, you merge it into the main book
- If it doesn't work, you can discard the draft without affecting the published book

In Git, branches allow multiple developers to work on different features simultaneously without interfering with each other's work.

### Why Branches Exist

Branches solve several critical problems in team development:

**Isolation**: Work on new features without breaking existing, working code. If your feature has bugs, it doesn't affect the main codebase.

**Collaboration**: Multiple developers can work on different features at the same time without conflicts.

**Experimentation**: Try new approaches or test ideas without risk. If it doesn't work, simply delete the branch.

**Code Review**: Changes are made in branches, reviewed via Pull Requests, and only merged when approved.

**Stability**: The main branch stays stable and deployable while new work happens in branches.

### main vs master (History Explanation)

Historically, Git's default branch was named `master`. In 2020, GitHub and many organizations changed the default branch name to `main` to use more inclusive language.

**Current Standard**: Most new repositories use `main` as the default branch name.

**Legacy Projects**: Older repositories may still use `master`. Both names function identically - it's just a naming convention.

**What to Use**: Follow your team's convention. If starting a new project, use `main`. If working on an existing project, use whatever branch name the project already uses.

### develop Branch

The `develop` branch (sometimes called `dev`) is typically where ongoing development work is integrated before it reaches production.

**Purpose**:
- Integration branch for completed features
- Testing ground for new code before it goes to production
- More stable than feature branches, but not as stable as `main`

**Workflow**: Feature branches → develop → main

**When to use**: Teams that want an extra layer between feature development and production. Not all teams need this branch.

### staging Branch

The `staging` branch is used for final testing before production deployment.

**Purpose**:
- Mirrors production environment for testing
- Final quality assurance before release
- Used to verify that all features work together

**Workflow**: develop → staging → main

**When to use**: Teams that need thorough testing before production releases. Smaller teams might skip this and go directly from develop to main.

### Feature Branches

Feature branches are where individual features or tasks are developed.

**Purpose**:
- Isolated development of a single feature or bug fix
- Allows multiple developers to work simultaneously
- Easy to review, test, and merge when complete

**Workflow**: Create from `main` or `develop` → develop feature → create Pull Request → merge back

**Naming**: Should follow a clear convention (see Branch Naming Conventions below)

**Lifecycle**: Created when starting work, merged when complete, then deleted

### Hotfix Branches

Hotfix branches are used for urgent fixes that need to go directly to production.

**Purpose**:
- Fix critical bugs in production quickly
- Bypass normal development workflow for emergencies
- Applied to both production (`main`) and development branches

**When to use**: Production is broken and needs immediate fixing. Regular bugs should go through normal feature branch workflow.

**Workflow**: Create from `main` → fix bug → merge to `main` and `develop` → deploy

### Which Branches are Required vs Optional

**Required Branches**:
- **main** (or master): Always required. This is your production-ready code.

**Common Optional Branches**:
- **develop**: Useful for teams with multiple active features. Small teams might skip this.
- **staging**: Useful for teams that need thorough pre-production testing. Many teams skip this.
- **feature branches**: Essential for any team with multiple developers. Always use these.
- **hotfix branches**: Only needed if you have production deployments. Not needed for projects still in development.

**Recommendation for Small Teams (2-5 developers)**:
- `main`: Production code
- Feature branches: One per task/feature
- Optional: `develop` if you want a testing branch

**Recommendation for Larger Teams (6+ developers)**:
- `main`: Production code
- `develop`: Integration branch
- Feature branches: One per task/feature
- Optional: `staging` for final testing

### Suggested Branch Strategy

**Small Team Strategy**:
```
main (production)
  └── feature/user-login
  └── feature/payment-integration
  └── fix/auth-bug
```

Workflow: Feature branches merge directly to `main` after review.

**Larger Team Strategy**:
```
main (production)
  └── develop (integration)
      └── feature/user-login
      └── feature/payment-integration
      └── fix/auth-bug
  └── staging (pre-production testing)
```

Workflow: Feature branches → `develop` → `staging` → `main`

Choose the strategy that fits your team size and deployment needs. Start simple and add branches as your workflow requires them.

### Branch Naming Conventions

Consistent naming makes it easy to understand what each branch is for. Here are common conventions:

**Feature branches**:
```
feature/login-api
feature/user-dashboard
feature/payment-processing
```

**Bug fix branches**:
```
fix/auth-timeout
fix/payment-error
bug/login-redirect-issue
```

**Hotfix branches**:
```
hotfix/critical-security-patch
hotfix/database-connection-fix
```

**Chore/maintenance branches**:
```
chore/update-dependencies
chore/refactor-auth-module
chore/update-documentation
```

**Format**: `<type>/<short-description>`

**Common types**:
- `feature/`: New functionality
- `fix/` or `bug/`: Bug fixes
- `hotfix/`: Urgent production fixes
- `chore/`: Maintenance tasks, dependency updates
- `refactor/`: Code improvements without changing functionality
- `docs/`: Documentation updates
- `test/`: Adding or updating tests

### Why Consistency Matters

Consistent branch naming provides several benefits:

**Clarity**: Anyone can immediately understand what a branch is for by its name.

**Organization**: Easy to find and manage branches when there are many active branches.

**Automation**: CI/CD pipelines can automatically detect branch types and run appropriate tests or deployments.

**Team Communication**: Reduces confusion during code reviews and team discussions.

**Best Practice**: Agree on a naming convention with your team and stick to it. Document it in your README or team wiki so everyone follows the same pattern.

---

## 6. Proper Commits

### What is a Commit?

A commit is a snapshot of your code at a specific point in time. When you commit, you're saving your changes to the Git history with a message describing what you did.

Think of a commit like saving a game with a descriptive save name. Instead of "save1" or "checkpoint", you write "defeated dragon boss" or "completed level 3". Later, you can return to that exact state and understand what had been accomplished.

Each commit includes:
- The changes you made (which files were modified and how)
- A commit message explaining what and why
- Your name and timestamp
- A unique identifier (commit hash)

### Why Small Commits are Better

Small, focused commits are much better than large, sweeping commits. Here's why:

**Easier to Review**: Reviewers can understand small changes quickly. A commit that changes 50 files across 10 features is overwhelming and error-prone.

**Easier to Debug**: If a bug appears, you can identify which specific commit introduced it. With large commits, you have to search through many changes.

**Easier to Revert**: If something breaks, you can revert just the problematic commit without undoing unrelated work.

**Better History**: The commit history tells a clear story of how the project evolved. Large commits create gaps in understanding.

**Less Conflict**: Smaller commits reduce the chance of merge conflicts with other developers' work.

**Example of Bad Practice**:
```
Commit: "Updated everything"
- Changed 30 files
- Added 5 features
- Fixed 10 bugs
- Updated dependencies
- Refactored 3 modules
```

**Example of Good Practice**:
```
Commit 1: "Add user authentication endpoint"
Commit 2: "Add password validation rules"
Commit 3: "Add unit tests for authentication"
Commit 4: "Update dependencies in requirements.txt"
```

Each commit does one thing and does it well.

### Commit Message Format Suggestions

A good commit message clearly explains what changed and why. Here are some format suggestions:

**Basic Format**:
```
<type>: <short description>

<optional longer explanation>
```

**Common Types**:
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, no logic change)
- `refactor`: Code restructuring without changing functionality
- `test`: Adding or updating tests
- `chore`: Maintenance tasks (dependencies, config)
- `perf`: Performance improvements

**Examples**:
```
feat: Add user login API endpoint

Implements POST /api/auth/login endpoint with email and password
authentication. Returns JWT token on successful login.

fix: Resolve timeout error in payment processing

The payment service was timing out after 30 seconds. Increased
timeout to 60 seconds and added retry logic for failed requests.

docs: Update API documentation for user endpoints

Added examples and parameter descriptions for all user-related
endpoints in the API documentation.
```

### Examples of Good vs Bad Commit Messages

**Bad Commit Messages**:

```
"update"
```
Problem: Too vague. What was updated?

```
"fix"
```
Problem: What was fixed? Why was it broken?

```
"changes"
```
Problem: Meaningless. Every commit has changes.

```
"WIP"
```
Problem: "Work in Progress" doesn't explain what you're working on.

```
"asdf"
```
Problem: Not professional and provides no information.

```
"Fixed the thing that was broken"
```
Problem: Too vague. What thing? How was it broken?

**Good Commit Messages**:

```
feat: Add password reset functionality

Users can now request password reset via email. Includes:
- Password reset request endpoint
- Email template with reset link
- Token expiration after 1 hour
- Password validation on reset
```

```
fix: Resolve memory leak in data processing job

The ETL job was not releasing database connections after use,
causing memory to accumulate over time. Added proper connection
cleanup in finally blocks.
```

```
refactor: Extract authentication logic into separate service

Moved authentication methods from UserController to AuthService
to improve separation of concerns and enable reuse across modules.
```

```
docs: Add setup instructions for local development

Updated README with step-by-step instructions for setting up
the development environment, including required environment
variables and database setup.
```

### Why "update" or "fix" Alone is Bad Practice

Single-word commit messages like "update" or "fix" are problematic because:

**No Context**: Future you (or your teammates) won't remember what was updated or fixed. When looking at commit history months later, these messages are useless.

**Hard to Search**: If you need to find when a specific feature was added or bug was fixed, vague messages make searching impossible.

**Poor Code Review**: Reviewers can't understand the purpose of changes from the commit message alone.

**Difficult Debugging**: When a bug appears, you can't easily identify which commit might have introduced it.

**Unprofessional**: Vague commit messages suggest carelessness and lack of attention to detail.

**Better Approach**: Always include:
- What was changed (specific files or features)
- Why it was changed (the problem it solves)
- Context if needed (related issues, dependencies)

**Remember**: Commit messages are communication. They help your future self and your teammates understand the project's evolution. Take the extra 30 seconds to write a clear message - it saves hours of confusion later.

---

## 7. Pull Requests (PR)

### What is a Pull Request?

A Pull Request (PR) is a request to merge your branch's changes into another branch (usually `main` or `develop`). It's a way to propose changes and have them reviewed before they become part of the main codebase.

Think of a Pull Request like submitting a document for review before it's published. You've written your changes, but before they become official, someone else reviews them to ensure quality, correctness, and that they fit with the rest of the project.

A PR includes:
- The changes you made (all commits in your branch)
- A description of what you did and why
- A place for reviewers to comment and discuss
- Automated checks (tests, linting) that run automatically

### Why PR is Required

Pull Requests are essential for team development because they:

**Ensure Code Quality**: Code is reviewed by other developers before it's merged, catching bugs and issues early.

**Share Knowledge**: Reviewers learn about new features and approaches. Authors get feedback and suggestions.

**Maintain Standards**: Ensures all code follows team conventions and best practices.

**Prevent Breaking Changes**: Reviewers can spot potential issues that might break existing functionality.

**Document Decisions**: PR discussions create a record of why certain decisions were made.

**Enable Collaboration**: Team members can discuss approaches, suggest improvements, and ask questions.

**Protect Main Branch**: Prevents broken or incomplete code from reaching production.

### Who Reviews PR?

Typically, PRs are reviewed by:

**Team Members**: Other developers on the project who understand the codebase.

**Tech Lead or Senior Developer**: Someone with more experience who can provide architectural guidance.

**Code Owners**: Developers responsible for specific parts of the codebase (if using GitHub's code owners feature).

**The Author**: You review your own PR to catch mistakes before others see them.

**Best Practice**: At least one other person should review your PR before it's merged. For critical changes (security, database migrations, infrastructure), require multiple approvals.

### PR Naming Best Practices

PR titles should be clear and descriptive, similar to commit messages but more concise:

**Good PR Titles**:
```
feat: Add user authentication API endpoint
fix: Resolve timeout error in payment processing
refactor: Extract authentication logic into AuthService
docs: Update API documentation for user endpoints
```

**Bad PR Titles**:
```
"update"
"fix"
"changes"
"WIP"
"PR"
```

**Format**: `<type>: <short description>`

The title should give reviewers an immediate understanding of what the PR does.

### What Must be Inside PR Description

A well-written PR description helps reviewers understand your changes quickly. Always include:

**1. What Was Done**
- Summary of changes
- Which files were modified
- What features were added or bugs fixed

**2. Why It Was Done**
- The problem it solves
- The business need or technical requirement
- Context about why this approach was chosen

**3. How It Was Tested**
- What tests were added or updated
- How you verified the changes work
- Manual testing steps if applicable
- Screenshots or examples if relevant

**4. Related Issue**
- Link to the GitHub issue this PR addresses
- Reference ticket numbers if using external tracking

**Example PR Description**:

```markdown
## What Was Done
- Added POST /api/auth/login endpoint
- Implemented JWT token generation on successful login
- Added password validation (minimum 8 characters, must include number)
- Created AuthService to handle authentication logic

## Why It Was Done
This PR addresses issue #123. Users need to be able to log in to the application.
The authentication was previously handled by a third-party service that we're migrating away from.

## How It Was Tested
- Added unit tests for AuthService (test_auth_service.py)
- Added integration tests for login endpoint (test_login_api.py)
- Manually tested with Postman:
  - Valid credentials return 200 with JWT token
  - Invalid credentials return 401
  - Missing fields return 400
- Tested password validation rules

## Related Issue
Closes #123
```

### Code Review Basics

Code review is the process of examining someone else's code before it's merged. Here's how to approach it:

**As a Reviewer**:
- Read the PR description first to understand the context
- Review the code changes carefully
- Check for bugs, security issues, and code quality
- Look for adherence to team standards
- Provide constructive feedback
- Ask questions if something is unclear
- Be respectful and professional

**As an Author**:
- Respond to all comments
- Make requested changes or explain why you disagree
- Update the PR when you make changes
- Don't take feedback personally - it's about the code, not you

### When to Approve

Approve a PR when:
- The code is correct and solves the stated problem
- It follows team coding standards and conventions
- Tests are included and passing
- The PR description is clear and complete
- No security concerns or breaking changes
- Code is readable and maintainable
- You understand what the code does

**Approving means**: "I've reviewed this code and I'm confident it's ready to merge."

### When to Request Changes

Request changes when:
- There are bugs or logical errors
- Code doesn't follow team standards
- Security concerns exist
- Tests are missing or inadequate
- Code is unclear or hard to understand
- The PR description is incomplete
- Breaking changes aren't documented
- Performance issues are present

**Requesting changes means**: "This needs work before it can be merged. Please address my comments."

**Be Specific**: When requesting changes, explain what's wrong and suggest how to fix it. Vague comments like "this looks wrong" aren't helpful.

### Why No One Should Push Directly to main

Pushing directly to `main` (or `master`) bypasses the review process and is dangerous because:

**No Code Review**: Code goes to production without anyone else checking it for bugs or issues.

**No Quality Control**: Automated tests and checks might be skipped.

**Risk of Breaking Production**: A single mistake can break the application for all users.

**No Documentation**: Changes aren't documented through PR descriptions and discussions.

**Knowledge Silos**: Other team members don't learn about changes.

**Difficult Rollback**: If something breaks, it's harder to identify what went wrong.

**Best Practice**: Always work in a branch and create a PR, even for small changes. This maintains consistency and safety.

**Exception**: Only in true emergencies (production is down) might you push directly to main, and even then, create a PR immediately after to document what happened.

---

## 8. Project Structure Basics

A well-organized project structure makes code easier to understand, maintain, and collaborate on. This section covers common structures for different types of projects and explains why organization matters.

### A. API Project Structure

A typical API project (using Python FastAPI, Flask, or Node.js Express) might look like this:

```
api-project/
├── app/
│   ├── __init__.py
│   ├── main.py                 # Application entry point
│   ├── routes/                 # API endpoints
│   │   ├── __init__.py
│   │   ├── users.py
│   │   ├── auth.py
│   │   └── products.py
│   ├── services/               # Business logic
│   │   ├── __init__.py
│   │   ├── user_service.py
│   │   ├── auth_service.py
│   │   └── product_service.py
│   ├── models/                 # Data models/database schemas
│   │   ├── __init__.py
│   │   ├── user.py
│   │   └── product.py
│   └── core/                   # Core functionality
│       ├── __init__.py
│       ├── config.py           # Configuration
│       ├── database.py         # Database connection
│       └── security.py         # Authentication/authorization
├── tests/                      # Test files
│   ├── __init__.py
│   ├── test_users.py
│   ├── test_auth.py
│   └── conftest.py            # Pytest configuration
├── Dockerfile                  # Container definition
├── docker-compose.yml         # Multi-container setup
├── requirements.txt           # Python dependencies
├── .env.example              # Example environment variables
├── .gitignore
└── README.md
```

**Explanation**:
- `app/`: Main application code
- `routes/`: HTTP endpoints (what URLs respond to requests)
- `services/`: Business logic (what the application actually does)
- `models/`: Data structures and database schemas
- `core/`: Shared utilities and configuration
- `tests/`: Test files mirroring the app structure

### B. ETL / Data Processing Project Structure

An ETL (Extract, Transform, Load) or data processing project might look like this:

```
etl-project/
├── extract/                    # Data extraction
│   ├── __init__.py
│   ├── api_extractor.py
│   ├── database_extractor.py
│   └── file_extractor.py
├── transform/                  # Data transformation
│   ├── __init__.py
│   ├── data_cleaner.py
│   ├── data_validator.py
│   └── data_transformer.py
├── load/                       # Data loading
│   ├── __init__.py
│   ├── database_loader.py
│   └── file_loader.py
├── jobs/                       # ETL job definitions
│   ├── __init__.py
│   ├── daily_sales_job.py
│   ├── user_sync_job.py
│   └── report_generation_job.py
├── utils/                      # Shared utilities
│   ├── __init__.py
│   ├── logging_config.py
│   └── error_handling.py
├── configs/                    # Configuration files
│   ├── database_config.yaml
│   └── job_config.yaml
├── tests/
│   ├── test_extract.py
│   ├── test_transform.py
│   └── test_load.py
├── Dockerfile
├── requirements.txt
└── README.md
```

**Explanation**:
- `extract/`: Code that retrieves data from sources
- `transform/`: Code that processes and modifies data
- `load/`: Code that writes data to destinations
- `jobs/`: Complete ETL workflows that combine extract, transform, and load
- `utils/`: Shared helper functions
- `configs/`: Configuration files for different environments

### C. ML / Inference Project Structure

A machine learning or inference project might look like this:

```
ml-project/
├── models/                     # Model definitions and training
│   ├── __init__.py
│   ├── model_architecture.py
│   └── train.py
├── inference/                  # Model inference/prediction
│   ├── __init__.py
│   ├── predictor.py
│   └── api.py                 # API for serving predictions
├── preprocessing/             # Data preprocessing
│   ├── __init__.py
│   ├── feature_engineering.py
│   └── data_loader.py
├── training/                   # Training scripts and utilities
│   ├── __init__.py
│   ├── trainer.py
│   └── evaluator.py
├── data/                      # Data files (usually gitignored)
│   ├── raw/
│   ├── processed/
│   └── models/                # Saved model files
├── tests/
│   ├── test_models.py
│   ├── test_inference.py
│   └── test_preprocessing.py
├── Dockerfile
├── requirements.txt
└── README.md
```

**Explanation**:
- `models/`: Model architecture and training code
- `inference/`: Code for making predictions with trained models
- `preprocessing/`: Data preparation and feature engineering
- `training/`: Training pipeline and evaluation
- `data/`: Data files (typically excluded from Git via .gitignore)

### Why Structure Matters

A well-organized project structure provides several benefits:

**Navigation**: Developers can quickly find the code they need. If you're working on authentication, you know to look in `routes/auth.py` or `services/auth_service.py`.

**Onboarding**: New team members can understand the project quickly by following the structure.

**Maintenance**: When bugs need fixing or features need updating, the structure guides you to the right place.

**Scalability**: As the project grows, a good structure prevents it from becoming unmanageable.

**Collaboration**: Multiple developers can work on different features without stepping on each other's code.

**Testing**: Tests are easier to write and maintain when they mirror the application structure.

### Why Modular Code Matters

Modular code means breaking functionality into separate, independent pieces (modules). Each module has a specific responsibility.

**Benefits**:
- **Reusability**: Write code once, use it in multiple places
- **Testability**: Test each module independently
- **Maintainability**: Fix bugs or add features in one place without affecting others
- **Readability**: Smaller, focused files are easier to understand
- **Collaboration**: Different developers can work on different modules simultaneously

**Example**: Instead of one 2000-line file with everything, break it into:
- `auth_service.py` (200 lines) - handles authentication
- `user_service.py` (150 lines) - handles user operations
- `email_service.py` (100 lines) - handles email sending

Each file has one clear purpose.

### Avoiding Spaghetti Code

Spaghetti code is code that is tangled, hard to follow, and difficult to maintain. It happens when:
- Everything is in one or two large files
- Functions call each other in confusing ways
- Code in one place affects unrelated functionality
- No clear separation of concerns

**How to Avoid It**:
- Keep files focused on one responsibility
- Limit file size (aim for under 300-400 lines when possible)
- Use clear function and class names
- Separate concerns (database access, business logic, API endpoints)
- Don't create circular dependencies (module A imports B, B imports A)

**Signs of Spaghetti Code**:
- Files over 1000 lines
- Functions that do multiple unrelated things
- Hard to find where a bug is located
- Changing one thing breaks something unrelated
- New developers can't understand the code

### Keeping Features Isolated

Features should be isolated so that:
- Changes to one feature don't break another
- Multiple developers can work on different features simultaneously
- Testing one feature doesn't require setting up everything
- Removing or disabling a feature is straightforward

**How to Isolate Features**:
- Put feature-specific code in its own module or folder
- Use clear boundaries (interfaces, APIs) between features
- Avoid shared mutable state between features
- Each feature should have its own tests

**Example**: In an e-commerce API:
- `routes/cart.py` - shopping cart endpoints
- `routes/payment.py` - payment processing endpoints
- `services/cart_service.py` - cart business logic
- `services/payment_service.py` - payment business logic

Cart and payment are separate features. Changes to payment shouldn't affect cart functionality.

### Collaborating Without Breaking Other Modules

When working in a team, follow these practices to avoid breaking others' work:

**Work in Your Own Branch**: Never push directly to main. Create a feature branch for your work.

**Keep Changes Focused**: Don't modify files unrelated to your feature. If you need to change shared code, coordinate with the team.

**Run Tests Before Pushing**: Make sure your changes don't break existing tests.

**Pull Latest Changes**: Before starting work and before creating a PR, pull the latest code to avoid conflicts.

**Communicate Breaking Changes**: If your changes affect other modules, discuss it in team meetings or PR descriptions.

**Review Others' PRs**: Understand what others are working on to avoid conflicts.

**Use Interfaces**: When modules need to interact, use well-defined interfaces (functions, classes, APIs) rather than directly accessing internal implementation.

**Example**: If you're adding a new payment method, don't modify the cart module. Instead, create a new payment method module and integrate it through the existing payment interface.

---

## 9. Coding Standards

Coding standards are conventions that ensure consistency across a codebase. When everyone follows the same standards, code becomes more readable, maintainable, and easier to collaborate on.

### snake_case vs camelCase

Different programming languages and communities use different naming conventions:

**snake_case** (Python convention):
- Variables: `user_name`, `total_amount`, `is_authenticated`
- Functions: `get_user_data()`, `calculate_total()`, `validate_email()`
- Files: `user_service.py`, `auth_handler.py`

**camelCase** (JavaScript, Java convention):
- Variables: `userName`, `totalAmount`, `isAuthenticated`
- Functions: `getUserData()`, `calculateTotal()`, `validateEmail()`
- Files: `userService.js`, `authHandler.js`

**PascalCase** (for classes in many languages):
- Classes: `UserService`, `AuthHandler`, `PaymentProcessor`

**Best Practice**: Follow the conventions of your programming language and project. If you're writing Python, use snake_case. If you're writing JavaScript, use camelCase. Consistency within a project is more important than which convention you choose.

### Naming Consistency

Consistent naming makes code predictable and easier to understand:

**Use descriptive names**:
- Good: `calculate_total_price()`, `user_email_address`, `is_payment_valid`
- Bad: `calc()`, `email`, `valid`

**Use consistent prefixes/suffixes**:
- Boolean variables: `is_`, `has_`, `can_` (e.g., `is_active`, `has_permission`, `can_edit`)
- Functions that return data: `get_`, `fetch_`, `retrieve_` (e.g., `get_user()`, `fetch_products()`)
- Functions that set data: `set_`, `update_`, `save_` (e.g., `set_status()`, `update_profile()`)

**Avoid abbreviations unless universally understood**:
- Good: `user_id`, `database_connection`, `calculate_total`
- Bad: `usr_id`, `db_conn`, `calc_tot`

**Use the same terms throughout**:
- If you call it `user` in one place, don't call it `customer` or `account` elsewhere (unless they're different concepts)
- If you call it `fetch`, don't switch to `get` or `retrieve` for the same operation

### Separation of Concerns

Separation of concerns means each part of your code should have one clear responsibility:

**Database Access**: Code that talks to the database should only talk to the database. It shouldn't contain business logic.

**Business Logic**: Code that implements business rules should be separate from database access and API endpoints.

**API Endpoints**: Code that handles HTTP requests should only handle requests/responses. It should call business logic, not implement it.

**Example of Poor Separation**:
```python
# BAD: Everything mixed together
@app.route('/users', methods=['POST'])
def create_user():
    # Database connection
    conn = psycopg2.connect("dbname=mydb")
    cursor = conn.cursor()
    
    # Business logic
    if len(request.json['email']) < 5:
        return {"error": "Email too short"}, 400
    
    # Database operation
    cursor.execute("INSERT INTO users VALUES ...")
    conn.commit()
    
    # Response formatting
    return {"id": cursor.lastrowid, "message": "User created"}
```

**Example of Good Separation**:
```python
# GOOD: Separated concerns
# routes/users.py - Only handles HTTP
@app.route('/users', methods=['POST'])
def create_user():
    user_data = request.json
    user = user_service.create_user(user_data)
    return {"id": user.id, "message": "User created"}, 201

# services/user_service.py - Business logic
def create_user(user_data):
    if not is_valid_email(user_data['email']):
        raise ValueError("Invalid email")
    return user_repository.save(user_data)

# repositories/user_repository.py - Database access
def save(user_data):
    # Database operations only
    ...
```

### Why Large Single Files are Bad

Large files (over 500-1000 lines) become difficult to:
- Navigate and find specific code
- Understand the overall structure
- Test individual pieces
- Modify without breaking something
- Review in Pull Requests
- Collaborate on (merge conflicts become common)

**Solution**: Break large files into smaller, focused modules:
- One class or set of related functions per file
- Group related functionality together
- Aim for files under 300-400 lines when possible

### Code Readability

Readable code is code that other developers (and future you) can understand quickly:

**Use meaningful variable names**:
- `total_price = item_price * quantity` instead of `tp = ip * q`

**Add comments for "why", not "what"**:
- Bad: `x = x + 1  # increment x`
- Good: `retry_count += 1  # Retry up to 3 times before failing`

**Keep functions focused**:
- A function should do one thing
- If a function is over 50 lines, consider breaking it into smaller functions

**Use whitespace appropriately**:
- Blank lines between logical sections
- Consistent indentation
- Don't cram everything together

**Avoid deep nesting**:
- Too many nested if statements or loops are hard to follow
- Extract nested logic into separate functions

### Clean Code Basics

Clean code follows principles that make it maintainable:

**DRY (Don't Repeat Yourself)**: If you write the same code in multiple places, extract it into a function.

**KISS (Keep It Simple, Stupid)**: Simple solutions are better than clever ones. Code should be easy to understand.

**YAGNI (You Aren't Gonna Need It)**: Don't add functionality until you actually need it. Avoid over-engineering.

**Single Responsibility**: Each function, class, or module should have one reason to change.

**Fail Fast**: Validate inputs early and fail with clear error messages rather than allowing bad data to propagate.

### Code Can Start Simple, But It Must...

Even if code starts simple, it must meet these requirements:

**Not Conflict with Others' Work**:
- Work in your own branch
- Pull latest changes before starting
- Communicate about shared code changes
- Use clear interfaces between modules

**Not Modify Unrelated Modules**:
- If you're adding a payment feature, don't modify the user authentication module
- If you need changes to shared code, discuss it first
- Keep changes focused on your feature

**Be Understandable by Other Developers**:
- Use clear names
- Add comments for complex logic
- Follow project conventions
- Write self-documenting code (code that explains itself through good naming)

**Be Testable**:
- Write code that can be tested
- Avoid tightly coupled code (code that's hard to separate for testing)
- Use dependency injection when possible

**Be Maintainable**:
- Future developers (including you) should be able to modify it easily
- Changes shouldn't require understanding the entire codebase
- Clear structure and organization

**Example**: You might start with a simple function:
```python
def process_order(order):
    # Simple implementation
    total = sum(item.price for item in order.items)
    order.total = total
    return order
```

But even this simple code:
- Uses clear variable names (`order`, `total`)
- Has a single responsibility (calculate order total)
- Doesn't modify unrelated data
- Can be understood by other developers
- Can be tested independently

As requirements grow, you can extend it without breaking these principles:
```python
def process_order(order):
    validate_order(order)  # Validation
    total = calculate_total(order.items)  # Business logic
    apply_discounts(order, total)  # More business logic
    order.total = total
    save_order(order)  # Persistence
    return order
```

Each function still has one responsibility, and the code remains understandable and maintainable.

---

## 10. Pre-commit and Ruff

Automated tools help maintain code quality and consistency without requiring manual effort. This section covers two important tools: pre-commit hooks and Ruff.

### What is Pre-commit?

Pre-commit is a framework that runs checks on your code before you commit it. These checks are called "hooks" and they run automatically when you try to commit.

**How it works**:
1. You write code and try to commit
2. Pre-commit runs configured checks (linters, formatters, tests)
3. If checks pass, the commit succeeds
4. If checks fail, the commit is blocked and you see what needs to be fixed

**Think of it as**: A quality gate that prevents bad code from being committed, like a spell-checker that runs before you send an email.

**Common pre-commit hooks**:
- Code formatting (ensures consistent style)
- Linting (finds potential bugs and style issues)
- Security checks (finds hardcoded secrets, vulnerable dependencies)
- File checks (prevents committing large files, ensures proper line endings)

### What is Ruff?

Ruff is a fast Python linter and code formatter. It checks your Python code for:
- Style violations (PEP 8 compliance)
- Potential bugs (unused variables, undefined names)
- Code quality issues (complex functions, duplicate code)
- Import organization

**Why Ruff**:
- Very fast (written in Rust)
- Combines multiple tools (replaces flake8, isort, and more)
- Catches errors before they reach production
- Enforces consistent code style across the team

**What Ruff does**:
- Checks code formatting (spacing, line length, etc.)
- Finds unused imports and variables
- Detects potential bugs
- Suggests code improvements
- Can automatically fix many issues

### Why Linting Matters

Linting is the process of analyzing code for potential errors, bugs, and style issues. Here's why it matters:

**Catches Bugs Early**: Finds errors before code reaches production or even before it's reviewed.

**Enforces Consistency**: Ensures all team members write code in the same style, making it easier to read and maintain.

**Saves Time**: Automated checks are faster than manual code reviews for style issues.

**Reduces Review Burden**: Reviewers can focus on logic and architecture instead of formatting.

**Prevents Common Mistakes**: Catches issues like unused variables, undefined names, or incorrect imports.

**Example**: Without linting, you might commit:
```python
def calculate_total(items):
    total = 0
    for item in items:
        total += item.price
    return total
    unused_var = 42  # This will never execute
```

Ruff would catch that `unused_var` is never used and flag it as an issue.

### Why Formatting Consistency Matters

Consistent formatting makes code:
- **Easier to Read**: When all code looks the same, you can focus on logic instead of style differences
- **Easier to Review**: PRs show actual changes, not formatting differences
- **Easier to Maintain**: No debates about spacing or line breaks
- **More Professional**: Consistent code looks polished and well-maintained

**Example of Inconsistency**:
```python
# Developer A's code
def get_user(id):
    return db.query(User).filter(User.id==id).first()

# Developer B's code
def get_user( id ):
    return db.query(User).filter( User.id == id ).first()
```

Both do the same thing, but the formatting is different. This creates unnecessary differences in PRs and makes code harder to read.

**With consistent formatting**:
```python
# Everyone's code looks the same
def get_user(id):
    return db.query(User).filter(User.id == id).first()
```

### How These Tools Protect Code Quality Before Merging

Pre-commit and Ruff work together to ensure code quality:

**Before Commit**:
1. You write code and try to commit
2. Pre-commit runs Ruff (and other tools)
3. Ruff checks formatting and finds issues
4. If issues are found, commit is blocked
5. You fix the issues and try again
6. Once checks pass, commit succeeds

**In CI/CD Pipeline**:
1. You create a Pull Request
2. GitHub Actions (or similar) runs the same checks
3. PR can't be merged until checks pass
4. Ensures no one bypasses local checks

**Benefits**:
- **Prevents Bad Code**: Can't commit code that doesn't meet standards
- **Automatic Fixes**: Many formatting issues can be auto-fixed
- **Team Consistency**: Everyone's code follows the same rules
- **Faster Reviews**: Reviewers don't waste time on style issues
- **Fewer Bugs**: Catches potential errors before they cause problems

**Example Workflow**:
```bash
# You try to commit
git commit -m "Add user authentication"

# Pre-commit runs automatically
Ruff check: Found 3 issues
- Line 45: Unused import 'os'
- Line 67: Line too long (120 > 88)
- Line 89: Missing blank line

# Commit is blocked
# You fix the issues (or Ruff fixes them automatically)
ruff check --fix

# Try committing again
git commit -m "Add user authentication"
# Pre-commit passes, commit succeeds
```

**Best Practice**: Set up pre-commit and Ruff when starting a project. It's much easier to maintain code quality from the start than to fix formatting issues across thousands of lines later.

---

## 11. Testing Basics

Testing is the process of verifying that your code works correctly. Well-written tests catch bugs before they reach production and give you confidence when making changes.

### What is pytest?

Pytest is a popular testing framework for Python. It makes writing and running tests simple and intuitive.

**Basic test example**:
```python
# test_calculator.py
def test_add():
    assert add(2, 3) == 5

def test_subtract():
    assert subtract(5, 2) == 3
```

**Running tests**:
```bash
pytest                    # Run all tests
pytest test_file.py       # Run tests in specific file
pytest -v                 # Verbose output (shows each test)
pytest -k "test_add"      # Run tests matching pattern
```

**Why pytest**:
- Simple syntax (just use `assert`)
- Helpful error messages
- Easy to organize tests
- Supports fixtures (reusable test setup)
- Can run tests in parallel
- Integrates well with CI/CD

### Why Tests Matter

Tests provide several critical benefits:

**Catch Bugs Early**: Find problems before code reaches production, where bugs are expensive to fix.

**Prevent Regressions**: Ensure new changes don't break existing functionality.

**Documentation**: Tests show how code is supposed to be used and what it's expected to do.

**Confidence**: Make changes knowing that tests will catch if something breaks.

**Faster Development**: Automated tests run faster than manual testing.

**Team Collaboration**: Tests help other developers understand your code and verify their changes don't break yours.

**Refactoring Safety**: Tests allow you to improve code structure without fear of breaking functionality.

### Unit Tests vs Integration Tests

**Unit Tests**:
- Test individual functions or methods in isolation
- Fast to run
- Don't require external services (databases, APIs)
- Test one thing at a time
- Example: Testing a function that calculates a total

```python
def test_calculate_total():
    items = [{"price": 10}, {"price": 20}]
    assert calculate_total(items) == 30
```

**Integration Tests**:
- Test how multiple components work together
- Slower to run
- May require external services (databases, APIs)
- Test complete workflows
- Example: Testing that a user can log in through the API

```python
def test_user_login_flow():
    # Creates user, makes API request, verifies response
    user = create_test_user()
    response = client.post("/api/login", json={"email": user.email, "password": "test"})
    assert response.status_code == 200
    assert "token" in response.json()
```

**When to use each**:
- **Unit tests**: For most code - test individual functions and classes
- **Integration tests**: For critical workflows - test that components work together correctly

**Best Practice**: Write more unit tests than integration tests. Unit tests are faster and catch most bugs. Use integration tests for critical user flows.

### Running Tests Locally

Always run tests locally before committing code:

**Basic commands**:
```bash
# Run all tests
pytest

# Run specific test file
pytest tests/test_user_service.py

# Run specific test function
pytest tests/test_user_service.py::test_create_user

# Run with verbose output
pytest -v

# Stop on first failure
pytest -x

# Show print statements
pytest -s
```

**Before committing**:
1. Write or update tests for your changes
2. Run tests locally: `pytest`
3. Ensure all tests pass
4. Then commit your code

**Why run locally**: Catching test failures locally is faster than waiting for CI/CD. Fix issues immediately rather than in a failed PR.

### Running Tests Using Docker

Many projects run tests in Docker containers to ensure consistent environments:

**Why use Docker for tests**:
- Same environment for all developers
- Matches production environment
- Isolated from your local machine
- Easy to set up dependencies (databases, services)

**Common workflow**:
```bash
# Build test container
docker-compose build

# Run tests in container
docker-compose run --rm app pytest

# Or using docker directly
docker run --rm myapp pytest
```

**Benefits**:
- Everyone runs tests in the same environment
- No "works on my machine" problems
- Easy to add test databases or services
- CI/CD can use the same Docker setup

### Mocking External Services

Mocking means replacing real external services with fake versions during testing. This is essential for reliable, fast tests.

**Why mock**:
- **Speed**: Don't wait for slow external services
- **Reliability**: Tests don't fail because external service is down
- **Cost**: Don't make real API calls that cost money
- **Isolation**: Test your code, not external services
- **Control**: Simulate different scenarios (success, failure, timeouts)

**What to mock**:
- **S3**: File storage operations
- **PostgreSQL**: Database queries
- **Redis**: Caching operations
- **Authentication**: User authentication services
- **External APIs**: Third-party services
- **Email services**: Sending emails
- **Payment processors**: Payment operations

**Example: Mocking S3**:
```python
from unittest.mock import patch, MagicMock

def test_upload_file_to_s3():
    # Mock the S3 client
    with patch('boto3.client') as mock_s3:
        mock_client = MagicMock()
        mock_s3.return_value = mock_client
        
        # Your code that uses S3
        upload_file("test.txt", "bucket", "key")
        
        # Verify S3 was called correctly
        mock_client.upload_file.assert_called_once()
```

**Example: Mocking Database**:
```python
from unittest.mock import patch

def test_get_user():
    # Mock database query
    with patch('db.session.query') as mock_query:
        mock_user = User(id=1, name="Test User")
        mock_query.return_value.filter.return_value.first.return_value = mock_user
        
        # Your code that queries database
        user = get_user(1)
        
        # Verify result
        assert user.name == "Test User"
```

**Example: Mocking Authentication**:
```python
from unittest.mock import patch

def test_protected_endpoint():
    # Mock authentication
    with patch('auth.verify_token') as mock_auth:
        mock_auth.return_value = {"user_id": 1}
        
        # Your code that requires authentication
        response = client.get("/api/protected")
        
        # Verify authentication was checked
        assert response.status_code == 200
```

### Why Testing Should Use Mock Data, Not Full Production Data

**Never use production data in tests** because:

**Security Risk**: Production data contains real user information, passwords, payment details. Exposing this in tests is a security breach.

**Data Corruption**: Tests might modify or delete data, corrupting production systems.

**Performance**: Production databases are large and slow. Tests should be fast.

**Reliability**: Production data changes, making tests unpredictable and flaky.

**Legal Compliance**: Using real user data in tests may violate privacy regulations (GDPR, etc.).

**Instead, use**:
- **Test fixtures**: Predefined test data created specifically for tests
- **Factories**: Code that generates fake but realistic test data
- **Mocks**: Fake objects that simulate real data

**Example of good test data**:
```python
# test_fixtures.py - Test data
TEST_USER = {
    "id": 1,
    "email": "test@example.com",
    "name": "Test User"
}

# test_user_service.py - Using test data
def test_get_user():
    user = get_user(TEST_USER["id"])
    assert user.email == TEST_USER["email"]
```

**Best Practice**: Always use mock data or test fixtures. Never connect tests to production databases or services. Create a separate test database if you need real database functionality in integration tests.

---

## 12. Issues and Task Tracking

GitHub Issues are a built-in way to track tasks, bugs, features, and discussions. Properly using issues helps teams stay organized and ensures nothing falls through the cracks.

### What is a GitHub Issue?

A GitHub Issue is a way to track work that needs to be done. Think of it as a to-do list item that can be:
- Assigned to team members
- Labeled and categorized
- Linked to code changes (Pull Requests)
- Discussed and commented on
- Closed when completed

Issues can represent:
- **Bugs**: Something that's broken and needs fixing
- **Features**: New functionality to be added
- **Tasks**: Work that needs to be done
- **Questions**: Things that need clarification
- **Improvements**: Enhancements to existing features

### How to Write a Clear Issue

A well-written issue makes it easy for developers to understand what needs to be done. A poor issue leads to confusion, questions, and wasted time.

**Good Issue Structure**:

**Title**: Clear and specific
- Good: "User login fails with invalid email format"
- Bad: "Bug" or "Problem" or "Issue"

**Description should include**:

1. **Problem**: What is wrong or what needs to be done?
2. **Expected Outcome**: What should happen?
3. **Steps to Reproduce** (for bugs): How can someone see the problem?
4. **Acceptance Criteria**: How do we know it's done correctly?
5. **Additional Context**: Screenshots, error messages, related issues

**Example of a Good Bug Issue**:

```markdown
## Problem
User login fails when email contains uppercase letters, even though the email is valid.

## Expected Outcome
Users should be able to log in with emails in any case (test@example.com, Test@Example.com, TEST@EXAMPLE.COM).

## Steps to Reproduce
1. Go to login page
2. Enter email: Test@Example.com
3. Enter password
4. Click login
5. See error: "Invalid email format"

## Current Behavior
Login fails with "Invalid email format" error.

## Expected Behavior
Login should succeed regardless of email case.

## Acceptance Criteria
- [ ] Login works with lowercase emails
- [ ] Login works with mixed case emails
- [ ] Login works with uppercase emails
- [ ] Email validation is case-insensitive
- [ ] Tests added for case-insensitive login

## Additional Context
- Error occurs in `auth_service.py` line 45
- Related to issue #123 (email validation)
```

**Example of a Good Feature Issue**:

```markdown
## Problem
Users need to be able to reset their passwords if they forget them.

## Expected Outcome
Users can request a password reset via email and set a new password.

## Acceptance Criteria
- [ ] "Forgot password" link on login page
- [ ] Password reset request endpoint
- [ ] Email sent with reset link
- [ ] Reset link expires after 1 hour
- [ ] User can set new password via reset link
- [ ] Old password is invalidated after reset
- [ ] Tests added for password reset flow

## Additional Context
- Should use JWT tokens for reset links
- Email template needs to be designed
- Related to authentication system (issue #45)
```

### Proper Issue Structure

Every issue should follow a consistent structure:

**1. Problem**
- Clear description of what needs to be addressed
- Context about why this matters
- Current state vs desired state

**2. Expected Outcome**
- What success looks like
- How users or the system will benefit

**3. Acceptance Criteria**
- Specific, testable conditions that must be met
- Written as checkboxes: `- [ ]`
- Clear enough that anyone can verify completion

**4. Additional Context** (optional)
- Screenshots or error messages
- Related issues or PRs
- Technical notes or constraints
- Design mockups or references

### Labels

Labels help categorize and prioritize issues:

**Common Label Types**:
- **Type**: `bug`, `feature`, `enhancement`, `documentation`, `question`
- **Priority**: `high-priority`, `low-priority`, `critical`
- **Status**: `in-progress`, `blocked`, `needs-review`
- **Area**: `frontend`, `backend`, `database`, `api`
- **Size**: `small`, `medium`, `large` (effort estimation)

**Benefits of Labels**:
- Quickly filter issues by type or priority
- See what areas need attention
- Track work distribution across the team
- Identify common problem areas

### Assigning Developers

Assign issues to team members to clarify ownership:

**When to assign**:
- Someone volunteers to work on it
- Task is allocated during planning
- Developer has relevant expertise
- Work needs to be distributed

**Benefits**:
- Clear ownership and responsibility
- Prevents duplicate work
- Helps track individual workload
- Makes it easy to see who to ask questions

**Best Practice**: Don't assign issues until someone is ready to work on them. Unassigned issues can be picked up by anyone. Assign when work begins.

### Linking PR to Issue

When you create a Pull Request that addresses an issue, link them together:

**How to link**:
- In PR description, mention: `Closes #123` or `Fixes #123`
- GitHub will automatically link them
- When PR is merged, issue will be automatically closed

**Benefits**:
- Shows what code changes address which issues
- Provides context for reviewers
- Automatically closes issues when work is done
- Creates a clear history of what was fixed

**Example PR Description**:
```markdown
## Changes
- Added password reset functionality
- Implemented email sending with reset tokens
- Added password reset endpoint

## Testing
- Added unit tests for reset flow
- Tested email delivery
- Verified token expiration

Closes #123
```

**Common linking keywords**:
- `Closes #123` - Closes the issue when PR is merged
- `Fixes #123` - Same as Closes
- `Resolves #123` - Same as Closes
- `Related to #123` - Links but doesn't auto-close
- `See #123` - References issue for context

**Best Practice**: Always link PRs to issues. This creates a clear trail from problem to solution and helps track project progress.

---











