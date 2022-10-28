# Lab Report 3

## Command 1: find
###### -mtime
```
Emilys-MacBook-Pro-4:~ emilybetter$ find ~/desktop -mtime +70 -mtime -75
/Users/emilybetter/desktop/ucsd/Academic History.pdf
/Users/emilybetter/desktop/Screen Shot 2022-08-18 at 01.49.51.png
```
This command finds all the files which are modified more than x days back and less than y days. In this example, x is 70 and y is 75.

###### -size
```
Emilys-MacBook-Pro-4:~ emilybetter$ find ~/desktop/ -size -1M
/Users/emilybetter/desktop//wavelet/.git/FETCH_HEAD
/Users/emilybetter/desktop//.idea
/Users/emilybetter/desktop//.idea/project-template.xml
/Users/emilybetter/desktop//.idea/encodings.xml
/Users/emilybetter/desktop//.idea/description.html
#the rest of the files listed
```
This command finds all the files in the chosen directory that have a size less than x. In this example, x is 1MB. You can also use this command to find greater than a certain size, or use it to find less than x and greater than y.
