#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_ENTRIES 100
#define MAX_LINE_LENGTH 100

typedef struct {
    int entryNo;
    char sensorNo[10];
    float temperature;
    int humidity;
    int light;
    char timestamp[10];
} LogEntry;

void extractLines(FILE *file, LogEntry logEntries[], int *numEntries) {
    char line[MAX_LINE_LENGTH];

    *numEntries = 0;

    while (fgets(line, MAX_LINE_LENGTH, file) != NULL) {
        char *token;
        token = strtok(line, ",");

        logEntries[*numEntries].entryNo = atoi(token);

        token = strtok(NULL, ",");
        strcpy(logEntries[*numEntries].sensorNo, token);

        token = strtok(NULL, ",");
        logEntries[*numEntries].temperature = atof(token);

        token = strtok(NULL, ",");
        logEntries[*numEntries].humidity = atoi(token);

        token = strtok(NULL, ",");
        logEntries[*numEntries].light = atoi(token);

        token = strtok(NULL, ",");
        strcpy(logEntries[*numEntries].timestamp, token);

        (*numEntries)++;
    }
}

void displayLogEntries(LogEntry logEntries[], int numEntries) {
    printf("Log Entries:\n");
    for (int i = 0; i < numEntries; i++) {
        printf("Entry No: %d\n", logEntries[i].entryNo);
        printf("Sensor No: %s\n", logEntries[i].sensorNo);
        printf("Temperature: %.2f\n", logEntries[i].temperature);
        printf("Humidity: %d\n", logEntries[i].humidity);
        printf("Light: %d\n", logEntries[i].light);
        printf("Timestamp: %s\n", logEntries[i].timestamp);
        printf("\n");
    }
}

int main() {
    FILE *file = fopen("data.csv", "r");
    if (file == NULL) {
        printf("Error opening file.\n");
        return 1;
    }

    LogEntry logEntries[MAX_ENTRIES];
    int numEntries = 0;

    extractLines(file, logEntries, &numEntries);

    displayLogEntries(logEntries, numEntries);

    fclose(file);

    return 0;
}