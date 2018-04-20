// 100% SOLUTION FOR CHALLAGE Matrix Layer Rotation
// https://www.hackerrank.com/challenges/matrix-rotation-algo/problem

import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    static int[] calculatePosition (int framePosition, int frameNum, int dim1, int dim2) {
        int [] position = new int [2];
        int frameDim1 = dim1 - 2*(frameNum - 1);
        int frameDim2 = dim2 - 2*(frameNum - 1);
        int point0 [] = new int[2];
        if (framePosition < frameDim1) {
            //point0[0] = frameNum-1;
            //point0[1] = frameNum-1;
            int loop = framePosition;
            position[0] = frameNum-1 + loop;
            position[1] = frameNum-1;
        }
        else if (framePosition < (frameDim1+frameDim2-1)) {
            //point0[0] = frameNum + frameDim1 - 2;
            //point0[1] = frameNum-1;
            int loop = framePosition - frameDim1 + 1;
            position[0] = frameNum + frameDim1 - 2;
            position[1] = frameNum-1 + loop;
        }
        else if (framePosition < (2*frameDim1+frameDim2-2)) {
            //point0[0] = frameNum + frameDim1 - 2;
            //point0[1] = frameNum + frameDim2 - 2;
            int loop = framePosition - frameDim1 - frameDim2 + 2;
            position[0] = frameNum + frameDim1 - 2 - loop;
            position[1] = frameNum + frameDim2 - 2;
        }
        else {
            //point0[0] = frameNum-1;
            //point0[1] = frameNum + frameDim2 - 2;
            int loop = framePosition - 2*frameDim1 - frameDim2 + 3;
            position[0] = frameNum-1;
            position[1] = frameNum + frameDim2 - 2 - loop;
        }
        return position;
    }
    
    static int[][] calculateFrame (int frameNum, int dim1, int dim2, int rotation, int[][] matrix) {
        int[][] solution = new int [dim1][dim2];
        for (int i = 0; i < dim1; i++) {
            for (int j = 0; j < dim2; j++) {
                solution[i][j] = matrix[i][j];
            }
        }
        
        int frameLength = 2*(dim1 - 2*(frameNum - 1)) + 2*(dim2 - 2*(frameNum - 1)) - 4;
        int frameRotation = rotation % frameLength;
        for (int i = 0; i < frameLength; i++) {
            int[] position = new int [2];
            int[] newPosition = new int [2];
            int positionInNewFrame = (i + frameRotation)%frameLength;
            //System.out.println(positionInNewFrame);
            position = calculatePosition(i, frameNum, dim1, dim2);
            newPosition = calculatePosition(positionInNewFrame, frameNum, dim1, dim2);
            solution[newPosition[0]][newPosition[1]] = matrix[position[0]][position[1]];
        }
        
        return solution;
    }
    
    static void matrixRotation(int dim1, int dim2, int rotation, int[][] matrix) {
        //
        int frames, frameDim1, frameDim2;
        if (dim1 < dim2)    { frames = dim1/2; } 
        else                { frames = dim2/2; }

        for (int i = 1; i <= frames; i++) {
            frameDim1 = dim1 - (i-1)*2;
            int [][] tempMatrix = calculateFrame(i, dim1, dim2, rotation, matrix);
            for (int j = 0; j < dim1; j++) {
                for (int k = 0; k < dim2; k++) {
                    matrix[j][k] = tempMatrix[j][k];
                }
            }
        }

        // print matrix
        for (int i = 0; i < dim1; i++) {
            for (int j = 0; j < dim2; j++) {
                System.out.print(matrix[i][j]);
                System.out.print(" ");
            }
            System.out.println("");
        }
        return;
    }

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int m = in.nextInt();
        int n = in.nextInt();
        int r = in.nextInt();
        int[][] matrix = new int[m][n];
        for(int matrix_i = 0; matrix_i < m; matrix_i++){
            for(int matrix_j = 0; matrix_j < n; matrix_j++){
                matrix[matrix_i][matrix_j] = in.nextInt();
            }
        }
        matrixRotation(m, n, r, matrix);
        in.close();
    }
}
