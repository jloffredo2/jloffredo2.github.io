# Joe Loffredo - Academic Website

This is a Quarto-based website for Joe Loffredo's academic portfolio.

## Building the Site Locally

To preview the site locally:

```bash
quarto preview
```

To render the site:

```bash
quarto render
```

## Deploying to GitHub Pages

This site is configured to automatically deploy to GitHub Pages using GitHub Actions.

### Setup Instructions:

1. Push this repository to GitHub
2. Go to your repository Settings → Pages
3. Under "Build and deployment", set:
   - Source: **GitHub Actions**
4. The site will automatically build and deploy when you push to the main branch

### Custom Domain

The `CNAME` file is configured for `joseph-loffredo.com`. If you need to change this:
1. Edit the `CNAME` file
2. Configure your DNS settings to point to GitHub Pages
3. In GitHub Settings → Pages, add your custom domain

## Structure

- `_quarto.yml`: Main configuration file
- `custom.scss`: Custom styling with MIT red color scheme (#750014)
- `styles.css`: Additional CSS styles
- `index.qmd`: Home page with bio and social links
- `research.qmd`: Publications and working papers
- `cv.qmd`: CV page with embedded PDF viewer
- `teaching.qmd`: Teaching assignments and educational materials
- `data.qmd`: Data and code resources
- `contact.qmd`: Contact information
- `CNAME`: Custom domain configuration
- `.nojekyll`: Required for Quarto on GitHub Pages

## Design

The site uses the Sandstone Bootswatch theme with MIT red (#750014) accent color. Layout inspired by modern academic websites with:
- Responsive side-by-side layout on home page
- Rectangular profile photo with social link buttons
- Collapsible abstracts with arrow indicators
- Clean typography and navigation

## Social Links

- X (Twitter)
- Bluesky
- GitHub
- Email
