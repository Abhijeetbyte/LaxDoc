# LaxDoc

A computer application for small and micro enterprises to manage "frequently used small documents" such as letters, board resolutions, meeting minutes, work reports.

All these documents have a "common" format, and are used each time with some variations in the overall content such as date, time, and writing material or subject.

Recreating entire documents manually or reusing them by editing them, using software like MS Word, etc. is practical only for small numbers.

Using this method, it lacks quick searches like files by "date" or "short description". Also managing multiple pages inside a single word file will increase the risk of mismanagement and file corruption or sometimes software incompatibility.


**To do:**

It would be a good idea to create a dedicated computer application to serve this purpose,
with features like, quick search, strictly typed document formats using [LaTex](https://www.latex-project.org/), light weight files and auto indexing, storage and management.



## 1. The UI window of this application has the following features:

a. Option to create new file type (letter, meeting minutes, work report), it accepts desired standard format given by user as LaTex file.

b. Option to take user input parameters for the respective file. Like date, place, main content, any prefix for file numbering (auto.handled in backend).

c. Option to generate, new files for respective types, according to given contents.

d.  Option to index/search files in related types.




## 2. The backend of the application handles.

a. Storing standard file types in LaTex.

b. Outfile is being generated as .pdf

c. Saving the original contents of related files in pairs of file numbers.

d. Handle automatic indexing and entry of files into Table as CSV file.




## 3. Additional features :

a.Edit and delete a file (data and its index)

b. Option to generate the original file at any time e.g. if any file is found in search, then there is option to generate this file again.




## 4. Additional Information:

a. The CSV file in the backend stores the file index number in pair with the date and a short description of the file.

b. Main content file and other files are stored as .text file



<br/>

**Concept reference**: https://github.com/Abhijeetbyte/MYPmanager
Just for visuals and for a more clear image in mind.
.
