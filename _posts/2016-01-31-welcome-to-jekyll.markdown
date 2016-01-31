---
layout: post
title:  "Difference between switch and if/else"
date:   2016-01-31 10:01:48
categories: Skill Distillery 
---




{% highlight java %}
import java.util.Scanner;
		/*
			Just testing the differences between if/if else and switch using
			 some junk code that has no intentional purpose 
		*/

	public class switchTest{
		public static void main(String[]args){
			Scanner keyboard = new Scanner(System.in);

			String word1 = "test1", word2 = "test2", sTest, switchVar;
			double dNumber, dTest;

			do{
				System.out.println("\nString test: if else1. Type exit to move on to the double if else... :) ");
				System.out.print("TEST ME STRING: ");
				sTest = keyboard.next();

				if (sTest.equals("test1")){
					System.out.println("asdf");
				}
				else if (sTest.equals(word2)){
					System.out.println(word2);
				}
				else if(sTest.equals("exit")){
						System.out.println("see you later");
				}
				else{
					if (sTest.compareTo("sanctuary") < 0 ){
					System.out.println(sTest + " alphabetically precedes sanctuary. ");
					}
					if (sTest.compareTo("sanctuary") == 0 ){
					System.out.println(sTest + " is... what it is... ");
					}
					if (sTest.compareTo("sanctuary") > 0 ){
					System.out.println(sTest + " alphabetically succeeds sanctuary. ");
					}
				}

				System.out.println("\nDouble test: if else2. Type 0 to exit and continue to the switch... :) ");
				System.out.print("TEST ME DOUBLE: ");
				dTest = keyboard.nextInt();

				if((dTest !=0) && (dTest * 5) < 100){
					System.out.println(dTest + " times 5 is less than 100. ");
				}
				else if((dTest * 10) > 100 && (dTest * 10) < 300) {
					System.out.println(dTest + " when multiplied by 10 is grater than 100 and less than 300. ");

				}
				else if(dTest == 0){
					System.out.println("Bye Bye! see you at the switch ");
				}
				else{
					System.out.print(" DOH!...");
				}


			}while(!sTest.equals("exit") && (dTest != 0));

// ------VVVV-------Here I attempt to replicate the if else with a switch --------VVVVV-----

			
			
			switchVar = "initialized";
			dTest = 1; //reset value 


			while(!switchVar.equals("see you later") && (dTest != 0)){
				System.out.println("\nTest: SWITCH1. :) ");
				System.out.print("TEST ME STRING: ");
				sTest = keyboard.next();
				word2 = "test2"; //<----  initializing the variabe does not help the case to hold a variable 
				switch(sTest){

					case "test1": switchVar = "asdf";
									break;
				/*	case word2: switchVar = word2;	<---- console prints error: constant string expression required 
									break;					
					
					As far as alphabetically comparing a var: 
					To my current knowledge, the only way to lexically order the stored input from a scanner 
					is to use inputVar.compareTo("comparate") < 0;....etc.
					Without suprise, the following does not compile with in switch: 

					case .compareTo("sanctuary") < 0 : switchVar = sTest + "alphabetically precedes sanctuary";
									break;

					I would have to get the < 0, = 0, or > 0 comparison value and store that into a variable prior to 
					the switch to then use in a switch, which I think is way more work than necessary. Might as well
					use a if/if else.

					Switches are for switching on the value of a single variable (that simplifies to a constant). 
					Switches do not support logical oporators.
					Therefor the previous "Double test: if else2" section can't (for the most part) be directly 
					translated into a switch without useing some other if statements and operators outside of the switch. 
				*/	
					case "exit": switchVar = "I think we understand whats going on here";
									break;
					default: switchVar = "DOH!...";

				}
				System.out.println("The value of your input has been \"switched\" to: " + switchVar);
				sTest = "reset";
			}


			System.out.println("..and thats it!...");

		}
	}
{% endhighlight %}



