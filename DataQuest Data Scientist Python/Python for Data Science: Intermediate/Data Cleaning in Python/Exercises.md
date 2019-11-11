* Use a for loop to loop over the moma list of lists. In each iteration of the loop:

* Clean the Nationality column.
* Clean the Gender column of the data set (found at index 5 of the row) by repeating the same technique you used for the Nationality column.

```python
# Variables you create in previous screens
# are available to you, so you don't need
# to read the CSV again
for i in moma:
    # remove parentheses from the nationality column
    nationality = i[2]
    nationality = nationality.replace("(","")
    nationality = nationality.replace(")","")
    row[2] = nationality

    # remove parentheses from the gender column
    gender = i[5]
    gender = gender.replace("(","")
    gender = gender.replace(")","")
    row[5] = gender
```
* Clean the Gender column.
* Assign the value from the Gender column, at index 5, to a variable.
* Make the changes to the value of that variable.
* Use the str.title() method to make the capitalization uniform.
* Use an if statement to check if the value is an empty string. If the value is an empty string, give it the value "Gender                Unknown/Other".
* Assign the modified variable back to list index 5 of the row.
* Clean the Nationality column of the data set (found at index 2) by repeating the same technique you used for the Gender column.
* For missing values in the Nationality column, use the string "Nationality Unknown".

```python
for i in moma:
    gender = i[5]
    
    gender = gender.title()
    
    if not gender:
        gender = "Gender Unknown/Other"
    i[5] = gender
    
    
    #Fix the capitalization
    nationality = i[2]
    nationality = nationality.title()
    if not nationality:
        nationality = "Nationality Unknown"
    i[2] = nationality
    ```
    
    
