
## Version Control System (VCS)
Use **Git** and **Github** for every project. Git is used for version controlling your actual project whilst Github is used for code storage, collaboration and browsing. Once you have been invited to the UKSI Github Organisation, make sure you [follow your fellow peers](https://docs.github.com/en/get-started/exploring-projects-on-github/following-people) and [enable 2FA on your own account](https://docs.github.com/en/github/authenticating-to-github/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication). 

!!! info "New to Git and GitHub? Read this first."
    New to any of these words? See the [Glossary](../Setup/Glossary.md) for plain-English definitions of *repo*, *branch*, *commit*, *pull request* and more.

### Why bother? Every project lives in a repository
It's tempting to email a script, drop it in a shared drive, or keep "final_v3_actual.py" on your desktop. **Don't.** Every project — even a solo one you think no one else will touch — belongs in a GitHub **repository (repo)**. A repo gives you:

- a **backup** in the cloud (your laptop can die, your work won't),
- a full **history** you can roll back to when something breaks,
- one obvious **place to find the latest version**, and
- the ability for a colleague (or future you) to pick it up later.

> Rule of thumb: if it's worth keeping, it goes in a repo. If you're sharing files any other way, stop and make a repo instead.

### You don't need the command line
Everything below can be done by **clicking buttons** in **GitHub Desktop** or the **Source Control panel in VS Code**. We show the equivalent `git` commands for anyone who wants them, but you never *have* to type them. Pick whichever you find easier and stick with it.

| What you want to do | GitHub Desktop / VS Code (recommended) | Command line (optional) |
|---|---|---|
| Get a repo onto your machine | **Clone** button | `git clone <url>` |
| Get the latest changes | **Pull** / "Fetch origin" | `git pull` |
| Start a new piece of work | **New branch** | `git switch -c my-branch` |
| Save a set of changes | Write a message → **Commit** | `git commit -m "..."` |
| Send your commits to GitHub | **Push** | `git push` |
| Ask for your work to be merged | **Create Pull Request** | (open on GitHub) |

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

### Commit often: what good looks like
"Commit often" is the habit people find hardest at first. Aim for a commit each time you finish one small, complete thing, not one giant commit at the end of the day.

!!! success "Good — small, purposeful commits"
    ```text
    Add function to load GPS csv files
    Fix wrong unit conversion in sprint speed
    Document load_gps with a docstring
    ```

!!! failure "Avoid — one vague commit for everything"
    ```text
    stuff
    update
    final changes
    ```

## Working with others (advanced)
If you're working **on your own**, the steps above are all you need — commit often and push to `main`. You don't have to use branches or pull requests.

The sections below matter **when you share a repo with other people**. You don't need them to get started — come back when you begin collaborating, or when you want to look up how to do it properly.

??? note "Branches and pull requests"
    When several people share a repo, avoid everyone editing `main` at once. Instead, each person works on their own **branch** and merges it back with a **pull request (PR)** that a colleague can look over first.

    1. **Pull** the latest `main` so you start from the current version.
    2. **Create a branch** for your task. A handy naming convention is your initials plus an imperative description, e.g. `sds/feature/automate_emails` or `jd/fix/gps-units`.
    3. **Do your work**, committing often (see above).
    4. **Push** your branch to GitHub.
    5. **Open a pull request** from your branch into `main`, and ask someone to review it (see [Collaboration and Code Reviews](Collaboration_And_Code_Reviews.md)).
    6. Once merged, **delete the branch**.
    7. **Pull `main` again** before your next piece of work so you're back in sync.

    All of this is available as buttons in **GitHub Desktop** and **VS Code** — you don't need the terminal.

??? note "Repo owners: protect the `main` branch"
    If you own a shared repo and want to *enforce* the branch/PR flow (rather than just ask for it), turn on branch protection so `main` can only be changed through a reviewed pull request:

    1. On GitHub, go to the repo's **Settings → Branches**.
    2. **Add a branch protection rule** for `main`.
    3. Tick **Require a pull request before merging** and **Require approvals** (at least 1).

    See GitHub's guide on [protecting branches](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches).

??? note "Getting unstuck: pulling and merge conflicts"
    Most "Git went wrong" moments come from working on an out-of-date copy. Two habits prevent almost all of them:

    - **Pull before you start** and **pull before you push.** This keeps your copy up to date.
    - **Keep commits and changes small.** Small changes rarely clash.

    A **merge conflict** happens when two people (or you, on two machines) changed the *same lines* of the same file. Git can't decide which version wins, so it asks you. This is normal and safe — nothing is lost.

    In VS Code, conflicted files are highlighted in the Source Control panel and show blocks like:

    ```text
    <<<<<<< HEAD
    speed = distance / time      # your version
    =======
    speed = distance / time_s    # the other version
    >>>>>>> main
    ```

    VS Code shows buttons above each block: **Accept Current Change**, **Accept Incoming Change**, or **Accept Both**. Pick the correct code, delete the `<<<<<<<`, `=======` and `>>>>>>>` marker lines, save, then commit.

    !!! tip "When in doubt, stop — don't force it"
        Never use `git push --force` or delete files to "make it go away" — you can lose a colleague's work. If a conflict is confusing, leave it and bring it to the **Thursday 10am coding office hours**, or ask someone from the data team. Getting stuck is expected while you're learning.


