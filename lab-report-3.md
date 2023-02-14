# Lab Report 3 - Researching Commands
Here is a report centered around researching commands for CSE 15L! The command I chose to research was `find`.

## Find only directories
The `-type d` command-line option outputs all the directories in a given file. Source: https://www.redhat.com/sysadmin/linux-find-command

# Example 1
```
find ~/skill-demo1-data/written_2/travel_guides -type d
/home/linux/ieng6/cs15lwi23/cs15lwi23aru/skill-demo1-data/written_2/travel_guides
/home/linux/ieng6/cs15lwi23/cs15lwi23aru/skill-demo1-data/written_2/travel_guides/berlitz1
/home/linux/ieng6/cs15lwi23/cs15lwi23aru/skill-demo1-data/written_2/travel_guides/berlitz2
```
This 

# Example 2
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

## Find empty files and directories
The `-empty` command-line options outputs empty folders and files in the directory. Source: https://www.geeksforgeeks.org/find-command-in-linux-with-examples/.

# Example 1
```
find ./travel_guides -empty
./travel_guides/berlitz1/grep-results.txt
```

# Example 2
```
find ./non-fiction -empty
```

## Deleting files
This command-line option finds and deletes a file with confirmation. Source: https://www.geeksforgeeks.org/find-command-in-linux-with-examples/

# Example 1
```
find ./travel_guides/berlitz1 -name WhereToHongKong.txt -exec rm -i {} \;
rm: remove regular file './travel_guides/berlitz1/WhereToHongKong.txt'? n
```

# Example 2
```
find ./travel_guides/berlitz1 -name WhereToDublin.txt -exec rm -i {} \;
rm: remove regular file './travel_guides/berlitz1/WhereToDublin.txt'? y
```

## 

# Example 1
```
find . -type f -name "*.txt"
./HandRHawaii.txt
./HandRHongKong.txt
./HandRIbiza.txt
./HandRIsrael.txt
./HandRIstanbul.txt
./HandRJamaica.txt
./HandRJerusalem.txt
./HandRLakeDistrict.txt
./HandRLasVegas.txt
./HandRLisbon.txt
./HandRLosAngeles.txt
./HandRMadeira.txt
./HandRMadrid.txt
./HandRMallorca.txt
./HistoryDublin.txt
./HistoryEdinburgh.txt
./HistoryEgypt.txt
./HistoryFWI.txt
./HistoryFrance.txt
./HistoryGreek.txt
./HistoryHawaii.txt
./HistoryHongKong.txt
./HistoryIbiza.txt
./HistoryIndia.txt
./HistoryIsrael.txt
./HistoryIstanbul.txt
./HistoryItaly.txt
./HistoryJamaica.txt
./HistoryJapan.txt
./HistoryJerusalem.txt
./HistoryLakeDistrict.txt
./HistoryLasVegas.txt
./HistoryMadeira.txt
./HistoryMadrid.txt
./HistoryMalaysia.txt
./HistoryMallorca.txt
./IntroDublin.txt
./IntroEdinburgh.txt
./IntroEgypt.txt
./IntroFWI.txt
./IntroFrance.txt
./IntroGreek.txt
./IntroHongKong.txt
./IntroIbiza.txt
./IntroIndia.txt
./IntroIsrael.txt
./IntroIstanbul.txt
./IntroItaly.txt
./IntroJamaica.txt
./IntroJapan.txt
./IntroJerusalem.txt
./IntroLakeDistrict.txt
./IntroLasVegas.txt
./IntroLosAngeles.txt
./IntroMadeira.txt
./IntroMadrid.txt
./IntroMalaysia.txt
./IntroMallorca.txt
./JungleMalaysia.txt
./WhatToDublin.txt
./WhatToEdinburgh.txt
./WhatToEgypt.txt
./WhatToFWI.txt
./WhatToFrance.txt
./WhatToGreek.txt
./WhatToHawaii.txt
./WhatToHongKong.txt
./WhatToIbiza.txt
./WhatToIndia.txt
./WhatToIsrael.txt
./WhatToIstanbul.txt
./WhatToItaly.txt
./WhatToJamaica.txt
./WhatToJapan.txt
./WhatToLakeDistrict.txt
./WhatToLasVegas.txt
./WhatToLosAngeles.txt
./WhatToMadeira.txt
./WhatToMalaysia.txt
./WhatToMallorca.txt
./WhereToDublin.txt
./WhereToEdinburgh.txt
./WhereToEgypt.txt
./WhereToFWI.txt
./WhereToFrance.txt
./WhereToGreek.txt
./WhereToHawaii.txt
./find-results.txt
./WhereToIbiza.txt
./WhereToIndia.txt
./WhereToIsrael.txt
./WhereToIstanbul.txt
./WhereToItaly.txt
./WhereToJapan.txt
./WhereToJerusalem.txt
./WhereToLakeDistrict.txt
./WhereToLosAngeles.txt
./WhereToMadeira.txt
./WhereToMadrid.txt
./WhereToMalaysia.txt
./WhereToMallorca.txt
./grep-results.txt
```

# Example 2
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
