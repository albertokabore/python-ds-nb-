# Python Data Structures and Notebooks

Complete the tasks in the Python Notebook in this repository.
To be submitted for credit, all changes must be committed and pushed to this repository (do not create your own repository unless instructed to on the course website).

## Rubric
Web Mining and Applied NLP (44-620)
Python Notebooks, Basics, and Data Structures

Question 1. Modify the Markdown cell above to put your name after "Student Name:"; you will be expected to do this in all assignments presented in this format for this class.


Question 3. Using loops (and potentially conditionals), write Python code that prints the factorial of each integer from 1 through 10 (which you can store in a variable if you want). The factorial of an integer is the product of all of the integers of 1 through the number. Print the result with an appropriate label.

```python

for i in range(1, 11):
    factorial = 1
    for j in range(1, i + 1):
        factorial *= j
    print(f"The factorial of {i} is: {factorial}")
```

Question 4. Write a python function that takes a single parameter and calculates and returns the average (mean) of the values in the parameter (which you may assume is iterable).  Show that your function works by printing the result of calling the function on the list in the cell below.  

```python
def calculate_mean(values):
    if len(values) == 0:
        return 0  # Handle empty list case
    return sum(values) / len(values)

# Test list
testlist = [1, -1, 2, -2, 3, -3, 4, -4]

# Call the function and print the result
mean_value = calculate_mean(testlist)
print(f"The average of testlist is: {mean_value}")
```
Question 5. Using your mean function above, write a function that calculates the variance of the list of numbers (see https://en.wikipedia.org/wiki/Variance for more information on the formula). In short:
* subtract the mean of the elements in the list from every element in the list; store these values in a new list
* square every element in the new list and sum the elements together
* divide the resulting number by N (where N is the length of the original list)

Show the result of calling your function in the lists in the code cell. You must use one or more list comprehensions or map/filter in your code.  

```python
# Test lists
list1 = [5.670e-1, -1.480e+0, -5.570e-1, -1.470e+0, 7.340e-1, 1.050e+0, 4.480e-1, 2.570e-1, -1.970e+0, -1.460e+0]
list2 = [-1.780e+0, 2.640e-1, 1.160e+0, 9.080e-1, 1.780e+0, 1.080e+0, 1.050e+0, -4.630e-2, 1.520e+0, 5.350e-1]

def calculate_variance(values):
    # Calculate the mean using the previously defined function
    mean_value = calculate_mean(values)
    
    # Create a list of squared differences from the mean
    squared_diffs = [(x - mean_value) ** 2 for x in values]
    
    # Calculate the variance by summing the squared differences and dividing by the length of the list
    variance = sum(squared_diffs) / len(values)
    
    return variance

# Calculate and print the variances for list1 and list2
variance_list1 = calculate_variance(list1)
variance_list2 = calculate_variance(list2)

print(f"The variance of list1 is: {variance_list1}")
print(f"The variance of list2 is: {variance_list2}")
```
