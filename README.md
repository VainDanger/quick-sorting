# quick-sorting
# recursion and quick sorting

#include<iostream>

void quick(int nu[], int l, int r)
{
  if(l>r)  return ;
  int i=l,j=r,p=nu[(l+r)/2];
  while(i<=j)
    {
      while(nu[i]<p)  i++;
      while(nu[j]>p)  j--;
      if(i<=j)  {std::swap(nu[i],nu[j]); i++;  j--;}
    }
  quick(nu,i,r);
  quick(nu,l,j);
}

int main(void)
{
  int n,l=0;  std::cin>>n;
  int nu[n],r=n-1;
  for(int i=0; i<n; i++)  std::cin>>nu[i];
  quick(nu,l,r);
  for(int i=0; i<n; i++)  std::cout<<nu[i]<<' ';
}
