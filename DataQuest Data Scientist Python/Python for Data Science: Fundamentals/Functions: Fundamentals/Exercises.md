Begin to work on a frequency table for the ratings list

```python
ratings = ['4+', '4+', '4+', '9+', '12+', '12+', '17+', '17+']

content_ratings = {}

for rating in ratings:
    if rating in content_ratings:
        content_ratings[rating] += 1
    else:
        content_ratings[rating] = 1
```

* Write a function named extract() that can extract any column you want from the apps_data data set.
* Use the extract() function to extract the values in the prime_genre column. Store them in a variable named genres. The index number of this column is 11.

```python
opened_file = open('AppleStore.csv')
from csv import reader
read_file = reader(opened_file)
apps_data = list(read_file)

def extract(n):
    column = []
    for i in apps_data[1:]:
        value = i[n]
        column.append(value)
    return(column)

genres = extract(11)
```

