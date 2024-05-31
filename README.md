// Java implementation of iterative Binary Search
class BinarySearch {
	// Returns index of x if it is present in arr[l....r], else return -1
	int binarySearch(int arr[], int l, int r, int x)
	{
		while (l <= r) {
			int mid = (l + r) / 2;

			// If the element is present at the
			// middle itself
			if (arr[mid] == x) {
				return mid;

			// If element is smaller than mid, then
			// it can only be present in left subarray
			// so we decrease our r pointer to mid - 1 
			} else if (arr[mid] > x) {
				r = mid - 1;

			// Else the element can only be present
			// in right subarray
			// so we increase our l pointer to mid + 1
			} else {
			l = mid + 1;
			} 
		}

		// We reach here when element is not present
		// in array
		return -1;
	}

	// Driver method to test above
	public static void main(String args[])
	{
		BinarySearch ob = new BinarySearch();

		int arr[] = { 2, 3, 4, 10, 40 };
		int n = arr.length;
		int x = 10;
		int result = ob.binarySearch(arr, 0, n - 1, x);

		if (result == -1)
			System.out.println("Element not present");
		else
			System.out.println("Element found at index "
							+ result);
	}
}


// Java implementation of
// recursive Binary Search

// Driver Class
class BinarySearch {

	// Returns index of x if it is present in arr[l..
	// r], else return -1
	int binarySearch(int arr[], int l, int r, int x)
	{
		if (r >= l) {
			int mid = l + (r - l) / 2;

			// If the element is present at the
			// middle itself
			if (arr[mid] == x)
				return mid;

			// If element is smaller than mid, then
			// it can only be present in left subarray
			if (arr[mid] > x)
				return binarySearch(arr, l, mid - 1, x);

			// Else the element can only be present
			// in right subarray
			return binarySearch(arr, mid + 1, r, x);
		}

		// We reach here when element is not present
		// in array
		return -1;
	}

	// main function
	public static void main(String args[])
	{
		BinarySearch ob = new BinarySearch();

		int arr[] = { 2, 3, 4, 10, 40 };
		int n = arr.length;
		int x = 10;
		int result = ob.binarySearch(arr, 0, n - 1, x);

		if (result == -1)
			System.out.println(
				"Element is not present in array");
		else
			System.out.println(
				"Element is present at index " + result);
	}
}


// Java Program to demonstrate working of binarySearch()
// Method of Arrays class In a sorted array

// Importing required classes
import java.util.Arrays;

// Main class
public class GFG {

	// Main driver method
	public static void main(String[] args)
	{
		// Declaring an integer array
		int arr[] = { 10, 20, 15, 22, 35 };

		// Sorting the above array
		// using sort() method of Arrays class
		Arrays.sort(arr);

		int key = 22;
		int res = Arrays.binarySearch(arr, key);

		if (res >= 0)
			System.out.println(
				key + " found at index = " + res);
		else
			System.out.println(key + " Not found");

		key = 40;
		res = Arrays.binarySearch(arr, key);
		if (res >= 0)
			System.out.println(
				key + " found at index = " + res);
		else
			System.out.println(key + " Not found");
	}
}












// Java Program to Demonstrate Working of binarySearch()
// method of Collections class

// Importing required classes
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

// Main class
public class GFG {
	// Main driver method
	public static void main(String[] args)
	{
		// Creating an empty ArrayList of integer type
		List<Integer> al = new ArrayList<Integer>();

		// Populating the Arraylist
		al.add(1);
		al.add(2);
		al.add(3);
		al.add(10);
		al.add(20);

		// 10 is present at index 3
		int key = 10;
		int res = Collections.binarySearch(al, key);

		if (res >= 0)
			System.out.println(
				key + " found at index = " + res);
		else
			System.out.println(key + " Not found");

		key = 15;
		res = Collections.binarySearch(al, key);

		if (res >= 0)
			System.out.println(
				key + " found at index = " + res);
		else
			System.out.println(key + " Not found");
	}
}




