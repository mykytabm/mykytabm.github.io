# Mykytabm's Blog

This is a personal blog built with [Hugo](https://gohugo.io/) static site generator and the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme, hosted on GitHub Pages.

## 🚀 Quick Start

### Prerequisites
- [Hugo Extended](https://gohugo.io/installation/) installed on your system
- Git

### Local Development
To run the site locally and preview changes:

```bash
hugo server -D
```

This will start a local server at `http://localhost:1313/` with live reload enabled. The `-D` flag includes draft posts.

## 📝 Creating New Blog Posts

### Method 1: Using Hugo Command
```bash
hugo new blog/my-new-post.md
```

This creates a new post in `content/blog/` with the default front matter from `archetypes/default.md`.

### Method 2: Manual Creation
Create a new `.md` file in `content/blog/` with the following front matter:

```markdown
---
title: "Your Post Title"
date: 2025-10-07T12:00:00+02:00
draft: false
---

Your content here...
```

## ✏️ Updating Existing Posts

1. **Edit the post**: Make changes to the markdown file in `content/blog/`
2. **Preview locally**: Run `hugo server -D` to see your changes
3. **Generate static files**: Run `hugo` to build the site
4. **Commit and push**: Git add, commit, and push to deploy

## 🔨 Building the Site

To generate the static website files:

```bash
hugo
```

This command:
- Processes all content files
- Applies the theme
- Generates HTML, CSS, and JavaScript files in the `public/` directory
- Only includes posts where `draft: false`

## 📂 Project Structure

```
.
├── config.yml          # Main configuration file
├── content/            # Your blog posts and pages
│   ├── blog/           # Blog posts go here
│   └── random/         # Other content
├── public/             # Generated static site (git ignored usually)
├── themes/             # Hugo themes
│   └── PaperMod/       # Current theme
├── archetypes/         # Templates for new content
└── docs/               # Published site for GitHub Pages
```

## 🚢 Publishing Workflow

After updating a post like `mentality.md`:

1. **Save your changes** to the markdown file

2. **Test locally** (optional but recommended):
   ```bash
   hugo server -D
   ```

3. **Build the site**:
   ```bash
   hugo
   ```

4. **Copy to docs folder** (if using GitHub Pages from `/docs`):
   ```bash
   xcopy /E /I /Y public docs
   ```
   Or if using Linux/Mac:
   ```bash
   cp -r public/* docs/
   ```

5. **Commit and push**:
   ```bash
   git add .
   git commit -m "Update mentality post"
   git push origin main
   ```

6. **GitHub Pages** will automatically deploy your changes

## ⚙️ Configuration

Edit `config.yml` to change:
- Site title, description, and URL
- Theme settings
- Menu items
- Social links
- And more...

## 📋 Front Matter Options

Common front matter options for posts:

```yaml
---
title: "Post Title"           # Required
date: 2025-10-07T12:00:00     # Required
draft: false                   # Set to false to publish
description: "Brief summary"   # Optional, for SEO
tags: ["tag1", "tag2"]        # Optional
categories: ["category"]       # Optional
author: "Your Name"            # Optional
ShowToc: true                  # Show table of contents
TocOpen: false                 # TOC closed by default
---
```

## 🎨 Theme Customization

The PaperMod theme is located in `themes/PaperMod/`. Theme settings are configured in `config.yml` under the `params:` section.

## 🆘 Common Commands Reference

| Command | Description |
|---------|-------------|
| `hugo` | Build the site |
| `hugo server` | Run local dev server |
| `hugo server -D` | Run local dev server including drafts |
| `hugo new blog/post.md` | Create new blog post |
| `hugo --help` | Show all Hugo commands |

## 📝 Notes

- Posts with `draft: true` won't be published in production builds
- The `public/` directory contains generated files and can be deleted/regenerated
- Always run `hugo` before deploying to ensure latest changes are built