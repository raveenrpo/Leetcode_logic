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
