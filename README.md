# DSAAssign1

# Q1
```
function twoSum(nums, target) {
    const complementMap = {};
    for (let i = 0; i < nums.length; i++) {
        const complement = target - nums[i];
        if (complement in complementMap) {
            return [complementMap[complement], i];
        }
        complementMap[nums[i]] = i;
    }
    return []; // No solution found
}

// Example usage:
const nums = [2, 7, 11, 15];
const target = 9;
const result = twoSum(nums, target);
console.log(result);

```

# Q2

```
function removeElement(nums, val) {
    let k = 0; // Number of elements not equal to val
    for (let i = 0; i < nums.length; i++) {
        if (nums[i] !== val) {
            nums[k] = nums[i];
            k++;
        }
    }
    return k;
}


```

# Q3

```
function searchInsert(nums, target) {
    let left = 0;
    let right = nums.length - 1;

    while (left <= right) {
        const mid = Math.floor((left + right) / 2);
        if (nums[mid] === target) {
            return mid;
        } else if (nums[mid] < target) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }

    return left; // Target not found, return the index for insertion
}


```

# Q4

```
function plusOne(digits) {
    const n = digits.length;
    let carry = 1;

    for (let i = n - 1; i >= 0; i--) {
        const sum = digits[i] + carry;
        digits[i] = sum % 10;
        carry = Math.floor(sum / 10);

        if (carry === 0) {
            // No more carry, early return
            return digits;
        }
    }

    if (carry !== 0) {
        // If carry remains after iterating through all digits, add it as a new digit at the beginning
        digits.unshift(carry);
    }

    return digits;
}


```

# Q5

```
function merge(nums1, m, nums2, n) {
    let i = m - 1;
    let j = n - 1;
    let k = m + n - 1;

    while (i >= 0 && j >= 0) {
        if (nums1[i] >= nums2[j]) {
            nums1[k] = nums1[i];
            i--;
        } else {
            nums1[k] = nums2[j];
            j--;
        }
        k--;
    }

    // Copy remaining elements from nums2 to nums1 if any
    while (j >= 0) {
        nums1[k] = nums2[j];
        j--;
        k--;
    }
}


```

# Q6

```
function containsDuplicate(nums) {
    let numSet = new Set();

    for (let num of nums) {
        if (numSet.has(num)) {
            return true;
        }
        numSet.add(num);
    }

    return false;
}


```

# Q7

```

function moveZeroes(nums) {
    let i = 0;  // Pointer for non-zero elements

    for (let j = 0; j < nums.length; j++) {
        if (nums[j] !== 0) {
            // Swap non-zero element to the current position
            [nums[i], nums[j]] = [nums[j], nums[i]];
            i++;
        }
    }
}


```

# Q 8

```
function findErrorNums(nums) {
    const n = nums.length;
    const numSet = new Set();
    let duplicate, missing;

    // Find the duplicate number
    for (let num of nums) {
        if (numSet.has(num)) {
            duplicate = num;
            break;
        }
        numSet.add(num);
    }

    // Find the missing number
    for (let i = 1; i <= n; i++) {
        if (!numSet.has(i)) {
            missing = i;
            break;
        }
    }

    return [duplicate, missing];
}


```
