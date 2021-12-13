## Usage of const keyword and & operator

### Constant Variables:

It's used to declare constant variable which cannot ever be changed all over the project

```markdown
    const int y = 10; // how to declare it
```
### Const Keyword With Pointer Variables:
there are three possible ways to use a const keyword with a pointer, which are as follows:
- **pointer variable point to a const value**

```markdown
int x= 10 ;
const int* i = &x;// how to declare it 
x=5; // successful statement
(*i)++;// error
```
Here i is a pointer variable that is pointing to a memory location const int-type, but the value stored at this corresponding location can be changed by the variable but cannot be changed through the pointer

- **Const pointer variable point to the value**

```markdown
  int x = 10; 
  int* const i = &x; // how to declare it 
  x=5; //successful statement
  (*i)++; //successful statement
  ```
  The value that is stored in the corresponding pointer variable is modifiable even through the pointer ot through the variable itself , but the locations that is pointed out by const-pointer variable where the corresponding value of x is stored is’t modifiable. 
 
 - **Const pointer pointing to a const variable**
 
 ```markdown
 int x = 10 ;
    const int* const i = &x;  // how to declare it
    x=5  //successful statement
    (*i)++ ; // error
 ```
    Here the const pointer variable points to the const variable. So, you are neither allowed to change the const pointer variable(*P) nor the value stored at the location pointed by that pointer variable(*P) , you can change it just with the var.
    
