javascriptfunction fibs(n) {
  if (n <= 0) return [];
  if (n === 1) return;
  
  const result =;
  for (let i = 2; i < n; i++) {
    result.push(result[i - 1] + result[i - 2]);
  }
  return result;
}
Use code with caution.fibsRec (Recursive Approach)javascriptfunction fibsRec(n) {
  console.log("This was printed recursively");
  
  // Base cases
  if (n <= 0) return [];
  if (n === 1) return;
  if (n === 2) return;
  
  // Recursive step: get the sequence up to n-1
  const seq = fibsRec(n - 1);
  
  // Append the sum of the last two elements
  seq.push(seq[seq.length - 1] + seq[seq.length - 2]);
  return seq;
}
Use code with caution.Verification & Testingjavascriptconsole.log("--- Testing Iterative Fibs ---");
console.log(fibs(0)); // []
console.log(fibs(1)); // [0]
console.log(fibs(8)); // [0, 1, 1, 2, 3, 5, 8, 13]

console.log("\n--- Testing Recursive Fibs (with logs) ---");
console.log(fibsRec(8)); 
// Prints "This was printed recursively" 7 times
// Returns [0, 1, 1, 2, 3, 5, 8, 13]
Use code with caution.2. Merge Sort Implementation (mergesort.js)Merge sort splits an array into halves recursively until single-element arrays remain (the base case), then merges them back together in sorted order.javascriptfunction mergeSort(arr) {
  // Base case: arrays with 0 or 1 element are already sorted
  if (arr.length <= 1) return arr;

  // Split the array into left and right halves
  const mid = Math.floor(arr.length / 2);
  const leftHalf = arr.slice(0, mid);
  const rightHalf = arr.slice(mid);

  // Recursively sort both halves and merge them
  return merge(mergeSort(leftHalf), mergeSort(rightHalf));
}

// Helper function to merge two sorted arrays
function merge(left, right) {
  const sorted = [];
  let i = 0; // Pointer for left array
  let j = 0; // Pointer for right array

  // Compare elements from both arrays and push the smaller one
  while (i < left.length && j < right.length) {
    if (left[i] < right[j]) {
      sorted.push(left[i]);
      i++;
    } else {
      sorted.push(right[j]);
      j++;
    }
  }

  // Concatenate any remaining elements left over
  return sorted.concat(left.slice(i)).concat(right.slice(j));
}.Verification & Testingjavascriptconsole.log("\n--- Testing Merge Sort ---");
console.log(mergeSort([])); 
// Output: []

console.log(mergeSort([73])); 
// Output: [73]

console.log(mergeSort([1, 2, 3, 4, 5])); 
// Output: [1, 2, 3, 4, 5]

console.log(mergeSort([3, 2, 1, 13, 8, 5, 0, 1])); 
// Output: [0, 1, 1, 2, 3, 5, 8, 13]

console.log(mergeSort([105, 79, 100, 110])); 
// Output: [79, 100, 105, 110]# recursion
