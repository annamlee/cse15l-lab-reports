# Lab Report 3 - Researching Commands
Here is a report centered around researching commands for CSE 15L! The command I chose to research was `find`.

## 1. Find only directories
The `-type d` command-line option outputs all the directories in a given file. This command is useful for when there are multiple files and directories within the working directory and the user is only interested in the directories because using `ls` in this scenario would just flood the screen with unnecessary file names. 
Source: https://www.redhat.com/sysadmin/linux-find-command

### Example 1
```
find ~/skill-demo1-data/written_2/travel_guides -type d
/home/linux/ieng6/cs15lwi23/cs15lwi23aru/skill-demo1-data/written_2/travel_guides
/home/linux/ieng6/cs15lwi23/cs15lwi23aru/skill-demo1-data/written_2/travel_guides/berlitz1
/home/linux/ieng6/cs15lwi23/cs15lwi23aru/skill-demo1-data/written_2/travel_guides/berlitz2
```
This example shows using the `type d` command on the directory travel_guides, and the output is the two directories within travel_guides, berlitz1 and berlitz2.

### Example 2
```
find ~/skill-demo1-data/written_2/non-fiction -type d  
/home/linux/ieng6/cs15lwi23/cs15lwi23aru/skill-demo1-data/written_2/non-fiction
/home/linux/ieng6/cs15lwi23/cs15lwi23aru/skill-demo1-data/written_2/non-fiction/OUP
/home/linux/ieng6/cs15lwi23/cs15lwi23aru/skill-demo1-data/written_2/non-fiction/OUP/Abernathy
/home/linux/ieng6/cs15lwi23/cs15lwi23aru/skill-demo1-data/written_2/non-fiction/OUP/Berk
/home/linux/ieng6/cs15lwi23/cs15lwi23aru/skill-demo1-data/written_2/non-fiction/OUP/Castro
/home/linux/ieng6/cs15lwi23/cs15lwi23aru/skill-demo1-data/written_2/non-fiction/OUP/Fletcher
/home/linux/ieng6/cs15lwi23/cs15lwi23aru/skill-demo1-data/written_2/non-fiction/OUP/Kauffman
/home/linux/ieng6/cs15lwi23/cs15lwi23aru/skill-demo1-data/written_2/non-fiction/OUP/Rybczynski
```
This example shows using the `type d` command on the directory non-fiction, and the output listed contains the paths to all 7 directories and sub-directories within non-fiction.

## 2. Find empty files and directories
The `-empty` command-line option outputs empty folders and files in the directory. This is useful for cleaning up directories, as you can easily locate empty directories and files to delete. 
Source: https://www.geeksforgeeks.org/find-command-in-linux-with-examples/.

### Example 1
```
find ./travel_guides -empty
./travel_guides/berlitz1/grep-results.txt
```
This example shows that there is only one empty file in the directory travel_guides. Its name (grep-results.txt) and path is outputted.

### Example 2
```
find ./non-fiction -empty

```
This example shows that there are no empty files or directories in the directory non-fiction.

## 3. Deleting files
This command-line option finds and deletes a file with confirmation. This command is useful for when users want to modify their directories by removing certain files. The confirmation assures that files are not mistakenly deleted. 
Source: https://www.geeksforgeeks.org/find-command-in-linux-with-examples/

### Example 1
```
find ./travel_guides/berlitz1 -name WhereToHongKong.txt -exec rm -i {} \;
rm: remove regular file './travel_guides/berlitz1/WhereToHongKong.txt'? n
```
This example shows a user inputting `n` when prompted for confirmation. Because of this input, the WhereToHongKong.txt file is not deleted and still resides in the berlitz1 directory. 

### Example 2
```
find ./travel_guides/berlitz1 -name WhereToDublin.txt -exec rm -i {} \;
rm: remove regular file './travel_guides/berlitz1/WhereToDublin.txt'? y
```
This example shows a user inputting `y` when prompted for confirmation. Because of this input, the WhereToDublin.txt file is removed from the berlitz1 directory and no longer exists.

## 4. Finding files by type
This command-line option finds files by their specific type/extension. This is useful for when the user only wants certain types of files (ex. pdf, txt, png, etc). 
Source: https://linuxhandbook.com/find-command-examples/.

### Example 1
```
find . -type f -name "*.png"

```
This example shows a command to find all `.png` files in the directory berlitz1. The output conveys that there are no png files in berlitz1.

### Example 2
```
find . -type f -name "*.txt"
./ch1.txt
./ch14.txt
./ch15.txt
./ch2.txt
./ch3.txt
./ch6.txt
./ch7.txt
./ch8.txt
./ch9.txt
```
This example shows a command to find all `.txt` files in the directory Abernathy, and the output lists out all such files in this directory.
