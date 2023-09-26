# LCM-of-Two-Numbers-using-Recursion-in-CPP

LCM of Two Numbers using Recursion in C++
 

Here, in this page we will discuss the program to find the LCM of Two numbers using Recursion in C++ Programming Language. We are given with two integers and need to find the LCM of the given numbers.  The LCM of two integers num1 and num2 is the smallest positive integer that is perfectly divisible by both num1 and num2(without a remainder). 

Example :

Input : num1 = 3 num2 = 21
Output : LCM of 3 and 21 is 21.
LCM of Two Numbers using Recursion in C++
Relationship Between HCF and LCM

To find the LCM of the given two numbers using recursion. We first calculate the HCF of the numbers using recursion and then Calculate the LCM using the following relationship :
LCM * HCF = num1 * num2
Different Methods Discussed in this page :
We have discussed the following methods using recursion to find the HCF of given two numbers and then can find the LCM using that HCF.

Method 1 :Recursive Euclidean Algorithm: Repeated Subtraction to calculate the HCF
Method 2: Modulo Recursive Euclidean Algorithm: Repeated Subtraction to calculate the HCF
You can also check out the given link to understand the recursive algorithm to find the HCF  Click Here

 
Method 1 :
This method is based on  Euclidean Algorithm.

Create a variable say HCF to hold the value return by getHCF(int num1, num2).
Then calculate the LCM = (num1 *num2)/HCF
Euclidean Algorithm
HCF of two numbers doesn’t change if smaller number is subtracted from a bigger number
Code to find LCM of a Number using Recursion in C++
Run
 #include<bits/stdc++.h>
using namespace std;

// Recursive function for repeated subtraction HCF calculation
int getHCF(int num1, int num2)
{
   if (num1 == 0)
      return num2;

   if (num2 == 0)
      return num1;

   // base case
   if (num1 == num2)
      return num1;

   if (num1 > num2)
      return getHCF(num1 - num2, num2);

   return getHCF(num1, num2 - num1);
}

int main()
{
   int num1 = 3, num2 = 21, HCF, LCM;

   HCF = getHCF(num1, num2);
 
   LCM = (num1*num2)/HCF;

   cout<<"LCM of " << num1<< " and " << num2 << " is "<< LCM;

   return 0;
}
Output

LCM of 3 and 21 is 21
Method 2 :
It is similar to what we have seen in method 1. In Addition, we are using modulo operation to reduce the number of subtractions required and improve time complexity for finding the HCF first .

Create a variable say HCF to hold the value return by getHCF(int num1, num2).
Then calculate the LCM = (num1 *num2)/HCF
Code to find LCM of a Number using Recursion in C++
Run
#include<bits/stdc++.h>
using namespace std;

int getHCF(int num1, int num2)
{
  return num2 == 0 ? num1 : getHCF(num2, num1 % num2);
}

int main()
{
  int num1 = 3, num2 = 21, HCF, LCM;

  HCF = getHCF(num1, num2);

  LCM = (num1*num2)/HCF;

  cout<<"LCM of " << num1 << " and " << num2 << " is " << LCM;

  return 0;
}
Output

LCM of 3 and 21 is 21
