# Local Setup

## We recommend VS Code as an IDE
VS code can be installed directly from the Windows store if using windows.  
Although some users will be more familiar with Spyder, we are moving to recommending VS Code as our primary platform. It's integrations with Copilot, GitHub, Jupyter etc. mean it is an all-in-one solution with much more support for project management.  
While you may lament the use of a variable viewer initially, getting the hang of the debugging tool or using a notebook-based solution like Jupyter is a good solution.

## We recommend **uv** as a project management tool  
It is very easy to use and install!  
Install on Windows:

1. Search "powershell" in your windows search bar  
2. Copy this into your powershell terminal: powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"  
3. Close powershell. That's it installed!  
More [info on installation](https://docs.astral.sh/uv/getting-started/installation/) here.  

>## uv troubleshooting
>If command not found after install, restart terminal.
>If sync fails, delete .venv and run uv sync again.
>Confirm Python version via project config before syncing.
