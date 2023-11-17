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

describe("Test Suite",()=>{
  
  
it("Fixed tests",()=>{
      
    assert.strictEqual(hacheTest(12,1000), "let's go the restaurant!");
    assert.strictEqual(hacheTest(1,3000), "No meal for you !!");
  })

  
it("Random tests", () => {  
function  hacheTestSol(students , objective){
  return (((objective/students)/7) <=80) ? "let's go the restaurant!" : "No meal for you !!";
}
  
function getRandomNumber(min, max) {
  return Math.floor(Math.random() * (max + 1 - min) + min);
}
for (var i = 0; i < 50; i++) {
  var students = getRandomNumber(1, 10000); // generator for students number
  var objective = getRandomNumber(1, 10000); // // generator for objectives even inputs
  console.log() ;
  Test.assertEquals(hacheTest(students, objective), hacheTestSol(students, objective));
}
})
})
```

## Exemple test case

```
const chai = require("chai");
const assert = chai.assert;

describe("Fixed Tests", function() {
  it("Basic Test Cases", function() {        
    assert.strictEqual(hacheTest(12,3000), "let's go the restaurant!");
    assert.strictEqual(hacheTest(6,1500), "let's go the restaurant!");
    assert.strictEqual(hacheTest(12,1000), "let's go the restaurant!");
    assert.strictEqual(hacheTest(1,3000), "No meal for you !!");
    assert.strictEqual(hacheTest(0,3000), "No meal for you !!");
    assert.strictEqual(hacheTest(1,0), "let's go the restaurant!");
  })
});
```