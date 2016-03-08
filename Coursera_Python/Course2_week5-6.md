### Week 5 Dictionary

1. List vs Dictionary
	list: linear collection of values that stay in order
	dictionary: collection of values who have their own labels.NO ORDERS IN DICTIONARY!!!!   (Key/Value)
	make empty list by `list()`
	make empty dictionary by `dict()`
2. it is powerful!!!
	can do fast database-like operations

3. syntaxe
```
purse = dict()
purse["money"] = 12
purse["candy"] = 5
print purse
```
this will print out:
```
{"money":12, "candy":3}
```
money and candy are keys, 12 and 3 are values

4. To add elements:
List:
```
lst = list()
list.append(XXX)
```
Dictionarys:
```
dic = dict()
dic['xxx'] = 111
```

also we can use `dic = {}` or `dic = {'xxx' : 1, 'yyy' : 2}`

5. EX:
find the most common name:
```
namecounts = dict()
names = ['csev', 'cwen', 'zqian', 'cwen']
for name in names
	if name not in namecounts:
		namecounts[name] = 1
	else:
		namecounts[name] = namecounts[name] + 1
print namecounts
```
or use another useful function `get()` for dictionary to make the code cleaner:
```
counts = dict()
names = ['xxx', 'yyy', 'zzz']
for name in names:
	counts[name] = counts.get(name,0) + 1
print counts
```

6. Ex:Find the most common word in an article

first make the program read the artical.

split strings into words

make a dictionary and use the .get()function to count then prin it out!

7. Use `.list()` or `.keys()` to make a list from the keys of a dictionary.
	`.values()` to make a list from the values inside the dictionary.
	`.items()` to print out in the fashion of tuples(talk about it later~~)

8. In python we can use TWO iteration variables(as a pair)
Ex:
	```
	xxx = {'cc':1, 'dd':3}
	for aaa.bbb in xxx.items()
		print aaa.bbb
	```

9. Exercise:
Write a program to read through the mbox-short.txt and figure out who has the sent the greatest number of mail messages. The program looks for 'From ' lines and takes the second word of those lines as the person who sent the mail. The program creates a Python dictionary that maps the senders mail address to a count of the number of times they appear in the file. After the dictionary is produced, the program reads through the dictionary using a maximum loop to find the most prolific committer.
My solution:
```
# input file name
name = raw_input("Enter file:")
if len(name) < 1 : name = "mbox-short.txt"

# file reading, spliting and remove extra \n   
handle = open(name)
content = handle.read()
scontent = content.split('\n')

# find the line we want and flil in the emails list 
emails = list()
for line in scontent:
    if "From " not in line:
        continue     
    else:
        words = line.split()
        emails.append(words[1])

# get the senders name and fill in the list
senders = list()
for email in emails:
    senders.append(email.split("@")[0])

# count send times and make the dictionary
sendscount = dict()
for sender in senders:
    if sender not in sendscount:
        sendscount[sender] = 1
    else:
        sendscount[sender] = sendscount[sender] + 1

# Find the maxsender and 
maxsender = None
icounts = 0
for sender,counts in sendscount.items():
    if icounts > counts:
        continue
    else:
        icounts = counts
        maxsender = sender

# Find max email
maxemail = None
for email in emails:
    if maxsender in email:
        maxemail = email
    else:
        continue

# print result
print  maxemail, icounts
```


###Week 6 Tuples
1. it is a non-modifiable list
