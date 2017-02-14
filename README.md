# LeetCodeInC-

1. Two Sum 
  Description
  Given an array of integers, return indices of the two numbers such that they add up to a specific target.
  You may assume that each input would have exactly one solution, and you may not use the same element twice.
  
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> hash;
        vector<int> result;
        for (int i = 0; i < nums.size(); i++) {
        	int numberToFind = target - nums[i];
            //if numberToFind is found in map, return them
        	if (hash.find(numberToFind) != hash.end()) {
        		result.push_back(hash[numberToFind]);
        		result.push_back(i);			
        		return result;
        	}
            //number was not found. Put it in the map.
        	hash[nums[i]] = i;
        }
        return result;
    }
};
