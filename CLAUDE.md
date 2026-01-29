# CLAUDE.md

This file contains design decisions and guidelines for Claude Code when working on this project.

## Project Overview

This repository contains single-file HTML tools inspired by [simonw/tools](https://github.com/simonw/tools).

## Design Principles

### Single HTML File Architecture

All tools should be self-contained in a single HTML file with inline CSS and JavaScript. This approach minimizes hosting and distribution hassle - just upload the file somewhere or send it to someone.

### No Build Steps

**Never use React or any framework requiring a build step.** JSX requires transpilation, which adds complexity. When prompting LLMs, explicitly request "no react" to avoid this pattern.

Vanilla JavaScript is preferred. If a framework is truly needed, use something that works directly in the browser without compilation.

### CDN Dependencies

Load external libraries from CDNs (cdnjs, jsdelivr, unpkg) rather than bundling them. Keep dependencies minimal - only add a library if it genuinely solves a problem that would be complex to implement manually.

Current dependencies:
- PDF.js from cdnjs for PDF parsing

### Keep Code Small

Target a few hundred lines per tool. At this scale:
- Maintainability concerns are minimal
- Any capable LLM can read and understand the entire codebase
- Rewriting from scratch with LLM assistance takes minutes, not hours

### File Naming

- Main tool files: `index.html` (for single-tool repos) or descriptive names like `tool-name.html`
- Keep filenames lowercase with hyphens

## Development Guidelines

When modifying or creating tools:

1. Write all CSS in a `<style>` tag in the `<head>`
2. Write all JavaScript in a `<script>` tag before `</body>`
3. Use modern ES6+ JavaScript (async/await, arrow functions, template literals)
4. No transpilation, no bundling, no npm packages
5. Test by opening the HTML file directly in a browser
