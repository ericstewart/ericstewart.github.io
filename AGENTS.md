# AGENTS.md

## Project Overview

This is a static blog site generator using Babashka and the quickblog library. The project generates HTML from Markdown blog posts using Selmer templates, styled with Tailwind CSS and daisyUI.

## Build Commands

### Babashka (Primary Build Tool)

```bash
# Generate the blog
bb quickblog

# Build blog with custom options (see bb.edn)
bb quickblog --help

# Serve locally (default port 8080)
bb quickblog serve

# Watch mode for auto-regeneration
bb quickblog watch

# Render all posts (full rebuild)
bb quickblog render
```

### Tailwind CSS (CSS Generation)

```bash
# Install dependencies
npm install

# Build CSS from Tailwind source (requires @tailwindcss/cli)
npx @tailwindcss/cli -i templates/input.css -o public/style.css

# Watch mode for development
npx @tailwindcss/cli -i templates/input.css -o public/style.css --watch
```

### Development Workflow

```bash
# Terminal 1: Watch for CSS changes
npx @tailwindcss/cli -i templates/input.css -o public/style.css --watch

# Terminal 2: Watch for blog changes and serve
bb quickblog watch
```

## Project Structure

```
.
├── bb.edn                    # Babashka configuration and quickblog options
├── tailwind.config.js        # Tailwind CSS configuration (legacy, not used)
├── package.json              # npm dependencies (Tailwind, daisyUI)
├── templates/
│   ├── base.html            # Main HTML layout (Selmer template)
│   ├── index.html           # Homepage template with hero section
│   ├── post.html            # Individual post template
│   ├── archive.html         # Archive page template
│   ├── tags.html            # Tags listing template
│   ├── about.html           # About page template
│   ├── post-links.html      # Post navigation links
│   └── input.css            # Tailwind source CSS
├── posts/                    # Markdown blog posts
│   ├── *.md                 # Post files with YAML frontmatter
│   └── about.md             # About page (Preview: true to hide from archives)
├── public/                   # Generated output (committed to repo)
│   ├── index.html           # Generated homepage
│   ├── archive.html         # Generated archive
│   ├── about.html           # Generated about page
│   ├── style.css            # Compiled CSS
│   └── ...                  # Other generated files
└── assets/                  # Static assets (images, etc.)
```

## Code Style Guidelines

### Blog Posts (Markdown)

- Frontmatter format (YAML):
  ```markdown
  Title: Post Title
  Description: Brief description for SEO/social sharing
  Date: 2024-01-15
  Tags: tag1 tag2 tag3
  Image: path/to/image.jpg  # Optional
  ```
- Title, Description, and Date are required
- Tags are lowercase, hyphenated
- Date format: YYYY-MM-DD
- Use standard Markdown with GitHub Flavored Markdown extensions

### Selmer Templates

- Use double-brace syntax for variables: `{{variable}}`
- Use pipe for filters: `{{variable | filter}}`
- Common filters: `safe` (raw HTML), `escape-tag` (URL encoding)
- Conditionals: `{% if variable %}...{% endif %}`
- Loops: `{% for item in items %}...{% endfor %}`

### Tailwind CSS

- Use utility classes from daisyUI and @tailwindcss/typography
- Use `prose` class for article content styling
- Use `prose-lg` for larger text in listings
- Use `badge` and `badge-outline` for tags
- Use `card`, `card-body`, `card-actions` for post cards

### HTML Conventions

- Use semantic HTML5 elements (`<article>`, `<header>`, `<footer>`, `<main>`)
- daisyUI component classes: `navbar`, `dropdown`, `btn`, `link`
- Responsive classes: `lg:`, `md:`, `sm:` prefixes
- **daisyUI v5 Note**: Footer is vertical by default. Use `footer-horizontal` for horizontal layout.

## Naming Conventions

### Files

- Blog posts: kebab-case (`my-blog-post.md`)
- Templates: kebab-case (`post-links.html`)
- Generated pages: kebab-case converted to HTML

### Variables (Selmer)

- Use lowercase with hyphens: `{{post-link}}`
- Available variables vary by template context

### CSS Classes

- Tailwind utilities: kebab-case
- daisyUI components: kebab-case

## Configuration

### bb.edn

Blog configuration is in `bb.edn`:
- `blog-title`: Site title
- `blog-description`: Site description
- `blog-root`: Production URL
- `page-suffix`: File extension (empty string for clean URLs)
- `link-prev-next-posts`: Enable prev/next navigation

## Git Workflow

- Generated static files (`public/`) are committed to the repository
- **Note**: The user always prefers to push changes manually. Do not push automatically.
- The `.gitignore` excludes:
  - `.clj-kondo/` - Clojure linter cache
  - `.lsp/.cache/` - LSP cache
  - `.portal/` - Portal debug tool cache

## Key Dependencies

- **babashka**: CLI build tool (v1.12+)
- **quickblog**: Blog generation library
- **@tailwindcss/cli**: Tailwind CSS CLI (v4.x)
- **tailwindcss**: CSS utility framework (v4.x)
- **@tailwindcss/typography**: Prose styling for blog content
- **daisyui**: Tailwind component library (v5.x)
- **prismjs**: Syntax highlighting (loaded via CDN)

## Design Features

### Theme
- Uses daisyUI `corporate` theme for a professional look

### Layout
- **Homepage**: Hero section with author info, post listing with hover effects
- **Posts**: Reading progress indicator, styled prev/next navigation
- **Archive**: Enhanced timeline with year groupings
- **Tags**: Grid layout of tag cards

### CSS Custom Features (templates/input.css)
- Smooth scroll behavior
- Card hover animations (`post-card` class)
- Reading progress bar (CSS scroll-driven animation)
- Staggered fade-in animations for post cards
- Custom scrollbar styling
- Avatar placeholder with gradient background

### Adding the About Page
1. Edit `posts/about.md` with your bio content
2. The page is excluded from archives via `Preview: true` in frontmatter
3. Rebuild with `bb quickblog render`

## Common Tasks

### Adding a New Post

1. Create a new `.md` file in `posts/` with frontmatter
2. Run `bb quickblog render` to regenerate the site
3. Commit both the post and generated files

### Modifying Styles

1. Edit `templates/input.css` to add custom Tailwind directives
2. Run `npx @tailwindcss/cli -i templates/input.css -o public/style.css --watch`
3. Commit the generated `public/style.css`

### Adding a New Template

1. Create template in `templates/` using Selmer syntax
2. Reference quickblog documentation for available variables
3. Test with `bb quickblog serve`

## Testing

This project has no automated tests. Manual testing is done by:
1. Running `bb quickblog serve`
2. Opening http://localhost:8080
3. Verifying the changes visually

## Quick Reference

```bash
# Full rebuild and serve
bb quickblog render && bb quickblog serve

# CSS rebuild
npx @tailwindcss/cli -i templates/input.css -o public/style.css --watch
```
