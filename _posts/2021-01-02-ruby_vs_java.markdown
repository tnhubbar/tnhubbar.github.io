---
layout: post
title:      "Ruby Vs. Java"
date:       2021-01-02 20:20:47 +0000
permalink:  ruby_vs_java
---


Educationally, Ruby in the language that I learned on my journey of learning software development. And I think Ruby is a very beginner friendly language. But when looking for jobs, I noticed that there are a lot of Java jobs out there hanging around so that got me curious as to the major differences between these 2 languages. 

The **main difference **is that Ruby is an interpreted scripting language, whereas Java is a compiled programming language. Ruby is run directly without first compliling and generating the cody. This means that a ruby file could be run with the following command. 

``` run rubyfile.rb ``` 

With Java being a compiled programing language, this means the applications are required to be compiled before running. For example, a Java class javafile.java is first compiled with a javac compiler with the following command 

``` javac javafile.java ```

This generates the byte code for the Java class. And then the compiled class may be run with the java.exe application. 

``` java javafile.java ```

Another difference that I had to get used to use with Java was typed variables. 

The are similar in that they are both object-oriented languages. In Ruby typed variables are not used. In Java, they are required.  They are both typed languages, but in Ruby variables do not have an explicit type associated with them. For example, a variable that's a string can be declared like this: 

``` strng = "My ruby string" ```
or it could also be assigned to an interger: 

``` strng = 1 ``` 

In Java, variables are statically typed and have a type associated with them. For example, a string variable is declared like this: 

``` String strng= "My Java String" 
And this cannot be assigned to an integer value. 

A similarity between them is that they are both object oriented languages. But there a few differences. In Ruby, everything is an object , including numbers, variables, and methods. In Java, only classes have objects. For example, an object of type Class1 is created as follows. 

``` Class1 class1= new Class1();  ``` 

The last difference that I felt was very significant was Member variables. In Ruby, all member variables are private, but in Java they have package access by default and can be declared as public, private, or protected with an identifier that is placed at the beginning. Private members may be accessed only within the class itself, public members may be access by any other class, and protected may be accessed within the same package as the class declaring them and in the subclasses of the class. 

