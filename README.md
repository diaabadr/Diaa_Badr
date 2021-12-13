# Usage of const keyword and & operator
## Const keyword:
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
    
### Constant Methods:
Like member functions and member function arguments, the objects of a class can also be declared as const. An object declared as const cannot be modified and can invoke only const member functions as these functions ensure not to modify the object.

```markdown
const Class_Name Object_name; // How to declare it
```
**Note that:**
- When a function is declared as const, it can be called on any type of object, const object as well as non-const objects.
- Whenever an object is declared as const, it needs to be initialized at the time of declaration. However, the object initialization while declaring is possible only with the help of constructors.

**Ways to declare const function:**
- If it's a global fun
```
const void fun() {}
```
- If it's a member fun
```
void fun() const {}
```
### Constant Function Parameters And Return Type:
- Const fun parameters:
```
void fun(const int y)
{
    // y = 6; error (y can't be change)
}
```
- Const return type:
```
const int fun(int y)
{
    y--;
    return y;
}
```
There is no issue to pass const or non-const variable to the function because the value that will be returned by the function will be constant automatically. As the argument of the function is non-const.
**Note that:** If you passed a const var to the function that returns a const, the passed var cannot be changed .
```
const int fun(const int x)
{
x=10; // not allowed
}
```
## References (or Aliases) (&):
When a variable is declared as a reference, it becomes an alternative name for an existing variable. A variable can be declared as a reference by putting ‘&’ in the declaration.

```
int x=10;
int y=&x; // y and x have the same location in the memory
```
**It has some useful apps like:**
- We can modify a value of a variable by passing it to a function by refernce like swapping function.
```
void swap(int &first,int &second)
{
int t=first;
first=second;
second=t;
}
```
- We can use it to save the memory when we pass an object with high size of memory to a function, We can pass it by reference and avoid copying if we passed it by value
```
struct Student {
   string name;
   string address;
   int rollNo;
}
// If we remove & in below function, a new copy of the student object is created. 
void print(const Student &s)
{
    cout << s.name << "  " << s.address << "  " << s.rollNo;
}
```
-  We can modify elements of an array by for each if we use reference
```
vector<int> vect{ 10, 20, 30, 40 }; 
    for (int &x : vect) 
        x = x + 5;
```
- In the copy constructors 
**At all most of references uses is to save the memory**
