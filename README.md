1
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.
You can return the answer in any order.

Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]

Ans:/\*\*

- @param {number[]} nums
- @param {number} target
- @return {number[]}
  \*/
  var twoSum = function(nums, target) {
  for(i=0;i<nums.length;i++)
  {
  for(j=i+1;j<nums.length;j++)
  {
  if(nums[i]+nums[j]==target)
  {
  return [i,j];
  }
  }
  }
  };

2
iven two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.
The overall run time complexity should be O(log (m+n)).
Example 1:

Input: nums1 = [1,3], nums2 = [2]
Output: 2.00000

Ans:var findMedianSortedArrays = function(nums1, nums2) {
var arr=nums1.concat(nums2)
var a=arr.sort((a,b)=>a-b);
if(a.length%2!=0)
{
return parseFloat(a[((a.length+1)/2)-1])
}
if(a.length%2==0)
{
return parseFloat((a[(a.length/2)-1]+a[(a.length/2)])/2)
}
};

3
Given a signed 32-bit integer x, return x with its digits reversed. If reversing x causes the value to go outside the signed 32-bit integer range [-231, 231 - 1], then return 0.
Assume the environment does not allow you to store 64-bit integers (signed or unsigned).
Example 1:

Input: x = 123
Output: 321

Ans:
var reverse = function(x) {
var sum = 0;
var neg = x < 0;
x = Math.abs(x);
while (x > 0) {
var a = x % 10;
x = Math.floor(x / 10);

        if (sum > (Math.pow(2, 31) - 1) / 10 || (sum === (Math.pow(2, 31) - 1) / 10 && a > 7))  {
            return 0;
        }

        sum = sum * 10 + a;
    }

    return neg ? -sum : sum;

};

4.Given an integer x, return true if x is a
palindrome and false otherwise.
Example 1:
Input: x = 121
Output: true

Ans:
var isPalindrome =function(x) {
if(x<0)
return false
var n;
n=x;
var rev=[]
while(x>0)
{
var a=x%10;
rev.push(a)
x=Math.trunc(x/10);
}
if(n==Number(rev.join('')))
return true
else
return false

}

5.Given an integer array nums sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once. The relative order of the elements should be kept the same. Then return the number of unique elements in nums.

Ans:
var removeDuplicates = function(nums) {
for( i=0;i<nums.length-1;i++){
for(j=i+1;j<nums.length;j++){
if(nums[i]==nums[j]){
nums.splice(j,1)
j--
}

    }

}
return nums.length
};

6.Given an unsorted integer array nums. Return the smallest positive integer that is not present in nums.
You must implement an algorithm that runs in O(n) time and uses O(1) auxiliary space

Ans:
var firstMissingPositive = function(nums) {
const arr=new Set(nums)
for(let i=1;i<=nums.length+1;i++)
{
if(!arr.has(i)){
return i
}
}

};

7.You are given an n x n 2D matrix representing an image, rotate the image by 90 degrees (clockwise).
You have to rotate the image in-place, which means you have to modify the input 2D matrix directly. DO NOT allocate another 2D matrix and do the rotation.
Input: matrix = [[1,2,3],[4,5,6],[7,8,9]]
Output: [[7,4,1],[8,5,2],[9,6,3]]

Ans:
var rotate = function(matrix) {
var l = matrix.length;
var temp;
for (let i = 0; i < l; i++) {
for (let j = i + 1; j < l; j++) {
let temp = matrix[i][j];
matrix[i][j] = matrix[j][i];
matrix[j][i] = temp;
}
}

for (let i = 0; i < l; i++) {
for (let j = 0; j < Math.floor(l / 2); j++) {
let temp = matrix[i][j];
matrix[i][j] = matrix[i][l - j - 1];
matrix[i][l - j - 1] = temp;
}
}
};

8:Implement pow(x, n), which calculates x raised to the power n (i.e., xn).

Ans:
var myPow = function(x, n) {
return x\*\*n;
};
