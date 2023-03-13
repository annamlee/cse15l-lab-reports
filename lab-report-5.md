# Lab Report 5 - Researching Commands (cont.)
Here is a lab report researching several different options for the `grep` command! This is a continuation of lab report 3, where some different options for the `find` command were explored.

## 1. Surrounding Lines
The `-C` command-line option outputs the searched line and n lines before and after the result ([source](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)). This command is useful for debugging because the user can print out the line containing the error and several lines around it to help undrstand what is causing the bug. 

### Example 1
```
grep -C 3 pineapple WhereToHawaii.txt 
 
sparsely-populated island are the setting for the leper colony founded
by Father Damien at Kalaupapa, which can be reached by mule (see
page 77).
Lanai: This pineapple plantation island has become a tiny
hide away with two splendid resorts and the remains of the historic
company town, Lanai City (see page 80).
```
This example shows using the `-C` command on the file `WhereToHawaii.txt` to attempt to output 3 lines before and after the occurance of the word pineapple in this file. The output shows a snippet of the surrounding passage around the word pineapple in this file.

### Example 2
```
grep -C 2 monsters WhereToHawaii.txt

```
This example shows using the `-C` command on the file `WhereToHawaii.txt` to attempt to output 2 lines before and after the occurance of the word monsters in this file. The output conveys that the word monsters is used within `WhereToHawaii.txt`.

## 2. Case Insensitivity
The `-i` command-line option outputs lines that contain the specified string whether or not their cases match ([source](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)). This is a useful command for when a word appears multiple times within a file, but its casing may not be consistent. It can also help speed up processes by allowing the user to only type in lowercase when inputting the command and still getting the matching lines.

### Example 1
```
grep -i "YUGOslavia" IntroItaly.txt

the former Yugoslavia. Off the Tyrrhenian (west) coast are the islands
```
This example shows using the `-i` command to perform a case insensitive search for the word Yugoslavia in the file `IntroItaly.txt`. The output displays the line containing the word "Yugoslavia", despite the command being for "YUGOslavia".

### Example 2
```
grep -i river IntroItaly.txt

Neapolitan taxi driver zig-zagging out of a traffic jam forces the
plates that no longer designate the driver’s origin. It is not so easy
to recognize the home town of a fellow driver.
Como, and Garda, the fertile plain of the Po river separates the Alps
middle of the peninsula to the arid south. Other major rivers are the
```
This example shows using the `i` command to search for lines containing the word "river" in the file `IntroItaly.txt`. The output shows all lines containing the word "river", whether ot not the cases match. This is a good example because "river" could be a general or part of a proper noun.

## 3. Line Numbers
The `-n` command-line option outputs lines that contains the specified string along with their line number ([source](https://www.gnu.org/software/grep/manual/grep.html#Matching-Control)). This command is useful for when a user wants to access that line in the file after finding out where a certain string is located. This could allow for quicker debugging.

### Example 1
```
grep -n gambling IntroLasVegas.txt

57:        gambling, drinking, and adult-oriented temptations. Hotel-casinos have
60:        addition to the gambling, golf courses, and showrooms of the past.
135:        gambling industry, non-gaming business has flourished here as well,
144:        gambling landscape.
166:        gambling and prostitution stop, to a desert retreat for Hollywood
```
This example shows using the `-n` command to search for lines containing the word "gambling" in the file `IntroLasVegas.txt"`. The output conveys the five instances where the word "gambling" occurs in this file, and the line and line number where these occurances are.

### Example 2
```
grep -n metamorphosis IntroLasVegas.txt

168:        eternal metamorphosis. A city living with one eye open to the future
```
This example shows using the `-n` command to search for lines containing the word "metamorphosis" in the file `IntroLasVegas.txt`. The output shows that "Metamorphosis" only appears in this file once, and it is on line 168 of the file.

## 4. File Names
The `-l` command-line option outputs all of the file names of files that contain a specified string ([source](https://www.gnu.org/software/grep/manual/grep.html#Matching-Control)). This is useful if a user wants to find all instances where a certain method or variable is used within their directory.

### Example 1
```
berlitz1 % grep -l "castles" *  

HistoryDublin.txt
HistoryEdinburgh.txt
HistoryItaly.txt
HistoryJapan.txt
HistoryMadeira.txt
WhatToJapan.txt
WhatToMallorca.txt
WhereToFWI.txt
WhereToFrance.txt
WhereToIndia.txt
```
This example shows using the `-l` command to search for all files containing the word "castles" in the directory `berlitz1`. The output conveys that "castles" in 10 files within this directory, and those filenames are printed out.

### Example 2
```
grep -l "fees" *  

WhatToFWI.txt
WhatToJapan.txt
WhatToMadeira.txt
```
This example shows using the `-l` command to search for all files within the `berlitz1` directory that contian the word "fees". The output shows that only theh files `WhatToFWI.txt`, `WhatToJapan.txt`, and `WhatToMadeira.txt` contain the word "fees".
