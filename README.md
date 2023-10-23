#include <stdio.h>
void input(int arr[], int size);
void searching(int arr[], int size);
void output(int arr[], int size);
void reverse(int arr[], int size);
void ascending(int arr[], int size);
void descending(int arr[], int size);

int main()
{
    int size;
    printf("Enter array Size:\n");
    scanf("%d", &size);
    int arr[size];
    while (1)
    {
        printf("Enter 1: Input an array.\n");
        printf("Enter 2: Output an array.\n");
        printf("Enter 3: The Reverse output of the Array.\n");
        printf("Enter 4: Seaching an Element.\n");
        printf("Enter 5: Ascending Order.\n");
        printf("Enter 6: Descending Order.\n");
        printf("Enter 0: to end\n");
        int enter;
        scanf("%d", &enter);
        switch (enter)
        {
        case 1:
            input(arr, size);
            break;
        case 2:
            output(arr, size);
            break;
        case 3:
            reverse(arr, size);
            break;
        case 4:
            searching(arr, size);
            break;
        case 5:
            ascending(arr, size);
            output(arr, size);
            break;
        case 6:
            descending(arr, size);
            output(arr, size);
            break;
        case 0:
            return 0;
        default:
            printf("Error");
            break;
        }
    }

    return 0;
}

// input an array
void input(int arr[], int size)
{
    printf("Enter an Array:\n");
    for (int i = 0; i < size; i++)
    {
        scanf("%d", &arr[i]);
    }
}
// ouput an array
void output(int arr[], int size)
{

    for (int i = 0; i < size; i++)
    {
        printf("%d ", arr[i]);
    }
    printf("\n");
}

// reverse an array
void reverse(int arr[], int size)
{   
   
    for (int i = size - 1; i >= 0; i--)
    {
        printf("%d ", arr[i]);
    }
}
// asecending order
void ascending(int arr[], int size)
{
    for (int i = 0; i < size; i++)
    {
        for (int j = i + 1; j < size; j++)
        {
            if (arr[i] > arr[j])
            {
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
    }
}
// desecending order
void descending(int arr[], int size)
{
    for (int i = 0; i < size; i++)
    {
        for (int j = i + 1; j < size; j++)
        {
            if (arr[i] < arr[j])
            {
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
    }
}
// searching an array
void searching(int arr[], int size)
{
    int element, i, found = 0;
     printf("Enter Element You Want to Search: \n");
    scanf("%d", &element);
    for (i = 0; i < size; i++)
    {
        if (arr[i] == element)
        {
            found = 1;
            break;
        }
    }
    if (found == 1)
    {
        printf("%d found at %d position.\n", element, i + 1);
    }
    else
    {
        printf("Not Found.\n");
    }
}
