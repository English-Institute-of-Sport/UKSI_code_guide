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

## Libraries
There are a few things to consider when using 3rd party libraries (funcitons, modules, whichever word you use!). Don't inlcude libraries just for the sake of it, and make sure you identify your version via virtual environments and uv so that others' will be able to run your code just as it is (i.e. if pandas gets an update, it might behave differently). 

There are plenty of widely adopted, well documented and actively maintained useful libraries such as: 

- numpy, pandas → data handling  
- matplotlib, seaborn → visualisation  
- scipy, statsmodels → statistics  
- scikit-learn → machine learning  

But if you're using a new one you haven't heard of or used, before importing, ask yourself (or google) these questions:

1. Is it fit for purpose?

    - Does it solve the specific scientific or applied problem we have (e.g. signal processing, modelling, visualisation)?
    - Does it integrate easily with the tools and workflows we already use (e.g. Python, NumPy, Pandas, biomechanics/physiology pipelines)?
    - Will using it limit future methodological or software choices (e.g. upgrading Python versions, changing analysis workflows, collaborating with other groups)?
> In short: will this tool help us answer our research or performance questions now, without causing problems later?

2. Maturity/stability of the library

    - Is this a well‑established library that has been used in multiple studies, labs, or applied sport settings?
    - Or is it a new or experimental tool that may still change substantially?

> Mature libraries are generally more stable, better tested, and safer for longitudinal projects or decision‑making workflows.

3. Size and quality of the user and developer community

    - Is there an active user community who ask and answer questions (e.g. GitHub issues, forums, Stack Overflow)?
    - How often is the library:
        Updated or improved?
        Fixed when bugs are identified?
    - Is it maintained by:
        A team or organisation, or
        A single individual (which may pose long‑term risks)?
    - Is the documentation clear and scientifically meaningful, with examples relevant to real data?

> Strong communities often mean faster support, clearer guidance, and greater confidence in results.

4. Licensing and usage constraints

    - Is the library legally usable for:
        Applied sport environments?
        Commercial or consultancy work?
        Research with potential publication or IP considerations?
    - Are there any restrictions on:
        Redistribution
        Commercial use
        Integration into larger tools?

> Some libraries are fully open source, while others are free for research purposes, it is your responsibility to know.

5. Security

      - Has there been any history of security issues, how quickly were they fixed?

6. Performance

    - Is the library fast and efficient enough for:
        Large datasets (e.g. time‑series, high‑frequency sensor data)?
        Repeated analyses or batch processing?
    - Does it require excessive memory or computational resources?
    - Is it practical for day‑to‑day applied use, not just small example datasets?

> Performance matters more when working with highly complex or large volumns of data, or real‑time or near‑real‑time analysis. Standard number-crunching processes should never take minutes. 
