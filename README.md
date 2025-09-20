# LLM File Formatter

A lightweight, single‑file HTML app to quickly format local files for sharing with LLMs. Drag and drop files or select a whole folder, preview the formatted result, and copy everything to your clipboard in one click.

- Single file: `llm_file_formatter.html`
- No build, no dependencies, works fully offline
- English‑language interface (vanilla JavaScript)

## Features

- Drag & Drop: Drop files directly onto the page
- Folder Selection: Select entire folders with a tree view and checkboxes
- Smart Text Filtering: Ignores non‑text files, optional “Hide binaries” toggle
- Automatic Formatting: Wraps content in code fences with a language tag inferred from file extension
- Clipboard: Copies the prepared, escaped text to your clipboard
- Encoding: Choose between UTF‑8 and Windows‑1252 (ISO‑8859‑1) when reading files

## How It Works

- Text‑only: Files are treated as text if their MIME type starts with `text/` or their extension/name is commonly textual (e.g., `.js`, `.ts`, `README`, `Dockerfile`).
- HTML‑Safe: All content is HTML‑escaped before rendering.
- Robust Fences: Code fences use as many backticks as needed to avoid colliding with content that already contains backticks.
- Language Tag: Derived from the file extension (e.g., `ts` → `typescript`, `js` → `javascript`). If unknown, the fence is emitted without a tag.
- Output Shape:
  
  Filename: path/to/file.ext
  ```ext-or-lang
  <file contents>
  ```

## Usage

1. Open `llm_file_formatter.html` in your browser (double‑click the file).
2. Add files via either option:
   - Drag and drop files onto the drop area, or
   - Click “Add folder” to select a directory (tree with checkboxes appears).
3. Optional tweaks:
   - Toggle “Hide binaries” to filter out non‑text files in the tree.
   - Pick the appropriate “Encoding” before reading/copying.
4. Click “Copy to clipboard” to copy the formatted output.

Tip: When a folder is selected, you can choose specific files in the tree; the copy action will include only those selected files and preserve your selection order.

## Limits & Notes

- Per‑file size limit: 10 MB
- Total size limit: 50 MB
- Max characters per file content: 200,000 (excess is truncated and marked with `[...] content truncated ...]`)
- Max files per operation: 100
- Everything runs locally in your browser; nothing is uploaded anywhere.

## Browser Support

- Works in modern browsers. Folder selection uses `input.webkitdirectory`, which is supported in most Chromium‑based browsers and Safari. If unavailable, you can still use drag & drop to add multiple files.

## Development

- Everything lives in a single file: `llm_file_formatter.html`
- No external libraries or build steps. Just open the file and edit.
- Contributions and suggestions are welcome.

