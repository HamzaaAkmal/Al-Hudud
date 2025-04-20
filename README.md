

---



Let's go through the topics.

---

**1. Lambda Expressions**

*   **Simple Definition (English):** A lambda function is a small, anonymous function that can have any number of arguments but can only have one expression. They are often used for short operations where a full `def` function is not needed.
*   **Examples:**

    ```python
    # Example 1: Simple lambda to calculate square
    square = lambda x: x * x
    print(square(7)) # Output: 49

    # Example 2: Lambda with filter() to get numbers greater than 10 from a list
    numbers = [5, 12, 8, 20, 3]
    filtered_list = list(filter(lambda num: num > 10, numbers))
    print(filtered_list) # Output: [12, 20]

    # Example 3: Lambda with map() to add a prefix to each string in a list
    ids = [101, 102, 103]
    prefixed_ids = list(map(lambda id: "ID_" + str(id), ids))
    print(prefixed_ids) # Output: ['ID_101', 'ID_102', 'ID_103']
    ```

*   **Practice Questions (English):**
    1.  Write a lambda function to check if a number is even.
    2.  Use `map()` with a lambda function to convert a list of strings to integers.
    3.  Use `filter()` with a lambda function to find all strings in a list that contain the letter 'a'.

---

**2. List Comprehension**

*   **Simple Definition (English):** List comprehension is a concise way to create lists. It offers a shorter syntax when you want to create a new list based on the values of an existing list (or other iterable) or generate a new list based on a sequence.
*   **Examples:**

    ```python
    # Example 1: Create a list of even numbers from a range
    even_numbers = [x for x in range(21) if x % 2 == 0]
    print(even_numbers) # Output: [0, 2, 4, ..., 20]

    # Example 2: Create a list of lengths of words in a sentence
    sentence = "This is a sample sentence"
    word_lengths = [len(word) for word in sentence.split()]
    print(word_lengths) # Output: [4, 2, 1, 6, 8]

    # Example 3: Create a list of tuples (number, cube)
    number_cubes = [(num, num**3) for num in range(1, 6)]
    print(number_cubes) # Output: [(1, 1), (2, 8), (3, 27), (4, 64), (5, 125)]
    ```

*   **Practice Questions (English):**
    1.  Use list comprehension to create a list of vowels from a given string.
    2.  Use list comprehension to create a list of squares of only the odd numbers in a given list.
    3.  Use list comprehension to flatten a list of lists (e.g., `[[1, 2], [3, 4], [5, 6]]` becomes `[1, 2, 3, 4, 5, 6]`).

---

**3. Filter Function**

*   **Simple Definition (English):** The `filter()` function is used to construct an iterator from elements of an iterable for which a function returns true. It filters the iterable based on a function's condition.
*   **Examples:**

    ```python
    # Example 1: Filter numbers less than 10
    numbers = [15, 8, 22, 4, 11, 18]
    def less_than_ten(x):
      return x < 10
    filtered_list = list(filter(less_than_ten, numbers))
    print(filtered_list) # Output: [8, 4]

    # Example 2: Filter empty strings from a list
    string_list = ["hello", "", "world", " "]
    # The filter function treats empty strings, 0, None, etc. as False by default
    filtered_strings = list(filter(None, string_list))
    print(filtered_strings) # Output: ['hello', 'world', ' ']
    ```

*   **Practice Questions (English):**
    1.  Use `filter()` to get all strings from a list that have a length greater than 3.
    2.  Use `filter()` to get all prime numbers from a given list (you'll need a function to check for primality).

---

**4. Map Function**

*   **Simple Definition (English):** The `map()` function applies a given function to each item of an iterable (like a list or tuple) and returns an iterator of the results. It is used for transforming elements.
*   **Examples:**

    ```python
    # Example 1: Map function to convert strings to integer
    string_numbers = ["1", "2", "3", "4"]
    integer_numbers = list(map(int, string_numbers))
    print(integer_numbers) # Output: [1, 2, 3, 4]

    # Example 2: Map function to double each number
    numbers = [10, 20, 30]
    def double(x):
      return x * 2
    doubled_numbers = list(map(double, numbers))
    print(doubled_numbers) # Output: [20, 40, 60]

    # Example 3: Map with multiple lists (adding elements pairwise)
    list1 = [1, 2, 3]
    list2 = [10, 20, 30]
    sum_list = list(map(lambda x, y: x + y, list1, list2))
    print(sum_list) # Output: [11, 22, 33]
    ```

*   **Practice Questions (English):**
    1.  Use `map()` to convert a list of names to uppercase.
    2.  Use `map()` to calculate the area of circles given a list of radii (Area = pi * radius^2).

---

**5. Generators**

*   **Simple Definition (English):** Generators are functions that return an iterator. They use the `yield` keyword instead of `return`. When a generator function is called, it returns a generator object but doesn't start execution immediately. Execution starts when a method like `next()` or `__next__()` is called on the generator object, or when it's used in a loop. They pause execution at `yield`, saving their state, and resume from there on the next call. This makes them memory efficient for large sequences.
*   **Examples:**

    ```python
    # Example 1: A simple counting generator
    def count_up_to(n):
      i = 1
      while i <= n:
        yield i # Pause and yield value
        i += 1

    # Using the generator
    counter = count_up_to(5)
    print(next(counter)) # Output: 1
    print(next(counter)) # Output: 2
    for num in counter: # Continues from where it left off
      print(num)
    # Output:
    # 3
    # 4
    # 5

    # Example 2: Generator to produce squares
    def square_generator(n):
        for i in range(n):
            yield i * i

    for sq in square_generator(4):
        print(sq)
    # Output:
    # 0
    # 1
    # 4
    # 9
    ```

*   **Practice Questions (English):**
    1.  Write a generator function that yields the Fibonacci sequence up to a certain limit.
    2.  Write a generator function that takes a list and yields each element one by one.

---

**How `if/else` Conditions Work**

*   **Simple Definition (English):** Conditional statements (`if`, `elif`, `else`) are used to perform different actions based on different conditions. They allow your program to make decisions.
    *   `if`: Executes a block of code if the condition is True.
    *   `elif` (else if): Checks another condition if the preceding `if` or `elif` conditions were False. You can have multiple `elif` blocks.
    *   `else`: Executes a block of code if none of the `if` or `elif` conditions are True. It is optional.
*   **Structure:** The general structure involves the `if` keyword, followed by a condition, a colon `:`, and then an indented block of code. `elif` and `else` follow a similar structure, aligning with the `if`.
*   **Examples:**

    ```python
    # Example 1: Basic if/else
    score = 75
    if score >= 60:
      print("Passed")
    else:
      print("Failed")
    # Output: Passed

    # Example 2: Using elif
    grade = 85
    if grade >= 90:
      print("Grade: A")
    elif grade >= 80:
      print("Grade: B")
    elif grade >= 70:
      print("Grade: C")
    else:
      print("Grade: D or below")
    # Output: Grade: B
    ```
*   **Using `if/else` in OOP (e.g., Validation in a Setter):**

    ```python
    class Person:
        def __init__(self, name, age):
            self.name = name
            self._age = None # Use protected convention internally
            self.age = age # Use the setter for initial assignment

        @property
        def age(self):
            print("Getting age...")
            return self._age

        @age.setter
        def age(self, value):
            print(f"Setting age to {value}...")
            # Using if/else for validation
            if isinstance(value, int) and value >= 0:
                self._age = value
            else:
                print("Warning: Age must be a non-negative integer. Setting age to 0.")
                self._age = 0 # Default or error value

    # Example usage
    p1 = Person("Alice", 30)
    print(f"{p1.name}'s age is {p1.age}") # Calls getter

    p1.age = 35 # Calls setter (valid)
    print(f"{p1.name}'s age is {p1.age}")

    p1.age = -5 # Calls setter (invalid)
    print(f"{p1.name}'s age is {p1.age}")

    p1.age = "twenty" # Calls setter (invalid type)
    print(f"{p1.name}'s age is {p1.age}")
    ```

*   **Practice Questions (English):**
    1.  Write a function that takes a number and uses `if/elif/else` to return "Positive", "Negative", or "Zero".
    2.  In a `Student` class, write a method `set_gpa(self, gpa)` that uses `if/else` to validate that the GPA is between 0.0 and 4.0 (inclusive). If valid, set the internal `_gpa` attribute; otherwise, print an error message.

---

**OOP Core Concepts (Class, Object, self, Constructor, Destructor, Encapsulation, Variables, Methods, Static Members)**

*   **Simple Definitions (English):**
    *   **Class:** A blueprint or template for creating objects. It defines the attributes (data) and methods (behavior) that objects of that class will have.
    *   **Object:** An instance of a class. When you create an object, you are creating a specific entity based on the class blueprint.
    *   `self`: In a class method, `self` refers to the *instance* of the class itself. It is the first parameter in instance method definitions and allows access to the object's attributes and methods.
    *   `__init__` (Constructor): A special method automatically called when a new object (instance) of the class is created. It is used to initialize the object's attributes.
    *   `__del__` (Destructor): A special method called when an object is about to be destroyed or garbage-collected. Less commonly used in Python due to automatic memory management.
    *   **Encapsulation:** The bundling of data (attributes) and the methods that operate on that data into a single unit (a class). It's used to hide the internal state of an object and prevent direct access to attributes from outside the class, controlling access only through methods. In Python, conventions (`_` for protected) and name mangling (`__` for 'private') are used.
    *   **Instance Variable:** A variable whose value is specific to a particular *instance* (object) of a class. Each object has its own copy. Accessed via `self.variable_name`.
    *   **Class Variable:** A variable that is shared among *all* instances (objects) of a class. Defined directly within the class but outside any methods. Accessed via `ClassName.variable_name` or `self.variable_name` (though ClassName is preferred for clarity).
    *   **Instance Method:** A method that operates on the data specific to an *instance* (object). It takes `self` as its first parameter.
    *   **Class Method:** A method that operates on the class itself, rather than an instance. It takes `cls` (conventionally) as its first parameter and is marked with the `@classmethod` decorator. Often used for alternative constructors.
    *   **Static Method:** A method that belongs to the class but does not operate on either the instance (`self`) or the class (`cls`). It's like a regular function placed inside a class because it's conceptually related to the class. Marked with the `@staticmethod` decorator.

*   **Examples (using Person/Student):**

    ```python
    # Example 1: Basic Class, Object, init, self, Instance/Class Variables/Methods
    class Person:
        # Class Variable (shared by all instances)
        species = "Human"

        # Constructor
        def __init__(self, name, age):
            print(f"A new Person object is being created for {name}")
            # Instance Variables (specific to each object)
            self.name = name
            self.age = age

        # Instance Method (operates on instance data - name, age)
        def greet(self):
            print(f"Hello, my name is {self.name} and I am {self.age} years old.")

        # Class Method (operates on class data - species)
        @classmethod
        def display_species(cls):
            print(f"This is from the {cls.__name__} class. All instances are {cls.species}.")

        # Static Method (utility, doesn't need instance or class)
        @staticmethod
        def is_adult(age):
            return age >= 18

        # Destructor (optional)
        def __del__(self):
             print(f"Person object {self.name} is being deleted.")


    # Creating Objects (Instances)
    person1 = Person("Ali", 25) # __init__ is called
    person2 = Person("Sara", 17) # __init__ is called

    # Calling Instance Methods
    person1.greet() # Output: Hello, my name is Ali and I am 25 years old.
    person2.greet() # Output: Hello, my name is Sara and I am 17 years old.

    # Accessing Instance Variables
    print(f"{person1.name} is {person1.age}") # Output: Ali is 25
    print(f"{person2.name} is {person2.age}") # Output: Sara is 17

    # Accessing Class Variable via Class Name
    print(Person.species) # Output: Human

    # Accessing Class Variable via Object (works, but via class is clearer)
    print(person1.species) # Output: Human

    # Calling Class Method
    Person.display_species() # Output: This is from the Person class. All instances are Human.
    # person1.display_species() # Can also call via object

    # Calling Static Method
    print(f"Is {person1.name} an adult? {Person.is_adult(person1.age)}") # Output: Is Ali an adult? True
    print(f"Is {person2.name} an adult? {Person.is_adult(person2.age)}") # Output: Is Sara an adult? False

    # Deleting objects (will call __del__)
    del person1
    del person2
    ```

    ```python
    # Example 2: Encapsulation (Protected and "Private" attributes)
    class Student:
        def __init__(self, name, student_id, initial_grade):
            self.name = name
            self._student_id = student_id # Protected (convention) - accessed via _
            self.__grade = initial_grade # "Private" (name mangling) - accessed via __

        # Method to access protected attribute
        def get_student_id(self):
            return self._student_id

        # Method to access (getter) private attribute
        def get_grade(self):
            return self.__grade # Accessible within the class

        # Method to modify (setter) private attribute - with validation using if/else
        def set_grade(self, new_grade):
            if 0 <= new_grade <= 100: # Using if/else for validation
                self.__grade = new_grade
                print(f"Grade updated for {self.name}")
            else:
                print(f"Invalid grade value: {new_grade}. Grade not updated.")

    s1 = Student("Bilal", "S123", 85)

    # Accessing public attribute
    print(f"Student Name: {s1.name}") # Output: Student Name: Bilal

    # Accessing protected attribute (by convention, still accessible from outside)
    print(f"Student ID (direct access): {s1._student_id}") # Output: Student ID (direct access): S123

    # Accessing protected attribute via method (preferred)
    print(f"Student ID (via method): {s1.get_student_id()}") # Output: Student ID (via method): S123

    # Trying to access "private" attribute directly (will cause error)
    # print(f"Grade (direct access): {s1.__grade}") # This will fail

    # Accessing "private" attribute via method (correct way)
    print(f"Grade (via method): {s1.get_grade()}") # Output: Grade (via method): 85

    # Modifying grade via setter (valid)
    s1.set_grade(92)
    print(f"New Grade: {s1.get_grade()}") # Output: New Grade: 92

    # Modifying grade via setter (invalid - uses if/else inside)
    s1.set_grade(110) # Output: Invalid grade value: 110. Grade not updated.
    print(f"Grade after invalid attempt: {s1.get_grade()}") # Output: Grade after invalid attempt: 92
    ```

*   **Practice Questions (English):**
    1.  Create a class `Teacher` with instance variables `name`, `subject`. Add an `__init__` method and a method `teach()` that prints which subject the teacher teaches.
    2.  Modify the `Teacher` class to add a class variable `school_name`. Add a class method `display_school_name()`.
    3.  Add a static method `is_qualified(degree)` to the `Teacher` class that returns True if the `degree` is "Masters" or "PhD".

---

**Special Methods (Dunder Methods) and Property Decorator**

*   **Simple Definitions (English):**
    *   **Special Methods (Dunder Methods):** These are methods with double underscores at the beginning and end of their names (e.g., `__str__`, `__add__`). They allow your objects to integrate with Python's built-in functions and operators. You don't call them directly; Python calls them in specific situations (e.g., `print(obj)` calls `obj.__str__()`).
    *   `@property` Decorator: A Python decorator used above a method to turn it into a 'property'. This allows you to access the method like an attribute (`obj.method_name`) instead of calling it like a function (`obj.method_name()`). It's commonly used to create getter methods. You can also use `@property_name.setter` and `@property_name.deleter` to define setter and deleter methods for the same property.
*   **Examples (using Person/Student):**

    ```python
    # Example 1: Special Methods __str__ and __eq__
    class Student:
        def __init__(self, name, student_id):
            self.name = name
            self.student_id = student_id

        # Special method for user-friendly string representation
        # Called by print() or str()
        def __str__(self):
            return f"Student: {self.name} (ID: {self.student_id})"

        # Special method for developer-friendly representation
        # Called by repr() or when object is displayed in interpreter
        def __repr__(self):
             return f"Student(name='{self.name}', student_id='{self.student_id}')"

        # Special method for equality check (using ==)
        def __eq__(self, other):
            if isinstance(other, Student):
                # Compare based on student_id
                return self.student_id == other.student_id
            return False # Not equal if 'other' is not a Student

    s1 = Student("Ali", "S123")
    s2 = Student("Sara", "S456")
    s3 = Student("Bilal", "S123") # Same ID as s1

    print(s1)        # Calls __str__
    print(repr(s2))  # Calls __repr__

    print(s1 == s2) # Calls __eq__ (Output: False)
    print(s1 == s3) # Calls __eq__ (Output: True)
    print(s1 == "S123") # Calls __eq__ (Output: False)
    ```

    ```python
    # Example 2: @property Decorator (Getter and Setter)
    class Student:
        def __init__(self, name, score):
            self.name = name
            self._score = None # Internal storage for score
            self.score = score # Use the setter for initial assignment

        # Use @property to make score access look like an attribute access
        @property
        def score(self):
            print("Accessing score...")
            return self._score

        # Use @score.setter to define how to set the score
        # This method runs when you do student_object.score = value
        @score.setter
        def score(self, value):
            print(f"Setting score to {value}...")
            if 0 <= value <= 100: # Validation using if/else
                self._score = value
            else:
                print(f"Invalid score {value}. Score must be between 0 and 100.")

        # Example of a calculated property (read-only)
        @property
        def grade_status(self):
            if self._score is None:
                return "Score not set"
            elif self._score >= 50:
                return "Passed"
            else:
                return "Failed"

    student1 = Student("Fatima", 75)
    print(f"{student1.name}'s score is: {student1.score}") # Calls the getter

    student1.score = 90 # Calls the setter
    print(f"{student1.name}'s updated score is: {student1.score}")

    student1.score = 105 # Calls the setter (with validation)
    print(f"{student1.name}'s score after invalid set: {student1.score}")

    print(f"{student1.name} status: {student1.grade_status}") # Accessing calculated property
    ```

*   **Practice Questions (English):**
    1.  Create a class `Rectangle` with `width` and `height` attributes. Implement `__str__` to display the rectangle's dimensions (e.g., "Rectangle: 10x5"). Implement `__add__` to add the areas of two rectangles.
    2.  Modify the `Rectangle` class. Use `@property` for `area` so it can be accessed like an attribute (`rect.area`) instead of a method (`rect.area()`).
    3.  In the `Rectangle` class, implement a setter for `width` using `@width.setter` that ensures the width is always a positive number.

---

**Inheritance (Basic, Types, Constructors, Access Modifiers)**

*   **Simple Definitions (English):**
    *   **Inheritance:** An OOP mechanism where a new class (child/derived class) inherits attributes and methods from an existing class (parent/base class). This promotes code reuse and models "is-a" relationships (e.g., a Student *is a* Person).
    *   **Types of Inheritance:**
        *   **Single Inheritance:** A class inherits from only one base class.
        *   **Multiple Inheritance:** A class inherits from multiple base classes.
        *   **Multilevel Inheritance:** A class inherits from a base class, and then another class inherits from that derived class (A -> B -> C).
        *   **Hierarchical Inheritance:** Multiple classes inherit from a single base class.
    *   **Constructors (`__init__`) in Inheritance:** When a derived class object is created, the base class's `__init__` method needs to be called to initialize the base class's part of the object. This is done using `super().__init__(...)` in the derived class's `__init__`.
    *   **Access Modifiers in Inheritance (Protected `_`, "Private" `__`):**
        *   **Protected members (`_variable_name`):** By convention, these should only be accessed within the class itself and by its derived classes. Python doesn't strictly enforce this but indicates they are internal. Derived classes *can* access them directly.
        *   **"Private" members (`__variable_name`):** Python uses name mangling (`_ClassName__variable_name`) to make these harder to access from outside the class, *including* derived classes. They are primarily intended for use *only* within the class where they are defined. Derived classes usually need to access them through public or protected methods provided by the base class.
*   **Examples (using Person/Student/Teacher/Principal):**

    ```python
    # Example 1: Single Inheritance, Constructors, Method Overriding
    class Person:
        def __init__(self, name, age):
            print(f"Initializing Person: {name}")
            self.name = name
            self.age = age

        def display_info(self):
            print(f"Name: {self.name}, Age: {self.age}")

    # Student inherits from Person (Single Inheritance)
    class Student(Person):
        def __init__(self, name, age, student_id):
            print(f"Initializing Student: {name}")
            # Call the parent (Person) constructor using super()
            super().__init__(name, age)
            self.student_id = student_id

        # Override the display_info method
        def display_info(self):
            # Can call parent's method if needed: super().display_info()
            print(f"Student Name: {self.name}, Age: {self.age}, Student ID: {self.student_id}")

    # Teacher inherits from Person (Hierarchical Inheritance example alongside Student)
    class Teacher(Person):
        def __init__(self, name, age, subject):
            print(f"Initializing Teacher: {name}")
            super().__init__(name, age)
            self.subject = subject

        # Override display_info
        def display_info(self):
            print(f"Teacher Name: {self.name}, Age: {self.age}, Subject: {self.subject}")

    # Creating objects
    p1 = Person("Ali", 30)
    p1.display_info()
    # Output:
    # Initializing Person: Ali
    # Name: Ali, Age: 30

    s1 = Student("Sara", 20, "S123")
    s1.display_info() # Calls the overridden method in Student
    # Output:
    # Initializing Student: Sara
    # Initializing Person: Sara
    # Student Name: Sara, Age: 20, Student ID: S123

    t1 = Teacher("Mr. Khan", 45, "Computer Science")
    t1.display_info() # Calls the overridden method in Teacher
    # Output:
    # Initializing Teacher: Mr. Khan
    # Initializing Person: Mr. Khan
    # Teacher Name: Mr. Khan, Age: 45, Subject: Computer Science
    ```

    ```python
    # Example 2: Multilevel Inheritance
    class Animal:
        def sound(self):
            print("Some animal sound")

    class Mammal(Animal): # Mammal inherits from Animal
        def walk(self):
            print("Can walk")

    class Dog(Mammal): # Dog inherits from Mammal (Multilevel)
        def sound(self): # Override sound from Animal
            print("Woof!")
        def fetch(self):
            print("Fetching the ball")

    d = Dog()
    d.sound() # Output: Woof! (Dog's overridden method)
    d.walk()  # Output: Can walk (Inherited from Mammal)
    # d.fetch() # Output: Fetching the ball (Dog's own method)
    ```

    ```python
    # Example 3: Multiple Inheritance
    class Flyer:
        def fly(self):
            print("Can fly")

    class Swimmer:
        def swim(self):
            print("Can swim")

    class Duck(Flyer, Swimmer): # Duck inherits from both
        pass

    ducky = Duck()
    ducky.fly()  # Output: Can fly
    ducky.swim() # Output: Can swim
    ```

    ```python
    # Example 4: Access Modifiers in Inheritance (using Person/Student again)
    class Person:
        def __init__(self, name, _tax_id):
            self.name = name # Public
            self._tax_id = _tax_id # Protected (convention)
            self.__salary = 50000 # "Private" (name mangling)

        def display_name(self): # Public method
            print(f"Name: {self.name}")

        def _get_tax_id(self): # Protected method (convention)
             return self._tax_id

        def get_salary(self): # Public method to access "private" attribute
            return self.__salary

    class Employee(Person): # Employee inherits from Person
        def __init__(self, name, _tax_id, employee_code):
            super().__init__(name, _tax_id)
            self.employee_code = employee_code

        def display_employee_details(self):
            print(f"Employee Code: {self.employee_code}")
            # Can access inherited public attribute
            print(f"Name: {self.name}")
            # Can access inherited protected attribute (by convention)
            print(f"Tax ID (from derived class): {self._tax_id}")
            # Cannot directly access inherited "private" attribute __salary
            # print(f"Salary (direct access from derived): {self.__salary}") # This will fail
            # Access "private" attribute using base class's public method
            print(f"Salary (via base method from derived): {self.get_salary()}")


    emp = Employee("Imran", "T987", "E101")
    emp.display_employee_details()

    # Accessing from outside:
    print(f"Employee Name (from outside): {emp.name}") # Public - OK
    print(f"Employee Tax ID (from outside, direct access): {emp._tax_id}") # Protected - Accessible but discouraged by convention
    # print(f"Employee Salary (from outside, direct access): {emp.__salary}") # Private - Fails
    print(f"Employee Salary (from outside, via base method): {emp.get_salary()}") # Via public method - OK
    ```

*   **Practice Questions (English):**
    1.  Create a base class `Building` with an attribute `address`. Create a derived class `School` that inherits from `Building` and adds an attribute `num_students`. Demonstrate initializing both attributes using `super()` and creating a method in `School` that prints both.
    2.  Explain Multilevel Inheritance with an example using `Shape`, `Polygon`, and `Rectangle`.
    3.  Define a base class `Printer` with a `print_document` method. Define another base class `Scanner` with a `scan_document` method. Create a derived class `AllInOneMachine` that inherits from both.

---

**Sample Test Paper (Total: 20 Marks)**

Here is a sample test paper based on your specified pattern and using the requested naming conventions where applicable.

**Course:** Object Oriented Programming (Python)
**Total Marks:** 20
**Time:** (Assume ~45-60 minutes)

**Instructions:** Attempt all questions.

---

**Part 1: Definitions and Examples (10 Marks)**

Define any **FIVE** of the following concepts in **simple English** and provide **ONE** clear Python code example for each. (2 Marks each)

1.  Object (in OOP)
2.  Instance Variable
3.  Python `@property` Decorator
4.  Generator Function
5.  List Comprehension
6.  Encapsulation (Explain its purpose)
7.  `__init__` (Constructor)
8.  Multiple Inheritance (Brief Definition)

---

**Part 2: Inheritance Programming Problem (5 Marks)**

Write a Python program using inheritance.

1.  Define a base class called `Staff`.
    *   The `Staff` class should have an `__init__` method that takes `name` and `staff_id` as arguments and initializes these attributes.
    *   Add a method `display_details()` that prints the staff member's name and ID.
2.  Define a derived class called `Teacher` that inherits from `Staff`.
    *   The `Teacher` class's `__init__` method should take `name`, `staff_id`, and `subject` as arguments. It must call the parent class's `__init__` using `super()` to handle `name` and `staff_id`, and then initialize the `subject` attribute.
    *   Override the `display_details()` method in the `Teacher` class to also print the teacher's subject along with their name and ID.
3.  Create an object of the `Teacher` class and call its `display_details()` method.

---

**Part 3: General Programming Problem (5 Marks)**

Write a Python program using a conditional statement (`if/else` or `if/elif/else`) and either `map()`, `filter()`, or a list comprehension.

You are given a list of student scores (integers). Create a new list containing a status for each score: "Pass" if the score is 50 or above, and "Fail" otherwise.

Use **either** a list comprehension with an `if/else` **or** a combination of `map()` and a function/lambda with `if/else` to achieve this.

**Example Input:**

```python
student_scores = [45, 65, 80, 30, 55, 90, 40]
```

**Expected Output:**

```
['Fail', 'Pass', 'Pass', 'Fail', 'Pass', 'Pass', 'Fail']
```
(The order must match the input list.)

---

Ji sir, maine koshish ki hai ke har point ko clearly explain karun English definitions ke saath aur code examples mein aapki requested conventions use karun. `if/else` ko bhi explain kiya hai aur OOP examples mein uski usage bhi dikhai hai (setter validation mein). Special methods ko bhi dobara explain kiya hai.

Umeed hai yeh aapke liye helpful hoga. Agar koi aur clarification chahiye ho ya kuch aur add karna ho toh bataiye ga. Insha'Allah, paper acha hoga! 😊👍
