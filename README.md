Removing all characters from the string except alphabets.
In this article we will be learning about Removing all characters from the string except alphabets.

Removing all characters excepts alphabets means removing special characters like ‘*’, ‘?’,  ‘@’,  etc. and numeric characters like ‘1’, ‘2’, ‘3’, etc. from the input string.

input string :- 1_pre9pins34a

Output sting:- prepinsta

Removing all characters from the string except alphabets
Algorithm:
Initialize the variables.
Accept the input.
Initialize a for loop and terminate it at the end of string.
Iterate each character through the loop.
Remove non alphabetical characters using while loop.
Store only alphabetical characters from the string using another for loop
Print result.
While loop in C
C++ programming code to remove all characters from string except alphabets
Run
#include <iostream>
using namespace std;
int main()
{
    //Initializing variable.
    char str[100];
    int i, j;
    
    //Accepting input.
    cout<<"Enter a string : ";
    gets(str);

    //Iterating each character and removing non alphabetical characters.
    for(i = 0; str[i] != '\0'; ++i)
    {
        while (!( (str[i] >= 'a' && str[i] <= 'z') || (str[i] >= 'A' && str[i] <= 'Z') || str[i] == '\0') )
        {
            for(j = i; str[j] != '\0'; ++j)
            {
                str[j] = str[j+1];
            }
            str[j] = '\0'; 
        }
    }
    //Printing output.
    cout<<"After removing non alphabetical characters the string is :";
    puts(str);
    return 0;
}
Output:
Enter a string : *1prep_insta*
After removing non alphabetical characters the string is :prepinsta
Note
 To do this first we will iterate each character of the string through a for loop then we will check if the character iterated is an alphabetic character or not. If it is found to be an alphabetical character than we will store it else we will not. In this way we will get a string that have only alphabetical characters as an output.
Method 2
Run
#include <bits/stdc++.h>
using namespace std;
// function to remove characters and
// print new string
void removeSpecialCharacter(string s) {
    for (int i = 0; i < s.size(); i++) {
        // Finding the character whose
        // ASCII value fall under this
        // range
        if (s[i] < 'A' || s[i] > 'Z' && s[i] < 'a' || s[i] > 'z') {
            // erase function to erase
            // the character
            s.erase(i, 1);
            i--;
        }
    }
    cout << s;
}
// driver code
int main() {
    string s = "P*re;p..ins't^a?";
    removeSpecialCharacter(s);
    return 0;
}
Output
Prepinsta
