# DSA-Bootcamp-assignment

Q1. Write a program to Swap to two numbers.
Ans.  #include<stdio.h>
  int main()
  {
  	int a,b;
  	clrscr();
  	printf("Enter two numbers : \n");
  	scanf("%d %d",&a,&b);
  	printf("\n Before swapping a=%d\n b=%d",a,b);
  	a=a+b;
  	b=a-b;
  	a=a-b;
  	printf("\nAfter swapping a=%d\n b=%d",a,b);
  	getch();
  	return 0;
  }
  
  Q2. Write a program to find the largest number among three numbers entered by the user.
  Ans. #include <stdio.h>
int main()
{
    int num1, num2, num3;
    printf(" Enter the number1 = ");
    scanf("%d", &num1);
    printf("\n Enter the number2 = ");
    scanf("%d", &num2);
    printf("\n Enter the number3 = ");
    scanf("%d", &num3);
    if (num1 > num2)
    {
        if (num1 > num3)
        {
            printf("\n Largest number = %d \n",num1);
        }
        else
        {
            printf("\n Largest number = %d \n",num3);
        }
    }
    else if (num2 > num3)
    {
        printf("\n Largest number = %d \n",num2);
    }
    else
    {
        printf("\n Largest number = %d \n",num3);
    }
    return 0;
}

Q3. Write a program to check whether a year entered by a user is Leap year or not.
Ans.#include <stdio.h>
int main() {
   int year;
   printf("Enter a year: ");
   scanf("%d", &year);

   // leap year if perfectly divisible by 400
   if (year % 400 == 0) {
      printf("%d is a leap year.", year);
   }
   // not a leap year if divisible by 100
   // but not divisible by 400
   else if (year % 100 == 0) {
      printf("%d is not a leap year.", year);
   }
   // leap year if not divisible by 100
   // but divisible by 4
   else if (year % 4 == 0) {
      printf("%d is a leap year.", year);
   }
   // all other years are not leap years
   else {
      printf("%d is not a leap year.", year);
   }

   return 0;
}

Q4. Write a program to display Fibonacci Series upto nth term. (Using loops)
Ans. #include<stdio.h>
 
main()
{
   int n, first = 0, second = 1, next, c;
 
   printf("Enter the number of terms\n");
   scanf("%d",&n);
 
   printf("First %d terms of Fibonacci series are :-\n",n);
 
   for ( c = 0 ; c < n ; c++ )
   {
      if ( c <= 1 )
         next = c;
      else
      {
         next = first + second;
         first = second;
         second = next;
      }
      printf("%d\n",next);
   }
 
   return 0;
}

Q5. Write a program to check whether a number is Prime or Not.
Ans.#include <stdio.h>
int main() {
  int n, i, flag = 0;
  printf("Enter a positive integer: ");
  scanf("%d", &n);

  for (i = 2; i <= n / 2; ++i) {
    // condition for non-prime
    if (n % i == 0) {
      flag = 1;
      break;
    }
  }

  if (n == 1) {
    printf("1 is neither prime nor composite.");
  } 
  else {
    if (flag == 0)
      printf("%d is a prime number.", n);
    else
      printf("%d is not a prime number.", n);
  }

  return 0;
}

Q6. Print this pattern using loops
For n=5
	    *
	   * *
	  * * *
	 * * * *
	* * * * *
Ans.#include <stdio.h>
int main() {
   int i, space, rows, k = 0;
   printf("Enter the number of rows: ");
   scanf("%d", &rows);
   for (i = 1; i <= rows; ++i, k = 0) {
      for (space = 1; space <= rows - i; ++space) {
         printf("  ");
      }
      while (k != 2 * i - 1) {
         printf("* ");
         ++k;
      }
      printf("\n");
   }
   return 0;
}

Q7.Write a program that takes n elements from the user and displays the second largest element of an array.
Ans. // C program to find second largest
// element in an array

#include <limits.h>
#include <stdio.h>

/* Function to print the second largest elements */
void print2largest(int arr[], int arr_size)
{
	int i, first, second;

	/* There should be atleast two elements */
	if (arr_size < 2) {
		printf(" Invalid Input ");
		return;
	}

	first = second = INT_MIN;
	for (i = 0; i < arr_size; i++) {
		/* If current element is greater than first
		then update both first and second */
		if (arr[i] > first) {
			second = first;
			first = arr[i];
		}

		/* If arr[i] is in between first and
		second then update second */
		else if (arr[i] > second && arr[i] != first)
			second = arr[i];
	}
	if (second == INT_MIN)
		printf("There is no second largest element\n");
	else
		printf("The second largest element is %dn", second);
}

/* Driver program to test above function */
int main()
{
	int arr[] = { 12, 35, 1, 10, 34, 1 };
	int n = sizeof(arr) / sizeof(arr[0]);
	print2largest(arr, n);
	return 0;
}

Q8.Given an array and a number, d, perform d left rotations on the array.
Ans. // C program to rotate an array by
// d elements
#include <stdio.h>

/* Function to left Rotate arr[] of size n by 1*/
void leftRotatebyOne(int arr[], int n);

/*Function to left rotate arr[] of size n by d*/
void leftRotate(int arr[], int d, int n)
{
	int i;
	for (i = 0; i < d; i++)
		leftRotatebyOne(arr, n);
}

void leftRotatebyOne(int arr[], int n)
{
	int temp = arr[0], i;
	for (i = 0; i < n - 1; i++)
		arr[i] = arr[i + 1];
	arr[n-1] = temp;
}

/* utility function to print an array */
void printArray(int arr[], int n)
{
	int i;
	for (i = 0; i < n; i++)
		printf("%d ", arr[i]);
}

/* Driver program to test above functions */
int main()
{
	int arr[] = { 1, 2, 3, 4, 5, 6, 7 };
	leftRotate(arr, 2, 7);
	printArray(arr, 7);
	return 0;
}


