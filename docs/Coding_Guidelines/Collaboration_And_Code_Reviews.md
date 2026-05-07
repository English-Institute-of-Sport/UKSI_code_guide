## Code Reviews
As a community, make sure you both request and perform frequent **code-reviews**. They provide exceptional learning opportunities, enforce better code quality, and can have positive effects on team culture. While aimed at software developers, [this video](https://www.youtube.com/watch?v=EAwJ6_tDMy0) gives a nice overview. 

As our community of coders within UKSI grows, so does our need to review our code. Our aim should be to make this a habit, but making a small start of sharing your GitHub repo with someone is a good first step! If you're asked to review someone else's code, there are a few main things to focus on:

🛠️ Is it **functional**, does it do what it's meant to?  
🏦 Structure: is the **workflow design** sensible?  
📖 Is it **readable**?  
📈 Is the analysis **accurate and reliable**?  
🤔 What is the practical **risk & impact**?  

To dig into a bit more detail, see the questions and examples below. 

🛠️ **Functionality**  

Ask:  
- Does the code actually calculate what it claims?
- Are the equations and methods scientifically correct?
- Does it answer the applied question (e.g., fatigue, load, performance)?

Examples:  
Jump height calculated using the correct method (impulse vs flight time)  
GPS velocity thresholds aligned with sport definitions  
Filtering matches accepted practice  

🔑 Core idea:  
“Is this scientifically correct and usable in practice?”  

🏦 **Structure**  

Ask:  
- Is the analysis structured logically (clean → process → output)?
- Can parts of the code be reused (e.g., a standard GPS cleaning function)?
- Is it easy to adapt to a new dataset or athlete group?

Examples:  
Separate steps: data cleaning → feature calculation → visualisation  
Reusable scripts across squads or seasons  
Modular functions (e.g., calculate_acceleration_load())  

🔑 Core idea:  
“Is this analysis built in a way that works across real-world scenarios?”

📖 **Readability**  

Ask:  
- Could another sport scientist understand this quickly?
- Are variable names meaningful? (e.g., peak_power vs pp1)
- Is it overly complicated for what it does?

Examples:  
Clear comments explaining steps like filtering or thresholds  
Logical ordering of code  
Avoiding unnecessary technical tricks  

🔑 Core idea:  
“Can a colleague pick this up and trust it?”

📈 **Analysis**  

Ask:  
- Has the method been checked against known values or benchmarks?
- Do outputs match expected ranges?
- Has it been tested on different datasets?

Examples:  
Checking jump height against lab system values  
Comparing outputs to previous seasons  
Running edge cases (missing data, extreme sessions)  

🔑 Core idea:  
“Do we know this works reliably?”

🤔 **Risk & Impact**  

Ask:  
- Could this lead to wrong decisions?
- Is it robust to messy real-world data?
- Is it fast enough for applied use (e.g., post-session turnaround)?
- Are there hidden assumptions?

Examples:  
A smoothing filter that hides peak sprint loads  
Hard-coded thresholds that don’t suit different athletes  
Code breaking when a column name changes  
Slow scripts delaying feedback to coaches  
 
🔑 Core idea:  
“What could go wrong when this is used in practice?”


Both Deepnote and Github provide you with tools to be able to perform/receive a code review remotely and with ease. Make sure you adhere to the following guidelines:

1. Perform or request code reviews **frequently**. This will mainly assist reviewers by not giving them so much to do at once, but also help you progress quicker.
2. Only request a review once you have **tested** and **linted** (automate this within VS code) your code.
3. As a reviewer, if clarity and understanding of the code is blocking your review, this must be communicated to the author, directed at the code or documentation, rather than the author.
4. As a reviewer, make comments **actionable**. Make it ***clear*** whether your comment is a question, suggestion or required change. 

> [!NOTE]  
> In GitHub, the best way to conduct code reviews is via Pull Requests. See video example explainers on [Pull Requests](https://www.youtube.com/watch?v=3Q1MZjAVIiE) and [Reviewing](https://www.youtube.com/watch?v=GbjI2x0dMK0) on GitHub (many others will be available!).

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
