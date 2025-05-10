# Defuse-the-Bomb
class Solution {
    public int[] decrypt(int[] code, int k) {
        int[] result = new int[code.length];

        if (k == 0) {
            return result;
        }

        int n = code.length;

        //case1
        if (k > 0) {
            for (int i = 0; i < n; i++) {
                int sum = 0;
                for (int j = 1; j <= k; j++) {
                    sum += code[(i + j) % n];
                }
                result[i] = sum;
            }
        } else {
            //case2
            for (int i = 0; i < n; i++) {
                int sum = 0;
                for (int j = 1; j <= -k; j++) {
                    sum += code[(i - j + n) % n];
                }
                result[i] = sum;
            }

        }
        return result;
    }
}
