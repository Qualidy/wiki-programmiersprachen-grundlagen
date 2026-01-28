# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an **educational IT documentation website** built with MkDocs Material. The content is in German and covers topics like HTML/CSS, JavaScript, XML, Java, Application Servers, and Low Code.

## Development Commands

### Local Development
```bash
# Install dependencies (if not already done)
pip install -r requirements.txt

# Serve locally with hot reload
mkdocs serve
```

The site will be available at `http://localhost:8000`.

### Deployment
```bash
# Deploy to GitHub Pages (gh-pages branch)
mkdocs gh-deploy --force
```

Deployment is also automated via GitHub Actions when pushing to the `main` branch.

## Architecture

### Core Files
- **`mkdocs.yml`** - MkDocs configuration with navigation, theme settings, and extensions
- **`main.py`** - MkDocs macros plugin providing custom Python functions
- **`requirements.txt`** - Python dependencies (MkDocs, Material theme, plugins)
- **`.github/workflows/ci.yml`** - GitHub Actions CI/CD for auto-deployment

### Content Structure
```
docs/
├── index.md              # Main landing page
├── content/              # Course content organized by topic
│   ├── HTML_CSS/
│   ├── JavaScript/
│   ├── XML/
│   ├── Java_Grundlagen/
│   ├── Java_Aufbau/
│   ├── Application_Server/
│   └── Low_Code/
├── assets/               # Images, logos, favicon
├── javascripts/          # MathJax configuration
├── stylesheets/          # Custom CSS (grid, video admonitions, etc.)
└── tasks/                # YAML task files for interactive exercises
```

### Macros (main.py)

The `main.py` file provides custom MkDocs macros:

- **`task(file)`** - Loads YAML task files and renders interactive exercises with questions, tips, and solutions
- **`youtube_video(url, title)`** - Embeds YouTube videos in styled admonitions
- **`python_tutor(code, title)`** - Generates Python Tutor iframe for interactive code debugging
- **`python_tutor_button(code, title)`** - Creates a button link to Python Tutor
- **`link(text, url, new_tab)`** - Creates styled external links

### Task System

Interactive exercises are stored as YAML files in `tasks/`:

```yaml
title: "Exercise title"
question: "Question text"
solution: "Solution text"
tip: "Optional hint"
difficulty: 1-5 (spice icons 🌶)
solution_video: optional YouTube URL
question_video: optional YouTube URL
```

Tasks are referenced in Markdown files using: `{{ task(file="tasks/01_00_01.yaml") }}`

### Content Format

Content files use Markdown with:
- **Admonitions** (`!!! note`, `!!! warning`, `!!! danger`, etc.)
- **Mermaid diagrams** for flowcharts
- **MathJax** for mathematical expressions
- **YouTube embeds** via macros
- **Python Tutor integration** for code debugging

## Key Patterns

### Adding Content
1. Create/edit Markdown files in `docs/content/{topic}/`
2. Add interactive exercises by creating YAML files in `tasks/`
3. Reference tasks using `{{ task(file="tasks/filename.yaml") }}`
4. Add videos using `{{ youtube_video("url", "Title") }}`

### Navigation
Navigation is defined in `mkdocs.yml` under the `nav:` section. New topics should be added there.

### Watch Configuration
The `mkdocs.yml` includes `watch: - tasks` to auto-reload when task YAML files change.

## Important Notes

- **No code tests** - This is a documentation site, not a codebase with executable tests
- **German language** - All content and documentation is in German
- **Auto-deployment** - Pushing to `main` branch triggers CI/CD that deploys to GitHub Pages
- **No package.json** - This is a Python/MkDocs project, not a Node.js project
- **Virtual environment** - Recommended to use `venv` for Python dependencies

## Common Tasks

### Update a content page
1. Edit the Markdown file in `docs/content/{topic}/`
2. Run `mkdocs serve` to preview
3. Push to `main` branch for auto-deployment

### Add a new exercise
1. Create a new YAML file in `tasks/` following the format
2. Reference it in the relevant content page using `{{ task(file="tasks/filename.yaml") }}`

### Fix a broken link or typo
1. Edit the Markdown file
2. Preview locally with `mkdocs serve`
3. Commit and push to `main`
