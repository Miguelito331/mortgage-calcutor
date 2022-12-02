import java.awt.Point;
import java.text.NumberFormat;
import java.util.Scanner;
public class sheeshables{
    
    public static void main(String[] args){
        // looks bad but it works
        //input principal
        Scanner principalInput = new Scanner(System.in);
        System.out.print("Principal: ");
        int principal = principalInput.nextInt();

        //input annual
        Scanner annualInterestInput = new Scanner(System.in);
        System.out.print("Annual Interest Rate: ");
        Double annual = annualInterestInput.nextDouble();

        //conversion annual interest to monthly interest
        Double monthly = (annual / 100 / 12);

        // input period in years
        Scanner periodInput = new Scanner(System.in);
        System.out.print("Period (years): ");
        int periodYears = periodInput.nextInt();

        // conversion years to months
        int periodMonths = (periodYears * 12);

        //raising to monthly 
        double raised = Math.pow(1 + monthly, periodMonths);    

        //whole solution
        double mortgageComputed = (principal * monthly) * raised / (raised - 1);

        //printing currency $$$
        String result = NumberFormat.getCurrencyInstance().format(mortgageComputed);
        System.out.println("Mortgage: " + result);
    }
} 
