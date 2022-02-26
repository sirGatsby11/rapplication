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


E.node  = new node ('+' E.node)
E.node  = new node ('-' E.node)
E.node = T.node 
T.node = new leaf 
T.node = new bay (num,!) // check symbols




P1 = newbay (id, a)
P2 = newbay (id, b)
P3 = newbay (-, P, P2)
P4 = newbay (id, c)
P5 = new node (+, !) // check symbols 



      | + |  |  |
        /        \
    |-| | |   |id | c |
  |id | a |     | id | b |      
   
