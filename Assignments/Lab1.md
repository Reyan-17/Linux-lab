# LINUX BASIC COMMANDS
## 1. **NAVIGATION COMMANDS**
### `pwd` - *Print working directory*
it shows the current location in the filesystem.
```bash
pwd
```
It's output:
```
/Users/reyanchauhan
```

### `ls` - *Lists directory content*
It show all files and folder in current directory.
```bash
ls
```
It's output:
```
Applications		l1.code-workspace	Public
armstrong.sh		lab			testf
Desktop			Library			UPES
Documents		linux			VirtualBox VMs
Downloads		Movies			VirtualBoxVMs
github			Music
hol			Pictures
```


### `cd` - *change directory*
It into a particular directory
```bash
cd Folder_name
```
It's output:
##### (cd UPES)
```
UPES %
```


## 2.**FILES AND DIRECTORY MANAGEMENT COMMANDS**
### `mkdir` - *Makes a directory*
It creats a new directory.
```bash
mkdir Newdirectory_name
```
### `touch` - *Create file*
It creates an empty file.
```bash
touch file.txt
```
we can us any extension to create different file like .sh , .iso etc.

### `cp` - *copies files or directories*
It copies files or directories where we want to.
```bash
cp linux.txt C-lang.txt     # Here content of linux.txt is copied in C_lang.
```
* copies folder
```bash
cp -r folderA folderB
```
### `mv` – *move or rename files*

```bash
mv name_1.txt name_2.txt
```
* moves file
```bash
mv file.txt ~/Downloads/     # Moves file to downloads.
```

### `rm` – *Remove Files*
It deletes the file.
```bash
rm linux.txt          # Delete file
```
## 3. FILE VIEWING AND EDITING
### `cat` - *View file content*
Display content of file in terminal.
```bash
cat reyan.txt
```
### `nano` - *edit files in terminal*
A basic linux based text editor.
```bash
nano assignment.txt
```
* `ctrl+o` ~ saves the file.
* `ctrl+x` ~ exit
* Use arrow key to move.

### clear - *clears the terminal*
```bash
clear
```
## 4.SYSTEM COMMANDS
### echo - *Print text*
It prints the desired text.
```bash
echo "my name is reyan"
```
### Output:

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/444fede1-9908-446a-9230-038f1e8680b0" />

---

### `whoami` – *Show Current User*

```bash
whoami
```
### output:
<img width="519" height="132" alt="image" src="https://github.com/user-attachments/assets/c88d4f08-9138-4253-b04e-28899655ee46" />

---

## 5. SEARCHING AND FINDING COMMANDS
### `find` - *Locate files*
```bash
find . -name "*.txt"
```
### Output:
<img width="448" height="133" alt="image" src="https://github.com/user-attachments/assets/06aadc1b-34a4-4565-823f-a8e3df9a8cea" />

---

### `grep` - *Search inside file*
```bash
grep "abc" file.txt   # search abc inside file.txt .
```
### Output:

<img width="482" height="140" alt="image" src="https://github.com/user-attachments/assets/2784b369-b67e-4f3a-9aae-ccd4e1271f3d" />    ``` searched "0" inside reyan.txt```



#  Shell Tutorial – *File Permissions with `chmod` and `chown`*
---


###  1. *Understanding File Permissions in Linux*

Each file/directory in Linux has:

* **Owner** - The user who created the file.
* **Group** - A group of users who may share access.
* **Others** - Everyone else.

### Permission Types

* **r** - Read------(4 in numeric)
* **w** - Write-----(2 in numeric)
* **x** - Execute---(1 in numeric)

### Permission Layout

Example from `ls -l`:

```
-rwxr-xr--
```
Breakdown:

* `-` - Regular file (`d` = directory, `l` = symlink, etc.)
* `rwx` - Owner has read, write, execute
* `r-x` - Group has read, execute
* `r--` - Others have read only
---
### 2. `chmod` – Change File Permissions
```bash
chmod [options] mode filename
```

Modes can be set in **numeric (octal)** or **symbolic** form.

---

### (A) Numeric (Octal) Method

Each permission is represented as a number:

* Read = 4
* Write = 2
* Execute = 1

add them up:

* `7 = rwx`
* `6 = rw-`
* `5 = r-x`
* `4 = r--`
* `0 = ---`

#### Example:

```bash
chmod 777 script.sh
```

Meaning:

* Owner: 7 - `rwx`
* Group: 7 - `r-w-x`
* Others: 7 -`r-w-x`


### (B) Symbolic Method

Use `u` (user/owner), `g` (group), `o` (others), `a` (all).
Operators:

* `+` - Add permission
* `-` - Remove permission
* `=` - Assign exact permission


Modes can be set in *numeric(octal)* or *symbolic* form.



# Extra Questions:
## Q1. what is the differnce between 'chmod' & 'chown' ?
### ANS.
chmod -  This command changes the permission for owner,group and others.
chown -  This command changes the owner and group of a file or directory.

## Q2. How do you check current directory and user ?
### ANS.
We can check the current directory by using 'pwd' command & current user by 'whoami' command.











