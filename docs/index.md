# Welcome to the UKSI Code Guide!

These pages will be continually updated to include best practice guidance for those working in the UK Sport Institute and wider high performance system. Explore this website for any support you might need and let us know if you spot anything you think we ought to be aware of! 

# Best Practice 
There are many different ways and places to code but variation risks losing understanding. This guide exists to try and ensure the legacy of any code written for the future benefit of the sport it was written to support and anyone who works on it. 

Below are the recommended systems for UKSI users. More information can be found in the [Local Setup Page](https://github.com/English-Institute-of-Sport/UKSI_code_guide/blob/main/docs/Setup/Local%20Setup.md). We will update these with additional information and pros/cons over the coming months.

We primarily support:
- Language: python
- IDE: VS Code 
- Project management tool: uv
    

## Start here (new users)
If you're just getting going, work through these in order — each links to a page with the detail:

1. **Set up your GitHub account** and [enable 2FA](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa), then ask to be added to the EIS GitHub Organisation.
2. **Install your tools:** [VS Code, GitHub Desktop and uv](Setup/Local_Setup.md).
3. **Create your first project** from the [Project Setup Guide](Setup/Project_Setup_Guide.md).
4. **Learn the GitHub workflow** in [Version Control](Coding_Guidelines/Version_Control.md) — how to commit and push your work (you can do it all by clicking buttons, no command line needed). Branches, pull requests and reviews are there too for when you start working with others.
5. **Follow the daily workflow** below every time you sit down to code.

Unsure what a word like *repo*, *branch* or *pull request* means? See the [Glossary](Setup/Glossary.md).

## Why GitHub, for every project
Even a project only you will ever touch belongs in a GitHub **repository**. It gives you a cloud backup, a full history to roll back to, and one clear place to find the latest version. **Please don't share code by email or shared drives** — put it in a repo. More on this in [Version Control](Coding_Guidelines/Version_Control.md).

## Daily Workflow
1. pull latest
2. uv sync
3. write/edit scripts as needed
4. uv run tests/lint
5. commit with clear message
6. open pull request

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

## Office Hours
Stuck on Git, an error, or anything else? Come along to the **coding office hours every Thursday morning at 10am**, or get in touch with someone from the data team.

