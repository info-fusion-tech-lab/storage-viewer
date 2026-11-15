# Storage Viewer CLI

![Python Version](https://img.shields.io/badge/python-3.7%2B-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![PyPI](https://img.shields.io/badge/pypi-v1.0.1-orange)

A powerful, feature-rich directory tree visualizer with advanced filtering options for the command line.

## Features

- **Hierarchical tree display** — Clean, readable directory structures
- **Advanced filtering** — Filter by extension, folder, pattern, and size
- **Size analysis** — Show file sizes in human-readable formats
- **File type icons** — Visual indicators for different file types
- **Depth control** — Limit directory traversal depth
- **Export capability** — Save tree structures to files
- **Statistics** — Summaries of directories and files
- **Fast and lightweight** — No external dependencies

## Installation

```
pip install storage-viewer
```

## Basic usage

View a directory tree:

```console
stree /path/to/directory
```

Show file type icons:

```console
stree . --icons
```

Show file sizes:

```console
stree . --show-size
```

Limit traversal depth:

```console
stree . --max-depth 3
```

## Examples

Exclude development folders:

```console
stree . --exclude-folders __pycache__,node_modules,.git,venv --max-depth 4
```

Find large files:

```console
stree /home --min-size 100M --show-size --sort-by size --reverse-sort
```

Export the tree to a file:

```console
stree /path --export directory_structure.txt
```

Show only code files:

```console
stree . --include-patterns "*.py,*.js,*.java,*.cpp"
```

Exclude temporary files:

```console
stree . --exclude-extensions tmp,bak,log --exclude-files "*.tmp,*.bak"
```

## Options

```text
Usage: stree [OPTIONS] PATH

Display directory tree structure with advanced filtering.

Options:
  --show-hidden          Show hidden files and folders
  --no-file              Exclude all files
  --no-folder            Exclude all folders
  --exclude-extensions   Comma-separated file extensions to exclude
  --exclude-folders      Comma-separated folder names to exclude
  --exclude-files        Comma-separated file patterns to exclude
  --include-patterns     Comma-separated patterns to include
  --max-depth            Maximum depth to traverse
  --min-size             Minimum file size (e.g., 1M, 100K, 1G)
  --max-size             Maximum file size (e.g., 1M, 100K, 1G)
  --show-size            Show file sizes
  --icons                Show file type icons
  --sort-by              Sort method: name, size, or type
  --reverse-sort         Reverse sort order
  --export               Export tree to specified file
  --version              Show version
  --help                 Show this help message
```
