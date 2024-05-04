
![Awesome ReadME](https://github.com/pottekkat/awesome-readme/raw/master/header.png)
 
# Dart Programming Guide

[![GitHub release (latest by date including pre-releases)](https://img.shields.io/github/v/release/navendu-pottekkat/awesome-readme?include_prereleases)](https://img.shields.io/github/v/release/navendu-pottekkat/awesome-readme?include_prereleases)
[![GitHub last commit](https://img.shields.io/github/last-commit/navendu-pottekkat/awesome-readme)](https://img.shields.io/github/last-commit/navendu-pottekkat/awesome-readme)
[![GitHub issues](https://img.shields.io/github/issues-raw/navendu-pottekkat/awesome-readme)](https://img.shields.io/github/issues-raw/navendu-pottekkat/awesome-readme)
[![GitHub pull requests](https://img.shields.io/github/issues-pr/navendu-pottekkat/awesome-readme)](https://img.shields.io/github/issues-pr/navendu-pottekkat/awesome-readme)
[![GitHub](https://img.shields.io/github/license/navendu-pottekkat/awesome-readme)](https://img.shields.io/github/license/navendu-pottekkat/awesome-readme)

Dart is a modern, object-oriented programming language developed by Google. It is known for its simplicity, efficiency, and versatility. Dart is primarily used for building web, mobile, and server-side applications.

 
## Table of Contents

- [Dart Programming Guide](#dart-programming-guide)
  - [Table of Contents](#table-of-contents)
- [Basic Information](#basic-information)
- [Basic Syntax](#basic-syntax)
- [Variables and Data Types](#variables-and-data-types)
- [Control Flow Statements](#control-flow-statements)
- [Functions](#functions)
- [Classes and Objects](#classes-and-objects)
- [Exception Handling](#exception-handling)
- [Asynchronous Programming](#asynchronous-programming)
- [Libraries and Packages](#libraries-and-packages)
- [Dart Collection](#dart-collection)
  - [List methods \[for\]:](#list-methods-for)
  - [Method \[for-in\]](#method-for-in)
  - [Method \[for-each\]](#method-for-each)
  - [Method \[for-in\]](#method-for-in-1)
  - [Method \[where in\]](#method-where-in)
  - [Method \[map\]](#method-map)
  - [Find the common](#find-the-common)
- [Sum of a List](#sum-of-a-list)
- [Sorting a List](#sorting-a-list)
  - [Map sorting](#map-sorting)
  - [Object soring](#object-soring)
- [String replacer](#string-replacer)
  - [Empty or null check](#empty-or-null-check)
- [Object into Bytes:](#object-into-bytes)
  - [decode](#decode)
- [Try Catch](#try-catch)
  - [Exception](#exception)
- [Contribute](#contribute)

# Basic Information
[(Back to top)](#table-of-contents)

# Basic Syntax
Dart syntax is easy to understand and resembles many other C-style languages. It includes features such as variables, data types, operators, and comments. Refer to Basic Syntax for detailed information.

# Variables and Data Types
In Dart, variables are used to store data values. Dart supports various data types including integers, doubles, strings, booleans, lists, and maps. Learn more about Variables and Data Types.

# Control Flow Statements
Control flow statements in Dart allow you to control the flow of your program execution. Dart supports if-else statements, switch statements, loops, and more. Check out Control Flow Statements for examples and explanations.

# Functions
Functions are a fundamental building block of Dart programming. They allow you to encapsulate code for reuse and modularity. Learn how to define and use functions in Dart in the Functions section.

# Classes and Objects
Dart is an object-oriented programming language, which means it supports classes and objects. Classes are used to create objects with properties and methods. Explore Classes and Objects to understand how to work with them in Dart.

# Exception Handling
Exception handling is crucial for writing robust and error-tolerant code. Dart provides try-catch-finally blocks to handle exceptions gracefully. Read more about Exception Handling to learn how to handle errors in Dart programs.

# Asynchronous Programming
Dart offers built-in support for asynchronous programming, which is essential for handling operations such as I/O, networking, and timers without blocking the main thread. Dive into Asynchronous Programming to understand Dart's asynchronous features.

# Libraries and Packages
Dart comes with a rich set of standard libraries for common programming tasks. Additionally, you can use third-party packages from pub.dev to extend Dart's functionality. Discover more about Libraries and Packages in Dart.

 
# Dart Collection
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
## decode
```dart
final map = {'key1': 'foo bar', 'key2': 123, 'key3': 'more'};

  const jsonCodec = JsonCodec();

  final jsonMap = jsonCodec.encode(map);
  final bytesMap = const Utf8Codec().encode(jsonMap);
  if (kDebugMode) {
    print(bytesMap);
  }
```
# Try Catch

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

## Exception
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
# Contribute
[(Back to top)](#table-of-contents)

Contributions are welcome



