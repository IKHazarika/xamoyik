# Assamese Wikipedia Time-Sensitive Tagger Bot (non-LLM)

## Setup

1) Create virtualenv
- Windows (PowerShell):
  python -m venv .venv
  .\.venv\Scripts\Activate.ps1

- macOS/Linux:
  python3 -m venv .venv
  source .venv/bin/activate

2) Install dependencies
  pip install -r requirements.txt

3) Create a BotPassword on Assamese Wikipedia:
   Special:BotPasswords
   Example name: aswiki-tagger

4) Fill user-password.py with the BotPassword secret.

5) Set your template name and date parameter in config/settings.yaml.

## Safe testing (recommended)

Create test pages in your userspace, e.g.
- User:IKHazarika/TestPage1
- User:IKHazarika/TestPage2

Run:
  python scripts/tagger.py --days 30 --limit 50 --dry-run --test-prefix "User:IKHazarika/"

If output looks good, run without --dry-run:
  python scripts/tagger.py --days 30 --limit 50 --test-prefix "User:IKHazarika/"

## Live run (after you're confident)
First do dry-run:
  python scripts/tagger.py --days 1 --limit 100 --dry-run

Then real:
  python scripts/tagger.py --days 1 --limit 100
