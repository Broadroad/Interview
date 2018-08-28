# binary add (111 + 001 = 1000)
// Add two binary values represented in strings, returns the result in string. For example “1011” + “101” = “10000”.
// const string & why?
string AddTwoString(const string& A, const string& B) {
	if (A.size() == 0) {
    	return B;
    }
  
  	if (B.size() == 0) {
    	return A;
    } 
  
  	string C;
  	int lenA = A.size();
  	int lenB = B.size();
  
  	int isOverflow = 0;
    int i = lenA - 1;
    int j = lenB - 1;
  
  	int k = 0;
	for (; i >= 0 || j >= 0; --i, --j) {
        int sumc = isOverflow;
      	if (i >= 0) {
        	sumc += A[i] - '0';
        } 
      
      	if (j >= 0) {
        	sumc += B[j] - '0';
        }
      
      	isOverflow = sumc >=2 ? 1: 0; // can use sumc >> 1 to determin isOverflow is 1 or 0
      	if (sumc & 1 == 0) {
        	C.append('0');
        } else {
        	C.append('1')
        }
      	
    }
  
  	if (isOverflow) {
    	C.append('1');
    }
  
  	return reverse(C.begin(), c.end());
}



# LRU cache design
- What to cache?
- Need to validate?
- Only use memory

## LRU cache key point
- Need to get at O(1)
- Need to set at O(1)
- Need to remove oldest item at O(1)

# longest tree in binary tree