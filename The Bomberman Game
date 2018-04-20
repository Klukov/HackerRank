// 100% SOLUTION FOR THE CHALLENGE: The Bomberman Game
// https://www.hackerrank.com/challenges/bomber-man/problem

import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    static String[] bomberMan(int time, int r, int c, String[] grid) {
        char [][] res = new char [r][c];
        char [][] griddd = new char [r][c];
        char [][] result = new char [r][c];
        for (int i = 0; i < r; i ++) {
            griddd[i] = grid[i].toCharArray();
        }
        //return convertionCharMatrixtoStringArray(r,c,griddd);
        for (int m=0; m < r; m++) {
            for (int n=0; n < c; n++) {
                res[m][n] = 'O';
            }
        }
        if ((time == 0) || (time == 1)){
            return convertionCharMatrixtoStringArray(r,c,griddd);
        }
        else if (time%2 == 0) {
            return convertionCharMatrixtoStringArray(r,c,res);
        }
        else {
            if ((time - 3)%4 == 0) {
                griddd = bombsCalculation (r, c, griddd);
            }
            if ((time - 3)%4 == 2) {
                griddd = bombsCalculation (r, c, griddd);
                griddd = bombsCalculation (r, c, griddd);
            }
            return convertionCharMatrixtoStringArray(r,c,griddd);
        }
        //return convertionCharMatrixtoStringArray(r,c,result);
    }
    
    public static char[][] bombsCalculation (int r, int c, char[][] grid) {
        char [][] result = new char [r][c];
        for (int m=0; m < r; m++) {
            for (int n=0; n < c; n++) {
                result[m][n] = 'O';
            }
        }
        for  (int i=0; i < r; i++) {
            for (int j=0; j < c; j++) {
                if (grid[i][j] == 'O') {
                    result[i][j] = '.';
                    if (!((i-1) < 0)) {
                        result[i-1][j] = '.';
                    }
                    if (!((i+1) >= r)) {
                        result[i+1][j] = '.';
                    }
                    if (!((j-1) < 0)) {
                        result[i][j-1] = '.';
                    }
                    if (!((j+1) >= c)) {
                        result[i][j+1] = '.';
                    }
                }
            }
        }
        return result;
    }
    
    public static String[] convertionCharMatrixtoStringArray (int rows, int columns, char[][] matrix) {
        String [] array = new String [rows];
        for (int i = 0; i < rows; i++) {
            array[i] = new String(matrix[i]);
        }
        return array;
    }
    
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int r = in.nextInt();
        int c = in.nextInt();
        int n = in.nextInt();
        String[] grid = new String[r];
        for(int grid_i = 0; grid_i < r; grid_i++){
            grid[grid_i] = in.next();
        }
        String[] result = bomberMan(n, r, c, grid);
        for (int i = 0; i < r; i++) {
            System.out.print(result[i] + (i != result.length - 1 ? "\n" : ""));
        }
        System.out.println("");
        in.close();
    }
}
