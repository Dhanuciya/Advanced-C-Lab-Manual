EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:
~~~
#include <stdio.h>

struct eligible
{
    int age;
    char n[50];
};

int main()
{
    struct eligible e[10];
    int i, num;

    printf("Enter number of persons: ");
    scanf("%d", &num);

    for(i = 0; i < num; i++)
    {
        printf("Enter name: ");
        scanf("%s", e[i].n);

        printf("Enter age: ");
        scanf("%d", &e[i].age);
    }

    printf("\nVaccine Eligibility Details:\n");

    for(i = 0; i < num; i++)
    {
        printf("\nName: %s\n", e[i].n);
        printf("Age: %d\n", e[i].age);

        if(e[i].age <= 6)
            printf("Vaccine Eligibility: No\n");
        else
            printf("Vaccine Eligibility: Yes\n");
    }

    return 0;
}
~~~

Output:

<img width="394" height="664" alt="image" src="https://github.com/user-attachments/assets/2c6175b5-9fc6-4f5f-8f56-a6300799fc9a" />


Result:

Thus, the program is verified successfully.
