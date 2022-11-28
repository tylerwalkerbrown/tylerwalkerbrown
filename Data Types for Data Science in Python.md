# Manipulating lists for fun and profit


```python
#List of food products
frig = ['cheese','bread','milk','eggs']
```


```python
#Extending the list 
frig.extend(['chips','cookies'])
```


```python
#Finding the position of cookies
frig.index('cookies')
```




    5




```python
#Removing the cookies from the list
frig.pop(5)
```




    'cookies'




```python
print(frig)
```

    ['cheese', 'bread', 'milk', 'eggs', 'chips']


# Looping over Lists


```python
#Sorting names of lists
for name in sorted(frig):
    # Print each name
    print(name)
```

    bread
    cheese
    chips
    eggs
    milk



```python
#Empty list
chest = []
```


```python
#List of records example
records = [['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Aarya', '10', '40'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Abby', '27', '23'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Abigail', '31', '19'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Aisha', '18', '32'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Aiza', '19', '31'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Aleena', '17', '33'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Alexandra', '11', '39'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Alice', '24', '26'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Alicia', '12', '38'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Alina', '41', '10'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Alisa', '11', '39'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Alisha', '11', '39'],
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Allison', '15', '35'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Alyssa', '22', '28'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Amanda', '15', '35'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Amber', '17', '33'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Amelia', '27', '23']]
```


```python
#Adding the 3rds element (index 2) to empty list that has been created 
for row in records:
    chest.append(row[2])
```


```python
#Prints out the 3rd element that is found is the records list
print(chest)
```

    ['ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER']


# Meet the Tuples



```python
girls = ['JADA','Emily','Ava','SERENITY','Claire','SOPHIA','Sarah','ASHLEY']
guys = ['JOSIAH','ETHAN','David','Jayden','MASON','RYAN','CHRISTIAN','ISAIAH']
```


```python
#Zip for the guys and girls names 
pairs = zip(girls, guys)
```


```python
idx
```




    6



Enumerate function allows you to track the index of the list. 


```python
for idx, pair in enumerate(pairs):
    # Unpack pair: girl_name, boy_name
    girl_name, boy_name = pair
    # Print the rank and names associated with each rank
    print('Rank {}: {} and {}'.format(idx, girl_name, boy_name))
```

    Rank 0: JADA and JOSIAH
    Rank 1: Emily and ETHAN
    Rank 2: Ava and David
    Rank 3: SERENITY and Jayden
    Rank 4: Claire and MASON
    Rank 5: SOPHIA and RYAN
    Rank 6: Sarah and CHRISTIAN
    Rank 7: ASHLEY and ISAIAH


# Sets

Sets only accept unique values. These can be used to identify elements not in one set or it can be used to find matches amoungst different sets.


```python
names = set(['Derek', 'Dayana', 'Meir','Melvin', 'Daphne', 'Jacqueline', 'David', 'Julian', 'Alston', 'Neil', 'Antonio',
 'Allan', 'Ariel', 'Chloe', 'Bryce', 'Alberto', 'Allen', 'Hannah', 'Molly', 'Fatima','Yahya', 'Vanessa','Carmen','Luciana','Rochel','Kyle'])
```


```python
names_2 = set(['Derek', 'Dayana', 'Meir','Melvin', 'Daphne', 'Jacqueline', 'David', 'Julian', 'Alston', 'Neil', 'Antonio',
 'Allan', 'Ariel',])
```


```python
len(names)
```




    26




```python
type(names_2)
```




    set



Union allows you to see all the names within two sets that are unique.


```python
all_names = names.union(names_2)
len(all_names)
```




    26



difference allows you to see non matching elements between two sets.


```python
overlapping = names.difference(names_2)
len(overlapping)
```




    13




```python
intersect = names.intersection(names_2)
```


```python
len(intersect)
```




    13



# Determining set differences


```python
# Create the empty set: baby_names_2011
baby_names_2011 = set()
```


```python
# Loop over records and add the names from 2011 to the baby_names_2011 set
for row in records:
    # Check if the first column is '2011'
    if row[0] == '2014':
        # Add the fourth column to the set
        baby_names_2011.add(row[3])

# Find the difference between 2011 and 2014: differences
differences = baby_names_2011.difference(names)


```


```python
# Print the differences
len(differences)
```




    17




```python
differences
```




    {'Aarya',
     'Abby',
     'Abigail',
     'Aisha',
     'Aiza',
     'Aleena',
     'Alexandra',
     'Alice',
     'Alicia',
     'Alina',
     'Alisa',
     'Alisha',
     'Allison',
     'Alyssa',
     'Amanda',
     'Amber',
     'Amelia'}



# Dictionaries - the root of Python




```python

```
