## Coding Guidelines
**Planning comes first**. Create and update the relevant documentation. Write out steps in comments before you code. This planning phase is vital for efficiency and clarity, and for the future legacy and readability of your code. 

1. **KISS**: Keep it simple sailor, **DRY**: Don't repeat yourself, **SRP**: [Single responsibility principle](https://towardsdatascience.com/solid-coding-in-python-1281392a6a94).
2. Use **linters**. At minimum, use Black and Pylint for all your python scripts and notebooks (pylint optional for notebooks). See [Linting](#linting-formatting-code) below.
3. Use a **`pyproject.toml`** and **`uv.lock`** file to keep track of the project's dependencies and their versions. 
4. Use **environment variables** for ***sensitive*** info like secret keys or passwords (i.e. Deepnote example [here](https://docs.deepnote.com/environment/environment-variables)).
5. Import all packages at the ***top*** of your script, module or notebook.
6. ***Avoid hardcoding*** variables wherever possible, but if needed, put it at the ***top*** of your script/notebook, clearly marked. 
7. Use **comments** and **docstring** in compliance with the [Style Guide](Style_Guide.md).
8. Exception names should be the ***only*** code you write that contains **capital letters**, other than constants and class names (see the [Style Guide](Style_Guide.md)).

**For more, make sure you check out the [Style Guide](Style_Guide.md).**

## Linting (formatting code)
Formatting your code consistently makes it easy for future you and others to read. A **linter** does this automatically and flags likely bugs at the same time. We use two tools:

- **Black** — automatically *formats* your code to a consistent style.
- **Pylint** — *checks* your code for style problems and likely errors.

### Setting it up in VS Code
1. Install the **Black Formatter** and **Pylint** extensions (see [Local Setup](../Setup/Local_Setup.md#recommended-vs-code-extensions)).
2. Turn on **Format On Save**: open Settings (`Ctrl+,`), search for *Format On Save*, and tick it. Black now tidies your code every time you save.
3. Pylint warnings appear underlined in your code and in the **Problems** panel — work through them before requesting a review.

You can also lint in Deepnote. Either way, always **lint before you open a pull request**. For the specific conventions Black and Pylint enforce, see the [Style Guide](Style_Guide.md).

## Checking your code is correct (testing)
You don't need a full testing framework to work responsibly, but you should **sanity-check your outputs** — this is exactly what reviewers look for under the *Analysis* pillar in [Collaboration and Code Reviews](Collaboration_And_Code_Reviews.md).

- Compare results against **known or expected values** (e.g. a jump height you calculated by hand, a sprint speed you know is realistic).
- Check outputs fall in a **sensible range** and handle **messy or missing data** without silently producing nonsense.
- When you fix a bug, add a quick check so it can't creep back in.

As projects grow, consider writing small automated tests with **pytest** and running them with `uv run pytest`.

## File naming & documenting (descriptions)
Name files with snake case (lower_case_divided_by_underscores) rather than camel case (UpperCaseCharactersDivideWords).
Add in a couple of sentence description either via a Readme or at the top of your project to ensure someone else could understand the purpose without further information. 

## Libraries
There are a few things to consider when using 3rd party libraries (funcitons, modules, whichever word you use!). Don't inlcude libraries just for the sake of it, and make sure you identify your version via virtual environments and uv so that others' will be able to run your code just as it is (i.e. if pandas gets an update, it might behave differently). 

There are plenty of widely adopted, well documented and actively maintained useful libraries such as: 

- numpy, pandas → data handling  
- matplotlib, seaborn → visualisation  
- scipy, statsmodels → statistics  
- scikit-learn → machine learning  

But if you're using a new one you haven't heard of or used, it's worth pausing before you import it. In short: **will this tool help you answer your question now, without causing problems later?** Expand the checklist below when you need it.

??? question "Checklist: is this library worth adopting?"
    Ask yourself (or google) these questions before depending on an unfamiliar library:

    1. **Fit for purpose** — Does it solve your specific problem (signal processing, modelling, visualisation)? Does it integrate with the tools you already use (Python, NumPy, Pandas)? Will it limit future choices (upgrading Python, collaborating with other groups)?
    2. **Maturity / stability** — Is it well-established and used in multiple studies or applied settings, or new and experimental and likely to change?
    3. **Community and maintenance** — Is there an active community answering questions? Is it updated and bug-fixed regularly? Is it maintained by a team/organisation (safer) or a single individual (riskier)? Is the documentation clear, with realistic examples?
    4. **Licensing** — Is it legally usable for applied sport, commercial/consultancy work, or research with IP/publication considerations? Any restrictions on redistribution or commercial use? It's your responsibility to know.
    5. **Security** — Any history of security issues, and how quickly were they fixed?
    6. **Performance** — Is it fast and memory-efficient enough for your data (large time-series, high-frequency sensor data, batch processing)? Standard number-crunching should never take minutes, especially when a coach is waiting for feedback.
