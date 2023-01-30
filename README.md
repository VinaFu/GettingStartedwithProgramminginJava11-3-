# GettingStartedwithProgramminginJava11-3-

7. Strings 

    e.g:
    String s1 = "I love";
    s1 += " Java"; // I love Java - can be added together as well
    String s2 = "I";
    s2 += " love Java"; // I love Java
    
    Equality:
    
    1) if(s1 == s2) // false - same value, but different instances
        // do sth.
        ==: refers to same string instance; do not compare the value
        
    2) if(s1.equals(s2))// true
        // do sth.
        char-by-char value comparison: I = I, space = space, L = L, etc.
        
    3) intern() - creates an exact copy of a String object in the heap memory and stores it in the String constant pool.
    
   TO BE CONTINUE 7 - 4:32 end (intern)

8. String Formatting
