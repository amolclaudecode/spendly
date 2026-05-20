# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Spendly is a Flask-based personal expense tracker web application. It uses SQLite for persistence and follows a simple Flask-Jinja2 frontend architecture.

## Commands

```bash
# Run the application (default - runs on port 5001)
python app.py

# Run tests
pytest
```

## Architecture

```
app.py              # Flask app factory and routes
database/db.py      # SQLite database module (students implement get_db, init_db, seed_db)
templates/          # Jinja2 HTML templates (base.html + page templates)
static/css/         # Custom CSS with CSS variables for theming
static/js/          # JavaScript for client-side interactivity
```

**Flask routes** in `app.py`:
- `/` - Landing page
- `/register` - User registration (form posts to `/register`)
- `/login` - User login
- `/logout` - Placeholder for Step 3
- `/profile` - Placeholder for Step 4
- `/expenses/add` - Placeholder for Step 7
- `/expenses/<id>/edit` - Placeholder for Step 8
- `/expenses/<id>/delete` - Placeholder for Step 9

**Database module** (`database/db.py`): Students implement this file. Expected functions:
- `get_db()` - Returns SQLite connection with `row_factory` and foreign keys enabled
- `init_db()` - Creates tables using `CREATE TABLE IF NOT EXISTS`
- `seed_db()` - Inserts sample data for development

## Key Implementation Details

- **Session management**: Flask `secret_key` should be set for session handling (not yet configured)
- **Password hashing**: Use `werkzeug.security` for password hashing
- **SQLite foreign keys**: Enable with `PRAGMA foreign_keys = ON` after connection
- **Template inheritance**: All pages extend `base.html` using `{% block content %}` and `{% block scripts %}`

## Dependencies

Flask 3.x, Werkzeug 3.x, pytest, pytest-flask