import java.util.Scanner;

public class MinMaxProductCheck {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input the size of the array
        System.out.print("Enter the size of the array: ");
        int n = scanner.nextInt();

        // Input the array elements
        int[] array = new int[n];
        System.out.println("Enter the elements of the array:");
        for (int i = 0; i < n; i++) {
            array[i] = scanner.nextInt();
        }

        // Find the minimum and maximum values in the array
        int min = array[0];
        int max = array[0];
        for (int i = 1; i < n; i++) {
            if (array[i] < min) {
                min = array[i];
            }
            if (array[i] > max) {
                max = array[i];
            }
        }

        // Calculate the product of min and max
        int product = min * max;

        // Check if the product is a multiple of both min and max
        boolean isMultipleOfMin = (product % min == 0);
        boolean isMultipleOfMax = (product % max == 0);

        // Output the result
        boolean result = isMultipleOfMin && isMultipleOfMax;
        System.out.println(result);

        scanner.close();
    }
}
