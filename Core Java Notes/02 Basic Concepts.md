# Basics of Java

## Datatypes

- Primitive Datatypes :
  - Boolean :
    - Boolean
  - Numeric :
    - Character :
      - char
    - Integral :
      - Integer :
        - byte
        - short
        - int
        - long
      - Floating-Point : 
        - float
        - double
- Non-Primitive Datatypes :
  - String
  - Array
  - Etc.

## Variables :
- Variable is a Container which store the value while the program is executed.
- It is assigned with a datatype.
```sh 
    data_type variable_name = initial_value ; 
```
- eg. string a = "Rushi"; int x = 1;
  
### Types of Variables :
1. Local Variable : Accessible(scope) only inside the body of Method.
2. Global(Instance) Variable : Accessible(scope) in Entire Program(Class).
3. Static Variable :  Declared as Static.

```sh 
class Demo{
    int data = 50 ; // Instance(global) Variable
    static int val = 100 ; // Static Variable
    void method(){
        int count = 90 ; // Local variable
    }
}
```

## Operators :
- Operator is a Symbol which performs any mathematical Operation.
  
### Types of operators :
1. Unary :
   1. Postfix : (expr)++ , (expr)--
   2. Prefix : ++(expr) , --(expr)
2. Arthmetic : 
   1. Additive : + , - 
   2. Multiplicative : * , / , %
3. Relational :
   1. Comparison : < , > , <= , >= 
   2. Equality : == , !=
- [ == : operator is used for Reference or Address Comparision]
4. Logical :
   1. Logical AND : &&
   2. Logical OR : ||
5. Ternary :
   1. Ternary : ? , :


## Keywords
|  |  |  |  |  |
| ---- | ---- | ---- | ---- | ---- | 
| Boolean | byte | char | double | float |
| short | void | int | long | while |
| for | do | switch | break | continue |
| case | default | if | else | try |
| catch | finally | class | abstract | extends |
| final | import | new | instanc of | private |
| interface | native | public | package | implements |
| protected | return | static | super | synchronized |
| this | throw | throws | transient | volatile | 

