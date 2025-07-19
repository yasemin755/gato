import java.util.Random;
import java.util.Scanner;

public class StonePaperScissors {
    public static void main(String[] args) {
        String[] choices = {"Stone", "Paper", "Scissors"};
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        while (true) {
            System.out.println("Enter your choice (Stone, Paper, Scissors). To quit, type Exit:");
            String userInput = scanner.nextLine();

            if (userInput.equalsIgnoreCase("Exit")) {
                System.out.println("Thanks for playing!");
                break;
            }

            int computerChoice = random.nextInt(3);
            String computerInput = choices[computerChoice];

            System.out.println("Computer chose: " + computerInput);

            if (userInput.equalsIgnoreCase(computerInput)) {
                System.out.println("It's a draw!");
            } else if (
                (userInput.equalsIgnoreCase("Stone") && computerInput.equals("Scissors")) ||
                (userInput.equalsIgnoreCase("Paper") && computerInput.equals("Stone")) ||
                (userInput.equalsIgnoreCase("Scissors") && computerInput.equals("Paper"))
            ) {
                System.out.println("You win!");
            } else if (
                userInput.equalsIgnoreCase("Stone") ||
                userInput.equalsIgnoreCase("Paper") ||
                userInput.equalsIgnoreCase("Scissors")
            ) {
                System.out.println("You lose!");
            } else {
                System.out.println("Invalid input. Please enter Stone, Paper, or Scissors.");
            }
        }
        scanner.close();
    }
}