
# # Constructors in Python: Welcome Message with Student Name

## 🎯 Aim
To write a Python program that creates a **Student** class with a **default constructor** and a method to display a welcome message along with the student’s name provided by the user.

## 🧠 Algorithm
1. **Get user input**: Accept the student's name from the user.
2. **Define the class**: Create a class `Student` with a default constructor (`__init__`).
3. **Default Constructor**: In the constructor, assign the user input (student name) to an instance variable `self.a`.
4. **Display Message**: Define a method `show` that prints "This is non-parameterized constructor" and a welcome message with the student’s name.
5. **Execute the Program**: Instantiate the `Student` class and call the `show` method.

## 🧾 Program

name = input("Enter the student's name: ")


class Student:
    def __init__(self):
      
        self.a = name


    def show(self):
        print("This is non-parameterized constructor")
        print(f"Welcome, {self.a}!")


s = Student()
s.show()


## Output
Enter the student's name: Nihal
This is non-parameterized constructor
Welcome, Nihal!

## Result
Thus the Python program that creates a **Student** class with a **default constructor** and a method to display a welcome message along with the student’s name provided by the user is executed successfully.

# Destructor in Python
Aim
Demonstrates how to implement a **destructor** in Python using a simple class.

## 🚀 Overview

The program defines a class `Demo` with:

- A **constructor** `__init__` that initializes an instance variable and prints a message.
- A **destructor** `__del__` that prints a message when the object is destroyed.

## 🧠 Algorithm

1. Define a class named `Demo`.
2. Inside the class, define the `__init__` method:
   - Initialize an instance variable `status` with the value `"Alive"`.
   - Print the value of `status`.
3. Define the `__del__` method:
   - Print a message indicating the object is being destroyed.
4. Outside the class:
   - Create an instance of the `Demo` class.
   - Delete the object using the `del` keyword.
## Program

class Demo:

    def __init__(self):
        self.status = "Alive"
        print(f"Status: {self.status}")

    def __del__(self):
        print("The Demo object is being destroyed.")

obj = Demo()   
del obj
## 🧪 Output
Status: Alive
The Demo object is being destroyed.

## Result
Thus the python program demonstrates how to implement a **destructor** in Python using a simple class.


# Hierarchical Inheritance in Python

This Python project demonstrates **Hierarchical Inheritance** using a base class `Details` and two derived classes `Employee` and `Patient`. The program collects and displays details for both employees and patients.

## 🎯 Aim

To write a Python program that uses **Hierarchical Inheritance** to input and display **Employee** and **Patient** details.

## 📘 Description

- **Base Class:** `Details`
  - Stores common attributes: `name`, `age`
  - Provides methods: `getName()`, `getAge()`

- **Derived Class 1:** `Employee`
  - Inherits from `Details`
  - Adds: `employee_id`, `department`
  - Method: `getEmployeeDetails()`

- **Derived Class 2:** `Patient`
  - Inherits from `Details`
  - Adds: `patient_id`, `disease`
  - Method: `getPatientDetails()`

## 🧠 Algorithm

1. Create base class `Details` with common attributes.
2. Create `Employee` class extending `Details`, adding employee-specific data.
3. Create `Patient` class extending `Details`, adding patient-specific data.
4. Get user input for employee and patient data.
5. Display collected information using class methods.

## Program
# Step 1: Base class
class Details:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def display_details(self):
        print(f"Name: {self.name}")
        print(f"Age: {self.age}")

# Step 2: Employee class extending Details
class Employee(Details):
    def __init__(self, name, age, emp_id, department):
        super().__init__(name, age)
        self.emp_id = emp_id
        self.department = department

    def display_details(self):
        print("\n--- Employee Details ---")
        super().display_details()
        print(f"Employee ID: {self.emp_id}")
        print(f"Department: {self.department}")

# Step 3: Patient class extending Details
class Patient(Details):
    def __init__(self, name, age, patient_id, illness):
        super().__init__(name, age)
        self.patient_id = patient_id
        self.illness = illness

    def display_details(self):
        print("\n--- Patient Details ---")
        super().display_details()
        print(f"Patient ID: {self.patient_id}")
        print(f"Illness: {self.illness}")

# Step 4: Get user input
print("Enter Employee Details:")
emp_name = input("Name: ")
emp_age = int(input("Age: "))
emp_id = input("Employee ID: ")
emp_dept = input("Department: ")

print("\nEnter Patient Details:")
pat_name = input("Name: ")
pat_age = int(input("Age: "))
pat_id = input("Patient ID: ")
pat_illness = input("Illness: ")

# Step 5: Create objects and display information
employee = Employee(emp_name, emp_age, emp_id, emp_dept)
patient = Patient(pat_name, pat_age, pat_id, pat_illness)

employee.display_details()
patient.display_details()
## Sample Output
--- Employee Details ---
Name: Nihal
Age: 23
Employee ID: 123456
Department: Ic

--- Patient Details ---
Name: Usaidh
Age: 45
Patient ID: 98765
Illness: Headache

Result
Thus the Python program that uses **Hierarchical Inheritance** to input and display **Employee** and **Patient** details is executed successfully.

# Multilevel Inheritance Example in Python

This Python project demonstrates the concept of **Multilevel Inheritance** to collect and display the **name**, **age**, and **location** of a person.

## 🎯 Aim

To write a Python program that uses multilevel inheritance to get and display a person’s name, age, and location.

## 🧠 Algorithm

1. **Parent Class**  
   - `__init__(name)` initializes the `name` attribute.  
   - `getName()` returns the `name`.

2. **Child Class (inherits Parent)**  
   - `__init__(name, age)` initializes `name` using `super()` and adds `age`.  
   - `getAge()` returns the `age`.

3. **Grandchild Class (inherits Child)**  
   - `__init__(name, age, location)` initializes `name` and `age` using `super()` and adds `location`.  
   - `getLocation()` returns the `location`.

4. **Input & Output**  
   - Take user input for name, age, and location.  
   - Create an instance of `Grandchild`.  
   - Print all details using class methods.

## Program

class Parent:
    def __init__(self, name):
        self.name = name

    def getName(self):
        return self.name

class Child(Parent):
    def __init__(self, name, age):
        super().__init__(name)  
        self.age = age

    def getAge(self):
        return self.age


class Grandchild(Child):
    def __init__(self, name, age, location):
        super().__init__(name, age)  
        self.location = location

    def getLocation(self):
        return self.location


name = input("Enter name: ")
age = int(input("Enter age: "))
location = input("Enter location: ")


person = Grandchild(name, age, location)


print("\n--- Details ---")
print(f"Name: {person.getName()}")
print(f"Age: {person.getAge()}")
print(f"Location: {person.getLocation()}")
## Sample Output

--- Details ---
Name: Nihal
Age: 23
Location: Chennai

Result
Thus the Python program that uses multilevel inheritance to get and display a person’s name, age, and location.


# Arithmetic Operations Using Multiple Inheritance in Python

This Python program demonstrates **multiple inheritance** by performing basic arithmetic operations — Addition, Subtraction, and Division — using three classes.

## 🎯 Aim

To write a Python program to calculate **Add, Sub & Division** using **Multiple Inheritance**.

## 🧠 Algorithm

1. **Define `Calculation1` class**
   - Contains `Summation(a, b)` method to return the sum of two numbers.
2. **Define `Calculation2` class**
   - Contains `Subtraction(a, b)` method to return the difference of two numbers.
3. **Define `Derived` class**
   - Inherits from both `Calculation1` and `Calculation2`.
   - Contains `Division(a, b)` method to return the division result.
4. **Input**
   - Prompt the user to enter two numbers.
5. **Process**
   - Create an object of the `Derived` class.
   - Call `Summation`, `Subtraction`, and `Division` methods.
6. **Output**
   - Display the results of the three operations.

## 💻 Program 
# Step 1: Define Calculation1 class
class Calculation1:
    def Summation(self, a, b):
        return a + b

# Step 2: Define Calculation2 class
class Calculation2:
    def Subtraction(self, a, b):
        return a - b

# Step 3: Define Derived class inheriting both Calculation1 and Calculation2
class Derived(Calculation1, Calculation2):
    def Division(self, a, b):
        if b != 0:
            return a / b
        else:
            return "Error! Division by zero."

# Step 4: Input
num1 = float(input("Enter first number: "))
num2 = float(input("Enter second number: "))

# Step 5: Process
calc = Derived()
sum_result = calc.Summation(num1, num2)
sub_result = calc.Subtraction(num1, num2)
div_result = calc.Division(num1, num2)

# Step 6: Output
print("\n--- Results ---")
print(f"Sum: {sum_result}")
print(f"Difference: {sub_result}")
print(f"Division: {div_result}")

## Output Example
Enter first number: 23.5
Enter second number: 34.6

--- Results ---
Sum: 58.1
Difference: -11.100000000000001
Division: 0.6791907514450867

Result:
Thus the Python program demonstrates **multiple inheritance** by performing basic arithmetic operations — Addition, Subtraction, and Division — using three classes is executed successfully.
