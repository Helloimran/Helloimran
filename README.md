import java.util.*;
  
  public class Main{
  
  public static void main(String[] args) {
      Scanner scn = new Scanner(System.in);
      int b = scn.nextInt();
      int n1 = scn.nextInt();
      int n2 = scn.nextInt();
      
      int d = getSum(b, n1, n2);
      System.out.println(d);
   }
     public static int getSum(int b, int n1, int n2){
         int dn1 = ConvertNuDecimal(b, n1);
         int dn2 = ConvertNuDecimal(b, n2);
         int sum = dn1 + dn2;
         int cvb = AnyBase(b, sum);
        
         return cvb;
  }
    public static int ConvertNuDecimal(int b, int n){
       int rv = 0;
       int p = 1;
       while(n > 0){
           int rem = n % 10;
           n = n / 10;
           rv = rv + p * rem;
           p = p * b;
       }
      
       return rv;
       
   }
     public static int AnyBase(int b, int n){
      int ans = 0;
      
      int p = 1;
      while(n > 0){
          int rem = n % b;
          n /= b;
          ans = ans + p * rem;
          p = p * 10;
      }
      return ans;
  }
   
 }
