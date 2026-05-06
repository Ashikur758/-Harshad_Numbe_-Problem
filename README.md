📘 LT #1 – Solving Problem: Harshad Number Challenge
👨‍💻 Language: Java
📌 Problem 1: Harshad Number Check
🔹 Description

A number is called a Harshad Number if it is divisible by the sum of its digits.

🔹 Code
import java.util.Scanner;

public class HarshadCheck {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int x = sc.nextInt();
        int sum = 0;
        int y = x;

        while (y > 0) {
            sum += y % 10;
            y /= 10;
        }

        if (x % sum == 0)
            System.out.println("Harshad Number");
        else
            System.out.println("Not Harshad Number");
    }
}
📌 Problem 2: LeetCode – Harshad Number
🔹 Description

Return digit sum if number is Harshad, else return -1.

🔹 Code
class Solution {
    public int sumOfTheDigitsOfHarshadNumber(int x) {
        int sum = 0;
        int y = x;

        while (y > 0) {
            sum += y % 10;
            y /= 10;
        }

        if (x % sum == 0)
            return sum;
        else
            return -1;
    }
}
📌 Problem 3: SPOJ – HARSHAD
🔹 Description

For each number, print Yes if Harshad, else No.

🔹 Code
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int t = sc.nextInt();

        while (t-- > 0) {
            int n = sc.nextInt();
            int sum = 0;
            int temp = n;

            while (temp > 0) {
                sum += temp % 10;
                temp /= 10;
            }

            if (n % sum == 0)
                System.out.println("Yes");
            else
                System.out.println("No");
        }
    }
}
📌 Problem 4: Devlali Numbers (HARSHAD Extension)
🔹 Description

A number m is Devlali if no r exists such that:

d(r) = r + digitSum(r) = m

If Devlali number is prime → Devlali Prime

🔹 Code (Simple Version)
import java.util.*;

public class Main {

    static int digitSum(int n) {
        int sum = 0;
        while (n > 0) {
            sum += n % 10;
            n /= 10;
        }
        return sum;
    }

    static boolean isPrime(int n) {
        if (n < 2) return false;
        for (int i = 2; i * i <= n; i++) {
            if (n % i == 0)
                return false;
        }
        return true;
    }

    static boolean isDevlali(int m) {
        for (int r = 1; r <= m; r++) {
            if (r + digitSum(r) == m)
                return false;
        }
        return true;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int Q = sc.nextInt();

        while (Q-- > 0) {
            int A = sc.nextInt();
            int B = sc.nextInt();

            int count = 0;

            for (int i = A; i <= B; i++) {
                if (isPrime(i) && isDevlali(i)) {
                    count++;
                }
            }

            System.out.println(count);
        }
    }
}
