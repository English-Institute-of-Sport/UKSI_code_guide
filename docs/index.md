# Welcome to the UKSI Code Guide!

These pages will be continually updated to include best practice guidance for those working in the UK Sport Institute and wider high performance system. 

# Best Practice 
There are many different ways and places to code but variation risks losing understanding. This guide exists to try and ensure the legacy of any code written for the future benefit of the sport it was written to support and anyone who works on it. 

Below are the recommended systems for UKSI users, listed **in bold**. We will update these with additional information and pros/cons over the coming months.

We primarily support:
> **Language: python**
> **IDE: VS Code **
> **Project management tool: uv**

## Daily Workflow
1. pull latest
2. uv sync
3. write/edit scripts as needed
4. uv run tests/lint
5. commit with clear message
6. open pull request

## Coding Guidelines
**Planning comes first**. Create and update the relevant documentation. Write out steps in comments before you code. This planning phase is vital for efficiency and clarity, and for the future legacy and readability of your code. 

1. **KISS**: Keep it simple sailor, **DRY**: Don't repeat yourself, **SRP**: [Single responsibility principle](https://towardsdatascience.com/solid-coding-in-python-1281392a6a94).
2. Use **linters** (See Style Guide - Linting - coming soon). At minimum, use Black and Pylint for all your python scripts and notebooks (pylint optional for notebooks).
3. Use a **`pyproject.toml`** and **`uv.lock`** file to keep track of the project's dependencies and their versions. 
4. Use **environment variables** for ***sensitive*** info like secret keys or passwords (i.e. Deepnote example [here](https://docs.deepnote.com/environment/environment-variables)).
5. Import all packages at the ***top*** of your script, module or notebook.
6. ***Avoid hardcoding*** variables wherever possible, but if needed, put it at the ***top*** of your script/notebook, clearly marked. 
7. Use **comments** and **docstring** in compliance with the style guide.
8. Exception names should be the ***only*** code you write that contains **capital letters**, other than constants and class names (See Style Guide - Naming - coming soon).

**For more make sure you checkout the Style Guide (in development)**. 

## Linting (formatting code)
It's good practice to format your code in a consistent way to make sure future you and others can read it easily. This can be done easily in deepnote, or locally we recommend using a function called **pylint**.

## File naming & documenting (descriptions)
Name files with snake case (lower_case_divided_by_underscores) rather than camel case (UpperCaseCharactersDivideWords).
Add in a couple of sentence description either via a Readme or at the top of your project to ensure someone else could understand the purpose without further information. 

## Version Control System (VCS)
Use **Git** and **Github** for every project. Git is used for version controlling your actual project whilst Github is used for code storage, collaboration and browsing. Once you have been invited to the EIS Github Organisation, make sure you [follow your fellow peers](https://docs.github.com/en/get-started/exploring-projects-on-github/following-people) and [enable 2FA on your own account](https://docs.github.com/en/github/authenticating-to-github/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication). 

When it comes to version controlling your code projects with **Git**, there are some best practices for you to follow:

1. **Know what you are committing**. Use a template **`.gitignore` file** and try to avoid using the `.` (dot) expression when adding files/changes to your VCS.
2. **Commit often**, **don't commit incomplete work** and **break up your commits** e.g. by purpose (i.e. one commit per bug fix, refactoring task, or feature built). It's much simpler for you, or a peer, to understand a historical commit or pull request (pr) if they are smaller and contain all the info/context needed in the one commit/pr.
3. **Write clear commit messages**. This has to include a short and concise **subject line**. So, start each commit with an imperative word that indicates best what the commit is about, and make sure it can complete this sentence: 

    `If applied, this commit will ...`
  
    First Word | Meaning
    --- | --
    Add | Create a capability e.g. feature, test, dependency.
    Cut | Remove a capability e.g. feature, test, dependency.
    Fix | Fix an issue e.g. bug, typo, accident, misstatement.
    Bump | Increase the version of something e.g. dependency.
    Refactor | A code change that MUST be just a refactoring.
    Reformat | Refactor of formatting, e.g. omit whitespace.
    Optimize | Refactor of performance, e.g. speed up code.
    Document | Refactor of documentation, e.g. help files.

    `git commit -m "Add Pandas 1.3.1"`
    
    `git commit -m "Reformat functions to include doc string"`
    
4. You should optionally include a more detailed description with your commits if it requires more context/explanation. This is extremely important when working collaboratively. To do so, simply **omit the `-m` flag** from your commit command. This will pop up your commit in a default text editor, where you'll be able to place a **subject line** followed by a text **body** that can contain additional information and links to relevant issues or cards. You can see a short [video tutorial here](https://www.loom.com/embed/efcab093bd7246cf937176108da433a7).

## Code Reviews
As a community, make sure you both request and perform frequent **code-reviews**. They provide exceptional learning opportunities, enforce better code quality, and can have positive effects on team culture. Both Deepnote and Github provide you with tools to be able to perform/receive a code review remotely and with ease. Make sure you adhere to the following guidelines:

1. Perform or request code reviews **frequently**. This will mainly assist reviewers by not giving them so much to do at once, but also help you progress quicker.
2. Only request a review once you have **tested** and **linted** (see Linting - coming soon) your code.
3. If you don't know where to begin when reviewing someone's work, start with making sure it adheres to the Style Guide. Then start thinking about the **purpose** and **implementation** of the code or PR. Do the commit messages and code effectively convey what was proposed and how it works, how well does the code read, how complex is it, is there any repeated code, do defined functions have a single responsibility, has the correct documentation been updated or produced?
4. As a reviewer, ***if*** clarity and understanding of the code is blocking your review, this ***must*** be communicated to the author, directed at the code or documentation, rather than the author.
5. As a reviewer, make comments **actionable**. Make it ***clear*** whether your comment is a question, suggestion or required change. 
6. Utilise links to existing code, external links and custom code snippets to **back up** your comments/discussions.

## Collaboration
When it comes to simple/one-off data exploration or analysis projects, we suggest setting up a real-time collaborative environment via Deepnote by simply adding your peers to the relevant project (up to 3, not including yourself). With that said, bear in mind that you can [create a Team space in Deepnote](https://docs.deepnote.com/collaboration/teams) for your specific project(s) or team(s).

For local collaboration, uv is your best friend. For existing projects you can clone a repo in VS code or GitHub Desktop, navigate to that folder in VS Code, open a new terminal and run "uv sync" and all of your project details will install themselves! It really is that simple. 

When it comes to **legacy, open source, or collaborative projects**, we suggested you additionally adopt a [Pull Request Workflow](https://guides.github.com/introduction/flow/) with your VCS (Git & Github) using the **shared repository model**. This should adhere to the following: 

1. Have **one original Github repository** that collaborators can clone and contribute too.
2. Collaborators **must** ***not*** **make changes directly to the** ***main*** **branch!**. This must be enforced (it's not automatic).
3. Collaborators must make changes via a new **branch**. Try utilise some sort of ***naming convention*** for branches (i.e. use initials and/or imperative words in the branch name: `sds/feature/automate_emails`).
4. **Pull requests** must be submitted from the relevant branch, to the main branch.
5. Keep track of your PRs. Make sure you have someone assigned to **review the PR** before merging. You can optionally squash and merge a pull request if it contains more than 5 separate commits.
6. **Delete the branch** once it has been submitted and merged.
7. If you plan on making more contributions, make sure your local project (main branch) is in **sync** with the original repo, before creating another branch.

> For a full PR flow walkthrough, see [GitHub flow](https://docs.github.com/en/get-started/quickstart/github-flow).

> 🎯 Project Management in Github
>
> Github is also a great place to manage your coding projects. Have a look at using a [project board](https://docs.github.com/en/issues/organizing-your-work-with-project-boards/managing-project-boards/about-project-boards) to organise tasks between your team. You can utilise issues for raising project bugs and suggestions. You can even activate a [project wiki](https://docs.github.com/en/communities/documenting-your-project-with-wikis/about-wikis) to house all your documentation.

## GDPR
See Code School [GDPR guidelines and membership protocols](https://github.com/English-Institute-of-Sport/BestPractice/blob/main/Code%20School%20GDPR%20guidelines%20%26%20member%20protocols.pdf).

## Using AI
Copilot is the only AI currently approved by UKSI. The below are general principles of how to use it and some examples of good time savers!
- Use as an assistant/collaborator not “auto-pilot”, keeping yourself as the decision maker.
- Always ask for explanations or don’t use code that doesn’t make sense. You cannot assume the code is 100% correct, particularly where accuracy/data protection are concerned.
- Use for repetitive or “boiler-plate” tasks to reduce chance of human error
- Use to write or improve your documentation
- SQL queries
- Unit tests

#### For further info on any of the above, get in touch with someone from the data team or come along to the coding office hours every Thursday morning at 10am.




## Pages coming soon: 
* IDE set up 
* Starting a new project
* Coding guidelines
* Version control
* Collaboration 
* Style guide

For full documentation on mkdocs visit [mkdocs.org](https://www.mkdocs.org).

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.
