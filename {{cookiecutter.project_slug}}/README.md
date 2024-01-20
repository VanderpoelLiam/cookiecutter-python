# {{cookiecutter.project_name}}
Project created by {{cookiecutter.author}}.

## Requirements
(Reccomended) Install [pyenv](https://github.com/pyenv/pyenv) to manage Python versions:
```
curl https://pyenv.run | bash
```

Install [pipx](https://github.com/pypa/pipx):
```
python3 -m pip install --user pipx
python3 -m pipx ensurepath
```

Install [Cookiecutter](https://github.com/cookiecutter/cookiecutter):
```
pipx install cookiecutter
```

Install [Poetry](https://python-poetry.org/)
```
pipx install poetry
```

## Development environment (reccomended)
We reccomend this approach for managing the development environment.

Install Python 3.10.12:
```
pyenv install 3.10.12
```

Create a new virtualenv:
```
pyenv virtualenv 3.10.12 {{cookiecutter.package_name}}
```

Set this to the default Python environment inside the repository:
```
pyenv local {{cookiecutter.package_name}}
```

## Create a new project
Example usage:
```
❯ cookiecutter gh:/VanderpoelLiam/cookiecutter-python 
  [1/4] project_name (Foundations Of Psychohistory): {{cookiecutter.project_name}}
  [2/4] project_slug (foundations-of-psychohistory): {{cookiecutter.project_slug}}
  [3/4] package_name (foundations_of_psychohistory): {{cookiecutter.package_name}}
  [4/4] author (Hari Seldon): {{cookiecutter.author}}

❯ cd {{cookiecutter.project_slug}} 

❯ git init
❯ git add . 
❯ git commit -m "Initial commit"

# Setup Python environment
❯ pyenv install 3.10.12 
❯ pyenv virtualenv 3.10.12 {{cookiecutter.package_name}}
❯ pyenv local {{cookiecutter.package_name}} 

# Setup Poetry
❯ poetry init --dev-dependency pre-commit pytest
... follow the instructions ...

# Add sample project dependencies
❯ poetry add pandas
❯ poetry add --group dev pytest-cov

# Install the project
❯ poetry install

# Install pre-commit
❯ poetry run pre-commit install
```