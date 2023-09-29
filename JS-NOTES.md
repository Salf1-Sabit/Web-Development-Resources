## Bible of Javascript (book)

[ Link to the book ](https://drive.google.com/file/d/1CEoFEEVuaOQ2cBYIBS2bBlGEqV5vg7A7/view?usp=drive_link)

## Javascript Mastery (notes)

1.  By default “list, object, function” copy works like a reference copy.
    This means, that if B is a copy of list A then, any changes made to B will also affect A.

    ```Javascript
    var arr = [1, 2, 3];
    var copyArr = [1, 2, 3];
    copyArr.pop(); // Now, arr = [1, 2]
    ```

    <br/>
    How to prevent that? Well, we can use spread operator.

    ```Javascript
    // Object example
    var obj = {name: "Sabit"};
    var copyObj = {...obj};

    // Array example
    var arr = [1, 2, 3];
    var copyArr = {...arr};
    ```

2.  List operations:
    ```Javascript
    arr.pop(); // removes last eleme
    arr.push(10); // add elems at back
    arr.shift(); // removes the 1st item
    arr.unshift(50); // add elements to the front
    ```
3.  Hoisting: <br/> Can use variables before declaring

    ```Javascript
    console.log(a); // Output: undefined, but works
    var a = 10;
    ```

4.  Versions: Mainly 2 versions of JS.
    1. ES5
    2. ES6
5.  Var, let, const:
    1. “var” (ES5 version)
    2. “var, let, const” (ES6 version)
6.  “Var” is function scoped
    ```Javascript
    function foo () {
        for (var i = 0; i < 3; ++i) {
            console.log(i);
        }
        console.log(i); // Here "i" can still be used
    }
    // Output: 0, 1, 2, 3
    ```
7.  “Let and const” is braces scoped

    ```Javascript
    function foo () {
        for (let i = 0; i < 3; ++i) {
            console.log(i);
        }
        console.log(i); // throws error
    }
    // Output: 0, 1, 2, ERROR
    ```

8.  “Var” adds itself to the window object.
9.  “Let, const” doesn’t add itself to the window object.
10. Some features are not present in JS. But, we can still use them. Which are provided by the browsers we use. All of those features are provided in the window object.
11. Truthy & Falsy:
    1. Falsy values - {0, false, undefined, null, NaN, document.all}
    2. Truthy values - everything else is truthy.
12. forEach loop: <br/> Only runs on array. Works on the temporary copy of the array. That's why items of the array are not changed.

    ```Javascript
    var a = [1, 2, 3, 4];
    a.forEach(function (item) {
        console.log(item + 7); // Doesn't changes the actual array
    })
    ```

13. for-in loop is only used for objects.

    ```Javascript
    var obj = {
        name: "Sabit",
        age: 23,
        city: "Dhaka"
    }
    for (var key in obj) {
        console.log(key); // Outputs the keys only
        console.log(obj[key]); // Outputs the value of the corresponding key
    }
    ```

14. Callback function: <br/> If a code-block, runs after a particular time limit, we write that code-block into a function and that function is callback function. This is a part of Asynchronous Javascript.
    ```Javascript
    setTimeout(function () {
        console.log("I'm a callback function, because I'm running after a particular time limit.");
    }, 2000);
    ```
15. First class function: <br/>
    If a function is treated as a value. Then, it is called a first class function.

    ```Javascript
    function foo (firstClass) {
        firstClass(); // Output: I'm a first class function
    }
    foo(function () {
        console.log("I'm a first class function");
    }) // Here, this anonymous function is passed as a value to another function.
    ```

16. Arrys in Javascript are not actually arrays. They're actually objects.

    ```Javascript
    var A = [10, 20, 30];
    console.log(typeof A); // Output: Object
    ```

    Behind the scene, JS converts the array like this in {index: value} pairs:

    ```Javascript
    // Behind the scene:
    var A = {
        0: 10,
        1: 20,
        2: 30
    }
    ```

    As arrays are not actually arrays but objects, so we can even store items in negative index as follows:

    ```Javascript
    A[-1] = 999; // A = [10, 20, 30, -1: 999]
    ```

17. Delete a key from object:
    ```Javascript
    var obj = {
        name: "Sabit",
        age: 23
    }
    delete obj.age; // Outout: obj = {name: "Sabit"}
    ```
