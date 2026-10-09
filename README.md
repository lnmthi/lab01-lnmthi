# Study Assistant — starter

A starter repository for the CSC10014 Smart Virtual Assistant project.

## Setup

~Requirements:
- Python 3.10 or newer
- Git

~Installation:
1. Clone the repository from GitHub.
2. Open the terminal in the project directory.
3. Create a virtual environment: 
	python -m venv .venv
4. Activate the virtual environment: 
	.\.venv\Scripts\Activate.ps1
5. Install dependencies: 
	python -m pip install -r requirements.txt
6. Install the project: 
	python -m pip install -e .

## Run

- Run the assistant with this command:
	python -m assistant "where is the IT helpdesk?"
- Example output:
IT Helpdesk: room E.005, open Mon-Fri 08:00-17:00.

## Test

- Run the tests:
	pytest -q
- Check the development environment:
	python scripts/check_env.py

## Project structure

- data/ - Project data.
- docs/ - Project documentation.
- scripts/ - Utility scripts.
- src/assistant/ - Assistant source code.
- tests/ - Automated tests.
- ui/ - User interface files.
- requirements.txt - Python dependencies.
- pyproject.toml - Project configuration.
- README.md - Project documentation.
- .gitignore - Files excluded from Git.

## Example question

- Ask the assistant a question from the terminal:

```powershell
python -m assistant "where is the IT helpdesk?"