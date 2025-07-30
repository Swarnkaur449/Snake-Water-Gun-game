# Snake-Water-Gun-game
import java.util.Scanner;
import java.util.Random;

public class SnakeWaterGun {

    static String gameWin(char comp, char you) {
        if (comp == you) {
            return "tie";
        } else if (comp == 's') {
            if (you == 'w') {
                return "lose";
            } else if (you == 'g') {
                return "win";
            }
        } else if (comp == 'w') {
            if (you == 'g') {
                return "lose";
            } else if (you == 's') {
                return "win";
            }
        } else if (comp == 'g') {
            if (you == 's') {
                return "lose";
            } else if (you == 'w') {
                return "win";
            }
        }
        return "invalid"; // in case of invalid input
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Random rand = new Random();

        System.out.println("Comp's Turn: Snake (s), Water (w), Gun (g)?");

        int randNo = rand.nextInt(3) + 1;  // 1 to 3
        char comp = ' ';

        if (randNo == 1)
            comp = 's';
        else if (randNo == 2)
            comp = 'w';
        else if (randNo == 3)
            comp = 'g';

        System.out.print("Your Turn: Snake (s), Water (w), Gun (g): ");
        char you = sc.next().charAt(0);

        System.out.println("Computer chose: " + comp);
        System.out.println("You chose: " + you);

        String result = gameWin(comp, you);

        if (result.equals("tie")) {
            System.out.println("The game is a tie!");
        } else if (result.equals("win")) {
            System.out.println("You Win!");
        } else if (result.equals("lose")) {
            System.out.println("You Lose!");
        } else {
            System.out.println("Invalid input!");
        }

        sc.close();
    }
}
