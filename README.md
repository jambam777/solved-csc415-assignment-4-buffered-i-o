Download Link: https://assignmentchef.com/product/solved-csc415-assignment-4-buffered-i-o
<br>
You are to create a set of routines in a file called b_io.c (don’t forget to add this file in the Makefile list). The prototypes for these functions must be in a file called b_io.h (provided).

You will be just writing three functions in b_io.c

int b_open (char * filename);int b_read (int fd, char * buffer, int count);void b_close (int fd);Your functions here will only use Linux I/O APIs. i.e. read, open, close (do not use the c library file functions).

The b_open should return a integer file descriptor (a number that you can track the file). You may want to also allocate the 512 byte buffer you will need for read operations here. Make sure though you know how to track the buffer for each individual file. You can return the same error code you receive if the Linux open returns an error.

The b_read takes a file descriptor, a buffer and the number of bytes desired. The Operation of your b_read function must only read 512 bytes chunks at a time from the operating system into your own buffer, you will then copy the appropriate bytes from your buffer to the caller’s buffer. This means you may not even need to do a read of the actual file if your buffer already has the data needed. Or, it may mean that you have some bytes in the buffer, but not enough and have to transfer what you have, read the next 512 bytes, then copy the remaining needed bytes to the caller’s buffer.The return value is the number of bytes you have transferred to the caller’s buffer. When it is positive but less than the request, it means you have reached the end of file. Hint: You may also need to track between calls where in the buffer you left off.

The b_close should close the file on the Linux side, and free and resources you were using.

Limits: You can assume no more than 20 files open at a time.

Your main program (separate file) should use the command line arguments for the file to b_open. So your main program should open the file using b_open, read exactly 80 characters at a time from the file using b_read, print those 80 characters to the screen (ending in a newline character), and loop until you have read the entire file, then b_close the file and exit.

You are provided the file DecOfInd.txt as the file to read and display.

You should submit your source code file(s) and Makefile, along with a short writeup in PDF format that includes a description of what you did and the compilation and execution output from your program in GitHub, and the PDF in iLearn.

Your main program filenames should be &lt;lastname&gt;_&lt;firstname&gt;HW&lt;#&gt;_&lt;optional&gt;.&lt;proper extension&gt;