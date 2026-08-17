// 1. Sum of Array
#include <stdio.h>

int main() {
    int arr[] = {10, 20, 30, 40}, n = 4, sum = 0;
    for (int i = 0; i < n; i++) sum += arr[i];
    printf("Sum = %d\n", sum);
    return 0;
}


// 2. Reverse an Array
#include <stdio.h>

int main() {
    int arr[] = {1, 2, 3, 4, 5}, n = 5;
    for (int i = 0; i < n / 2; i++) {
        int temp = arr[i];
        arr[i] = arr[n - 1 - i];
        arr[n - 1 - i] = temp;
    }
    printf("Reversed: ");
    for (int i = 0; i < n; i++) printf("%d ", arr[i]);
    return 0;
}


// 3. Maximum Element in Array
#include <stdio.h>

int main() {
    int arr[] = {12, 45, 2, 67, 23}, n = 5, max = arr[0];
    for (int i = 1; i < n; i++) if (arr[i] > max) max = arr[i];
    printf("Max = %d\n", max);
    return 0;
}


// 4. Minimum Element in Array
#include <stdio.h>

int main() {
    int arr[] = {12, 45, 2, 67, 23}, n = 5, min = arr[0];
    for (int i = 1; i < n; i++) if (arr[i] < min) min = arr[i];
    printf("Min = %d\n", min);
    return 0;
}


// 5. Count Odd & Even Numbers in Array
#include <stdio.h>

int main() {
    int arr[] = {1, 2, 3, 4, 5, 6}, n = 6, even = 0, odd = 0;
    for (int i = 0; i < n; i++) {
        if (arr[i] % 2 == 0) even++;
        else odd++;
    }
    printf("Even: %d, Odd: %d\n", even, odd);
    return 0;
}


// 6. Union of Two Arrays
#include <stdio.h>

int main() {
    int a[] = {1, 2, 3}, b[] = {2, 3, 4}, n1 = 3, n2 = 3;
    printf("Union: ");
    for (int i = 0; i < n1; i++) printf("%d ", a[i]);
    for (int i = 0; i < n2; i++) {
        int found = 0;
        for (int j = 0; j < n1; j++) {
            if (b[i] == a[j]) { found = 1; break; }
        }
        if (!found) printf("%d ", b[i]);
    }
    return 0;
}


// 7. Frequency of Elements in Array
#include <stdio.h>

int main() {
    int arr[] = {2, 3, 2, 5, 3}, n = 5;
    for (int i = 0; i < n; i++) {
        int seen = 0;
        for (int k = 0; k < i; k++) if (arr[i] == arr[k]) seen = 1;
        if (!seen) {
            int count = 0;
            for (int j = 0; j < n; j++) if (arr[i] == arr[j]) count++;
            printf("%d occurs %d times\n", arr[i], count);
        }
    }
    return 0;
}


// 8. Second Smallest Element in Array
#include <stdio.h>

int main() {
    int arr[] = {12, 5, 8, 2, 9}, n = 5;
    int small = arr[0], secSmall = 1e9;
    for (int i = 0; i < n; i++) {
        if (arr[i] < small) { secSmall = small; small = arr[i]; }
        else if (arr[i] < secSmall && arr[i] != small) secSmall = arr[i];
    }
    printf("Second Smallest = %d\n", secSmall);
    return 0;
}


// 9. Peak Element in Array
#include <stdio.h>

int main() {
    int arr[] = {1, 3, 20, 4, 1}, n = 5;
    for (int i = 0; i < n; i++) {
        if ((i == 0 || arr[i] >= arr[i - 1]) && (i == n - 1 || arr[i] >= arr[i + 1])) {
            printf("Peak Element = %d\n", arr[i]);
            break;
        }
    }
    return 0;
}


// 10. Matrix Addition
#include <stdio.h>

int main() {
    int A[2][2] = {{1, 2}, {3, 4}}, B[2][2] = {{5, 6}, {7, 8}}, sum[2][2];
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            sum[i][j] = A[i][j] + B[i][j];
            printf("%d ", sum[i][j]);
        }
        printf("\n");
    }
    return 0;
}


// 11. Matrix Subtraction
#include <stdio.h>

int main() {
    int A[2][2] = {{5, 6}, {7, 8}}, B[2][2] = {{1, 2}, {3, 4}}, diff[2][2];
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            diff[i][j] = A[i][j] - B[i][j];
            printf("%d ", diff[i][j]);
        }
        printf("\n");
    }
    return 0;
}


// 12. Maximum Element in Matrix
#include <stdio.h>

int main() {
    int mat[2][3] = {{12, 45, 23}, {67, 89, 34}}, max = mat[0][0];
    for (int i = 0; i < 2; i++)
        for (int j = 0; j < 3; j++)
            if (mat[i][j] > max) max = mat[i][j];
    printf("Max = %d\n", max);
    return 0;
}


// 13.1 String Operations: Length
#include <stdio.h>

int main() {
    char s[] = "Hello";
    int len = 0;
    while (s[len] != '\0') len++;
    printf("Length = %d\n", len);
    return 0;
}


// 13.2 String Operations: Copy
#include <stdio.h>

int main() {
    char src[] = "Hello", dest[20];
    int i = 0;
    while ((dest[i] = src[i]) != '\0') i++;
    printf("Copied: %s\n", dest);
    return 0;
}


// 13.3 String Operations: Concatenation
#include <stdio.h>

int main() {
    char s1[20] = "Hello ", s2[] = "World";
    int i = 0, j = 0;
    while (s1[i] != '\0') i++;
    while ((s1[i++] = s2[j++]) != '\0');
    printf("%s\n", s1);
    return 0;
}


// 13.4 String Operations: Counting Words
#include <stdio.h>

int main() {
    char s[] = "Hello World from C";
    int words = 1;
    for (int i = 0; s[i] != '\0'; i++)
        if (s[i] == ' ' && s[i + 1] != ' ') words++;
    printf("Words = %d\n", words);
    return 0;
}


// 13.5 String Operations: Counting Vowels and Consonants
#include <stdio.h>

int main() {
    char s[] = "Hello World", v[] = "AEIOUaeiou";
    int vowels = 0, consonants = 0;
    for (int i = 0; s[i] != '\0'; i++) {
        char c = s[i];
        if ((c >= 'a' && c <= 'z') || (c >= 'A' && c <= 'Z')) {
            int isVowel = 0;
            for (int j = 0; v[j] != '\0'; j++) {
                if (c == v[j]) { isVowel = 1; break; }
            }
            if (isVowel) vowels++;
            else consonants++;
        }
    }
    printf("Vowels: %d, Consonants: %d\n", vowels, consonants);
    return 0;
}


// 14. String Palindrome
#include <stdio.h>

int main() {
    char s[] = "madam";
    int len = 0, isPalindrome = 1;
    while (s[len] != '\0') len++;
    for (int i = 0; i < len / 2; i++) {
        if (s[i] != s[len - 1 - i]) {
            isPalindrome = 0;
            break;
        }
    }
    if (isPalindrome) printf("Palindrome\n");
    else printf("Not Palindrome\n");
    return 0;
}


// 15. Structures Program (Car Details)
#include <stdio.h>

struct Car {
    char brand[20];
    char model[20];
    int year;
    float price;
};

int main() {
    struct Car myCar = {"Toyota", "Corolla", 2022, 21500.50};
    printf("Brand: %s\n", myCar.brand);
    printf("Model: %s\n", myCar.model);
    printf("Year: %d\n", myCar.year);
    printf("Price: $%.2f\n", myCar.price);
    return 0;
}

/* Palindrome Number Checker */
#include <stdio.h>

int main() {
    int num, originalNum, reversedNum = 0, remainder;

    printf("Enter an integer: ");
    scanf("%d", &num);

    originalNum = num;

    while (num > 0) {
        remainder = num % 10;
        reversedNum = reversedNum * 10 + remainder;
        num /= 10;
    }

    if (originalNum == reversedNum)
        printf("%d is a palindrome.\n", originalNum);
    else
        printf("%d is not a palindrome.\n", originalNum);

    return 0;
}


/* Half Pyramid Pattern */
#include <stdio.h>

int main() {
    int rows = 5;

    for (int i = 1; i <= rows; i++) {
        for (int j = 1; j <= i; j++) {
            printf("* ");
        }
        printf("\n");
    }

    return 0;
}


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
