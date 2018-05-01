##How to generate Tag36h11 family AprilTag mosaic

####ApirlTags are arranged in grids. Id of the tags starts from 0 at the top left corner.

1. Open **tag_mosaic.ps** with text editor
2. Find the following lines in the begining of the file: 
    ```
    % set page size and resolution, here 21 inches and 300 DPI
    /pagewidth 21 300 mul def
    /pageheight 21 300 mul def

    % generating a 7 by 7 mosaic
    /rows 7 def
    /columns 7 def
    ```
3. Change settings suitable to your application like physical size of file(height and width), file resolution(DPI), and size of the mosaic (number of rows and columns):
    **ie.** generating 8.5in x 11in letter size, 72dpi, 5 by 5 mosaic
    ```
    /pagewidth 8.5 72 mul def
    /pageheight 11 72 mul def

    /rows 5 def
    /columns 5 def
    ```

4. To convert PostScript into PDF file, in terminal, use command: 
    ```
    gs -o /directory/to/output_file.pdf -sDEVICE=pdfwrite -dDEVICEWIDTHPOINTS=612 -dDEVICEHEIGHTPOINTS=792 -dPDFFitPage /directory/to/input_file.ps
    ```

    Height points: 612 = 8.5 * 72; 
    Width points: 792 = 11 * 72

    For viewing only,
    ```
    gs -dDEVICEWIDTHPOINTS=612 -dDEVICEHEIGHTPOINTS=792 /directory/to/input_file.ps
    ```

---
* AprilTag image hex are from [AprilTag](https://april.eecs.umich.edu/software/apriltag/)
* **.ps** file is **PostScript** file. It can be converted to **.pdf** by **gs**
* The **gs** command invokes **Ghostscript**, an interpreter  of  Adobe  Systems' PostScript(tm)  and Portable Document Format (PDF) languages. [From Ubuntu Manual](http://manpages.ubuntu.com/manpages/artful/man1/gs.1.html)