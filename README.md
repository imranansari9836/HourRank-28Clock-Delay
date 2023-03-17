# HourRank-28Clock-Delay
Vernon is a working man. He needs to attend a conference, and so he has to leave his home at exactly , denoting the time in hours and minutes in a 24-hour clock. The moment he leaves, his home clock displays the correct time, .

image

He returns home after exactly  hours. It is guaranteed that he returns on the same day, hence . However, the home clock shows , which may or may not be the correct time. He suspects that the home clock is lagging, and he wishes to know the duration of time in minutes by which his home clock has been lagging.

It is guaranteed that the actual time is either the same as, or after the time displayed by the clock.

Complete the function lagDuration which takes in five integers  and returns an integer denoting the duration of time in minutes by which the clock has been lagging.

Input Format

The first line contains , the number of queries.

Each query is described by two lines. The first line contains four space-separated integers . The second line contains a single integer .

Constraints

It is guaranteed that  is strictly before 
Output Format

For each query, print a single line containing a single integer indicating the duration of time in minutes by which the clock has been lagging.

Sample Input 0

6
12 0 12 58
1
10 12 10 17
2
11 40 15 33
6
18 13 19 25
5
14 27 21 1
9
16 40 23 40
7
Sample Output 0

2
115
127
228
146
0

import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {

    // Complete the lagDuration function below.
    static int lagDuration(int h1, int m1, int h2, int m2, int k) {
        // Return an integer denoting the duration of time in minutes by which the clock has been lagging.
         int delay = (h1 + k - h2) * 60 + m1 - m2;
           return delay;
    }

    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) throws IOException {
        BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(System.getenv("OUTPUT_PATH")));

        int q = scanner.nextInt();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        for (int qItr = 0; qItr < q; qItr++) {
            String[] h1M1H2M2 = scanner.nextLine().split(" ");

            int h1 = Integer.parseInt(h1M1H2M2[0]);

            int m1 = Integer.parseInt(h1M1H2M2[1]);

            int h2 = Integer.parseInt(h1M1H2M2[2]);

            int m2 = Integer.parseInt(h1M1H2M2[3]);

            int k = scanner.nextInt();
            scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

            int result = lagDuration(h1, m1, h2, m2, k);

            bufferedWriter.write(String.valueOf(result));
            bufferedWriter.newLine();
        }

        bufferedWriter.close();

        scanner.close();
    }
}
