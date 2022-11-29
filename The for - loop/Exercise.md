
1. Write a program that prints the product of all integer numbers from **_a_** to **_b_** (**_a_** < **_b_**).

Include **_a_** and exclude **_b_** from the product.

**Sample Input 1:**

```java
1 2
```
**Sample Output 1:**

```java
1 
```

**Sample Input 2:**

```java
6 14
```
**Sample Output 2:**

```java
51891840
```

```java
import java.util.Scanner;  
  
class Main {  
    public static void main(String[] args) {  
  
  
        Scanner scanner = new Scanner(System.in);  
        // start coding here  
        int a = scanner.nextInt();  
        int b = scanner.nextInt();  
        long multiply = 1 ;  
        for (long i = a; i < b; i++) {  
          multiply *= i;  
        }  
        System.out.println( multiply);  
  
  
  
    }  
}```


2. Write a program that reads three positive integers **a, b, n** and outputs the count of numbers divisible by **n** in the range from a to b (a < b) inclusively.

**Note:** it is possible to write this program more efficiently without any loops.

  
**Sample Input:**  

10 20 10

  
**Sample Output:**  

2

  
  
**Sample Input:**  

15 25 5

  
**Sample Output:**  

3


my solution
```java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        // start coding here
        int a = scanner.nextInt();
        int b = scanner.nextInt();
        int n = scanner.nextInt();
        int count = 0;

        for (int i = a; i <= b; i++) {
            if (i % n == 0) {
                count++;
            }

        }
        System.out.println(count);
    }
}```
### more optimized one

```java
import java.util.Scanner;
import java.util.stream.IntStream;

class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);        
        int a = scanner.nextInt();
        int b = scanner.nextInt();
        int n = scanner.nextInt();
        System.out.println(IntStream.rangeClosed(a, b).filter(i -> i % n == 0).count());
    }
}
```

### another
```java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        int a = scanner.nextInt();
        int b = scanner.nextInt();
        int n = scanner.nextInt();
        
        System.out.println(b / n - (a - 1) / n);
        /*   if you find this simple expression confusing I tried my best to explain it below:
        B / N is the count of all numbers from 1 to B divisible by N. B included.
        A - 1 / n is the count of all numbers from 1 to A(exclusive) divisible by N. -1 appears because A is excluded.
        So the difference (B/N) - ((A-1)/N) is the count of numbers divisible by N in the range from A to B inclusively.
        cheers  */ 
    }
}

```
