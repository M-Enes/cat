# Pat

A simple program to output file contents to standard output. Inspired by cat from GNU Coreutils.

## Compilation

Clone the repo if not already: `git clone https://github.com/m-enes/pat.git`. \
Go into repo directory: `cd pat`. \
Create bin directory: `mkdir bin`. \
Compile the source code: `gcc -Wall -Wextra -Wpedantic pat.c -o bin/pat`. \
Go into bin directory: `cd bin`. \
Create or copy a text file into the bin directory. \
Run the program: `./pat <filename>`, replace `<filename>` with the name of the file you want to read in the bin directory.

## Note on Windows

`pat` just reads bytes from file and send them to the standard output. \
In Linux, there is no problem with sending binary data to the console. \
But, in Windows, the console is in a certain encoding mode and it might affect the look of output from `pat`. \
So, if you know the encoding of the file, then: \
If you are using cmd: please switch to that encoding mode with a command like `chcp 65001` before running `pat`. \
If you are using powershell: please switch to that encoding mode with a command like `[Console]::OutputEncoding = [System.Text.Encoding]::UTF8` before running `pat`. \
Also, piping the output like `pat message.txt > copyofmessage.txt` works correctly regardless. (only if you use cmd, powershell seems not working even if you set the correct encoding mode).