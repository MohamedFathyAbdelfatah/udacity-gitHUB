### Linux commands and Notes ###
```
cat file_one file_two			#print file or concat two files 
wc filename						#word count
diff filename1 filename2 		#diff between two files  
```
#### Terminal Vs shell ####

terminal - emulator for the real terminal
shell - program to interpret text entered in terminal.  

> command line is case-sensitive 

```
rm -rf   	# remove everything  

Ctrl + c  	#sent interrupt signal and gives prompt back  

Ctrl + d 	#ends_of_file, no input expecting anymore. execute one line programs

i.e : sort [enter] b [enter] a [enter] [Ctrl+d] gives a b  

less filename   	# to see pages in terminal  
					# can search by / or Go to line by typing line number. View only.  
nano filename 	# to edit file in terminal.
```

### The Filesystem Tree ###
Files and directories have names "filenames". Filename can contain any character except the slash, \/. 
When you write a filename that contains spaces or punctuation such as ```!$#()$%``` put the filename in 'quotes' or 
precede each special character with \.
Example:  
Great Filename!   --actual filename  
\'Great Filename!\'  --quoted  
Great\Filename\!  --escaped  


```
mv    #move or rename files
cp    #copy files
mkdir </filepath/name> 				#create a directory  
rmdir <directory> 					#remove empty folder  
rm -r <filename>					#remove folder with contents  
man mv 								#open 'mv' manual
```

### Globbing ###
to find files with pattern


`\*` -> any characters  
```Spanish.*```      matches `Spanish.html`, Spanish.jpg. It doesn't match `spanish.html`  
`{this, that}` 
```ls b{ad, rock}``` matches `bad` and `brock`
[any_character_inthisArray]  
```ls b[ac]d```     matches `bad` and `bcd`  
? - match any one character in ? place. 
```b?d```         matches `bad`, bod, bcd!
```a??```		  matches `app`, `acc`,  does not match `apple`


