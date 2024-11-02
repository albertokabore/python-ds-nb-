# Python Data Structures and Notebooks

## Rubric
Web Mining and Applied NLP (44-620)
Python Notebooks, Basics, and Data Structures

Question 1. Modify the Markdown cell above to put your name after "Student Name:"; you will be expected to do this in all assignments presented in this format for this class.

```powershell
Student Name: Albert Kabore
```

Question 2. Write code that divides any two numbers, stores the result in a variable, and prints the result with an appropriate label.

```python
# Define two numbers
num1 = 10  # You can change this to any number
num2 = 2   # You can change this to any non-zero number

# Perform division and store the result
result = num1 / num2

# Print the result with a label
print(f"The result of dividing {num1} by {num2} is: {result}")
```


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

Question 6. Create a list with at least 15 elements in it. Use list slicing to print the following:
* The first 5 elements of the list
* The last 5 elements of the list
* The list reversed (hint, show the entire list with a stride of -1)
* Every second element in the list
* Every third element in the list (stride of 3)

```python
# Sample list with 15 elements
my_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15]

# The first 5 elements of the list
print("First 5 elements:", my_list[:5])

# The last 5 elements of the list
print("Last 5 elements:", my_list[-5:])

# The list reversed
print("Reversed list:", my_list[::-1])

# Every second element in the list
print("Every second element:", my_list[::2])

# Every third element in the list
print("Every third element:", my_list[::3])
```

Question 7. Build a dictionary that contains the following information about this class (with appropriate names as keys):
* The name
* The course number
* The semester/term in which you are taking this course
* The number of credit hours this course counts for
* A list of the course learning objectives

The majority of this information can be found in the syllabus. Print the dictionary.

```python
# Dictionary containing information about the class
course_info = {
    "name": "Web Mining & Applied Natural Language Processing (NLP)",
    "course_number": "44-620 80/81",
    "semester_term": "Fall 2024 - Block 2",
    "credit_hours": 3,
    "learning_objectives": [
        "View hidden files and folders",
        "View file extensions",
        "Create a new GitHub project repository",
        "Clone a project repository down to their machine",
        "Open their project repository folder in VS Code",
        "Manage a project virtual environment (create, activate, install dependencies)",
        "Employ common project files (e.g. README.md, .gitignore, requirements.txt)",
        "Create and execute new Python scripts",
        "Create and execute new Jupyter notebooks using Python and Markdown",
        "Use git pull and git add / commit / push to keep a project synchronized between their machine and GitHub repository"
    ]
}

# Print the dictionary
print(course_info)
```

Question 8.  Given the dictionary defined in the code cell below, print the list of level 3 spells the character has.                                                                                                                                    

```python
# Dictionary with player character details
player_character = {
    'name': 'Kitab',
    'class': [('Cleric: Knowledge', 7)],
    'spells': {
        'cantrip': ['Guidance', 'Light', 'Thaumaturgy', 'Toll the Dead', 'Word of Radiance'],
        'level 1': ['Command', 'Detect Magic', 'Healing Word', 'Identify', 'Sleep'],
        'level 2': ['Augury', 'Calm Emotions', 'Command', 'Invisibility', 'Lesser Restoration'],
        'level 3': ['Mass Healing Word', 'Nondetection', 'Revivify', 'Feign Death', 'Speak with Dead'],
        'level 4': ['Banishment', 'Confusion']
    }
}

# Print the list of level 3 spells
print("Level 3 spells:", player_character['spells']['level 3'])
```

Question 9. Write code to determine the number of unique elements in the list below.  You MUST use a set in finding your solution.  Print the number of unique values in the list with an appropriate label.      

```python
# List of values
values = [10, 11, 10, 8, 1, 12, 0, 1, 6, 5, 5, 13, 6, 15, 0, 0, 1, 1, 9, 7]

# Convert the list to a set to remove duplicates
unique_values = set(values)

# Print the number of unique values
print("Number of unique values:", len(unique_values))
```

Question 10. Create a new Jupyter Notebook (the name of the notebook should be your S number). Add a Markdown cell that contains your name. Add a Code cell and write Python that uses loops to draw the following pattern:

*      *
**    **
***  ***
********

Make sure to add and submit both the new notebook and the changes to this notebook for this assignment.

```python
# Define the number of rows for the pattern
rows = 4

# Loop through each row
for i in range(1, rows + 1):
    # Print left-side stars
    print('*' * i, end='')

    # Print spaces in the middle
    print(' ' * (2 * (rows - i)), end='')

    # Print right-side stars
    print('*' * i)
```

### Export to HTML and Finalize Repo
Export Using Inline Command (in a Python Cell)

Add a Python cell at the end of your notebook, enter the following Python command (change the file name as needed), and run the cell:

```python
!jupyter nbconvert --to html python-ds.ipynb
```

```python
!jupyter nbconvert --to html S575959.ipynb
```
