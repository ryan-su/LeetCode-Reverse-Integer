# LeetCode-Reverse-Integer
Brush-The second question.
Question from https://leetcode.com/problems/reverse-integer/
Reverse digits of an integer.
Example1: x = 123, return 321
Example2: x = -123, return -321

class Solution {
public:
    int reverse(int x) {
        bool isPositive=true;
        int tempNum,absNum;
        if(x<0)
        {
            isPositive=!isPositive;
            absNum=tempNum=abs(x);
        }
        else absNum=tempNum=x;
        int count;
        long long result=0;
        for(count=0;tempNum>0;tempNum/=10,count++);
        
        while(absNum>0)
        {
            long long num=absNum%10;
            for(int i=1;i<count;i++)
            {
                num*=10;
            }
            result+=num;
            count--;
            absNum/=10;
        }
        if(isPositive)
        {
            if((result>=-2147483648)&&(result<=2147483647))
            return result;
            else return 0;
        }
        else 
        {
            if(((-result)>=-2147483648)&&((-result)<=2147483647))
            return -result;
            else return 0;
        }

    }
};
