###Week1
1. Strings in Python
	all we know for now: string is a sequence of characters, we use " " or ' ' to marke it, can be concatenated, numbers insde quotes are strings, we can convert it by useing int() or float()

2. looking inside strings
	useing index operaters : inside square brackets
	starting from 0
	0 1 2 3 4 5
	b a n a n a
	```
	fruit = "banana"
	print fruit[2]
	```
	this will print out "n"

	slicing strings
	using colon operator [:]
	[0:5] start at 0 up to but not including index 5.


3. built in functions for strings
	`len()`
	`len(fruit)`
	it is 6
	
4. using `in` as logic operator
	```
"n" in "fruit"
false
```

5. can be coompared 
	"banana" < "fruit"

6. String Library
upper(), lower()
```
yes = "Super"
UP = yes.upper()
low = yes.lower()
```
find(()
replace(,)
lstrip()
rstrip()
strip()
startswith()



7. like type() is a python built-in funcion dir() can check for the methods whitch can be used by an object



###Week 3 chapter 7
1. Reading Files
	we have been working with programes, with cpu and ram. But not using the secondary storage, the disk, some files.
	text files.
	by using `open(filename,mode)` function in python. We create a handle of the file in the programe.
2. notion of the "newline" character
	`\n`, it is "one" character.
	We have to know that EVERY line have a `\n` character in its end.
	Ex:
	```
	Xfile = open("myfile.txt")
	count = 0
	for line in Xfile:
		count = count + 1
		print line
	```
	
	```
	Xfile = open("myfile.txt")
	for line in Xfile:
		if line.startswith("From:"):
			print line
	```
	THIS WILL PRINT OUT EXTRA BLANK LINES!!!
	Cuz the `print` statment adds a new line.
	So just `rstrip()` it before the search, to remove the `\n` character in the file.
	`line = line.rstrip()`

Exercise1:
```
# ask for user to enter the file name
fname = raw_input("Enter file name: ")
# open the file
fh = open(fname)
#read the file and strip it to remove extra lines
fread = fh.read().strip()

print fread.upper()
```

Exercise2:
Write a program that prompts for a file name, then opens that file and reads through the file, looking for lines of the form:
X-DSPAM-Confidence:    0.8475
Count these lines and extract the floating point values from each of the lines and compute the average of those values and produce an output as shown below. Do not use the sum() function or a variable named sum in your solution.
You can download the sample data at http://www.pythonlearn.com/code/mbox-short.txt when you are testing below enter mbox-short.txt as the file name.


```
# Use the file name mbox-short.txt as the file name
fname = raw_input("Enter file name: ")
fh = open(fname)
count =0
snum = 0
position = 0

for line in fh:
    if not line.startswith("X-DSPAM-Confidence:") : continue
    count = count +1
    position = line.find(":")
    fnum = float(line[position + 1:].strip())
    snum = snum + fnum

averagenum = snum / float(count)    
    
print "Average spam confidence:", averagenum 
```


###Week4 Chapter 8 lists
1. List is a kind of Collection
	values in `[ ]`
	list elements can be any python object even another list!
	list can also be empty

2. looking inside lists 
	useing index 0, 1, 2, 3......
3. strings are immutable (cant change the content of a string, but we can reassign another string to replace it )
	lists are mutable
	can be concatenate
	can be sliced
4. functions that can be used with strings
	`len()`
	`range()` create a list with the given number, or the number of the given list)
	`dir()` to check what can we do with it.
	`append()` to add elements
	use `in` `not in` to check if an element is in the list
	`sort()` to sort the elements in alphabetic order
	`max()` `min()` `sum()` it is kinda obvious what they do.....(but strings can not be sum up)

5. strings and lists
	use `split()` to break a phrase into word list. 
	use the character inside the `()` to define what the split will based on.
	Ex: 
	```
	phrase = 'jason;huang;munkee'
	words = phrase.split(';')
	```
	the words will be a list with 3 elements: jason huang munkee
	
	
Exercise 8.1

Open the file romeo.txt and read it line by line. For each line, split the line into a list of words using the split() method. The program should build a list of words. For each word on each line check to see if the word is already in the list and if not append it to the list. When the program completes, sort and print the resulting words in alphabetical order.

You can download the sample data at http://www.pythonlearn.com/code/romeo.txt
```
fname = raw_input("Enter file name: ")
fh = open(fname)
lst = list()

for line in fh:
    
    words = line.split()
    
    if len(lst) == 0 :
        lst = words
        
    else:
        for wd in words:
            if wd in lst :
                continue
            else:
                lst.append(wd)

lst.sort()
    
print lst
```

NOTE: append() and sort() dont need to be assign to another variable, just put it after the list we want to append or sort!!!!!



