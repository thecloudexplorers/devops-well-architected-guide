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

2. **Configuration is already complete**:
   - `hugo.toml` contains the site configuration
   - GitHub Actions workflow is configured in `.github/workflows/hugo.yml`

3. **Commit and push** your changes:
   ```bash
   git add .
   git commit -m "Add Hugo theme and GitHub Pages setup"
   git push origin main
   ```

## Theme Customization

### Current Theme

The site uses the **Ezhil** theme, which provides:
- Clean, minimal design
- Responsive layout
- Dark/light mode toggle
- Fast loading times

### Custom Styling

To customize the appearance:

1. Create `layouts/` directory for custom page layouts
2. Create `assets/` directory for custom CSS/JS
3. Create `static/` directory for images and other assets

### Navigation

The navigation is configured in `hugo.toml` under `[[menu.main]]`. Add or remove pages as needed:

```toml
[[menu.main]]
  name = "Design Principles"
  url = "/design-principles/"
  weight = 2
```

## File Structure

```
├── hugo.toml                   # Hugo configuration
├── content/                    # Content directory
│   ├── _index.md              # Home page
│   ├── design-principles.md   # Design principles page
│   ├── checklists.md          # Checklists page
│   ├── recommendations.md     # Recommendations page
│   └── how-to-use.md          # Usage guide page
├── themes/ezhil/              # Theme files (submodule)
└── .github/workflows/hugo.yml # GitHub Actions workflow
```

## Troubleshooting

### Common Issues

1. **Hugo version errors**: Ensure you're using Hugo Extended v0.121.1+
2. **Theme not found**: Make sure you cloned with `--recursive` flag for submodules
3. **GitHub Pages not building**: Check the Actions tab for error details
4. **Theme not applying**: Ensure the theme submodule is properly initialized

### Local Development Tips

- Use `hugo server --buildDrafts` to include draft content
- Use `hugo server --disableFastRender` for full rebuilds on change
- Use `hugo --gc --minify` for production builds

## Next Steps

1. **Customize the site**:
   - Update `hugo.toml` with your information
   - Modify the theme or add custom CSS
   - Add more pages as needed

2. **Set up domain** (optional):
   - Add a `CNAME` file to the `static/` directory
   - Configure DNS settings

3. **Add analytics** (optional):
   - Add Google Analytics ID to `hugo.toml`
   - Configure other tracking tools

4. **SEO optimization**:
   - Hugo includes built-in SEO features
   - Add meta descriptions to page front matter
   - Configure social media previews

## Resources

- [Hugo Documentation](https://gohugo.io/documentation/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Ezhil Theme Documentation](https://github.com/vividvilla/ezhil)
- [Hugo Themes](https://themes.gohugo.io/)

## Hugo vs Jekyll Benefits

### Performance
- **Build Time**: Hugo builds in milliseconds vs Jekyll's seconds/minutes
- **Development**: Instant live reload with built-in server
- **CI/CD**: Much faster deployment pipelines

### Simplicity  
- **Single Binary**: No Ruby/gem dependency management
- **Cross-Platform**: Works consistently across all platforms
- **Modern Tooling**: Built with Go, actively maintained

### Features
- **Built-in**: Sitemap, RSS feeds, syntax highlighting
- **Themes**: Large ecosystem of modern themes  
- **Flexibility**: Powerful templating and content organization