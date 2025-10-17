# sample_code_exercise

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

2. another method Find Largest Number

```
    const array = [1, 3, 2, -1, 0, 7];
    
    console.log(`Largest Number Method 2: `,Math.max(...array));
```

3. Find Smallest number

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

4. Find smallest value other method

```
function findSmallest2(arr) {
// Math.max() is used to find the largest number
    return Math.min(...arr);
}
console.log(`Smallest Number Method 2 :`, findSmallest2([99, 5, 3, 100, 1 , 0, -7, -7.5]));
```
5. Find two largest number

```
function findTwoLargestNumber (arr) {
    // need to set decending order so only we use b-a
    let a = arr.sort((a,b) => b-a);
    
    return `The two largest number is ${a[0]} , ${a[1]}`;
}
console.log(findTwoLargestNumber([20, 3, 25, 99, 0, -3, -4.5]));
```


6. Find two smallest number

```
function findTwoSmallestNumber (arr) {
    // need to set a numbers is asending order so only use a-b
    let a = arr.sort((a,b) => a-b);
    
    return `The two smallest number is ${a[0]} , ${a[1]}`;
}
console.log(findTwoSmallestNumber([20, -7, 25, 99, 0, -3, -4.5]));
```

7. Remove duplicate Values

```
function removeDuplicateValues (arr) {
    let a = [...new Set(arr)]
    // console.log();
    return a.sort((a,b)=>a-b);
}
console.log(`uniqueArray Method 1=`, removeDuplicateValues([2, 4, 2, 0 , -1 , -1 , -5, -0.3, 0.2, -0.3, "a", "a", "ab"]));
```

8. Remove Duplicates method 2

```
function removeDuplicates(arr) {
    return arr.filter((value, index) => arr.indexOf(value) === index);
}
console.log(`uniqueArray Method 2=` , removeDuplicates([1, 2, 5, 3, 2, 5, 7, 0, 0, -3.4, -4, -3.4, "ab", "ab", "a", "cd"]));
```

9. Remove Duplicate method 3

```
let a = [1, 2, 5, 3, 2, -3.5, 0, 0,"string", "string", "a", "a", 5, 7]; 
let uniqueArray = a.reduce((acc, val) => {
  if (!acc.includes(val)) acc.push(val); 
  return acc; 
}, []); 
console.log(`UniqueArray Method 3=`, uniqueArray);
```

10. Remove Duplicate Values in string input Array

```
let newData = ["a", "ab", "a", "ab", "set", "set"];
let resultData = [...new Set(newData)];
console.log("The unique Array = ",resultData);
```
