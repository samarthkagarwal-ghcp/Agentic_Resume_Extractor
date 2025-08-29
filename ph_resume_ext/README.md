# ph_resume_ext

A modular Python project for automated resume extraction, processing, and evaluation using LLMs and CrewAI.

## Features
- Extracts structured data from resumes in DOCX and PDF formats
- Uses LLMs (e.g., Gemini) for content extraction and cleaning
- Modular agent/task/crew design with CrewAI
- Outputs standardized JSON for downstream processing
- Includes evaluation scripts to compare extracted data with golden records

## Project Structure
```
ph_resume_ext/
│   README.md
│   pyproject.toml
│   resume_py.py
│   uv.lock
│
├── src/
│   └── ph_resume_ext/
│       ├── main.py                # Main entry point for resume processing
│       ├── type.py                # Pydantic models for output format
│       ├── crews/
│       │   └── resume_crew_pr/
│       │       └── resume_crew.py # CrewAI crew/agent/task definitions
│       ├── tools/
│       │   ├── doc_extractor_tool.py  # DOCX extraction tool
│       │   ├── pdf_reader_tool.py     # PDF extraction tool
│       │   └── Text_Cleaner.py       # Text cleaning tool
│       └── resume/
│           ├── templates/         # Input resumes
│           ├── processed/         # Output JSONs
│           └── Golden_Records/    # Ground truth for evaluation
│
├── tests/
│   └── Evaluation_Script.py       # Script to evaluate extraction accuracy
```

## Usage

### 1. Install dependencies
```
pip install -r requirements.txt
```

### 2. Set up environment variables
Create a `.env` file in the project root with your LLM API keys and model info:
```
GEMINI_MODEL=your-model-name
GEMINI_API_KEY=your-api-key
```

### 3. Run resume extraction
```
python src/ph_resume_ext/main.py
```

### 4. Evaluate extraction results
```
python tests/Evaluation_Script.py
```

## Customization
- Add new tools in `src/ph_resume_ext/tools/` for more file types or processing steps.
- Update `type.py` to change the output schema.
- Modify `resume_crew.py` to adjust agent/task logic or LLM settings.

## Notes
- Only `.docx` and `.pdf` files are supported by default. For `.doc` files, convert to `.docx` first.
- Ensure all input/output paths are correct for your environment.

## License
MIT License
# {{crew_name}} Crew

Welcome to the {{crew_name}} Crew project, powered by [crewAI](https://crewai.com). This template is designed to help you set up a multi-agent AI system with ease, leveraging the powerful and flexible framework provided by crewAI. Our goal is to enable your agents to collaborate effectively on complex tasks, maximizing their collective intelligence and capabilities.

## Installation

Ensure you have Python >=3.10 <3.14 installed on your system. This project uses [UV](https://docs.astral.sh/uv/) for dependency management and package handling, offering a seamless setup and execution experience.

First, if you haven't already, install uv:

```bash
pip install uv
```

Next, navigate to your project directory and install the dependencies:

(Optional) Lock the dependencies and install them by using the CLI command:
```bash
crewai install
```

### Code, Prompt and Agent Orchestraction Files

- Modify `src/ph_resume_ext/config/agents.yaml` to define your agents
- Modify `src/ph_resume_ext/config/tasks.yaml` to define your tasks
- Modify `src/ph_resume_ext/crew.py` to add your own logic, tools and specific args
- Modify `src/ph_resume_ext/main.py` to add custom inputs for your agents and tasks

## Running the Project

To kickstart your flow and begin execution, run this from the root folder of your project:

```bash
crewai run
```

This command initializes the ph_resume_ext Flow as defined in your configuration.

This example, unmodified, will run the create a `report.md` file with the output of a research on LLMs in the root folder.

## Understanding Your Crew

The ph_resume_ext Crew is composed of multiple AI agents, each with unique roles, goals, and tools. These agents collaborate on a series of tasks, defined in `config/tasks.yaml`, leveraging their collective skills to achieve complex objectives. The `config/agents.yaml` file outlines the capabilities and configurations of each agent in your crew.

## Support

For support, questions, or feedback regarding the {{crew_name}} Crew or crewAI.

- Visit our [documentation](https://docs.crewai.com)
- Reach out to us through our [GitHub repository](https://github.com/joaomdmoura/crewai)
- [Join our Discord](https://discord.com/invite/X4JWnZnxPb)
- [Chat with our docs](https://chatg.pt/DWjSBZn)

Let's create wonders together with the power and simplicity of crewAI.
