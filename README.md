# LaxDoc

LaxDoc is a computer application designed for small and micro enterprises to manage frequently used small documents such as letters, board resolutions, meeting minutes, and work reports. These documents follow a common format but require variations in content such as date, time, and subject matter.

Recreating entire documents manually or reusing the same document by editing it, using software like MS Word, is practical only for small numbers. However, this method lacks quick search capabilities, like searching files by date or short description. Additionally, managing multiple pages inside a single Word file increases the risk of mismanagement, file corruption, or software incompatibility.

**To-do:**

Creating a dedicated computer application with quick search, strictly typed document formats using LaTex, lightweight files, auto indexing, storage, and management features would be beneficial.

## 1. UI Features:

- Option to create new file types (letter, meeting minutes, work report) using the desired standard format provided by the user as a LaTex file.

- Option to generate new documents for respective file types based on given contents.
    
- Option to input user contents as parameters for the respective documents, such as date, place, main content, and any prefix for it's numbering (automatically handled in the backend).

  
- Option to index/search files in related types.

## 2. Backend Functionality:

- Storing standard document types in [LaTex](https://www.latex-project.org/) format.
  
- Generating final output as PDFs.
  
- Saving the original contents of related documents in pairs of assign file numbers.
  
- Handling automatic indexing and entry of documents into a table as a CSV file.

## 3. Additional Features:

- Edit and delete document types (standard format)

- Edit and delete a document (data and its index/numbering).
  
- Option to generate the original document at any time. For example, if a document is searched and found, then there is an option to regenerate it again as PDF.

## 4. Additional Information:

- The CSV file in the backend stores the document index number paired with the date and a short description of the it.
  
- Perticular content of documents and other files are stored as .txt files.

**Concept reference:** [MYPmanager](https://github.com/Abhijeetbyte/MYPmanager) - For visuals and a clearer understanding.
