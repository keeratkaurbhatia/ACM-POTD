# Attempting the Intermediate Question (Two Sum II - Input Array Is Sorted)

## LeetCode
<img width="1919" height="1021" alt="image" src="https://github.com/user-attachments/assets/71c31b72-075d-44f7-8f4d-037e6311cd54" />


## Code
```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& numbers, int target) {
        unordered_map<int,int> remember;
        vector<int> ans;
        for (int i = 0; i<numbers.size(); i++)
        {
            if(remember.find(numbers[i])==remember.end())
            {
                remember[target-numbers[i]] = i;
            }
            else
            {
                auto it = remember.find(numbers[i]);
                ans.push_back((it->second) + 1);
                ans.push_back(i + 1);
            }
        }
        return ans;
    }
};
```

## Approach
Brute force hash map strategy as the standard two sum problem.

## Complexities
TC = O(n)

SC = O(n)

    
