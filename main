import java.util.Scanner;

public class MetricConverter {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Welcome to Metric Converter!");
        System.out.println("Please input your query. For example, '1 kg to lb'.");
        System.out.println("Enter 'exit' to quit the program.");

        while (true) {
            System.out.print("Enter your conversion query: ");
            String input = scanner.nextLine().trim();

            if (input.equalsIgnoreCase("exit")) {
                System.out.println("Exiting the program. Goodbye!");
                break;
            }

            String[] tokens = input.split(" ");

            if (tokens.length != 4 || !tokens[2].equals("to")) {
                System.out.println("Invalid input format. Please use 'X unit to unit'.");
                continue;
            }

            double value;
            try {
                value = Double.parseDouble(tokens[0]);
            } catch (NumberFormatException e) {
                System.out.println("Invalid input format for value. Please use a number.");
                continue;
            }

            String fromUnit = tokens[1];
            String toUnit = tokens[3];

            double result = performConversion(value, fromUnit, toUnit);

            if (result == -1) {
                System.out.println("Conversion not supported. Please try another query.");
            } else {
                System.out.println(value + " " + fromUnit + " is equal to " + result + " " + toUnit);
            }
        }

        scanner.close();
    }

    private static double performConversion(double value, String fromUnit, String toUnit) {
        switch (fromUnit) {
            case "kg":
                switch (toUnit) {
                    case "lb":
                        return value * 2.20462;
                }
                break;
            case "g":
                switch (toUnit) {
                    case "oz":
                        return value * 0.03527396;
                }
                break;
            case "km":
                switch (toUnit) {
                    case "mi":
                        return value * 0.621371;
                }
                break;
            case "mm":
                switch (toUnit) {
                    case "in":
                        return value * 0.0393701;
                }
                break;
        }
        return -1; // Conversion not supported
    }
}
