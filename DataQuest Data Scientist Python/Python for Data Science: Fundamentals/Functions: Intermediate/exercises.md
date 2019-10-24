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

* Edit the open_dataset() function (already written in the code editor) such that:

* If the data set has a header, the function returns separately both the header and the rest of the data set.
** Else (if there's no header), the function returns the entire data set.

* Use the updated open_dataset() function to open the AppleStore.csv file, which has a header row.

```python
def open_dataset(file_name='AppleStore.csv', header=True):        
    opened_file = open(file_name)
    from csv import reader
    read_file = reader(opened_file)
    data = list(read_file)
    
    if header:
        return data[1:], data[0]
    else:
        return data
    
all_data = open_dataset()
header = all_data[1]
apps_data = all_data[0]
```

* Use the open_dataset() function to open the AppleStore.csv file, which has a header row.
* Do the variable assignment step in a single line of code.
* Assign the header to a variable named header.
* Assign the rest of the data set to a variable named apps_data.

```python
def open_dataset(file_name='AppleStore.csv', header=True):        
    opened_file = open(file_name)
    from csv import reader
    read_file = reader(opened_file)
    data = list(read_file)
    
    if header:
        return data[1:], data[0]
    else:
        return data
apps_data, header = open_dataset()
```


