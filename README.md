

# **LaxDoc**

**LaxDoc** is a desktop-based computer application built using Python. It is designed for **small and micro enterprises** to efficiently manage **frequently used short-format documents** such as:

- Letters  
- Board Resolutions  
- Meeting Minutes  
- Work Reports  

These types of documents often follow a common and repetitive structure. In most cases, only a few key elements such as the **date**, **location**, **subject**, or **core message** change with each use. However, retyping or manually editing the same document each time using general-purpose word processors (e.g., MS Word) becomes inefficient and error-prone.

Using MS Word or similar tools may be feasible for occasional document creation. But in real operational environments, this approach leads to:
- Lack of structured document indexing
- Difficulty in retrieving old records quickly
- File mismanagement due to editing overlaps
- Software compatibility issues across systems
- No control over format consistency

---

###  **Purpose and Objective**

The goal of this application is to provide a **dedicated desktop solution** with the following core principles:

- Use of **strict, typed document templates** created using LaTeX
- Quick generation of documents through user-defined parameters
- Built-in indexing and search capabilities
- Lightweight and portable storage using `.csv` and `.txt`
- Guaranteed format consistency using LaTeX formatting
- Reliable offline use with PDF exports

---

## 1. User Interface Features

The graphical user interface of this application is developed using the `tkinter` and `customtkinter` Python libraries. The interface provides a minimal but functional window-based experience with clearly labeled sections for each operation.

---

### - **Option to Import LaTeX Templates**

The user is provided with the option to import LaTeX `.tex` files that are used as document templates. These files must contain variable placeholders (e.g., `{{date}}`, `{{subject}}`, `{{content}}`) which are automatically detected and listed for input.

Each imported template is assigned a **type name** and stored internally in a designated folder. Templates can be reused indefinitely and referenced by their name in the document creation process.

---

### - **Option to Generate New Documents**

The user can generate a new document by selecting any previously imported template and supplying values for all required placeholders. A dedicated form is generated dynamically based on the detected placeholders in the template.

For example, if the template contains `{{date}}`, `{{place}}`, `{{subject}}`, and `{{body}}`, the application will show four input fields labeled accordingly.

The user fills in each field and clicks on a “Generate Document” button. Upon submission, a `.pdf` file is created automatically and saved to the local directory.

---

### - **Option to Input Document Parameters**

All templates are driven by placeholders. The application automatically reads each placeholder from the LaTeX template and displays a corresponding input field.

The user is expected to enter:
- Date (in a consistent format)
- Place of issue
- Subject line or topic
- Content paragraph or resolution text
- Any other required prefix or suffix

These values are inserted into the LaTeX structure and compiled into a complete PDF document.

---

### - **Option to Index and Search Previously Generated Documents**

Every document generated is saved in a structured folder along with metadata. A master `.csv` file is maintained as an index table. This allows the user to search previously generated documents by:
- Date
- Template type
- Short description (provided during save)
- Document index number (auto-generated)

A search bar is provided in the GUI to perform filtered lookups.

---

### - **Option to Index and Search Template Files**

Template files imported into the system are also indexed. Users can search and filter templates by:
- Template type name
- Date of import
- Internal identifier

This feature helps in managing a large number of template types across use cases.

---

### - **Option to Regenerate Original Documents**

If a document’s original `.txt` input file and its associated LaTeX template are still present in the system, the exact same document can be regenerated at any time.

This allows for future re-use, corrections, or duplications without re-entering all parameters manually. It also supports PDF re-export in case the file is lost or needs to be printed again.

---

## 2. Backend Functionality

All backend processes are handled using standard Python and open-source modules only. No external or proprietary dependency is introduced.

---

### - **Storage of Template Files**

Template files are stored in `.tex` format inside a fixed folder (e.g., `templates/`). Each file is named using its template type and a unique ID.

The LaTeX file is expected to use `{{variable_name}}` syntax to indicate dynamic placeholders. These are parsed using regular expressions.

---

### - **PDF Generation from LaTeX Templates**

When a user submits a new document for generation:
1. The application creates a temporary `.tex` file with all placeholders replaced by user values.
2. A system call is made using Python’s `subprocess` module to compile this `.tex` file using `pdflatex` or `lualatex`.
3. The output is stored as a `.pdf` file in a dedicated `documents/` folder.

If any compilation error occurs, the LaTeX log is captured and shown to the user for manual correction.

---

### - **Storage of User Content in `.txt` Files**

For every document generated, the user input is saved into a `.txt` file named using the document’s index number.

This file contains key-value pairs in a readable format (e.g., `date = 2024-05-12`, `place = Delhi`), allowing easy inspection or reuse.

---

### - **Automatic Indexing and CSV Entry**

An index number is assigned automatically to each new document using a configurable logic system (see below). Each new document's details are written into a master `.csv` file that serves as the internal registry of all generated documents.

The `.csv` file contains the following columns:
- Document Index Number
- Template Type Name
- Date of Generation
- Short Description (provided by user)
- Reference to Parameter File
- Path to PDF File

This index is used for search, management, and regeneration.

---

## 3. Additional Features

### - **Delete or Export Template Files**

A user is allowed to:
- Permanently delete a template
- Export a template as a `.zip` or `.tex` file for use on another system

Templates in use by documents are warned before deletion.

---

### - **Edit or Delete Documents**

A document can be:
- Edited by updating its parameter `.txt` file
- Deleted permanently from the system, including its PDF, `.txt`, and `.csv` entries

All operations are validated before execution and must be confirmed by the user.

---

## 4. Dynamic Document Configuration Function

LaxDoc includes an internal feature for automatic document numbering and ID generation, referred to as the **Dynamic Document Configuration Function**.

This function assigns each new document a unique index. The numbering format can be:
- Based on template type + date + sequence number  
  (e.g., `LET-20240326-01`)
- Custom prefix and numbering provided by the user  
  (e.g., `BR-March24-A1`)

If no format is specified, the system falls back to a default ID scheme.

This function ensures:
- Each document has a permanent identifier
- No duplicate entries are created
- Documents are easily referenced in reports or directories

---

## 5. File Formats and Folder Structure

The application uses the following data storage conventions:

- Template files → `.tex` → stored in `/templates`
- User input parameters → `.txt` → stored in `/data`
- Generated PDFs → `.pdf` → stored in `/documents`
- Document index → `.csv` → stored as `/index.csv`

All paths are internally managed and updated automatically when templates or documents are added, edited, or removed.

---

## 6. Technology Stack

| Component                    | Library / Tool                 |
|------------------------------|--------------------------------|
| Application Language         | Python 3.x                     |
| GUI Framework                | `tkinter`, `customtkinter`    |
| PDF Compilation              | `pdflatex` or `lualatex`      |
| System Calls                 | `subprocess` (Python stdlib)  |
| PDF Preview (optional)       | `PyMuPDF` or `tkPDFViewer`    |
| File I/O                     | `os`, `shutil`, `pathlib`     |
| Data Management              | `csv`, `json`, `configparser` |
| String/Tag Parsing           | `re` (regular expressions)    |
| Error Logging                | `logging` (Python stdlib)     |
| Application Packaging        | `PyInstaller` for `.exe`      |

---

## 7. Platform Compatibility

- LaxDoc is developed for **Windows 10 and higher**.
- All operations are offline. No internet connection is required.
- The application is distributed as a **standalone `.exe` file** built using **PyInstaller**.
- A local installation of **LaTeX (TeX Live or MiKTeX)** is required for document compilation.

---



## Prerequisites

Before installing or running **LaxDoc**, the following software components and system requirements must be fulfilled:

---

### 1. Python Environment

The application is written in **Python 3**, and should be run using:

- **Python Version**:  
  `Python 3.10` or higher is recommended (minimum `3.8`)

- **Recommended Python Distribution**:  
  - [Python.org official installer](https://www.python.org/downloads/) (Windows 64-bit)
  - Anaconda or Miniconda (optional, for isolated environments)

---

### 2. Required Python Modules

The following Python libraries must be installed before running the program:

| Module Name       | Purpose                                  |
|-------------------|------------------------------------------|
| `tkinter`         | GUI interface (bundled with Python)      |
| `customtkinter`   | Modern themed GUI components             |
| `subprocess`      | System calls for LaTeX compilation       |
| `os`, `shutil`    | File and folder operations               |
| `pathlib`         | Cross-platform path handling             |
| `csv`             | Document metadata storage                |
| `re`              | Placeholder parsing in LaTeX templates   |
| `logging`         | Error logging and tracking               |
| `PyMuPDF` (optional) | PDF preview rendering (for viewer)   |

To install missing libraries (especially `customtkinter` and `PyMuPDF`), use the following command:

```bash
pip install customtkinter pymupdf
```

---

###  3. System-Level Requirements

To compile LaTeX templates into PDF files, a LaTeX engine must be installed separately on the system.

- **LaTeX Distribution (One Required)**:
  -  [TeX Live](https://www.tug.org/texlive/windows.html) (recommended for full features)
  -  [MiKTeX](https://miktex.org/download) (recommended for Windows users)

> After installation, ensure that the LaTeX compiler (e.g., `pdflatex`) is available in the system's PATH environment variable.

---

###  4. LaTeX Packages

The following LaTeX packages should be available in the installed distribution (most are bundled by default):

- `geometry`  
- `babel`  
- `amsmath`, `amssymb`  
- `graphicx`, `xcolor`  
- Any other packages referenced by user-imported templates

>  If using **MiKTeX**, missing packages may be downloaded automatically at runtime.

---

###  5. Platform Compatibility

- **Operating System**: Windows 10 or higher (64-bit)  
- **Offline Use**: All features are available offline after setup  
- **Packaging Tool**: Final build distributed as `.exe` using `PyInstaller`

---
