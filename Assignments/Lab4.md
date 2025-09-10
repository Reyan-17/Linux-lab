#  BACKUP

## 1). Backup.sh Script
Create a new file named backup.sh inside your project folder:

<img width="654" height="380" alt="image" src="https://github.com/user-attachments/assets/cfd090e0-d418-435c-a9d6-1fa2a91d894b" />

## 2. * Make Script Executable
Run the following command once:

chmod 777 backup.sh

## 3. * Testing the script
### 1. Create some samples .txt files:

<img width="560" height="171" alt="image" src="https://github.com/user-attachments/assets/9a5a6cfb-eaca-44c2-9efb-ebe08480a209" />

### 2. Run the script:
./backup.sh

### 3. Check the backup/folder:

ls backup/


#  LAB4– * File & Backup Automation

## Objective
Automate the backup of ⁠ .txt ⁠ files into a ⁠ backup/ ⁠ folder with timestamps in filenames.

---

##  Script Explanation

1.⁠ ⁠⁠ mkdir -p backup ⁠  
   Creates a folder n".

2. Using at (One-time Scheduling)
Run a script once at a specific time:

echo "/home/user/backup.sh" "
amed ⁠ backup ⁠ if it does not exist.

3.⁠ ⁠⁠ timestamp=$(date +"%Y%m%d_%H%M%S") ⁠  
   Generates a timestamp (format: YYYYMMDD_HHMMSS).

4.⁠ ⁠⁠ for file in *.txt; do ... done ⁠  
   Loops through all ⁠ .txt ⁠ files in the current directory.

5.⁠ ⁠⁠ basename "$file" .txt ⁠  
   Extracts the file name without extension.

6.⁠ ⁠⁠ cp "$file" "backup/${filename}_$timestamp.txt" ⁠  
   Copies the file into ⁠ backup/ ⁠ with the timestamp appended.

---

##  Example Run

### Input
Created two ⁠ .txt ⁠ files:

file1.txt
world.txt


### Command
./backup.sh


### Output
Files copied into ⁠ backup/ ⁠ with timestamps:


<img width="1011" height="100" alt="image" src="https://github.com/user-attachments/assets/3b386641-8685-4f71-a712-d9b58ede15c0" />


###  Q1-What is the difference between cp,mv,and rsync?

ANS  =cp-Copies files or directories
     mv-Moves or renames files or directories
     rsync-Synchronizes files/directories efficiently


###  Q2-How can you schedule scripts to run automatically?

 ANS=You can schedule scripts to run automatically using task schedulers built into your operating system.
