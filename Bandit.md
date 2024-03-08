Bandit Lvl 0 --> 1
cat readme -->  NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

Bandit Lvl 1 --> 2
ls ---> OUTPUT:  -
cat < -       ---->  rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi


# Bandit Level 2 → Level 3

aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG


# Bandit Level 3 → Level 4

The password for the next level is stored in a hidden file in the **inhere** directory.

Step 1: ls
OUTPUT: directory named /inhere
Step 2: cd inhere
Step 3: ls -lah 
OUTPUT: .hidden
Step 4: cat .hidden
OUTPUT: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

# Bandit Level 4 → Level 5

The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

Step 1: cd inhere/
OUTPUT:

Step 2: ls -lah
OUTPUT: 
total 48K
drwxr-xr-x 2 root    root    4.0K Oct  5 06:19 .
drwxr-xr-x 3 root    root    4.0K Oct  5 06:19 ..
-rw-r----- 1 bandit5 bandit4   33 Oct  5 06:19 -file00
-rw-r----- 1 bandit5 bandit4   33 Oct  5 06:19 -file01
-rw-r----- 1 bandit5 bandit4   33 Oct  5 06:19 -file02
-rw-r----- 1 bandit5 bandit4   33 Oct  5 06:19 -file03
-rw-r----- 1 bandit5 bandit4   33 Oct  5 06:19 -file04
-rw-r----- 1 bandit5 bandit4   33 Oct  5 06:19 -file05
-rw-r----- 1 bandit5 bandit4   33 Oct  5 06:19 -file06
-rw-r----- 1 bandit5 bandit4   33 Oct  5 06:19 -file07
-rw-r----- 1 bandit5 bandit4   33 Oct  5 06:19 -file08
-rw-r----- 1 bandit5 bandit4   33 Oct  5 06:19 -file09

Step 3: 

for file in ./-file*; do
    file "$file"
done

OUTPUT:
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data

Step 4: cat ./-file07
OUTPUT: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR


# Bandit Level 5 → Level 6

The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

Step 1:  cd inhere
OUTPUT:

Step 2: ls -lah
OUTPUT: 
total 88K
drwxr-x--- 22 root bandit5 4.0K Oct  5 06:19 .
drwxr-xr-x  3 root root    4.0K Oct  5 06:19 ..
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere00
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere01
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere02
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere03
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere04
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere05
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere06
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere07
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere08
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere09
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere10
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere11
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere12
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere13
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere14
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere15
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere16
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere17
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere18
drwxr-x---  2 root bandit5 4.0K Oct  5 06:19 maybehere19

Step 3: 
for file in ./maybehere*; do
    file "$file"
done

OUTPUT: 

./maybehere00: directory
./maybehere01: directory
./maybehere02: directory
./maybehere03: directory
./maybehere04: directory
./maybehere05: directory
./maybehere06: directory
./maybehere07: directory
./maybehere08: directory
./maybehere09: directory
./maybehere10: directory
./maybehere11: directory
./maybehere12: directory
./maybehere13: directory
./maybehere14: directory
./maybehere15: directory
./maybehere16: directory
./maybehere17: directory
./maybehere18: directory
./maybehere19: directory

Step 4: 
find ./maybehere* -type f -size 1033c ! -executable -exec file {} + | grep "ASCII text"
OUTPUT: ./maybehere07/.file2: ASCII text, with very long lines (1000)

Step 5: cat .file2
OUTPUT: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

# Bandit Level 6 → Level 7

## Level Goal

The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

**Step 1:**
Here is a command that you can use to find the password file:

```bash
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

Explanation of the command:
- `find /`: Starts the search from the root directory `/`.
- `-type f`: Specifies that we are looking for regular files.
- `-user bandit7`: Filters files owned by the user `bandit7`.
- `-group bandit6`: Filters files owned by the group `bandit6`.
- `-size 33c`: Filters files by size to be exactly 33 bytes.
- `2>/dev/null`: Redirects any error messages to `/dev/null` to suppress permission denied errors.

This command will search for files on the server that are owned by user `bandit7`, owned by group `bandit6`, and are exactly 33 bytes in size, helping you find the password file for the next level.

OUTPUT: /var/lib/dpkg/info/bandit7.password

# Bandit Level 7 → Level 8

## Level Goal

The password for the next level is stored in the file **data.txt** next to the word **millionth**
Step 1: grep "millionth" data.txt
OUTPUT: millionth	TESKZC0XvTetK0S9xNwm25STk5iWrBvP



