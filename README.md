# 1313.-Decompress-Run-Length-Encoded-List
We are given a list nums of integers representing a list compressed with run-length encoding.

Consider each adjacent pair of elements [freq, val] = [nums[2*i], nums[2*i+1]] (with i >= 0).  For each such pair, there are freq elements with value val concatenated in a sublist. Concatenate all the sublists from left to right to generate the decompressed list.

Return the decompressed list.


````c#
public class Solution {
    public int[] DecompressList(int[] nums) {
    
        List<int> res = new List<int>();
        
        for(int i=0; i<nums.Length; i = i+2){
            int freq = nums[i];
            int val = nums[i+1];
            
            while(freq > 0){
                res.Add(val);
                freq--;
            }
        }
        
        return res.ToArray();
    }
}

``````
