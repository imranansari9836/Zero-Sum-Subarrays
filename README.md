
class Solution{
    //Function to count subarrays with sum equal to 0.
    public static long findSubarray(long[] arr ,int n) 
    { HashMap<Long, Long> map1 = new HashMap<>();
        map1.put(0L, 1L);
        long count = 0;
        long sum = 0;
        for(int i = 0; i < n; i++){
            sum += arr[i];
            if(map1.containsKey(sum)){
                count += map1.get(sum);
            }
            map1.put(sum, map1.getOrDefault(sum, 0L) + 1);
        }
        return count;
    }
}
