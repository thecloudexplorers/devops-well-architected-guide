# Hugo Theme Setup Instructions

This repository is now configured with Hugo and the Ezhil theme for GitHub Pages. Follow these steps to complete the setup:

## Prerequisites

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

## Local Development Setup

1. **Clone the repository with submodules**:
   ```bash
   git clone --recursive https://github.com/thecloudexplorers/devops-well-architected-guide.git
   cd devops-well-architected-guide
   ```

2. **Start the development server**:
   ```bash
   hugo server
   ```

3. **Access the site**: Visit `http://localhost:1313/devops-well-architected-guide/`

## GitHub Pages Setup

1. **Enable GitHub Pages** in your repository:
   - Go to repository Settings
   - Scroll to "Pages" section
   - Under "Source", select "GitHub Actions"

2. **Update configuration**:
   - Edit `_config.yml`
   - Change `baseurl` to your repository name (e.g., `/devops-well-architected-guide`)
   - Change `url` to your GitHub Pages URL (e.g., `https://yourusername.github.io`)

3. **Commit and push** your changes:
   ```bash
   git add .
   git commit -m "Add Jekyll theme and GitHub Pages setup"
   git push origin main
   ```

## Theme Customization

### Available Themes

The current setup uses the **Minima** theme. You can change to other GitHub-supported themes by editing `_config.yml`:

```yaml
# Popular GitHub Pages themes:
theme: minima                    # Clean, minimal theme (current)
theme: jekyll-theme-minimal      # Very minimal theme
theme: jekyll-theme-cayman       # Green gradient header
theme: jekyll-theme-architect    # Professional theme
theme: jekyll-theme-slate        # Dark theme
theme: jekyll-theme-modernist    # Modern, clean theme
```

### Custom Styling

To customize the appearance:

1. Create `_sass/minima/_custom.scss` for custom CSS
2. Create `_layouts/` directory for custom page layouts
3. Create `_includes/` directory for reusable components

### Navigation

The navigation is configured in `_config.yml` under `header_pages`. Add or remove pages as needed:

```yaml
header_pages:
  - index.md
  - devops-well-architected-guide/design-principles.md
  - devops-well-architected-guide/checklists.md
  - devops-well-architected-guide/recommendations.md
  - devops-well-architected-guide/how-to-use.md
```

## File Structure

```
├── _config.yml                 # Jekyll configuration
├── Gemfile                     # Ruby dependencies
├── index.md                    # Home page (main guide)
├── README.md                   # Repository description
├── devops-well-architected-guide/
│   ├── design-principles.md    # Design principles page
│   ├── checklists.md          # Checklists page
│   ├── recommendations.md      # Recommendations page
│   └── how-to-use.md          # Usage guide page
└── .github/workflows/jekyll.yml # GitHub Actions workflow
```

## Troubleshooting

### Common Issues

1. **Ruby version errors**: Ensure you're using Ruby 3.0+
2. **Bundle install fails**: Try `bundle update` instead
3. **GitHub Pages not building**: Check the Actions tab for error details
4. **Theme not applying**: Ensure you've committed all files and pushed to GitHub

### Local Development Tips

- Use `bundle exec jekyll serve --livereload` for automatic page refresh
- Add `--drafts` flag to include draft posts
- Use `--incremental` for faster builds during development

## Next Steps

1. **Customize the site**:
   - Update `_config.yml` with your information
   - Modify the theme or add custom CSS
   - Add more pages as needed

2. **Set up domain** (optional):
   - Add a `CNAME` file with your custom domain
   - Configure DNS settings

3. **Add analytics** (optional):
   - Add Google Analytics ID to `_config.yml`
   - Configure other tracking tools

4. **SEO optimization**:
   - The site includes `jekyll-seo-tag` plugin
   - Add meta descriptions to page front matter
   - Configure social media previews

## Resources

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Minima Theme Documentation](https://github.com/jekyll/minima)
- [Jekyll Themes](https://jekyllthemes.io/)
