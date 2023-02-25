# Lab Report 3 - Researching Commands
Here is a report centered around researching commands for CSE 15L! The command I chose to research was `find`.

## 1. Find only directories
The `-type d` command-line option outputs all the directories in a given file([source](https://www.redhat.com/sysadmin/linux-find-command)). This command is useful for when there are multiple files and directories within the working directory and the user is only interested in the directories because using `ls` in this scenario would just flood the screen with unnecessary file names. 

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
The `-empty` command-line option outputs empty folders and files in the directory ([source](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/)). This is useful for cleaning up directories, as you can easily locate empty directories and files to delete. 

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

## 3. Find files with a case-insensitive search
The `-iname` command-line option outputs all directories and files that match the name, whether or not the cases match ([source](https://linuxhandbook.com/find-command-examples/)). This is useful for when a user does not remember what case their file name is. It also helps to speed up the finding process, as it would be easier to type in all lowercase instead of case specifying.

### Example 1
```
written_2 % find ./travel_guides/berlitz2 -iname bermuda-wheretogo.txt
./travel_guides/berlitz2/Bermuda-WhereToGo.txt
```
This example shows how the file Bermuda-WhereToGo.txt is outputted even though the inputted command was for bermuda-wheretogo.txt in all lowercase. The file with the matching name (excluding case) is returned.

### Example 2
```
find ./non-fiction/OUP/Kauffman -iname "CH4.TXT"
./non-fiction/OUP/Kauffman/ch4.txt
```
This example shows how the file ch4.txt from the directory Kauffman is outputted even though the inputted command was for CH4.TXT in all capitals. The correct file was returned despite the mismatch capitals.

## 4. Find files based on size
The `-size` command-line option allows for searching for files based on their sizes ([source](https://linuxhandbook.com/find-command-examples/)). This is useful for when the user only wants files within a certain size range or if they want to see which files may need more refining or elaboration.

### Example 1
```
find ./travel_guides/berlitz1 -size -1k   
./travel_guides/berlitz1/HandRIstanbul.txt
./travel_guides/berlitz1/HandRIbiza.txt
```
This example shows a command to find all files in the directory berlitz1 that are smaller than 1 KB. The output shows that only HandRIstanbul.txt and HandRIbiza.txt are smaller than 1KB in this directory, meaning there is probably the least information for these locations.

### Example 2
```
find ./travel_guides/berlitz2 -size +80k -size -1G 
./travel_guides/berlitz2/Portugal-WhereToGo.txt
./travel_guides/berlitz2/Canada-WhereToGo.txt
./travel_guides/berlitz2/China-WhereToGo.txt
```
This example shows a command to find all files in the directory berlitz2 that are larger than 80 KB but smaller than 1 GB. The output shows that Portugal-WhereToGo.txt, Canada-WhereToGo.txt, and China-WhereToGo.txt are the only files in berlitz2 that fit this size range.
