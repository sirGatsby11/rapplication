# rapplication

syntax tree for the expressions 

a = b + c 

*make node (op, left ptr, right ptr)
*make-leaf value


        =       a+b  (operator)
      /   \         
     a      +         
            / \
          b    c
          
 // b left ptr
 // c right ptr
 
 E-> E1 + E2
 E-> E1             E
                    |
                    E1
                    
                    
E-> id               E
     |               |
     !               !    // check symbols
     
 
E -> E1 + T:                     E.node 
E -> E1 - T:                    /   |   \
E -> T:                     E.node  +   T.node 
T -> (E):                     |             |
T -> id:                    T.node           ! // check symbol
T -> id:                       |              |
T -> num:                     id               c


