# Assignment2.1-Closest_Sum-

public class Main{

    static int closestSum(int[] arr, int x){

        int closestSum = Integer.MAX_VALUE;
        int n = arr.length;

        for(int i = 0; i < n; i++){
            for(int j = i+1; j < n; j++){
                for(int k = j+1; k < n; k++){

                    if(Math.abs(x - closestSum) > Math.abs(x - (arr[i] + arr[j] + arr[k])))
                        closestSum = (arr[i] + arr[j] + arr[k]);
                }
            }
        }
        return closestSum;
    }
    public static void main(String[] args) {
        int[] arr = {-1,2,1,-4};
        int x = 1;

        System.out.println(closestSum(arr,x));

    }
}

Assignment 3:-


public class Main{
    static void permute(int[] A, int[] P, int n){
        for(int i = 0; i < n; i++){
            int next = i;

            while(P[next] >= 0){
                swap(A, i, P[next]);
                int temp = P[next];

                P[next] -= n;
                next = temp;
            }
        }
    }

    static int[] swap(int[] arr, int i, int j){
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
        return arr;
    }

    public static void main(String[] args) {
        int A[] = {1,2,3};
        int P[] = { 4,5,6};
        int n = A.length;

        permute(A, P, n);

        for(int i = 0; i < n; i++)
            System.out.println(A[i]+ " ");
    }
}

Assignment 4:-

import java.util.Scanner;
public class Main{
    static int targetIndex(int[] arr, int target){

        int n = arr.length;
        int ans = 0;

        for(int i = 0;i < n; i++){
            if(arr[i] >= target){
                ans++;
            }
        }
        return ans;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the size of an Array: ");
        int n = sc.nextInt();
        int[] arr = new int[n];

        System.out.println("Enter " + n + " elements");
        for(int i = 0; i < n; i++){
            arr[i] = sc.nextInt();
        }
        System.out.println("Enter the Target sum: ");
        int target = sc.nextInt();
        System.out.println(targetIndex(arr, target));

    }
}

Assignment 5:-

import java.util.*;
import java.io.*;
public class Main {
    public static void main(String[] args) {

        int[] arr ={1,2,3};
        int num=arrayToNum(arr);
        num=num+1;
        int[] result=numToArray(num);
        arr=result;
        for(int i=0;i<arr.length;i++){
            System.out.print(arr[i]+" ");
        }
    }
    public static int arrayToNum(int[] arr){
        int idx=0;
        int ans=0;
        for(int i=arr.length-1;i>=0;i--){
            ans+=arr[i]*Math.pow(10,idx++);
        }
        return ans;
    }
    public static int[] numToArray(int num){
        int n=0;
        int copy_num=num;
        while(copy_num>0){
            copy_num/=10;
            n++;
        }
        int[] result=new int[n];
        int idx=n-1;
        while(num>0){
            result[idx--]=num%10;
            num=num/10;
        }
        return result;
    }
}

Assignment 6:-


import java.io.*;
public class Main{

    static int findSingle(int[] arr, int n){

        int ans = 0;
         for(int i=0; i<n; i++){
             for(int j=0; j<n; j++){
                 if(arr[i] == arr[j]){
                     ans++;
                 }
             }
             if(ans == 1){
                 return arr[i];
             }

         }
         return -1;
    }
    public static void main(String[] args) {
        int[] arr = {2,3,5,4,5,3,4};
        int n = arr.length;

        System.out.println("Element Occurring once " + findSingle(arr,n));
    }
}

Assignment:- 8


public class Main {
    public static boolean canAttend(int[][] intervals){
        if(intervals == null || intervals.length == 0) return true;
        for(int i = 1; i < intervals.length; i++){
            if(intervals[i][0] < intervals[i - 1][1])
                return false;
        }
        return true;
    }
    public static void main(String[] args) {
        int[][] t = {{0, 30}, {5, 10}, {15, 20}};
        System.out.println(canAttend(t));
    }
}


