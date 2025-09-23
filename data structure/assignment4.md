# Assignment 4
## task

2. The worst case is sorted in reverse [5,4,3,2,1]. Every pass 1 has 1 comparison and 1 shift, pass 2 has 2 and 2, pass 3 has 3 and 3, pass 4 has 4 and 4. So that makes in total 10 comparsions plus 10 shifts which would end up equaling 20 operations.I changed the inspected index to start at 0, but I skipped the first element since it’s already sorted. The passes are the same, so the total is still 20 operation.
3. 
A. the function's time complexity regarding big O notation is O(N).

B. function containsX(string) {
	foundX = false;
	for(let i = 0; i < string.length; i++) { 
		if (string[i] === "X") {
			return true; 
		}
	}
	return false; 
}
