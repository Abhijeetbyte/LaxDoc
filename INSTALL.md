# INSTALLATION GUIDE

This document provides step-by-step instructions to install and configure LaxDoc on a Windows system.

---

## Prerequisites

Before running LaxDoc, ensure the following components are installed and configured:

### 1. LaTeX Distribution (for PDF Generation)
To compile .tex templates into PDF format, one of the following LaTeX distributions must be installed:

- TeX Live (recommended)
  - Download: https://www.tug.org/texlive/windows.html

- MiKTeX (suitable for Windows users)
  - Download: https://miktex.org/download

After installation, verify that the LaTeX compiler (such as pdflatex) is available in the system PATH by running the following command in Command Prompt:

```
pdflatex --version
```

If the installation is successful, this will display the LaTeX version.

### 2. LaTeX Package Requirements
The following LaTeX packages are commonly required by templates used in LaxDoc:
- geometry
- babel
- amsmath, amssymb
- graphicx, xcolor
- Any additional packages referenced by the imported LaTeX templates

MiKTeX users may allow the installer to download missing packages automatically when compiling documents.

---

## Running the Application

### Running from Source Code
1. Python 3.10 or higher must be installed.
2. Required Python libraries:
   - Install using the command:
     ```
     pip install customtkinter pymupdf
     ```
3. Open a terminal in the project directory.
4. Run the application using the following command:
   ```
   python main.py
   ```

### Running from Executable (.exe)
1. Python installation is **not required**.
2. Required Python libraries are bundled inside the executable.
3. Ensure a LaTeX distribution is installed and configured (as noted above).
4. Double-click the `LaxDoc.exe` file.
5. The application should open and operate normally.

---

## Notes
- The application works fully offline.
- A working LaTeX engine is mandatory for generating PDF files.
- All templates and document files are stored in structured folders managed automatically by the application.
- If errors occur during LaTeX compilation, check the template file for syntax issues and ensure the required LaTeX packages are available.

