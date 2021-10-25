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
## Create Makefile3 
