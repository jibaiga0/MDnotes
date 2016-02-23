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

