# LaTeX Document Template

This is a LaTeX document template designed for technical reports, academic papers, and project documentation. It is suposed to be cloned to other directory and changed.


## 🚀 Quick Start

### Prerequisites

1. **Install TeX Live**:
   - **Ubuntu/Debian**: `sudo apt install texlive-full`
   - **Fedora**: `sudo dnf install texlive-scheme-full`
   - **macOS**: Download from [MacTeX](https://www.tug.org/mactex/)
   - **Windows**: Download from [TeX Live](https://www.tug.org/texlive/)

2. **Install VS Code Extension**:
   - Open VS Code
   - Go to Extensions (Ctrl+Shift+X)
   - Search for "LaTeX Workshop" by James Yu
   - Install the extension

### Usage

1. **Clone or download** this template
2. **Open the folder** in VS Code
3. **Edit document** for your content
4. **Compile the document** by opening `main.tex` in VS Code and pressing Ctrl+Alt+B

## 🏗️ Building the Document

### Using LaTeX Workshop (VS Code)
1. Open `main.tex`
2. Use one of these methods:
   - Press `Ctrl+Alt+B` to build
   - Press `Ctrl+Alt+V` to view PDF
   - Use Command Palette (`Ctrl+Shift+P`) → "LaTeX Workshop: Build LaTeX project"

### Using Command Line
```bash
# Basic compilation
pdflatex main.tex

# With bibliography (if using BibTeX)
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

## 🚀 CI/CD Automation

This template includes GitLab CI/CD that automatically builds and releases your PDF documents.

### How to Use CI/CD

1. **Push your changes** to GitLab repository
2. **Create and push a tag** for releases:
   ```bash
   git tag v1.0.0
   git push origin v1.0.0
   ```
3. **Download the PDF** from GitLab releases

### What the CI/CD Does

- **Builds PDF automatically** on every push and merge request
- **Creates versioned releases** when you push a tag (e.g., `Report-v1.0.0.pdf`)
- **Uploads to Package Registry** for easy distribution
- **Creates GitLab releases** with direct download links

### CI/CD Configuration

To customize the CI/CD in `.gitlab-ci.yml`, update these variables:

```yaml
variables:
  FILE_PREFIX: "Report"          # Change this to your desired filename prefix
  FILE_SEPARATOR: "-"            # Separator between prefix and version
  PACKAGE_NAME: "${CI_PROJECT_NAME}-pdf"  # Package registry folder name
```

**Example**: With `FILE_PREFIX: "MyDocument"` and tag `v2.1.0`, you'll get `MyDocument-v2.1.0.pdf`

## 🎨 Tips for Usage

1. **Keep images organized** in the `Images/` directory with descriptive names
2. **Use consistent formatting** across all section files
3. **Comment your code** for future reference
4. **Use labels and references** for figures, tables, and equations
5. **Compile frequently** to catch errors early

---

*Happy LaTeX writing! 📝*

## How to hide trash files in vscode (ADDed by Afonso)

1. Open the command palette (Ctrl+Shift+P) and type Preferences: Open Settings (JSON).
2. Add or edit the files.exclude section like this:
```yaml
{
  "files.exclude": {
    "**/*.log": true,
    "**/*.aux": true,
    "**/*.out": true,
    "**/*.maf": true,
    "**/*.mtc*": true,
    "**/*.fls": true,
    "**/*.loc": true,
    "**/*.blg": true,
    "**/*.soc": true,
    "**/*.gz": true,
    "**/*.fdb_latexmk": true,
    "**/*.bbl": true,
    "**/*.toc": true
  }
}
```