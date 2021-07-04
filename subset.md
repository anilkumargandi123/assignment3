#include<iostream>
using namespace std;
int arr_subset(int a[],int b[],int m,int n)
{
	int i,j;
	for(i=0;i<n;i++)
	{
		for(j=0;j<m;j++)
		{
			if(b[i]==a[j])
			{
				break;
			}
		}
		if(j==6)
		{
			return -1;
		}
	}
	return 1;
}
int main()
{
	int m,n;
	cin>>m>>n;
	int a[m],b[n];
	int i;
	for(i=0;i<m;i++)
	{
		cin>>a[i];
	}
	for(i=0;i<n;i++)
	{
		cin>>b[i];
	}
	int result = arr_subset(a,b,m,n);
	if(result==1)
	{
		printf("Subset");
	}
	else
	{
		printf("Not a subset");
	}
