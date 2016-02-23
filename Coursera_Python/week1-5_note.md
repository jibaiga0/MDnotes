### Week1 - Week2
Like all introductory programing course! Nothing really important.
	How computer works, why programming, how to install python on your computer...etc.

### Week3
Write the first program........HELLO WORLD!!!

### Week4
1. Expressions

	Constance, variable, reserved words, assignment, doing math, integer and float point.

2. Data type and how to convert them

	integer - int()
	float - float()
	string - str()
	to check the type of an object use 'type()'
	
3. User input

	`xyz = raw_input("What's in your mind?")`

4. Comments

	use `#`

###Week5

1. Conditional Statements
	
	syntaxe:
	```
	if XXXXX:
		do something.
	elif YYYYY:
		do some other thing.
	else:
		do this other thing.
	```
	
	The indentation in python is important, it's part of the syntaxe.
	
2. The `try/except` structure
	
	Ex:
	```
	x = raw_input("What?")
	str1 = int(x)
	print str1
	
	y = raw_input("Again?")
	str2 = int(y)
	print str2
	```

	If the user put in a string for the first question, the program dies, and the second part will not exacute.
	to prevent this from happening we need `try/except` structure:
	
	```
 	x = raw_input("What?")
	try:
		str1 = int(x)
	except:
		str1 = "nan"
	print str1
	
	y = raw_input("Again?")
	try:
		str2 = int(y)
	except:
		str2 = "nan"
	print str2
	```

