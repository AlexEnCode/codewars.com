https://www.codewars.com/kata/65577d4c9396b30679576d53

## task

Hache just met his new `students` in JavaScript.
He wants to challenge them !
If they do their `objective` in one week, he will take them to the restaurant!

Take care, students can't do more than 80 katas per day. Exceptionaly, they will work every day of the week.

If they complete enough kata, Hache will say `"let's go the restaurant!"`, if not he will say `"No meal for you !!"`.

Create a function to find what Hache is going to say. 

Be carefull, the number you are looking for has to be an `integer`. 



## Example

```
students = 12 ; \\ The number of students

objective = 3000 ; \\ The number of katas the class needs to score.

( The minimum number of kata each students has to make is 36. )

Hache : "let's go the restaurant!"

```




## Initial solution

```
function  hacheTest(students , objective){
  // your code 
}
```


## Complete solution
```
function  hacheTest(students , objective){
  return ((objective/students)/7) <=80 ? "let's go the restaurant!" : "No meal for you !!";
}
```

## Test case

```
const Test = require('@codewars/test-compat');
const chai = require("chai");
const assert = chai.assert;

function hacheTest(students, objective) {
  if (students === 0 || objective === 0) {
    return "let's go the restaurant!";
  }

  return students * 80 * 7 > objective ? "let's go the restaurant!" : "No meal for you !!";
}

describe("Test Suite", () => {
  
  
    it("Basic Test Cases", function() {        
      assert.strictEqual(hacheTest(12, 3000), "let's go the restaurant!");
      assert.strictEqual(hacheTest(6, 1500), "let's go the restaurant!");
      assert.strictEqual(hacheTest(12, 1000), "let's go the restaurant!");
      assert.strictEqual(hacheTest(1, 3000), "No meal for you !!");
      assert.strictEqual(hacheTest(0, 3000), "let's go the restaurant!");
      assert.strictEqual(hacheTest(1, 0), "let's go the restaurant!");
      });

  it("Random tests", () => {  
    function hacheTestSol(students, objective) {
      return students * 80 * 7 > objective ? "let's go the restaurant!" : "No meal for you !!";
    }

    function getRandomNumber(min, max) {
      return Math.floor(Math.random() * (max + 1 - min) + min);
    }

    for (var i = 0; i < 50; i++) {
      var students = getRandomNumber(1, 50);
      var objective = getRandomNumber(1, 5000);

      console.log("Test Case:", i + 1);
      console.log("Students:", students);
      console.log("Objective:", objective);

      var result = hacheTest(students, objective);
      var expectedResult = hacheTestSol(students, objective);

      console.log("Result:", result);
      console.log("Expected Result:", expectedResult);

      Test.assertEquals(result, expectedResult);
    }
  })
});
```

## Exemple test case

```
const chai = require("chai");
const assert = chai.assert;

describe("Fixed Tests", function() {
  it("Basic Test Cases", function() {        
    function runTest(students, objective, expected) {
      const result = hacheTest(students, objective);
      if (result !== expected) {
        console.log(`Test failed for Students: ${students}, Objective: ${objective}`);
        console.log(`Expected: ${expected} | Actual: ${result}`);
      }
      assert.strictEqual(result, expected);
    }

    // Test 1
    runTest(12, 3000, "let's go the restaurant!");

    // Test 2
    runTest(6, 1500, "let's go the restaurant!");

    // Test 3
    runTest(12, 1000, "let's go the restaurant!");

    // Test 4
    runTest(1, 3000, "No meal for you !!");

    // Test 5
    runTest(0, 3000, "No meal for you !!");

    // Test 6
    runTest(1, 0, "let's go the restaurant!");
  });
});
```