# Python Copier Template

A [Copier](https://copier.readthedocs.io/) template for quickly scaffolding new Python projects with modern tooling and best practices.

## What is this?

This template generates a standardized Python project structure with:
- Modern `pyproject.toml` configuration
- Ruff linting and formatting setup
- Docker support
- Configurable Python version support
- Pre-configured project metadata

## Usage

Generate a new project from this template:

```bash
copier copy gh:statkern15/python_copier_template /path/to/new/project
```

Or use a local copy:

```bash
copier copy /path/to/python_copier_template /path/to/new/project
```

You'll be prompted for:
- Project name
- Project description
- Author name and email
- Python version

## Next Steps After Generation

Once your project is created:

1. **Navigate to the project directory:**
   ```bash
   cd /path/to/new/project
   ```

2. **Initialize git repository (if not already done):**
   ```bash
   git init
   git add .
   git commit -m "Initial commit from template"
   ```

3. **Set up Python environment and install dependencies:**
   ```bash
   uv sync --group dev
   ```

4. **Verify Ruff configuration:**
   ```bash
   uv run ruff check .
   uv run ruff format .
   ```

5. **Start coding!** Your project structure is ready with best practices configured.

## Updating Existing Projects

Update a project created from this template to get the latest changes:

```bash
cd /path/to/project
copier update
```

Or specify the template path:

```bash
copier update --vcs-ref=HEAD /path/to/project
```