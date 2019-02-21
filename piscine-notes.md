# Piscine

![enter image description here](https://www.raviday.com/blog/wp-content/uploads/2016/04/piscine-hors-sol-intex.jpg)

# Day 00
## basics , filesystem, cat, touch, vim, Kerberos, Git


* **standard output** - means it's displayed on your screen
* **man** - manual
* **pwd** - current working directory
* **mkdir** - make directory
* **touch** - create file
* **cat** - preview file content
* **rm** - remove
* **rm -rf** - remove directory
* **cp** - copy
* **mv** - move (change name if you move within 1 dir.)
* **ls** - list of directory content
* **ls - la** - lists all (info in folder)
* **ls - l** - displays details of a directory (lists file type,
	permissions, owner, size, date of creation & file name)
* **/** - root directory/file system (the way the files are organized on the hard-drive
* **.**  - current directory
* **. .**  - directory before current one
* **Create link** - ln -s [source file] [my file] `ln -s linkx file x`
* **softlink** -  ln -s (link A link B)
* **tar** -  tape archive `Tar -cf [filename].tar [filename]`
* **Change date and time of a file** -
* `touch -t 201806012342 file x`
* **Change date and time of a link** -
 `touch -h -t 201806012342 file x`
* **chmod** - change access permissions

<font color="red">drwx<font color="green">r-xr-<font color="blue">x

d - directory
 r -  read
w - write
x - execute
<font color="red">red letters <font color="2E2D2D"> > your own permission
<font color="green">red letters <font color="2E2D2D">> group permissions
<font color="blue">red letters <font color="2E2D2D"> > everybody else, rest of the world
 
To change the mod, type in "chmod <font color="red">x<font color="green">x<font color="blue">x <font color="2E2D2D">[filename]
To regain permission: chmod <font color="red">7<font color="green">0<font color="blue">0 <font color="2E2D2D"> [filename]
To let others read only: chmod <font color="red">6<font color="green">4<font color="blue">4 <font color="2E2D2D">[filename]
To let others read and execute: chmod <font color="red">5<font color="green">5<font color="blue">5 <font color="2E2D2D">[filename]

    
0: no permission
1: execute only
2: write only
3: execute and write (1+2)
4: read only
5: read and execute (4+1)
6: read and write (4+2)
7: all permissions

**vim**
Two modes: command & insert
**i:** insertion mode
**esc:** leave insertion mode
**:w** - save
**q** - quit
**$** - brings you to the end of the line
**^** - beginning of line
**:vs** - split screen vertically
**:sp** - split screen horizontally
**^W** - move between buffers
**:e main** - re-edit "main"

**Kerberos** - Standaard authenticatieprotocol voor het veilig aanmelden van gebruikers op een netwerk (bewijzen identiteit)
**Keytab** - A file containing pairs of Kerberos principles and encrypted keys
**Ktutil** - invokes a command interface from which an admin can read, write & edit entries in keytab or Kerberos file
**Klist** - lists your ticket cache
**Kdestroy** - clears your ticket cache (destroys the active Kerberos tickets by overwriting and deleting the credentials cache that contains them)
**Kinit** - obtains and caches a Kerberos ticket

---

**Patch**
**1** Apply a diff file to an original. Diff file adds the new stuff to the original file by patching it. File 1 (original), file 2 (update)
**2** diff -u [original file] (compare them with the new file)
[file 2] > [name].patch (to create a patch file)
**3** cat [name].patch to see what the difference is between the files.
**4** delete the file
**5a**   patch < (read IN) [name].patch
-> original file will be patched with the update
**5b.** after creating a patch: patch [original file] -i [name.patch] -o [updated file] (will patch the original file.

**diff** used to compare two files line by line
**diff a b > sw.diff** shows what's the difference between file a and b. So if you need to know what's in b, you need to diff a sw.diff > b to create b file.

The output indicates how the lines in each file are different, and the steps invoved to change file1 to file2. The ‘patch’ command can be used to make the suggested changes. The output is formatted as blocks of

**Change commands**

> _< lines from file1_  
> _—_  
> _> lines from file2_

---
## Git
**git clone git repository file x** 
**git commit -m** (-m is to add a comment)
**git status** - see what has been uploaded/what didn't
**git push (1st time add origin master)** - uploads local repository content to a remote repository
**git-init** - Create an empty Git repository or reinitialize an existing one
**bash file x** - create a list of last commits.
**git show** [url in log of the file you want to see]
**git rm cached file x** - will delete the file without deleting it locally
**git rm file x** - will delete it and delete it locally (make sure to backup before you try these!)
**git log --pretty=format:"%H"** - shows the commit url's. You can add -5 behind is to show the last 5.
**Gitignore** (specifies intentionally untracked files to ignore)

[https://www.atlassian.com/git/tutorials/saving-changes/gitignore](https://www.atlassian.com/git/tutorials/saving-changes/gitignore)

**Master** - The default development branch (Whenever you create a Git a branch named "master" is created, and becomes the active branch.)
Index: A collection of files with stat information, whose contents are stored as objects. The index is a stored version of your working tre

Git stores the history of a collection of files as a compressed collection of interrelated snapshots of the project’s contents. Each such version is called a commit

Those snapshots aren’t necessarily all arranged in a single line from oldest to newest; instead, work may simultaneously proceed along parallel lines of development, called **branches** which may merge and diverge.

A single Git repository can track development on multiple branches. It does this by keeping a list of  **heads** which reference the latest commit on each branch; the **git-branch**  command shows you the list of branch heads

A **branch** is an active line of development. The most recent  commit on a branch is referred to as the tip of that branch. The tip of the branch is referenced by a branch  **head** which moves forward as additional development is done on the branch. A single Git  **repository** can track an arbitrary number of branches, but your  **working tree** is associated with just one of them (the "current" or "checked out" branch), and **HEAD**   points to that branch.

----

# Day 01
## / file content processing (display, filter, modify, redirection)

**commands to print files**
**echo "" >** - outputs the strings it is being passed as arguments; standard output (echoes back the input)
**echo"" >>** - will add on a new line
**cat** - takes a file as an argument & displays the content
**more**  - view (not modify) the contents of a text file
**less** - allows you to view the contents of a file & navigate through it using up/down keys (faster than more)
**head** - display first lines of a file
**tail** - display the end of a file `tail -n 3 ` (displays last three lines)
**grep** - searches for patterns in each file (allows you to specify which lines you want to display)
`grep -i xv file x` displays case insensitive matching with 'x'
`grep -v x file x ` - displays lines that don't contain word x

**commands**
**cat** "no file" - re-displays on standard output
**delimiter** - one or more characters used to specify the beginning or the end of a character string (e.x. **,  ;  {} | /**)
**>** - redirects standard output to a file
**>>** - will add content to a file on a new line
**<** - redirects standard output from a file
**|** - uses the output of command x as input for command y
`cat file x | grep name x`
**wc** - calculates the number of lines, characters and words within a file `file x | grep namex | wc - l` -> number of lines
**file** - gives info on a file passed as a parameter (the variable as found in the function definition)
**ifconfig** - gives information on your network (IP, address etc.)
**bc** - calculator (sin, cosine, exponents, convert number bases) `echo " 1 + 2" | bc` -> 3
**find** - lists all files within a directory, passed as an argument, can be used to filter files
**env** */environment* - displays a list of variables in Shell that'll be automatically to all your binaries & scripts
**PATH** -  colon-delimited list of directories that your shell searches through when you enter a command
`"date", "size", "colour" `

----
**chain commands**
-  **AND (&&)** *(will execute only if the preceding command executes successfully)*
- **OR(||)** *(will execute only if the preceding command fails)*
-  **Semi-Colon (;)** *(will execute regardless of the exit status of the command that precedes it)*
-   **Pipe (|)** *(output of the previous command acts as the input to the next command in the chain)*
-   **Ampersand (&)**  *(sends the current command to the background)*
-   **Redirection (>, <, >>)**  *(operator can be used to redirect the output of a command or a group of commands to a stream or file)*

**sort/cut**
**sort** - sort out lines of text files (allows you to sort what you're giving as arguments, based on ASCII characters sorting)
**ASCII** - character encoding standard for electronic communication
**cut** - allows you to cut each line depending on the delimiter 
**cat -e** - allows non-printing characters to be displayed & $ for end of lines
**sed** - stream editor, allows you to make manipulte data through substituting (displays differently without editing the original file `sed'"s/namex/nameX/"`
**"s** - substitute
**regex** - regular expression // one out of two modifications // sequence of characters the define a search
on patterns
**tr** - takes two arguments, char x & the one that's replacing it `tr "é" "e"`

# Day 02
## first step in C

**vim file.c** - lets the program know that it's a source file
**:Stdhead** - header
**./** - executing in current directory
**#stdio.h** - the header for printf(), scanf() etc.
**unistd.h** - header file for read, write, close etc.
(used so that the compiler has the declaration, knows what arguments are required & what the output parameter is) 

---

`#include <unistd.h>`

`int main()` 
`{`
	`write(1, "@\n", 2)`
	`return(0); `
`}`


**-> displays @**

---

`#include <unistd.h>`

`int ft_putchar(char c)` 
`{`
	`write(1, "&c", 1)`
	`return(0); `
`}`

`int main()` 
`{`
	`ft_putchar('@');`
	`ft_putchar ('\n');`
	`return(0); `
`}`

-> **displays the address of char c**
(allows you to transform it into a string (char *)

---

**commands**
**norminette file.c** - checks if your code passes the "norms" (spaces, brackets, lining etc.)
**main()** - function has no arguments
**int main()** - function returns int value
**void main()** - function returns nothing
**write(1, &x, 1)** - display(standard output, character x, 1 char)
**string** - any finite sequence of characters (can contain spaces & numbers)
**parameter** - a special kind of variable that is used to pass information between functions or procedures The actual information passed is called an **argument**.
**Argument** - a value that is passed between programs, subroutines or functions; independent item, or variables, that contain data or codes
**&** give a character
**'x'** - char
**x** - int
**"x"** - string
**%c** - refers to a character
**%d** - refers to an integer
**%p** - refers to a pointer
**%s** - refers to a string
data types - **int**, **float**, **double**, **char**, and **_Bool**
**int** - used to contain integral values only
**argv** - argument vector/
**argc** - argument count/the number of strings pointed to by arg (1 + number of arguments)

**expressions**
**If** - if the expression is true then the statement or block of statements gets executed otherwise these statements are skipped. (check for the condition that will occur most often before you check for special occurances)
**While** - similar to an if statement; if the test condition is true: the statements get executed. The difference is that after the statement has been executed, the condition is checked again. Cycle repeats until the test condition evaluates to false.

**Else** 
`if(conditionx){`
`true for x` `...`
`}else{`
`false for x`
`...`
`}`
***check condition x
if valid: execute the 'true for x' part
else, execute the 'false for x'** 


**Else if**
`if(condition x){`
`true part for x`
`...`
`}else if (condition y){`
`true for y`
`...`
`}else{`
`if neither of x or y is true`
`...`
 
***check condition x
if valid, execute the 'true for x' part & skip the other sections of code
or
if condition x is invalid then check for condition y
if valid, execute the 'true for y' part & skip the other sections of code
if both are invalid, then execute the 'if neither x or y is true'**



#  Day 03
## Pointers
**Function** - a closed entity that has
1. an input date: the parameters
2. a piece of output data: the return value

**Arrays**:
`type	name[numeric_value];` 
*example*
`int	tab[42];`

**Structures**:
`struct struct_name`
`{ `
`type name;`
`type name;`
`}`
*example*
`struct s_fortytwo`
`{`
`int a;`
`char b[21];`
`};`

**declaration**:
`struct struct_name name;`
*example*
`struct s_fortytwo a;`


**Pointer** - variable that stores the memory address of another variable of a given type, instead of storing data
(allows you to possess another variable address & modify it remotely)

*how to declare a pointer*:
- **type** - first declare the type of what you point to `[int *p;]`
- **address** - write `[p = &a]` which will set the address of a in p
- **value** give value to the pointer `[*p = 1]`

*advantages:*
/ allows management of structures which are allocated memory dynamically
/ allows passing of arrays and strings to functions more efficiently
/ makes it possible to pass address of structure instead of entire structure to the functions. 
/ makes it possible to return more than one value from the function

**Swap memory** - the on-disk component of the virtual memory system. Pre-configured as a swap file when Linux is first installed, but can also be added later. Disk access is very slow compared to memory access.
**MMU** Allows you to reserve memory somewhere, physically on the computer
**High memory/stack** -  Used every time you call a function/do anything, starts at the top of the memory (the more elements you add, the further down the stack you go)
**Low memory/heap** - place where you can allocate memory
**&** - retrieves the addresss of something
**Array** - data structure that holds multiple elements of the same data type (values or variables). The first element in the array is numbered 0, so that last element is 1 less than the size of the array. 
*Before using an array its type and dimension must be declared
**%p** - refers to a pointer
***x** - x = variable name
**&** - refers


# Day 04
## Recursion

**What we've been doing so far is called iterative programming. 
**iterative programming**: uses instruction loops that repeat themselves, that evaluate to nothing, and uses side effects in order to return values. (Meaning they use variables.) Results are stored in variables.

*example* `ft_strlen()` takes a variable, initialises it to 0, then does a loop that at each iteration will increase the variable by 1.

**Pile**/Stack: a program reserved region of memory which fills up as we call functions 

**Recursive function** - a function that calls itself and pushes itself, on the stack, on top of itself (like Matryoshka)
*if the function does't get to a point in the execution where there's a stopping condition it'll keep calling itself!!

1. Call a function
2. Define its parameters  
3. Make it return values 
4.  Define it's evaluated

Possible outcomes:

1. The function will continuously call itself: every time it finishes its action, it'll re-push another instance of the function onto the stack. If not stopped the sack will keep growing until it's full/crashes.
2. The function will get to a point in the execution where there's a stopping condition and return instead of recall. *(Similar to a stopping condition in a loop but with different implementation.)* When the stopping condition is met, it stops piling up functions onto the stack and return to the initial state.

Remember:
1. A recursive function is a function that calls on itself
2. It has a stopping condition
3. If you use counters, make sure to relay them between functions instances for both parameters ; return values 


**Iterative function** 
`5! = 5 * 4 * 3 * 2 * 1`
`5! = 5 * 4!`

`n! = n * (n - 1) * (n - 2) * ... * 3 * 2 * 1`
`n1 = n * (n-1)!`
**Note: 1! = 1 is a stopping condition**

`Fact(N) = N * fact(N - 1)`
`Fact(1) = 1`
**Note: fact(N) = 1 is a stopping condition**


**power functions** - 3 * 3 * 3 * 3 can also be noted as 3^4

# Day 05
## Character manipulation

**character string** - array of chars

**creating a char array**:
`int	main(void)`
`{`
`char strl[];`
`strl[] = "Hello";`
`}`

`ft_putstr();`
`ft_putstr(strl);`
`ft_putchar('\n');`
`void ft_putchar(char c)`
`{`
`write(1, c, 1);`
`return (0);`
}

**creating a string**:
`void ft_putstr(char *str)`
`{`
`while (str[index] != '\0'`
`{ int index;`
`index = 0`
`ft_putchar(str[index]);`
`index++;`
`}`

**Remember! All char strings stop at 10**

**Char manipulation** - change a value within the string
**ft_replace** - allows you to replace the first char
`void ft_replace_first(char *str)`
`{`
`str[0] = "y"`
`}`

**signed int** - holds +, - or 0 numbers
**unsigned int** - holds + and 0 numbers
**src** - source
**dest** - destination
**index** - used to specify the elements of an array of numbers 
**strncpy** at most: len characters from src into dst
*if src < len: fill the rest of dest with \0*
*if strlcpy*:
`strstr:`
`char str1[] = "TutorialPoint";`
`char str2[] = "Point";`

*Function searches for the first occurrence of the char, so the first
str1[i] = str2[i]
keeps comparing until either
str1[i] != str2[i] or str2 [i] = '\0'*
after which it will print the remaining chars in stroll until \0 is reached.*

***str** - looks into the array at str
**str++** - moves up in the string without looking in it
char str[] = "hello"
**ft_strcmp** -lexicographically copare the null terminated strings s1 and s2
*if str1 = str 2 -> 0
if str1 > str2 -> +value
if str1 < str 2 -> -value*

**Don't forget to norminette!! -R CheckForbiddenSourceHeader**


# Day 06
## Libraries

-**library** - set of built-in functions, gathering of constants & header files, gathered into one place. *(Making your own can help you gather useful functions and reduce time rewriting them)*
*always starts with lib
`(libname functiona functionb functionc)`
**Retrieving program arguments** - *Until now, mains had no arguments, mains can take arguments too, so instead of recompiling after changing something constantly; you only compile once. This makes the program more efficient. 
To make files, you first need to compile the functions you want to include in it. You always need a main.
To add things to a library without needing a main: `gcc - c ft_putstr.c`
This creates a file that is named ft_putstr.o (o = object)
Only a computer can display this, and to do anything with it, you need a main.
(Libraries use .o files. Main.c is a wall, o-files are bricks that can be used in multiple walls, as once you have the brick, you don't need to make it again, and you can use it any time, anywhere.)*
**creating a library with only ft_putchar ; ft_putstr**
1. create .o files
2. ar rc libraryname *files that contain the functions you want to add*
`ar rc libstr.a ft_putchar.o ft_putstr.o` *(will create libstr.a with all functions included)*
*How to use libs*: `gcc main.c -L -lstr` *(can now be moved)*
**ranlib** - takes library as parameter and makes an index in your library. This will help gcc know where to go
**-o** - adds a function to your library
**ar** -  utility that maintains groups of files as a single archive file
**ar r** - inserts the files member into archive
**ar c** - creates the archive
**gcc main.c -L. -lstr** - tells that the library is in the current directory (it's now possible to move your library anywhere)
**ranlib** - takes your library as a parameter and creates an index in your library which will allow GCC to know where to go
**int main(int arg, char ** argv)** - enable you to retrieve the parameters that can be passed to your binary
**arg c** - represents the number of parameters that you can pass to your program ; always equal to 1
Can be used to find out how many arguments you have and/or to display one by one, the parameters passed to your program (this can indicate whether the program needs an argument
**arg v** - a char a.k.a. a string array ; always filled
in arg v's first box you have the binary's name
**" "** - used to regroup multiple arguments within one same string 
ls can use -l to display details of a directory, launching a binary; adding arguments would not change anything.

***Now that you're allowing other users to interact with you program, you'll never be sure of what the'll try and pass as arguments.. Be careful and bear in mind that you'll never be able to guess EVERYTHING the user might pass to your program. So test your arguments thoroughly & check everything you do!!**


# Day 07
## Compilation
**gcc** - compiler
**gcc -o** allows us to define the type of gcc output file aka change the name `gcc -o filename filenamex`
**gcc -c** creates object files (**.o**) that can be used in your library
**gcc -W -Werror -Wextra -Wall**
*gcc main function function -o filename





