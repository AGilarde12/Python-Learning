* Use a for loop to loop over the moma list of lists. In each iteration of the loop:

Clean the Nationality column.
Clean the Gender column of the data set (found at index 5 of the row) by repeating the same technique you used for the Nationality column.

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
