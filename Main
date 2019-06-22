import java.util.*;
class TicTacToe
{
    char ticTacToeGrid[][];
    char ch1;
    char ch2;
    
    public void displayOptions()
    {
        System.out.println("********    ***    *******        ********          ***          *******        ********         ***         *******");
        System.out.println("********    ***    *******        ********         *****         *******        ********       *******       *******");
        System.out.println("********    ***    **             ********        *** ***        **             ********    ****     ****    **     ");
        System.out.println("   **       ***    **                **          ***   ***       **                **      ***         ***   *******");
        System.out.println("   **       ***    **                **         ***********      **                **      ***         ***   *******");
        System.out.println("   **       ***    **                **        *************     **                **       ****     ****    **     ");
        System.out.println("   **       ***    *******           **       ***         ***    *******           **          *******       *******");
        System.out.println("   **       ***    *******           **      ***           ***   *******           **            ***         *******"); 
        System.out.println("\n\n\n\n\n\tMenu");
        System.out.println("1. NEW GAME;");
        System.out.println("2. HOW TO PLAY");
        System.out.println("3. QUIT");
    }
    
    public void createGrid()
    {
        ticTacToeGrid=new char[3][3];
        for (int i=0;i<3;i++)
        {
            for (int j=0;j<3;j++)
            {
                ticTacToeGrid[i][j]=' ';
            }
        }
        ch1='X';
        ch2='O';
    }

    public void displayGrid()
    {
        for (int i=0;i<3;i++)
        {
            for (int j=0;j<3;j++)
            {
                if(j != 0)
                {
                    System.out.print(" |");
                }
                System.out.print(ticTacToeGrid[i][j]);
            }
            
            System.out.println("");
            
            if(i != 2)
            {
                System.out.println("-- -- --");
            }
        }
    }
    
    
    
    public int condition(int row,int col,int opt)
    {
        int i,j;
        int r=(opt==1)?1:2;
        char ch=(opt==1)?ch1:ch2; 
        for (i=0;i<=2;i++)
        {
            if(ticTacToeGrid[i][0] == ch && ticTacToeGrid[i][1] == ch && ticTacToeGrid[i][2] == ch)
            {
                return r;
            }
            else if(ticTacToeGrid[0][i]==ch&&ticTacToeGrid[1][i]==ch&&ticTacToeGrid[2][i]==ch)
            {
                return r;
            }
        }  
        if(ticTacToeGrid[0][0]==ch&&ticTacToeGrid[1][1]==ch&&ticTacToeGrid[2][2]==ch)
        {
            return r;
        }
        else if(ticTacToeGrid[2][0]==ch&&ticTacToeGrid[1][1]==ch&&ticTacToeGrid[0][2]==ch)
        {
            return r;
        }            
            
        for (i=0;i<=2;i++)
        {
            for (j=0;j<=2;j++)
            {
                if (ticTacToeGrid[i][j]==' ')
                {
                    return 3;
                }
            }
        }
        
        return 4;        
    }
    public int result(int row,int col,int opt)
    {
        int r=condition(row,col,opt);
        switch(r)
        {
            case 1:System.out.println("Winner of the match is Player X");
                   break;
            case 2:System.out.println("Winner of the match is Player O");
                   break;
            case 4:System.out.println("All the spaces in the grid are filled up \nMATCH DRAW!");
                   break;
            case 3:return 3;
        }
        return 0;
    }
    public int enter(int row,int col,int opt)
    {
        char ch=(opt==1)?ch1:ch2;
        if(row<=2&&col<=2&&row>=0&&col>=0)
        {            
            if (ticTacToeGrid[row][col]!=' ')
            {
                System.out.println("Invalid input. The input block is already occupied.\n");
                displayGrid();
                return 5;
            }
            else
            {
                ticTacToeGrid[row][col]=ch;
                return 3;
            }
        }
        System.out.println("Invalid input. Row and column nos. should be either 1, 2 or 3");
        return 5;
    }
    public void main()
    {
        Scanner sc=new Scanner (System.in);
        double l=0;
        int choice;
        int a;
        char ch;
        do
        {
            displayOptions();
            choice=sc.nextInt();
            if (choice==1)
            {
                createGrid();
                displayGrid();
                int opt,col,row,r=1;
                for (int i=1;r!=0;i++)
                {
                    opt=i%2;
                    ch=(opt==1)?ch1:ch2;
                    System.out.println("Player "+ch+"'s turn\n\nPlease enter the column number:");
                    col=sc.nextInt()-1;
                    System.out.println("Please enter the row number:");
                    row=sc.nextInt()-1;
                    a=enter(row,col,opt);
                    if(a==5)
                    {
                        i--;
                    }
                    else
                    {
                        r=result(row,col,opt);   
                    }
                    displayGrid();
                }
                for (l=0;l<=99999999;l+=0.1)
                {
                    
                }
            }
            else if(choice==2)
            {
                System.out.println("The instruction of theis game is simple\nThe objective is to form the first straight line in the grid of 'X' or 'O'.\nIf  line is of 'X' the player 1 wins.\nIf line is of 'O' then player 2 wins\nNo straight line then match is draw");
                
            }
            else if(choice!=3)
            {
                System.out.println("Invalid Input . Enter values from 1/2/3");
            }
        }while(choice!=3);
    }
}
