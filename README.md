# Installing and Getting Started with the 8088 Assembler And Tracer Toolkit (v. 1.0)
##Andrew Lee Instructions
*These instructions are my own. However, if you prefer to use the original instructions that were created by Hawken Rives, go to StoDevX Directions at the below*

The following commands will download the source files for as88, s88, and t88, build them manually for Mac or Linux.
Furthermore, it will create symbolic links via the "sudo ln -s" commands to ensure you can use as88, s88, and t88 without having to copy them in the same directory you saved your source files.

```
cd ~/
git clone https://github.com/gilgameshskytrooper/as88.git cs241_assembly
cd cs241_assembly
bash asinstall.sh
sudo ln -s ~/cs241_assembly/trce_src/s88 /usr/bin/s88
sudo ln -s ~/cs241_assembly/trce_src/t88 /usr/bin/t88
sudo ln -s ~/cs241_assembly/as_src/as88 /usr/bin/as88
```

*If you do not clone this into ~/ (your home directory), then replace the path of ~/cs241_assembly/... appropriately during the symbolic linking step. Furthermore, you can always go ahead and delete the symlinks using the following command ```sudo rm /usr/bin/as88``` (if you want to delete the symbolic link to the as88 program)*

Now, should be able to assembly using "as88" and execute using "s88" (without the need to copy over the programs to the directory you want to use it in)

To test:
```
cd HD/as88
as88 hello
s88 hello
```

*You might get some type of error, but just see if your code runs or not.*

##StoDevX Directions
Intel-based Linux version

NOTE: If at any point while installing the software supplied on this CD, you are presented with an error message that states you do not have the correct privileges or permissions to install the software, you will need to log off and then log on as the Administrator (or as another user with administrative permissions). If you are installing this software at a company, educational institution, or other organizational site, you may need to ask your system administrator for assistance or for an appropriate password.

To install this software on Intel-based Linux systems, follow these steps:


## I. Copying the 8088 Assembler and Tracer Toolkit to your Hard Disk

1. If you have not done so already, create a directory named `tracer` on your hard disk. This is where you will place all the software in the 8088 Assembler and Tracer Toolkit. 

2. If you have not done so already, browse the CD-ROM to the /8088_tracer/linux directory, and copy all of its contents to the new tracer directory you just created on your hard disk. 

3. Make sure the following directories and files now exist within your new tracer directory:

Directories: 

	as_src/
	bin/
	examples/
	exercises/
	trce_src/

Additional files in the main tracer directory: 

	asinstal.bat
	README.txt
	release.txt
	syscalnr.h


## II. Testing the 8088 Assembler and Tracer toolkit 

1. Change to the `/tracer/examples` directory. 

2. Run the first example program. Type: 

		./t88 HlloWrld


## III. Getting started with the 8088 Assembler and Tracer toolkit

### A. INTRODUCTION

This section contains notes intended to help you quickly begin working with the 8088 Assembler and Tracer Toolkit. For more detailed instructions, please see Appendix C of the book. 

Within the tracer directory, you can find precompiled sources in the `bin` subdirectory. For your convenience, copies of the binaries also appear in the examples and exercise subdirectories.

Source code for the assembler is in the subdirectory `as_src`. 

Source code for the interpreter `s88` and debugger-tracer `t88` is in the subdirectory trce_src.

The only important difference between the interpreter `s88` and the tracer `t88` is that the interpreter does not display the tracer window, and does not accept tracer commands from standard input. All other steps independent of the tracing process are identical.

### B. COMPILATION

C-based source files are provided in the event you ever need to recompile this software. On Unix and Linux platforms, the command "make" should recompile the sources and place the binaries in the directories "bin", "examples", and "exercise."

To recompile, you need a working C compiler installed. If you have one, you can compile by typing:

	asinstal

After you compile, either move your executable files to a program directory, or change the PATH variable to make the assembler `as88` and the tracer `t88` visible from the directories containing the assembly source codes.

### C. CREATING BINARIES

Assembler source files have an extension ".s". To create a binary for a source named "project.s", enter the command:

	as88 project

This performs the assembly, and generates three files:

- `project.88` — The 8088 binary
- `project.#` — A file which links the file positions in the source file to the positions in the binary file
- `project.$` — A copy of the source file which contains included secondary sources and satisfies preferred conventions for the assembly process

The tracer subwindow for the source file displays the "project.$" version.

### D. TRACING

To trace a file, use the command `t88`. For example, to trace a file named "project," enter the command:

	t88 project

This displays the registers, stack, portions of memory, and other information in a set of windows, enabling you to observe execution.

The tracer executes exactly on assembler command when the return key is hit. To stop execution, type the command "q", followed by a return. Execution stops on its own when the process itself exits.

To interpret a file without displaying the tracer window, use the s88 Command. For example, to interpret a file named "project," enter the command:

	s88 project

The entire assembler project uses command line terminal windows. This is commonplace on Posix compliant systems, but less typical for Windows platforms.

Additional notes on the current implementation, known bugs, and restrictions can be found in the file `release.txt` in this directory.

Good Luck,
Evert Wattel (<evert@cs.vu.nl> or <e.wattel@few.vu.nl>)
Vrije Universiteit, Amsterdam
