---
layout: default
title: Jekyll Setup Guide
---

# Jekyll Setup for DevOps Well-Architected Guide

This document explains the Jekyll setup that has been configured for GitHub Pages deployment.

## Files Added

### Core Jekyll Files
- `_config.yml` - Jekyll site configuration
- `Gemfile` - Ruby gem dependencies
- `index.md` - Main guide homepage content with Jekyll front matter
- `README.md` - Updated with Jekyll front matter and links to the guide

### GitHub Actions
- `.github/workflows/jekyll.yml` - Automated build and deployment workflow

### Configuration Updates
- `.gitignore` - Added Jekyll-specific ignore patterns

## How It Works

1. **Local Development**: Run `bundle install` then `bundle exec jekyll serve` to test locally
2. **Deployment**: Automatic deployment via GitHub Actions when pushing to `main` branch
3. **Site URL**: Will be available at `https://thecloudexplorers.github.io/devops-well-architected-guide/`

## Features Enabled

- 📄 SEO optimization (`jekyll-seo-tag`)
- 🗺️ XML sitemap generation (`jekyll-sitemap`) 
- 📰 RSS feed generation (`jekyll-feed`)
- 🎨 Minima theme (clean, responsive design)
- 🚀 Automated GitHub Pages deployment
- 📱 Mobile-friendly responsive layout

## GitHub Pages Setup Required

To complete the setup, a repository administrator needs to:

1. Go to repository Settings → Pages
2. Set Source to "GitHub Actions"
3. The site will automatically deploy when changes are pushed to main

## Theme Customization

The site uses the [Minima theme](https://github.com/jekyll/minima). To customize:

1. Create `_layouts/` directory for custom layouts
2. Create `_sass/` directory for custom styles
3. Create `assets/` directory for images and other assets

## Content Organization

- `index.md` - Main guide homepage (root level)
- `README.md` - Repository description with links to the guide
- Guide sections are organized in the `devops-well-architected-guide/` directory
- Additional pages can be added as `.md` files in the guide directory or other folders