```java
public class main {
    public static void main(String[] args) {
        String output;
        String s =  "\\begin{comment}\n"+
        "this block should be removed\n"+
        "i.e. it need to be replaced\n"+
        "\\end{comment}\n"+
        "this block should remains.\n"+
        "\\begin{comment}\n"+
        "this should be removed too.\n"+
        "\\end{comment}";
        Matcher m = Pattern.compile("\\\\begin\\{comment(?s).*\\\\end\\{comm.*?\\}").matcher(s);
        while(m.find())
        {
            System.out.println(m.group(0));
            output = m.replaceAll("");
        }

        m = Pattern.compile("\\begin").matcher(s);
        while(m.find())
        {
            System.out.println(m.group(0));
            output = m.replaceAll("");
        }
    }
}
```
