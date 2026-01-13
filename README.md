# School Report LaTeX Template

A professional LaTeX template for internship reports and academic documents. This template is inspired by the official template recommended by INRIA for thesis manuscripts.

## Overview

This template provides a complete document structure with custom styling, cover pages, bibliography management, and glossary support. It uses XeLaTeX for advanced font support and includes D-DIN as the main font family with Inconsolata for code listings.

## Features

- Professional cover pages (front and back)
- Custom document class with consistent styling
- Bibliography management with biblatex and Biber
- Glossary and acronym support
- Code listings with syntax highlighting
- Automatic table of contents, figures, tables, and listings
- Header and footer customization
- Multi-language support (English by default)

## Requirements

### LaTeX Distribution

You need a full LaTeX distribution installed on your system:

- **TeX Live** (recommended) - Full installation
- **MiKTeX** (Windows) - Full installation
- **MacTeX** (macOS) - Full installation

### Additional Packages

Some packages may not be included in the basic installation. Install them using your distribution's package manager:

**Fedora / RHEL:**
```bash
sudo dnf install texlive-abstract texlive-wallpaper texlive-biblatex texlive-biber texlive-glossaries
```

**Debian / Ubuntu:**
```bash
sudo apt-get install texlive-full
```

**Arch Linux:**
```bash
sudo pacman -S texlive-most
```

**macOS (MacTeX):**
The full MacTeX distribution includes all necessary packages.

## Repository Structure

```
.
├── main.tex                    # Main document file
├── school-report.cls           # Custom document class
├── Makefile                    # Build automation
├── glossary.tex                # Glossary and acronym definitions
│
├── cover/                      # Cover page files
│   ├── front.tex              # Front cover content
│   ├── back.tex               # Back cover content
│   ├── company.png            # Company logo
│   ├── enib_inp.png           # School logo
│   └── profile.jpg            # Profile picture
│
├── introduction/               # Introduction chapter
├── chapter1/                   # Chapter 1
├── chapter2/                   # Chapter 2
├── chapter3/                   # Chapter 3
├── conclusion/                 # Conclusion chapter
├── appendix/                   # Appendices
│
├── biblio/                     # Bibliography files
│   └── biblio.bib             # Bibliography database
│
├── d-din/                      # D-DIN font files
└── inconsolata-4/              # Inconsolata font files (code listings)
```

## Getting Started

### 1. Customize the Cover Pages

Edit the cover page files to add your information:

**Front Cover (`cover/front.tex`):**
- Author name
- Report title
- Semester information
- Date and location
- Jury members
- Company information
- Student email

**Back Cover (`cover/back.tex`):**
- Subject
- Keywords
- Work done summary
- Company feedback
- Conclusion

### 2. Add Your Content

Edit the chapter files in their respective directories:
- `introduction/introduction.tex`
- `chapter1/chapter1.tex`
- `chapter2/chapter2.tex`
- `chapter3/chapter3.tex`
- `conclusion/conclusion.tex`
- `appendix/appendix.tex`

### 3. Customize Logos and Images

Replace the logo files in the `cover/` directory:
- `company.png` - Company logo
- `enib_inp.png` - School logo
- `profile.jpg` - Profile picture

The logo paths can also be modified in `school-report.cls` if you prefer different file names or locations.

### 4. Add Bibliography Entries

Add your references to `biblio/biblio.bib` in BibTeX format. The template uses biblatex with the IEEE citation style by default.

### 5. Define Glossary Terms

Add glossary entries and acronyms in `glossary.tex` using the `\newglossaryentry` and `\newacronym` commands.

## Compilation

The template includes a Makefile to simplify the compilation process.

### Basic Compilation

Compile the document and generate the PDF:

```bash
make
```

or

```bash
make pdf
```

### View the PDF

Compile and open the PDF in your default viewer:

```bash
make viewpdf
```

### Clean Build Files

Remove all auxiliary files generated during compilation:

```bash
make clean
```

**Note:** The compilation process runs XeLaTeX multiple times to properly resolve cross-references, citations, and glossary entries. This is normal and expected.

## Manual Compilation

If you prefer to compile manually, use the following sequence:

```bash
xelatex main.tex
biber main
makeglossaries main
xelatex main.tex
```

## Customization

### Changing Fonts

The template uses D-DIN as the main font family. Font settings are defined in `school-report.cls`. To change fonts, modify the `\setmainfont`, `\setsansfont`, and `\setmonofont` commands.

### Modifying Document Class

The document class file `school-report.cls` contains:
- Package imports and configuration
- Page layout and geometry settings
- Header and footer definitions
- Custom environments and commands
- Bibliography and glossary settings

Modify this file to customize the overall document appearance and behavior.

### Citation Style

The template uses the IEEE citation style by default. To change it, modify the `biblatex` package options in `school-report.cls`:

```latex
\RequirePackage[
  backend=biber,
  style=ieee  % Change this to your preferred style
]{biblatex}
```

Available styles include: `numeric`, `alphabetic`, `authoryear`, `ieee`, `apa`, etc.

## Troubleshooting

### Missing Font Warnings

If you see font warnings, ensure that:
- The D-DIN font files are present in the `d-din/` directory
- The Inconsolata font files are present in the `inconsolata-4/` directory
- XeLaTeX is being used (not pdfLaTeX)

### Bibliography Not Appearing

If citations are not resolved:
1. Ensure `biber` is installed
2. Run `biber main` after the first LaTeX compilation
3. Run LaTeX again to include the bibliography

### Glossary Not Appearing

If glossary entries are not showing:
1. Ensure `makeglossaries` is installed
2. Run `makeglossaries main` after the first LaTeX compilation
3. Run LaTeX again to include the glossary

### Compilation Errors

If you encounter compilation errors:
1. Check the `.log` file for detailed error messages
2. Ensure all required packages are installed
3. Verify that all referenced files exist
4. Try cleaning with `make clean` and recompiling

## License

This template is provided as-is for academic and educational purposes.

## Contributing

Contributions, suggestions, and improvements are welcome. Please feel free to open issues or submit pull requests.

## Acknowledgments

This template is inspired by the INRIA Thesis Template available at:
https://gitlab.inria.fr/ed-mathstic/latex-template
