Yahtzee
=======

import java.util.*;

public class yams{

	static int ones (int[]die) {  
		int sum;
		int valeur;

		valeur=1;
		sum=0;
		for(i=0; i<=die.length){
		   if(die[i]==valeur){
	              sum==sum+valeur;
	           }
		}
		return sum;
	}

	static int twos (int[]die) {
		int sum;
		int valeur;

		valeur=2;
		sum=0;
		for(i=0; i<=die.length; i++){
		   if(die[i]==valeur){
	              sum==sum+valeur;
	           }
		}
		return sum;
	}
	
	/* it's the same code of "ones" and "twos" for the 3s,4s,5s,6s */

	static int full (int[]die) {
		int points;
		int sum;

		points=25;
		sum=0;
		if(die[0]==die[1] && die[1]==die[2] && die[3]==die[4] || die[0]==die[1] && die[2]==die[3] && die[3]==die[4]){
			for(i=0; i<=die.length; i++){
				sum==sum+die[i];
			}
			return points;
		}
		return 0;
	}

	static int fourOfAKind (int[]die) {
		int sum;
		int carre;

		carre=1;
		sum=0;
		i=0;		
		do{	
	   		if(die[i]==die[i+1]) {
				carre==carre+1;
			}else{
				if(i!=0&&i!=3){
					carre==0;
				}
			}
			sum=sum+die[i];
			i=i+1;
		while(i<die.length-1);
		sum=sum+die[i];
		if(carre>=4){
			return sum;
		}else{
			return 0;
		}
	}


	static int smallSuite(int[]die){
		int points;
		int c;

		points=30;
		c=0;
		for(i=0; i<=die.length;i++){
			if(die[i]==(die[i+1]-1)){
				c==c+1;
			}
		}
		if(c>=3){
			return points;
		} else{
			return 0;
		}
	}


	static int grandSuite(int[]die){
		int points;
		int c;

		for(i=0;i<=die.length-1;1++){
			if(die[i]==(die[i+1]-1)){
				c==c+1;
			}
		}
		if(c>=4){
			return points;
		} else{
			return 0;
		}
	}


	static int yahtzee(int[]die){
		int points;
		int sum;

		points=50;
		sum=0;
		for(i=0;i<=die.length-1;i++){
			if(die[i]==die[i+1]){
				sum==sum+die[i];
			}else{
				return 0;
			}
		}
		return points;
	}





    public static void main(String[] args){

 	   int x;
 	   int valeur;
 	   int[][]grille;
   	   int[]die;
   	   String[]name;

	Scanner sc = new Scanner(System.in);
	Scanner scn = new Scanner(System.in);

	do{
	    System.out.println("Give the number of the players(be careful, it has to be a positive number): ");
    	     x = sc.nextInt();
	}while(x<1);

	 grille= new int [15][x];
	 die= new int[4];

	 valeur=(int)(Math.random()*6+1);

	 name= new String [x-1];
	 for(int i=0;i<=name.length;i++){
	     System.out.println("Names: ");
	     name[i]=scn.nextLine();
	}
	

}

}

	    
