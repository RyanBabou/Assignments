# Assignment 4
## task

2. The worst case is sorted in reverse [5,4,3,2,1]. Pass 1 has 1 comparison and 1 shift, pass 2 has 2 comparisons and 2 shifts, pass 3 has 3 comparisons and 3 shifts, pass 4 has 4 comparisons and 4 shifts. So that makes in total 10 comparisons plus 10 shifts which would end up equaling 20 operations.I changed the inspected index to start at 0, but I skipped the first element since it’s already sorted. The passes are the same, so the total is still 20 operations.
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
##link
https://drive.google.com/file/d/1m7hnLI7xmmWnfczc7lbvDrfVo4VaJ7HP/view?usp=sharing
