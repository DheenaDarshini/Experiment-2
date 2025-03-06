# Experiment-2
# Name: Dheena Darshini Karthik Dheepan
# Reg no: 212223240030
Write a program in C language for Matrix multiplication fails. Introspect the causes for its failure and write down the possible reasons for its failure.
## Aim
The aim of this program is to perform matrix multiplication, understand the causes for failure during its execution, and identify possible reasons for failure. Matrix multiplication is a binary operation that produces a matrix from two matrices. The number of columns in the first matrix must be equal to the number of rows in the second matrix for multiplication to be possible.

## Algorithm
1.	Input the dimensions of the matrices: First, input the number of rows and columns for both matrices.
2.	Check for multiplication compatibility: Ensure the number of columns of the first matrix is equal to the number of rows of the second matrix.
3.	Input matrix elements: Input the elements for both matrices.
4.	Perform matrix multiplication: For each element in the resultant matrix, sum the products of the corresponding row and column elements from the two matrices.
5.	Output the resulting matrix: Display the resultant matrix.

## Causes for Failure

## Program
~~~
#include <stdio.h>
#include <stdlib.h>

// Function to multiply two matrices
void multiplyMatrices(int A[][10], int B[][10], int C[][10], int rowA, int colA, int rowB, int colB) {
    // Check if multiplication is possible
    if (colA != rowB) {
        printf("Matrix multiplication is not possible. Number of columns in Matrix A must equal number of rows in Matrix B.\n");
        return;
    }

    // Perform multiplication
    for (int i = 0; i < rowA; i++) {
        for (int j = 0; j < colB; j++) {
            C[i][j] = 0;  // Initialize the result matrix element to zero
            for (int k = 0; k < colA; k++) {
                C[i][j] += A[i][k] * B[k][j];
            }
        }
    }
}

// Function to input matrix elements
void inputMatrix(int matrix[][10], int rows, int cols) {
    printf("Enter elements of the matrix:\n");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            printf("Element [%d][%d]: ", i + 1, j + 1);
            scanf("%d", &matrix[i][j]);
        }
    }
}

// Function to print matrix
void printMatrix(int matrix[][10], int rows, int cols) {
    printf("Resultant Matrix:\n");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }
}

int main() {
    int A[10][10], B[10][10], C[10][10]; // Declare matrices
    int rowA, colA, rowB, colB;

    // Input dimensions of Matrix A
    printf("Enter the number of rows and columns for Matrix A: ");
    scanf("%d %d", &rowA, &colA);

    // Input dimensions of Matrix B
    printf("Enter the number of rows and columns for Matrix B: ");
    scanf("%d %d", &rowB, &colB);

    // Check for multiplication compatibility
    if (colA != rowB) {
        printf("Matrix multiplication is not possible. The number of columns in A must be equal to the number of rows in B.\n");
        return 0; // Exit the program if matrices are incompatible
    }

    // Input elements for Matrix A
    inputMatrix(A, rowA, colA);

    // Input elements for Matrix B
    inputMatrix(B, rowB, colB);

    // Perform matrix multiplication
    multiplyMatrices(A, B, C, rowA, colA, rowB, colB);

    // Print the resulting matrix
    printMatrix(C, rowA, colB);

}
~~~

## Output

## Result
