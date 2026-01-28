# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a MkDocs-based educational documentation site for IT basics (HTML/CSS, JavaScript, XML, Java, Application Servers, Low Code). The site is published to GitHub Pages via a CI/CD pipeline and uses the Material theme with custom macros and admonitions.

## Development Commands

### Local Development

**Setup virtual environment:**
```bash
python -m venv venv
.\venv\Scripts\Activate.ps1  # Windows
# source venv/bin/activate  # macOS/Linux
```

**Install dependencies:**
```bash
pip install -r requirements.txt
```

**Serve the documentation locally:**
```bash
mkdocs serve
```

The dev server automatically rebuilds on file changes and can be viewed at `http://127.0.0.1:8000`.

### Publishing

The CI/CD pipeline automatically deploys to GitHub Pages when changes are pushed to the `main` or `master` branch. No manual deployment is required.

## Architecture

### mkdocs.yml Configuration

The main MkDocs configuration file defines the site structure, theme, extensions, and custom CSS/JS. Key settings:
- **Theme**: Material with blue primary/accent colors
- **Navigation**: 8 topic sections (HTML_CSS, JavaScript, XML, Java_Grundlagen, Java_Aufbau, Application_Server, Low_Code)
- **Extensions**: pymdownx for custom fences (mermaid, math), admonitions, emoji, etc.
- **Plugins**: `search` and `macros` plugins
- **Custom macros**: Defined in `main.py`

### main.py - Custom Macros

This Python file provides Jinja2 macros for MkDocs content generation:

- `task(file, **parameter)`: Renders a task block from YAML files in `tasks/`. Tasks are admonition blocks with optional video, tip, and solution sections.
- `youtube_video(inner_url, title)`: Embeds YouTube videos in admonitions.
- `python_tutor(code_string, title)`: Embeds Python Tutor interactive debugger.
- `python_tutor_button(code_string, title)`: Generates a button linking to Python Tutor.
- `link(text, url, new_tab=True, icon)`: Generates Markdown links with optional icons.

### Task System

Tasks are defined as YAML files in the `tasks/` directory and referenced using `{{ task(file="tasks/01_00_01.yaml") }}` in Markdown files. Each YAML file contains:
- `title`: Task heading
- `question`: The question text
- `solution`: Solution text
- `tip`: Optional hint
- `difficulty`: Number of chili peppers indicating difficulty
- `difficulty_icon`: Icon for difficulty (default: 🌶)
- `collapsed`: Whether to collapse the task by default
- `solution_video` / `question_video`: Optional YouTube video URLs

### Content Structure

- `docs/content/`: Main documentation pages organized by topic
- `docs/stylesheets/`: Custom CSS for admonitions, grids, and special components
- `docs/assets/`: Logo and favicon images
- `tasks/`: YAML task definition files

### CI/CD

GitHub Actions workflow (`/.github/workflows/ci.yml`) automatically:
1. Installs Python and dependencies
2. Builds and deploys to GitHub Pages via `mkdocs gh-deploy --force`
3. Runs on pushes to `main` or `master` branches

## Key Conventions

- All content is written in Markdown
- Mermaid diagrams are supported for flowcharts and other visualizations
- YouTube videos are embedded using the `youtube_video` macro
- Python code examples use the `python_tutor` macro for interactive debugging
- Tasks use the `task` macro for consistent formatting
- The project is German-language educational content for IT basics