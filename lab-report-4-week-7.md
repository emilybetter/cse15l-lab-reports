# Lab Report 4
### Part 1
In DocSearchServer.java, change the name of the start parameter of getFiles, and all of its uses, to instead be called base.

The shortest sequence of vim commands that we came up with for this task was:  
`:` `1` `2` `,` `2` `3` `s` `/` `s` `t` `a` `r` `t` `/` `b` `a` `s` `e` `/` `g` `<Enter>`
This is a total of 21 keys pressed.<br />
`:s/searchString/replaceString/g` replaces a string across the whole file (g means global).  <br />  
`[a,b]` replaces between lines a and b<br />
So, ':12,23s/start/base/g` replaces the string start with base from line 12 to line 23.  <br />

Vim into DocSearch.java:
![Image](vim_docsearch.png)
Typing command:
![Image](type_command.png)
After replacing:
![Image](after_enter.png)

### Part 2

