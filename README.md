# **Learn-Make**
Learning how to use the make command on simple c programs.

## **Create some C-programs with header file.** 
Here we created basic c-program containing a function that excutes a printf statement.
The command tha was used in the commad line to execute was as follows
```
 gcc -o output main.c func.c -I.
```
Unfortunately, this approach to compilation has two downfalls. First, if you lose the compile command or switch computers you have to retype it from scratch, which is inefficient at best. Second, if you are only making changes to one .c file, recompiling all of them every time is also time-consuming and inefficient. So, it's time to see what we can do with a makefile. That sione reason we use make to automate this process
## **Creating Makefile1**
I created a make file with the following contents
be sure that the GCC is used after a TAB space
the contents are as follows
```
make1: main.c func.c
    gcc -o output main.c func.c -I.
```
you can just use this command in commandline
```
make
```
Or we can use the command. txt format is used as the file is saved in txt format
```
make -f makefile.txt
```
## Creating  Makefile2

Here we will be using constants to store the the values of gcc and I. 
The $ sign is used to deference in the place of usage.
Please check the commands below.
Here also we need to add a " TAB" space before GCC

```
CC = gcc
CFLAGS = -I.
output : main.o func.o
    $(CC) -o output main.o func.o $(CFLAGS)
 ```
Here see below, the command line commands that run when the above script is called

- gcc -I.   -c -o main.o main.c
- gcc -I.   -c -o func.o func.c
- gcc -o output main.o func.o -I.

commands  I have used are 
```
make  -f makefile2.txt
```
Here by putting the object files --main.o and func.o--in the dependency list and in the rule, make knows it must first compile the .c versions individually, and then build the executable output.

## Create Makefile3 

Here we will add an extra constant called DEPS or dependecies.
DEPS = main.h
The new formate explanation are as follows
The -c flag says to generate the object file, the -o $@ says to put the output of the compilation in the file named on the left side of the :, the $< is the first item in the dependencies list, and the CFLAGS macro is defined as above.
The file contents are as foolows
```
CC =gcc
CFLAGS =-I.
DEPS =main.h

%.o : %.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS)
output : main.o func.o
	$(CC) -o output main.o func.o
```
The commands used in Command Prompt are as follows
```
make -f makefile3.txt
```
## Create Makefile4
```
CC =gcc
CFLAGS =-I.
DEPS =main.h
OBJK = main.o func.o

%.o : %.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS)
output : $(OBJK)
	$(CC) -o $@ $< $(CFLAGS)
```
Addition of a new variable OBJK as obj files.

For more information go through this link [https://cs.colby.edu/maxwell/courses/tutorials/maketutor/]


