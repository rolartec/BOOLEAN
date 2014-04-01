BOOLEAN
=======

GUESS-NUMBER-BOOLEAN 



//	By  Reina Olarte
// 	Guessing Number using BOOLEAN

import java.util.Scanner;// imports the scanner class
import java.util.Random;// imports the random class

public class BooleanFinal

{
		public static void main( String[]args)
{
	//Create the Scanner to input the number
	Scanner input = new Scanner(System.in);
	//Create the Random number
	Random randomNumber = new Random();

	//Declaring the variables
	int UserNumber;
	int computerNumber;
	computerNumber = 0 + (int)(Math.random() *10);
	boolean GameWon = false;
	boolean ResultLow = false;
	boolean ResultHigh = false;
	boolean EndGame = false;
	String Continue = "Q";

	while (!EndGame)
	{

	System.out.println("Welcome to the Guessing game\nPlease enter a digit from 0 to 10:");
	UserNumber = input.nextInt();

	if (computerNumber == UserNumber)
	{
		GameWon = true;
	}

	else
		{
			if (computerNumber < UserNumber)
			{
				ResultHigh = true;
			}
			else
			{	
				ResultLow = true;
			}	
		}

	if(GameWon)
	{
		System.out.println("You Guessed the right number");
		System.out.printf("Your number %d, Random number %d" , UserNumber, computerNumber);
	}
	else if (ResultHigh)
	{
		System.out.println("You Guessed to High");
		System.out.printf("Your number %d, Random number %d" , UserNumber, computerNumber);
	}
	else if (ResultLow)
	{
		System.out.println("You Guessed to Low");
		System.out.printf("Your number %d, Random number %d" , UserNumber, computerNumber);
	}

	System.out.println("\n\nWould You like to continue?\nPress Y for yes, Type Q for Quit");

	Continue = input.next();

	if (Continue.isEmpty() || Continue.length() == 0)
	{
		EndGame = false;
	}

	switch(Continue.toUpperCase())
		{
	case "Q":
		EndGame = true;
		break;
	case "QUIT":
		EndGame = true;
		break;
	case "":
		EndGame = false;
		break;
	default:
		EndGame = false;
		break;
		}


	//EndGame = !(EndGame || Continue.isEmpty() || Continue.length() == 0);

	}//End of While loop
}//End main

}//End class
