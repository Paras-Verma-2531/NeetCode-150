## 875. Koko Eating Bananas

```java
class Solution {
    private int requiredTime(int[]arr,int speed)
    {
        int totalHours=0;
        for(int item:arr)totalHours+=Math.ceil((double)item/speed);
        return totalHours;
    }
    public int minEatingSpeed(int[] piles, int h) {
        int minTime=1,maxTime=0;
        for(int i:piles)maxTime=Math.max(i,maxTime);
        while(minTime<=maxTime)
        {
            int avgTime=(minTime+maxTime)/2;
            if(requiredTime(piles,avgTime)<=h)maxTime=avgTime-1;
            else minTime=avgTime+1;
        }return minTime;
    }
}
