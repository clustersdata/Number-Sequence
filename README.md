# Number-Sequence

Number Sequence

Problem Description

A number sequence is defined as follows:


f(1) = 1, f(2) = 1, f(n) = (A * f(n - 1) + B * f(n - 2)) mod 7.


Given A, B, and n, you are to calculate the value of f(n).

 
Input

The input consists of multiple test cases. Each test case contains 3 integers A, B and n on a single line (1 <= A, B <= 1000, 1 <= n <= 100,000,000). Three zeros signal the end of input and this test case is not to be processed.

 
Output

For each test case, print the value of f(n) on a single line. 


Sample Input

1 1 3

1 2 10

0 0 0 

Sample Output

2

5

代码：

#include<stdio.h>

int f[200];

int main()

{

    int a,b,n,i;
    
    while(scanf("%d%d%d",&a,&b,&n)&&a&&b&&n)
    
    {
    
        if(n>=3)
        
        {
        
            f[1]=1;f[2]=1;
            
            for(i=3;i<=200;i++)
            
            {
            
                f[i]=(a*f[i-1]+b*f[i-2])%7;
                
                if(f[i-1]==1&&f[i]==1)
                
                    break;
                    
            }
            
            i-=2;
            
            n=n%i;
            
            if(n==0)
            
                printf("%d\n",f[i]);
                
            else
            
                printf("%d\n",f[n]);
                
        }
        
        else
        
            printf("1\n");
            
    }
    
    return 0;
    
}
