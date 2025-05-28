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


# LCM & GCD
class Solution {
    public static int[] lcmAndGcd(int a, int b) {
        int prod=a*b;
        while(b!=0){
            int temp=a%b;
            a=b;
            b=temp;
        }
        int gcd=a;
        int lcm=prod/gcd;
        return new int[] {lcm,gcd};
    }
}


# Sieve of Eratosthenes
class Solution {
    static ArrayList<Integer> sieveOfEratosthenes(int n) {
        boolean []primes=new boolean[n+1];
        ArrayList<Integer> res=new ArrayList<>();
        Arrays.fill(primes,true);
        primes[0]=primes[1]=false;
        for(int i=2;i<=n;i++){
            if(primes[i]==true){
                for(int j=2*i;j<=n;j+=i){
                    primes[j]=false;
                }
            }
        }
        for(int i=0;i<n+1;i++){
            if(primes[i]==true){
                res.add(i);
            }
        }
        return res;
   }
}

# Find rectangle with corners
class Solution {
    public boolean ValidCorner(int[][] mat) {
        int rows = mat.length;
        int cols = mat[0].length;
        for (int i = 0; i < rows; i++) {
            for (int j = i + 1; j < rows; j++) {
                int count = 0;
                for (int k = 0; k < cols; k++) {
                    if (mat[i][k] == 1 && mat[j][k] == 1) {
                        count++;
                        if (count >= 2) {
                            return true;
                        }
                    }
                }
            }
        }
        return false;
    }
}


# Pascal Triangle
class Solution {
    ArrayList<Integer> nthRowOfPascalTriangle(int n) {
        ArrayList<Integer> Prev=new ArrayList<>();
        ArrayList<Integer> Cur=new ArrayList<>();
        Prev.add(1);
        for(int i=1;i<n;i++){
            Cur=new ArrayList<>();
            Cur.add(1);
            for(int j=1;j<i;j++){
                Cur.add(Prev.get(j-1)+Prev.get(j));
            }
            Cur.add(1);
            Prev=Cur;
        }
        return Prev;
    }
}
