# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **MkDocs-based documentation website** for IT fundamentals (web technologies and programming languages). The site is built for a German-language course covering HTML/CSS, JavaScript, XML, Java, Application Servers, and Low Code topics.

## Common Development Commands

### Local Development

```bash
# Create virtual environment (first time only)
python -m venv venv

# Activate virtual environment
source venv/bin/activate          # Linux/macOS
# or
.\venv\Scripts\Activate.ps1       # Windows

# Install dependencies
pip install -r requirements.txt

# Serve documentation locally (with hot reload)
mkdocs serve
```

The site runs on `http://localhost:8000` by default.

### Deployment

The site is automatically deployed via GitHub Actions when pushing to `main` branch:

```bash
# Simply push to main - CI/CD handles deployment
git push origin main
```

The workflow (`.github/workflows/ci.yml`) builds and deploys to `gh-pages` branch, which GitHub Pages serves.

## Code Architecture

### Core Components

**`main.py`** - MkDocs Macros Plugin
- Defines custom Jinja2 macros for the documentation
- Key macros:
  - `task(file, **params)`: Renders interactive exercises from YAML files
  - `youtube_video(url, title)`: Embeds YouTube videos with styled admonitions
  - `python_tutor(code, title)`: Embeds Python Tutor debugger iframes
  - `python_tutor_button(code, title)`: Creates a button linking to Python Tutor
  - `link(text, url, new_tab, icon)`: Creates styled external links

**`mkdocs.yml`** - MkDocs Configuration
- Theme: Material for MkDocs
- Navigation structure defined in `nav` section
- Extensions: admonition, pymdownx (details, superfences, emoji, arithmatex, highlight)
- Custom CSS/JS: `docs/stylesheets/` and `docs/javascripts/`
- Watch configuration: monitors `tasks/` directory for changes

**`tasks/*.yaml`** - Exercise Definitions
- YAML files containing exercise data (title, question, solution, tip, difficulty)
- Loaded by `main.py` via the `task()` macro
- Example structure:
  ```yaml
  title: "Exercise Title"
  question: "Question text..."
  solution: "Solution text..."
  tip: "Optional hint"
  difficulty: 1  # 0-3 scale
  ```

### Documentation Structure

```
docs/
├── assets/              # Images, logos, favicons
├── content/             # Topic-specific pages
│   ├── HTML_CSS/
│   ├── JavaScript/
│   ├── XML/
│   ├── Java_Grundlagen/
│   ├── Java_Aufbau/
│   ├── Application_Server/
│   └── Low_Code/
├── javascripts/         # Custom JavaScript
├── stylesheets/         # Custom CSS
└── index.md            # Landing page
```

### Custom Features

**Python Tutor Integration**
- `python_tutor()` macro generates embedded iframe with code visualization
- Dynamically calculates iframe height based on code line count
- Uses `pythontutor.com/iframe-embed.html` for embedded view
- `python_tutor_button()` creates a standalone link button

**Task Macro**
- Loads exercise data from YAML files
- Renders collapsible question/solution sections with difficulty indicators
- Supports optional video links for questions and solutions
- Error handling for missing/invalid YAML files

**YouTube Video Admonitions**
- Styled video embeds using MkDocs admonitions
- Responsive iframe with 16:9 aspect ratio

**Custom CSS**
- `python_tutor_admonition.css`: Custom styling for Python Tutor admonitions (yellow theme)
- `video_admonition.css`: Video container styling
- `grid.css`: Grid layout utilities
- `logo.css`: Logo positioning

## Key Dependencies

- **mkdocs**: Static site generator
- **mkdocs-material**: Theme
- **mkdocs-macros-plugin**: For custom macros (Python code execution in Markdown)
- **mkdocs-mermaid2**: Mermaid diagram support
- **PyYAML**: YAML parsing for exercise files
- **mkdocs-git-revision-date-localized-plugin**: Shows last modified dates

## Workflow for Adding Content

### Adding a New Topic Page

1. Create markdown file in `docs/content/<Topic>/` (e.g., `docs/content/HTML_CSS/2.md`)
2. Update `mkdocs.yml` navigation to include the new page
3. Add exercises using the `task()` macro:
   ```markdown
   {{ task(file="tasks/01_00_06.yaml") }}
   ```
4. Create corresponding YAML file in `tasks/` directory

### Adding Exercises

1. Create YAML file in `tasks/` directory (follow naming convention: `XX_XX_XX.yaml`)
2. Define exercise properties:
   ```yaml
   title: "Exercise Title"
   question: |
     Question text with **markdown** support
   solution: |
     Solution text
   tip: "Optional hint shown before solution"
   difficulty: 2  # 0-3 scale, displayed as 🌶🌶
   solution_video: null  # or YouTube URL
   question_video: null  # or YouTube URL
   ```
3. Reference in markdown: `{{ task(file="tasks/XX_XX_XX.yaml") }}`

### Adding Python Tutor Code

```markdown
{{ python_tutor("print('Hello')\nx = 5", "Simple Python Example") }}
```

or with button:

```markdown
{{ python_tutor_button("print('Hello')\nx = 5", "View in Python Tutor") }}
```

### Adding External Links

```markdown
{{ link("Website", "https://example.com", new_tab=true, icon=":fontawesome-solid-globe:") }}
```

## Error Handling

The `task()` macro includes comprehensive error handling:
- **FileNotFoundError**: Shows error if YAML file doesn't exist
- **YAMLError**: Shows error if YAML is malformed
- **UnicodeDecodeError**: Shows error if file encoding is invalid
- **Type Error**: Shows error if YAML content is not a dictionary

All errors are displayed as red "danger" admonitions with detailed error messages.

## CI/CD Pipeline

**`.github/workflows/ci.yml`**
- Triggers on push to `main` or `master` branch
- Sets up Python 3.x
- Uses caching for faster builds
- Runs `mkdocs gh-deploy --force` to deploy to `gh-pages`
- Auto-commits with `github-actions[bot]` user

## Development Tips

- **Watch mode**: `mkdocs serve` automatically reloads when files change
- **YAML validation**: The `task()` macro validates YAML structure at build time
- **Mermaid diagrams**: Use fenced code blocks with `mermaid` language
- **MathJax**: Use `$$...$$` for block math or `$...$` for inline math
- **Icons**: Uses Material Design icons via `:icon-name:` syntax (e.g., `:material-language-html5:`)

## File Organization

- Keep exercise YAML files in `tasks/` directory
- Organize content by topic in `docs/content/<Topic>/`
- Use descriptive filenames for exercises (e.g., `01_00_01.yaml` for topic 1, section 0, exercise 1)
- Assets (images, logos) go in `docs/assets/`
