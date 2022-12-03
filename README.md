#include<stdio.h>
void diff();
void sym();
void uni();
void inter();

int main(){
	int a;
	printf("Enter 1 for union.");
	printf("\nEnter 2 for intersection.");
	printf("\nEnter 3 for difference.");
	printf("\nEnter 4 for Symmetric difference.\n");
	scanf("%d",&a);
	if(a==1){

   		uni();
	   }
	else if(a==2){
   	inter();
   }
    else if(a==3){
		diff();
    }
	else if(a==4){
		sym();
	}
	else
		{
			printf("\nEnter your decision");
		}
	return 0;	
}

void diff(){
	int a[10],b[10],c[10],d[10],m=0,k=0,n1,n2,l,i,j;
    printf("Enter size of set A\n");
    scanf("%d",&n1);
    printf("Enter element of set\n");
    for( i=0;i<n1;i++)
    scanf("%d",&a[i]);
    printf("Enter size of set B\n");
    scanf("%d",&n2);
    printf("Enter element of set\n");
    for( i=0;i<n2;i++)
    scanf("%d",&b[i]);




    // logic for find A-B

    for( i=0;i<n1;i++)
    {
        for(j=0;j<n2;j++)
        {
            if(b[j]==a[i])
             break;
        }
        if(j==n2)
        {
          // here we check that is element already present in the set 
          // if present than ignore it otherwise add to the difference set   
            for(l=0;l<k;l++)
            {
                if(c[l]==a[i])
                 break;
            }
            if(l==k)
            {
                c[k]=a[i];
                k++;
            }
        }

    }

    // logic for find B-A

    for( i=0;i<n2;i++)
    {
        for(j=0;j<n1;j++)
        {
            if(b[i]==a[j])
             break;
        }
        if(j==n1)
        {
          // here we check that is element already present in the set 
          //if present than ignore it otherwise add to the difference set
            for(l=0;l<m;l++) 
            {
                if(d[l]==b[i])
                 break;
            }
            if(l==m)
            {
                d[m]=b[i];
                m++;
            }
        }

    }
     printf("Difference of A-B is:-\n");
     for(i=0;i<k;i++)
     {
         printf("%d ",c[i]);
     }
     printf("\n");
     printf("Difference of B-A is:-\n");
     for(i=0;i<m;i++)
     {
         printf("%d ",d[i]);
     }
}
void sym(){
	int a[10],b[10],c[10],d[10],m=0,k=0,n=0,n1,n2,l,i,j,sy[100];
    printf("Enter size of set A\n");
    scanf("%d",&n1);
    printf("Enter element of set\n");
    for( i=0;i<n1;i++)
    scanf("%d",&a[i]);
    printf("Enter size of set B\n");
    scanf("%d",&n2);
    printf("Enter element of set\n");
    for( i=0;i<n2;i++)
    scanf("%d",&b[i]);


    // logic for find A-B

    for( i=0;i<n1;i++)
    {
       // here we check that is b[i] already present in the ans set
      // if present then ignore it otherwise add it to the ans set
        for(j=0;j<n2;j++)
        {
            if(b[j]==a[i])
             break;
        }
        if(j==n2)
        {

            for(l=0;l<k;l++)
            {
                if(c[l]==a[i])
                 break;
            }
            if(l==k)
            {
                c[k]=a[i];
                k++;
            }
        }

    }

    // logic for find B-A

    for( i=0;i<n2;i++)
    {
        for(j=0;j<n1;j++)
        {
            if(b[i]==a[j])
             break;
        }
        if(j==n1)
        {
          // here we check that is b[i] already present in the ans set
          // if present then ignore it otherwise add it to the ans set 
            for(l=0;l<m;l++)
            {
                if(d[l]==b[i])
                 break;
            }
            if(l==m)
            {
                d[m]=b[i];
                m++;
            }
        }

    }

    //logic for symmetric Difference

    for(i=0;i<k;i++)
    {
        sy[n]=c[i];
        n++;
    }
    for(i=0;i<m;i++)
    {
        sy[n]=d[i];
        n++;
    }

    printf("\nsymmetric Difference of sets is:-\n");
    for(i=0;i<n;i++)
     printf("%d ",sy[i]);
}

void uni(){
	int a[10],b[10],i,c[10],d[10],j,k=0,n1,n2,l=0,F[100],G[100];

   // taking input set A

   printf("Enter number of  element of set A\n");
   scanf("%d",&n1);
   printf("Enter the element of set A \n");
   for(i=0;i<n1;i++)
      scanf("%d",&a[i]);

    // taking input set B

   printf("Enter number of element of set B\n");
   scanf("%d",&n2);
   printf("Enter the element of set B \n");
   for(i=0;i<n2;i++)
     scanf("%d",&b[i]);

   // logic for calculate union

   // copy the element of set A in set C
   for(i=0;i<n1;i++)
   {
       // repeted element is not allowed so we check is any value repeted
      for(j=0;j<k;j++)
      {
         if(c[j]==a[i]) 
            break;
       }
       if(j==k) //if not repesated then store value in set c 
       {
          c[k]=a[i];
          k++;
       }
    }
    // copy element of set B in set C
   for(i=0;i<n2;i++)
   {
       // check for repeted element
      for(j=0;j<k;j++)
      {
         if(c[j]==b[i])
           break;
      }
     if(j==k) // if element is not repeted then store in set C
     {
       c[k]=b[i];
       k++;
     }
   }

   // printing of union of set A and set B
   printf("Union of set A and B is:-\n");
    for(i=0;i<k;i++)
      printf("%d ",c[i]);

}
void inter(){
	int a[10],b[10],i,c[10],d[10],j,k=0,n1,n2,l=0,F[100],G[100];
	printf("Enter size of set A\n");
    scanf("%d",&n1);
    printf("Enter element of set\n");
    for( i=0;i<n1;i++)
    scanf("%d",&a[i]);
    printf("Enter size of set B\n");
    scanf("%d",&n2);
    printf("Enter element of set\n");
    for( i=0;i<n2;i++)
    scanf("%d",&b[i]);

// Logic for intersection

    for( i=0;i<n1;i++)
    {
         for(j=0;j<n2;j++)
         {
            if(a[i]==b[j])
            {
                c[l]=a[i];
                l++;
            }
         }

    }

    // Printing the elements of intersection of set A and set B
    printf("\nIntersection of set A and set B is:-\n");
    for(i=0;i<l;i++)
      printf("%d ",c[i]); 
}

