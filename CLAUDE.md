# CLAUDE.md

## Project Overview

This repo hosts static image assets served via GitHub Pages at:
`https://mlevison.github.io/apr-public-files/`

Files are organized into subdirectories by context (e.g. `scrumalliance/`, `corsizio/`). A file at `corsizio/example.png` is accessible at `https://mlevison.github.io/apr-public-files/corsizio/example.png`.

## Repository Structure

```
apr-public-files/
├── corsizio/       # Images for Corsizio course listings
├── scrumalliance/  # Images for ScrumAlliance course descriptions
```

## Key Rules

### File Permissions
All files **must** have permissions `644` (`-rw-r--r--`) so GitHub Pages can serve them. Files uploaded via the GitHub web UI sometimes get `600` permissions when pulled locally. Always verify after adding files:

```bash
# Check for restrictive permissions
find . -type f -not -path './.git/*' -not -perm 644

# Fix any files that aren't 644
find . -type f -not -path './.git/*' -not -perm 644 -exec chmod 644 {} +
```

### Adding New Files
1. Place the image in the appropriate subdirectory.
2. Ensure file permissions are `644`.
3. Commit and push to `main` — GitHub Pages deploys automatically from the `main` branch.
4. Verify the file is accessible at `https://mlevison.github.io/apr-public-files/<path>`.

### Naming Conventions
- Use lowercase with hyphens for new files (e.g. `noun-library-3377733.png`).
- Some legacy files use underscores and mixed case; don't rename them as external references may depend on the existing names.
