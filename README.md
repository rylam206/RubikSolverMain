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
         side++;
     }
     return input;
   }
  
   public static int[][] cw(int colors[][]){
      int[] primaryFace = new int[58];
      primaryFace[0] = colors[1][0];
      primaryFace[1] = colors[1][1];
      primaryFace[2] = colors[1][2];
      primaryFace[3] = colors[1][3];
      primaryFace[4] = colors[1][4];
      primaryFace[5] = colors[1][5];
      primaryFace[6] = colors[1][6];
      primaryFace[7] = colors[1][7];
      primaryFace[8] = colors[1][8];
        
      colors[1][2] = primaryFace[0];
      colors[1][5] = primaryFace[1];
      colors[1][8] = primaryFace[2];
      colors[1][1] = primaryFace[3];
      colors[1][4] = primaryFace[4];
      colors[1][7] = primaryFace[5];
      colors[1][0] = primaryFace[6];
      colors[1][3] = primaryFace[7];
      colors[1][6] = primaryFace[8];

      int[] primaryOuter = new int[58];
      primaryOuter[40] = colors[4][0];
      primaryOuter[43] = colors[4][3];
      primaryOuter[46] = colors[4][6];
      primaryOuter[10] = colors[1][0];
      primaryOuter[13] = colors[1][3];
      primaryOuter[16] = colors[1][6];
      primaryOuter[50] = colors[5][0];
      primaryOuter[53] = colors[5][3];
      primaryOuter[56] = colors[5][6];
      primaryOuter[38] = colors[3][8];
      primaryOuter[35] = colors[3][5];
      primaryOuter[32] = colors[3][2];
        
      colors[1][0] = primaryOuter[40];
      colors[1][3] = primaryOuter[43];
      colors[1][6] = primaryOuter[46];
      colors[5][0] = primaryOuter[10];
      colors[5][3] = primaryOuter[13];
      colors[5][6] = primaryOuter[16];
      colors[3][8] = primaryOuter[50];
      colors[3][5] = primaryOuter[53];
      colors[3][2] = primaryOuter[56];
      colors[4][0] = primaryOuter[38];
      colors[4][3] = primaryOuter[35];
      colors[4][5] = primaryOuter[32];

   }
   
}
