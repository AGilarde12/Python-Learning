* Write a function named max() that takes in a list but just returns the string "No max value returned".
* Use the max() function on the list a_list. Assign the result to a variable named max_val_test_0.
* Print max_val_test_0. Observe how the function returned "No max value returned" instead of 10.
* Run the code del max to delete the max() function you wrote. This will allow you to use the built-in max() function again.

```python
a_list = [1, 8, 10, 9, 7]
print(max(a_list))

def max(a_list):
    return("No max value returned")

max_val_test_0 = max(a_list)
print(max_val_test_0)

del max
```

* Write a function such that it only returns data sets without header rows.

```python
def open_dataset(file_name='AppleStore.csv', header=True):        
    opened_file = open(file_name)
    from csv import reader
    read_file = reader(opened_file)
    data = list(read_file)
    
    if header:
        return data[1:]
    else:
        return data
    
apps_data = open_dataset()
```

