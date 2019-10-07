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
