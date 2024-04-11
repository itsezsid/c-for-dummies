# C for dummies ;)

## Table of Contents
1. [Basic Syntax](#basic-syntax)
2. [Structures and Unions](#structures-and-unions)
3. [Preprocessor Directives](#preprocessor-directives)
4. [Pointers to Functions](#pointers-to-functions)
5. [Command Line Arguments](#command-line-arguments)
6. [Type Casting](#type-casting)
7. [Error Handling](#error-handling)
8. [Common Libraries](#common-libraries)
9. [Sorting Algorithms](#sorting-algorithms)
10. [Memory Management](#memory-management)
11. [File Operations](#file-operations)
12. [String Manipulations](#string-manipulations)
13. [Pointers and Arrays](#pointers-and-arrays)
14. [Debugging and Error Handling](#debugging-and-error-handling)
15. [Best Practices](#best-practices)
16. [Code Styling](#code-styling)
17. [Compiling and Building](#compiling-and-building)
18. [Concurrency](#concurrency)
19. [Additional Notes](#additional-notes)

## 1. Basic Syntax <a name="basic-syntax"></a>
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

## 2. Structures and Unions <a name="structures-and-unions"></a>
- **Usage**
  ```c
  struct Person {
    char name[50];
    int age;
    float salary;
  };
  ```

## 3. Preprocessor Directives <a name="preprocessor-directives"></a>
- **Usage**
  ```c
  #define PI 3.14
  #include <stdio.h>
  ```

## 4. Pointers to Functions <a name="pointers-to-functions"></a>
- **Usage**
  ```c
  void (*fun_ptr)(int) = &fun;
  ```

## 5. Command Line Arguments <a name="command-line-arguments"></a>
- **Usage**
  ```c
  int main(int argc, char *argv[]) { /* code */ }
  ```

## 6. Type Casting <a name="type-casting"></a>
- **Usage**
  ```c
  int x = 10;
  double y = (double)x;
  ```

## 7. Error Handling <a name="error-handling"></a>
- **Usage**
  ```c
  if ((fp = fopen("file.txt", "r")) == NULL) {
    perror("Error opening file");
    return(-1);
  }
  ```

## 8. Common Libraries <a name="common-libraries"></a>
- **Usage**
  ```c
  #include <stdio.h> // Standard input/output functions
  #include <stdlib.h> // General purpose functions
  #include <string.h> // String handling functions
  #include <math.h> // Mathematical functions
  ```

## 9. Sorting Algorithms <a name="sorting-algorithms"></a>
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

## 10. Memory Management <a name="memory-management"></a>
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

## 11. File Operations <a name="file-operations"></a>
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

## 12. String Manipulations <a name="string-manipulations"></a>
- **Common Functions**
  ```c
  size_t len = strlen(s); // Get string length
  strcpy(dst, src); // Copy string
  strcat(s1, s2); // Concatenate strings
  int cmp = strcmp(s1, s2); // Compare strings
  ```

## 13. Pointers and Arrays <a name="pointers-and-arrays"></a>
- **Usage**
  ```c
  int arr[10]; // Declare an array
  int *p = &arr[0]; // Pointer to the array
  p[2] = 5; // Set 3rd element of the array to 5
  ```

## 14. Debugging and Error Handling <a name="debugging-and-error-handling"></a>
- **Check Return Values**
  ```c
  if (fopen("file.txt", "r") == NULL) { /* handle file open error */ }
  ```

- **Asserts**
  ```c
  #include <assert.h>
  assert(ptr != NULL); // Assert that ptr is not NULL
  ```

## 15. Best Practices <a name="best-practices"></a>
- **Avoid Memory Leaks:** Always `free` allocated memory and set the pointer to NULL.
- **Buffer Overflows:** Prefer `strncpy` over `strcpy` to avoid buffer overflow.
- **Use `const` Keyword:** For non-modifiable parameters and variables.
- **Modular Programming:** Use functions and split code across multiple files for better organization.
- **Comments:** Document the "why", not the "what". Use comments to explain complex code sections.

## 16. Code Styling <a name="code-styling"></a>
- Be consistent with naming conventions (snake_case, camelCase).
- Use consistent indentation (e.g., 4 spaces) and spacing.
- Choose a consistent style for curly braces.

## 17. Compiling and Building <a name="compiling-and-building"></a>
- **Compiler Warnings:** Use `-Wall` to enable all compiler warnings.
- **Makefiles:** Use for managing larger projects.

## 18. Concurrency <a name="concurrency"></a>
- **Thread Safety:** Use mutexes for protecting shared resources.
- **Atomic Operations:** Use for certain operations on shared variables to prevent race conditions.

## 19. Additional Notes <a name="additional-notes"></a>
- **Error Handling:** Always validate the return values from library functions for potential errors.
- **Dynamic Memory:** Check for `NULL` from `malloc` indicating allocation failure.
- **File Operations:** Ensure `fclose` is called after finishing operations on a file to avoid resource leaks.
