# b4Help's Tech Blog

Built with Jekyll + Midnight theme, hosted on GitHub Pages.

## 🚀 Setup Instructions

### 1. Create the GitHub repo

Your repo `techblog-b4Help` is already created with Pages activated.

### 2. Push these files

```bash
git init
git add .
git commit -m "Initial blog setup"
git branch -M main
git remote add origin https://github.com/b4Help/techblog-b4Help.git
git push -u origin main
```

### 3. Enable GitHub Pages

- Go to your repo → **Settings** → **Pages**
- Under **Source**, select `main` branch and `/ (root)`
- Click **Save**

Your blog will be live at: **https://b4Help.github.io/techblog-b4Help**

(Takes ~2 minutes on first deploy.)

---

## ✍️ Writing a new post

Create a file in `_posts/` named:

```
YYYY-MM-DD-your-post-title.md
```

With this frontmatter at the top:

```yaml
---
layout: default
title: "Your Post Title"
date: 2026-03-19
tags: [tag1, tag2]
---
```

Then write your post in Markdown below the `---`.

---

## 🏃 Running locally (optional)

```bash
gem install bundler
bundle install
bundle exec jekyll serve
```

Visit `http://localhost:4000`
