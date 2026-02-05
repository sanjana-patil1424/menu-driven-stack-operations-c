# menu-driven-stack-operations-c

##  Description
This project demonstrates implementation of stack operations using a menu driven program in C language. 
A simple menu-driven C program that demonstrates fundamental stack operations including push, pop, display, and palindrome checking.


##  Features
- Push element onto stack
- Pop element from stack
- Display stack status
- Palindrome checking using stack logic
- Overflow and underflow handling

##  Concepts Used
- Stack Data Structure (LIFO)
- Arrays
- Functions
- Conditional Statements
- Menu Driven Programming

##  Language
C Programming

## Features

- **Push**: Add an element to the top of the stack
- **Pop**: Remove the top element from the stack
- **Display**: View all elements currently in the stack
- **Palindrome**: Check if a given number is a palindrome
- **Exit**: Terminate the program

## Compilation

```bash
gcc -o stack stack.c
```

## Usage

```bash
./stack
```

## Menu Options

```
1. Push    - Add an element to the stack
2. Pop     - Remove the top element
3. Display - Show all stack elements
4. Palindrome - Check if a number is a palindrome
5. Exit    - Quit the program
```

## Code

```c
#include <stdio.h>
#include <stdlib.h>

#define MAX 100

int stack[MAX];
int top = -1;

void push(int x)
{
    if(top == MAX - 1)
        printf("Stack Overflow\n");
    else
        stack[++top] = x;
}

void pop()
{
    if(top == -1)
        printf("Stack Underflow\n");
    else
        printf("Popped element: %d\n", stack[top--]);
}

void display()
{
    int i;
    if(top == -1)
        printf("Stack is empty\n");
    else
    {
        printf("Stack elements:\n");
        for(i = top; i >= 0; i--)
            printf("%d ", stack[i]);
    }
}

void palindrome()
{
    int num, temp, rev = 0;

    printf("Enter number: ");
    scanf("%d", &num);

    temp = num;

    while(temp != 0)
    {
        rev = rev * 10 + temp % 10;
        temp /= 10;
    }

    if(rev == num)
        printf("Palindrome\n");
    else
        printf("Not Palindrome\n");
}

int main()
{
    int choice, x;

    while(1)
    {
        printf("\n1.Push\n2.Pop\n3.Display\n4.Palindrome\n5.Exit\n");
        printf("Enter choice: ");
        scanf("%d", &choice);

        switch(choice)
        {
            case 1:
                printf("Enter element: ");
                scanf("%d", &x);
                push(x);
                break;

            case 2:
                pop();
                break;

            case 3:
                display();
                break;

            case 4:
                palindrome();
                break;

            case 5:
                exit(0);

            default:
                printf("Invalid choice\n");
        }
    }
}
```

## Example Output

```
1.Push
2.Pop
3.Display
4.Palindrome
5.Exit
Enter choice: 1
Enter element: 10

1.Push
2.Pop
3.Display
4.Palindrome
5.Exit
Enter choice: 1
Enter element: 20

1.Push
2.Pop
3.Display
4.Palindrome
5.Exit
Enter choice: 3
Stack elements:
20 10 

1.Push
2.Pop
3.Display
4.Palindrome
5.Exit
Enter choice: 2
Popped element: 20

1.Push
2.Pop
3.Display
4.Palindrome
5.Exit
Enter choice: 5
```

## Author

[Your Name]

## License

MIT
EOF
