Web_project
===========

Getting Started
---------------

- Change directory into your newly created project if not already there. Your
  current directory should be the same as this README.txt file and setup.py.

    cd UnixBot

- Create a Python virtual environment, if not already created.

    python3 -m venv env

- Upgrade packaging tools, if necessary.

    env/Scripts/pip install --upgrade pip setuptools

- Install the project in editable mode with its testing requirements.

    env/Scripts/pip install -e ".[testing]"

- Initialize and upgrade the database using Alembic.

    - Generate your first revision.

        env/Scripts/alembic -c development.ini revision --autogenerate -m "init"

    - Upgrade to that revision.

        env/Scripts/alembic -c development.ini upgrade head

- Load default data into the database using a script.

    env/Scripts/initialize_UnixBot_db development.ini

- Run your project's tests.

    env/Scripts/pytest

- Run your project.

    env/Scripts/pserve development.ini
