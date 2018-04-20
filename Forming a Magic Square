// 100% SOLUTION FOR CHALLENGE: Forming a Magic Square
// https://www.hackerrank.com/challenges/magic-square-forming/problem

import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    static int formingMagicSquare(int[][] s) {
        int [][] magicSquare = {{4,9,2},
                                {3,5,7},
                                {8,1,6}};
        int minimum = 100;
        int result;
        /*
        for (int i = 0; i < 3; i ++) {
            // first check
            result = compare(magicSquare, s);
            if (result < minimum) { minimum = result; }
            int[][] anotherMagic;
            // horizontal mirror
            anotherMagic = mirrorHorizontal(magicSquare);
            result = compare(anotherMagic, s);
            if (result < minimum) { minimum = result; }
            // vertical mirror
            anotherMagic = mirrorVertical(magicSquare);
            result = compare(anotherMagic, s);
            if (result < minimum) { minimum = result; }
            // double mirror
            anotherMagic = mirrorVertical(mirrorHorizontal(magicSquare));
            result = compare(anotherMagic, s);
            if (result < minimum) { minimum = result; }
            magicSquare = matrixRevolve(magicSquare);
        }
        */
        int matrix[][] = {
                                {4,9,2,3,5,7,8,1,6},
                                {4,3,8,9,5,1,2,7,6},
                                {2,9,4,7,5,3,6,1,8},
                                {2,7,6,9,5,1,4,3,8},
                                {8,1,6,3,5,7,4,9,2},
                                {8,3,4,1,5,9,6,7,2},
                                {6,7,2,1,5,9,8,3,4},
                                {6,1,8,7,5,3,2,9,4},
                        };
        for (int i=0; i < 8; i++) {
            int j = 0;
            int [][] magic = new int[3][3];
            for (int p = 0; p < 3; p++) {
                for (int r = 0; r<3; r++) {
                    magic[p][r] = matrix[i][j];
                    j++;
                }
            }
            result = compare(magic,s);
            if (result < minimum) { minimum = result; }
        }
        return minimum;
    }
    
    static int[][] mirrorHorizontal(int[][] matrix) {
        int [][] result = new int[3][3];
        for (int i = 0; i < 3; i++) {
            result[0][i] = matrix[2][i];
            result[1][i] = matrix[1][i];
            result[2][i] = matrix[0][i];
        }
        return result;
    }
    
    static int[][] mirrorVertical(int[][] matrix) {
        int [][] result = new int[3][3];
        for (int i = 0; i < 3; i++) {
            result[i][0] = matrix[i][2];
            result[i][1] = matrix[i][1];
            result[i][2] = matrix[i][i];
        }
        return result;
    }
    
    static int[][] matrixRevolve (int[][] matrix) {
        int[][] solution = new int [3][3];
        solution[0][0] = matrix [2][0];
        solution[0][1] = matrix [1][0];
        solution[0][2] = matrix [0][0];
        solution[1][2] = matrix [0][1];
        solution[2][2] = matrix [0][2];
        solution[2][1] = matrix [1][2];
        solution[2][0] = matrix [2][2];
        solution[1][0] = matrix [2][1];
        solution[1][1] = matrix [1][1];
        return solution;
    }
    
    static int compare (int[][] magic, int [][]normal) {
        int result = 0;
        for (int i=0; i < 3; i++) {
            for (int j=0; j<3; j++) {
                if (magic[i][j] != normal[i][j]) {
                    result += Math.abs(magic[i][j]-normal[i][j]);
                }
            }
        }
        return result;
    }

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int[][] s = new int[3][3];
        for(int s_i = 0; s_i < 3; s_i++){
            for(int s_j = 0; s_j < 3; s_j++){
                s[s_i][s_j] = in.nextInt();
            }
        }
        int result = formingMagicSquare(s);
        System.out.println(result);
        in.close();
    }
}
