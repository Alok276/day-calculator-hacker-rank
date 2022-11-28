
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.function.*;
import java.util.regex.*;
import java.util.stream.*;
import static java.util.stream.Collectors.joining;
import static java.util.stream.Collectors.toList;

class Result {
    public static String findDay(int month, int day, int year)
     {
        Scanner sc= new Scanner(System.in);
    
        if(year%4!=0)
        {
                int arr[]={0,31,59,90,120,151,181,212,243,273,304,334};
           String findDay[]=new String[]{"FRIDAY","SATURDAY","SUNDAY","MONDAY","TUESDAY","WEDNESDAY","THRUSDAY"};
            int a=(year/4)+year+day+arr[month-1];
            a=a%7;
            return(findDay[a]);
        }
        
else
        {
                int arr[]={0,31,60,91,121,152,182,213,244,274,305,335};
           String findDay[]=new String[]{"THRUSDAY","FRIDAY","SATURDAY","SUNDAY","MONDAY","TUESDAY","WEDNESDAY"};
            int a=(year/4)+year+day+arr[month-1];
            a=a%7;
            return(findDay[a]);
        }
        
    }

}

public class Solution {
    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));
        BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(System.getenv("OUTPUT_PATH")));

        String[] firstMultipleInput = bufferedReader.readLine().replaceAll("\\s+$", "").split(" ");

        int month = Integer.parseInt(firstMultipleInput[0]);

        int day = Integer.parseInt(firstMultipleInput[1]);

        int year = Integer.parseInt(firstMultipleInput[2]);

        String res = Result.findDay(month, day, year);

        bufferedWriter.write(res);
        bufferedWriter.newLine();

        bufferedReader.close();
        bufferedWriter.close();
    }
}
