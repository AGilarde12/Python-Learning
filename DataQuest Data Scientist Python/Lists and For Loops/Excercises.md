Compute the average app rating for the apps stored in the app_data_set variable.

1. Initialize a variable named rating_sum with a value of zero outside the loop body.
2. Loop (iterate) over the app_data_set list of lists. For each of the five iterations of the loop (for each row in app_data_set):
3. Extract the rating of the app and store it to a variable named rating. The rating is the last element of each row.
4. Add the value stored in rating to the current value of the rating_sum.
5. Outside the loop body, divide the rating sum (stored in rating_sum) by the number of ratings to get an average value. Store the result in a variable named avg_rating.

```python
row_1 = ['Facebook', 0.0, 'USD', 2974676, 3.5]
row_2 = ['Instagram', 0.0, 'USD', 2161558, 4.5]
row_3 = ['Clash of Clans', 0.0, 'USD', 2130805, 4.5]
row_4 = ['Temple Run', 0.0, 'USD', 1724546, 4.5]
row_5 = ['Pandora - Music & Radio', 0.0, 'USD', 1126879, 4.0]

app_data_set = [row_1, row_2, row_3, row_4, row_5]

rating_sum = 0
for i in app_data_set:
    rating = i[-1]
    rating_sum = rating_sum + rating
    print(rating_sum)
    

avg_rating = rating_sum/len(app_data_set)    
```
