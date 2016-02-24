###Week6
1. Function
	use the key word `def` to tell python that we want to create a function.
	
	Built-in functions
	
	it can take arguments inside `()` this!!
	
	return value
	
	result --fruitful function vs void -- non-fruitful

###Week7
1. Indefinite Loop
	Repeat steps
	`while`
	breaking out of a loop useing `break`
	use `continue` to go out of the loop and restart the loop.

2. Definite loops
	```
	for x in [5,3,2,1]:
		print x
	```
	
	The x here is an iteration variable.

3. Loop idioms (the way we construct loops)
	building "smart" loops
	```
	set a variable
	make a loop to do what we want
	return the variable
	```

	finding largest value, counting elements, summing values, finding the average, filtering, using boolean variabl,

4. finding the SMALLEST with loop??
	how to set a number big enough?
	we can use None as original value, and add an `if smallest is None` statement inside the loop.
	*dont overuse `is`.
	

5. The Exercise!!
   Instruction:
	>
	5.2 Write a program that repeatedly prompts a user for integer numbers until the user enters 'done'. Once 'done' is entered, print out the largest and smallest of the numbers. If the user enters anything other than a valid number catch it with a try/except and put out an appropriate message and ignore the number. Enter the numbers from the book for problem 5.1 and Match the desired output as shown.
	>
	
	Answer:
```
# Set variables
largest = None
smallest = None
count = 0
numberlist =[]

# Infinite loop to ask user for numbers
while True:
    num = raw_input("Enter a number: ")
    
    if num == "done" : break # Make a break point
    if len(num) < 1: continue # Check for empty line

    # Check for bad inputs
    try:
        number = int(num)
    except:
        print "Invalid input"
        continue
    # Count iteration and add value to numberlist array
    count = count + 1
    number = numberlist.append(number)

# Find the largest number
for newnumber in numberlist:
    if largest == None:
        largest = newnumber
    elif newnumber > largest:
        largest = newnumber
    else:
        largest = largest

# Find the smallest number
for newnumber in numberlist:
    if smallest == None:
        smallest = newnumber
    elif newnumber < smallest:
        smallest = newnumber
    else:
        smallest = smallest
        
# print out results
print "Maximum is", largest
print "Minimum is", smallest
print numberlist
```
