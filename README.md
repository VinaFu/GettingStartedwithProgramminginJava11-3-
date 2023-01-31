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
        
    3) .intern() - creates an exact copy of a String object in the heap memory and stores it in the String constant pool.
    
    String class Methods: https://www.w3schools.com/java/java_ref_string.asp
    Common ones: 
                 Method	    	Description		Return Type
                 charAt()		Returns the character at the specified index (position)		char
                 concat()		Appends a string to the end of another string	String
                 substring()		Returns a new string which is the substring of a specified string		String
                equalsIgnoreCase()		Compares two strings, ignoring case considerations	Boolean
                trim()	Removes whitespace from both ends of a string	String
                toLowerCase()	Converts a string to lower case letters		String
                toString()	Returns the value of a String object		String
		
     Converting Non-string Types to String
            String.valueOf()
            .toString()
            conversation - see e.g below
            
           e.g:
                int i = 2, j = 3;
                int result = i * j;
                String output =  result + " * ";
                System.out.println(output); // 6 *
                                            // String output = result, doesn't work; while converstion: i + " * " + j + "=" + result, works 
	
     For instance, how to use charAt() & word.equals(), see the practice below:
	
	static char opCodeFromString(String operationName){
		char opCode = operationName.charAt(0);
		return opCode;
	    } // m - multiply; s - subtract;

	    double valueFromWord(String word){
		String[] numberWords = {
			"zero", "one", "two", "three", "four", "five", "six", "seven", "eight", "nine"
		};
		double value = 0d;
		for(int index = 0; index < numberWords.length; index++){
		    if(word.equals(numberWords[index])) { // if the typing words match the numberWords array, convert it into number/value
			value = index;
			break;
		    }
		}
		return value;
	    }

8. String Formatting
