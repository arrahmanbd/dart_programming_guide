
![Awesome ReadME](cover.png)
 
# Dart Programming Guide ✨

[![GitHub release (latest by date including pre-releases)](https://img.shields.io/github/v/release/navendu-pottekkat/awesome-readme?include_prereleases)](https://img.shields.io/github/v/release/navendu-pottekkat/awesome-readme?include_prereleases)
[![GitHub last commit](https://img.shields.io/github/last-commit/navendu-pottekkat/awesome-readme)](https://img.shields.io/github/last-commit/navendu-pottekkat/awesome-readme)
[![GitHub issues](https://img.shields.io/github/issues-raw/navendu-pottekkat/awesome-readme)](https://img.shields.io/github/issues-raw/navendu-pottekkat/awesome-readme)
[![GitHub pull requests](https://img.shields.io/github/issues-pr/navendu-pottekkat/awesome-readme)](https://img.shields.io/github/issues-pr/navendu-pottekkat/awesome-readme)
[![GitHub](https://img.shields.io/github/license/navendu-pottekkat/awesome-readme)](https://img.shields.io/github/license/navendu-pottekkat/awesome-readme)

Dart is a modern, object-oriented programming language developed by Google. It is known for its simplicity, efficiency, and versatility. Dart is primarily used for building web, mobile, and server-side applications.

 
## Table of Contents 💡

- [Dart Programming Guide ✨](#dart-programming-guide-)
  - [Table of Contents 💡](#table-of-contents-)
- [Basic Information](#basic-information)
- [Basic Syntax](#basic-syntax)
- [Variables and Data Types](#variables-and-data-types)
  - [Record DataType:](#record-datatype)
    - [Returning Multiple value Using Record](#returning-multiple-value-using-record)
    - [Using Record in Real world](#using-record-in-real-world)
- [Control Flow Statements](#control-flow-statements)
- [Functions](#functions)
  - [More about functions:](#more-about-functions)
- [Classes and Objects](#classes-and-objects)
- [Exception Handling](#exception-handling)
    - [Try Catch](#try-catch)
    - [Exception](#exception)
- [Asynchronous Programming](#asynchronous-programming)
- [Libraries and Packages](#libraries-and-packages)
- [Dart Collection \& Methods](#dart-collection--methods)
  - [List methods \[for\]:](#list-methods-for)
  - [Method \[for-in\]](#method-for-in)
  - [Method \[for-each\]](#method-for-each)
  - [Method \[for-in\]](#method-for-in-1)
  - [Method \[where in\]](#method-where-in)
  - [Method \[map\]](#method-map)
  - [Future \[for-each\]](#future-for-each)
  - [Find the common](#find-the-common)
- [Sum of a List](#sum-of-a-list)
- [Sorting a List](#sorting-a-list)
  - [Map sorting](#map-sorting)
  - [Object soring](#object-soring)
- [String replacer](#string-replacer)
  - [Empty or null check](#empty-or-null-check)
- [Object into Bytes:](#object-into-bytes)
  - [Decode](#decode)
- [OOP Concepts](#oop-concepts)
  - [Object and Constractor](#object-and-constractor)
    - [Constructor:](#constructor)
    - [Parameterized Constructor:](#parameterized-constructor)
    - [Static Method:](#static-method)
    - [Getter and Setter:](#getter-and-setter)
  - [Abstraction:](#abstraction)
  - [Inheritance:](#inheritance)
  - [Polymorphism:](#polymorphism)
  - [OOP Example](#oop-example)
  - [Real life example](#real-life-example)
  - [Clean Concept](#clean-concept)
- [Contribute](#contribute)
  - [🚀  Follow](#--follow)
  - [Badges](#badges)

# Basic Information
[(Back to top)](#table-of-contents)

# Basic Syntax
Dart syntax is easy to understand and resembles many other C-style languages. It includes features such as variables, data types, operators, and comments. 

# Variables and Data Types
In Dart, variables are used to store data values. Dart supports various data types including integers, doubles, strings, booleans, lists, and maps. Learn more about Variables and Data Types.

```dart
void main(List<String> arguments) {

	// Numbers: int
	int score = 23;
	var count = 23;     // It is inferred as integer automatically by compiler
	int hexValue = 0xEADEBAEE;

	// Numbers: double
	double percentage = 93.4;
	var percent = 82.533;
	double exponents = 1.42e5; 

	// Strings
	String name = "Henry";
	var company = "Google";

	// Boolean
	bool isValid = true;
	var isAlive = false;

	print(score);
	print(exponents);

	// NOTE: All data types in Dart are Objects.
	// Therefore, their initial value is by default 'null'
  // String Interpolation : Use ["My name is $name"] instead of ["My name is " + name]
	String name = "AR Rahman";

	print("My name is $name");
	print("The number of characters in String AR Rahman is ${name.length}");


	int l = 20;
	int b = 10;

	print("The sum of $l and $b is ${l + b}");
	print("The area of rectangle with length $l and breadth $b is ${l * b}");
}
```
## Record DataType:
Dart 2 provides you with some options for bundling multiple objects into a single value.
Dart Record type that allows you to bundle multiple objects into a single value.
```dart
// the following defines a record with two values latitude and longitude:
final location = (10.0, 20.0);
//The fields of records may have a name to make it more clear
final location = (lat: 10.0, lon: 20.0);
//To annotate the type of the record in a variable declaration, you use the following:
(double, double) location = (10.0, 20.0);
//Also, you can name the positional fields in the record type annotation:
(double lat, double lon) location = (10.0, 20.0);
  final lat = location.$1;
  final lon = location.$2;
  print('($lat, $lon)');

  //Record equality
  final loc1 = (10.0, 20.0);
  final loc2 = (10.0, 20.0);
  final result = loc1 == loc2;
  print(result); // true
```
### Returning Multiple value Using Record
```dart
void main() {
  final result = minmax([5, 2, 3, 7, 0, -1]);
  print(result);
}

(double?, double?) minmax(List<double> numbers) {
  if (numbers.length == 0) {
    return (null, null);
  }

  double min = numbers[0];
  double max = numbers[0];

  for (int i = 1; i < numbers.length; i++) {
    if (numbers[i] < min) {
      min = numbers[i];
    }

    if (numbers[i] > max) {
      max = numbers[i];
    }
  }
  return (min, max);
}
```
### Using Record in Real world
```dart
import 'package:http/http.dart' as http;
import 'todo.dart';

Future<(Todo?, String)> fetchTodo(int id) async {
  final uri = Uri(
    scheme: 'https',
    host: 'jsonplaceholder.typicode.com',
    path: 'todos/$id',
  );

  try {
    var response = await http.Client().get(uri);

    // if not OK
    if (response.statusCode != 200) {
      return (
        null,
        'Failed to fetch todo: ${response.statusCode}, ${response.reasonPhrase}'
      );
    }

    final todo = Todo.fromJson(response.body);
    return (todo, 'Success');
  } catch (e) {
    return (null, 'Error to fetch todo: $e');
  }
}

```
# Control Flow Statements
Control flow statements in Dart allow you to control the flow of your program execution. Dart supports if-else statements, switch statements, loops, and more. Check out Control Flow Statements for examples and explanations.

```dart
void main() {
  //if else
  var salary = 25000;

  if (salary >= 25000) {
    print("Conratulations");
  } else {
    print("Lololol");
  }

  String grade = 'A';

//switch - applicable only for int and string

  switch (grade) {
    case 'A':
      print("Excellent");
      break;
    case 'B':
      print("Great");
      break;
    case 'C':
      print("Good");
      break;
    default:
      print("Invalid grade");
  }
}
```

# Functions
Functions are a fundamental building block of Dart programming. They allow you to encapsulate code for reuse and modularity.In dart, "main " function is the mother of your programme. Learn how to define and use functions. 
```dart
void main() {
  printPlanets("Earth", "Mars"); //3rd param is optional

  print("");

  printCities("Delhi", "Mumbai", "Goa");

  print("");

  printFruits("Apple");
  print("The volume is: ${findVolume(lenghth: 5, breadth: 6, height: 5)}");
}

//1. Required params
void printCities(String a, String b, String c) {
  //we can define optional params by defining them in "[]", square brackets

  print("Name is $a");
  print("Name is $b");
  print("Name is $c");
}

//2. Optional positional params
void printPlanets(String a, String b, [String c]) {
  //we can define optional params by defining them in "[]", square brackets

  print("Name is $a");
  print("Name is $b");
  print("Name is $c");
}

void printFruits(String a, [String b, String c]) {
  //multiple optional positional params

  print("Name is $a");
  print("Name is $b");
  print("Name is $c");
}
int findVolume({int lenghth, int breadth, int height}) {
  /**
   * Named params: used to prevent errors if there are large no. of params
   * - use "{}", curly brackets to define
   */
  return lenghth * breadth * height;
}
```
## More about functions: 
```dart

// Objectives
// 1. Higher-Order Function:
// 2. Lambda function
// 3. Closer
// How to pass function as parameter?
// How to return a function from another function?


void main() {

	// Example One: Passing Function to Higher-Order Function
	Function addNumbers = (a, b) => print(a + b);
	someOtherFunction("Hello", addNumbers);


	// Example Two: Receiving Function from Higher-Order Function
	var myFunc = taskToPerform();
	print(myFunc(10));      // multiplyFour(10)         // number * 4       // 10 * 4       // OUTPUT: 40
}



// Example one: Accepts function as parameter
void someOtherFunction(String message, Function myFunction) {       // Higher-Order Function

	print(message);
	myFunction(2, 4);       // addNumbers(2, 4)    // print(a + b);   // print(2 + 4)       // OUTPUT: 6
}


// Example two: Returns a function
Function taskToPerform() {       // Higher-Order Function
  //labda function/nameless function
	Function multiplyFour = (int number) => number * 4;
	return multiplyFour;
}
//More labda functions
// Defining Lambda: 1st way
	Function addTwoNumbers = (int a, int b) {
		var sum = a + b;
		print(sum);
	};

	var multiplyByFour = (int number) {
		return number * 4;
	};

	// Defining Lambda: 2nd way: Function Expression: Using Short Hand Syntax or FAT Arrow ( '=>' )
	Function addNumbers = (int a, int b) => print(a + b);

  //closer
	// Definition 1:
	// A closure is a function that has access to the parent scope, even after the scope has closed.

	String message = "Dar is good";

	Function showMessage = () {
		message = "Dart is awesome";
		print(message);
	};

	showMessage();

```

# Classes and Objects
Dart is an object-oriented programming language, which means it supports classes and objects. Classes are used to create objects with properties and methods. Explore Classes and Objects to understand how to work with them in Dart, Scroll  to bottom and check [OOP Concepts](#oop-concepts).

```dart
// 1. Callable class
// --> Class treated as Function.
// --> Implement call() method

void main() {

	var personOne = Person();
	var msg = personOne(25, "Peter");
	print(msg);
}

class Person {
	
	String call(int age, String name) {
		return "The name of the person is $name and age is $age";
	}
}

// Objectives
// 1. Interface class

void main() {

	var tv = Television();
	tv.volumeUp();
	tv.volumeDown();
}

class Remote {

	void volumeUp() {
		print("up");
	}

	void volumeDown() {
		print("down");
	}
}

class AnotherClass {

	void justAnotherMethod(){
		// Code
	}

}

// Here Remote and AnotherClass acts as Interface
class Television implements Remote, AnotherClass {

	void volumeUp() {
//		super.volumeUp();       // Not allowed to call super while implementing a class as Interface
		print("uppp");
	}

	void volumeDown() {
		print("downn");
	}

	void justAnotherMethod() {
		print("Some code");
	}
}
```

# Exception Handling
Exception handling is crucial for writing robust and error-tolerant code. Dart provides try-catch-finally blocks to handle exceptions gracefully. Read more about Exception Handling to learn how to handle errors in Dart programs.

### Try Catch

```dart
List<int> numbers = [1, 2, 3, 4, 5, 0, 6]; // A list of numbers
  int product = 1; // A variable to store the product
  try {
    // Loop through the list of numbers
    for (int i = 0; i < numbers.length; i++) {
      // If the number is 0, throw an exception
      if (numbers[i] == 0) {
        throw Exception('The number cannot be zero.');
      }

      // Multiply the number with the current product
      product *= numbers[i];
    }
  } catch (e) {
    // Handle any errors or exceptions
    debugPrint('An error occurred while looping through the list: $e');
  } finally {
    // Print the product of the numbers in the finally block
    debugPrint(
        'The product of the numbers before the exception occurred (if any) is: $product');
  }
  ```

### Exception
```dart
String input = '-10'; // A string that can be parsed into an integer
  int number;
  try {
    number = int.parse(input); // This might throw a FormatException

    debugPrint('The number is $number.');

    if (number < 0) {
      throw ArgumentError(
          'The number cannot be negative.'); // This might throw an ArgumentError
    }
  } on FormatException catch (e) {
    debugPrint('The input is not a valid number: $e');
  } on ArgumentError catch (e) {
    debugPrint('The input is not acceptable: $e');
  }
  ```

# Asynchronous Programming
Dart offers built-in support for asynchronous programming, which is essential for handling operations such as I/O, networking, and timers without blocking the main thread. Dive into Asynchronous Programming to understand Dart's asynchronous features.
```dart
import 'dart:async';

void main() {
  print('Start of main');
  
  // Simulating an asynchronous operation that returns a Future after 2 seconds
  Future<String> delayedResult = simulateAsyncOperation();
  
  // Executing some other synchronous code while waiting for the Future to complete
  print('Executing some other code while waiting...');
  
  // Handling the result of the Future when it completes
  delayedResult.then((result) {
    print('Result from asynchronous operation: $result');
  }).catchError((error) {
    print('Error occurred: $error');
  });
  
  print('End of main');
}

Future<String> simulateAsyncOperation() {
  return Future.delayed(Duration(seconds: 2), () {
    return 'Async operation completed!';
  });
}

```

# Libraries and Packages
Dart comes with a rich set of standard libraries for common programming tasks. Additionally, you can use third-party packages from [pub.dev](https://pub.dev) to extend Dart's functionality. Discover more about Libraries and Packages in Dart.

 
# Dart Collection & Methods
[(Back to top)](#table-of-contents)

## List methods [for]:

```dart
// Declare and initialize a list of numbers
  List<int> numbers = [1, 2, 3, 4, 5];

  // Use a for loop to iterate over the list
  for (int index = 0; index < numbers.length; index++) {
    // Access the element at the index position and print its square
    int number = numbers[index];

    // Print the square of the number if in debug mode
    if (kDebugMode) {
      print(number * number);
    }
  }
```

## Method [for-in]
 
 ```dart
  List<String> names = ["Goodman", "Badman", "Batman", "Spiderman"];

  // Use a for-in loop to iterate over the list
  for (String name in names) {
    // Print the element in uppercase
    debugPrint(name.toUpperCase());
  }
  ```
## Method [for-each]
 
 ```dart
   // Declare and initialize a list of booleans
  List<bool> flags = [true, false, true, false];

  // Define a function that takes a boolean as an argument and prints its negation
  void negate(bool flag) {
    if (kDebugMode) {
      print(!flag);
    }
  }

  // Call the forEach method on the list and pass the function as an argument
  flags.forEach(negate);
  ```
## Method [for-in]
 
 ```dart
  List<String> words = ['Hello', 'World', 'Flutter'];
  int i = 0;
  while (i < words.length) {
    debugPrint(words[i]);
    i++;
  }
  ```
## Method [where in]
 
 ```dart
  List<Map<String, dynamic>> products = [
    {
      "name": "Product 1",
      "price": 100,
    },
    {
      "name": "Product 2",
      "price": 200,
    },
    {
      "name": "Product 3",
      "price": 300,
    },
  ];

  Iterator<Map<String, dynamic>> it = products.iterator;
  while (it.moveNext()) {
    if (kDebugMode) {
      print(it.current);
    }
  }
  ```
## Method [map]
 
 ```dart
List<String> names = ["John Doe", "Foo Bar", "AR Rahman"];

  // using the map() method to get a list of names in uppercase
  List<String> uppercaseNames =
      names.map((name) => name.toUpperCase()).toList();

  if (kDebugMode) {
    print(uppercaseNames);
  }
  ```
## Future [for-each]
```dart
final items = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
  await Future.forEach(items, (item) async {
    if (kDebugMode) {
      print(item);
    }
    await Future.delayed(const Duration(seconds: 3));
  });
```
## Find the common
```dart
  List<int> list1 = [1, 2, 3, 4, 5];
  List<int> list2 = [3, 4, 5, 6, 7];

  // Convert the lists to sets
  Set<int> set1 = list1.toSet();
  Set<int> set2 = list2.toSet();

  // Find the intersection of the sets
  Set<int> common = set1.intersection(set2);

  // Convert the set to a list
  List<int> result = common.toList();

  // Print the result
  if (kDebugMode) {
    print(result);
  }
```
# Sum of a List
```dart
 List<double> numbers = [1, 2, 3, 4, 5, 0.5, -1.5, 0.25, -0.25];
  double sum = numbers.fold(0, (a, b) => a + b);
  print(sum);
```
```dart
final myListofNumbers = [1, 2, 3, 4, 5, 6.4, 7.1, -4, -1.5];

  var sum = 0.0;
  for (var i = 0; i < myListofNumbers.length; i++) {
    sum += myListofNumbers[i];
  }
  print(sum);
```

```dart
final numbers = [1, 2, 3, 4.4, -1.2, 5, 6, 7, 8, 9];
  var sum = numbers.reduce((a, b) => a + b);
  print(sum);
```
```dart
final numbers = [100, 50, 0, 25, 1, 90.8];
  var sum = numbers.sum;
  print(sum);
  ```
```dart
final numbers = [5, 10, 15, 20, 25];
  var sum = 0;
  numbers.forEach((number) {
    sum += number;
  });
  print(sum);
```

# Sorting a List 
```dart
 List<double> myNumbers = [1, 2.5, 3, 4, -3, 5.4, 7];
  myNumbers.sort();

  if (kDebugMode) {
    print('Ascending order (0-9/A-Z): $myNumbers');
    print('Descending order (9-0/Z-A) ${myNumbers.reversed}');
  }
```
## Map sorting
```dart
List<Map<String, dynamic>> myProducts = [
    {"name": "Shoes", "price": 100},
    {"name": "Pants", "price": 50},
    {"name": "Book", "price": 10},
    {"name": "Lamp", "price": 40},
    {"name": "Fan", "price": 200}
  ];

  // Selling price from low to high
  myProducts.sort((a, b) => a["price"].compareTo(b["price"]));

  // Selling price from high to low
  myProducts.sort((a, b) => b["price"].compareTo(a["price"]));

  if (kDebugMode) {
    print('Low to hight in price: $myProducts');
    print('High to low in price: $myProducts');
  }
```
## Object soring
```dart
class User {
  String name;
  int age;

  User(this.name, this.age);

  @override
  toString() {
    return ('$name - $age years old \n');
  }
}

void main() {
  List<User> users = [
    User('Plumber', 10),
    User('John Doe', 50),
    User('Pipi', 4),
    User('Invisible Man', 31),
    User('Electric Man', 34)
  ];

  // Age from small to large
  users.sort((a, b) => a.age.compareTo(b.age));
  debugPrint('Age ascending order: ${users.toString()}');

  // Age from large to small
  users.sort((a, b) => b.age.compareTo(a.age));
  debugPrint('Age descending order: ${users.toString()}');
}
```
# String replacer
```dart
String str =
      "I like playing video games as well as reading articles on Kindacode.com";

  // matches any five-letter word
  var pattern = RegExp(r'\b\w{5}\b');
  String replacement = "*****";

  String newStr = str.replaceAllMapped(pattern, (match) => replacement);
  print(newStr); 
```
## Empty or null check
```dart
bool validateInput(String? input) {
  if (input == null) {
    return false;
  }

  if (input.isEmpty) {
    return false;
  }

  return true;
}
//Sorthand
bool validateInput(String? input) {
  return input?.isNotEmpty ?? false;
}
```
# Object into Bytes:
```dart
// a list of numbers
  final list1 = [1, 2, 3];
  // a list of strings
  final list2 = ['a', 'b', 'c'];

  // Convert the list into bytes using Utf8Codec
  const codec = Utf8Codec();

  final bytesList1 = codec.encode(list1.toString());
  final bytesList2 = codec.encode(list2.toString());

  if (kDebugMode) {
    print(bytesList1);
    print(bytesList2);
  }
```
## Decode
```dart
final map = {'key1': 'foo bar', 'key2': 123, 'key3': 'more'};

  const jsonCodec = JsonCodec();

  final jsonMap = jsonCodec.encode(map);
  final bytesMap = const Utf8Codec().encode(jsonMap);
  if (kDebugMode) {
    print(bytesMap);
  }
```

# OOP Concepts
## Object and Constractor
 ### Constructor: 
 In Dart, a constructor is a special method used for initializing objects of a class. It has the same name as the class and no return type. Dart supports several types of constructors:
Default Constructor: This is provided by Dart if you don't declare any constructor explicitly. It initializes instance variables with their default values.
### Parameterized Constructor: 
Allows you to initialize instance variables with custom values when creating an object.
Named Constructor: Dart allows you to declare multiple constructors with different names. These constructors can have different parameter lists and provide alternative ways to create objects.
Example of a constructor in Dart:
```dart
class Person {
  String name;
  int age;
  
  // Default Constructor
  Person(this.name, this.age);
  
  // Named Constructor
  Person.guest() {
    name = 'Guest';
    age = 0;
  }
}
```
### Static Method: 
A static method in Dart belongs to the class itself rather than to any instance of the class. It can be called without creating an instance of the class. Static methods are defined using the static keyword.Example of a static method in Dart:
```dart
class MathUtils {
  static int add(int a, int b) {
    return a + b;
  }
}

// Calling the static method
var result = MathUtils.add(5, 3);
```
### Getter and Setter: 
Getters and setters are used to control access to the private instance variables of a class. Getters retrieve the value of a variable, and setters modify the value of a variable. In Dart, getters and setters are defined using the get and set keywords respectively.Example of a getter and setter in Dart:
```dart
class Rectangle {
  double _width;
  double _height;
  
  // Getter for width
  double get width => _width;
  
  // Setter for width
  set width(double value) {
    if (value > 0) {
      _width = value;
    }
  }
  
  // Getter for height
  double get height => _height;
  
  // Setter for height
  set height(double value) {
    if (value > 0) {
      _height = value;
    }
  }
}
```
## Abstraction: 
Abstraction is the process of hiding the implementation details and showing only the essential features of the object. In Dart, abstraction can be achieved using abstract classes and methods.
## Inheritance: 
Inheritance is a mechanism where a new class inherits properties and behaviors from an existing class. This promotes code reusability and establishes a relationship between classes.
## Polymorphism:
Polymorphism allows objects of different classes to be treated as objects of a common superclass. In Dart, polymorphism is achieved through method overriding.
Here's an example that illustrates these concepts:

## OOP Example
```dart
// Abstraction: Define an abstract class
abstract class Shape {
  // Abstract method
  double calculateArea();
}

// Inheritance: Create subclasses that inherit from Shape
class Circle extends Shape {
  double radius;

  Circle(this.radius);

  @override
  double calculateArea() {
    return 3.14 * radius * radius;
  }
}

class Rectangle extends Shape {
  double width;
  double height;

  Rectangle(this.width, this.height);

  @override
  double calculateArea() {
    return width * height;
  }
}

// Polymorphism: Using objects of different classes through a common interface
void printArea(Shape shape) {
  print('Area of the shape: ${shape.calculateArea()}');
}

void main() {
  // Create objects of different shapes
  Circle circle = Circle(5);
  Rectangle rectangle = Rectangle(4, 6);

  // Print area of each shape
  printArea(circle); // Polymorphism: Circle treated as a Shape
  printArea(rectangle); // Polymorphism: Rectangle treated as a Shape
}

```
## Real life example
```dart
// Use Case: Student Grades

// Define the Student class representing individual students
class Student {
  final String name;
  final int grade;

  Student(this.name, this.grade);
}

// Abstract class representing a student repository
abstract class StudentRepository {
  void addStudent(Student student);
  List<Student> getAllStudents();
}

// Concrete implementation of StudentRepository using in-memory storage
class InMemoryStudentRepository implements StudentRepository {
  List<Student> _studentList = [];

  @override
  void addStudent(Student student) {
    _studentList.add(student);
  }

  @override
  List<Student> getAllStudents() {
    return List.from(_studentList); // Return a copy to prevent direct modification
  }
}

// Use Case: AddStudent - Represents the use case of adding a new student
class AddStudent {
  final StudentRepository _repository;

  AddStudent(this._repository);

  // Function to execute the use case
  void execute(String name, int grade) {
    _repository.addStudent(Student(name, grade));
  }
}

// Use Case: PrintStudents - Represents the use case of printing all students
class PrintStudents {
  final StudentRepository _repository;

  PrintStudents(this._repository);

  // Function to execute the use case
  void execute() {
    print("Students:");
    for (var student in _repository.getAllStudents()) {
      print("- ${student.name}: Grade ${student.grade}");
    }
  }
}

void main() {
  // Initialize StudentRepository with the concrete implementation
  var studentRepository = InMemoryStudentRepository();

  // Use cases
  var addStudent = AddStudent(studentRepository);
  var printStudents = PrintStudents(studentRepository);

  // Add some students
  addStudent.execute("Alice", 90);
  addStudent.execute("Bob", 85);
  addStudent.execute("Charlie", 95);

  // Print students
  printStudents.execute();
}

```
## Clean Concept
```dart
// Entities: Define domain objects representing individual students

class Student {
  final String name;
  final int grade;

  Student(this.name, this.grade);
}

// Use Cases: Define application-specific business logic

abstract class AddStudentUseCase {
  void execute(String name, int grade);
}

abstract class PrintStudentsUseCase {
  void execute();
}

class AddStudentInteractor implements AddStudentUseCase {
  final StudentRepository repository;

  AddStudentInteractor(this.repository);

  @override
  void execute(String name, int grade) {
    repository.addStudent(Student(name, grade));
  }
}

class PrintStudentsInteractor implements PrintStudentsUseCase {
  final StudentRepository repository;

  PrintStudentsInteractor(this.repository);

  @override
  void execute() {
    print("Students:");
    for (var student in repository.getAllStudents()) {
      print("- ${student.name}: Grade ${student.grade}");
    }
  }
}

// Data Access: Define interfaces for data storage

abstract class StudentRepository {
  void addStudent(Student student);
  List<Student> getAllStudents();
}

// Concrete implementation of StudentRepository using in-memory storage
class InMemoryStudentRepository implements StudentRepository {
  List<Student> _studentList = [];

  @override
  void addStudent(Student student) {
    _studentList.add(student);
  }

  @override
  List<Student> getAllStudents() {
    return List.from(_studentList); // Return a copy to prevent direct modification
  }
}

// Presentation: Wiring everything together

void main() {
  // Initialize StudentRepository with the concrete implementation
  var studentRepository = InMemoryStudentRepository();

  // Initialize use cases
  var addStudentUseCase = AddStudentInteractor(studentRepository);
  var printStudentsUseCase = PrintStudentsInteractor(studentRepository);

  // Add some students
  addStudentUseCase.execute("Alice", 90);
  addStudentUseCase.execute("Bob", 85);
  addStudentUseCase.execute("Charlie", 95);

  // Print students
  printStudentsUseCase.execute();
}

```
# Contribute
Together, we can achieve great things and create positive change in our community and beyond.So,If you're interested in contributing to this project, you are warmly welcomed! 🎁

## 🚀  Follow
[![LinkedIn](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/arrahmanbd)
[![GitHUb](https://img.shields.io/badge/Github-22272e?style=for-the-badge&logo=github&logoColor=white)](https://www.github.com/arrahmanbd)
[![Facebook](https://img.shields.io/badge/Facebook-0A66C2?style=for-the-badge&logo=facebook&logoColor=white)](https://www.facebook.com/arrahman.dev)


## Badges
[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)





