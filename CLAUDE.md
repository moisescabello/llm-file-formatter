# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a standalone HTML file application that formats files for sharing with LLMs. The application provides a drag-and-drop interface to convert file contents into a formatted text output suitable for copying to the clipboard.

## Architecture

**Single-file application**: `llm_file_formatter.html`
- Self-contained HTML page with embedded CSS and JavaScript
- No build process or external dependencies
- Uses vanilla JavaScript for all functionality
- English-language interface

## Key Features

1. **Drag & Drop Interface**: Users can drag files directly onto the drop zone
2. **Folder Selection**: Supports selecting entire folders with a tree view for selective file inclusion
3. **Automatic Formatting**: Converts files into markdown code blocks with appropriate syntax highlighting
4. **Clipboard Management**: Automatically copies formatted content to clipboard

## Development Notes

- The application escapes HTML content to prevent rendering issues
- File paths are built using `webkitRelativePath` for folder selections
- Tree view allows checkbox selection of individual files or entire folders
- Output format includes filename and code block with file extension for syntax highlighting
- Code should be as efficient and lean as possible (avoid unnecessary complexity, minimize memory usage, and prefer simple, performant solutions)

## Git and GitHub Conventions

- **No emojis in GitHub**: Do not use emojis in commit messages, release notes, or pull requests
- Keep commit messages clear and professional
- Use conventional commit format when appropriate (feat:, fix:, docs:, etc.)
- Release notes should be clean and technical without decorative elements
