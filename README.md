import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String str = scanner.nextLine();
        System.out.println(countHi(str));
        System.out.println(removeHi(str));
        System.out.println(replaceHi(str));
    }
    private static int countHi(String str) {
        if (str.length() < 2) {
            return 0;
        }
        if (str.substring(0, 2).equals("hi")) {
            return 1 + countHi(str.substring(2));
        }
        return countHi(str.substring(1));
    }
    private static String removeHi(String str) {
        if (str.length() < 2) {
            return str;
        }
        if (str.substring(0, 2).equals("hi")) {
            return removeHi(str.substring(2));
        }
        return str.charAt(0) + removeHi(str.substring(1));
    }
    private static String replaceHi(String str) {
        if (str.length() < 2) {
            return str;
        }
        if (str.substring(0, 2).equals("hi")) {
            return "bye" + replaceHi(str.substring(2));
        }
        return str.charAt(0) + replaceHi(str.substring(1));
    }
}
