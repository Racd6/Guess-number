# Guess-number

Guess number


import java.util.Random;
import java.util.Scanner;

public class GuessNumberGame {
    public static void main(String[] args) {
        Random random = new Random();
        int randomNumber = random.nextInt(21); // Generate a random number between 0 and 20
        int maxGuessCount = 5;
        int remainingGuesses = maxGuessCount;

        Scanner scanner = new Scanner(System.in);

        System.out.println("Guess a number between 0 and 20.");

        while (remainingGuesses > 0) {
            System.out.printf("You have %d guesses remaining. Enter your guess: ", remainingGuesses);
            int userGuess = scanner.nextInt();

            if (userGuess == randomNumber) {
                System.out.println("You win!");
                break;
            } else if (remainingGuesses == 1) {
                System.out.println("You lose!");
                System.out.println("The number was: " + randomNumber);
                break;
            } else {
                remainingGuesses--;
                System.out.println("Wrong guess. Try again.");
            }
        }

        scanner.close();
    }
}
