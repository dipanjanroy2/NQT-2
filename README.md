# NQT-2

## Write a function that reads a sentence into a string and splits the sentence into words without using library functions.
You have to do this without using the strtok function. Since the delimiters are not specified you assume the default delimiters such as spaces, comma, tabs, and newlines

You examine character by character and when you encounter a delimiter you have to terminate the word with the NULL character(\0)

#include <stdio.h>
#include <string.h>
int main()
{
    char str[100];
    char splitStrings[10][10]; //can store 10 words of 10 characters
    int i,j,cnt;
    printf(“Enter a string: “);
    gets(str);
    j=0; cnt=0;
    for(i=0;i<=(strlen(str));i++)
    {
        // if space or NULL found, assign NULL into splitStrings[cnt]
        if(str[i]==‘ ‘||str[i]==‘\0‘)
        {
            splitStrings[cnt][j]=‘\0‘;
            cnt++;  //for next word
            j=0;    //for next word, init index to 0
        }
        else
        {
            splitStrings[cnt][j]=str[i];
            j++;
        }
   }
    printf(“\nOriginal String is: %s”,str);
    printf(“\nStrings (words) after split by space:\n“);
    for(i=0;i < cnt;i++)
        printf(“%s\n“,splitStrings[i]);
    return 0;
}


## Write a function that reads a sentence into a string and splits the sentence into words using library functions

#include<stdio.h>
#include<stdlib.h>

int main() 
{
    char sentence[100];
    char *p;
    printf(“\nPlease enter a sentence :”);
    gets(sentence);
    p = strtok(sentence, “\t “);
    while ( p != NULL )
    {
        printf(“%s\n”, p);
        p = strtok(NULL, “\t”);
    }
    return 0;
}


## Write a function that removes all duplicate spaces from a sentence. Your program should ensure that only one space exists between words.

/* We can remove duplicates by checking each character and having a space count.

But here we are doing it using the string library function strtok*/

#include<stdio.h>

#include<stdlib.h>

int main()

{

    char input[100];

    char output[100];

    char temp[100];

    char *p;

    printf(“\nPlease enter a sentence :”);

    gets(input);

    strcpy(temp, input);

    strcpy(output,“”);

    p = strtok(temp, “”);

    while ( p != NULL )

    {

        strcat(output,p);

        strcat(output,“”);

        printf(“%s\n“, p);

        p = strtok(NULL, “”);

    }

    printf(“%s\n“, input);

    printf(“%s\n“, output);

    printf(“%d\n“, strlen(output));

    return 0;

}

## Write a function that uses character handling library functions to determine the number of upper case, lower case, digits, spaces and punctuation characters in the specified text
#include <stdio.h>
#include <string.h>
#include <math.h>

int main ()
{
  int length, i;
  int alpha = 0, punct = 0, digit = 0, lower = 0, upper = 0,
    spaces = 0, others = 0;
  char buffer[150] = “English Language consists of letters
from A to Z and digits 1 to 9 which are
used to form : words, sentences and
paragraphs!!!”;
  length = strlen (buffer);
  for (i = 0; i < length; i++)
    {
      if (isalpha (buffer[i]))
    {
      alpha++;
      if (islower (buffer[i]))
        lower++;
      else
        upper++;
    }
      else if (isdigit (buffer[i]))
    {
      digit++;
    }
      else if (isspace (buffer[i]))
    {
      paces++;
    }
      else if (ispunct (buffer[i]))
    {
      punct++;
    }
      else
    others++;
    }
  printf (“The number of lowercase letters = %d\n“, lower);
  printf (“The number of uppercase letters = %d\n“, upper);
  printf (“The number of spaces = %d\n“, spaces);
  printf (“The number of punctuation characters = %d\n“, punct);
  printf (“The number of alphabets = %d\n“, alpha);
  printf (“The number of digits = %d\n“, digit);
}

## Write a function that takes an array called scores and 2 pointer parameters min and max and determines the minimum and maximum values and returns them to the calling function.


#include <stdio.h>

void minmax (int score[], int len, int *min, int *max)
{
    int i;
    *max = score[0];
    *min = score[0];
    for (i = 0; i < len; i++)
        {
            if (*max < score[i])
                *max = score[i];
            if (*min > score[i])
                *min = score[i];
        }
}

int main ()
{
    int score[100], i, len, min, max;
    printf (“\nPlease enter the length of array:”);
    scanf (“%d”, &len);
    for (i = 0; i < len; i++)
    {
        printf (“Enter the a[%d] values: “, i);
        scanf (“%d”, &score[i]);
    }

    minmax (score, len, &min, &max);
    printf (“\nMaximum values is: %d \nMinimum value is: %d”, max, return 0;
}

## Write a Program to remove vowels from a string?


#include <stdio.h>
#include <string.h>

int check_string (char);

int main ()
{
    char string[100], tp[100];
    int c, d = 0;

    printf (“Enter a string you want to manipulate: “);
    gets (string);

    for (c = 0; string[c] != ‘\0‘; c++)
        {
            if (check_string (string[c]) == 0)
            {
                tp[d] = string[c];
                d++;
            }
        }

    tp[d] = ‘\0‘;

    strcpy (string, tp);

    printf (“The string after deletion of vowels: %s\n“, string);

    return 0;
}

int check_string (char ch)
{
    if (ch == ‘a’ || ch == ‘A’ || ch == ‘e’ || ch == ‘E’ || ch == ‘i’ || ch == ‘I’ || ch == ‘o’ || ch == ‘O’ || ch == ‘u’ || ch == ‘U’)
        return 1;
    else
        return 0;
}


## Write a Program for Matrix Multiplication(Universal Program)



#include <stdio.h>


void main ()

{

    int arr[2][2], arr2[2][2];

    int temp, i, j;

    printf (“Enter elements for 1 st array \n“);

    for (i = 0; i < 2; i++)

        {

            for (j = 0; j < 2; j++)

            {

                scanf (“%d”, &arr[i][j]);

            }

        }

    printf (“Enter elements for 2nd array\n“);

    for (i = 0; i < 2; i++)

        {

            for (j = 0; j < 2; j++)

            {

                scanf (“%d”, &arr2[i][j]);

            }

        }

    printf (“elements for 1st and 2nd array\n“);

    for (i = 0; i < 2; i++)

        {

            for (j = 0; j < 2; j++)

            {

                printf (“%d \t“, arr[i][j]);

            }

            printf (“\t“);

            for (j = 0; j < 2; j++)

            {

                printf (“%d \t“, arr2[i][j]);

            }

            printf (“\n“);

        }

    printf (“\n“);

    for (i = 0; i < 2; i++)

        {

            for (j = 0; j < 2; j++)

            {

                for (int k = 0; k < 2; k++)

                    {

                        temp = temp + ((arr[i][k]) * (arr2[k][j]));

                    }

                printf (“%d\t“, temp);

                temp = 0;

            }

            printf (“\n“);

        }

}


##   Given an array of integers, Find the sum of its elements.
For example, If the array ar = [1,2,3], 1+2+3=6, so return 6.


#include<stdio.h>

int main ()
{
  int n;
  int i;
  scanf (“%d”, &n);
  int array[n];
  int sum_of_array = 0;

  for (i = 0; I < n; i++)
    {
      scanf (“%d”, &array[i]);
      sum_of_array += array[i];
    }

  printf (“%d \n“, sum_of_array);
  return 0;
}

## Given a square matrix. Calculate the absolute difference between the
sums of its diagonals.


#include<iostream>
using namespace std;

int main ()
{
    int n;
    cin >> n;
    int arr[n][n];
    long long int d1 = 0;   // First diagonal
    long long int d2 = 0;   // Second diagonal

    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < n; j++)
        {
            cin >> arr[i][j];
            if (i == j) 
                d1 += arr[i][j];
            if (i == n – j – 1) 
                d2 += arr[i][j];

        }
    }
    cout << abs (d1 – d2) << end;   // absolute difference of the sum across the diagonals
    return 0;
}
  
  
 ## Given five positives, Find the minimum and maximum values that can be calculated by summing exactly four the five integers. Then print the respective minimum and maximum values as a single line of two space- separated long integer.   
  
  
  
  
```
  
  
import java.util.*;

public class Solution
{
    public static void main (String[]args)
    {
        Scanner scan = new Scanner (System.in);
        long sum = 0;
        long min = 1000000000;
        long max = 0;

        While (Scan.hasNext ())
            {
                long n = scan.nextLong ();
                sum = sum + n;
                if (min > n)
                {
                    min = n;
                }
                if (max < n)
                {
                    max = n;
                }
            }
        scan.close ();
        System.out.println (sum – max) + ” “ +(sum – min));
    }
}
  
```
