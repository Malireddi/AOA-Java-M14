
# EX 4E Longest Increasing Subsequence - Dynamic Programming.
## DATE: 20/10/2025
## AIM:
To write a Java program to for given constraints.
Given an integer array nums, return the length of the longest strictly increasing subsequence.
Example 1:
Input: nums = [10,9,2,5,3,7,101,18]
Output: 4
Explanation: The longest increasing subsequence is [2,3,7,101], therefore the length is 4.
## Algorithm
1. 
2. 
3. 
4.  
5.   

## Program:
```
/*
Program to implement Reverse a String
Developed by: Malyadri Reddy N
Register Number:  212223100037
*/
import java.util.*;

public class LongestIncreasingSubsequence {

    public static int lengthOfLIS(int[] nums) {
        if (nums == null || nums.length == 0) return 0;

        int n = nums.length;
        int[] dp = new int[n];  // dp[i] = length of LIS ending at nums[i]
        Arrays.fill(dp, 1);     // Each element is a LIS of length 1 by itself

        int maxLen = 1;

        for (int i = 1; i < n; i++) {
            for (int j = 0; j < i; j++) {
                if (nums[i] > nums[j]) {
                    dp[i] = Math.max(dp[i], dp[j] + 1);
                }
            }
            maxLen = Math.max(maxLen, dp[i]);
        }

        return maxLen;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int n = scanner.nextInt();
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = scanner.nextInt();
        }

        int result = lengthOfLIS(nums);
        System.out.println("Length of Longest Increasing Subsequence: " + result);

        scanner.close();
    }
}

```

## Output:
<img width="812" height="257" alt="image" src="https://github.com/user-attachments/assets/520c0acf-b436-422b-9aff-b9e07ce4377b" />



## Result:
The program successfully implemented and the expected output is verified.
