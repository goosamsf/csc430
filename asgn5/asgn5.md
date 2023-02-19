## Assignment 5 : Environment instead of Substitution, Higher order function.

## Things to do for this assignment:

### Environment Related :




### Higherorder Function Related :
    - Functions as Expressions and Values  
        1. Define core language to include function definitions.
        2. Change appC : now appC takes two exprC, function definition and arguments
            " now it doesn't have to look up by name as we've lumed function definition into exprC"  
        3.By change of 2, we need to chnage "interp" : add a case for function definition
        
            Think about the case : [fdC (n a b) exprC ] : error because interp return number  

        4. Interp need to reuturn something but not number  

        5. Define new type called "Value " , Now interp return Value instead of number  

        6. By the modification #5, Modify Binding and lookup accordingly.  

        7. BinopC has to be changed as interp returns value not a number  

        - What is closure ? 
            when you apply nested function, outer function's identifier is not bound to inner function  
            's body. So my environment should do something : a function value must be bundled with an environment.  
            This resulting datastructure is called closure.

        8. Add definition of closV in Value.
        9. Add lamC
        10. interp ,when encountering lamC, do closV
        11. interp ,when encountering appC, do with closV,
        12. Sugaring over anoymit


Current Problem :  How to convert JYSS5 -> IKEU5
    JYSS5 has function definition syntax : {proc {id ...} go Expr} whereas  
    IKEU5 has function definition syntax : {{id ...} : ExprC}
     [(list `proc (list (? symbol? args) ...) `go body)  << JYSS5 Syntax 
    
    IKEU? if there is list and ': colon ' and ExprC
    solved.
    {let {[id = ExprC] ... } ExprC}
    {vars: [id =Expr] ... body: Expr}
    
