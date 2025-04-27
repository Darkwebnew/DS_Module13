# Ex4 Evaluation of prefix expression
## DATE:
## AIM:
To write a C function to evaluate the given prefix expression using stack and print the output of the given prefix expression from the stack inside the function . 

## Algorithm

1. Start the program.
2. Initialize a stack. 
3. Traverse the prefix expression from right to left
4. If the symbol is an operand, push it onto the stack.  
5. If the symbol is an operator, pop two elements from the stack, apply the operator, and push the result back.  
6. After the traversal, the final result will be at the top of the stack.
7. Print the result.
8. End.


## Program:
```
Program to evaluate the given prefix expression
Developed by: 
RegisterNumber:  
```
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int s[50];
int top=0;

void push(int ch)
{
	top++;
	s[top]=ch;
}

int pop()
{
	int ch;
	ch=s[top];
	top=top-1;
	return(ch);
}

void evalprefix(char p[50])
{
        int a,b,c,i;
    for(i=strlen(p)-1;i>=0;i--){
        if(p[i]=='-'){
            a=pop();
		b=pop();
		c=a-b;
		push(c);
        }else if(p[i]=='+'){
            a=pop();
		b=pop();
		c=a+b;
		push(c);
        }else if(p[i]=='*')
		{	
		a=pop();
		b=pop();
		c=b*a;
		push(c);
		}
		else if(p[i]=='/')
		{
			a=pop();
			b=pop();
			c=a/b;
			push(c);
		}else
		{
			push(p[i]-48);
		}
    }
    printf("%d",pop());
    	
}

int  main()
{
  char p[100]="-+8/632";
  evalprefix(p);
	return 0;
	
}

```

## Output:

![image](https://github.com/user-attachments/assets/610808aa-d073-4eb3-ad3d-0af4a086a8b6)


## Result:
Thus, the C program to evaluate the prefix expression using stack and print the output of the given prefix expression from the stack inside the function is implemented successfully.
