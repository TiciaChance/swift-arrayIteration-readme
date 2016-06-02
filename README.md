# Array - Iteration

<img src="http://vignette4.wikia.nocookie.net/gameofthrones/images/b/b8/Hodor_1x04.jpg/revision/latest?cb=20110525185057" alt="Drawing" style="width: 200px;"/>  


> Hodor. 

## Learning Objectives - The student should be able to..

* Explain the problem they are solving by being able to iterate over values in an `Array`.
* Create a `for-in` loop to iterate over an `Array`.

```swift
let friends = ["Chris", "Billy", "Jessica"]

for friend in friends {
    print("Hello \(friend)")
}

// Hello Chris
// Hello Billy
// Hello Jessica
```
* Explain that friend is a constant whose value is automatically set at the start of each iteration of the loop. They can't change this constant within the scope of the of the for loop.
* Explain that the type of the constant friend is of type `String` because the `friends` array is of type `[String]`. They should be able to see this by typing this into a playground file and option clicking the friend Constant to see its signature.
* Iterate over an `Array`, do something with the elements in the array and append them to a new array like so:

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

* Understand that they can use `for-in` loops within a function to perform any calculation on the elements within that array passed into the function as an argument like so:

```swift
func numberOfStudentsWhoGotA100OnExam(grades: [Int]) -> Int {
    var studentsWith100 = 0
    
    for grade in grades {
        if grade == 100 {
            studentsWith100 += 1
        }
    }
    
    return studentsWith100
}

let gradesFromExam = [80, 75, 79, 92, 94, 100, 83, 100]

numberOfStudentsWhoGotA100OnExam(gradesFromExam) // 2
```

## What the student can do at this point 

* Create variables and constants
* Is familiar with type annotations, type inference and string interpolation.
* Can create functions with return types.
* Is familiar with the String, Int, Double, and Bool type.
* Can perform arithmetic operations on Int and Double.
* Understands if and else clause statements.

## Outline / Notes

*  Covering what is outlined in the Learning Objective needs to be done in an explicit manner. When showing them anything in code, we need to be thorough in our explanations as if we're iterating this to a 12 year old. I think this topic introduces a lot of what they can now do and might derail a few.
* To get around that, I think we build up slowly to harder examples making sure they get the basics down.
* I think in first showing them a `for-in` loop, we do so by having them follow along in a playground file, and adding a print function to see how/when stuff gets called like so.

```swift
let characters = ["Joy", "Sadness", "Bing Bong", "Fear", "Anger", "Disgust", "Riley"]

for character in characters {
    print(character)
}

// Riley
// Joy
// Sadness
// Bing Bong
// Fear
// Anger
// Disgust
```

* It's very good for them to know that they can place print functions throughout their methods to see when stuff is getting called and to get a handle of the flow. It's a great way for them to understand what's going on but also a good habit for them to make when they need to debug their code... WHY isn't this working.. well they might be making a ton of assumptions where adding print functions everywhere might help them decipher WHERE the problem is.

```swift
func didWeIncludeRileyInCharacters(characters: [String]) -> Bool {
    print("Function has been called, we're about to go into the for loop.")
    
    for character in characters {
        print("We are inside the for loop, character: \(character)")
        
        if character == "Riley" {
            print("Inside the if statement where character is equal to Riley.")
            print("About to return true.")
            return true
        }
    }
    
    print("End of our function, about to return false.")
    return false
}

didWeIncludeRileyInCharacters(characters)

// Function has been called, we're about to go into the for loop.
// We are inside the for loop, character: Joy
// We are inside the for loop, character: Sadness
// We are inside the for loop, character: Bing Bong
// We are inside the for loop, character: Fear
// We are inside the for loop, character: Anger
// We are inside the for loop, character: Disgust
// We are inside the for loop, character: Riley
// Inside the if statement where character is equal to Riley.
// About to return true.
```
* You can ask them... what do you think would print if we were to add Riley to the front of the array instead of being at the end. Also, what would print if we removed Riley from this array. Ask them to walk through it in their head to see if they can figure it out BEFORE they make the attempt at writing the code
 


<a href='https://learn.co/lessons/ArrayIteration' data-visibility='hidden'>View this lesson on Learn.co</a>
