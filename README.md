# leetcode_Median_of_Two_Sorted_Arrays
+ 두input값을 합쳐 중간값을 리턴하기
+ 把兩個input值合起來求出 中間值
-----
+ Example1
```
Input: nums1 = [1,3], nums2 = [2]
Output: 2.00000
Explanation: merged array = [1,2,3] and median is 2.
```
----
+ Example2
```
Input: nums1 = [1,2], nums2 = [3,4]
Output: 2.50000
Explanation: merged array = [1,2,3,4] and median is (2 + 3) / 2 = 2.5.
```
----

```python
class Solution:
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:
        totalnum = nums1+nums2 # 첫번째 input과 두번째 input 합치기
        totalnum.sort() # 합친 후 sort를 통해 오름차순으로 정리  
        
        n = len(totalnum) # 정리한 값의 길이 구하기
        
        if n % 2 == 1: # 길이를 나눴을때 홀수 일 경우 중간 값 리턴 
            return totalnum[n//2] 
        else: # 짝수 일 경우 두가지의 중간 값을 더하여 /2 하고 리턴 
            return (totalnum[n//2-1]+totalnum[n//2])/2
```
---
```
결론 : 
input들을 합치고 sort후 길이가 홀수인지 짝수인지 판단 그후 홀수 일 경우엔 중간 값 리턴 하지만 짝수 일 경우엔 두 중간 값을 더하고 리턴
```
---
```
結論:
把兩個input值結合之後 使用sort去排列，排列之後求出len的大小並計算出是否奇數還是偶數，當長度為奇數時直接return中間值，如果是偶數是時把(中間值)與(中間值-1)的值結合/2再return
```
---
### Result
Runtime: 98 ms, faster than 90.96% of Python3 online submissions for Median of Two Sorted Arrays.\
Memory Usage: 14.1 MB, less than 67.89% of Python3 online submissions for Median of Two Sorted Arrays.
