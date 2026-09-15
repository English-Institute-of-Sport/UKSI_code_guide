# Local Setup

## We recommend VS Code as an IDE
VS code can be installed directly from the Windows store if using windows.  
Although some users will be more familiar with Spyder, we are moving to recommending VS Code as our primary platform. It's integrations with Copilot, GitHub, Jupyter etc. mean it is an all-in-one solution with much more support for project management.  
While you may lament the use of a variable viewer initially, getting the hang of the debugging tool or using a notebook-based solution like Jupyter is a good solution.

For support getting set up in VS code watch [this getting started video.](https://code.visualstudio.com/docs/introvideos/basics) 

### Recommended VS Code extensions
Install these from the Extensions panel (the squares icon in the left sidebar) to get the best experience:

- **Python** and **Pylance** — Python language support, autocomplete and error checking.
- **Black Formatter** — auto-formats your code (see the [Style Guide](../Coding_Guidelines/Style_Guide.md)).
- **Pylint** — flags style issues and likely bugs.
- **GitLens** — makes the Git history easy to see.

To format your code every time you save, open Settings (`Ctrl+,`), search for **Format On Save**, and tick it.

## We recommend **GitHub Desktop** for working with GitHub (outside of VS Code)
You do **not** need the command line to use Git. [GitHub Desktop](https://desktop.github.com/) lets you clone, commit, push, pull, branch and open pull requests by clicking buttons. VS Code's built-in **Source Control** panel does the same. Install GitHub Desktop, sign in with your GitHub account, and you're ready. See [Version Control](../Coding_Guidelines/Version_Control.md) for the workflow.

## We recommend **uv** as a project management tool  
It is very easy to use and install!  
Install on Windows:

1. Search "powershell" in your windows search bar  
2. Copy this into your powershell terminal: powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"  
3. Close powershell. That's it installed!  
More [info on installation](https://docs.astral.sh/uv/getting-started/installation/) here.  

!!! note "On macOS or Linux?"
    Install uv with:
    ```bash
    curl -LsSf https://astral.sh/uv/install.sh | sh
    ```
    See the [uv installation docs](https://docs.astral.sh/uv/getting-started/installation/) for other options.

>## uv troubleshooting
>If command not found after install, restart terminal.
>If sync fails, delete .venv and run uv sync again.
>Confirm Python version via project config before syncing.
