# leetcode 119
## Question
#### Pascal's Triangle II
Given an index k, return the kth row of the Pascal's triangle.

For example, given k = 3,
Return [1,3,3,1].

Note:
Could you optimize your algorithm to use only O(k) extra space?
## Answer
比较简单 一个一个求呗
```Python
class Solution(object):
    def getRow(self, rowIndex):
        """
        :type rowIndex: int
        :rtype: List[int]
        """
        rowIndex+=1
        if rowIndex ==1:
            return [1,]
        elif rowIndex == 2:
            return [1,1]
        else:
            last=[1,1]
            i=3
            while i<=rowIndex:
                now=[None]*i
                for j in range(i):#j= [0,i-1]
                    if j==0 or j==i-1:
                        now[j]=1
                    else:
                        now[j]=last[j]+last[j-1]
                i+=1
                last=now
            return now
```
