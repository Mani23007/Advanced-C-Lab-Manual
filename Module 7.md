# EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

## Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

## Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
## Program:
```c
#include <stdio.h>

struct Person {
    char name[50];
    int age;
};

int main() {
    int n;
    printf("Enter number of persons: ");
    scanf("%d", &n);

    struct Person people[n];

    for (int i = 0; i < n; i++) {
        printf("\nEnter name of person %d: ", i + 1);
        scanf("%s", people[i].name);

        printf("Enter age of %s: ", people[i].name);
        scanf("%d", &people[i].age);
    }

    printf("\n--- Eligibility Result ---\n");

    for (int i = 0; i < n; i++) {
        if (people[i].age >= 6)
            printf("%s is ELIGIBLE for vaccine\n", people[i].name);
        else
            printf("%s is NOT eligible for vaccine\n", people[i].name);
    }

    return 0;
}
```

## Output:
<img width="495" height="491" alt="image" src="https://github.com/user-attachments/assets/2a2aa0bd-00ee-4f9b-bbe0-1dfde653b556" />


## Result:
Thus, the program is verified successfully. 


# EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION

## Aim:
To write a C program for passing structure as function and returning a structure from a function

## Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
## Program:
```c
#include <stdio.h>

struct Person {
    char name[50];
    int age;
};

/* Function that takes a structure and returns a structure */
struct Person updateAge(struct Person p) {
    p.age += 1;  // Just modifying to show the return works
    return p;    // Returning updated structure
}

int main() {
    struct Person p1;

    printf("Enter name: ");
    scanf("%s", p1.name);

    printf("Enter age: ");
    scanf("%d", &p1.age);

    // Passing structure to function
    struct Person updated = updateAge(p1);

    printf("\n--- Updated Person Details ---\n");
    printf("Name : %s\n", updated.name);
    printf("Age  : %d\n", updated.age);

    return 0;
}
```

## Output:

<img width="527" height="307" alt="image" src="https://github.com/user-attachments/assets/00064bb2-6a9d-4beb-8c6c-917315d0e272" />

## Result:
Thus, the program is verified successfully


 
# EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

## Aim:
To write a C program to read a file name from user

## Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
## Program:
```c
#include <stdio.h>

int main() {
    char filename[100];

    printf("Enter file name: ");
    scanf("%s", filename);

    printf("You entered: %s\n", filename);

    return 0;
}
```

## Output:

<img width="547" height="215" alt="image" src="https://github.com/user-attachments/assets/0dddc04f-3ef5-4d65-8ad7-6dd2f02fa217" />

## Result:
Thus, the program is verified successfully.
 

# EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE

## Aim:
To write a C program to read, a file and insert text in that file.

## Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
## Program:
```c
#include <stdio.h>

int main() {
    char filename[50];
    char text[100];
    FILE *fp;

    printf("Enter file name: ");
    scanf("%s", filename);

    fp = fopen(filename, "a");   // open file in append mode
    if (fp == NULL) {
        printf("File cannot be opened.\n");
        return 1;
    }

    printf("Enter text to write: ");
    getchar();                    // clear leftover newline
    fgets(text, sizeof(text), stdin);

    fputs(text, fp);              // write to file
    fclose(fp);

    printf("Text written successfully.\n");

    return 0;
}
```

## Output:

<img width="667" height="232" alt="image" src="https://github.com/user-attachments/assets/9b2afc19-b20b-4955-8912-d084847666ad" />


## Result:
Thus, the program is verified successfully.



# Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

## Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

## Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

## Program:
```c

#include <stdio.h>
#include <stdlib.h>

struct Subject {
    char name[50];
    int marks;
};

int main() {
    int n;
    struct Subject *s;

    // 1 & 2. Input the number of subjects
    printf("Enter number of subjects: ");
    scanf("%d", &n);

    // 3 & 4. Dynamically allocate memory
    s = (struct Subject *) malloc(n * sizeof(struct Subject));

    // 5. Check if allocation failed
    if (s == NULL) {
        printf("Memory not allocated.\n");
        return 1;
    }

    // 6 & 7. Input details for each subject
    for (int i = 0; i < n; i++) {
        printf("\nEnter name of subject %d: ", i + 1);
        scanf("%s", s[i].name);

        printf("Enter marks of %s: ", s[i].name);
        scanf("%d", &s[i].marks);
    }

    // 8 & 9. Display the details
    printf("\n--- Subject Details ---\n");
    for (int i = 0; i < n; i++) {
        printf("Subject: %s, Marks: %d\n", s[i].name, s[i].marks);
    }

    // 10 & 11. Free allocated memory
    free(s);

    // 12 & 13. End
    return 0;
}
```




## Output:

<img width="532" height="481" alt="image" src="https://github.com/user-attachments/assets/88513809-1ea4-49f6-81ea-7d75c0b34b3d" />


## Result:
Thus, the program is verified successfully.
