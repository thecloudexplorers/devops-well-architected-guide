---
title: Hugo Setup Guide
---

# Hugo Setup for DevOps Well-Architected Guide

This document explains the Hugo setup that has been configured for GitHub Pages deployment.

## Files Added

### Core Hugo Files
- `hugo.toml` - Hugo site configuration
- `content/` - Site content directory with all pages
- `themes/ezhil/` - Clean, minimal Hugo theme
- `content/_index.md` - Main guide homepage content
- `README.md` - Updated with links to the guide

### GitHub Actions
- `.github/workflows/hugo.yml` - Automated build and deployment workflow

### Configuration Updates
- `.gitignore` - Added Hugo-specific ignore patterns

## How It Works

1. **Local Development**: Install Hugo and run `hugo server` to test locally
2. **Deployment**: Automatic deployment via GitHub Actions when pushing to `main` branch
3. **Site URL**: Will be available at `https://thecloudexplorers.github.io/devops-well-architected-guide/`

## Features Enabled

- 🚀 Fast build times (Hugo builds in ~20ms vs Jekyll's minutes)
- 🗺️ XML sitemap generation (built-in)
- 📰 RSS feed generation (built-in)
- 🎨 Ezhil theme (clean, responsive design)
- 🚀 Automated GitHub Pages deployment
- 📱 Mobile-friendly responsive layout
- ⚡ Single binary deployment (no Ruby dependencies)

## GitHub Pages Setup Required

To complete the setup, a repository administrator needs to:

1. Go to repository Settings → Pages
2. Set Source to "GitHub Actions"
3. The site will automatically deploy when changes are pushed to main

## Local Development Setup

### Prerequisites
- Hugo Extended v0.121.1 or later

### Installation

#### On macOS
```bash
brew install hugo
```

#### On Windows
```bash
winget install Hugo.Hugo.Extended
```

#### On Linux
```bash
wget https://github.com/gohugoio/hugo/releases/download/v0.121.1/hugo_extended_0.121.1_linux-amd64.tar.gz
tar -xzf hugo_extended_0.121.1_linux-amd64.tar.gz
sudo mv hugo /usr/local/bin/
```

### Running Locally
```bash
# Clone the repository with submodules (for the theme)
git clone --recursive https://github.com/thecloudexplorers/devops-well-architected-guide.git

# Navigate to the directory
cd devops-well-architected-guide

# Start the development server
hugo server
```

The site will be available at `http://localhost:1313/devops-well-architected-guide/`

## Theme Customization

The site uses the [Ezhil theme](https://github.com/vividvilla/ezhil). To customize:

1. Create `layouts/` directory for custom layouts
2. Create `assets/` directory for custom styles  
3. Create `static/` directory for images and other assets

### Navigation

The navigation is configured in `hugo.toml` under `[[menu.main]]`. Add or remove pages as needed:

```toml
[[menu.main]]
  name = "Design Principles"
  url = "/design-principles/"
  weight = 2
```

## Content Organization

- `content/_index.md` - Main guide homepage (root level)
- `content/design-principles.md` - Design principles page
- `content/checklists.md` - Checklists page  
- `content/recommendations.md` - Recommendations page
- `content/how-to-use.md` - Usage guide page
- Additional pages can be added as `.md` files in the content directory

## Hugo vs Jekyll Benefits

### Performance
- **Build Time**: Hugo builds in ~20ms vs Jekyll's 30+ seconds
- **Development**: Instant live reload with Hugo's built-in server
- **CI/CD**: Faster deployment pipelines

### Simplicity
- **Single Binary**: No Ruby/gem dependency management
- **Cross-Platform**: Works consistently across all platforms
- **Modern Tooling**: Built with Go, actively maintained

### Features
- **Built-in**: Sitemap, RSS feeds, syntax highlighting
- **Themes**: Large ecosystem of modern themes
- **Flexibility**: Powerful templating and content organization