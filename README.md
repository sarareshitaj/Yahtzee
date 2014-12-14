import java.util.*;

public class yams {

    static int deUnASix(int[] die, int valeur) {
        int sum;
        int x;

        x = valeur;
        sum = 0;

        // The <= below will cause an ArrayIndexOutOfBoundsException. You need <
        for (int i = 0; i <= die.length; i++) {
            if (die[i] == x) {
                sum = sum + x;
            }
        }
        return sum;
    }

    static int full(int[] die) {
        int points;
        int sum;

        points = 25;
        sum = 0;
        if (die[0] == die[1] && die[1] == die[2] && die[3] == die[4] || die[0] == die[1] && die[2] == die[3] && die[3] == die[4]) {
            for (int i = 0; i <= die.length; i++) {
                sum = sum + die[i];
            }
            return points;
        }
        return 0;
    }

    static int fourOfAKind(int[] die) {
        int sum;
        int carre;
        int k;

        carre = 1;
        sum = 0;
        k = 0;
        // Why use a 'do - while' here rather than a 'for'?
        do {
            if (die[k] == die[k + 1]) {
                carre = carre + 1;
            } else {
                if (k != 0 && k != 3) {
                    carre = 0;
                }
            }
            sum = sum + die[k];
            k = k + 1;
        } while (k < die.length - 1);
        sum = sum + die[k];
        if (carre >= 4) {
            return sum;
        } else {
            return 0;
        }
    }

    static int smallSuite(int[] die) {
        int points;
        int c;

        points = 30;
        c = 0;
        // The <= below will cause an ArrayIndexOutOfBoundsException. You need <
        for (int i = 0; i <= die.length; i++) {
            if (die[i] == (die[i + 1] - 1)) {
                c = c + 1;
            }
        }
        if (c >= 3) {
            return points;
        } else {
            return 0;
        }
    }

    static int grandeSuite(int[] die) {
        int points = 40;
        int c = 0;

        for (int i = 0; i <= die.length - 1; i++) {
            // You will get an ArrayIndexOutOfBoundsException below. Check your loop declaration
            if (die[i] == (die[i + 1] - 1)) {
                c = c + 1;
            }
        }
        if (c >= 4) {
            return points;
        } else {
            return 0;
        }
    }

    static int yahtzee(int[] die) {
        int points;
        int sum;

        points = 50;
        sum = 0;
        // The <= below will cause an ArrayIndexOutOfBoundsException.
        for (int i = 0; i <= die.length - 1; i++) {
            if (die[i] == die[i + 1]) {
                sum = sum + die[i];
            } else {
                return 0;
            }
        }
        return points;
    }

    public static void main(String[] args) {

        int x;
        int valeur;
        int[][] grille;
        int[] die;
        String[] name;

        Scanner sc = new Scanner(System.in);
        Scanner scn = new Scanner(System.in);

        do {
            System.out.println("Give the number of the players(be careful, it has to be a positive number): ");
            x = sc.nextInt();
        } while (x < 1);

        grille = new int[15][x];
        die = new int[4];

        valeur = (int) (Math.random() * 6 + 1);

        // I think you should use 'x' below, not x - 1. If x is the number of players, you
        // want x elements in the array, not x - 1.
        name = new String[x - 1];
        // The <= below will cause an ArrayIndexOutOfBoundsException. You need <
        for (int i = 0; i <= name.length; i++) {
            System.out.println("Names: ");
            name[i] = scn.nextLine();
        }

        // Next: OK. You've got the number of players and their names. Let's do a bit of top-down programming:
        // It seems that there are a number of rounds in the game. During each round the players will take turns
        // to throw the dice. They will be allowed to rethrow some of the dice up to 3 times before the score
        // is evaluated.
        // What I want you to do is write code here that calls a function (that doesn't
        // exist yet) that allows the players to play a round. At the end of the round, it should return
        // an updated score sheet for each player, which it will use in the next round.
        // It might seem strange to call a function that doesn't exist yet, but what you're actually doing is
        // saying 'this is what I want at this layer'. In order to do this, you'll need to think about what
        // parameters to pass. You won't get this right first time, but have a think about it. What you need
        // to think about is what bits of information you have in local scope here that that function will need.
        // Again, don't worry about getting it exactly right. Just get the shape of the code you're writing here
        // approximately right.
    }

}
