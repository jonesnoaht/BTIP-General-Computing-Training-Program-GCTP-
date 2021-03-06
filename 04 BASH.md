# BASH

## Summary

BASH (born-again shell) is the user interface for Unix operating systems. It allows you to run programs etc. It has a scripting language. It allows you to use many built-in utilities. Learning BASH is not so much learning to use BASH itself but rather to develop fluency in using the myriad of utilities that came with your machine.

## General Reference Commands

### Moving Around in BASH

```{BASH}
pwd
ls
cd dir
cd ..
ls dir
cd ~/
mv file ~/Desktop/
mv file new_file_name
exit
```

Here are some nifty commands and shortcuts.

```{bash}
mv 20210222NJ-tSNE.md ~/*UFL*/Noah\ Notebook/Collaborations/NSilver/*Microbiome*/
cd !-1$
```

### Text Editing
```{BASH}
vim # ':q' to quit
emacs # 'ctrl-x ctrl-c' to quit
nano # I don't remember how to quit
```

### Writing Scripts

```{BASH}
chmod +x script.sh
./script.sh
```

### Coding

```{BASH}
python # 'quit()' to quit
```

### Useful and a Bit Niche

```{BASH}
pandoc -f markdown --latex-engine=xelatex PNOCCT02\ Feline\ Trial.md -o PNOCCT02\ Feline\ Trial.pdf
```

### HiPerGator

```{BASH}
ssh gatorlink@hpg2.rc.ufl.edu # log in
srun --ntasks=1 --cpus-per-task=2 --mem=2gb -t 90 --pty bash -i # interactive shell

gui start -c 2 -m 4 -e rstudio
gui show
scancel 63419153

squeue -A esayour
```

### Permissions

r: read files
w: write files
x: execute files

u: user -- permissions per user
g: group -- permissions per group
o: other -- the permissions for everyone else

 u   g   o
rwx r-x r--
111 101 100 = 754

When you add permissions, you are adding permissions to each of those groups:

```{bash}
chmod u+rwx g+rx o+r filename
chmod 754 filename
```

By default, the permissions are 664 (for safety reasons). You can use the chmod command to add the ability to execute files.

Each file has a defined owner and a defined group.

```{bash}
chown noahjones # change the owner to noahjones
chgrp root # change the group
chmod u+w filename.ext # change the rights
man chmod # learn more about these tools
```

Visit [this link](https://help.ubuntu.com/community/FilePermissions) for more details.

## Scripting

### Variables

You can set a variable by specifying it in all caps and then call it by preceding it with a dollar sign. You can call a variable from within a string. When you type the variable, it is equivalent to typing the value to which it was assigned.

```{bash}
VAR="hello world"
echo $NAME # hello world
echo "$NAME"
```

### Conditionals

Boolean expressions (e.g., "a equals b") can be described as follows.

```{bash}
[[ a == b ]]
```

This will return a 1 or a 0. These can be used in if-then-else statements.

```{bash}
if [[ a == b ]]; then
  echo "a equals b"
elif [[ a != b ]]; then
  echo "a does not equal b"
fi
```

The if statement is closed with a ```fi```. You can include as many elif statements as you would like, and you can leave them out completely if you desire.

### Functions

Declaring a function is easy.

```{bash}
my_function(arg1) {
  echo arg1
}
```

Calling a function is equally easy.

```{bash}
my_function "duck"
```

### Brace expansion

These are incredibly useful because you can perform batch operations.

```{A,B}``` is the same as ```A B```, and ```{A,B}.md``` is the same as ```A.md B.md```. You can also specify ranges. ```{1..5}``` is ```1 2 3 4 5```.

### Loops

The loop construction is simple and merely uses a list.

```{bash}
for i in ./*; do
  echo $i
done
```

### Manipulating Strings

```{bash}
name="John"
echo ${name}
echo ${name/J/j}    #=> "john" (substitution)
echo ${name:0:2}    #=> "Jo" (slicing)
echo ${name::2}     #=> "Jo" (slicing)
echo ${name::-1}    #=> "Joh" (slicing)
echo ${name:(-1)}   #=> "n" (slicing from right)
echo ${name:(-2):1} #=> "h" (slicing from right)
echo ${food:-Cake}  #=> $food or "Cake"
```

### Disucssion

For more, please visit [this devhints page](https://devhints.io/bash). There are also some great exmaples in the comments, such as . . .

```for F in *.txt; do echo "$F" >> files.list; done```

```$((RANDOM % 200))```

Also check out [Linux Cheat Sheet](https://sites.google.com/site/mrxpalmeiras/linux/linux-cheat-sheet) (you will likely need to shrink the page the view the entire contents) and [BASH hackers](https://wiki.bash-hackers.org).
