# CS6233-Homework-1-solved

Download Here: [CS6233 Homework 1 solved](https://jarviscodinghub.com/assignment/homework-1-solved/)

For Custom/Original Work email jarviscodinghub@gmail.com/whatsapp +1(541)423-7793

Part 1: Hello World (20 points)
Write a program for xv6 that, when run, prints “Hello world” to the xv6 console. This can be
broken up into a few steps:
1. Create a file in the xv6 directory named hello.c
2. Put code you need to implement printing “Hello world” into hello.c
3. Edit the file Makefile, find the section UPROGS (which contains a list of programs to be
built), and add a line to tell it to build your Hello World program. When you’re done that
portion of the Makefile should look like:
UPROGS=\
_cat\
_echo\
_forktest\
_grep\
_init\
_kill\
_ln\
_ls\
_mkdir\
_rm\
_sh\
_stressfs\
_usertests\
_wc\
_zombie\
_hello\
4. Run make to build xv6, including your new program (repeating steps 2 and 4 until you
have compiling code)
5. Run make qemu to launch xv6, and then type hello in the QEMU window. You should
see “Hello world” be printed out.
Of course step 2 is where the bulk of the work lies. You will find that many things are subtly
different from the programming environments you’ve used before; for example, the printf
function takes an extra argument that specifies where it should print to. This is because you’re
writing programs for a new operating system, and it doesn’t have to follow the conventions of
anything you’ve used before. To get a feel for how programs look in xv6, and how various APIs
should be called, you can look at the source code for other utilities: echo.c, cat.c, wc.c, ls.c.
Hints:
1. In places where something asks for a file descriptor, you can use either an actual file
descriptor (i.e., the return value of the open function), or one of the standard I/O
descriptors: 0 is “standard input”, 1 is “standard output”, and 2 is “standard error”.
Writing to either 1 or 2 will result in something being printed to the screen.
2. The standard header files used by xv6 programs are “types.h” (to define some standard
data types) and “user.h” (to declare some common functions). You can look at these
files to see what code they contain and what functions they define.
A brief digression on IDEs and text editors
I do not have strong preferences as to how you create source code. I personally prefer to use a
traditional text editor that can be run at the command line such as pico. Altough vim and emacs
are great as well and there are plenty of alternatives out there. On OS X, some may prefer to use
XCode, others may prefer to use something like TextMate or Sublime Text. In the Linux VM I
have provided, pico works fine. As long as you get a plain text file out of it with valid C syntax,
you can choose whatever you like.
How you compile the code is another matter. The xv6 OS is set up to be built using make, which
uses the rules defined in Makefile to compile the various pieces of xv6, and to allow you to run
the code. The simplest way to build and run it is to use this system. Trying to coerce an IDE such
as XCode into building xv6 is far more trouble than it’s worth.
Part 2: Implementing the ‘tail’ command (50 points)
Write a program that prints the last 10 lines of its input. If a filename is provided on the
command line (i.e., tail FILE) then tail should open it, read and print the last 10 lines, and
then close it. If no filename is provided, tail should read from standard input.
$ tail README
To build xv6 on an x86 ELF machine (like Linux or FreeBSD), run “make”.
On non-x86 or non-ELF machines (like OS X, even on x86), you will
need to install a cross-compiler gcc suite capable of producing x86 ELF
binaries. See https://pdos.csail.mit.edu/6.828/2014/tools.html.
Then run “make TOOLPREFIX=i386-jos-elf-“.
To run xv6, install the QEMU PC simulators. To run in QEMU, run “make qe
mu”.
To create a typeset version of the code, run “make xv6.pdf”. This
requires the “mpage” utility. See https://www.mesa.nl/pub/mpage/.
You should also be able to invoke it without a file, and have it read from standard input. For
example, you can use a pipe to direct the output of another xv6 command into tail:
$ grep the README | tail
Version 6 (v6). xv6 loosely follows the structure and style of v6,
xv6 borrows code from the following sources:
JOS (asm.h, elf.h, mmu.h, bootasm.S, ide.c, console.c, and others)
Plan 9 (entryother.S, mp.h, mp.c, lapic.c)
In addition, we are grateful for the bug reports and patches contributed
by
The code in the files that constitute xv6 is
To run xv6, install the QEMU PC simulators. To run in QEMU, run “make qe
mu”.
To create a typeset version of the code, run “make xv6.pdf”. This
requires the “mpage” utility. See https://www.mesa.nl/pub/mpage/.
The above command searches for all instances of the word the in the file README, and then prints
the last 10 matching lines.
Hints:
1. Many aspects of this are similar to the wc program: both can read from standard input if
no arguments are passed or read from a file if one is given on the command line. Reading
its code will help you if you get stuck.
Part 3: Extending tail (30 points)
The traditional UNIX tail utility can print out a configurable number of lines from the end of a
file. Implement this behavior in your version of tail. The number of lines to be printed should
be specified via a command line argument as tail -NUM FILE, for example tail -2 README to
print the last 2 lines of the file README. The expected output of that command is:
$ tail -2 README
To create a typeset version of the code, run “make xv6.pdf”. This
requires the “mpage” utility. See https://www.mesa.nl/pub/mpage/.
If the number of lines is not given (i.e., if the first argument does not start with -), the number of
lines to be printed should default to 10 as in the previous part.
Hints:
1. You can convert a string to an integer with the atoi function.
2. You may want to use pointer arithmetic (discussed in class in Lecture 2) to get a string
suitable for passing to atoi.
Submitting the Assignment
Submit hello.c and the completed tail.c on NYU Classes.
