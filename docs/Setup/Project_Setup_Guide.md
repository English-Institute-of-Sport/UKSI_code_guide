## Project Setup Guide
The setup below is in line with the UKSI Python Project Template on the UKSI GitHub, which comes ready with `pyproject.toml`, `uv.lock`, a `.gitignore` and a starter `README.md`.

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

    -  `Readme.md` file (with contributing guideline).  
    - `.gitignore` file.  
    - `pyproject.toml` file.  
    - `uv.lock` file.  
5. Before you jump straight into the coding, remember to follow all the advice on these webpages!   

## Starter templates
If you started from the [Python Project Template](https://github.com/English-Institute-of-Sport/Python_Project_Template) you'll already have these. If not, copy them into your project.

### `.gitignore`
Keeps data, secrets and environment files out of Git. A good starting point for Python:

```text
# Virtual environments
.venv/
env/

# Python cache
__pycache__/
*.py[cod]

# Secrets and environment variables
.env

# Data (don't commit datasets)
data/
*.csv
*.parquet

# Notebook checkpoints
.ipynb_checkpoints/

# OS / editor files
.DS_Store
.vscode/
```

### `README.md`
Tells the next person what the project is and how to run it:

```markdown
# Project name

One or two sentences on what this project does and who it's for.

## Getting started
1. Clone this repo.
2. Run `uv sync` to install dependencies.
3. Run the main script with `uv run <script>.py`.

## Contributing
- Never commit directly to `main` — work on a branch and open a pull request.
- Commit often with clear messages.
- Request a review before merging.

## Contact
Who to ask for help with this project.
```

### `pyproject.toml`
Created for you by `uv init`. It records your project's name, Python version and dependencies — you rarely edit it by hand (use `uv add`):

```toml
[project]
name = "my-project"
version = "0.1.0"
requires-python = ">=3.12"
dependencies = []
```


