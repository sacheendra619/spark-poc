Intuition

Take the example A = [12, 28, 46], B = [46, 12, 28]. We want to know where the 12 occurs in B, say at position 1; then where the 28 occurs in B, which is position 2; then where the 46 occurs in B, which is position 0.

If we had a dictionary (hash table) D = {46: 0, 12: 1, 28: 2}, then this question could be handled easily.

Algorithm

Create the hash table D as described above. Then, the answer is a list of D[A[i]] for i = 0, 1, ....
```java
class Solution {
    public int[] anagramMappings(int[] A, int[] B) {
        Map<Integer, Integer> D = new HashMap();
        for (int i = 0; i < B.length; ++i)
            D.put(B[i], i);

        int[] ans = new int[A.length];
        int t = 0;
        for (int x: A)
            ans[t++] = D.get(x);
        return ans;
    }
}
```

Complexity Analysis

Time Complexity: O(N)where N is the length of A.

Space Complexity: O(N)
