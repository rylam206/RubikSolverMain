# RubikSolver
import java.util.Scanner;
public class rubikSolverMain{
   
   public static void main(String[] args){
      int Cube_colors[][] = new int[6][9];
      Cube_colors = getColors();
   }
   
   public static int[][] getColors(){
      int input[][] = new int[6][9];
      
      int counter_0 = 0;
      int counter_1 = 1;
      int side = 0;
      String[] colors = {"green", "white", "blue", "yellow", "orange", "red"};
      Scanner in = new Scanner(System.in);
      
      while(side <= 5){
         System.out.println("Enter the colors for the " + colors[side] + " side"
                           + " \n1 = Green\n2 = White\n3 = Blue\n4 = Yellow\n5 = Orange\n6 = Red\n"
                           + "Orange side should be on top\n"
                           + "The red side should be on the bottom\n"
                           + "The white side should be on the right\n"
                           + "And the yellow side should be on the left\n");
         while(counter_0 <= 8){
            input[side][counter_0] = Integer.parseInt(in.nextLine());
            counter_0++;
         }
         counter_0 = 0;
     }
     return input;
   }
}
