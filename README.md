# operator
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>
//Complete the following function.


void calculate_the_maximum(int n, int k) {
  //Write your code here.
  int and[5000],or[5000],xor[5000],max_and,max_or,max_xor;
  int count=0;
  for(int i=1;i<n;i++)
    {
      for(int j=1;j<=n;j++)
      {
          if(j==i||j<i)
          {
            continue;
          }
          else 
          {
              
              and[count]=i&j;
              or[count]=i|j;
              xor[count]=i^j;
              if(count>=1)
              {
                  if(and[count]>=and[count-1])
                  {
                      max_and=and[count];
                  }
                  else{
                      max_and=and[count-1];
                  }
                  if(or[count]>=or[count-1])
                  {
                      max_or=or[count];
                  }
                  else{
                      max_or=or[count-1];
                  }
                  if(xor[count]>=xor[count-1])
                  {
                      max_xor=xor[count];
                  }
                  else{
                      max_xor=xor[count-1];
                  }
                 
              }
              count++;
          }
       }
    }
    printf("%d\n%d\n%d",max_and,max_or,max_xor);
  
  }

int main() 
{
    int n, k;
    scanf("%d %d", &n, &k);
    calculate_the_maximum(n, k);
 
    return 0;
}
