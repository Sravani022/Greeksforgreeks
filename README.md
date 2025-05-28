# Greeksforgreeks
class Solution {
    public int sumSubstrings(String s) {
        int totalSum = 0;
        for (int i = 0; i < s.length(); i++) {
            for (int j = i + 1; j <= s.length(); j++) {
                String substring = s.substring(i, j);
                totalSum += Integer.parseInt(substring);
            }
        }
        return totalSum;
    }
    public static void main(String[] args) {
        String s = "6759";
        Solution ob = new Solution();
        System.out.println("Output: " + ob.sumSubstrings(s));
}
}

# GCd Of Two Numbers
class Solution {
    public static int gcd(int a, int b) {
        // code here
        while(b!=0){
            int temp=a%b;
            a=b;
            b=temp;
        }
        return a;
    }
}
