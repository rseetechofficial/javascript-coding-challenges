# javascript-coding-challenges

   > Click :star: Please follow me on GitHub and LinkedIn [@RameshKumar](https://www.linkedin.com/in/ramesh-kumar-choudhary/) for more updates.


   ## JavaScript Coding Challenges and Interview Question list available here :-

   >1. Click here for [Javascript Basics Coding](https://github.com/rseetech/javascript-basics) more information.
   >  
   >2. Click here for [Javascript Coding Challenges](https://github.com/rseetech/javascript-coding-challenges) more information.
   >
   >3. Click here for [Javascript quick coding interview questions](https://github.com/rseetech/javascript-quick-coding-interview-questions) more information. 
   >
   >3. Click here for [Javascript interview asking output questions](https://github.com/rseetech/javascript-interview-asking-output-questions) more information. 

   ## React nterview Questions & Coding Project list available here :-

   >1. Click here for [React Interview Questions & Answers](https://github.com/rseetech/React-interview-questions) more information.
   >
   >2. Click here for [React Routing Axios Search Counter App Using MUI](https://github.com/rseetech/react-routing-axios-search-counter-app-using-mui) more information.
   >
   >3. Click here for [React Routing Pass data Child to Parent](https://github.com/rseetech/react-router-axios-pass-data-child-to-parent) more information.
   >
   >4. Click here for [React Create Tic Tac Toe Game](https://github.com/rseetech/react-create-tic-tac-toe-game) more information.


### Table of Contents

| No. | Questions                                                                              |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | [Multiplie values](#multiplie-values)           |
| 2   | [Remove Dublicate from array](#remove-dublicate-from-array)                        |
| 3   | [Print all duplicate elements of an array](#print-all-duplicate-elements-of-an-array)                   |
| 4   | [Find the nth largest element in a sorted array](#find-the-nth-largest-element-in-a-sorted-array)                   |
| 5   | [Find the frequency of elements in array](#find-the-frequency-of-elements-in-array)                   |
| 6   | [Group items on the basis of age of given array of object](#group-items-on-the-basis-of-age-of-given-array-of-object)                   |
| 7   | [Collect books from array of objects and return collection of books as an array](#collect-books-from-array-of-objects-and-return-collection-of-books-as-an-array)                   |
| 8   | [Anagram Javascript Program To Check Whether Two Strings Are Anagram Of Each Other ](#javascript-program-to-check-whether-two-strings-are-anagram-of-each-other)                   |

1. ### Multiplie values (Currying function)

   **Method 1.**
   
      ```
         function mui(a){
            return function(b){
               return function (c){
                  return a*b*c; // 24
               }
            }
         }
         console.log(mui(2)(3)(4));

         **Output:** 24
      ```
   **Method 2.** 

      ```
         function add(a){
            return function (b){
            if(b === undefined){
               return a;
            } else {
               return add(a+b);
            }
         }
         }
         console.log(add(1)(2)()); // 3
         console.log(add(1)(2)(5)()); // 8

      ```

   **[⬆ Back to Top](#table-of-contents)**

2. ### Remove Dublicate from array

   #### Method 1 : Remove duplicates from an array and return unique values in O(n) complexity.
      ```
         let arr3 = [1,4,3,5,7,2,5,8,3,5,9,1,8];

         let finalarr = [...new Set(arr3)];
         console.log(finalarr);

         **Output:** [1, 4, 3, 5, 7, 2, 8, 9]

      ```

   #### Method 2 : Remove duplicates from an array and return unique values in O(n) complexity.
      ```
         function unique(arr) {
         let items = {}
         arr.forEach( (item) => {
            if (!items[item]) {

               items[item] = item;
            }
            });	
         return Object.values (items);
         }
         console.log(unique(arr5));

         **Output:** 
      ```

   **[⬆ Back to Top](#table-of-contents)**

3. ### Print all duplicate elements of an array

   ```
      let arr6 =[1,1,5,6,7,8,9,3,2,2,4,4];

      function  printDuplicates(ar) {
         let result =ar.filter((item,index)=> {
            return ar.indexOf(item) !==index;
         });
         return result ;
      }
      console.log(printDuplicates(arr6));

      **Output:** 
   ```
   **[⬆ Back to Top](#table-of-contents)**

4. ### Find the nth largest element in a sorted array
   ```
      let arr4 = [12,34,21,14,67,35,64,25];
      let n = 2;
      let sortArr = arr4.sort((a, b) => a - b);

      const nthLargest = arr4[arr4.length - n] // if n= 2 output = 64

      console.log(sortarr);
      console.log(nthLargest);

      **Output:**  12, 14, 21, 25, 34, 35, 64, 67
               64 
   ```
   **[⬆ Back to Top](#table-of-contents)**

5. ### Find the frequency of elements in array

   #### Method 1: Using Reduce method of array

      ```
         let arr = ["hello", "world", "java", "hello", "java"]

         function countWord(p) {
            let result = p.reduce((allNames, name) => {

               if (name in allNames) {
                  allNames[name]++
               } else {
                  allNames[name] = 1
               }

               return allNames;
            },{});

            return result;
         }
         console.log(countWord(arr));

      ```

   #### Method 2: Using an Object

      ```
         let arr2 = ["hello", "world", "java", "hello", "java"]

         function countWord(p) {
            var count = {};
            p.forEach( (item) => {
               if (count[item]) {
                  count[item]++
               } else {
                  count[item] =1
               }
            })
            return count;
         }
         console.log(countWord(arr));

      ```
   **[⬆ Back to Top](#table-of-contents)**

6. ### Group items on the basis of age of given array of object

   ```
      let people =[{name: "Alice", age: 21 },{name: "Max", age: 20 },{name: 'Jane', age: 20 }];

      function groupBy(ar) {
         var check = {};
         ar.forEach( (item) => {
            if (!check[item.age]) {
               check[item.age] = [item];
            } else {
            check[item.age].push (item);
            }
         })
         return check;
      }
      console. log(groupBy(people));
      
      **Output:** {
                     20: [{
                        age: 20,
                        name: "Max"
                     }, {
                        age: 20,
                        name: "Jane"
                     }],
                     21: [{
                        age: 21,
                        name: "Alice"
                     }]
                  }
   ```

   **[⬆ Back to Top](#table-of-contents)**

7. ### Collect books from array of objects and return collection of books as an array

   ```
      let friends = [{
         name: "Anna",
         books: ['Bible', 'Harry Potter'],
         age: 21
      },{
         name: "Bob",
         books: ['War and peace', 'Romeo and Juliet'],
         age: 26
      },{
         name: "Alice",
         books: ['The Lord of the Rings', "The Shining"],
         age: 18
      }];

      let result = friends.reduce( (pre, curr) => {
         return [...pre, ...curr.books]
      },[]);

      console.log(result);

      **Output:** ["Bible", "Harry Potter", "War and peace", "Romeo and Juliet", "The Lord of the Rings", "The Shining"]
   ```
   **[⬆ Back to Top](#table-of-contents)**

8. ### Anagram Javascript Program To Check Whether Two Strings Are Anagram Of Each Other

   ```
      function charCheck( val1, val2){
   
         let value1 = val1.length;
         let value2 = val2.length;
         
         if(value1 !== value2){
            console.log("not matching")
            return
         }
         let char1 = val1.toLowerCase().split('').sort().join('');
         let char2 = val2.toLowerCase().split('').sort().join('');
         
         if(char1 === char2){
            console.log("matching")
         } else {
            console.log("Not matching");
         }
      }
      charCheck("Apple","papel");

      **Output:** matching

   ```
   
   **[⬆ Back to Top](#table-of-contents)**

10. ### Using currying solve problem 

   Solve this problem : f(g(h(i(j(x)))))

   ```
      // Step 1: Create individual functions
      function f(x) {
      return x + 1;
      }

      function g(x) {
      return x * 2;
      }

      function h(x) {
      return x - 3;
      }

      function i(x) {
      return x / 2;
      }

      // Step 2: Implement currying
      function curry(fn) {
      return function curried(...args) {
         if (args.length >= fn.length) {
            return fn(...args);
         } else {
            return function (...nextArgs) {
            return curried(...args.concat(nextArgs));
            };
         }
      };
      }

      // Step 3: Compose the curried functions
      const composedFunction = curry(f)(curry(g)(curry(h)(curry(i))));

      // Usage
      const result = composedFunction(5); // Pass the initial value 'x' as an argument
      console.log(result); // Output: 9

   ```

   **[⬆ Back to Top](#table-of-contents)**

2. ### Solve problem and find output

   ```
      const circle = {
         radius: 10,
         diameter() { return this.radius * 2; },

         perimeter: () => 2 * Math.PI * circle.radius,
      };
      console.log(circle.diameter()); // 20
      console.log(circle.perimeter()); // 62.83185307179586

   ```
   
   **[⬆ Back to Top](#table-of-contents)**

11. ### Deep copy and Shallow copy

   **Exapmle :**

   ```
      let obj = {name: "Ramesh", profession: {des: "lead", location: "somewhere"}};

      const shallowcopy = {...obj};
      console.log(shallowcopy);

      const deepcopy = JSON.parse(JSON.stringify(obj));
      console.log(deepcopy);
   ```
   **[⬆ Back to Top](#table-of-contents)**

12. ### WAP to findPairsWithSum of 7 in array?

   **Example:** 

   ```
      function findPairsWithSum(arr, targetSum) {
         const pairs = [];
         const numMap = {};
         for (const num of arr) {
            const complement = targetSum - num;
            if (numMap[complement]) {
               pairs.push([num, complement]);
            }
            numMap[num] = true;
         }
         return pairs;
      }
      const array = [2, 4, 3, 5, 6, 1, 7];
      const target = 7;
      const result = findPairsWithSum(array, target);
      console.log("Pairs with sum", target, ":", result);
   ```

   **[⬆ Back to Top](#table-of-contents)**

13. ### WAP to findMissingNumbers from given array?

   **Example:** 

   ```
      function findMissingNumbers(arr) {
         const maxNum = Math.max(...arr);
         const minNum = Math.min(...arr);
         const missingNumbers = [];
         for (let i = minNum; i <= maxNum; i++) {
            if (!arr.includes(i)) {
               missingNumbers.push(i);
            }
         }
         return missingNumbers;
      }
      const numbers = [2, 4, 7, 9, 13];
      const missingNumbers = findMissingNumbers(numbers);
      console.log("Missing numbers:", missingNumbers);
      
   ```
   
   **[⬆ Back to Top](#table-of-contents)**   