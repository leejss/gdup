# gd-up - Google Drive Command Line Helper

A command-line tool for interacting with Google Drive, built with TypeScript.

## Features

- Upload files to Google Drive
- Upload directories recursively
- List files and directories in your Google Drive
- Download files from Google Drive
- Remove files from Google Drive

## Installation

```bash
# Install globally
npm install -g gd-up

# Or install locally
npm install gd-up
```

## Setup

Before using gd-up, you need to authenticate with Google Drive:

```bash
gd-up auth
```

This will open a browser window where you can authenticate and authorize the application to access your Google Drive.

## Usage

### Upload Files

```bash
# Upload a single file
gd-up file.txt

# Upload multiple files
gd-up file1.txt file2.jpg document.pdf

# Upload to a specific folder in Google Drive
gd-up --folderId "1234567890" file.txt
```

### Upload Directories

```bash
# Upload a directory recursively
gd-up -d my-directory

# Upload a directory to a specific folder in Google Drive
gd-up -d my-directory --folderId "1234567890"
```

### List Files and Directories

```bash
# List files in your Google Drive root
gd-up list

# List files in a specific folder
gd-up list --folderId "My Folder"

# List with more details
gd-up list --verbose
```

### Search for Files

```bash
# Search for files by name
gd-up list --search "document"

# Search with file type filter
gd-up list --search "photo" --type image
```

### Download Files

```bash
# Download a file by ID
gd-up download FILE_ID

# Download a file by name
gd-up download --name "document.pdf"

# Download to a specific directory
gd-up download FILE_ID --output ~/Downloads
```

### Remove Files

```bash
# Remove a file by ID
gd-up remove FILE_ID

# Remove a file by name
gd-up remove --name "document.pdf"

# Remove multiple files
gd-up remove FILE_ID1 FILE_ID2 FILE_ID3
```

## Options

| Option | Alias | Description |
|--------|-------|-------------|
| `--folderId` | `-f` | Specify the destination folderId in Google Drive |
| `--name` | `-n` | Specify a custom name for the uploaded file |
| `--recursive` | `-r` | Upload directories recursively |
| `--verbose` | `-v` | Show detailed information |
| `--output` | `-o` | Specify download location |
| `--type` | `-t` | Filter by file type |
| `--quiet` | `-q` | Suppress output |
| `--help` | `-h` | Show help |
| `--version` | | Show version |

## Examples

```bash
# Upload multiple files to a specific folder
gd-up --folderId "Work Documents" report.docx presentation.pptx

# Upload a directory with custom naming
gd-up -d project-files --name "Project X Files"

# Search for images and show details
gd-up list --search "vacation" --type image --verbose

# Download a file to a specific location
gd-up download 1a2b3c4d5e --output ~/Downloads/important-docs/

# Remove multiple files
gd-up remove 1a2b3c4d5e 2f3g4h5i6j
```
