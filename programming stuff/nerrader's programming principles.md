
- AI should never write code for you, ask it for suggestions on what to add or how to fix problems (try to do them yourself though)
  
  If it is writing code for you, you ain't gonna learn shit.
- For python projects, mypy, ruff, vulture, radon, (and maybe bandit) should be installed
  
  - mypy: for type annotations and checking errors before you ever reach them, basically ESLint but python
  - ruff: code formatter and linter
  - vulture: finding dead code (unused functions, variables, class methods, etc.)
  - radon: for calculating Cyclomatic Complexity (CC) to stop functions from being too complex and being too stupid, and Maintainability Index (MI) for, well, maintainability and also to make it readable
- Always use comments, docstrings, and type annotations to document your code
- Use all the packages to fully debug your code first, then you can commit it (mypy, ruff, vulture) scores must be perfect, radon must have no C grade functions (CC) or C grade files (MI)
- pytest is good but lowkey i haven't been using it so ill cut future me some slack for not using it as well i guess
- Make sure dependencies and dev dependencies are in the correct place
- Always add a build system table on the pyproject.toml file (preferably hatchling)
- Use vermin or something to determine the minimum version of python needed to run it
- Try and not use global variables at all