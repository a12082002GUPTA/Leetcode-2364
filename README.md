# Leetcode-2364

# C++

 class Solution {
public:
    long long countBadPairs(vector<int>& nums) {
        map<int,int>mp;
        mp[nums[0]]++;
        long long count=0;
        for(int i=1;i<nums.size();i++)
        {
          int a=nums[i]-i;
          count+=(i-mp[a]);
          mp[a]++;
        }
        return count;
    }
};

# Python

from collections import defaultdict
from typing import List

class Solution:
    def countBadPairs(self, nums: List[int]) -> int:
        mp = defaultdict(int)
        mp[nums[0]] += 1
        count = 0
        
        for i in range(1, len(nums)):
            a = nums[i] - i
            count += (i - mp[a])
            mp[a] += 1
        
        return count

# Java

import java.util.HashMap;

class Solution {
    public long countBadPairs(int[] nums) {
        HashMap<Integer, Integer> mp = new HashMap<>();
        mp.put(nums[0] - 0, 1); // Store nums[i] - i
        long count = 0;
        
        for (int i = 1; i < nums.length; i++) {
            int a = nums[i] - i;
            count += (i - mp.getOrDefault(a, 0));
            mp.put(a, mp.getOrDefault(a, 0) + 1);
        }
        
        return count;
    }
}
        
