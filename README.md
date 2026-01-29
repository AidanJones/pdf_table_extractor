# PDF Table Extractor

A browser-based tool to extract tables from PDF files. Upload a PDF and copy extracted tables as plain text, Markdown, or CSV.

## Try it

Open `index.html` in your browser - no server required.

## Features

- Drag & drop PDF upload
- Automatic table detection
- Export as tab-separated text, Markdown, or CSV
- Configurable minimum rows/columns for table detection
- Option to treat first row as header

## Inspiration

This tool is inspired by [simonw/tools](https://github.com/simonw/tools) - a collection of small, single-file HTML tools.

See that repository for many more examples of this approach.

## Design Philosophy

**Inline JavaScript and CSS in a single HTML file** means the least hassle in hosting or distributing them. Just upload the file somewhere, or send it to someone, and it works.

**No React, or anything with a build step.** The problem with React is that JSX requires a build step, which makes everything massively less convenient. Prompting "no react" skips that whole rabbit hole entirely.

**Load dependencies from a CDN.** The fewer dependencies the better, but if there's a well-known library that helps solve a problem, load it from cdnjs or jsdelivr or similar.

**Keep them small.** A few hundred lines means the maintainability of the code doesn't matter too much: any good LLM can read them and understand what they're doing, and rewriting them from scratch with help from an LLM takes just a few minutes.
