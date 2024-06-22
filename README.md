# Currency-converter-using-Java
import java.util.Scanner;

public class CurrencyConverter {
    
    // Define conversion rates (as of some specific date)
    // Note: In real applications, you'd likely fetch these rates from a reliable financial API.
    private static final double INR_TO_USD = 0.012;
    private static final double INR_TO_EUR = 0.012;
    private static final double INR_TO_GBP = 0.0095;
    private static final double INR_TO_JPY = 1.9122;

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        // Prompt the user for the amount in INR
        System.out.print("Enter amount in INR: ");
        double amountInINR = scanner.nextDouble();
        
        // Prompt the user to choose the target currency
        System.out.println("Choose the target currency:");
        System.out.println("1: USD");
        System.out.println("2: EUR");
        System.out.println("3: GBP");
        System.out.println("4: JPY");
        int choice = scanner.nextInt();
        
        // Convert the amount to the chosen currency
        double convertedAmount = 0.0;
        String currency = "";
        
        switch (choice) {
            case 1:
                convertedAmount = convertINRToUSD(amountInINR);
                currency = "USD";
                break;
            case 2:
                convertedAmount = convertINRToEUR(amountInINR);
                currency = "EUR";
                break;
            case 3:
                convertedAmount = convertINRToGBP(amountInINR);
                currency = "GBP";
                break;
            case 4:
                convertedAmount = convertINRToJPY(amountInINR);
                currency = "JPY";
                break;
            default:
                System.out.println("Invalid choice.");
                System.exit(0);
        }
        
        // Display the converted amount
        System.out.printf("%.2f INR is equal to %.2f %s%n", amountInINR, convertedAmount, currency);
        
        scanner.close();
    }

    // Conversion methods
    public static double convertINRToUSD(double amountInINR) {
        return amountInINR * INR_TO_USD;
    }

    public static double convertINRToEUR(double amountInINR) {
        return amountInINR * INR_TO_EUR;
    }

    public static double convertINRToGBP(double amountInINR) {
        return amountInINR * INR_TO_GBP;
    }

    public static double convertINRToJPY(double amountInINR) {
        return amountInINR * INR_TO_JPY;
    }
}
