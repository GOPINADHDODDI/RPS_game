import java.util.*;

public class Game7 
{
    
    public static final String ROCK = "ROCK";
    public static final String PAPER = "PAPER";
    public static final String SCISSORS = "SCISSORS";

    public static void main(String args[]) 
    {
	int k=0;
	Scanner in = new Scanner(System.in);
	while(k!=-1){
      System.out.println("Enter any one of the following inputs:  ");
      System.out.println("ROCK");
      System.out.println("PAPER");
      System.out.println("SCISSORS");
      System.out.println();
          
      String playerMove = getPlayerMove();
      String computerMove = getComputerMove(); 
 
      //Rules of the Game Applied Below:
      /*if both playerMove and computerMove
        produces the same formation, then 
        Game is a tie*/
      if (playerMove.equals(computerMove))
            System.out.println("Game is Tie !!");
      // if playerMove is ROCK         
      else if (playerMove.equals(Game7.ROCK))
        System.out.println(computerMove.equals(Game7.PAPER) ? "Computer Wins": "Player wins");   
      // if playerMove is PAPER
      else if (playerMove.equals(Game7.PAPER))
        System.out.println(computerMove.equals(Game7.SCISSORS) ? "Computer Wins": "Player wins");   
      // if playerMove is SCISSORS    
      else
        System.out.println(computerMove.equals(Game7.ROCK) ? "Computer Wins": "Player wins");   
    
	System.out.println("Do You Want To Continue");
	System.out.println("If yes type any number else type '-1'");
	k=in.nextInt();
    }
    }
    /* Get Computer's move using Random 
       class nextInt() method */   
    public static String getComputerMove()
    {
        String computermove;
        Random random = new Random();
        int input = random.nextInt(3)+1;
        if (input == 1)
            computermove = Game7.ROCK;
        else if(input == 2)
            computermove = Game7.PAPER;
        else
            computermove = Game7.SCISSORS;
            
        System.out.println("Computer move is: " + computermove);
        System.out.println();
        return computermove;    
    }
    
    /* Get Player's move using Scanner
       class */
    public static String getPlayerMove()
    {
	  
        Scanner in = new Scanner(System.in);
        String input = in.next();
        String playermove = input.toUpperCase();
        System.out.println("Player move is: "+ playermove);
	  return playermove;
	  
    }    
}
