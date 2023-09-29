## Bible of Javascript (book)

[ Link to the book ](https://drive.google.com/file/d/1CEoFEEVuaOQ2cBYIBS2bBlGEqV5vg7A7/view?usp=drive_link)

## Javascript Mastery (notes)

1. By default “list, object, function” copy works like a reference copy.
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

2. List operations:
   ```Javascript
   arr.pop(); // removes last eleme
   arr.push(10); // add elems at back
   arr.shift(); // removes the 1st item
   arr.unshift(50); // add elements to the front
   ```
3. Hoisting: Can use variables before declaring

   ```Javascript
   console.log(a); // Output: undefined, but works
   var a = 10;
   ```

4. Versions: Mainly 2 versions of JS.
   1. ES5
   2. ES6
5. Var, let, const:
   1. “var” (ES5 version)
   2. “var, let, const” (ES6 version)
6. “Var” is function scoped
   ```Javascript
   function foo () {
       for (var i = 0; i < 3; ++i) {
           console.log(i);
       }
       console.log(i); // Here "i" can still be used
   }
   // Output: 0, 1, 2, 3
   ```
7. “Let and const” is braces scoped

   ```Javascript
   function foo () {
       for (let i = 0; i < 3; ++i) {
           console.log(i);
       }
       console.log(i); // throws error
   }
   // Output: 0, 1, 2, ERROR
   ```

8. “Var” adds itself to the window object.
9. “Let, const” doesn’t add itself to the window object.
10. Some features are not present in JS. But, we can still use them. Which are provided by the browsers we use. All of those features are provided in the window object.
