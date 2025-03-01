# Introduction to Object-Oriented Programming (OOP)

## What is OOP?
Imagine you are designing a game or an app. Instead of writing all the code in one place, you can break it into smaller, manageable parts called **objects**. These objects are created using **classes**, which act as blueprints. Each object has its own **data** (characteristics) and **actions** (things it can do).

OOP is a way to organize code that makes it easier to understand, reuse, and modify. It is used in many modern programming languages like Python, Java, and C++.

---

## **1. Understanding Classes and Objects**
### **What is a Class?**
A **class** is a blueprint or template for creating objects. It defines the structure (attributes) and behavior (methods) that objects of that class will have.

### **What is an Object?**
An **object** is an actual instance of a class. It has real data stored in it and can perform the actions defined in the class.

### **Example 1: Basic Class and Object**
```python
class Animal:
    def __init__(self, name, species):
        self.name = name  # Instance attribute
        self.species = species  # Instance attribute
    
    def make_sound(self, sound):
        return f"{self.name} the {self.species} says {sound}."

# Creating objects (instances of the class)
dog = Animal("Buddy", "Dog")
cat = Animal("Whiskers", "Cat")

print(dog.make_sound("Woof"))  # Output: Buddy the Dog says Woof.
print(cat.make_sound("Meow"))  # Output: Whiskers the Cat says Meow.
```

### **Key Takeaways:**
- `Animal` is the **class** (blueprint).
- `dog` and `cat` are **objects** (instances of `Animal`).
- `self.name` and `self.species` are **attributes** (store data about the object).
- `make_sound()` is a **method** (defines behavior of the object).

---

## **2. Exploring Instance and Class Attributes**
### **Instance Attributes (Unique to Each Object)**
Each object has its own values for instance attributes.
```python
class Car:
    def __init__(self, brand, model, year):
        self.brand = brand  # Instance attribute
        self.model = model  # Instance attribute
        self.year = year  # Instance attribute

car1 = Car("Toyota", "Corolla", 2022)
car2 = Car("Honda", "Civic", 2023)

print(car1.brand)  # Output: Toyota
print(car2.brand)  # Output: Honda
```

### **Class Attributes (Shared Across All Objects)**
A class attribute is the same for all objects.
```python
class Car:
    wheels = 4  # Class attribute (same for all cars)
    
    def __init__(self, brand, model):
        self.brand = brand  # Instance attribute
        self.model = model  # Instance attribute

car1 = Car("Toyota", "Corolla")
car2 = Car("Honda", "Civic")

print(car1.wheels)  # Output: 4
print(car2.wheels)  # Output: 4
```

Even if we change `wheels` in `car1`, the class attribute remains unchanged for `car2`.
```python
car1.wheels = 6  # Changing wheels for car1 only
print(car1.wheels)  # Output: 6
print(car2.wheels)  # Output: 4
```

---

## **3. Methods in Classes**
### **Types of Methods**
1. **Instance Methods**: Work with instance attributes (use `self`).
2. **Class Methods**: Work with class attributes (use `@classmethod`).
3. **Static Methods**: Do not modify instance or class attributes (use `@staticmethod`).

### **Example: All Three Method Types**
```python
class MathOperations:
    base = 10  # Class attribute

    def __init__(self, number):
        self.number = number  # Instance attribute
    
    def square(self):  # Instance method
        return self.number ** 2
    
    @classmethod
    def change_base(cls, new_base):  # Class method
        cls.base = new_base
    
    @staticmethod
    def add(x, y):  # Static method
        return x + y

num1 = MathOperations(5)
print(num1.square())  # Output: 25 (5^2)

MathOperations.change_base(20)
print(MathOperations.base)  # Output: 20

print(MathOperations.add(3, 7))  # Output: 10
```

---

## **4. Creating Multiple Objects and Using Lists**
We can store multiple objects in a list and loop through them.
```python
class Student:
    def __init__(self, name, grade):
        self.name = name
        self.grade = grade
    
    def get_details(self):
        return f"Student: {self.name}, Grade: {self.grade}"

students = [
    Student("Alice", "A"),
    Student("Bob", "B"),
    Student("Charlie", "A+")
]

for student in students:
    print(student.get_details())
```
### **Output:**
```
Student: Alice, Grade: A
Student: Bob, Grade: B
Student: Charlie, Grade: A+
```

---

## **Next Step: Encapsulation and Data Hiding**
Now that we understand classes and objects deeply, the next step is **encapsulation**, which protects data by restricting direct access. Stay tuned! 🚀

