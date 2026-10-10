# Study Assistant — starter

A starter repository for the CSC10014 Smart Virtual Assistant project.

## Setup

~Requirements:
- Python 3.10 or newer
- Git
- PowerShell on Windows, or a compatible terminal on other operating systems.

~Installation:
1. Clone the repository from GitHub and enter the project directory:
		git clone <repository-url>
		cd <repository-folder>
	- Replace the placeholders with the actual repository URL and folder name.

2. Create a virtual environment: 
		python -m venv .venv
	- A virtual environment isolates the project's Python packages from other Python projects.

3. Activate the virtual environment: 
	+ On Windows PowerShell:
		.\.venv\Scripts\Activate.ps1
	+ On macOS or Linux:
		source .venv/bin/activate

4. Install dependencies: 
		python -m pip install -r requirements.txt
		python -m pip install -e .

	- The first command installs the packages listed in requirements.txt. The second installs the project in editable mode so that changes to the source code can be tested without reinstalling the package.
	- If the test dependencies are not included in the project's requirements, install pytest separately:
		python -m pip install pytest

## Run

- Run the Assistant:
	+ Run a single question:
		python -m assistant "where is the IT helpdesk?"	  Example output:
		IT Helpdesk: room E.005, open Mon-Fri 08:00-17:00.
	  The response depends on the office records and rules configured in the project.

- Run in interactive mode:
	+ Start the assistant without a question:
		python -m assistant
	  Enter a question when prompted. Type quit or exit to end the interactive session.

## Test

- Run the automated test suite from the project root:
	python -m pytest -q
  The tests check that the assistant's existing behavior works as expected. A successful run reports the number of passed tests and no failures.

- To check the development environment, run:
	python scripts/check_env.py
  Review the output and resolve any failed checks before submitting changes.

## Project structure

.
├── data/
│   └── offices.csv          # Office names, locations, and opening hours
├── docs/                    # Project documentation
├── scripts/
│   └── check_env.py         # Development environment checks
├── src/
│   └── assistant/
│       ├── __init__.py      # Package initialization
│       ├── __main__.py      # Command-line entry point
│       └── rules.py         # Rule-based response logic
├── tests/                   # Automated tests
├── ui/                      # User interface resources
├── requirements.txt         # Python dependencies
├── pyproject.toml            # Package and build configuration
├── README.md                 # Project documentation
└── .gitignore                # Files excluded from Git

- Some directories may be expanded as the team develops additional features.

## Office data

- Office information is stored in data/offices.csv. Each record describes an office and includes its name, room, and opening hours.
- When adding a new office:
	1. Follow the existing CSV column format.
	2. Use consistent office names and opening-hour formats.
	3. Add or update automated tests when appropriate.
	4. Run the test suite before committing the change.

## Development guidelines

- Keep changes small and focused.
- Use clear, descriptive names for variables, functions, and files.
- Add tests for new behavior and bug fixes.
- Update this README when installation steps, commands, or features change.
- Do not commit the virtual environment, Python cache files, or local secrets.
- Use meaningful Git commit messages.

## Current limitations

- Responses are based on predefined rules rather than a full conversational AI model.
- The assistant supports only the intents implemented in the source code.
- The accuracy of office information depends on the contents of data/offices.csv.
- The user interface is currently command-line based.

## Future improvements

- Possible extensions include:
	+ Add a help command to explain available commands.
	+ Support more natural variations of user questions.
	+ Support more natural variations of user questions.
	+ Add more office records and corresponding tests.
	+ Improve handling of empty or unrecognized questions.
	+ Develop a graphical or web-based user interface.

## Run the assistant

- Activate the virtual environment, then run:
	```powershell
	python -m assistant "where is the IT helpdesk?"