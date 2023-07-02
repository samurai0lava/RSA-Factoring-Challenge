#include <stdio.h>
#include <stdlib.h>
#include <math.h>

/**
 * factorize - Factorizes a given number into a product of two smaller numbers.
 *
 * @num: The number to factorize.
 */
void factorize(int num)
{
    int i;

    for (i = 2; i <= sqrt(num); i++)
    {
        while (num % i == 0)
        {
            printf("%d=%d*%d\n", num, i, num / i);
            num /= i;
        }
    }

    if (num > 1)
    {
        printf("%d=%d*%d\n", num, num, 1);
    }
}

/**
 * main - Entry point of the program.
 *
 * @argc: The number of command-line arguments.
 * @argv: An array of command-line argument strings.
 *
 * Return: 0 on success, 1 on failure.
 */
int main(int argc, char *argv[])
{
    if (argc != 2)
    {
        printf("Usage: factors <file>\n");
        return 1;
    }

    char *file_path = argv[1];
    FILE *file = fopen(file_path, "r");
    if (file == NULL)
    {
        printf("Error opening file: %s\n", file_path);
        return 1;
    }

    char line[100];
    while (fgets(line, sizeof(line), file))
    {
        int num = atoi(line);
        factorize(num);
    }

    fclose(file);
    return 0;
}

