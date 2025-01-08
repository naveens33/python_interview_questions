# 100 Python interview questions with answers.
---
### What is Python?
Answer: Python is a high-level, interpreted, and dynamically typed programming language. It emphasizes code readability and supports multiple programming paradigms.
### 1. What are the key features of Python?
**Answer:** 
1. Interpreted
2. Dynamically typed
3. Platform-independent
4. Extensive standard library
5. Object-oriented and functional programming support
### 2. What is PEP 8?
**Answer:** PEP 8 is the Python Enhancement Proposal that outlines conventions for writing readable Python code.
### 3. How is memory managed in Python?
**Answer:** Python uses automatic memory management via reference counting and garbage collection. The gc module handles cyclic references.
### 4. What are Python's built-in data types?
**Answer:** 
1. Numeric types: int, float, complex
2. Sequence types: list, tuple, range
3. Text type: str
4. Set types: set, frozenset
5. Mapping type: dict
6. Boolean type: bool
### 5. What are Python decorators?
**Answer:** Decorators are functions that modify the behavior of another function or method.
```Python
# Define the decorator
def add_title(title):
    def decorator(func):
        def wrapper(name):
            # Add the title before the name
            return f"{title} {func(name)}"
        return wrapper
    return decorator

# Apply the decorator to a function
@add_title("Mr.")
def display_name(name):
    return name

# Use the decorated function
print(display_name("John Doe"))

# Apply another title
@add_title("Mrs.")
def display_name_with_title(name):
    return name

print(display_name_with_title("Jane Doe"))
```
```
Mr. John Doe
Mrs. Jane Doe
```
### 6. Explain list comprehension in Python.
**Answer:** List comprehension provides a concise way to create lists.

[Reference link](https://github.com/naveens33/python_tutorials/blob/master/list_comprehension/list_comprehension.md)

Here’s a sample program to demonstrate **list comprehension** in Python:

---

### Basic Example: Squares of Numbers
```python
# Generate a list of squares for numbers 1 through 10
squares = [x**2 for x in range(1, 11)]
print(squares)
```

**Output:**
```
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

---

### Example with Condition: Even Numbers
```python
# Generate a list of even numbers from 1 to 20
evens = [x for x in range(1, 21) if x % 2 == 0]
print(evens)
```

**Output:**
```
[2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
```

---

### Nested Example: Multiplication Table
```python
# Generate a multiplication table for numbers 1 through 3
multiplication_table = [[x * y for y in range(1, 6)] for x in range(1, 4)]
print(multiplication_table)
```

**Output:**
```
[[1, 2, 3, 4, 5],
 [2, 4, 6, 8, 10],
 [3, 6, 9, 12, 15]]
```

---

### Example with String Manipulation: Capitalizing Words
```python
# Capitalize each word in a list
words = ["hello", "world", "python", "rocks"]
capitalized = [word.capitalize() for word in words]
print(capitalized)
```

**Output:**
```
['Hello', 'World', 'Python', 'Rocks']
```

---

### Explanation:
- **Syntax**: `[expression for item in iterable if condition]`
  - `expression`: The operation or value to be included in the new list.
  - `item`: The variable representing each element in the iterable.
  - `iterable`: The source of elements (e.g., list, range, etc.).
  - `if condition` (optional): A filter to include elements that meet the condition.

List comprehensions provide a concise and Pythonic way to generate lists in a single line, making the code more readable and efficient.
### 7. What is the difference between deepcopy and shallow copy?
**Answer:** 
* copy.copy(): Creates a shallow copy; changes in nested objects affect the copied object.
* copy.deepcopy(): Creates a deep copy; changes in nested objects do not affect the copied object.

**Shallow Copy Example:**
```Python
import copy

# Create a simple list
original_list = [1, 2, 3, 4]

# Create a shallow copy of the list
shallow_copied_list = copy.copy(original_list)

# Modify the original list
original_list[0] = 99

# Outputs
print("Original List:", original_list)
print("Shallow Copied List:", shallow_copied_list)
```
**Output**
```
Original List: [99, 2, 3, 4]
Shallow Copied List: [1, 2, 3, 4]
```
**Deep Copy Example:**
```python
import copy

# Create a nested list
original_list = [[1, 2, 3], [4, 5, 6]]

# Create a deep copy
deep_copied_list = copy.deepcopy(original_list)

# Modify an element in the original list
original_list[0][0] = 99

# Outputs
print("Original List:", original_list)
print("Deep Copied List:", deep_copied_list)
```
**Output**
```
Original List: [[99, 2, 3], [4, 5, 6]]
Deep Copied List: [[1, 2, 3], [4, 5, 6]]
```
### 8. What are Python's lambda functions?
**Answer:** Lambda functions are anonymous, single-expression functions.

[Reference link](https://github.com/naveens33/python_tutorials/blob/master/functions/lambda.md) 

***Example 1:*** Adding two numbers using a lambda expression:
```python
add = lambda x, y: x + y
result = add(3, 5)
print(result)  # Output: 8
```
### 9. What are Python's modules and packages?
**Answer:** 
1. Module: A Python file containing functions and variables.
2. Package: A collection of modules, typically containing an __init__.py.
### 10. What is the Global Interpreter Lock (GIL)?
**Answer:** GIL is a mutex that protects access to Python objects, ensuring that only one thread executes Python bytecode at a time.
### 11. Explain the difference between is and ==.
**Answer:** 
1. is: Checks if two references point to the same object.
2. ==: Checks if the values of two objects are equal.
**Example**
```python
# Using == (value comparison)
a = [1, 2, 3]
b = [1, 2, 3]

# Using is (identity comparison)
c = a

print(f"a == b: {a == b}")  # Compare values
print(f"a is b: {a is b}")  # Compare identities

print(f"a == c: {a == c}")  # Compare values
print(f"a is c: {a is c}")  # Compare identities
```
**Output**
```
a == b: True
a is b: False
a == c: True
a is c: True
```
### 12. What are metaclasses in Python?
**Answer:** Metaclasses are classes of a class that define the behavior and structure of other classes.
### 13. What is the asyncio module in Python?
**Answer:** The asyncio module provides support for asynchronous programming.
### 14. How does Python handle exceptions?
**Answer:** Python uses try, except, else, and finally blocks for exception handling.
### 15. How would you reverse a string in Python?
**Answer:** reversed_string = my_string[::-1]
### 16. Write a Python program to check if a number is prime.
```python
def is_prime(num):
    # Check for numbers less than 2
    if num <= 1:
        return False

    # Check for factors from 2 to sqrt(num)
    for i in range(2, int(num**0.5) + 1):
        if num % i == 0:
            return False  # num is divisible by i, hence not prime

    return True  # num is prime if no factors are found

# Input from the user
number = int(input("Enter a number: "))

# Check if the number is prime
if is_prime(number):
    print(f"{number} is a prime number.")
else:
    print(f"{number} is not a prime number.")
```
**Output**
```
Enter a number: 29
29 is a prime number.
```
### 17. How can you optimize a large dataset processing task in Python?
**Answer:** Use generators, multiprocessing, or libraries like Dask or PySpark.
### 18. Explain the Python with statement.
**Answer:** The with statement simplifies resource management like file handling.
```Python
# Using the 'with' statement to handle a file
with open("example.txt", "w") as file:
    file.write("Hello, World!\n")
    file.write("This is an example of using the 'with' statement.\n")

# File is automatically closed after exiting the 'with' block
print("File writing completed.")
```
### 19. Explain Python's dataclasses. 
**Answer:** dataclasses is a module to create classes for storing data.
### 20. What are Python’s key differences from other languages like Java or C++?
**Answer:** Python is dynamically typed, has simple syntax, and does not require manual memory management.
### 21. Explain Python’s indentation rules.
**Answer:** Python uses indentation to define blocks of code instead of braces or keywords.
### 22. What is the difference between None, False, and 0?
**Answer:** None is a null object, False is a Boolean, and 0 is a number.
### 23. How do you add comments in Python?
**Answer:** Use # for single-line comments and triple quotes (''' or """) for multi-line comments.
### 24. What is a docstring in Python?
**Answer:** A docstring is a string used to document a module, class, or function.
### 25. What are frozen sets?
**Answer:** Immutable sets in Python that do not allow modifications.
```python
# Creating a frozenset
fs = frozenset([1, 2, 3, 4])

# Trying to modify the frozenset (will raise an error)
try:
    fs.add(5)  # This will raise an error since frozensets are immutable
except AttributeError as e:
    print(e)  # Output: 'frozenset' object has no attribute 'add'

# Using frozenset in set operations
fs1 = frozenset([1, 2, 3])
fs2 = frozenset([3, 4, 5])

# Union
print("Union:", fs1 | fs2)  # Output: Union: frozenset({1, 2, 3, 4, 5})

# Intersection
print("Intersection:", fs1 & fs2)  # Output: Intersection: frozenset({3})

# Difference
print("Difference:", fs1 - fs2)  # Output: Difference: frozenset({1, 2})

# Symmetric Difference
print("Symmetric Difference:", fs1 ^ fs2)  # Output: Symmetric Difference: frozenset({1, 2, 4, 5})

```
**Output**
```
'frozen' object has no attribute 'add'
Union: frozenset({1, 2, 3, 4, 5})
Intersection: frozenset({3})
Difference: frozenset({1, 2})
Symmetric Difference: frozenset({1, 2, 4, 5})
```
### 26. What is the difference between tuple and list?
**Answer:** Tuples are immutable, while lists are mutable.
### 27. How do you check the type of an object in Python?
**Answer:** Use type(object).
### 28. What is the difference between isinstance() and type()?
**Answer:** isinstance() checks inheritance, while type() checks the exact type.
### 29. How are strings immutable in Python?
**Answer:** Any operation on a string creates a new object instead of modifying the original.
### 30. What is the difference between break and continue?
In Python, `break` and `continue` are control flow statements used inside loops (`for` and `while`) to alter the loop's execution. However, they serve different purposes:

### `break`:
- **Purpose**: It **terminates** the loop entirely, regardless of whether the loop condition has been fully evaluated or not.
- **Usage**: The `break` statement is used when you want to exit the loop early, often when a certain condition is met.
- **Effect**: It exits the loop and proceeds to the next statement after the loop.

### `continue`:
- **Purpose**: It **skips the current iteration** of the loop and proceeds with the next iteration.
- **Usage**: The `continue` statement is used when you want to skip the rest of the code inside the loop for the current iteration but continue with the next iteration.
- **Effect**: The loop continues from the next iteration without executing the remaining code in the loop body for the current iteration.

**Example Code Demonstrating `break` and `continue`:**

```python
# Example with break
print("Using break:")
for i in range(1, 6):
    if i == 3:
        print("Breaking the loop at i =", i)
        break
    print("i =", i)

# Example with continue
print("\nUsing continue:")
for i in range(1, 6):
    if i == 3:
        print("Skipping iteration at i =", i)
        continue
    print("i =", i)
```

**Output**:
```
Using break:
i = 1
i = 2
Breaking the loop at i = 3

Using continue:
i = 1
i = 2
Skipping iteration at i = 3
i = 4
i = 5
```

### 31. How does the pass statement work?
**Answer:** It acts as a placeholder for code to be written later.
### 32. Explain Python’s ternary conditional operator.
**Answer:** Syntax: value_if_true if condition else value_if_false.
```Python
# Using ternary operator to check if a number is even or odd
num = 10

result = "Even" if num % 2 == 0 else "Odd"

print(result)  # Output: Even
```
### 33. How is the else block used with loops?
**Answer:** Executes if the loop completes without a break.
```Python
# Check if a number is prime
num = 29

for i in range(2, num):
    if num % i == 0:
        print(f"{num} is not a prime number (divisible by {i})")
        break
else:
    print(f"{num} is a prime number.")  # Executes only if no 'break' occurs
```
**Output**
```
29 is a prime number.
```
### 34. What is the difference between for and while loops?

| **Feature**              | **`for` Loop**                                             | **`while` Loop**                                               |
|--------------------------|------------------------------------------------------------|---------------------------------------------------------------|
| **Control**              | Iterates over a sequence (e.g., list, tuple, range).       | Runs as long as a condition is `True`.                         |
| **Use Case**             | When the number of iterations is known or based on a sequence. | When the number of iterations is not predetermined.            |
| **Iteration Type**       | Iterates through a collection or range.                    | Iterates based on a condition being `True`.                    |
| **Termination**          | Terminates when the sequence ends or when `break` is encountered. | Terminates when the condition becomes `False` or when `break` is encountered. |
| **Condition Check**      | Implicitly handled by the iterable (e.g., the range or list). | Explicitly checked before each iteration.                      |
| **Example**              | `for` loop iterating over a list.                          | `while` loop checking a condition.                             |

**Example: `for` Loop**

```python
# Using a 'for' loop to iterate over a list
fruits = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(fruit)
```

**Output:**
```
apple
banana
cherry
```

**Explanation**: The `for` loop iterates over the `fruits` list and prints each element.


**Example: `while` Loop**

```python
# Using a 'while' loop to count from 1 to 5
i = 1
while i <= 5:
    print(i)
    i += 1
```

**Output:**
```
1
2
3
4
5
```

**Explanation**: The `while` loop continues to run as long as `i <= 5` is `True`, printing `i` and incrementing it on each iteration.

### 35. What is the difference between *args and **kwargs?
In Python, `*args` and `**kwargs` are used to pass a variable number of arguments to a function. They allow you to call a function with a dynamic number of arguments.

### 36. Difference Between `*args` and `**kwargs`:

| **Feature**             | **`*args`**                                             | **`**kwargs`**                                              |
|-------------------------|---------------------------------------------------------|------------------------------------------------------------|
| **Syntax**              | `*args` is used to pass a variable number of **non-keyword** arguments. | `**kwargs` is used to pass a variable number of **keyword** arguments. |
| **Type of Arguments**   | Accepts a tuple of arguments.                         | Accepts a dictionary of key-value pairs.                   |
| **Usage**               | Used when you do not know how many arguments will be passed to the function. | Used when you want to pass a variable number of named (keyword) arguments. |
| **Example**             | `*args` can be used to pass positional arguments.       | `**kwargs` can be used to pass named (keyword) arguments.  |

**Example 1: Using `*args`**

```python
def print_numbers(*args):
    for num in args:
        print(num)

# Function call with a variable number of arguments
print_numbers(1, 2, 3, 4, 5)
```

**Output:**
```
1
2
3
4
5
```

**Explanation**:
- `*args` collects all the arguments passed to the function and stores them in a tuple.
- In this example, the `print_numbers` function prints each number passed as an argument.

**Example 2: Using `**kwargs`**

```python
def print_student_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

# Function call with keyword arguments
print_student_info(name="John", age=20, grade="A")
```

**Output:**
```
name: John
age: 20
grade: A
```

**Explanation**:
- `**kwargs` collects all the keyword arguments passed to the function and stores them in a dictionary.
- The function `print_student_info` prints each key-value pair in the dictionary.

**Example 3: Combining `*args` and `**kwargs`**

```python
def student_info(*args, **kwargs):
    print("Positional arguments:", args)
    print("Keyword arguments:", kwargs)

# Function call with both *args and **kwargs
student_info(1, 2, 3, name="John", age=20)
```

**Output:**
```
Positional arguments: (1, 2, 3)
Keyword arguments: {'name': 'John', 'age': 20}
```

**Explanation**:
- In this example, `*args` collects the positional arguments, and `**kwargs` collects the keyword arguments. Both can be used together in a function.
- The `args` are stored as a tuple, and the `kwargs` are stored as a dictionary.

### 37. How do you make a function return multiple values?
**Answer:** Use tuples or lists.
In Python, you can make a function return multiple values by simply separating the values with commas. When you do this, Python automatically packs the values into a **tuple**, which can then be accessed individually when the function is called.

**Example 1: Returning multiple values as a tuple**

```python
def get_student_info():
    name = "John"
    age = 20
    grade = "A"
    return name, age, grade  # Returning multiple values

# Calling the function and unpacking the returned tuple
student_name, student_age, student_grade = get_student_info()

print(f"Name: {student_name}")
print(f"Age: {student_age}")
print(f"Grade: {student_grade}")
```

**Output:**
```
Name: John
Age: 20
Grade: A
```

**Example 2: Returning multiple values as a list or dictionary**

While returning a tuple is the default, you can also return values as a **list** or **dictionary** if you prefer those data structures.

**Returning as a List:**
```python
def get_student_info():
    name = "John"
    age = 20
    grade = "A"
    return [name, age, grade]  # Returning as a list

info = get_student_info()
print(info)  # Output: ['John', 20, 'A']
```

**Returning as a Dictionary:**
```python
def get_student_info():
    name = "John"
    age = 20
    grade = "A"
    return {"name": name, "age": age, "grade": grade}  # Returning as a dictionary

info = get_student_info()
print(info)  # Output: {'name': 'John', 'age': 20, 'grade': 'A'}
```

### 38. What are Python's built-in functions?
**Answer:** Examples: len(), map(), filter(), zip().
### 39. What is a higher-order function in Python?
**Answer:** A function that takes another function as an argument or returns one.
### 40. Explain recursion with an example.
**Answer:** A function calling itself. Example: Fibonacci series calculation.
### 41. What is Recursion?

Recursion is a technique in programming where a function calls itself to solve smaller instances of the same problem. It is often used to break down complex problems into simpler ones.

**Recursive Function for Fibonacci:**

```python
def fibonacci(n):
    if n == 0:
        return 0  # Base case
    elif n == 1:
        return 1  # Base case
    else:
        return fibonacci(n - 1) + fibonacci(n - 2)  # Recursive case

# Calling the function
result = fibonacci(6)
print(f"Fibonacci number at position 6 is {result}")
```

**Output:**
```
Fibonacci number at position 6 is 8
```

**Advantages of Recursion:**
- Recursive functions can simplify the solution to problems that have a repetitive structure, like factorials, Fibonacci numbers, tree traversals, etc.
- It can make the code shorter and more readable in certain situations.

**Disadvantages of Recursion:**
- Recursion can be less efficient and use more memory because each function call adds a new layer to the call stack.
- If the recursion depth is too large, it can lead to a **stack overflow**.

### 42. What is the purpose of self in Python?
In Python, the self keyword is used in object-oriented programming (OOP) to represent the instance of the class. It allows you to access the instance's attributes and methods within the class.

**Purpose of self:**
1. Referring to Instance Variables: The self parameter allows you to reference instance variables (attributes) of the class, which are unique to each instance of the class.
2. Accessing Instance Methods: It is used to call other methods within the same class and allows you to refer to the current instance of the class.
3. Distinguishing Between Instance Variables and Local Variables: self helps to differentiate between instance variables and local variables within a method.
### 43. What is the difference between a class and an instance?
In object-oriented programming (OOP), the concepts of **class** and **instance** are foundational. Here’s a breakdown of their differences:

| **Aspect**               | **Class**                                  | **Instance**                                  |
|--------------------------|--------------------------------------------|-----------------------------------------------|
| **Definition**            | A class is a blueprint or template for creating objects. It defines the attributes (data) and methods (functions) that the objects created from it will have. | An instance is a specific object created from a class. It is an individual occurrence of the class with its own unique set of data. |
| **Memory**                | A class does not occupy memory for data. It only occupies memory for the structure (methods, attributes) used to create instances. | Each instance occupies memory for its own data (attributes). Multiple instances of a class can exist, each with its own set of data. |
| **Creation**              | A class is created once, usually during the program execution, and serves as a template. | Instances are created by calling the class, usually using the `__init__` method to initialize the object's state. |
| **Accessing Attributes**  | Class attributes are shared by all instances of the class. | Instance attributes are unique to each instance. |
| **Examples**              | A class can be considered like a `Car` class, which defines the structure of a car. | An instance would be a specific car, like a `Car("Honda Civic", "Red", 2022)`. |
| **Methods**               | Methods in a class are general and define actions that can be performed on instances. | Instances can call methods defined in the class to perform actions specific to that instance. |

### 44. How do you implement inheritance in Python?

Inheritance is a fundamental concept in object-oriented programming (OOP) that allows a class to inherit attributes and methods from another class. This helps in promoting code reusability, and a child class can extend or modify the behavior of its parent class.

**Basic Syntax:**
```python
class ParentClass:
    # Parent class definition

class ChildClass(ParentClass):
    # Child class definition
```

In this syntax:
- The **`ParentClass`** is the base class (also called superclass).
- The **`ChildClass`** is the derived class (also called subclass).
- The child class inherits the attributes and methods of the parent class.

**Key Points:**
- A **child class** can inherit all attributes and methods from the **parent class**.
- A **child class** can add its own attributes and methods.
- A **child class** can override or extend the behavior of methods inherited from the **parent class**.

**Example 1: Basic Inheritance**

```python
# Parent class
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        print(f"{self.name} makes a sound")

# Child class inheriting from Animal
class Dog(Animal):
    def __init__(self, name, breed):
        # Call the constructor of the parent class
        super().__init__(name)
        self.breed = breed

    # Overriding the speak method
    def speak(self):
        print(f"{self.name} barks!")

# Creating an instance of the Dog class
dog = Dog("Buddy", "Golden Retriever")
dog.speak()  # Output: Buddy barks!
```

**Example 2: Multiple Inheritance**

In Python, a class can inherit from more than one class, which is known as **multiple inheritance**.

```python
# Parent class 1
class Printer:
    def print_document(self, document):
        print(f"Printing document: {document}")

# Parent class 2
class Scanner:
    def scan_document(self, document):
        print(f"Scanning document: {document}")

# Child class inheriting from both Printer and Scanner
class AllInOnePrinterScanner(Printer, Scanner):
    def copy_document(self, document):
        print(f"Copying document: {document}")

# Creating an instance of AllInOnePrinterScanner
device = AllInOnePrinterScanner()
device.print_document("Resume.pdf")  # Output: Printing document: Resume.pdf
device.scan_document("Report.pdf")  # Output: Scanning document: Report.pdf
device.copy_document("Invoice.pdf") # Output: Copying document: Invoice.pdf
```

### Key Points of Inheritance:
1. **Single Inheritance**: A child class inherits from a single parent class.
2. **Multiple Inheritance**: A child class can inherit from multiple parent classes (like the `AllInOnePrinterScanner` example).
3. **Method Overriding**: A child class can override methods from the parent class to provide specific implementations.
4. **`super()` Function**: The `super()` function allows a child class to call methods from its parent class, which can be useful for extending functionality without completely overriding it.


### 45. What are @classmethod and @staticmethod?

Both `@classmethod` and `@staticmethod` are used to define methods in a class that are not bound to instance-specific data. However, there are key differences in how they work and how they are used.

| **Aspect**             | **@classmethod**                                                                                             | **@staticmethod**                                                                                    |
|------------------------|------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| **Definition**          | A method that takes the class as the first argument instead of the instance. It can access class attributes and other class methods. | A method that doesn't take any special first argument (like `self` or `cls`). It cannot access or modify instance-specific or class-specific data. |
| **First Parameter**     | Takes `cls` (the class itself) as the first argument.                                                        | Does not take `self` (instance) or `cls` (class) as the first argument.                             |
| **Access to Class Data**| Can access and modify class-level attributes and methods.                                                   | Cannot access or modify class-level or instance-level attributes.                                  |
| **Usage**               | Used when you need to operate on class attributes or need to call other class methods.                      | Used when the method doesn't need to access or modify any instance-specific or class-specific data.  |
| **Inheritance Behavior**| A `@classmethod` is inherited by child classes and can be overridden.                                        | A `@staticmethod` is inherited by child classes, but cannot modify the behavior of the parent class. |
| **Example**             | Used when you need to modify or access class-level data, or when you want to call other class methods.      | Used when the method doesn't interact with class or instance data, and is just a utility function.  |

**Examples:**

**1. `@classmethod` Example**

```python
class Car:
    wheels = 4  # Class attribute

    def __init__(self, make, model):
        self.make = make
        self.model = model

    @classmethod
    def change_wheels(cls, new_wheel_count):
        cls.wheels = new_wheel_count  # Modify class attribute

    @classmethod
    def create_sports_car(cls, make, model):
        return cls(make, model)  # Factory method

# Accessing the class method
print(f"Default wheels: {Car.wheels}")
Car.change_wheels(6)  # Modifying class attribute through class method
print(f"Updated wheels: {Car.wheels}")

# Using the factory method to create an instance
car = Car.create_sports_car("Ferrari", "488")
print(f"Car make: {car.make}, model: {car.model}")
```

**Output:**
```
Default wheels: 4
Updated wheels: 6
Car make: Ferrari, model: 488
```

- `change_wheels`: A class method that modifies the class attribute `wheels` for all instances.
- `create_sports_car`: A factory method that uses the class method to create and return a new instance of the `Car` class.

**2. `@staticmethod` Example**

```python
class Math:
    
    @staticmethod
    def add(x, y):
        return x + y
    
    @staticmethod
    def subtract(x, y):
        return x - y

# Calling static methods without creating an instance
print(Math.add(10, 5))  # Output: 15
print(Math.subtract(10, 5))  # Output: 5
```

**Output:**
```
15
5
```

### 46. What is the purpose of __init__ in Python?

The `__init__` method in Python is a special method used to initialize a newly created object (instance) of a class. It is known as the **constructor** in Python. The purpose of `__init__` is to set the initial state of the object by assigning values to the object's attributes when it is created.

**Syntax:**
```python
class ClassName:
    def __init__(self, arg1, arg2, ...):
        # Initialize object attributes
        self.attribute1 = arg1
        self.attribute2 = arg2
        ...
```

**Example:**

```python
class Person:
    def __init__(self, name, age):
        # Initialize instance attributes
        self.name = name
        self.age = age

    def greet(self):
        print(f"Hello, my name is {self.name} and I am {self.age} years old.")

# Creating an instance of the Person class
person1 = Person("Alice", 30)

# Accessing object attributes and calling method
person1.greet()  # Output: Hello, my name is Alice and I am 30 years old.
```

**Explanation:**
1. **`__init__` Method**:
   - When we create an object `person1 = Person("Alice", 30)`, the `__init__` method is automatically invoked.
   - The `__init__` method takes two arguments, `name` and `age`, and assigns them to instance variables `self.name` and `self.age`.
   - The method doesn't return anything; it simply initializes the object’s state.

2. **Accessing Attributes**:
   - We can access the attributes `name` and `age` via the object `person1`.

**Important Notes:**
- **`self` parameter**: The first parameter of `__init__` is always `self`, which refers to the current instance of the class. It is used to access instance variables.
- **Constructor is not for creating instances**: While the `__init__` method initializes the object's attributes, the actual creation of the object is done by the Python runtime. You don't need to manually create an object; this is handled by calling the class name, e.g., `person1 = Person("Alice", 30)`.
- **Optional Arguments**: You can pass arguments to `__init__` to provide custom values when creating an instance.

**Example with Default Values:**

```python
class Book:
    def __init__(self, title="Unknown", author="Unknown"):
        self.title = title
        self.author = author

    def display_info(self):
        print(f"Title: {self.title}, Author: {self.author}")

# Creating instances with and without arguments
book1 = Book("1984", "George Orwell")
book2 = Book()

book1.display_info()  # Output: Title: 1984, Author: George Orwell
book2.display_info()  # Output: Title: Unknown, Author: Unknown
```

### 47. What are Python’s built-in exceptions?
Python provides a wide range of **built-in exceptions** that allow you to handle various errors in your programs. These exceptions are part of Python's standard library and are used to catch errors or exceptional conditions that arise during the execution of a program.

Here’s a list of some of the most commonly used built-in exceptions in Python:

1. **BaseException**:
   - The base class for all built-in exceptions.
   - All other exceptions in Python are derived from `BaseException`.

2. **Exception**:
   - The base class for most of the built-in exceptions, except for `SystemExit`, `KeyboardInterrupt`, and `GeneratorExit`.

3. **ArithmeticError**:
   - The base class for errors that occur in numeric calculations.
   - Includes exceptions like:
     - `ZeroDivisionError`: Raised when dividing by zero.
     - `OverflowError`: Raised when a calculation exceeds the maximum limit for a numeric type.
     - `FloatingPointError`: Raised when a floating point operation fails.

4. **AttributeError**:
   - Raised when an attribute reference or assignment fails (e.g., trying to access an attribute that doesn't exist).

5. **FileNotFoundError**:
   - Raised when trying to open a file that does not exist.

6. **IndexError**:
   - Raised when trying to access an element from a list or sequence using an invalid index (e.g., an index out of range).

7. **KeyError**:
   - Raised when trying to access a dictionary with a key that doesn't exist.

8. **NameError**:
   - Raised when a local or global name is not found.

9. **TypeError**:
   - Raised when an operation or function is applied to an object of inappropriate type.

10. **ValueError**:
   - Raised when a function receives an argument of the correct type but an inappropriate value (e.g., passing a negative number to a function that requires a positive one).

11. **RuntimeError**:
   - Raised when a generic error occurs that doesn't fall into other specific exceptions.

12. **IOError**:
   - Raised when an I/O operation (like reading or writing to a file) fails.

13. **ImportError**:
   - Raised when an import statement fails to find the module.

14. **MemoryError**:
   - Raised when a program runs out of memory.

15. **OverflowError**:
   - Raised when the result of an arithmetic operation is too large to be represented within the allowed range.

16. **StopIteration**:
   - Raised by the `next()` function when there are no further items to return from an iterator.

17. **KeyboardInterrupt**:
   - Raised when the user hits the interrupt key (usually Ctrl+C) during program execution.

18. **SyntaxError**:
   - Raised when the Python parser encounters invalid syntax.

19. **IndentationError**:
   - A subclass of `SyntaxError` raised when there are issues with indentation.

20. **NotImplementedError**:
   - Raised when an abstract method requires implementation in a subclass but has not been implemented.

21. **UnboundLocalError**:
   - A subclass of `NameError`, raised when a local variable is referenced before it is assigned a value.

22. **AssertionError**:
   - Raised when an `assert` statement fails (i.e., the expression being tested evaluates to `False`).

23. **RuntimeError**:
   - Raised when an error is detected that doesn’t fall into other categories, typically for unexpected situations during program execution.

24. **SystemExit**:
   - Raised when the `sys.exit()` function is called. This exception is used to terminate a program.

25. **TypeError**:
   - Raised when an operation or function is applied to an object of inappropriate type.

26. **UnicodeDecodeError**:
   - Raised when a `decode()` operation fails.

### 48. What is the difference between try-except and try-finally?

Both `try-except` and `try-finally` are used to handle exceptions in Python, but they serve different purposes and have different behaviors. Here’s a breakdown of the differences:

| **Aspect**            | **`try-except`**                                                                                           | **`try-finally`**                                                                                     |
|-----------------------|------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------|
| **Purpose**           | Used to catch exceptions that occur within the `try` block and handle them using the `except` block.       | Used to guarantee that certain code in the `finally` block is executed, whether or not an exception occurs. |
| **Exception Handling**| Catches specific exceptions or all exceptions that occur within the `try` block.                           | Does not catch exceptions. It ensures that the code in `finally` is executed, even if an exception occurs. |
| **When It Executes**  | The `except` block executes if an exception occurs in the `try` block. If no exception occurs, `except` is skipped. | The `finally` block always executes, whether or not an exception occurs in the `try` block. |
| **Flow**              | The program flow moves to the `except` block if an exception is raised, or it continues after the `try-except` block if no exception occurs. | The program flow always moves to the `finally` block after the `try` block, regardless of whether an exception occurs. |
| **Use Case**          | Use `try-except` when you want to handle or log exceptions in a specific way or recover from an error.       | Use `try-finally` when you want to ensure some code is executed (e.g., cleanup code like closing a file or releasing a resource) no matter what happens. |

**Key Points:**
- **`try-except`**: Useful when you want to catch specific exceptions, log them, or handle them in a particular way.
- **`try-finally`**: Ensures that certain code (such as cleanup or closing resources) is always executed, even if an exception occurs.
---
**Example: `try-except`**

```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
except ZeroDivisionError:
    print("Cannot divide by zero.")
except ValueError:
    print("Invalid input. Please enter a valid number.")
else:
    print(f"Result is {result}")
```

**Explanation:**
- If the user enters `0`, a `ZeroDivisionError` will be caught and handled by the corresponding `except` block.
- If the user enters a non-numeric value, a `ValueError` will be caught and handled.
- If no exception occurs, the `else` block will execute, and the result will be printed.
---
**Example: `try-finally`**

```python
def file_operations():
    file = None
    try:
        file = open("sample.txt", "r")
        # Read from the file
        content = file.read()
        print(content)
    finally:
        if file:
            file.close()  # Ensures the file is closed no matter what happens

file_operations()
```

**Explanation:**
- In the above example, the `finally` block ensures that the file is always closed, whether or not an exception occurs during reading.
- Even if an exception occurs (e.g., if the file is not found), the `finally` block will still execute and close the file if it was successfully opened.
---
**Example: `try-except-finally`**

```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
except ZeroDivisionError:
    print("Cannot divide by zero.")
except ValueError:
    print("Invalid input. Please enter a valid number.")
finally:
    print("Execution completed.")
```

**Explanation:**
- The `finally` block ensures that "Execution completed." is printed regardless of whether an exception was raised or not.


### 49. How do you raise an exception?
In Python, you can raise an exception using the `raise` keyword. This allows you to trigger an exception manually in your program, either as a custom error or based on certain conditions.

**Syntax:**
```python
raise ExceptionType("Error message")
```

- **ExceptionType**: This is the type of exception you want to raise (e.g., `ValueError`, `TypeError`, `CustomException`, etc.).
- **Error message** (optional): A string that provides additional information about the exception.
---
**Example 1: Raising a built-in exception**

```python
def check_age(age):
    if age < 18:
        raise ValueError("Age must be 18 or older")
    else:
        print("Age is valid")

try:
    check_age(15)
except ValueError as e:
    print(f"Error: {e}")
```

**Output:**
```
Error: Age must be 18 or older
```
---
**Example 2: Raising a custom exception**

You can also define your own exception class by subclassing the built-in `Exception` class:

```python
class AgeRestrictionError(Exception):
    def __init__(self, message):
        super().__init__(message)

def check_age(age):
    if age < 18:
        raise AgeRestrictionError("Age must be 18 or older")
    else:
        print("Age is valid")

try:
    check_age(16)
except AgeRestrictionError as e:
    print(f"Custom Error: {e}")
```

**Output:**
```
Custom Error: Age must be 18 or older
```
---
**Example 3: Raising an exception without a message**

If you want to raise an exception without an error message, you can simply do:

```python
def test_function(value):
    if value < 0:
        raise ValueError
    else:
        print("Value is valid")

try:
    test_function(-1)
except ValueError:
    print("Caught a ValueError!")
```

**Output:**
```
Caught a ValueError!
```
---
**Example of Re-raising an Exception:**

```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
except ZeroDivisionError as e:
    print(f"Error occurred: {e}")
    raise  # Re-raises the ZeroDivisionError
```

### 50. Explain the assert statement.

The `assert` statement in Python is used for debugging purposes. It tests if a condition is `True`, and if it isn't, it raises an `AssertionError` with an optional message. It helps in catching bugs early in the development process by ensuring that conditions you assume to be true actually hold true during runtime.

### Syntax:
```python
assert condition, message
```
### 51. How can you create a custom exception?
**Example 2: Raising a custom exception**

You can also define your own exception class by subclassing the built-in `Exception` class:

```python
class AgeRestrictionError(Exception):
    def __init__(self, message):
        super().__init__(message)

def check_age(age):
    if age < 18:
        raise AgeRestrictionError("Age must be 18 or older")
    else:
        print("Age is valid")

try:
    check_age(16)
except AgeRestrictionError as e:
    print(f"Custom Error: {e}")
```

**Output:**
```
Custom Error: Age must be 18 or older
```
### 52. How do you open a file in Python?

In Python, you can open a file using the built-in `open()` function. This function allows you to work with files for reading, writing, appending, and other operations. 

**Syntax:**
```python
file_object = open(file_name, mode)
```

- **file_name**: Name (and path, if not in the current directory) of the file you want to open.
- **mode**: A string specifying the mode in which the file is opened. This is optional and defaults to `'r'` (read mode).

**Common File Modes:**
| **Mode** | **Description**                                                                                     |
|----------|-----------------------------------------------------------------------------------------------------|
| `'r'`    | Opens the file for reading. Raises an error if the file does not exist.                             |
| `'w'`    | Opens the file for writing. Creates a new file if it doesn't exist or truncates the file if it exists. |
| `'a'`    | Opens the file for appending. Creates the file if it does not exist.                                |
| `'x'`    | Creates a new file. Raises an error if the file already exists.                                     |
| `'b'`    | Opens the file in binary mode.                                                                      |
| `'t'`    | Opens the file in text mode (default).                                                              |
| `'r+'`   | Opens the file for both reading and writing. Raises an error if the file does not exist.            |
| `'w+'`   | Opens the file for both writing and reading. Creates a new file or truncates an existing file.      |
| `'a+'`   | Opens the file for appending and reading. Creates the file if it does not exist.                    |

**Example 1: Reading a File**
```python
# Open a file in read mode
file = open("example.txt", "r")

# Read the content
content = file.read()
print(content)

# Close the file
file.close()
```
---
**Example 2: Writing to a File**
```python
# Open a file in write mode
file = open("example.txt", "w")

# Write content to the file
file.write("Hello, Python!")
file.close()
```

### 53. What is the difference between read() and readlines()?
The primary difference between `read()` and `readlines()` in Python lies in **how they read data from a file** and the format of the output.

| **Feature**              | **`read()`**                              | **`readlines()`**                             |
|--------------------------|--------------------------------------------|-----------------------------------------------|
| **Purpose**              | Reads the entire content as a single string. | Reads the file content as a list of lines.    |
| **Output**               | A single string.                          | A list of strings, one for each line.         |
| **Use Case**             | When you want the whole content at once.  | When you need line-by-line processing.        |
| **Newline Characters**   | Preserved within the single string.        | Preserved in each list element (unless stripped). |

### 54. What is the purpose of the with statement?
> Refer 18th questions.
### 55. How do you handle binary files in Python?
### 56. What are the file modes in Python?
> Refer 52nd questions.
### 57. What are Python’s magic methods?
**Answer:** Methods with double underscores like __str__, __repr__, __add__.
### 58. What is monkey patching in Python?
**Answer:** Modifying a class or module at runtime.
### 59. What is Python’s yield keyword?
**Answer:** Used in generator functions to return a value without terminating the function.
### 60. How does Python implement multithreading?
### 61. What are coroutines in Python?
### 62. How do you use NumPy for array operations?
### 63. What is the use of pandas in Python?
### 64. Explain how Matplotlib can be used for plotting graphs.
### 65. How does the requests library simplify HTTP operations?
### 66. What is Flask and how is it different from Django?
### 67. How do you perform unit testing in Python?
### 68. What is the unittest module?
### 69. Explain pytest and its advantages.
### 70. What are fixtures in pytest?
### 71. How do you mock objects in Python tests?
### 72. How can you optimize Python code for performance?
### 73. What are Python’s profiling tools?
### 74. How do you handle memory leaks in Python?
### 75. What is the difference between cProfile and line_profiler?
### 76. What are Python’s built-in optimization techniques?
### 77. How do you reverse a list in place?
### 78. Reversing a List in Place in Python

Reversing a list "in place" means modifying the original list without creating a new list. Python provides several ways to achieve this:


**Method 1: Using the `reverse()` Method**

The `reverse()` method reverses the list in place without returning a new list.

```python
# Example
numbers = [1, 2, 3, 4, 5]
numbers.reverse()
print(numbers)  # Output: [5, 4, 3, 2, 1]
```

**Explanation**:
- The `reverse()` method modifies the original list directly.
- No additional memory is used for a new list.

---

**Method 2: Using Slicing**

You can reverse a list in place using slicing with the `[::-1]` syntax.

```python
# Example
numbers = [1, 2, 3, 4, 5]
numbers[:] = numbers[::-1]
print(numbers)  # Output: [5, 4, 3, 2, 1]
```

**Explanation**:
- `[::-1]` creates a reversed copy of the list.
- `numbers[:] =` ensures the original list is updated in place.

---

**Method 3: Using a Two-Pointer Approach**

This method swaps elements in the list from the start and end, moving towards the center.

```python
# Example
numbers = [1, 2, 3, 4, 5]
left, right = 0, len(numbers) - 1

while left < right:
    numbers[left], numbers[right] = numbers[right], numbers[left]
    left += 1
    right -= 1

print(numbers)  # Output: [5, 4, 3, 2, 1]
```

**Explanation**:
- Two pointers (`left` and `right`) are used to swap elements until they meet at the center.
- This approach modifies the list in place without any additional memory.

### 79.Write a Python program to merge two dictionaries.

**Method 1: Using the `update()` Method**
The `update()` method merges two dictionaries, modifying the first dictionary in place.

```python
# Example
dict1 = {'a': 1, 'b': 2}
dict2 = {'c': 3, 'd': 4}

# Merging using update()
dict1.update(dict2)
print("Merged dictionary:", dict1)
```

**Output**:
```
Merged dictionary: {'a': 1, 'b': 2, 'c': 3, 'd': 4}
```
---
**Method 2: Using the `**` Unpacking Operator**
Python allows merging dictionaries using the unpacking operator `**`.

```python
# Example
dict1 = {'a': 1, 'b': 2}
dict2 = {'c': 3, 'd': 4}

# Merging using **
merged_dict = {**dict1, **dict2}
print("Merged dictionary:", merged_dict)
```

**Output**:
```
Merged dictionary: {'a': 1, 'b': 2, 'c': 3, 'd': 4}
```
---
**Method 3: Using the `|` Operator (Python 3.9+)**
From Python 3.9 onward, you can use the `|` operator to merge dictionaries.

```python
# Example
dict1 = {'a': 1, 'b': 2}
dict2 = {'c': 3, 'd': 4}

# Merging using |
merged_dict = dict1 | dict2
print("Merged dictionary:", merged_dict)
```

**Output**:
```
Merged dictionary: {'a': 1, 'b': 2, 'c': 3, 'd': 4}
```

---

**Method 4: Using a Loop**
If you need more control, you can merge dictionaries manually using a loop.

```python
# Example
dict1 = {'a': 1, 'b': 2}
dict2 = {'c': 3, 'd': 4}

# Merging using a loop
merged_dict = dict1.copy()  # Start with a copy of dict1
for key, value in dict2.items():
    merged_dict[key] = value

print("Merged dictionary:", merged_dict)
```

**Output**:
```
Merged dictionary: {'a': 1, 'b': 2, 'c': 3, 'd': 4}
```

### 80. How do you find duplicates in a list?

Here are several ways to find duplicates in a list:

---

**Method 1: Using a `set` and `for` Loop**

```python
# Example
numbers = [1, 2, 3, 4, 5, 2, 3, 6]

duplicates = set()
seen = set()

for num in numbers:
    if num in seen:
        duplicates.add(num)
    else:
        seen.add(num)

print("Duplicates:", duplicates)
```

**Output**:
```
Duplicates: {2, 3}
```

**Explanation**:
- `seen` keeps track of unique elements.
- If an element is already in `seen`, it is added to `duplicates`.

---

**Method 2: Using `collections.Counter`**

The `Counter` class from the `collections` module counts the occurrences of each element.

```python
from collections import Counter

# Example
numbers = [1, 2, 3, 4, 5, 2, 3, 6]

counter = Counter(numbers)
duplicates = [item for item, count in counter.items() if count > 1]

print("Duplicates:", duplicates)
```

**Output**:
```
Duplicates: [2, 3]
```

**Explanation**:
- `Counter` creates a dictionary-like object with elements as keys and their counts as values.
- A list comprehension filters out elements that appear more than once.

---

**Method 3: Using `set` Comprehension**

```python
# Example
numbers = [1, 2, 3, 4, 5, 2, 3, 6]

duplicates = {num for num in numbers if numbers.count(num) > 1}

print("Duplicates:", duplicates)
```

**Output**:
```
Duplicates: {2, 3}
```

**Explanation**:
- `numbers.count(num)` counts occurrences of each element.
- A set comprehension ensures no duplicate values in the result.

---

**Method 4: Using `pandas` (For Larger Datasets)**

If you are dealing with large datasets, `pandas` provides an efficient way to find duplicates.

```python
import pandas as pd

# Example
numbers = [1, 2, 3, 4, 5, 2, 3, 6]

duplicates = pd.Series(numbers).duplicated(keep=False)
result = pd.Series(numbers)[duplicates].unique()

print("Duplicates:", result)
```

**Output**:
```
Duplicates: [2 3]
```

**Explanation**:
- `pd.Series.duplicated()` returns a boolean mask for duplicate elements.
- `.unique()` extracts unique duplicate values.

### 81. Write a program to check if a string is a palindrome.

```python
def is_palindrome(string):
    # Remove non-alphanumeric characters and convert to lowercase
    clean_string = ''.join(char.lower() for char in string if char.isalnum())
    
    # Check if the string reads the same forward and backward
    return clean_string == clean_string[::-1]

# Test the function
test_string = input("Enter a string to check if it's a palindrome: ")
if is_palindrome(test_string):
    print(f'"{test_string}" is a palindrome!')
else:
    print(f'"{test_string}" is not a palindrome.')
```

### 82. How do you count the frequency of elements in a list?
To count the frequency of elements in a list, Python provides several methods, ranging from simple loops to built-in functions and libraries. Here are some common approaches:

---

**Method 1: Using `collections.Counter`**
The `collections.Counter` class is the most efficient and readable way to count the frequency of elements.

```python
from collections import Counter

# Example
numbers = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4]

frequency = Counter(numbers)
print(frequency)
```

**Output**:
```
Counter({4: 4, 3: 3, 2: 2, 1: 1})
```

**Explanation**:
- The `Counter` object is a dictionary-like structure where keys are elements and values are their counts.

---

**Method 2: Using a `for` Loop**
Manually counting the frequency using a loop.

```python
# Example
numbers = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4]

frequency = {}
for num in numbers:
    frequency[num] = frequency.get(num, 0) + 1

print(frequency)
```

**Output**:
```
{1: 1, 2: 2, 3: 3, 4: 4}
```

**Explanation**:
- The `get()` method is used to handle missing keys, initializing counts to `0`.

---

**Method 3: Using a Dictionary Comprehension**
A concise way to calculate frequencies.

```python
# Example
numbers = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4]

frequency = {num: numbers.count(num) for num in set(numbers)}
print(frequency)
```

**Output**:
```
{1: 1, 2: 2, 3: 3, 4: 4}
```

**Explanation**:
- `set(numbers)` ensures each element is counted only once.
- The `count()` method counts occurrences of each element.

---

**Method 4: Using `pandas` (For Larger Datasets)**
If you're working with large datasets, `pandas` is efficient.

```python
import pandas as pd

# Example
numbers = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4]

frequency = pd.Series(numbers).value_counts()
print(frequency)
```

**Output**:
```
4    4
3    3
2    2
1    1
dtype: int64
```

**Explanation**:
- `value_counts()` returns a sorted frequency count.

### 83. Write a function to calculate the factorial of a number.

**Factorial Function**

```python
def factorial(n):
    # Check for non-negative integers
    if n < 0:
        return "Factorial is not defined for negative numbers"
    
    result = 1
    for i in range(1, n + 1):
        result *= i
    return result

# Test the function
number = int(input("Enter a number to calculate its factorial: "))
print(f"The factorial of {number} is {factorial(number)}")
```

---

**Input:**
```
Enter a number to calculate its factorial: 5
```

**Output:**
```
The factorial of 5 is 120
```

**Input:**
```
Enter a number to calculate its factorial: 0
```

**Output:**
```
The factorial of 0 is 1
```

---

**Alternative Method: Using Recursion**

You can also calculate the factorial recursively:

```python
def factorial_recursive(n):
    # Check for non-negative integers
    if n < 0:
        return "Factorial is not defined for negative numbers"
    elif n == 0 or n == 1:
        return 1
    else:
        return n * factorial_recursive(n - 1)

# Test the function
number = int(input("Enter a number to calculate its factorial: "))
print(f"The factorial of {number} is {factorial_recursive(number)}")
```

### 84. Find the longest substring without repeating characters.
To find the longest substring without repeating characters, you can use the **sliding window technique** with a hash set or dictionary to keep track of characters that have already been seen.

**Python Code:**

```python
def longest_substring_without_repeating_chars(s):
    # Dictionary to store the last index of each character
    char_map = {}
    left = 0
    max_len = 0
    
    # Iterate over the string with the right pointer
    for right in range(len(s)):
        # If the character is already in the window, move the left pointer
        if s[right] in char_map and char_map[s[right]] >= left:
            left = char_map[s[right]] + 1
        
        # Update the last index of the character
        char_map[s[right]] = right
        
        # Calculate the maximum length of the substring
        max_len = max(max_len, right - left + 1)
    
    return max_len

# Test the function
input_string = input("Enter a string: ")
print(f"The length of the longest substring without repeating characters is: {longest_substring_without_repeating_chars(input_string)}")
```

### 85. Write a Python program to flatten a nested list.
To flatten a nested list in Python (i.e., convert a list of lists into a single list with all the elements), you can use a recursive approach or iteration to handle nested structures. Here’s a Python program to flatten a nested list using both methods:

---

**Method 1: Using Recursion**

```python
def flatten(nested_list):
    flattened_list = []
    for item in nested_list:
        if isinstance(item, list):
            flattened_list.extend(flatten(item))  # Recursively flatten nested lists
        else:
            flattened_list.append(item)
    return flattened_list

# Test the function
nested_list = [1, [2, 3], [4, [5, 6]], 7]
print(f"Flattened list: {flatten(nested_list)}")
```

---

**Explanation:**
1. The function checks if the current item is a list using `isinstance(item, list)`.
2. If the item is a list, it recursively flattens that sublist and adds the result to the flattened list.
3. If the item is not a list, it appends it directly to the result.

---

**Method 2: Using Iteration with a Stack**

```python
def flatten_iterative(nested_list):
    flattened_list = []
    stack = nested_list[::-1]  # Start with the reversed list
    while stack:
        item = stack.pop()
        if isinstance(item, list):
            stack.extend(item[::-1])  # Add the elements of the nested list to the stack in reverse order
        else:
            flattened_list.append(item)
    return flattened_list

# Test the function
nested_list = [1, [2, 3], [4, [5, 6]], 7]
print(f"Flattened list (iterative): {flatten_iterative(nested_list)}")
```

---

**Explanation:**
1. A stack is initialized with the reversed input list to maintain the order of the elements.
2. The while loop pops elements from the stack and checks if they are lists.
3. If it is a list, the elements of the list are added to the stack in reverse order (so the first item appears first when popped).
4. If it is not a list, it is added to the flattened result.

### 86. How do you sort a dictionary by its values?
To sort a dictionary by its values, you can use the `sorted()` function in Python, which allows you to specify a custom sorting key. Here's how you can do it:

---

**Method 1: Using `sorted()` and a Lambda Function**

```python
def sort_dict_by_values(input_dict):
    # Sort dictionary by value and return the sorted items as a list of tuples
    sorted_dict = sorted(input_dict.items(), key=lambda x: x[1])
    return dict(sorted_dict)

# Test the function
input_dict = {'apple': 10, 'banana': 2, 'orange': 5, 'mango': 7}
sorted_dict = sort_dict_by_values(input_dict)
print(f"Sorted dictionary by values: {sorted_dict}")
```

---


**Method 2: Sorting in Descending Order**

If you want to sort the dictionary by values in descending order, you can set the `reverse=True` parameter in the `sorted()` function:

```python
def sort_dict_by_values_desc(input_dict):
    # Sort dictionary by value in descending order and return the sorted items as a list of tuples
    sorted_dict = sorted(input_dict.items(), key=lambda x: x[1], reverse=True)
    return dict(sorted_dict)

# Test the function
input_dict = {'apple': 10, 'banana': 2, 'orange': 5, 'mango': 7}
sorted_dict = sort_dict_by_values_desc(input_dict)
print(f"Sorted dictionary by values (descending): {sorted_dict}")
```

### 87. Write a Python program to check for balanced parentheses.
To check for balanced parentheses in a string, we can use a **stack** data structure. Here's the approach:

**Approach:**
1. Traverse the string character by character.
2. If the character is an opening parenthesis (`(`, `{`, or `[`), push it onto the stack.
3. If it's a closing parenthesis (`)`, `}`, or `]`), check if it matches the top element of the stack:
   - If it matches, pop the stack.
   - If it doesn't match or the stack is empty, the parentheses are unbalanced.
4. Finally, if the stack is empty, all parentheses are balanced; otherwise, they are unbalanced.

---

**Python Program:**

```python
def is_balanced(expression):
    # Dictionary to match opening and closing parentheses
    parentheses_map = {')': '(', '}': '{', ']': '['}
    stack = []

    # Traverse through each character in the expression
    for char in expression:
        if char in parentheses_map.values():  # If the character is an opening parenthesis
            stack.append(char)
        elif char in parentheses_map.keys():  # If the character is a closing parenthesis
            # Check if the stack is empty or the top of the stack doesn't match
            if not stack or stack.pop() != parentheses_map[char]:
                return False
    # If the stack is empty, all parentheses matched; otherwise, it's unbalanced
    return not stack

# Test the function
expression = input("Enter an expression: ")
if is_balanced(expression):
    print("The parentheses are balanced.")
else:
    print("The parentheses are not balanced.")
```

### 88. What are Python’s popular IDEs?
### 89. How is Python used in machine learning?
### 90. What is Python’s role in web development?
### 91. Explain Python’s role in data science.
### 92. How does Python integrate with databases?
### 93. Explain how Python handles large files.
### 94. What is the use of the multiprocessing module?
### 95. How do you implement a cache in Python?
### 96. What is the purpose of the inspect module?
### 97. How does Python work with JSON data?
### 99. Write a Python program to find the GCD of two numbers.
To find the **Greatest Common Divisor (GCD)** of two numbers, we can use **Euclid's Algorithm**, which is efficient and works as follows:

**Approach (Euclid’s Algorithm):**
1. If `b` is 0, then the GCD is `a`.
2. Otherwise, calculate `gcd(a, b) = gcd(b, a % b)` recursively until `b` becomes 0.

---

**Python Program to Find the GCD:**

```python
def gcd(a, b):
    while b:
        a, b = b, a % b  # Swap and take the remainder
    return a

# Test the function
num1 = int(input("Enter the first number: "))
num2 = int(input("Enter the second number: "))

print(f"The GCD of {num1} and {num2} is: {gcd(num1, num2)}")
```

---

**Explanation:**
1. The function `gcd(a, b)` uses a `while` loop to repeatedly compute the remainder (`a % b`) until `b` becomes zero. At that point, `a` will hold the GCD.
2. The loop continues swapping the values of `a` and `b` until the second number (`b`) becomes zero.
3. The GCD is the value of `a` when `b` becomes zero.

### 100. Implement a queue using two stacks.
To implement a **queue** using two **stacks**, we can simulate the queue's behavior by using two stacks: `stack1` for enqueuing elements and `stack2` for dequeuing elements. The key idea is:

1. **Enqueue Operation**: Push the new element onto `stack1`.
2. **Dequeue Operation**: If `stack2` is empty, move all elements from `stack1` to `stack2`, then pop the element from `stack2`. This ensures that the elements are dequeued in the correct order (FIFO).

**Python Program to Implement Queue Using Two Stacks:**

```python
class QueueUsingTwoStacks:
    def __init__(self):
        # Initialize two stacks
        self.stack1 = []
        self.stack2 = []

    def enqueue(self, item):
        # Push item onto stack1
        self.stack1.append(item)

    def dequeue(self):
        # If both stacks are empty, the queue is empty
        if not self.stack1 and not self.stack2:
            print("Queue is empty")
            return None

        # If stack2 is empty, move elements from stack1 to stack2
        if not self.stack2:
            while self.stack1:
                self.stack2.append(self.stack1.pop())
        
        # Pop and return the element from stack2
        return self.stack2.pop()

    def peek(self):
        # Get the front element without removing it
        if not self.stack1 and not self.stack2:
            print("Queue is empty")
            return None
        if not self.stack2:
            while self.stack1:
                self.stack2.append(self.stack1.pop())
        return self.stack2[-1]

    def is_empty(self):
        # Return whether the queue is empty
        return not self.stack1 and not self.stack2

# Test the Queue
queue = QueueUsingTwoStacks()

# Enqueue elements
queue.enqueue(10)
queue.enqueue(20)
queue.enqueue(30)

print("Dequeue:", queue.dequeue())  # Output: 10
print("Dequeue:", queue.dequeue())  # Output: 20

# Peek front element
print("Front element:", queue.peek())  # Output: 30

# Enqueue more elements
queue.enqueue(40)
queue.enqueue(50)

print("Dequeue:", queue.dequeue())  # Output: 30
print("Dequeue:", queue.dequeue())  # Output: 40
print("Dequeue:", queue.dequeue())  # Output: 50
```

---

**Explanation:**
1. **`enqueue(item)`**: Pushes the item onto `stack1`, which handles all insertions.
2. **`dequeue()`**: If `stack2` is empty, we transfer all elements from `stack1` to `stack2` (this reverses the order). Then, we pop the top item from `stack2` to dequeue the element in FIFO order.
3. **`peek()`**: Checks the front element without removing it. If `stack2` is empty, we transfer elements from `stack1` to `stack2` and return the top of `stack2`.
4. **`is_empty()`**: Checks if both stacks are empty, indicating the queue is empty.

### 101. Write a function to find all permutations of a string.
To find all permutations of a string, we can use **backtracking** or **recursion**. Python provides a built-in method `itertools.permutations()` that can be used to find permutations, but we'll also implement a custom recursive function to generate all permutations manually.

**Recursive Approach:**
1. We will swap each character of the string and recursively find permutations of the remaining substring.
2. Once all characters are swapped, we add the permutation to the result.

---

**Python Program to Find All Permutations of a String:**

```python
def get_permutations(s):
    # List to store the permutations
    permutations = []

    # Helper function to generate permutations recursively
    def permute(s_list, start):
        # Base case: if we reach the end of the string, add the permutation
        if start == len(s_list):
            permutations.append(''.join(s_list))
            return
        
        # Recursively generate permutations by swapping each character
        for i in range(start, len(s_list)):
            s_list[start], s_list[i] = s_list[i], s_list[start]  # Swap
            permute(s_list, start + 1)  # Recursively permute the rest
            s_list[start], s_list[i] = s_list[i], s_list[start]  # Backtrack (swap back)

    # Convert the string into a list of characters for easier manipulation
    permute(list(s), 0)
    return permutations

# Test the function
input_string = input("Enter a string: ")
result = get_permutations(input_string)
print(f"All permutations of the string are: {result}")
```

---

**Explanation:**
1. **Base Case**: When `start` reaches the end of the string (i.e., `start == len(s_list)`), we join the list of characters into a string and add it to the `permutations` list.
2. **Recursive Step**: For each character in the string (from index `start` to the end), we swap it with the character at `start` and recursively generate permutations for the remaining substring. After the recursion, we swap back the characters (backtracking) to restore the string to its original state for the next iteration.

---

**Example:**

**Input:**
```
Enter a string: ABC
```

**Output:**
```
All permutations of the string are: ['ABC', 'ACB', 'BAC', 'BCA', 'CAB', 'CBA']
```

### 102. How do you generate a random password in Python?
To generate a random password in Python, you can use the `random` module along with the `string` module to select characters from a pool of uppercase letters, lowercase letters, digits, and special characters.

### **Approach:**
1. Use the `string` module to define sets of characters for uppercase, lowercase, digits, and special characters.
2. Use the `random.choice()` function to randomly select characters from these sets.
3. Combine the selected characters to form the password.

---

**Python Program to Generate a Random Password:**

```python
import random
import string

def generate_random_password(length=12):
    # Define the character sets
    all_characters = string.ascii_letters + string.digits + string.punctuation
    
    # Randomly select characters from the set
    password = ''.join(random.choice(all_characters) for _ in range(length))
    
    return password

# Test the function
password_length = int(input("Enter the desired password length: "))
random_password = generate_random_password(password_length)
print(f"Generated random password: {random_password}")
```

---

**Explanation:**
1. **Character Set**: We use `string.ascii_letters` (which includes both lowercase and uppercase letters), `string.digits` (which includes digits), and `string.punctuation` (which includes special characters).
2. **Password Generation**: We randomly select characters from the combined set using `random.choice()` and join them into a string of the desired length.
3. **Password Length**: The function allows you to specify the desired password length. The default is 12 characters.

---

**Example:**

**Input:**
```
Enter the desired password length: 16
```

**Output:**
```
Generated random password: A4h!jP&8fD#qJzK9
```

### 103. Write a Python program to validate an email address.
To validate an email address in Python, you can use regular expressions (regex). A valid email generally follows the format `local_part@domain.com`. We'll use the `re` module to match an email against a regex pattern.

**Regex Pattern for Email Validation:**
The regex pattern for a simple email address validation can be as follows:
- **Local part**: Can contain letters, digits, underscores, hyphens, and periods.
- **Domain part**: Can contain letters and periods.
- **Top-level domain**: Typically, 2-4 alphabetic characters.

Here's a simple Python program that validates an email address using regex.

---

**Python Program to Validate an Email Address:**

```python
import re

def validate_email(email):
    # Define the regex pattern for validating an email
    pattern = r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$'
    
    # Use re.match to check if the email matches the pattern
    if re.match(pattern, email):
        return True
    else:
        return False

# Test the function
email = input("Enter the email address: ")
if validate_email(email):
    print("Valid email address")
else:
    print("Invalid email address")
```

---

**Explanation:**
1. **Regex pattern breakdown**:
   - `^[a-zA-Z0-9._%+-]+`: Matches the local part of the email (before the `@` symbol). It allows alphanumeric characters and some special characters like `.`, `_`, `%`, `+`, and `-`.
   - `@`: This matches the literal `@` symbol.
   - `[a-zA-Z0-9.-]+`: Matches the domain part (after `@`). It allows alphanumeric characters, hyphens, and periods.
   - `\.[a-zA-Z]{2,4}$`: Matches the top-level domain (after the `.`). It allows 2 to 4 alphabetic characters.
   
2. **re.match()**: This function checks if the given email matches the specified regex pattern. If it does, the email is valid; otherwise, it is invalid.

---

**Example Runs:**

**Input 1:**
```
Enter the email address: user@example.com
```
**Output 1:**
```
Valid email address
```

**Input 2:**
```
Enter the email address: user@.com
```
**Output 2:**
```
Invalid email address
```

