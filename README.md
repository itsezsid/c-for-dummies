# C for dummies ;)

### Table of Contents
1. [Basic Syntax](#basic-syntax)
2. [Sorting Algorithms](#sorting-algorithms)
3. [Memory Management](#memory-management)
4. [File Operations](#file-operations)
5. [String Manipulations](#string-manipulations)
6. [Pointers and Arrays](#pointers-and-arrays)
7. [Debugging and Error Handling](#debugging-and-error-handling)
8. [Best Practices](#best-practices)
9. [Code Styling](#code-styling)
10. [Compiling and Building](#compiling-and-building)
11. [Concurrency](#concurrency)
12. [Additional Notes](#additional-notes)
13. [Structures and Unions](#structures-and-unions)
14. [Preprocessor Directives](#preprocessor-directives)
15. [Pointers to Functions](#pointers-to-functions)
16. [Command Line Arguments](#command-line-arguments)
17. [Type Casting](#type-casting)
18. [Error Handling](#error-handling)
19. [Common Libraries](#common-libraries)

### [Basic Syntax](#basic-syntax)
- **Variables and Types**
  ```c
  int age = 30; // Integer
  float price = 19.99; // Floating point number
  char grade = 'A'; // Character
  ```

- **Conditional Statements**
  ```c
  if (condition) { /* code if condition is true */ } 
  else if (another_condition) { /* code if another_condition is true */ } 
  else { /* code if all conditions are false */ }
  ```

- **Loops**
  ```c
  for (int i = 0; i < 10; i++) { /* code executed 10 times */ }
  while (condition) { /* code executed while condition is true */ }
  do { /* code */ } while (condition); // code executed at least once and then while condition is true
  ```

- **Functions**
  ```c
  returnType functionName(parameters) { /* function body */ }
  ```

### [Sorting Algorithms](#sorting-algorithms)
- **Bubble Sort**
  ```c
  void swap(int* a, int* b) {
    int temp = *a;
    *a = *b;
    *b = temp;
  }

  void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n-1; i++)    
      for (int j = 0; j < n-i-1; j++)
        if (arr[j] > arr[j+1])
          swap(&arr[j], &arr[j+1]);
  }
  ```

- **Insertion Sort**
  ```c
  void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; i++) {
      int key = arr[i], j = i - 1;
      while (j >= 0 && arr[j] > key) {
        arr[j + 1] = arr[j];
        j = j - 1;
      }
      arr[j + 1] = key;
    }
  }
  ```

### [Memory Management](#memory-management)
- **Dynamic Allocation**
  ```c
  int* ptr = malloc(sizeof(int) * n); // Allocate memory
  if (ptr == NULL) { /* handle allocation failure */ }
  free(ptr); // Free memory
  ptr = NULL; // Good practice after freeing memory
  ```

- **Memory Copy**
  ```c
  memcpy(dest, src, n); // Copies n bytes from src to dest
  ```

### [File Operations](#file-operations)
- **Reading and Writing Files**
  ```c
  FILE *fp = fopen("file.txt", "r"); // Open for reading
  if (fp == NULL) { /* handle file open error */ }
  char buffer[100];
  fgets(buffer, 100, fp); // Read from file
  fclose(fp); // Close file

  fp = fopen("file.txt", "w"); // Open for writing
  if (fp == NULL) { /* handle file open error */ }
  fprintf(fp, "Hello, world!\n"); // Write to file
  fclose(fp); // Close file
  ```

### [String Manipulations](#string-manipulations)
- **Common Functions**
  ```c
  size_t len = strlen(s); // Get string length
  strcpy(dst, src); // Copy string
  strcat(s1, s2); // Concatenate strings
  int cmp = strcmp(s1, s2); // Compare strings
  ```

### [Pointers and Arrays](#pointers-and-arrays)
- **Usage**
  ```c
  int arr[10]; // Declare an array
  int *p = &arr[0]; // Pointer to the array
  p[2] = 5; // Set 3rd element of the array to 5
  ```

### [Debugging and Error Handling](#debugging-and-error-handling)
- **Check Return Values**
  ```c
  if (fopen("file.txt", "r") == NULL) { /* handle file open error */ }
  ```

- **Asserts**
  ```c
  #include <assert.h>
  assert(ptr != NULL); // Assert that ptr is not NULL
  ```

### [Best Practices](#best-practices)
- **Avoid Memory Leaks:** Always `free` allocated memory and set the pointer to NULL.
- **Buffer Overflows:** Prefer `strncpy` over `strcpy` to avoid buffer overflow.
- **Use `const` Keyword:** For non-modifiable parameters and variables.
- **Modular Programming:** Use functions and split code across multiple files for better organization.
- **Comments:** Document the "why", not the "what". Use comments to explain complex code sections.

### [Code Styling](#code-styling)
- Be consistent with naming conventions (snake_case, camelCase).
- Use consistent indentation (e.g., 4 spaces) and spacing.
- Choose a consistent style for curly braces.

### [Compiling and Building](#compiling-and-building)
- **Compiler Warnings:** Use `-Wall` to enable all compiler warnings.
- **Makefiles:** Use for managing larger projects.

### [Concurrency](#concurrency)
- **Thread Safety:** Use mutexes for protecting shared resources.
- **Atomic Operations:** Use for certain operations on shared variables to prevent race conditions.

### [Additional Notes](#additional-notes)
- **Error Handling:** Always validate the return values from library functions for potential errors.
- **Dynamic Memory:** Check for `NULL` from `malloc` indicating allocation failure.
- **File Operations:** Ensure `fclose` is called after finishing operations on a file to avoid resource leaks.

### [Structures and Unions](#structures-and-unions)
- **Usage**
  ```c
  struct Person {
    char name[50];
    int age;
    float salary;
  };
  ```

### [Preprocessor Directives](#preprocessor-directives)
- **Usage**
  ```c
  #define PI 3.14
  #include <stdio.h>
  ```

### [Pointers to Functions](#pointers-to-functions)
- **Usage**
  ```c
  void (*fun_ptr)(int) = &fun;
  ```

### [Command Line Arguments](#command-line-arguments)
- **Usage**
  ```c
  int main(int argc, char *argv[]) { /* code */ }
  ```

### [Type Casting](#type-casting)
- **Usage**
  ```c
  int x = 10;
  double y = (double)x;
  ```

### [Error Handling](#error-handling)
- **Usage**
  ```c
  if ((fp = fopen("file.txt", "r")) == NULL) {
    perror("Error opening file");
    return(-1);
  }
  ```

### [Common Libraries](#common-libraries)
- **Usage**
  ```c
  #include <stdio.h> // Standard input/output functions
  #include <stdlib.h> // General purpose functions
  #include <string.h> // String handling functions
  #include <math.h> // Mathematical functions
  ```
