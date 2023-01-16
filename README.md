# mergesort

// Online Java Compiler
// Use this editor to write, compile and run your Java code online

class HelloWorld {
    public static void conquer(int arr[], int strt, int mid, int end){
        int merged[]=new int [end-strt+1];
        int indx1=strt;
        int indx2= mid+1;
        int x=0;
        while(indx1<=mid &&indx2<=end){
            if(indx1<indx2){
                merged[x++]=arr[indx1++];
            }
            else
            {
                  merged[x++]=arr[indx2++];
            }
        }
        while(indx1<=mid){
             merged[x++]=arr[indx1++];
            
        }
        while(indx2<=end){
             merged[x++]=arr[indx2++];
            
        }
        
    }
    
    public static void mergesort(int arr[], int strt , int end) {
        int mid = strt+(end-strt)/2;
        if(strt>=end){
            return;
        }
        mergesort(arr, 0 , mid);
        mergesort(arr, mid+1, end);
        conquer(arr, strt , mid , end);
    }
    public static void main(String[] args) {
    int arr[]= { 2,1,8,5,9};
    int n= arr.length;
    mergesort(arr, 0, n-1);
    for(int i=0; i<n;i++){
    System.out.print(arr[i]+" ");
    }
    System.out.println();
    }
}
