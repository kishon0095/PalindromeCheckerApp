import java.util.*;

public class PalindromeSystem {

    public static void main(String[] args) {

        showHeader("UC1 - Application Entry");
        System.out.println("Palindrome System Started\n");

        /* UC2 */
        showHeader("UC2 - Hardcoded Check");
        String w1 = "madam";
        System.out.println("Input : " + w1);
        System.out.println("Palindrome : " + PalindromeUtil.twoPointer(w1));
        System.out.println();

        /* UC3 */
        showHeader("UC3 - Reverse Logic");
        String w2 = "radar";
        System.out.println("Input : " + w2);
        System.out.println("Palindrome : " + PalindromeUtil.reverseCheck(w2));
        System.out.println();

        /* UC4 */
        showHeader("UC4 - Character Array");
        String w3 = "level";
        System.out.println("Input : " + w3);
        System.out.println("Palindrome : " + PalindromeUtil.arrayCheck(w3));
        System.out.println();

        /* UC5 */
        showHeader("UC5 - Stack Method");
        String w4 = "noon";
        System.out.println("Input : " + w4);
        System.out.println("Palindrome : " + PalindromeUtil.stackCheck(w4));
        System.out.println();

        /* UC6 */
        showHeader("UC6 - Queue + Stack");
        String w5 = "civic";
        System.out.println("Input : " + w5);
        System.out.println("Palindrome : " + PalindromeUtil.queueStackCheck(w5));
        System.out.println();

        /* UC7 */
        showHeader("UC7 - Deque Method");
        String w6 = "refer";
        System.out.println("Input : " + w6);
        System.out.println("Palindrome : " + PalindromeUtil.dequeCheck(w6));
        System.out.println();

        /* UC8 */
        showHeader("UC8 - LinkedList Method");
        String w7 = "level";
        System.out.println("Input : " + w7);
        System.out.println("Palindrome : " + PalindromeUtil.listCheck(w7));
        System.out.println();

        /* UC9 */
        showHeader("UC9 - Recursion Method");
        String w8 = "racecar";
        System.out.println("Input : " + w8);
        System.out.println("Palindrome : " +
                PalindromeUtil.recursiveCheck(w8,0,w8.length()-1));
        System.out.println();

        /* UC10 */
        showHeader("UC10 - Ignore Spaces & Case");
        String sentence = "A man a plan a canal Panama";
        String cleaned = sentence.replaceAll("[^A-Za-z0-9]","").toLowerCase();

        System.out.println("Original : " + sentence);
        System.out.println("Normalized : " + cleaned);
        System.out.println("Palindrome : " + PalindromeUtil.twoPointer(cleaned));
        System.out.println();

        /* UC11 */
        showHeader("UC11 - Service Class");
        PalindromeManager manager = new PalindromeManager();

        String w9 = "madam";
        System.out.println("Input : " + w9);
        System.out.println("Palindrome : " + manager.check(w9));
        System.out.println();

        /* UC12 */
        showHeader("UC12 - Strategy Pattern");
        CheckStrategy st = new StackStrategyImpl();

        String w10 = "noon";
        System.out.println("Input : " + w10);
        System.out.println("Strategy : StackStrategyImpl");
        System.out.println("Palindrome : " + st.validate(w10));
        System.out.println();

        /* UC13 */
        showHeader("UC13 - Performance Test");
        String test = "amanaplanacanalpanama";

        long start = System.nanoTime();
        boolean res = PalindromeUtil.twoPointer(test);
        long end = System.nanoTime();

        System.out.println("Input : " + test);
        System.out.println("Result : " + res);
        System.out.println("Execution Time : " + (end-start));
    }

    public static void showHeader(String title){
        System.out.println("========================================");
        System.out.println("Palindrome Management System");
        System.out.println("Version 2.0");
        System.out.println("Running : " + title);
        System.out.println("========================================");
    }
}


/* Utility Class */
class PalindromeUtil {

    /* Two pointer */
    public static boolean twoPointer(String s){
        int i = 0, j = s.length()-1;

        while(i < j){
            if(s.charAt(i) != s.charAt(j))
                return false;
            i++; j--;
        }
        return true;
    }

    /* Reverse logic */
    public static boolean reverseCheck(String s){
        String rev = "";
        for(int i=0;i<s.length();i++){
            rev = s.charAt(i) + rev;
        }
        return s.equals(rev);
    }

    /* Character array */
    public static boolean arrayCheck(String s){
        char[] a = s.toCharArray();

        for(int i=0;i<a.length/2;i++){
            if(a[i] != a[a.length-1-i])
                return false;
        }
        return true;
    }

    /* Stack */
    public static boolean stackCheck(String s){
        Stack<Character> st = new Stack<>();

        for(char c : s.toCharArray())
            st.push(c);

        for(char c : s.toCharArray())
            if(c != st.pop())
                return false;

        return true;
    }

    /* Queue + Stack */
    public static boolean queueStackCheck(String s){
        Queue<Character> q = new LinkedList<>();
        Stack<Character> st = new Stack<>();

        for(char c : s.toCharArray()){
            q.add(c);
            st.push(c);
        }

        while(!q.isEmpty()){
            if(q.remove() != st.pop())
                return false;
        }
        return true;
    }

    /* Deque */
    public static boolean dequeCheck(String s){
        Deque<Character> dq = new ArrayDeque<>();

        for(char c : s.toCharArray())
            dq.add(c);

        while(dq.size() > 1){
            if(dq.removeFirst() != dq.removeLast())
                return false;
        }
        return true;
    }

    /* LinkedList */
    public static boolean listCheck(String s){
        LinkedList<Character> list = new LinkedList<>();

        for(char c : s.toCharArray())
            list.add(c);

        while(list.size() > 1){
            if(list.removeFirst() != list.removeLast())
                return false;
        }
        return true;
    }

    /* Recursion */
    public static boolean recursiveCheck(String s,int l,int r){
        if(l >= r) return true;

        if(s.charAt(l) != s.charAt(r))
            return false;

        return recursiveCheck(s,l+1,r-1);
    }
}


/* Service Class */
class PalindromeManager {

    public boolean check(String s){
        int left = 0, right = s.length()-1;

        while(left < right){
            if(s.charAt(left) != s.charAt(right))
                return false;
            left++;
            right--;
        }
        return true;
    }
}


/* Strategy Pattern */
interface CheckStrategy{
    boolean validate(String s);
}

class StackStrategyImpl implements CheckStrategy{

    public boolean validate(String s){

        Stack<Character> st = new Stack<>();

        for(char c : s.toCharArray())
            st.push(c);

        for(char c : s.toCharArray())
            if(c != st.pop())
                return false;

        return true;
    }
}
