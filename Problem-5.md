## 347. Top K Frequent Elements

```java
class Solution {
    public int[] topKFrequent(int[] nums, int k) {
    Map<Integer,Integer> map= new HashMap<Integer,Integer>();
    for(int i:nums)map.put(i,map.getOrDefault(i,0)+1);
    PriorityQueue<Pair>pq=new PriorityQueue<>(new Comparator<Pair>()
    {
        public int compare(Pair a,Pair b)
        {
            return Integer.compare(a.freq,b.freq);
        }
    });
    Iterator<Integer>it=map.keySet().iterator();
    while(it.hasNext())
    {
        int key=(int)it.next();
        int freq=(int)map.get(key);
        pq.offer(new Pair(key,freq));
        if(pq.size()>k)pq.poll();
    }
    int[]arr=new int[k];
    int i=0;
    while(!pq.isEmpty())arr[i++]=pq.poll().key;
    return arr;
}
class Pair
{
    int key,freq;
    public Pair(int key,int freq)
    {
        this.key=key;
        this.freq=freq;
    }
}
}
