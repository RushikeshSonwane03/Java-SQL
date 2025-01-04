# Control Statements

# Loops 
- Decision Making :
  1. if-else Statement :
     1. if statement 
      ```sh
        if (condition){
        statement ; 
        }
      ```
     2. if - else statement
      ```sh
        if (condition){
        statement ; 
        }
        else{
          statement ;
        }
      ```
     3. if - else - if statement
      ```sh
        if (condition1){
          statement ; 
        }
        else if (condition2){
          statement ;
        }
        else{
          statement ;
        }
      ```
     4. nested if statement
      ```sh
        if (condition1){
          if(condtion2){
            statement ;
          }
        }
      ```
     5. Short hand if-else
      ```sh
        variable = (condition) ? expressionTrue :  expressionFalse;
      ```

  2. Switch Case :

      ```sh
        switch(expression) {
          case x:
            // code block
            break;
          case y:
            // code block
            break;
          default:
            // code block
        }
      ```


- Iterations
  1. For Loop :
    For loop is used when we already know the starting and ending of the program.
    ```sh
    for (initialization; break condition; increment/decrement){
      // code block 
    }
    ```

  2. While Loop :
    While loop is used when we know the starting of the program but we have a condition to stop.
    ```sh
    initiaization ;
    while(break condition){
      // code block 
      increment/decrement ;
    }
    ```

  3. Do While Loop :
   ```sh
    initiaization ;
    do{
      // code block 
      increment/decrement ;
    } while(break condition);
    ```
