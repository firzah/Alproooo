Alproooo
========
package romawit3;

public class Romawi implements Comparable{
    private double rata;
    private String ahay;
    double kosong=0;
    public Romawi (){}
    public Romawi (String a){
    ahay=(String) a;   
    nilai();
  }    
    public int nilai (){
        
    for (int a=0;a<ahay.length();a++){    
           
        char convertToDecimal = ahay.charAt(a);

        switch (convertToDecimal)
        {
        case 'M':
            kosong += 1000;
            break;
        case 'D':
            kosong += 500;
            break;
        case 'C':
            kosong += 100;
            break;
        case 'L':
            kosong += 50;
            break;
        case 'X':
            kosong += 10;
            break;
        case 'V':
            kosong += 5;
            break;
        case 'I':
            kosong += 1;
            break;
        }
    }
    if (ahay.contains("IV"))
    {
        kosong-=2;
    }
    if (ahay.contains("IX"))
    {
        kosong-=2;
    }
    if (ahay.contains("XL"))
    {
        kosong-=20;
    }
    if (ahay.contains("XC"))
    {
        kosong-=20;
    }
    if (ahay.contains("CD"))
    {
        kosong-=200;
    }
    if (ahay.contains("CM"))
    {
        kosong-=200;
    }
        
        return (int) kosong;
    }  
    public int compareTo(Comparable z){
        
        Romawi p = (Romawi) z;
        
        if(kosong>p.kosong){
            return 1 ;
        }
        if(kosong<p.kosong){
            return -1;
                    }
        else return 0;
}
    public static Romawi findMax (Romawi[] arr)
   {
       int maxIndex = 0;
       
       for(int i = 1 ;i<arr.length;i++)
           if(arr[i].compareTo( arr[maxIndex])>0)
                   maxIndex = i;
       return arr[maxIndex];
   }
   public static Romawi findMin (Romawi[] arr)
   {
       int maxIndex = 0;
       
       for(int i = 1 ;i<arr.length;i++)
           if(arr[i].compareTo((Comparable) arr[maxIndex])<0)
                   maxIndex = i;
       return arr[maxIndex];
   }
   public static double findAverage (Romawi[] arr)
   {
       double total=0;
       for (int i = 0; i < arr.length; i++) {
           total+=arr[i].kosong;
       }
       double rata = total/arr.length;
       return rata;
   }
   public String toString(){
       return ahay;
   }
    
   
    
    
    
    
    
    @Override
    public int compareTo(Object o) {
        throw new UnsupportedOperationException("Not supported yet."); //To change body of generated methods, choose Tools | Templates.
    }
}
