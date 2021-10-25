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
you can just use this command in commandline
```
make
```
Or we can use the command
```
make -f makefile
```
```
make1: main.c func.c
    gcc -o output main.c func.c -I.
```
