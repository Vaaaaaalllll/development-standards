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
