# Glossary

Plain-English definitions of the terms used across this guide. If something here isn't clear, bring it to the Thursday 10am coding office hours.

## Environments and tools
| Term | Definition |
|------|------------|
| **IDE** (Integrated Development Environment) | The software you use to work on coding projects. It bundles a selection of tools — text editor, file explorer, terminal, debugger and integrations (e.g. GitHub, Jupyter, linters). We recommend **VS Code**. |
| **Local** | Working on your own computer, where code runs without needing the internet. Requires installing and maintaining tools (IDE, package manager, etc.). |
| **Browser based** | Working on code online in a browser (e.g. **Deepnote**). Nothing to install — handy while learning. |
| **Terminal** | The place you type commands directly to your computer (the "command line"). You can do most day-to-day work in this guide *without* it. |
| **uv** | The project and package manager we recommend. It creates virtual environments and installs the exact library versions a project needs. |
| **Virtual environment** | An isolated set of libraries for one project, so it runs the same on someone else's machine. Managed for you by uv. |
| **Linter** | A tool that checks your code for consistent formatting and likely errors (we use **Black** and **Pylint**). |

## Git and GitHub
| Term | Definition |
|------|------------|
| **Git** | The tool that tracks the history of changes to your project on your computer. |
| **GitHub** | The website where repositories are stored online for backup, sharing, collaboration and browsing. |
| **Repository (repo)** | A project's folder that Git tracks — its code plus full change history. Every project should be a repo. |
| **Clone** | Make a copy of a GitHub repo onto your computer. |
| **Commit** | A saved snapshot of a set of changes, with a short message describing them. |
| **Push** | Send your commits from your computer up to GitHub. |
| **Pull** | Bring the latest changes from GitHub down to your computer. Pull before you start work and before you push. |
| **Branch** | A separate line of work, so you can make changes without touching the trusted `main` version. |
| **`main`** | The trusted, working version of a project that everyone shares. Never edit it directly — use a branch and a pull request. |
| **Pull request (PR)** | A request to merge the work on your branch into `main`, so a colleague can review it first. |
| **Merge conflict** | When two changes touch the same lines and Git asks you to choose which to keep. Normal and safe — see [Version Control](../Coding_Guidelines/Version_Control.md#getting-unstuck-pulling-and-merge-conflicts). |
| **`.gitignore`** | A file listing things Git should *not* track (e.g. data, secrets, virtual environments). |
