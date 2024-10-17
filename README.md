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
