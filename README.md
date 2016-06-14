# Array - Iteration

![Drawing](http://vignette4.wikia.nocookie.net/gameofthrones/images/b/b8/Hodor_1x04.jpg/revision/latest?cb=20110525185057)

> Hodor.

## Learning Objectives - The student should be able to.

- Explain the problem they are solving by being able to iterate over values in an `Array`.
- Create a `for-in` loop to iterate over an `Array`.


--------------------------------------------------------------------------------

## Improving Repetitive Tasks

In the last lesson you saw how to create and manipulate a collection of values. You also saw how to print individual items in that collection, so if you wanted to print a list of your three friends you could do the following:

```swift
let friends = ["Chris", "Billy", "Jessica"]
print (friends[0])
// "Chris"
print (friends[1])
// "Billy"
print (friends[2])
// "Jessica"
```

But what if you had 100 friends? Printing values like this will become tedious quickly and if you added more friends to the list, you would have to add more `print` commands to handle them.

Programming languages are very good at repetitive tasks, in fact they are better than humans, so in this lesson you will learn how to perform the same action(s) on values in an array multiple times. This is called _iterating over an array_ and introduces a new concept, a _loop_.

## Loops

```swift
let friends = ["Chris", "Billy", "Jessica"]

for friend in friends {
    print("Hello \(friend)")
}

// Hello Chris
// Hello Billy
// Hello Jessica
```

This examples starts with a familiar array initialization, but then instead of using the `print` command for each value in the array, says that `for` each value in the `friends` array, process the instructions in-between the `{}` symbols, which are called 'curly brackets' or 'mustaches'. In this example these instructions print the current value of `friend`, or the value of the current index in the `friends` array, in the order they appear in the array.

As `friends` is an array of type String, the type of `friend` will also be a String, and you can confirm this by typing the example above into a playground and _option + clicking_ `friend`.

![Array Type Inference](array-type-inference.png)

## Loops and Calculations

You typically use loops to undertake more complex repetitive processing than printing the value of a variable, such as calculations.

Say you have a list of numbers and want to know what the square of each one and add that value to a new list. You create one array containing the original list of numbers and a placeholder array for the list of squared numbers. Then iterate through the array containing the list of numbers, perform the necessary calculations to find it's square and add that value to the second array. Let's look at some code!

```swift
let numbers = [1, 2, 3, 4, 5]
var squaredNumbers: [Int] = []

for number in numbers {
    let squaredNumber = number * number
    squaredNumbers.append(squaredNumber)
}

print(squaredNumbers)
// prints "[1, 4, 9, 16, 25]"
```

For the first `numbers` array, you use the `let` keyword as you don't want to change the values in the array. As you don't know what the values of the second `squaredNumbers` array will be yet, you initialize it first with no values. Inside the `for in` loop you generate the square of the value at the current index of the array and assign it to another unchanging variable. The next line introduces something called a _method_, which you can think of as a pre-written convenient way of performing actions on something. In this particular case `.append` adds a new value to the end of the `squaredNumbers` array.

In the first iteration of the `for in` loop, `number`, which is of type `Int`, will have a value of 1\. The value of `number` is then squared (1 _1), assigned to the `squaredNumber` constant, and appended to the `squaredNumbers` array. During the second iteration, `number` will have a value of 2 and the squared value will be 4 (2_ 2). This value is then assigned to a `squaredNumber` constant and appended to the `squaredNumbers` array. The same process continues until the array is fully iterated.

This last example introduced a couple of new concepts, if you want to understand better what a line of code is doing then feel free to add `print` and `if` statements to inspect values (this is called 'debugging'). For example to see the value of `squaredNumber` you could add `print (squaredNumber)` inside the loop.

Maybe one of your friends deserves a special mention for being so awesome, so you need to find them in the `friends` list, and when you do, print a message for them:

```swift
let friends = ["Chris", "Billy", "Jessica"]

for friend in friends {
    print("We are inside the for loop, friend: \(friend)")

    if friend == "Billy" {
        print("Hello \(friend), you are awesome!")
    }
}

// We are inside the for loop, friend: Chris
// We are inside the for loop, friend: Billy
// Hello Billy, you are awesome!
// We are inside the for loop, friend: Jessica
```

In the above, you iterate the `friends` list printing the value of each index in the array. If the current value is equal to "Billy", then inside an if statement you print them a special greeting.

## Loops and Functions

In unit 1, lesson 8 you learned about functions, a convenient way to package functionality into reusable components. You can add any code can into a function, including loops.

Say for example you want to know how many of your friends got over 70 in their recent exam.

You first create an array of their grades and pass that array to a function. That function iterates through the array and maintains a count of how many grades were above 70, and returns that value.

```swift
func numberOfFriendsAbove70(grades: [Int]) -> Int {
    var studentsAbove70 = 0

    for grade in grades {
        if grade >= 70 {
            studentsAbove70 += 1
        }
    }

    return studentsAbove70
}

let gradesFromExam = [80, 45, 79, 32, 84, 100, 53, 60]

print numberOfFriendsAbove70(gradesFromExam)
// 4
```

Again, there's a lot happening in this example, so let's break everything down by starting at the bottom of the code. First you create an array called `gradesFromExam` of your friends grades that can't change and then pass that array to the `numberOfFriendsAbove70` function and print the returned result.

At the declaration of the `numberOfFriendsAbove70` function you set the incoming parameter (accessed by the `grades` variable) as an array of numbers and the return value as a single number. Inside the function you first initialize to 0 a variable to count the number of grades over 70.

Next iterate through each value in the `grades` array and if the value at the current index is greater than 70 increase the value of `studentsAbove70` by 1\. Once the array has been fully iterated, return the total value or `studentsAbove70`.

Have a good look at the code above as it introduces a lot of new, but essential concepts. Try this code in a playground and add some `print` commands to see if your understanding of it matches the practical application.

[View this lesson on Learn.co](https://learn.co/lessons/ArrayIteration)
