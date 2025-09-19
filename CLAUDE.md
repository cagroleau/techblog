# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hugo static site project using the "Goa" theme - a clean, minimalist theme for personal blogs and websites. The site belongs to Chris Groleau, a DataOps Engineer exploring DevOps and Data intersections.

## Key Commands

### Development
- `hugo server` - Start development server (builds drafts by default)
- `hugo server -D` or `hugo server --buildDrafts` - Start server including draft posts
- `hugo server --port 1314` - Start server on custom port

### Content Creation
- `hugo new content posts/post-name.md` - Create new blog post
- `hugo new projects/index.md` - Create new standalone page (like projects, about)

### Building and Publishing
- `hugo` - Build site for production (excludes drafts)
- `hugo --cleanDestinationDir` - Clean build (removes old files from public/)
- `hugo --buildDrafts` - Build including draft content

## Site Structure

### Content Organization
- `/content/posts/` - Blog posts in markdown format
- `/content/about/` - About page with index.md override
- `/archetypes/` - Content templates for new posts
- `/static/` - Static assets (images, custom CSS/JS)
- `/assets/images/` - Images processed by Hugo
- `/public/` - Generated static site (created by hugo build)

### Theme Architecture
- Uses "Goa" theme located in `/themes/goa/`
- Theme provides layouts in `/themes/goa/layouts/`
- Main layout files: `index.html`, `_default/single.html`, `_default/list.html`
- Partials in `/themes/goa/layouts/partials/` for reusable components

### Configuration
- `hugo.toml` - Main site configuration
- Key settings: author, intro, description, authorimage, menu structure
- Theme configured with social media links, meta tags, and display options

## Content Management

### Post Front Matter
Posts use TOML front matter with:
- `date` - Publication date
- `title` - Post title  
- `draft` - true/false (drafts not included in production builds)
- `categories` and `tags` - For organization

### Publishing Workflow
1. Create content with `hugo new content posts/title.md`
2. Edit content and set `draft = false` when ready
3. Test with `hugo server -D` during development
4. Build with `hugo --cleanDestinationDir` for production

## Theme Customization

The Goa theme supports:
- Custom CSS in `/static/css/custom.css`
- Custom JavaScript in `/static/js/custom.js`
- Author image configuration via `authorimage` parameter
- Social media integration via `[params.social]` section
- Menu customization via `[[menu.main]]` sections