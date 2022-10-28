# Lab Report 3
In this lab report, I will be exploring 3 command line options for the find command through some examples in `./technical`

###### -mtime
```
Emilys-MacBook-Pro-4:technical emilybetter$ find . -mtime +5
#some files
./plos/journal.pbio.0020043.txt
./plos/pmed.0020039.txt
./plos/pmed.0010071.txt
./plos/journal.pbio.0030127.txt
./plos/pmed.0010058.txt
./plos/pmed.0010070.txt
./plos/pmed.0010064.txt
./plos/pmed.0020158.txt
./plos/journal.pbio.0020042.txt
./plos/journal.pbio.0020297.txt
./plos/pmed.0020206.txt
./plos/pmed.0020212.txt
./plos/pmed.0020216.txt
#more files
```
This command finds all the files which are modified more than x days back. In this example, x is 5 days. You can also find files which are modified greater than y days ago, or files which are modified more than x days back and less than y days.

###### -size
```
Emilys-MacBook-Pro-4:technical emilybetter$ find . -size -1M
#some files listed
./plos/journal.pbio.0020043.txt
./plos/pmed.0020039.txt
./plos/pmed.0010071.txt
./plos/journal.pbio.0030127.txt
./plos/pmed.0010058.txt
./plos/pmed.0010070.txt
./plos/pmed.0010064.txt
./plos/pmed.0020158.txt
./plos/journal.pbio.0020042.txt
./plos/journal.pbio.0020297.txt
./plos/pmed.0020206.txt
./plos/pmed.0020212.txt
./plos/pmed.0020216.txt
#the rest of the files listed
```
This command finds all the files in the chosen directory that have a size less than 1 MB.

```
Emilys-MacBook-Pro-4:technical emilybetter$ find . -size +5M 
#some files listed...
.//plos/journal.pbio.0020043.txt
.//plos/pmed.0020039.txt
.//plos/pmed.0010071.txt
.//plos/journal.pbio.0030127.txt
.//plos/pmed.0010058.txt
.//plos/pmed.0010070.txt
.//plos/pmed.0010064.txt
.//plos/pmed.0020158.txt
.//plos/journal.pbio.0020042.txt
.//plos/journal.pbio.0020297.txt
.//plos/pmed.0020206.txt
.//plos/pmed.0020212.txt
.//plos/pmed.0020216.txt
#the rest of the files listed

```

This command finds all the files in the chosen directory that have a size greater than 1MB. You can also find files that are greater than size x and less than size y.


```
Emilys-MacBook-Pro-4:technical emilybetter$ find . -size +1k -and -name "*.txt"
./plos/journal.pbio.0030050.txt
./plos/pmed.0020239.txt
./plos/journal.pbio.0020241.txt
./plos/pmed.0020005.txt
./plos/journal.pbio.0020043.txt
./plos/pmed.0020039.txt
./plos/pmed.0010071.txt
./plos/journal.pbio.0030127.txt
./plos/pmed.0010058.txt
./plos/pmed.0010070.txt
./plos/pmed.0010064.txt
./plos/pmed.0020158.txt
./plos/journal.pbio.0020042.txt
./plos/journal.pbio.0020297.txt
```

This command finds files whose size is greater than 1 kilobyte and also have an extension of .txt.











###### -type
```
Emilys-MacBook-Pro-4:technical emilybetter$ find . -type d
.
./government
./government/About_LSC
./government/Env_Prot_Agen
./government/Alcohol_Problems
./government/Gen_Account_Office
./government/Post_Rate_Comm
./government/Media
./plos
./biomed
./911report
```
This command finds all the directories in technical. 

```
Emilys-MacBook-Pro-4:technical emilybetter$ find ./government -type d
./government
./government/About_LSC
./government/Env_Prot_Agen
./government/Alcohol_Problems
./government/Gen_Account_Office
./government/Post_Rate_Comm
./government/Media
```
This commands finds all the directories in the directory government.



