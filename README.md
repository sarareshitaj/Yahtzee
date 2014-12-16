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

// i made some new programming which works so it rolls the dices and shows their values

public static void main(String[] args) {

    int x;
    String[] nom;
    int[] de = new int[] { 0, 0, 0, 0, 0 };

    Scanner sc = new Scanner(System.in);
    Scanner scn = new Scanner(System.in);

    do {
        System.out.println("how many players? ");
        x = sc.nextInt();
    } while (x < 1);
   
    nom = new String[x];
    
    for (int i = 0; i < nom.length; i++) {
        System.out.println(" Names: ");
        nom[i] = scn.nextLine();
    }
 // here i roll the dices and i show their values
    for (x = 0; x < 5; x++) {
	de[x] = (int)(Math.random()*6+1);
		
    }

	System.out.println("Die 1: " + de[0]);
	System.out.println("Die 2: " + de[1]);
	System.out.println("Die 3: " + de[2]);
	System.out.println("Die 4: " + de[3]);
	System.out.println("Die 5: " + de[4]);
}
 
    // until here it works. 
    //Then i tried this code to reroll some of the dices but it doesnt really work :/ ??
    
    do {
	System.out.println("how many dices do you want to reroll?(0-5)");
	 Scanner sc;
	 Scanner scn;
	  = sc.nextInt();
	if (rejouer1 > 0) {
		int[] rejouer = new int[rejouer1];
		for (y = 0; y < rejouer1; y++) {
			System.out.println("which ones?");
			rejouer2 = scn.nextInt();
			rejouer[y] = rejouer2;
		}
		for (w = 0; w < rejouer1; w++) {
			if (rejouer[w] == 1) {
				de[0] = (int)(Math.random()*+1);
			}
			if (rejouer[w] == 2) {
				de[1] = (int)(Math.random()*+1);
			}
			if (rejouer[w] == 3) {
				de[2] = (int)(Math.random()*+1);
			}
			if (rejouer[w] == 4) {
				de[3] = (int)(Math.random()*+1);
			}
			if (rejouer[w] == 5) {
				de[4] = (int)(Math.random()*+1);
			}
		}
		roll++;
		System.out.println("De 1: " + de[0]);
		System.out.println("De 2: " + de[1]);
		System.out.println("De 3: " + de[2]);
		System.out.println("De 4: " + de[3]);
		System.out.println("De 5: " + de[4]);

	}
} while ((roll < 2) && (rejouer1 > 0));
	

}

 
 
