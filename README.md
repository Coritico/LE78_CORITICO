#include <stdio.h>
#include <ctype.h>
#include <string.h>

int main(void) {
    int n, arr[10], i, largest;

    printf("How many numbers (1-10)? ");
    if (scanf("%d", &n) != 1 || n < 1) return 0;
    if (n > 10) n = 10;

    printf("Enter %d integers:\n", n);
    for (i = 0; i < n; ++i) scanf("%d", &arr[i]);

    largest = arr[0];
    for (i = 1; i < n; ++i)
        if (arr[i] > largest) largest = arr[i];

    printf("Largest: %d\n", largest);

    /* consume leftover newline */
    int ch = getchar();
    while (ch != '\n' && ch != EOF) ch = getchar();

    char s[200];
    printf("Enter a string: ");
    if (!fgets(s, sizeof s, stdin)) return 0;
    /* remove newline */
    s[strcspn(s, "\n")] = '\0';

    int vowels = 0;
    for (i = 0; s[i]; ++i) {
        char c = tolower((unsigned char)s[i]);
        if (c=='a' || c=='e' || c=='i' || c=='o' || c=='u') ++vowels;
    }

    printf("Vowels: %d\n", vowels);
    return 0;
}
