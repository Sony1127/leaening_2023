#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct Student {
    int rollno;
    char name[20];
    float marks;
};

struct Student *addStudent(struct Student *students, int *numStudents) {
    (*numStudents)++; // Increment the number of students

    struct Student *temp = realloc(students, (*numStudents) * sizeof(struct Student));
    if (temp == NULL) {
        printf("Memory reallocation failed.\n");
        return students; // Return original pointer without modification
    }

    students = temp;

    printf("Enter the details of the student:\n");
    printf("Roll No: ");
    scanf("%d", &students[*numStudents - 1].rollno);
    getchar(); // Clear the newline character from the input buffer

    printf("Name: ");
    fgets(students[*numStudents - 1].name, sizeof(students[*numStudents - 1].name), stdin);
    students[*numStudents - 1].name[strcspn(students[*numStudents - 1].name, "\n")] = '\0';

    printf("Marks: ");
    scanf("%f", &students[*numStudents - 1].marks);
    getchar(); // Clear the newline character from the input buffer

    return students;
}

void displayStudents(const struct Student *students, int numStudents) {
    printf("\nStudent details:\n");
    for (int i = 0; i < numStudents; i++) {
        printf("Roll No: %d, Name: %s, Marks: %.2f\n",
               students[i].rollno, students[i].name, students[i].marks);
    }
}

int main() {
    int numStudents = 0;
    struct Student *students = NULL;

    students = addStudent(students, &numStudents);
    displayStudents(students, numStudents);

    free(students);
    return 0;
}