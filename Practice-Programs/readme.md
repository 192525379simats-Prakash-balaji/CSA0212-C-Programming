/* Scalar Matrix Multiplication */
#include <stdio.h>

int main() {
    int a[2][2] = {{1, 2}, {3, 4}};
    int k = 3;

    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            a[i][j] = a[i][j] * k;
            printf("%d ", a[i][j]);
        }
        printf("\n");
    }

    return 0;
}


/* Determinant of a 2x2 Matrix */
#include <stdio.h>

int main() {
    int a[2][2] = {
        {4, 3},
        {2, 5}
    };

    int det = (a[0][0] * a[1][1]) - (a[0][1] * a[1][0]);

    printf("Determinant: %d\n", det);

    return 0;
}


/* Inverse of a 2x2 Matrix */
#include <stdio.h>

int main() {
    float a = 4, b = 7;
    float c = 2, d = 6;

    float det = (a * d) - (b * c);

    if (det == 0) {
        printf("No inverse!\n");
    } else {
        printf("%.2f  %.2f\n",  d / det, -b / det);
        printf("%.2f  %.2f\n", -c / det,  a / det);
    }

    return 0;
}


/* Rank of a 2x2 Matrix */
#include <stdio.h>

int main() {
    int a = 1, b = 2;
    int c = 2, d = 4;

    int det = (a * d) - (b * c);

    if (a == 0 && b == 0 && c == 0 && d == 0) {
        printf("Rank: 0\n");
    } else if (det != 0) {
        printf("Rank: 2\n");
    } else {
        printf("Rank: 1\n");
    }

    return 0;
}


/* Gauss-Jordan Elimination (2x2 System) */
#include <stdio.h>

int main() {
    float a[2][3] = {
        {2, 1, 5},
        {1, 3, 5}
    };

    float pivot1 = a[0][0];
    a[0][0] = a[0][0] / pivot1;
    a[0][1] = a[0][1] / pivot1;
    a[0][2] = a[0][2] / pivot1;

    float factor1 = a[1][0];
    a[1][0] = a[1][0] - (factor1 * a[0][0]);
    a[1][1] = a[1][1] - (factor1 * a[0][1]);
    a[1][2] = a[1][2] - (factor1 * a[0][2]);

    float pivot2 = a[1][1];
    a[1][0] = a[1][0] / pivot2;
    a[1][1] = a[1][1] / pivot2;
    a[1][2] = a[1][2] / pivot2;

    float factor2 = a[0][1];
    a[0][0] = a[0][0] - (factor2 * a[1][0]);
    a[0][1] = a[0][1] - (factor2 * a[1][1]);
    a[0][2] = a[0][2] - (factor2 * a[1][2]);

    printf("x = %.2f\n", a[0][2]);
    printf("y = %.2f\n", a[1][2]);

    return 0;
}


/* Sum and Average of Numbers (Hardcoded) */
#include <stdio.h>

int main() {
    float numbers[] = {10, 20, 30, 40, 50};
    int n = 5;

    float sum = 0;

    for (int i = 0; i < n; i++) {
        sum += numbers[i];
    }

    float average = sum / n;

    printf("Sum = %.2f\n", sum);
    printf("Average = %.2f\n", average);

    return 0;
}


/* Multiplication Table (Hardcoded) */
#include <stdio.h>

int main() {
    int num = 5;

    for (int i = 1; i <= 10; i++) {
        printf("%d x %d = %d\n", num, i, num * i);
    }

    return 0;
}


/* Diamond Pattern using Two Pyramids */
#include <stdio.h>

int main() {
    int n = 3;

    for (int i = 1; i <= n; i++) {
        for (int s = 1; s <= n - i; s++) printf(" ");
        for (int k = 1; k <= 2 * i - 1; k++) printf("*");
        printf("\n");
    }

    for (int i = n - 1; i >= 1; i--) {
        for (int s = 1; s <= n - i; s++) printf(" ");
        for (int k = 1; k <= 2 * i - 1; k++) printf("*");
        printf("\n");
    }

    return 0;
}
