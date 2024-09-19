// completed solotions link above
https://www.codewars.com/users/bsafakerpark/completed_solutions ``

// 1- Find the odd int 
public class FindOdd {
    public static int findIt(int[] a) {
      int result = 0;
        for (int num : a) {
            result ^= num;
        }
        return result;
    }
}

// 2- Convert a Number to a String!
class Kata {
  public static String numberToString(int num) {
    // Return a string of the number here!
    return Integer.toString(num);
  }
}

// 3- reversed strings
public class Kata {

public static String solution(String str) {
    StringBuilder rs = new StringBuilder(str);
    rs.reverse();
    return rs.toString();
  }

}

// 4-Fractions class
public class Fraction implements Comparable<Fraction>
{ private final long top;
  private final long bottom;
    public Fraction(long numerator, long denominator) {
    top = numerator;
    bottom = denominator;
}
public int hashCode() {return 17*Long.hashCode(top)+Long.hashCode(bottom);}    
public boolean equals(Object o) { return compareTo((Fraction)o)==0;}    
    
   public int compareTo(Fraction f2){ 
    return Long.compare(top * f2.bottom, f2.top * bottom); 
}   
    public Fraction add(Fraction f2){    
    long newNumerator = top * f2.bottom + f2.top * bottom;
    long newDenominator = bottom * f2.bottom;
    long gcd = gcd(newNumerator, newDenominator);
    return new Fraction(newNumerator / gcd, newDenominator / gcd);
}
    private long gcd(long x, long y) {
      if (y == 0) {
      return x;
    }
    return gcd(y, x % y);
    }
    //...and make this class string representable
    @Override
    public String toString() {
        return top + "/" + bottom;
    }
}

// 5- Hex Class 
public class Hex {
    private final int value;
    public Hex(int value) {
        this.value = value;
    }
    public int valueOf() {
        return value;
    }
    public String toJSON() {
        return "0x" + Integer.toHexString(value).toUpperCase();
    }
    public String toString() {
        return toJSON();
    }
    public Hex plus(Hex other) {
        return new Hex(this.value + other.value);
    }
    public Hex minus(Hex other) {
        return new Hex(this.value - other.value);
    }
    public Hex plus(int number) {
        return new Hex(this.value + number);
    }
    public Hex minus(int number) {
        return new Hex(this.value - number);
    }
    public static int parse(String string) {
        if (string.startsWith("0x") || string.startsWith("0X")) {
            return Integer.parseInt(string.substring(2), 16);
        } else {
            return Integer.parseInt(string, 16);
        }
    }
    public boolean equals(Object other) {
        if (this == other) return true;
        if (other == null || getClass() != other.getClass()) return false;
        Hex hex = (Hex) other;
        return value == hex.value;
    }
}
