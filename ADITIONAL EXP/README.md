# EXPERIMENT3
## TITLE: 1.substring
```
import java.util.Scanner;

public class InsertSubstring {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter the main string: ");
        String mainString = sc.nextLine();
        System.out.print("Enter the substring to insert: ");
        String subString = sc.nextLine();
        System.out.print("Enter the position to insert the substring: ");
        int position = sc.nextInt();
        if (position < 0 || position > mainString.length()) {
            System.out.println("Invalid position!");
        } else {
            String firstPart = mainString.substring(0, position);
            String secondPart = mainString.substring(position);
            String resultString = firstPart + subString + secondPart;
            System.out.println("Resulting string: " + resultString);
        }

        sc.close();
    }
}
```
# output
<img width="411" height="117" alt="1a ouput" src="https://github.com/user-attachments/assets/177c7441-38f8-4b46-81e8-b719f1038808" />
