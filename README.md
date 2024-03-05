# LaxDoc

LaxDoc is a computer application designed for small and micro enterprises to manage frequently used small documents such as letters, board resolutions, meeting minutes, and work reports. These documents follow a common format but require variations in content such as date, time, and subject matter.

Recreating entire documents manually or reusing the same document by editing it, using software like MS Word, is practical only for small numbers. However, this method lacks quick search capabilities, like searching files by date or short description. Additionally, managing multiple pages inside a single Word file increases the risk of mismanagement, file corruption, or software incompatibility.

**To-do:**

Creating a dedicated computer application with quick search, strictly typed document formats using LaTex, lightweight files, auto indexing, storage, and management features would be beneficial.

## 1. UI Features:

- Option to create new file types (letter, meeting minutes, work report) using the desired standard format provided by the user as a LaTex file.
  
- Option to input user parameters for the respective file, such as date, place, main content, and any prefix for file numbering (automatically handled in the backend).
- Option to generate new files for respective file types based on given contents.
  
- Option to index/search files in related types.

## 2. Backend Functionality:

- Storing standard file types in [LaTex](https://www.latex-project.org/)format.
  
- Generating output files as PDFs.
  
- Saving the original contents of related documents in pairs of assign file numbers.
  
- Handling automatic indexing and entry of documents into a table as a CSV file.

## 3. Additional Features:

- Edit and delete a file (data and its index).
- Option to generate the original file at any time. For example, if any file is found in search, then there is an option to regenerate this file again.

## 4. Additional Information:

- The CSV file in the backend stores the file index number paired with the date and a short description of the file.
- Main content files and other files are stored as .txt files.

**Concept reference:** [MYPmanager](https://github.com/Abhijeetbyte/MYPmanager) - For visuals and a clearer understanding.
