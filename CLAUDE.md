# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

MyWeek is a personal weekly review tracking system that combines quantitative metrics (CSV) with qualitative reflections (Markdown) to document work progress, accomplishments, and learning.

## File Structure & Naming Conventions

- **Data files:** `data/YYYY-week-XX.csv` (e.g., `data/2025-week-25.csv`)
- **Review files:** `reviews/YYYY-week-XX.md` (e.g., `reviews/2025-week-25.md`)
- **Templates:** Located in `templates/` folder for consistent formatting

## Key Data Fields

### CSV Template Fields
- `year,week,date_start,date_end` - temporal identifiers
- `repositories_worked_on` - comma-separated list of repos
- `commits_made` - total commit count for the week  
- `main_projects,key_accomplishments` - high-level work summary
- `hours_worked` - estimated time investment
- `learning_highlights,challenges_faced,goals_next_week` - reflection data

### Markdown Template Structure
- Overview and repository breakdown
- Key accomplishments (checkbox format)
- Projects & activities with status tracking
- Learning & development section
- Challenges & solutions
- Quantitative metrics
- Forward-looking goals

## Workflow for Adding New Entries

1. Copy templates from `templates/` folder
2. Gather git commit data across repositories using: `git log --oneline --since="1 week ago" --author="[email]"`
3. Fill CSV with quantitative data 
4. Create detailed markdown review using template structure
5. Follow naming convention: `YYYY-week-XX`
6. Commit both files together with descriptive commit message

## Data Collection Commands

To gather weekly git activity across multiple repositories:
```bash
# Find all git repositories
find . -name ".git" -type d -exec dirname {} \;

# Check commits for specific week
git log --oneline --since="1 week ago" --author="[email]"

# Get commit count
git rev-list --count --since="1 week ago" --author="[email]" HEAD
```

## Architecture Notes

This is a data collection and documentation system, not a software project. The "architecture" is the standardized data schema across CSV and Markdown formats that enables consistent tracking and potential future analysis of work patterns over time.