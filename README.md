# Javascript code snippet / Exercises

### 1. Find Largest number

```
function findLargest1(arr) {
    let largest = arr[0];
    for (let i = 1; i < arr.length; i++) {
        if (arr[i] > largest) {
            largest = arr[i];
        }
    }
    return largest;
}
console.log(`Largest Number Method 1 :`, findLargest1([10,0,4,15,-1,8]));
```

### 2. Another method Find Largest Number

```
    const array = [1, 3, 2, -1, 0, 7];
    
    console.log(`Largest Number Method 2: `,Math.max(...array));
```

### 3. Find Smallest number

```
function findSmallest(arr) {
    let smallest = arr[0];
    
    for (let i= 1; i <arr.length; i++) {
        if(arr[i] < smallest) {
            smallest = arr[i];
        }
    }
    return smallest;
}
console.log(`Smallest Number Method 1 :`,findSmallest([2, 0, -3, -5, -5.5]));
```

### 4. Find smallest value other method

```
function findSmallest2(arr) {
// Math.max() is used to find the largest number
    return Math.min(...arr);
}
console.log(`Smallest Number Method 2 :`, findSmallest2([99, 5, 3, 100, 1 , 0, -7, -7.5]));
```
### 5. Find two largest number

```
function findTwoLargestNumber (arr) {
    // need to set decending order so only we use b-a
    let a = arr.sort((a,b) => b-a);
    
    return `The two largest number is ${a[0]} , ${a[1]}`;
}
console.log(findTwoLargestNumber([20, 3, 25, 99, 0, -3, -4.5]));
```


### 6. Find two smallest number

```
function findTwoSmallestNumber (arr) {
    // need to set a numbers is asending order so only use a-b
    let a = arr.sort((a,b) => a-b);
    
    return `The two smallest number is ${a[0]} , ${a[1]}`;
}
console.log(findTwoSmallestNumber([20, -7, 25, 99, 0, -3, -4.5]));
```

### 7. Remove duplicate Values

```
function removeDuplicateValues (arr) {
    let a = [...new Set(arr)]
    // console.log();
    return a.sort((a,b)=>a-b);
}
console.log(`uniqueArray Method 1=`, removeDuplicateValues([2, 4, 2, 0 , -1 , -1 , -5, -0.3, 0.2, -0.3, "a", "a", "ab"]));
```

### 8. Remove Duplicates method 2

```
function removeDuplicates(arr) {
    return arr.filter((value, index) => arr.indexOf(value) === index);
}
console.log(`uniqueArray Method 2=` , removeDuplicates([1, 2, 5, 3, 2, 5, 7, 0, 0, -3.4, -4, -3.4, "ab", "ab", "a", "cd"]));
```

### 9. Remove Duplicate method 3

```
let a = [1, 2, 5, 3, 2, -3.5, 0, 0,"string", "string", "a", "a", 5, 7]; 
let uniqueArray = a.reduce((acc, val) => {
  if (!acc.includes(val)) acc.push(val); 
  return acc; 
}, []); 
console.log(`UniqueArray Method 3=`, uniqueArray);
```

### 10. Remove Duplicate Values in string input Array

```
let newData = ["a", "ab", "a", "ab", "set", "set"];
let resultData = [...new Set(newData)];
console.log("The unique Array = ",resultData);
```
Above 3 methods also work for string array.

### 11. Sort function for only passitive value , without dupilicate numbers and non repetive values
```
function sorter(array){
    var swap;
    console.log(array , 'array');
    for(var i = 1; i<array.length; i++){
        if(array[i-1] > array[i]) {
            swap = array[i-1];
            array[i-1] = array[i];
            array[i] = swap;
        }
    }
    return array;
}
console.log("Sorted array :", sorter([1,5,2,4,6]));
```

### 12. Sort function for all values (repetive values and negative values)

```
var Arr = [1, 7, 2, 8, 3, 4, 5, 0, 9, -1.4, -1.1, 2];

for (var i = 1; i < Arr.length; i++){
    for (var j = 0; j < i; j++){
      if (Arr[i] < Arr[j]) {
          var x = Arr[i];
          Arr[i] = Arr[j];
          Arr[j] = x;
      }
    }
}

console.log(Arr);
```

### 13. [2, [3,4, [5,6,7],1],8] to [1,2,3,4,5,6,7,8] result javascript ?

```
let a = [2, [3, 4, [5, 6, 7], 1], 8];
let result = a.flat(Infinity).sort((x, y) => x - y);
console.log(result); // [1, 2, 3, 4, 5, 6, 7, 8]
```
Explanation:

flat(Infinity) → flattens any level of nested arrays.

sort((x, y) => x - y) → sorts numbers in ascending order (default sort() sorts as strings).

### 14. Remove Duplicate objects from array ?

```
let arr = [
  { a: 5 },
  { a: 5 },
  { c: 10 },
  { b: 20, d: 25 },
  { b: 20, d: 25 },
  { a: 5, b: 20, c: 10, d: 25 }
];

let uniqueArr = Array.from(
  new Map(arr.map(obj => [JSON.stringify(obj), obj])).values()
);

console.log(uniqueArr);
```
Explanation :

JSON.stringify(obj) converts each object to a string (so duplicates look the same).

Map ensures unique keys (only one copy per stringified object).

.values() gives back the original unique objects.

### 15 . [2, "b", 4, "d", 3, "a", "c", "e", 5, 1] to [2, 4, 3, 5, 1, "b", "d", "a", "c", "e"] javascript

```
let arr = [2, "b", 4, "d", 3, "a", "c", "e", 5, 1];

let numbers = arr.filter(item => typeof item === "number");
let strings = arr.filter(item => typeof item === "string");

let result = numbers.concat(strings);
console.log(result);
```

#### Explanation :
filter() separates the array by type (number or string).

concat() merges the two filtered arrays — numbers first, then strings.

### With Sort :
```
let arr = [2, "b", 4, "d", 3, "a", "c", "e", 5, 1];

// numeric sort
let numbers = arr .filter(item => typeof item === "number").sort((a, b) => a - b);

// alphabetical sort
let strings = arr .filter(item => typeof item === "string").sort();

let result = numbers.concat(strings);
console.log(result);
```

### 16. Sorting the array without sort keyword

```
let arr = [2, "b", 4, "d", 3, "a", "c", "e", 5, 1];

// Step 1: Separate numbers and strings
let numbers = arr.filter(item => typeof item === "number");
let strings = arr.filter(item => typeof item === "string");


// Step 2: Sort numbers (ascending) — using Bubble Sort
for (let i = 0; i < numbers.length - 1; i++) {
  for (let j = 0; j < numbers.length - i - 1; j++) {
    if (numbers[j] > numbers[j + 1]) {
      let temp = numbers[j];
      numbers[j] = numbers[j + 1];
      numbers[j + 1] = temp;
    }
  }
}

// Step 3: Sort strings (alphabetically) — using Bubble Sort
for (let i = 0; i < strings.length - 1; i++) {
  for (let j = 0; j < strings.length - i - 1; j++) {
    if (strings[j] > strings[j + 1]) {
      let temp = strings[j];
      strings[j] = strings[j + 1];
      strings[j + 1] = temp;
    }
  }
}

// Step 4: Combine
let result = numbers.concat(strings);
console.log(result);
```





