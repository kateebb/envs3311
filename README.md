# ENVS 3311 course website

A no-build Jekyll site that GitHub Pages renders automatically.

## Set up (5 minutes)
1. Create a GitHub repo named **`envs3311`**.
2. Upload these files to the repo root (or `git push` them).
3. Repo **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, folder `/ (root)`.
4. Visit https://kateebb.github.io/envs3311 after ~1 minute.


## What to edit
| File | What it controls |
|---|---|
| `_config.yml` | Course title, term, instructor, meeting time |
| `_data/schedule.yml` | Schedule table (one entry per class) |
| `_data/staff.yml` | Staff & office hours cards |
| `_data/nav.yml` | Top navigation links |
| `index.md` | Home page & announcements |
| `syllabus.md`, `assignments.md`, `resources.md` | Those pages |
| `lectures/*.md`, `assignments/*.md` | Individual lecture notes / assignment pages |
| `assets/css/style.css` | Colors & styling (light + dark mode) |

To add a lecture: copy `lectures/01-introduction.md`, rename it, and put its path
(e.g. `/lectures/03-new-topic/`) in the `notes:` field of `_data/schedule.yml`.

## Preview locally (optional)
```bash
gem install bundler jekyll jekyll-seo-tag
jekyll serve   # open http://localhost:4000
```
