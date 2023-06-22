#include <stdio.h>
#include <stdlib.h>
#include <ctype.h>

#define BUFFER_SIZE 4096

void copyFile(FILE *sourceFile, FILE *destinationFile) {
    char buffer[BUFFER_SIZE];
    size_t bytesRead;

    while ((bytesRead = fread(buffer, 1, BUFFER_SIZE, sourceFile)) > 0) {
        fwrite(buffer, 1, bytesRead, destinationFile);
    }
}

void changeToUpperCase(FILE *sourceFile, FILE *destinationFile) {
    int ch;

    while ((ch = fgetc(sourceFile)) != EOF) {
        fputc(toupper(ch), destinationFile);
    }
}

void changeToLowerCase(FILE *sourceFile, FILE *destinationFile) {
    int ch;

    while ((ch = fgetc(sourceFile)) != EOF) {
        fputc(tolower(ch), destinationFile);
    }
}

void changeToPureUpperCase(FILE *sourceFile, FILE *destinationFile) {
    int ch;

    while ((ch = fgetc(sourceFile)) != EOF) {
        if (isalpha(ch)) {
            fputc(toupper(ch), destinationFile);
        } else {
            fputc(ch, destinationFile);
        }
    }
}

int main(int argc, char *argv[]) {
    if (argc < 3) {
        printf("Insufficient arguments.\n");
        printf("Usage: %s <option> <source_file> <destination_file>\n", argv[0]);
        printf("Options:\n");
        printf("-u: Change file content to upper case\n");
        printf("-l: Change file content to lower case\n");
        printf("-s: Change file content to purely upper case\n");
        printf("No option: Perform a normal copy\n");
        return 1;
    }

    char *option = argv[1];
    char *sourceFileName = argv[2];
    char *destinationFileName = argv[3];

    FILE *sourceFile = fopen(sourceFileName, "r");
    if (sourceFile == NULL) {
        printf("Error opening source file.\n");
        return 1;
    }

    FILE *destinationFile = fopen(destinationFileName, "w");
    if (destinationFile == NULL) {
        printf("Error opening destination file.\n");
        fclose(sourceFile);
        return 1;
    }

    if (strcmp(option, "-u") == 0) {
        changeToUpperCase(sourceFile, destinationFile);
        printf("File content changed to upper case.\n");
    } else if (strcmp(option, "-l") == 0) {
        changeToLowerCase(sourceFile, destinationFile);
        printf("File content changed to lower case.\n");
    } else if (strcmp(option, "-s") == 0) {
        changeToPureUpperCase(sourceFile, destinationFile);
        printf("File content changed to purely upper case.\n");
    } else {
        copyFile(sourceFile, destinationFile);
        printf("Normal copy performed.\n");
    }

    fclose(sourceFile);
    fclose(destinationFile);

    return 0;
}