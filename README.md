# 007Reverse-Integer
反转数字
Example1: x = 123, return 321
Example2: x = -123, return -321

easy题目，注意result出现数字溢出边界的问题，设置成long型。

public class Solution {
    public int reverse(int x) {
        
        int flag = 1;
        long result = 0;
        
        if(x < 0) {
            flag = -1;
            x = -x;
        }
        
        while(x > 0) {
            result = x % 10 + result * 10;
            x /= 10;
        }
        
        result = result < Integer.MIN_VALUE ? 0 : result;
        result = result > Integer.MAX_VALUE ? 0 : result;
        
        return flag*(int)result;       
    }
}
