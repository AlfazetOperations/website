# GitHub Copilot Instructions for Yarn Classic Website

## Project Overview
This repository contains the source code for the Yarn Classic (v1) website, available at https://classic.yarnpkg.com/. It's a Jekyll-based documentation site with React components for interactive features.

## Role and Expertise
**Role Type**: Technical Writer and Web Developer
**Domain**: Package Manager Documentation and Web Development
**Key Skill Area**: Documentation, Jekyll, React, JavaScript, Markdown, Web Design

## Code Guidelines and Patterns

### Technology Stack
- **Static Site Generator**: Jekyll (Ruby-based)
- **Frontend**: React 16.4+ with Bootstrap 4.0.0-alpha.5
- **Build Tools**: Webpack 3, Babel
- **Languages**: JavaScript (ES6+), Markdown, HTML, SCSS
- **Package Management**: Yarn (self-hosting)

### Code Patterns
1. **Markdown Documentation**
   - All documentation lives in `lang/en/` directory
   - Use Jekyll front matter with `id`, `guide`, and `layout` fields
   - Include `{% include vars.html %}` for accessing site variables
   - Use `{{url_base}}` for internal links to support internationalization

2. **React Components**
   - Located in `js/src/` directory
   - Use ES6+ syntax with Babel transpilation
   - Follow React 16 patterns (class components and hooks where appropriate)
   - PropTypes for type checking

3. **Jekyll Layouts**
   - Main layouts in `_layouts/` directory
   - Partials in `_includes/` directory
   - Use Liquid templating syntax

4. **Styling**
   - SCSS files in `_sass/` directory
   - Bootstrap 4 for base styling
   - Compressed CSS output

### Formatting and Style
- **Format**: Use Prettier for code formatting
- **Language**: Professional, clear, and beginner-friendly documentation
- **Tone**: Helpful and educational, suitable for developers of all skill levels

### Source Types
- **Markdown files** (`.md`) for documentation content
- **JavaScript files** (`.js`) for React components and webpack config
- **SCSS files** (`.scss`) for styling
- **HTML files** (`.html`) for Jekyll layouts and includes
- **YAML files** (`.yml`) for configuration and data

## Development Workflow

### Building the Site
```sh
# Install dependencies
make install

# Serve locally
make serve

# Build production assets
npm run build:production
```

### Code Quality
- Run Prettier on staged files automatically (pre-commit hook)
- Format code: `yarn format`
- Build webpack bundles: `yarn build`

## Documentation Guidelines

### Goal
The primary goal is to provide clear, accurate, and accessible documentation for Yarn Classic users. Documentation should:
- Be easy to understand for developers new to Yarn
- Provide practical examples and code snippets
- Maintain consistency with existing documentation style
- Support internationalization structure
- Be technically accurate and up-to-date

### Writing Style
- Use clear, concise language
- Include code examples where applicable
- Link to related documentation using `{{url_base}}` prefix
- Follow the established markdown format with proper front matter

### File Organization
- CLI documentation: `lang/en/docs/cli/`
- General docs: `lang/en/docs/`
- Organization docs: `lang/en/org/`
- Blog posts: `_posts/`

## Important Considerations

1. **This is Yarn Classic (v1)** - Not Yarn v2/Berry (that's a separate repository)
2. **Internationalization** - English is the primary language (`lang/en/`), other languages are ignored in git
3. **Static site** - Changes require rebuild, no server-side processing
4. **Bootstrap 4.0.0-alpha.5** - Using an alpha version of Bootstrap 4
5. **Node.js support** - Document supported Node.js versions: ^4.8.0 || ^5.7.0 || ^6.2.2 || >=8.0.0

## When Making Changes

- Test locally using `make serve` before submitting
- Ensure markdown files have proper front matter
- Keep line length reasonable for documentation files
- Use existing files as templates for new documentation
- Maintain the established URL structure for documentation
- Update `_config.yml` for site-wide configuration changes
