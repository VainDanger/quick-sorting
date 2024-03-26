# quick-sorting
# recursion and quick sorting

#include <iostream>

void quick(int (&nu)[], int l, int r)
{
  if(l>r)
  {
    return ;
  }
  int p=nu[(l+r)/2];
  int i=l,j=r;
  while(i<=j)
    {
      while(nu[i]<p)  i++;
      while(nu[j]>p)  j--;
      if(i<=j)  {std::swap(nu[i],nu[j]);  i++;  j--;}
    }
  quick(nu,l,j);
  quick(nu,i,r);
}

int main()
{
  int l=0, r=9;
  int nu[10];
  for(int i=0; i<10; i++)  nu[i]=rand()%11;
  for(int i=0; i<10; i++)  std::cout<<nu[i]<<'\t';
  std::cout<<'\n';
  quick(nu,l,r);
  for(int i=0; i<10; i++)  std::cout<<nu[i]<<'\t';
}
