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
 

