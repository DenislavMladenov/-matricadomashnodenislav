package matricadomashnodenislav;

public class matricadomashnodenislav 
{

	public static void main (String[] args) {
	int[][] matrix = 
	{
            { 0, 2, 4, 0, 9, 5 },

            { 7, 1, 3, 3, 2, 1 },

            { 1, 3, 9, 8, 5, 6 },

            { 4, 6, 7, 9, 1, 0 },
    };

    int bestsum = Integer.MIN_VALUE;

    int bestrow = 0;

    int bestcol = 0;

    for (int row = 0; row < matrix.length - 1; row++) {

        for (int col = 0; col < matrix[0].length - 1; col++) {

            int sum = matrix[row][col] + matrix[row][col + 1] + matrix[row + 1][col] + matrix[row + 1][col + 1];

            if (sum > bestsum) {

                bestsum = sum;

                bestrow = row;

                bestcol = col;

            }

        }

    }

    System.out.println("the best platform is:");

    System.out.printf("  %d %d %d %n",

    matrix[bestrow][bestcol], matrix[bestrow][bestcol + 1], matrix[bestrow + 1][bestcol]);

    System.out.printf("  %d %d %d %n",

    matrix[bestrow + 1][bestcol],matrix[bestrow + 1][bestcol - 1],matrix[bestrow + 1][bestcol - 1]);
    System.out.printf("  %d %d %d %n", matrix[bestrow + 1][bestcol],matrix[bestrow + 1][bestcol - 1],
    matrix[bestrow][bestcol]);

    System.out.printf("the maximal sum is: %d%n", bestsum);

}
}
