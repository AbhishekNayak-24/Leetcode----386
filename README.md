# Leetcode----386
Lexicographical Numbers":
//code in java 
import java.util.ArrayList;
import java.util.List;

class Solution {
    public List<Integer> lexicalOrder(int n) {
        List<Integer> result = new ArrayList<>();
        int current = 1;
        for (int i = 1; i <= n; i++) {
            result.add(current);
            if (current * 10 <= n) {
                current *= 10;
            } else {
                while (current % 10 == 9 || current == n) {
                    current /= 10;
                }
                current++;
            }
        }
        return result;
    }
}
