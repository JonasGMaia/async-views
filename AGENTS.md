# AGENTS.md

## Cursor Cloud specific instructions

This is a minimal Django project demonstrating async views. It uses SQLite (zero-config) and has no external service dependencies.

### Services

| Service | Command | Port |
|---------|---------|------|
| Django dev server | `python3 manage.py runserver 0.0.0.0:8000` | 8000 |

### Endpoints

- `/api/` — Async view that spawns a background HTTP call to httpbin.org
- `/sync/` — Synchronous view that makes a blocking HTTP call to httpbin.org
- `/admin/` — Django admin panel

### Key commands

- **Lint:** `ruff check .` (install ruff with `pip install ruff` if missing)
- **Django checks:** `python3 manage.py check`
- **Migrations:** `python3 manage.py migrate`
- **Run dev server:** `python3 manage.py runserver 0.0.0.0:8000`

### Notes

- Dependencies are listed in `requirements.txt` (django, httpx).
- The database is SQLite (`db.sqlite3`) — no external DB setup needed.
- The dev server must bind to `0.0.0.0` for external access in cloud environments.
