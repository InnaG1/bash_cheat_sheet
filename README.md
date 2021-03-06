# bash_cheat_sheet
Unix shell cheat sheet

Permissions:
read = 4, write = 2, execute = 1
777 = <sum of user><sum of group><sum of other>

Example: chmod 777 filename

Create file: 1) Unix text editor 2) Derect output to file 3) touch
Reading file: cat, more, less (Backward scrolling, better memory use, less>more)
 head, tail (-f follow the file)
 
 Creating directory: mkdir name
 Moving directory: mv 
     mv options: 
     -n  no overwirting
     -f forve overwrite
     -i interactive
     -v verbose
 
 ls -ls 
 
 copy: cp source destination
 cp(same options as move)
 -R recursevely
 deleting: rm 
 delete directory: rmdir (only if they are empty) hence we need to use -R
 
 
 Finder Aliases and links:
 Hard links: ln filetilink hardlink (references the file, do not break when moved, do not break if file deteted)
 allowing two different names link to the file
 Symbolik link: ln -s filetolink symlink(reference a file or directory, break if file is moved, break if file is deleted)
 
 Find path expression
 find ~/Documents -name "some.jpg"
 
 
 File ownership:
 whoami
 
 
 Exit:
 q, x, ctrl+q,ctrl+x, ESC
 Force quit = ctrl +c
 
 whereis, which, whatis
 
 System into commands:
 date, 
 uptime, 
 who - list of all users
 uname - unix name
 dimainname
 
 Disc information info:
 df - disc free space
 df -h actual amount
 df -H base 10
 du - disc usage
 du - ah (a - all)
 du - hd 1 ~/.../ (1 depth function)
 
 Viewing processes 
 ps- process status, owned by me and not background
 ps - a all but still not backgound
 ps aux all, include column with user, background
 
 Monitoring Processes:
 top 
 -o order, s - refresh, -U user, n - number
 
 Stopping Processes:
 kill pid - sometimes whould not work
 kill -9 pid 
 
 Text file helpers:
 wc, sort, uniq 
 
 Utility Programs:
 cal/ncal - calendar, 
 bc - calculator
 expr - expression evaluator
 units - unit conversion
 
 Hitory
 located in .bash_history when it closes
 
 !<number>
 !-<number fi the commands back>
 !<beginning of the command>
 !! - previous command , useful when sudo !!
 !$ - ference previous commands argument
 
 
 Input/Output:
 > to_filename (overwrites)
 >> appends
 
 Pipe:
 \| pipes to the command
 ps aux \| less
 
 or you can use direct input <
 
 Suppressing output /dev/null - > special output device, unix just dicurd
 
 
 Profile, login, resource files:
 
 ~/.bash_profile, ~/.bash_login, ~/.profile, ~/.login
 
 .bashrc for each terminal, so to run the same then you first log in:
 ```
 if [ -f ~/.bashrc ]; then
    source ~/.bashrc
 fi
 ```
 
 Commad alliaces:
 `alias ll='ls -la'`
 
 also can redefine a command to add options
 ```
 alias mv='mv -i'
 alias cp='cp -i'
 alias rm='rm -i'
 alias du='du -h'
  ```
  
  export PATH='/ss/bin:$PATH'
 
 history -c - clear
 
 export HISTSIZE=10000 # default 500
 export HISTCONTROL=ignoreboth # ignoredups::ignorespace
 export HISTIGNORE="history:pwd:exit:df:ls:ls -la:ll"
 
 
 Customize command prompt:
 
 ```
 PS1="-->"
 \u - user name
 \s - current shell
 \w current working directoru
 \W basename of current working directory
 \d date
 \D{format} - date in format("%Y-%m-%d")
 \T time
 \H hostname
 \h hostname up to first "."
 \! history number of this command
 \$ when UID is 0 (root), a # otherwise a $
 ```
 
 grep Global regular expression print
 grep in directory use -R `grep -R apple /sss/sss/sss`
 -Rn where it was located 
 -Rh - suppress file name
 -RL - files that do not match
 `grep --color=auto abc abtc.txt`
 
 TR - translating 
 ```
 echo '12345343' | tr '123456' 'EBGDAE'
 EBGDAGDG
 ```
 works like mapping , use case replace special characters
 
 deleting and sqeezing 
 ```
 -d Detele characters in listed set
 -s Squeeze repeats in listed set
 -c Use complementary set
 -dc Delete characters not in set
 -sc Squeeze characcters not in listed set
 ```
 SED stream editor
 
 substitution `sed 's/a/b' `
 s: substitution, a: search string, b: replacement string 
 `echo 'upsrtream' | sed 's/up/down'`
 by default does not search globally to to that globally:
  `echo 'upsrtream' | sed 's/up/down/g'`
  
delimiters are modifieble
  `echo 'upsrtream' | sed 's:up:down:g'`
  
CUT cut out some portion caracters, butes, filds (byte in english = character)
`cut -c 2-10 a.txt` - characters
`cut -f 2, 6 a.txt` - columns

 
 
 

