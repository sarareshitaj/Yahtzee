import java.util.*;

public class tp {

    static int deUnASix(int[] de, int valeur) {
        int somme;
        int x;

        x = valeur;
        somme = 0;

        for (int i = 0; i < de.length; i++) {
            if (de[i] == x) {
                somme = somme + x;
            }
        }
        return somme;
    }

    static int full(int[] de) {
        int points;
        int somme;

        points = 25;
        somme = 0;
        if (de[0] == de[1] && de[1] == de[2] && de[3] == de[4] || de[0] == de[1] && de[2] == de[3] && de[3] == de[4]) {
            for (int i = 0; i <= de.length; i++) {
                somme = somme + de[i];
            }
            return points;
        }
        return 0;
    }

    static int carre(int[] de) {
        int somme;
        int carre;
        int k;

        carre = 1;
        somme = 0;
        k = 0;
        do {
            if (de[k] == de[k + 1]) {
                carre = carre + 1;
            } else {
                if (k != 0 && k != 3) {
                    carre = 0;
                }
            }
            somme = somme + de[k];
            k = k + 1;
        } while (k < de.length - 1);
        somme = somme + de[k];
        if (carre >= 4) {
            return somme;
        } else {
            return 0;
        }
    }

    static int petiteSuite(int[] de) {
        int points;
        int c;

        points = 30;
        c = 0;
        for (int i = 0; i < de.length; i++) {
            if (de[i] == (de[i + 1] - 1)) {
                c = c + 1;
            }
        }
        if (c >= 3) {
            return points;
        } else {
            return 0;
        }
    }

    static int grandeSuite(int[] de) {
        int points = 40;
        int c = 0;

        for (int i = 0; i <= de.length - 1; i++) {
            if (de[i] == (de[i + 1] - 1)) {
                c = c + 1;
            }
        }
        if (c >= 4) {
            return points;
        } else {
            return 0;
        }
    }

    static int yams(int[] de) {
        int points;
        int somme;

        points = 50;
        somme = 0;
        for (int i = 0; i < de.length - 1; i++) {
            if (de[i] == de[i + 1]) {
                somme = somme + de[i];
            } else {
                return 0;
            }
        }
        return points;
    }

// You are trying to do the detail before you've got the overall structure. I'm going to refactor
// the code below a little bit to try to help you. I don't want to just write the whole thing
// for you because you won't learn that way.

    static int readNumberOfPlayers(Scanner sc) {
        int x;

        do {
            System.out.println("How many players? ");
            x = sc.nextInt();
            sc.nextLine(); // This consumes the newline after the int that was read above
        } while (x < 1);

        return x;
    }

    static String[] readPlayerNames(Scanner sc) {
        int number = readNumberOfPlayers(sc);
        String[] nom = new String[number];

        for (int i = 0; i < nom.length; i++) {
            System.out.println("Name " + (i + 1) + ": ");
            nom[i] = sc.nextLine();
        }

        return nom;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // You see that here I *delegate* to a function to do this work? I don't try to do everything at this level.
        String[] names = readPlayerNames(sc);

        // I am now going to delegate to another function to play the game. I'm going to write that function for you, then I
        // am going to ask you to do the next bit in the same style as I've established here.

        int[][][] rolls = playGame(names);
    }

    // The dimensions of the array returned represent rounds, players and dice. So, there are:
    // * 15 elements in its first dimension, which represent the rounds
    // * the same number of elements in its second dimension as there are playerNames
    // * 5 elements in its third dimension which are the values of the dice throws
    static int[][][] playGame(String[] playerNames) {
        int[][][] rolls = new int[15][playerNames.length][5];
        for (int round = 0; round < 15; round++) {
            playRound(round, playerNames, rolls);
        }
        return rolls;
    }

    static void playRound(int round, String[] playerNames, int[][][] rolls) {
        // TODO Fill in this method in the same style as I've done in playGame.
        // i.e. Describe how you would play a round and delegate to other methods. As a hint, a round consists of each player
        // taking a turn. Consider looping over the playerNames and delegating to another method which will deal with that player
        // having a turn. The idea is that when that method returns, the appropriate elements of 'rolls' will have been filled in.
        // But do not write that other method yet. Just fill in this one for now.
        // When you have implemented this method, it should only be three lines long.
    }
}
