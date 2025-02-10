# Cyclic_Group
#include<stdio.h>
#include<math.h>
int gcd(int a,int b)
{
    if(b==0)
    {
        return a;
    }
    return gcd(b,a%b);    // To calculate gcd
}
int main()
{
    int n,m;             // to check (Zn*Zm, +) is a cyclic group or not
    printf("Enter m,n:\n");
    scanf("%d%d",&m,&n);
    
    if(m>0 && n>0)

    {
            printf("Z%d+Z%d |\n",n,m);
    printf("_______________________________\n");
    
    for(int i=0;i<m;i++)
    {
    for(int j=0;j<n;j++)
    {
        printf("(%d %d)\t|",i,j);
    
        for(int k=0;k<m;k++)
        {
            for(int l=0;l<n;l++)
            {     
                printf("(%d%d)",(i+k)%m,(j+l)%n);
            }  
        }
       
      printf("\n");
    }
    }
     
    if(gcd(m,n)==1)
    {
        printf("Z%d + Z%d is a cyclic group.\n",m,n);   // condition for cyclic group
    }
    }
    else
    {
        printf("It is not cyclic.");
    }
             
    
    
    return 0;
}
