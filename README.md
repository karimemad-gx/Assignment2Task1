# Assignment2Task1
# Name:Kareem Emad Abu Einen
# ID:20220249
# Course Name:Structured programming
# FCAI

for FCAI structured programming assignment
#include <iostream>
#include <limits>
using namespace std;

int main()
{
int number,sum,player1,player2;
sum=0;
while (0<=sum<=90)
{
    cout<< "enter an integer number(1-10):\n ";
    cin>> number;
    while (true)
    {
        if(cin.fail())
        {
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(),'\n');
            cout <<"Invalid input please,enter a valid integer input:\n";
        }
        if(!cin.fail())
        {
            break;
        }
    }
    if (1<=number<=10)
    {
        player1=number;
        sum+=number;
        if (sum >90)
        {
            break;
        }
        else if (sum<=90)
        {
            cout << "Enter an integer number(1-10):\n";
            cin >> number;
            while(true)
            {
                if(cin.fail())
                {
                    cin.clear();
                    cin.ignore(numeric_limits<streamsize>::max(),'\n');
                    cout<<"Invalid input please,enter a valid integer input:\n";
                }
                if(!cin.fail())
                {
                    break;
                }
            }
            if (1<=number<=10)
            {
                player2=number;
                sum+=number;
                if (sum>90)
                {
                    break;
                }
            }
            else
            {
                cout <<"Invalid input please, enter a valid integer input:\n";
            }
         }
      }
      else
      {
          cout << "Invalid input please, enter a valid integer input:\n";
      }
}
while (sum>90)
{
    cout << "Enter an integer number (1-(10-(sum%10)))\n";
    cin >> number;
    while(true)
    {
        if(cin.fail())
        {
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(),'\n');
            cout<<"Invalid input please,enter a valid integer input\n";
        }
        if(!cin.fail())
        {
            break;
        }
    }
    if (1<=number<=(10-(sum%10)))
    {
        player1=number;
        sum+=number;
        if (sum==100)
        {
            cout << "player1 is winner\n";
            break;
        }
        else if (sum!=100)
        {
            cout <<"Enter an integer number (1-(10-(sum%10)))\n";
            cin >> number;
            while(true)
            {
                if(cin.fail())
                {
                    cin.clear();
                    cin.ignore(numeric_limits<streamsize>::max(),'\n');
                    cout<<"Invalid input please,enter a valid integer input\n";
                }
                if(!cin.fail())
                {
                    break;
                }
            }
            if (1<=number<=(10-(sum%10)))
            {
                player2=number;
                sum+=number;
                if (sum==100)
                {
                    cout <<"player2 is winner\n";
                    break;
                }
            }
            else
            {
                cout <<"Invalid input please, enter a valid input\n";
            }
        }
    }
    else
    {
        cout <<"Invalid input please, enter a valid input\n";
    }
}
return 0;

}
##project notes
/* This code is in C++ language about 100 game where two players start from 0 and alternatively add a number from 1 to 10 to the sum and the first player who makes the sum reach 100 is the winner.
There are various functions to validate the input like cin.fail(),cin.ignore()and cin.clear().
cin.fail():This function returns true when input failure occurs. it whould be an input that is not an integer.
cin.clear():This is used to clear the error state of the buffer so that further processing of input can take place.
cin.ignore():This function is used to ignore the rest of the line after the first instance of error that has occured.
So if the user input wrong data type like string or float or double instead of integer these functions will warn the user and tell him/her to enter a valid input.
when i say player1=number it means player1 is the one who entered the number and when i say player2=number it means player2 is the one who entered the number
when the sum exceeds 90 the players have to enter numbers between 1 and (10-sum%10) because the sum must not become more than 100 .
for example : if the sum is 91 the  entered number must be from 1 to 9 and (10-sum%91=9) and so on
if the user enter integer but it is zero or negative numbers or numbers more than 10 the programm warns the user and tell him/her to enter a right number.
the header preprocessor # include <imits> defines constants with the limits of fundamental integral types for the specific system and compiler implementation used.
numeric_limits is a class for representing information about scalar types.specializations are included for each fundamental type integer , floating point etc,.
break statment is used to exit the while loop.# include <iostream> is a library backage which supports all basic input and output operations such as printing data and collecting input from user etc.*/
# The algorithm I developed for my encryption and decryption
#include <iostream>
#include <limits>
#include <string>
#include <vector>
#include <locale>
#include <functional>
#include <algorithm>
#include <bits/stdc++.h>

using namespace std;

bool isWhitespace(unsigned char c) {
    if (c == ' ' || c== '\t' || c=='\n' || c=='\r' || c=='\f' || c=='\v' ){
            return true;
    } else {
        return false;
    }
}

int main()
{
  string plaintext;
int n=3;
cout <<"Enter plaintext\n";
vector<string> plaintexte;
getline(cin,plaintext);
plaintexte.push_back(plaintext);
plaintext.erase(remove_if(plaintext.begin(), plaintext.end(), isWhitespace), plaintext.end());
transform(plaintext.begin(), plaintext.end(), plaintext.begin(), ::tolower);
vector<vector<char>> a(n,vector<char>(plaintext.size(),' '));
 int  j=0;
 int flag=0;
    for(int i=0;i<plaintext.size();i++){
        a[j][i] = plaintext[i];
         if(j==n-1){
            flag=1;
        }
        else if(j==0){
          flag=0;
        }
        if(flag==0){
           j++;
        }
        else{
          j--;
        }
    }
    for(int i=0;i<n;i++){
        for(int j=0;j<a[i].size();j++){
            if(a[i][j]!=' '){
                cout<<a[i][j];
            }
        }
    }
cout<<'\n';
    return 0;
}
# 12 of the basic operations that can be done on github
Git push : Push operation is used to upload local repository data to a remote repository. Git push is performed using
Git commit :Commit operation in git is used to save all changes present in the staging area along with a short description from the user in a local repository.
Git add : The Add operation is used to adds a change in the working directory to the staging area. A staging area is a virtual place that collects all the files you want to include in the next commit.
Git clone : Creates a copy of an existing Git repository
Git branch :This command is your general-purpose branch administration tool. It lets you create isolated development environments within a single repository.
Git checkout :In addition to checking out old commits and old file revisions, git checkout is also the means to navigate existing branches. Combined with the basic Git commands, it’s a way to work on a particular line of development.
Git Pull :The pull operation is used to fetch and download data from a remote repository and merge it into the local repository to match that code or data.
Git status:Displays the state of the working directory and the staged snapshot. You’ll want to run this in conjunction with git add and git commit to see exactly what’s being included in the next snapshot.
Git init:Initializes a new Git repository. If you want to place a project under revision control, this is the first command you need to learn. 
Git merge :A powerful way to integrate changes from divergent branches. After forking the project history with git branch, git merge lets you put it back together again.
Git config :A convenient way to set configuration options for your Git installation. You’ll typically only need to use this immediately after installing Git on a new development machine.
Git log :Lets you explore the previous revisions of a project. It provides several formatting options for displaying committed snapshots.












## project notes
