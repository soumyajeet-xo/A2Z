# Second Largest
### Brute Force : Sort the array then second largest number is a number such that number is just less than largest
Code : 
```
class Solution {
    int print2largest(int arr[], int n) {
        // code here
        int lar=arr[0];
        for(int i=0;i<n;i++){
            if(arr[i]>lar)
             lar=arr[i];
        }
        int slar=-1;
        for(int i=0;i<n;i++){
            if(arr[i]>slar && arr[i]!=lar){
                slar=arr[i];
            }
        }
        return slar;
    }
}
```

### Optimised : if arr[i] is greater than lar then slar becomes lar and lar becomes arr[i] but if arr[i] is lesser then lar and greater then slar then slar becomes arr[i]
```
 int print2largest(int arr[], int n) {
        int lar=arr[0];
        int slar=-1;
        for(int i=0;i<n;i++){
            if(arr[i]>lar){
                slar=lar;
                lar=arr[i];
            }
            else if(arr[i]<lar && arr[i]>slar){
                slar=arr[i];
        }
    }
    return slar;
}
```
