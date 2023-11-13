#include <stdio.h>
#include <string.h>

#define NUM_STUDENTS 5
#define NUM_UNITS 5

struct Student {
    char name[50];
    char regNumber[15];
    float grades[NUM_UNITS];
    float averageGrade;
};

// Function to calculate the average grade for a student
float calculateAverage(float grades[], int numUnits) {
    float sum = 0.0;
    for (int i = 0; i < numUnits; i++) {
        sum += grades[i];
    }
    return sum / numUnits;
}

int main() {
    struct Student students[NUM_STUDENTS];
    float highestGrade = -1.0;
    float lowestGrade = 101.0;

    // Input data for each student
    for (int i = 0; i < NUM_STUDENTS; i++) {
        printf("Enter details for student %d:\n", i + 1);
        printf("Name: ");
        scanf("%s", students[i].name);
        printf("Registration Number: ");
        scanf("%s", students[i].regNumber);
        
        for (int j = 0; j < NUM_UNITS; j++) {
            printf("Enter grade for Unit %d: ", j + 1);
            scanf("%f", &students[i].grades[j]);
            
            // Update highest and lowest grades
            if (students[i].grades[j] > highestGrade) {
                highestGrade = students[i].grades[j];
            }
            if (students[i].grades[j] < lowestGrade) {
                lowestGrade = students[i].grades[j];
            }
        }

        // Calculate and store the average grade
        students[i].averageGrade = calculateAverage(students[i].grades, NUM_UNITS);
    }

    // Display the average, highest, and lowest grades
    for (int i = 0; i < NUM_STUDENTS; i++) {
        printf("\nStudent: %s, Reg Number: %s\n", students[i].name, students[i].regNumber);
        printf("Average Grade: %.2f\n", students[i].averageGrade);
    }
    
    printf("\nHighest Grade: %.2f\n", highestGrade);
    printf("Lowest Grade: %.2f\n", lowestGrade);

    // Search for a specific student grade by entering registration number
    char searchRegNumber[15];
    printf("\nEnter a student registration number to search for: ");
    scanf("%s", searchRegNumber);

    for (int i = 0; i < NUM_STUDENTS; i++) {
        if (strcmp(searchRegNumber, students[i].regNumber) == 0) {
            printf("Found student: %s, Reg Number: %s\n", students[i].name, students[i].regNumber);
            printf("Average Grade: %.2f\n", students[i].averageGrade);
            break;
        }
    }

    return 0;
}
