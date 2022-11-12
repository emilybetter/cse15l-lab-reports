# Lab Report 3
In this lab report, I will be exploring 3 command line options for the find command through some examples in `./technical`


The size command can be used to find files of a certain size. You can have a lower bound (files greater than X size), an upper bound (files less than X size), or both (greater than X size and less than Y size). You can also use it with file extensions (.txt files greater than size X, etc). This command can be very useful if you need to sort by size, or find the biggest/smallest files in a directory.

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

This command finds all the files in the chosen directory that have a size greater than 5MB. You can also find files that are greater than size x and less than size y.


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

The type command can be used to find items of a certain file type. You can find directories, symbolic links, files, character devices, and more. This can be useful if you are searching a directory for all files of a certain extension, or searching a directory for all subdirectories with a certain permission, and many more options.

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



```
Emilys-MacBook-Pro-4:technical emilybetter$ find ./plos -type f
#some lines printed
./plos/journal.pbio.0020043.txt
./plos/journal.pbio.0020046.txt
./plos/journal.pbio.0020047.txt
./plos/journal.pbio.0020052.txt
#more lines printed 
```
This command  prints all the files in technical/plos .



###### -newer

The newer command is used to find files that are newer than the argument you give it. You can also do the opposite, and find everything that is older using the ! operator. This can be useful if you are trying to find the most recent files, or the oldest files in a directory.

```
Emilys-MacBook-Pro-4:technical emilybetter$  find . -newer biomed/bcr567.txt
#some files printed
./government/Post_Rate_Comm/Gleiman_EMASpeech.txt
./government/Post_Rate_Comm/Mitchell_spyros-first-class.txt
./government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt
./government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt
./government/Post_Rate_Comm/Mitchell_RMVancouver.txt
./government/Post_Rate_Comm/Gleiman_gca2000.txt
./government/Post_Rate_Comm/Cohenetal_Cost_Function.txt
./government/Post_Rate_Comm/Redacted_Study.txt
./government/Post_Rate_Comm/Mitchell_6-17-Mit.txt
#the rest of the files printed
```

This command prints out all files that were modified more recently than the file specified (in this example, biomed/bcr567.txt).


```
Emilys-MacBook-Pro-4:technical emilybetter$ find 911report ! -newer ./911report/chapter-1.txt
911report/chapter-13.4.txt
911report/chapter-13.5.txt
911report/chapter-13.1.txt
911report/chapter-13.2.txt
911report/chapter-13.3.txt
911report/chapter-3.txt
911report/chapter-2.txt
911report/chapter-1.txt
911report/chapter-5.txt
911report/chapter-6.txt
911report/chapter-7.txt
911report/chapter-9.txt
911report/chapter-8.txt
911report/preface.txt
911report/chapter-12.txt
911report/chapter-10.txt
911report/chapter-11.txt
```
-newer can also be used with Boolean expressions. This command prints all files that were not modified more recently than 911report/chapter-1.txt.


```
Emilys-MacBook-Pro-4:technical emilybetter$ find plos -newer plos/pmed.0020278.txt
plos
```
This command prints out all the files newer than plos/pmed.0020278.txt in the directory technical/plos.



