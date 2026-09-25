# Bitwise-Number-Analyzer
A menu-driven C program that analyzes numbers using bitwise operators - checking even/odd, showing binary representation, and doubling/halving using bit shifts | BCA Project | C Programming
# 🔢 Bitwise Number Analyzer

## 📌 About This Project
A menu-driven C program that analyzes numbers using 
bitwise operators — checking even/odd, showing binary 
representation, and doubling/halving numbers using bit shifts.

## 🎯 Features
- Check Even/Odd using bitwise AND (&)
- Display 8-bit binary representation of any number
- Double a number using Left Shift (<<)
- Halve a number using Right Shift (>>)
- Tracks total numbers analyzed using a static variable

## 💡 Why I Built This
This project helped me understand:
- How bitwise operators work at the bit level
- How numbers are represented in binary
- Practical use of static storage class (remembers 
  count across operations, unlike auto variables)
- Menu-driven program design using do-while loop

## 📊 Sample Output
===== BITWISE NUMBER ANALYZER =====
Enter your choice: 2
Enter a number: 13
Binary (8-bit) of 13: 00001101

## 🔗 Real World Connection
Bitwise operations power networking (IP masking), 
cryptography, graphics (color processing), and 
Linux file permission systems.

## 📚 Concepts Used
- do-while loop (menu-driven design)
- switch-case statement
- Bitwise operators (&, <<, >>)
- static storage class
- if-else statement

## ⏱️ Time Taken
Concept: 25 min | Coding: 30 min | Testing: 15 min
Total: ~1 hour 10 minutes

## 🔧 How To Run
1. Install GCC compiler
2. Save as analyzer.c
3. Compile: gcc analyzer.c -o analyzer
4. Run: ./analyzer

## 👨‍💻 Author
Abdul Noor Khan
BCA Student | City Group of Colleges, Lucknow
#include<stdio.h>

void main()
{
    int choice, num, i, bit;
    static int totalAnalyzed = 0;
    
    do
    {
        printf("\n===== BITWISE NUMBER ANALYZER =====\n");
        printf("1. Check Even or Odd\n");
        printf("2. Show Binary Representation (8-bit)\n");
        printf("3. Double the Number (Left Shift)\n");
        printf("4. Halve the Number (Right Shift)\n");
        printf("5. Show Total Numbers Analyzed\n");
        printf("6. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        
        if(choice >= 1 && choice <= 4)
        {
            printf("Enter a number: ");
            scanf("%d", &num);
            totalAnalyzed++;
        }
        
        switch(choice)
        {
            case 1:
                if(num & 1)
                    printf("%d is ODD\n", num);
                else
                    printf("%d is EVEN\n", num);
                break;
                
            case 2:
                printf("Binary (8-bit) of %d: ", num);
                for(i = 7; i >= 0; i--)
                {
                    bit = (num >> i) & 1;
                    printf("%d", bit);
                }
                printf("\n");
                break;
                
            case 3:
                printf("%d doubled (left shift) = %d\n", num, num << 1);
                break;
                
            case 4:
                printf("%d halved (right shift) = %d\n", num, num >> 1);
                break;
                
            case 5:
                printf("Total numbers analyzed so far: %d\n", totalAnalyzed);
                break;
                
            case 6:
                printf("Thank you for using Bitwise Analyzer!\n");
                break;
                
            default:
                printf("Invalid choice! Try again.\n");
        }
        
    } while(choice != 6);
}