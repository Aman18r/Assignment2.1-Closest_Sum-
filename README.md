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
