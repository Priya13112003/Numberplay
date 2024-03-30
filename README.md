 import java.util.Scanner;

import java.util.Scanner;
class NumberPlay {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter the number");
        int number = scanner.nextInt();
        scanner.close();

        NumberSolver numberSolver = new NumberSolver();
        int result = numberSolver.solve(number);
        if (result == -999) {
            System.out.println("Invalid number");
        } else {
            System.out.println(result);
        }
    }
}

class NumberSolver {
    public int solve(int number) {
        if (number < 10 || number > 99) {
            return -999; // Invalid number
        }

        if (number > 50) {
            return Math.abs(getDigit(number, 0) - getDigit(number, 1));
        } else {
            int reversedNumber = getReversedNumber(number);
            return Math.abs(getDigit
 return Math.abs(getDigit(reversedNumber, 0) - getDigit(reversedNumber, 1));
        }
    }

    private int getDigit(int number, int position) {
        return Integer.parseInt(String.valueOf(number).substring(position, position + 1));
    }

    private int getReversedNumber(int number) {
        int tensDigit = number / 10;
        int onesDigit = number % 10;
        return onesDigit * 10 + tensDigit;
    }
}
