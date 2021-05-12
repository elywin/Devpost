---
layout: post
title: Unit Testing
---
**What is Unit Testing?**<br>
UNIT TESTING is a type of software testing where individual units or components of a software are tested.

The purpose is to validate that each unit of the software code performs as expected. Unit Testing is done during the development (coding phase) of an application. Unit Tests isolate a section of code and verify its correctness, a unit may be an individual function, method, procedure, module, or object.

**Why Unit Testing?**

- Unit tests help to fix bugs early in the development cycle and save costs( test parts of the project without waiting for others to be completed).
- It helps the developers to understand the testing code base and enables them to make changes quickly
- Good unit tests serve as project documentation
- Unit Testing allows developers to learn what functionality is provided by a unit and how to use it to gain(code re-use).

**Types of unit testing**
- Manual
- Automated

> `The automated method is the most preferred as it is faster and more accurate, but performing this task manually is also an option`

Under the automated approach-<br>
A coder uses a UnitTest Framework to develop automated test cases. Using an automation framework, the developer codes criteria into the test to verify the correctness of the code. During execution of the test cases, the framework logs failing test cases and also automatically flag and report these failed test cases. Depending on the severity of a failure, the framework may halt subsequent testing.

**Unit Testing Techniques**

- [Black Box Testing](https://www.tutorialspoint.com/software_testing_dictionary/black_box_testing.htm) - involves testing of user interface along with input and output.

- [White Box Testing](https://www.tutorialspoint.com/software_testing_dictionary/white_box_testing.htm) - involves testing the functional behaviour of the software application.

- [Gray Box Testing](https://www.tutorialspoint.com/software_testing_dictionary/grey_box_testing.htm) - used to execute test suites, test methods, test cases and performing risk analysis.

**Unit Testing Tools**

- [PHPUnit](https://phpunit.de/): PHPUnit is a unit testing tool for PHP language.
- [NUnit](https://nunit.org/):  NUnit is widely used unit-testing framework use for all .net languages.
- [JMockit](http://jmockit.github.io/index.html):  JMockit is open source Unit testing tool. 
- [Junit](https://www.guru99.com/junit-tutorial.html): Junit is a free to use testing tool used for Java programming language.
-[EMMA](http://emma.sourceforge.net/):  EMMA is an open-source toolkit for analyzing and reporting code written in Java language.

**Unit Testing Best Practices**

- Unit Test cases should be independent. In case of any enhancements or change in requirements, unit test cases should not be affected.
- Test only one code at a time.
- Follow clear and consistent naming conventions for your unit tests
- In case of a change in code in any module, ensure there is a corresponding unit Test Case for the module, and the module passes the tests before changing the implementation
- Bugs identified during unit testing must be fixed before proceeding to the next phase in SDLC
- Adopt a "test as your code" approach. The more code you write without testing, the more paths you have to check for errors.