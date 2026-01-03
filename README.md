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
copier copy gh:yourusername/python_copier_template /path/to/new/project
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

# TODO check this again
### Update Issues

**Merge conflicts during update:**
- Copier will prompt you to resolve conflicts between template changes and your modifications
- Use `k` to keep your version, `o` to overwrite with template version, or `d` to see diff
- Review `.copier-answers.yml` to track template version

**Dependencies out of sync after update:**
- Run `uv sync --group dev` after updating to install any new dependencies

**Configuration drift:**
- If you've heavily customized template files, consider selectively applying updates
- Keep custom configurations in separate files when possible

## Common Issues & Pitfalls

### "Template not found" error
Make sure Copier is installed: `uv tool install copier`

### Invalid project name characters
Project names are sanitized to valid Python package names (lowercase, underscores only). Special characters and spaces are automatically converted.

### Python version mismatch
Ensure the Python version you select during setup matches your local environment. The template sets `requires-python` in `pyproject.toml` based on your selection.

### Ruff not found after generation
Run `uv sync --group dev` in the generated project to install development dependencies including Ruff.

### Template update conflicts
When updating, Copier may ask about conflicts if you've modified template files. Review changes carefully before accepting.
