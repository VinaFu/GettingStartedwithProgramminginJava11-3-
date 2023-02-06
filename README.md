# GettingStartedwithProgramminginJava11-3-

7. Strings 

	How to convert into String
	
	How to modify the String - using StringBuilder
	
	How to find an item - .indexOf  : returns the index(position) of 1st occurrence of a specific text in a string(space incl.)
	
	How to insert the string - .insert(position, item)
				   .insert(position +4, time)		- two differnt ways, but same result.


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
	
	
Other classes that are useful:

    Scanner = get user input, and it is found in the java.util package. 
    StringBuilder = create mutable(modified) string. 
		.append()
		.insert()
    
    See example below: change [location] & [flightNumber]
    
    e.g.
	    public class Main {
	    public static void main(String[] args) {
		String location = "Florida";
		int flightNumber = 175;
		StringBuilder sb = new StringBuilder(40);
		sb.append("I flew to ");
		sb.append(location);
		sb.append(" on Flight # ");
		sb.append(flightNumber);

	//                I flew to (Florida) on Flight # (175)
		System.out.println(sb);
	    }
	}


.append()
	
	    public class Main {
	    public static void main(String[] args) {
		String location = "Florida";
		int flightNumber = 175;
		StringBuilder sb = new StringBuilder(40);
		sb.append("I flight to " + location + " on Flight # " + flightNumber);
		System.out.println(sb);
	    }
	}
	
.insert(pos, item); manipulating wiht the index of item
	
	String time = "9:00"; // define a string
        int pos = sb.indexOf(" on");  // define the position of " on"
        sb.insert(pos, " at " + time); // insert before the position
		//I flew to Florida at 9:00 on Flight # (175)
	
	String time = "9:00"; //
        int pos = sb.indexOf(" on");  // see ~~~
        sb.insert(pos, " at " );     // see ----
        sb.insert(pos +4, time); // here, the pos is the original place of " on", 
				 // since " at " occupy 4 places, start with the four digit after pos
				 // I flew to Florida on Flight # 175
				 		     ~~~
				 // I flew to Florida at  on Flight # 175		  
						     ----~~~ 	original pos +4, then add "time"

        System.out.println(sb);
	
	 
        sb.insert(pos, " around " );
        sb.insert(pos +8, time); // 8-digits in " around ".
				 // I flew to Florida around 9:00 on Flight # 175
	
	int pos = sb.indexOf(" on");  
        sb.insert(pos -4, time); // I flew to Flo9:00rida on Flight # 175
	
	int pos = sb.indexOf(" on");  
        sb.insert(pos +4, time); // I flew to Florida on 9:00Flight # 175
	
	
Convert the word-operation into symbol equation and display it: 
	
	private static void displayResult(char opCode, double leftVal, double rightVal, double result) {
        char symbol = symbolFromOpCode(opCode);
        StringBuilder builder = new StringBuilder(20);
        builder.append(leftVal + " " + symbol + " " + rightVal + " = " + result); // concatenation the string;
        String output = builder.toString();
        System.out.println(output);
    }

    private static char symbolFromOpCode(char opCode){
        char[] opCodes = {'a', 's', 'm', 'd'};
        char[] symbols = {'+', '-', 'x', '/'};
        char symbol = ' ';
        for(int index = 0; index < opCodes.length; index++){
            if (opCode == opCodes[index]){
                symbol = symbols[index];
                break;
            }
        }
        return symbol;
    } 
