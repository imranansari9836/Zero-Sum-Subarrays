class Solution{
    //Function to count subarrays with sum equal to 0.
    public static long findSubarray(long[] arr ,int n) 
    {
        HashMap<Long, Long> map = new HashMap<>();

        long sum =0, count =0;

        map.put((long)0, (long)1);

        for(int i=0; i< n; i++){

            sum += arr[i];

            if(map.containsKey(sum)){

                count += map.get(sum);

            }

            map.put(sum, map.getOrDefault(sum, (long)0) + (long)1);

        }

        return count;

    }

}
