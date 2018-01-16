#HelloAirbus

//Scanner class is used to get input from the user.
import java.util.Scanner;

public class HelloAirbus {
    public static void main(String[] args) {
    	
     Scanner scan=new Scanner(System.in);
     System.out.println("Enter the number that you would like to convert :");

     
//While loop checks the input number if it is valid or not
     while(true){
    	 int nummer=scan.nextInt();
    	  
    	 if(nummer>0){
    		 String roman=HelloAirbus.toRoman(nummer);
    		 int number=HelloAirbus.toNumber(roman);
    		 System.out.println(number + " = " + roman);
    		 break;
    	 }
    	 else
    		 System.out.println("Number is invalid!");
     }
    }

//This method converts string values to Roman.
    private static String toRoman(int number) {
        return String.valueOf(new char[number]).replace('\0', 'I')
                .replaceAll("IIIII", "V")
                .replaceAll("IIII", "IV")
                .replaceAll("VV", "X")
                .replaceAll("VIV", "IX")
                .replaceAll("XXXXX", "L")
                .replaceAll("XXXX", "XL")
                .replaceAll("LL", "C")
                .replaceAll("LXL", "XC")
                .replaceAll("CCCCC", "D")
                .replaceAll("CCCC", "CD")
                .replaceAll("DD", "M")
                .replaceAll("DCD", "CM");
    }

//This method defines the number.
    private static Integer toNumber(String roman) {return roman
        	    	.replaceAll("CM", "DCD")
                .replaceAll("M", "DD")
                .replaceAll("CD", "CCCC")
                .replaceAll("D", "CCCCC")
                .replaceAll("XC", "LXL")
                .replaceAll("C", "LL")
                .replaceAll("XL", "XXXX")
                .replaceAll("L", "XXXXX")
                .replaceAll("IX", "VIV")
                .replaceAll("X", "VV")
                .replaceAll("IV", "IIII")
                .replaceAll("V", "IIIII").length();

// .length determines the value of number
    }
}
