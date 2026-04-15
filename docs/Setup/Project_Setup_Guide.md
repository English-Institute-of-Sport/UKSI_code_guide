## Project Setup Guide
The setup below is inline with the Python Project Template (in progress) on the UKSI GitHub.

For new projects:  
1. Setup a Github repository. Use a [template](https://github.com/English-Institute-of-Sport/Python_Project_Template) if starting a new project, otherwise, create an empty repository.  
2. Setup your project environment using uv.  
    - ensure or navigate to the relevant root (filepath)  
    - use `uv init` in the terminal to create the relevant files for you, including a virtual environment.  
    - Run scripts or tests with `uv run ...`  
    - Add dependencies (libraries, modules) with `uv add ...`  
    - For more info go to: https://docs.astral.sh/uv/guides/projects/  
3. Clone the repository into the root of your project environment (you should see a `.git` folder in the root of your project folder). This is easiest to do in GitHub Desktop or directly in a new VS Code window.  
    - We recommend having all code stored in a "dev" folder directly on your c drive as it minimises the filepath and avoids potential issues with OneDrive storage. 
4. Your project (new or existing) should at the least contain the following files:  
    - `Readme.md` file (with contributing guideline).  
    - `.gitignore` file.  
    - `pyproject.toml` file.  
    - `uv.lock` file.  
5. Before you jump straight into the coding, remember to follow all the advice on these webpages!   

