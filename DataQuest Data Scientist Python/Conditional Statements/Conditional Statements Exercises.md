Inside the for loop:
1. Assign the price of an app as a float to a variable named price. The price is the fifth element in each row (don't forget that the index starts at 0).
2. price == 0.0, append the value stored in rating to the free_apps_ratings list using the list_name.append() command (note the free_apps_ratings is already defined in the code editor). Be careful with indentation.
3. outside the for loop body, compute the average rating of free apps. Assign the result to a variable named avg_rating_free. The ratings are stored in the free_apps_ratings list.

```python
# INITIAL CODE
opened_file = open('AppleStore.csv')
from csv import reader
read_file = reader(opened_file)
apps_data = list(read_file)

free_apps_ratings = []
for row in apps_data[1:]:
    rating = float(row[7])
    # Complete the code from here
    price = float(row[4])
    if price == 0.0:
        free_apps_ratings.append(rating)

avg_rating_free = sum(free_apps_ratings)/len(free_apps_ratings)
```

Compute the average rating of non-gaming apps.

```python
opened_file = open('AppleStore.csv')
from csv import reader
read_file = reader(opened_file)
apps_data = list(read_file)

non_games_ratings = []
for i in apps_data[1:]:
    rating = float(i[7])
    genre = i[11]
    
    if genre != 'Games':
        non_games_ratings.append(rating)
        
avg_rating_non_games = sum(non_games_ratings)/len(non_games_ratings)
```

What is the average rating of the apps that have a price greater than $9?
How many apps have a price greater than $9?
How many apps have a price smaller than or equal to $9?

```python
opened_file = open('AppleStore.csv')
from csv import reader
read_file = reader(opened_file)
apps_data = list(read_file)

p_over_9 = []
n_apps_more_9 = 0
n_apps_less_9 = 0
for i in apps_data[1:]:
    rating = float(i[7])
    price = float(i[4])
    if price > 9.0:
        p_over_9.append(rating)
        
for i in apps_data[1:]:
    rating = float(i[7])
    price = float(i[4])
    if price > 9.0:
        n_apps_more_9 = n_apps_more_9 + 1
    elif price <= 9.0:
        n_apps_less_9 = n_apps_less_9 + 1

avg_rating = sum(p_over_9) /  len(p_over_9)
```

* If the price of the app is 0, label the app as "free" by appending the string 'free' to the current iteration variable.
* If the price of the app is greater than 0 and less than 20, label the app as "affordable." For efficiency purposes, use an elif clause.
* If the app is greater or equal to 20 and less than 50, label the app as "expensive." For efficiency purposes, use an elif clause.
* If the app is greater or equal to 50, label the app as "very expensive." For efficiency purposes, use an elif clause.
* Name the newly created column "price_label" by appending the string 'price_label' to the first row of the apps_data data set.
* Inspect the header row and the first five rows to see some of the changes you made.

``` python
opened_file = open('AppleStore.csv')
from csv import reader
read_file = reader(opened_file)
apps_data = list(read_file)

for app in apps_data[1:]:
    price = float(app[4])
    # Complete code from here
    if price == 0.0:
        app.append('free')
    elif price > 0.0 and price < 20:
        app.append('affordable')
    elif price >= 20 and price < 50:
        app.append('expensive')
    elif price >= 50:
        app.append('very expensive')

apps_data[0].append('price_label')

print(apps_data[-1])
```
Count the number of times each unique content rating occurs in the data set
```python
opened_file = open('AppleStore.csv')
from csv import reader
read_file = reader(opened_file)
apps_data = list(read_file)

content_ratings = {'4+': 0, '9+': 0, '12+': 0, '17+': 0}

for row in apps_data[1:]:
    c_rating = row[10]
    if c_rating in content_ratings:
        content_ratings[c_rating] += 1
print(content_ratings)
```

Count the number of times each unique content rating occurs in the data set while finding the unique values automatically.

```python
opened_file = open('AppleStore.csv')
from csv import reader
read_file = reader(opened_file)
apps_data = list(read_file)

content_ratings = {}
for i in apps_data[1:]:
    c_rating = i[10]
    if c_rating in content_ratings:
        content_ratings[c_rating] += 1
    else:
        content_ratings[c_rating] = 1

print(content_ratings)
```
Count the number of times each unique genre occurs
```python
opened_file = open('AppleStore.csv')
from csv import reader
read_file = reader(opened_file)
apps_data = list(read_file)

genre_counting = {}

for i in apps_data[1:]:
    genre = i[11]
    if genre in genre_counting:
        genre_counting[genre] += 1
    else:
        genre_counting[genre] = 1
        
        
print(genre_counting)
```
Loop over the content_ratings dictionary and transform the frequencies to percentages
Find out the percentage of apps that have a content rating of '17+'. Assign your answer to a variable named percentage_17_plus.
Find out the percentage of apps that can be downloaded by a 15-year-old. Assign your answer to a variable named percentage_15_allowed.
```python
content_ratings = {'4+': 4433, '12+': 1155, '9+': 987, '17+': 622}
total_number_of_apps = 7197

for i in content_ratings:
    content_ratings[i]/= total_number_of_apps
    content_ratings[i] *= 100
    
print(content_ratings)
percentage_17_plus = content_ratings['17+']
percentage_15_allowed = content_ratings['4+'] + content_ratings['9+'] + content_ratings['12+']
```

Transform the frequencies inside content_ratings to proportions and percentages while creating separate dictionaries for each.
Optional challenge: try to solve this exercise using a single for loop 

```python
content_ratings = {'4+': 4433, '12+': 1155, '9+': 987, '17+': 622}
total_number_of_apps = 7197

c_ratings_proportions = {}
c_ratings_percentages = {}

for key in content_ratings:
    proportion = content_ratings[key] / total_number_of_apps
    percentage = proportion * 100
    
    c_ratings_proportions[key] = proportion
    c_ratings_percentages[key] = percentage
```

Extract the values in the size_bytes column in a separate list.
Find out the minimum and the maximum app data size.

```python
opened_file = open('AppleStore.csv')
from csv import reader
read_file = reader(opened_file)
apps_data = list(read_file)

data_sizes = []

for i in apps_data[1:]:
    size = i[2]
    data_sizes.append(float(size))
    
    min_size = min(data_sizes)
    max_size = max(data_sizes)
```

