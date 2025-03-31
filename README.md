# Time Table Displayer

## Overview
This is a **C program** that allows students to view their respective batch-wise time tables. The program prompts the student for their name and batch number, then displays the corresponding schedule.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [How to Use](#how-to-use)
- [Code Explanation](#code-explanation)
  - [Structure Definition](#structure-definition)
  - [Batch Time Table Functions](#batch-time-table-functions)
  - [Main Function](#main-function)
- [Example Output](#example-output)
- [Potential Enhancements](#potential-enhancements)
- [Contributing](#contributing)
- [License](#license)

---

## Features
- Takes **student name** and **batch number** as input.
- Displays the corresponding **batch-specific timetable**.
- Uses **struct** to store student details.
- Implements **switch-case** for batch selection.
- Provides a clean and formatted display.

---

## Installation
1. Ensure you have a C compiler (like `gcc`) installed.
2. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/timetable-displayer.git
   ```
3. Navigate to the directory:
   ```bash
   cd timetable-displayer
   ```
4. Compile the program:
   ```bash
   gcc timetable.c -o timetable
   ```
5. Run the executable:
   ```bash
   ./timetable
   ```

---

## How to Use
1. Run the program.
2. Enter the student's **name**.
3. Choose the **batch number** (1 or 2).
4. The corresponding timetable will be displayed.
5. If an invalid batch number is entered, an error message is shown.

---

## Code Explanation
### Structure Definition
```c
struct st {
    char name[20];
    int batch;
};
```
- Defines a structure `st` with:
  - `name` (character array to store student name)
  - `batch` (integer to store batch number)

### Batch Time Table Functions
#### `b1()` - Displays **Batch 1** time table
```c
void b1() {
    printf("---------------Your Batch 1 Time Table---------------\n");
    printf("Day Order 8:00 - 9:40 9:45 - 11:30 11:35 - 12:30 12:30 - 3:10\n");
    printf("Day 1 MATH PPS LUNCH PPS LAB\n");
    printf("Day 2 CME LAB CME LAB LUNCH LANG\n");
    printf("Day 3 CHEM MATH LUNCH NSS/NSO\n");
    printf("Day 4 - - LUNCH CHEM LAB\n");
    printf("Day 5 CME PPS LUNCH LANG\n");
}
```

#### `b2()` - Displays **Batch 2** time table
```c
void b2() {
    printf("\n---------------Your Batch 2 Time Table---------------\n");
    printf("Day Order 8:00 - 9:40 9:45 - 11:30 11:35 - 12:30 12:30 - 3:10\n");
    printf("Day 1 CME PPS LUNCH LANG\n");
    printf("Day 2 CHEM LAB CHEM LAB LUNCH -\n");
    printf("Day 3 NSS/NSO MATH LUNCH CHEM\n");
    printf("Day 4 - LANG LUNCH CME LAB\n");
    printf("Day 5 PPS LAB PPS LAB LUNCH -\n");
}
```

### Main Function
```c
int main() {
    struct st s;
    printf("------------------Time Table Displayer------------------\n");
    printf("Enter the name of the Student : ");
    scanf("%s", s.name);
    printf("Batch :\nPress 1 - Batch 1\nPress 2 - Batch 2\nYour Batch no: ");
    scanf("%d", &s.batch);
    
    switch(s.batch) {
        case 1:
            b1();
            break;
        case 2:
            b2();
            break;
        default:
            printf("Invalid Choice\n");
            break;
    }
    printf("------------------Exiting the Program------------------");
    return 0;
}
```
- Takes student **name** and **batch number** as input.
- Calls the corresponding function based on batch selection.
- Displays an error message for invalid input.

---

## Example Output
```
------------------Time Table Displayer------------------
Enter the name of the Student : Alice
Batch :
Press 1 - Batch 1
Press 2 - Batch 2
Your Batch no: 1

---------------Your Batch 1 Time Table---------------
Day Order       8:00 - 9:40     9:45 - 11:30    11:35 - 12:30    12:30 - 3:10
Day 1          MATH            PPS            LUNCH            PPS LAB
Day 2          CME LAB         CME LAB        LUNCH            LANG
Day 3          CHEM            MATH           LUNCH            NSS/NSO
Day 4          -               -              LUNCH            CHEM LAB
Day 5          CME             PPS            LUNCH            LANG
------------------Exiting the Program------------------
```

---

## Potential Enhancements
- **Dynamic Time Table Loading**: Store timetables in an external file and load dynamically.
- **GUI Version**: Create a graphical interface for better user interaction.
- **More Batches**: Add support for additional batches.
- **Error Handling**: Improve input validation to prevent invalid entries.

---

## Contributing
Feel free to fork this repository and submit pull requests for improvements or additional features.

---

## License
This project is licensed under the MIT License. See the `LICENSE` file for more details.

---

## References
- [C Programming Documentation](https://devdocs.io/c/)

