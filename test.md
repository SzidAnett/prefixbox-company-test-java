# Prefixbox Test

## Short questions

- What is a package? How do you define a package?
	A package in Java is used to group related classes.
	Think of it as a folder in a file directory. 
	We use packages to avoid name conflicts, and to write a better maintainable code. 
	Packages are divided into two categories:
		Built-in Packages (packages from the Java API)
		User-defined Packages (create your own packages)

- What is a constructor? When is it executed?
	A constructor in Java is a special method that is used to initialize objects.
	The constructor is called when an object of a class is created.

- How do you implement inheritance in Java?
	To inherit from a class, use the extends keyword.
	In Java, it is possible to inherit attributes and methods from one class to another.
	We group the "inheritance concept" into two categories:
	subclass (child) - the class that inherits from another class
	superclass (parent) - the class being inherited from

- How do you prevent someone to inherit from a class?
	If you don't want other classes to inherit from a class, use the final keyword
	
- What is a final variable? Where you can assign value to final variables?
	A non-access modifier used for classes, attributes and methods, 
	which makes them non-changeable (impossible to inherit or override)
	The final keyword is useful when you want a variable to always store 
	the same value, like PI (3.14159...).
	The final keyword is called a "modifier".
	In Java, non-static final variables can be assigned a value either in constructor 
	or with the declaration. But, static final variables cannot be assigned value in constructor;
	they must be assigned a value with their declaration.

- Specify the available access modifiers in Java and briefly explain them
	Default – No keyword required	
		When no access modifier is specified for a class , method or data member – 
		It is said to be having the default access modifier by default.
		The data members, class or methods which are not declared using 
		any access modifiers i.e. having default access modifier are accessible only within the same package.

	Private
		The private access modifier is specified using the keyword private.
		The methods or data members declared as private are accessible only within the class in which they are declared.
		Any other class of same package will not be able to access these members.
		Top level Classes or interface can not be declared as private because
		private means “only visible within the enclosing class”.
		protected means “only visible within the enclosing class and any subclasses”
		Hence these modifiers in terms of application to classes, they apply only to nested classes and not on top level classes
		
	Protected
		The protected access modifier is specified using the keyword protected.
		The methods or data members declared as protected are accessible within 
		same package or sub classes in different package.
		
	Public
		The public access modifier is specified using the keyword public.
		The public access modifier has the widest scope among all other access modifiers.
		Classes, methods or data members which are declared as public are accessible from every where in the program. 
		There is no restriction on the scope of a public data members.

- Briefly explain the mechanism of exception handling
	The Exception Handling in Java is one of the powerful mechanism to handle the runtime errors
	so that normal flow of the application can be maintained.

- What is the difference between an abstract class and an interface?
	Main difference is methods of a Java interface are implicitly abstract and cannot have implementations. 
	A Java abstract class can have instance methods that implements a default behavior.
	Variables declared in a Java interface is by default final. An  abstract class may contain non-final variables.
	Members of a Java interface are public by default. A Java abstract class can have the usual flavors of class members like private, protected, etc..
	Java interface should be implemented using keyword “implements”; A Java abstract class should be extended using keyword “extends”.
	An interface can extend another Java interface only, an abstract class can extend another Java class and implement multiple Java interfaces.
	A Java class can implement multiple interfaces but it can extend only one abstract class.
	Interface is absolutely abstract and cannot be instantiated; A Java abstract class also cannot be instantiated, but can be invoked if a main() exists.
	In comparison with java abstract classes, java interfaces are slow as it requires extra indirection.
		
- What is the difference between Comparator and Comparable?
	Comparable provides compareTo() method to sort elements in Java whereas Comparator provides compare() method to sort elements in Java.
	Comparable interface is present in java.lang package whereas Comparator interface is present in java.util package.
	Comparable provides single sorting sequences while Comparator provides multiple sorting sequences.
	Comparable affects the original class whereas comparator doesn't affect the original class.

- How Iterable and Iterator interface works? What methods need to exist in a
class that implements them? What is their relation to for loops?
	Every class that implements Iterable interface appropriately, can be used in the enhanced For loop (for-each loop). 
	The need to implement the Iterator interface arises while designing custom data structures.

## Programming tasks

You can write your solutions in any language, you can even write pseudo code or
using only your own words.
The point is not to make a perfectly running application, the point is the way
you think!
Don't worry if you miss a semicolon or some parantheses.
You might use the Java stream API for your solutions but none of the exercises
require them

### Palindrom

Write a function which decides whether a text is palindrom(It's the same whether
you read it forwards or backwards). E.g.: abba, rotator, stats.
You might assume that the input string is not null, the length is greater than
1 and less than one million. **Strive for the low memory complexity!**

Example:

```java
public boolean isPalindrom(String input) {

}

isPalindrom("alma"); //false
isPalindrom("görög"); //true
```

### Find The Duplicate

You have an array that contains strings. Every item in the array is
unique except one which is present in the array exactly twice.
Write a function which finds the string that is present twice in the array.
You might assume that the input array is not null, the length is greater
or equal to 2 and less than one million. **Strive for the low time complexity!**

Example:

```java
public String findTheDuplicate(String[] input) {

}

String[] fruitBasket = new String[] { "apple", "banana", "coconut", "durian",
"banana", "elderberry", "fig", "grapefruit" };
findTheDuplicate(fruitBasket); //should return banana
```

### Count The Words

You have a long string that has some meaning on a real language. For example a
whole novel in a single string.
Write a function that counts the occurence of each word inside the string and
writes them to the output in the following format: `word: number of occurences`
You might assume that the input is not null and not empty. The order of the
words on the ouput does not matter.
The solution might be case insensitive, you don't have to differentiate
bwetween capital and non-capital letters.
The punctuation marks and line endings are not part of the words!

Example:

```java
public void countTheWords(String crazyLongString) {

}

String boci = "Boci, boci tarka, se füle, se farka.";
countTheWords(boci);

//Output:
//boci:2
//tarka:1
//se:2
//füle:1
//farka:1
```

### What Is The Output

What is the output of the following Java application? Explain your solution!

```java
package com.mycompany.myproject;

public class Person {
    public String firstName;
    public String lastName;

    public Person(String firstName, String lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }  

    @Override
    public String toString() {return this.firstName + " " + this.lastName;}
}

public class Main {
    public static void main(String[] args) {
        int i = 0;
        String s = "apple";
        Person p = new Person("Jonh", "Doe");

        doSomething(i, s, p);

        System.out.println(i);
        System.out.println(s);
        System.out.println(p);
    }

    public static void doSomething(int i, String s, Person p)
    {
        i = 5;
        s += "banana";
        p.lastName = "Rambo";
    }
}

```

## SQL

- What is the PRIMARY KEY?
- What is the difference between CLUSTERED INDEX and NONCLUSTERED INDEX?
- There is a table called `Employees`. Let's assume that the columns exist
and they have the right data type.
What is going to happen if we execute the script and we destroy
the database connection during the execution? What are the possible problems
that might occure?

```sql
BEGIN TRANSACTION

UPDATE Employees
SET Salary = Salary * 1.1
WHERE
    Salary < 250000
    AND IsActiveEmployee = 1
```

## Web and HTTP

- Specify the existing HTTP request methods and describe their usage!
- What are the groups of HTTP response status codes? Write an example for each group!
