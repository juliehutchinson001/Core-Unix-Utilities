# Core: Unix Utilities

_More powerful than the spiky blue shell_

## Working with this GitHub repository

Follow these steps to set up your own repository:

1. Fork this repository on GitHub to create your own version of this repo on your GitHub account, which should also be named `Core-Unix-Utilities`

1. Visit your fork and clone that repository onto your computer:
`git clone https://github.com/<your-username>/Core-Unix-Utilities.git`

1. Push your commits and link the local repo to your remote GitHub repo:
`git push -u origin master`

1. When you've completed a challenge and want to share it for code review, commit your work and push it to your own remote repo with:
`git push`

1. Add this GitHub repository as a _remote_ to the local one on your computer:
`git remote add core https://github.com/Product-College-Labs/Core-Unix-Utilities.git`

1. When you want to access new course materials, just pull from the origin remote repo:
`git pull core master`

## Challenges, Part 1

Challenges within each section are meant to be solved in order.

### Navigation

1.  Print the path of your working directory
>* pwd
1.  List the files in your working directory
>* ls
1.  List the files with a particular extension, like `.txt`
>* ls *.txt
1.  List the files in a subdirectory, like `project`
>* ls project/
1.  Navigate to a subdirectory, like `project`
>* cd project/
1.  Navigate to the parent directory of your working directory
>* cd ../
1.  Navigate to a nested subdirectory, like `path/to/project` cd
>* path/to/project
1.  Navigate to your home directory
>* cd ~
1.  Navigate back to the previous directory
>* cd ..

### Variables

1.  Print a sentence, like `Hello world`
>* echo Hello world
1.  Print a variable value, like `$USER` or `$PATH`
>* echo $USER
1.  Set a variable `NAME` equal to your first name, then print its value
> NAME=Julie
> echo $name
1.  Set a variable `FULL_NAME` equal to your full name, then print its value
> FULL_NAME=“Julie Hutchinson”
> echo $FULL_NAME
1.  Print all environment variables (names and values)
>* env
1.  Make an alias named `hello` that prints `Hello world`
>* alias hello=“echo ‘Hello world’”
1.  Make an alias named `gocode` that navigates to your code directory
>* alias gocode=“cd ~/”
1.  Print all aliases (names and values)
>* cat .bash_profile

### Getting Help

1.  Print what options a command accepts, like `bash` or `python`
> man bash
> man python
1.  Read the manual for a command, like `echo` or `ls`
> man echo
> man ls
1.  Print the file path to a command, like `bash` or `python`
> type -a bash
> type -a python

### Files

1.  Navigate to the directory `Animals`
> cd Animals/
1.  Print the contents of the file `Cats.txt`
> cat Cats.txt
1.  Print the contents of both files `Cats.txt` and `Dogs.txt`
> cat Cats.txt Dogs.txt
1.  Count the words in the file `Cats.txt`
> wc Cats.txt
1.  Count the words in all files with the extension `.txt`
> wc *.txt
1.  Copy the file `Dogs.txt` to a new file `BabyDogs.txt`
> cp Dogs.txt BabyDogs.txt
1.  Rename the file `BabyDogs.txt` to `Puppies.txt`
> mv BabyDogs.txt Puppies.txt
1.  Make a new directory named `Shelter` inside `Animals`
> mkdir Animals/Shelter/
1.  Move the file `Puppies.txt` into the directory `Shelter`
> mv Puppies.txt Shelter/
1.  Copy the file `Cats.txt` to `Kittens.txt` inside `Shelter`
> cp Cats.txt Shelter/Kittens.txt
1.  List the files within the directory `Shelter`
> ls Shelter/
1.  Count the words in all `.txt` files inside `Shelter`
> wc Shelter/*.txt
1.  Try to remove the directory `Shelter` (this should fail)
> rm -r Shelter/
1.  Remove all `.txt` files inside `Shelter`
> rm Shelter/*.txt
1.  Remove the directory `Shelter` (this should succeed)
> rm -r Shelter/
1.  Now cry because you just deleted those poor tiny animals

### Permissions

1.  Print out your user name
> echo $USER
1.  List the permissions (and metadata) of all `.txt` files
> stat *.txt
1.  Give all users write permission on the file `Cats.txt`
> chmod a+w Cats.txt
1.  List the permissions (and metadata) of the file `Cats.txt`
> stat *.txt
1.  Change the owner of the file `Cats.txt` to another user
> sudo chown julie2 Cats.txt
1.  Now list the permissions (and owner) of the file `Cats.txt`
> stat Cats.txt
1.  Try to change the owner of the file `Cats.txt` back to yourself
> chown $USER Cats.txt
1.  Invoke the super-user to make the previous command succeed
> sudo chown $USER Cats.txt
1.  List the permissions (and owner) of the file `Cats.txt` again
> stat *.txt


## Challenges, Part 2

These challenges utilize more sophisticated Unix utilities.
Challenges within each section are meant to be solved in order.

### Streams

1.  Print a sentence like `Hello world` into a file named `test.txt`
> echo "Hello world" > test.txt
1.  Append another sentence `Hola Mundo` on a new line of `test.txt`
> echo "Hola Mundo" >> test.txt
1.  Print the contents of the file `test.txt`
> cat test.txt
1.  Print the contents of the file `numbers.txt`
> cat numbers.txt
1.  Print the first 10 lines in the file `numbers.txt`
> head -10 numbers.txt
1.  Print the first 5 lines in the file `numbers.txt`
> head -5 numbers.txt
1.  Print the last 10 lines in the file `numbers.txt`
> tail -10 numbers.txt
1.  Print the last 5 lines in the file `numbers.txt`
> tail -5 numbers.txt
1.  Print lines 6 through 10 in the file `numbers.txt`
> sed -n "6,10p" numbers.txt
1.  Sort all lines in the file `numbers.txt`
> sort numbers.txt -o numbers.txt
1.  Print the first 2 characters of each line in `numbers.txt`
> 
1.  Print only characters 9-16 of each line in `numbers.txt`
> 
1.  Sort the first 2 characters of each line in `numbers.txt`
> 
1.  Print only the unique first 2 characters of each line in `numbers.txt`
> 
1.  Replace all `o`s with `0`s in file `test.txt`
> 
1.  Capitalize all letters in the file `test.txt`
> 
1.  Capitalize all letters in the string `Hello world`
> 

### Search

1.  Find the file named `Cats.txt` in the directory `Animals`
> find Animals/Cats.txt
1.  Find all files ending with `.py` in your code directory
> find *.py
1.  Find all files larger than 100 MB in your movies directory
> find -size +101M
1.  Find all lines containing the word `one` in the file `numbers.txt`
> grep -n one numbers.txt
1.  Find all lines containing the letter `e` at least 3 times in the file `numbers.txt`
> egrep -n "e{3,}" numbers.txt
1.  Find the `search` function definition in a source code file
> 
1.  Find the `search` function definition in all source code files
> 
1.  Count the lines and words in all source code files
> 
1.  Find all U.S. zip codes in a file containing addresses
> egrep -n '\d{5}' file_name
1.  Find all U.S. zip codes in a file containing addresses
> 
