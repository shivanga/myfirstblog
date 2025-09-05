# My Minimalist Blog

A simple, fast, and elegant Jekyll blog built with the "no-style-please" theme, designed for GitHub Pages hosting.

## Features

- ✨ **Minimalist Design**: Clean, distraction-free reading experience
- 📅 **Chronological Posts**: All posts displayed in reverse chronological order
- 🏷️ **Tagging System**: Organize posts with tags and browse by tag
- 💬 **Comments**: GitHub Discussions-powered comments via Giscus
- 📱 **Responsive**: Works perfectly on all devices
- ⚡ **Fast**: Optimized for speed and performance
- 🚀 **GitHub Pages Ready**: Deploy directly to GitHub Pages

## Setup Instructions

### 1. Repository Setup

1. Fork or clone this repository
2. Enable GitHub Pages in repository settings
3. Enable Discussions in your repository (for comments)

### 2. Configuration

Edit `_config.yml` to customize your blog:

```yaml
title: Your Name
email: your-email@example.com
description: Your blog description
github_username: your-github-username
```

### 3. Comments Setup (Optional)

To enable comments using Giscus:

1. Visit [giscus.app](https://giscus.app/)
2. Enter your repository details
3. Copy the generated configuration
4. Update the `giscus` section in `_config.yml`:

```yaml
giscus:
  repo: "your-username/your-repo-name"
  repo_id: "your-repo-id"
  category: "General"
  category_id: "your-category-id"
```

### 4. GitHub Pages Deployment

1. Push your changes to the main branch
2. Go to repository Settings → Pages
3. Select "Deploy from a branch" and choose "main"
4. Your blog will be available at `https://your-username.github.io/your-repo-name`

## Writing Posts

Create new posts in the `_posts` directory with the format: `YYYY-MM-DD-title.md`

### Post Front Matter Example

```yaml
---
layout: post
title: "Your Post Title"
date: 2025-01-15 10:00:00 +0530
tags: [tag1, tag2, tag3]
---

Your post content here...
```

## Local Development

1. Install Ruby and Bundler
2. Run `bundle install`
3. Run `bundle exec jekyll serve`
4. Visit `http://localhost:4000`

## Customization

### Adding Pages

Create new pages in the root directory or in folders. Add them to the navigation by updating `header_pages` in `_config.yml`.

### Styling

The theme uses minimal CSS. You can customize styles by:
- Overriding theme files in `_sass/`
- Adding custom CSS to individual layouts
- Modifying the existing layout files in `_layouts/`

### Theme Features

This blog uses the "no-style-please" theme which supports:
- Dark/light mode toggle
- Minimal, semantic HTML
- Fast loading times
- Accessibility features

## File Structure

```
├── _config.yml          # Site configuration
├── _posts/              # Blog posts
├── _layouts/            # Custom layouts
├── _includes/           # Reusable components
├── tags.md              # Tags page
├── about.markdown       # About page
├── index.markdown       # Homepage
└── README.md           # This file
```

## Contributing

Feel free to submit issues and enhancement requests!

## License

This project is open source and available under the [MIT License](LICENSE).

---

Built with ❤️ using [Jekyll](https://jekyllrb.com/) and the [no-style-please](https://github.com/riggraz/no-style-please) theme.
