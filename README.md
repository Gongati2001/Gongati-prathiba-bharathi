# Gongati-prathiba-bharathiimport java.util.*;
class Binary_Search {
// recursive binary search
int binarySearch(int numArray[], int left, int right, int key){
if (right >= left) {
//calculate mid of the array
int mid = left + (right - left) / 2;
// if the key is at mid, return mid
if (numArray[mid] == key)
return mid;
// if key < mid, recursively search the left subarray
if (numArray[mid] > key)
return binarySearch(numArray, left, mid - 1, key);
// Else recursively search in the right subarray
return binarySearch(numArray, mid + 1, right, key);
}
// no elements in the array, return -1
return -1;
}
}
class Main{
public static void main(String args[]) {
Binary_Search ob = new Binary_Search();
//declare and print the array
int numArray[] = { 4,6,12,16,22};
System.out.println("The given array : " Arrays.toString(numArray)); int len = numArray.length; //length of the array
int key = 16; //key to be searched
int result = ob.binarySearch(numArray, 0, len - 1, key);
if (result == -1)
System.out.println("Element " + key + " not present");
else
System.out.println("Element " + key + " found at index " +result);
}
}
