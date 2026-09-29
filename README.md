# Data Dashboard

`data-dashboard.py` is a command-line exercise dashboard for member step activity and active skills. It uses in-memory sample data and prints its results directly to the terminal; it does not contact an API or database.

## What It Shows

- A preview of the member, weekly activity, and skills data sets.
- Member totals, the number meeting the 10,000-step goal, average steps, cold-shower count, meal-protocol counts, and the member with the most steps.
- Daily step totals for the week, including the highest day, weekly average, and total steps.
- Active skill count, enrollment totals, and the most popular skill.
- A JSON summary of the weekly, member, and skills metrics.

With the data currently in the script, the dashboard processes 6 members, 7 daily step totals, and 5 skills. Three members meet the step goal; Thursday has the highest daily total (71,000); and copywriting has the highest skill enrollment (15).

## Run

Use Python 3 and run this command from this directory:

```powershell
python data-dashboard.py
```

The script uses only the Python standard library, so no package installation is required.

## Data Notes

All records are hard-coded in `data-dashboard.py` and use generic member labels. The printed dashboard banner says `YEAR 2026, Week 33-37`, while the weekly and JSON data labels say `2024-W47`; update these labels if they are intended to describe the same reporting period.

## Repository setup and GitHub push

Create an empty repository on GitHub, then run these commands from this directory. Replace the URL with the HTTPS or SSH URL for your repository:

```powershell
git init
git add README.md .gitignore data-dashboard.py
git commit -m "Initial data dashboard"
git branch -M main
git remote add origin <repository-url>
git push -u origin main
```

This folder is currently inside a larger workspace. Running `git init` here creates a separate nested repository for this dashboard; run the commands from this folder only if that is the intended GitHub repository. Avoid committing credentials or identifiable member data without permission.
