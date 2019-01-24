# Introduction to Programming with JavaScript 2

## Table of Contents

* [Notes](#notes)

* [Overview](#overview)

* [Review](#review)

* [Arrays](#arrays)
  * [The Array Prototype](#the-array-prototype)
  * [The String Prototype](#the-string-prototype)

* [Objects](#objects)
  * [Defining Objects](#defining-objects)
  * [Accessing Object Properties](#accessing-object-properties)

* [Additional Resources](#additional-resources)

## Notes

* This class builds on the topics presented in Intro to Programming with Javascript 1, including:
	* Basic data types
	* Variables
	* Conditionals (if/else statements)
	* Functions
	* Loops
* Don't worry if you're not an expert in these, but hopefully they sound familiar
* We'll be using a free, online tool called [repl.it](https://repl.it/languages/javascript) to run our code.  On the left is a place to write code and on the right is the __*console*__ which will show us the output of our programs.
* Something we'll be using pretty regularly is `console.log()` - it looks pretty fancy, but all it does is print what's put in the parenthesis to the console.
* JavaScript is case sensitive and cares about punctuation.  `heyThere`, `HeyThere`, `hey_there`, and `Hey_There` are all different to JavaScript.
* Comments are great to add notes to code. You can tell other programmers how to use your programs or even remind yourself what you were thinking when your wrote the code initially. To add a comment, you'll start a line with `//` and everything after that on the same line with be a comment.

``` javascript
// This is a comment in JavaScript
// I really want the console to print "Hello World!"
console.log("Hello World!");
```

## Overview
Today we'll be looking at two important data types in Javascript, __*Arrays*__ and __*Objects*__.   They're both considered *composite* data types because they're made up of other data types.  Just like the other data types we've learned about, these two have analogues in most other programming languages.


Cool, let's get down to it!



## Review
__Rapid fire questions!__
* What's a variable?
* What are three kinds of data types? Come up with an example for each one.
* What's an "if statement"?
* What's a function and why are they useful?
* What's a loop?  What types of loops can you think of?

__Activity__:
Create a function that takes in a number (e.g. 4) and adds up all the whole numbers from 1 to that number (e.g. 4 + 3 + 2 + 1 = 10).


## Arrays
Arrays are container-like values that can hold other values. The values inside an array are called elements.

``` javascript
const breakfast = ["coffee", "croissant"];
```

To access one of the elements inside an array, you’ll need to use the brackets and a number like this: myArray[3].  This number is called an `index` and it's like an address to access elements in your array. __Important__: Javascript arrays begin at 0, so the first element will always be inside [0]:

``` javascript
console.log(breakfast[0]);
// --> "coffee"
```

And there's nothing stopping you from using a number variable as your index:

``` javascript
const myIndex = 1;
console.log(breakfast[myIndex]);
// --> "croissant"
```

__Activity:__

Make an array of strings where the strings are your grocery list (e.g. "eggs").  Then we'll practice accessing the array to get certain items out of it.

### The Array Prototype
You can think of a *prototype* in Javascript as a blueprint for different data types.  What this means is each data type (arrays in this example) have certain properties and functions (also known as "methods") available to them.
* Example 1: `length` is used to check how many elements an array has
	* `console.log(breakfast.length);` ==> 2
* Example 2: `push()` is used to add elements onto an existing array
	* `breakfast.push("OJ");`
	* `console.log(breakfast);` ==> `["coffee", "croissant", "OJ"]`
* Example: 3: `reverse()` is used to, you guessed it, reverse the order of an array
	* `const reversedBreakfast = breakfast.reverse()`
	* `console.log(reversedBreakfast);` ==> `["OJ", "croissant", "coffee"]`

There are lots more; see the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/prototype) for more examples.


__Activity #1:__

Starting with an array `[1, 2, 3]` and applying some of what we just learned, how could I get an array `[10, 3, 2, 1]`?


__Activity #2:__

Knowing what you know about accessing array elements and the `length` property, what's a surefire way to access the *last* element of an array?


__Activity #3:__
Using a loop (e.g. a for-loop), iterate over your grocery list and log each item individually.


__Activity #4:__
Building on your answer from #3, how could we filter the array to only contain elements that start with the letter "C"?


### The String Prototype
Just like the Array prototype, there is a String prototype.  There's some overlap, too -- we can find out how many characters are in a string by using the `.length` property, just like with arrays!  Here's a couple more:
* Example 1: `toLowerCase()` and `toUpperCase()`
	* `"WHY ARE WE YELLING?".toLowerCase()` ==> `"why are we yelling?"`
* Example 2: `split()`
	* `const letters = "abc".split();`
	* `console.log(letters);` ==> `["a", "b", "c"]`
* Example 3: `split(separator)`
	* This is a variant of the last one, but now we can specify how elements should be separated.
	* `const words = "The dog jumped over the fence, I heard".split(" ")`
	* Notice the space between the quotes in the above `split` function
	* `console.log(words)` ==> `["The", "dog", "jumped", "over", "the", "fence,", "I", "heard"]`


To learn more about the String prototype methods, see the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/prototype).

__Activity #1:__
Write a function that takes in a sentence as a string and returns an array of the words in that sentence. Bonus activity if you finish: try modifying the function to return the number of words in the sentence.



## Objects
You may not know it, but we've been using objects all along.  An object is a collection of properties, and a property is an association between a name (or key) and a value.  Cool, what's that mean?  Let's look at a basic (empty) object:

`const myObj = {};`


### Defining Objects

That's it.  But let's make it more interesting by adding a `property` which you can think of as a label and the value associated with that label:

``` javascript
const myDog = {
  paws: 4,
  sound: "woof woof"
};
```

Functions can also be properties.  When we do this, the function is called a *method*:
``` javascript
const myDog = {
  paws: 4,
  sound: "woof woof",
  sayHello: function() {
    console.log("Woof woof!");
  }
};
```

And there's nothing stopping us from having properties that are arrays or even other objects (often referred to as *nested objects*).  Pretty cool huh?  Let's practice!


__Activity #1:__

Let's start off by making a simple object with at least 3 properties representing qualities of your favorite actor or musician. You can choose any properties you want but `name`, `age`, or `films` would be a good place to start.


### Accessing Object Properties
So we have our object, but how do we access its values?  There are two ways:
 1. Dot Notation
	* `myDog.paws` ==> `4`
 2. Bracket Notation
	* `myDog["paws"]` ==> `4`

Both do the same thing but Dot Notation is easier to read and more common. The advantage of Bracket Notation is that it allows us to use strings (and therefore, variables) as keys.
* ✔ => `myDog["favorite toy"] = "squeaky mermaid squirrel";`
* ✖ => `myDog.favorite toy = "squeaky mermaid squirrel";` ==> this will throw an error
* More info about the differences and use cases [here](https://codeburst.io/javascript-quickie-dot-notation-vs-bracket-notation-333641c0f781).


__Activity #2:__

Let's keep going -- make a couple more actor objects and put them inside of an array.  Iterate over (loop through) this array and console.log out their names.


__Activity #3:__
I'll provide you with an array of objects representing users in a fictional system.  Iterate over all of the users and filter the list so we end up with array of only the admins in our system.


## Additional Activities (Advanced!)

__Bonus Activity #1:__

A slug in web development refers to the hyphen-separated text you see in a URL, for example in the URL `www.hello.com/greetings/it-is-nice-to-meet-you` the slug is `it-is-nice-to-meet-you`.  Write a "de-slugify" function that takes in a slug and does its best to return a human readable string.  Hint: the Array prototype method `split()` is your friend.


__Bonus Activity #2:__
Create a function that repeats a string `x` amount of times, where `x` is a positive number.  For example, `repeatify("ha", 3)` returns `"hahaha"`.  Once you've got the function, add it as a method to the String prototype.  [(Answer here)](https://www.sitepoint.com/5-typical-javascript-interview-exercises/)


__Bonus Activity #3:__
Using the `filter` method on the Array prototype [(info here)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter), filter out all negative values from the following array: `[414, -19, 54, -2913, 0, 882, 124, -0.001]`.



## Additional Resources

* [Free Code Camp](https://www.freecodecamp.com/) is a free, online program for learning HTML, CSS, and JavaScript (the three technologies you need to know to make custom websites).
* [Codecademy](https://www.codecademy.com/learn) has free programming courses in several programming languages - including a bunch of courses in JavaScript.
* [Khan Academy](https://www.khanacademy.org/computing/computer-programming) has a ton of free resources to help you learn to be a better programmer.
* [Code Wars](https://www.codewars.com) is a great way to increase your JavaScript skills once you've completed a more in depth JavaScript course. You learn to program by solving programming puzzles and they have puzzles for all levels of programmers!
* [CodeSchool](https://www.codeschool.com/learn/javascript) is a paid site similar to Codeacademy that has interactive practice.
* [Meetups](http://www.meetup.com/) are a great way to meet people in the community and learn in-person, asking questions or seeing what other people are learning and working on.
* [Youtube](https://www.youtube.com/results?search_query=introduction+to+javascript) is great if you're a visual learner like myself.
* Google!  Professional developers google things all the time!
* [Phaser](https://phaser.io/) is a tool for making browser games using JavaScript.  If you're interested in making visual games and have a good grasp on the fundamentals of the language, this is a great library!
