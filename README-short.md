# LaxDoc

LaxDoc is a computer application designed for small and micro enterprises to manage "frequently used small documents" such as letters, board resolutions, meeting minutes, and work reports. These documents often follow a common/standard format, and whenever they are prepared, only a few changes are required in the overall content such as date, place, subject matter etc.

Recreating an entire document manually or reusing the same document by editing it, using software like MS Word, is practical only for small numbers. However, this method lacks quick search capabilities, like searching files by date or short description. And have to do manual entry of documents for indexing. Additionally, managing multiple pages inside a single Word file increases the risk of mismanagement, file corruption, or software incompatibility.

**To-do:**

Creating a dedicated computer application with "quick search", and "strictly typed document formats/templates" using LaTex, lightweight files, auto-indexing, storage, and management features would be beneficial.

## 1. UI Features:

- Option to import LaTeX-based document templates for letters, meeting minutes, work reports, etc.. by the user.

- Option to generate new documents for respective templates based on user-given contents.
    
- Option to input user contents as parameters such as date, place, main content, and any additional prefix etc, for respective documents.
  
- Option to index/search previously generated documents.

- Option to index/search  standard/template files.

- Option to regenerate the original document at any time. If the template and main contents files have not been deleted.
  

## 2. Backend Functionality:

- Storing template files in [LaTex](https://www.latex-project.org/) format.
  
- Generating final output documents as PDFs based on user inputs.
  
- Saving the user-given contents of a document in pairs of assigned index numbers (auto handle in the backend) and corresponding template type.
  
- Automatic **indexing** and entry of documents into tabular form as **CSV**.

## 3. Additional Features:

- Delete/export template files.

- Edit and delete a document (main content and its index/numbering).
  

## 4. Additional Information:

- **"Dynamic Document Configuration Function"** is a  document index allocation function, used for automatically assigning documents it's unique index/entry addresses. It can operate on numbering system given by the user (date/prefix/number, etc.) also on the the default system, which is based on the document type, date, sequence and other parameters.

- The **CSV** file in the backend stores the document index number paired with the date, short description (asked by the user while saving), information of its main content and corresponding template type used.
  
- Particular content of documents and other files are stored as .txt files.

**Concept reference:** [MYPmanager](https://github.com/Abhijeetbyte/MYPmanager) - For visuals and a clearer understanding.
